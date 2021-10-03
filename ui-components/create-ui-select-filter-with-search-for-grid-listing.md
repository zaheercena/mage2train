# Create a Search UI-Select listing filter

Here we show how to make the listing filters searcheable.

![Magento2 Kata - Searcheable and Multiple listing filter](searcheable-and-multiple-filter.png)

## Kata Solution

### UI Component XML Difinition

`view/adminhtml/ui_component/magekata_ui_listing.xml`:

```xml
<?xml version="1.0" encoding="UTF-8"?>

<listing xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:noNamespaceSchemaLocation="urn:magento:module:Magento_Ui:etc/ui_configuration.xsd">
    <listingToolbar name="listing_top">
        ...
        <filters name="listing_filters">
            <argument name="data" xsi:type="array">
                <item name="config" xsi:type="array">
                    <item name="templates" xsi:type="array">
                        <item name="filters" xsi:type="array">
                            <item name="select" xsi:type="array">
                                <item name="component" xsi:type="string">Magento_Ui/js/form/element/ui-select</item>
                                <item name="template" xsi:type="string">ui/grid/filters/elements/ui-select</item>
                                <item name="filterOptions" xsi:type="boolean">true</item>
                            </item>
                        </item>
                    </item>
                </item>
            </argument>
        </filters>
    </listingToolbar>
    <columns name="my_listing_grid_columns">
        <column name="region_id" component="Magento_Ui/js/form/element/ui-select">
            <argument name="data" xsi:type="array">
                <item name="options" xsi:type="object">Glushko\MageKata\Model\Source\Region</item>
                <item name="config" xsi:type="array">
                    <item name="filter" xsi:type="string">select</item>
                    <item name="source" xsi:type="string">premise_region_id</item>
                    <item name="filterOptions" xsi:type="boolean">true</item>
                    <item name="multiple" xsi:type="boolean">true</item>
                    <item name="showCheckbox" xsi:type="boolean">true</item>
                    <item name="disableLabel" xsi:type="boolean">true</item>
                    <item name="dataType" xsi:type="string">select</item>
                    <item name="component" xsi:type="string">Magento_Ui/js/grid/columns/select</item>
                    <item name="label" xsi:type="string" translate="true">State/Region</item>
                    <item name="sortOrder" xsi:type="number">100</item>
                </item>
            </argument>
        </column>
    </columns>
</listing>

```
