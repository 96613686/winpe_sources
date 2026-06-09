# Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::MapInvalidSiteMapUrlsToExistingHandler

- ea: `0x23080`
- end: `0x23203`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::MapInvalidSiteMapUrlsToExistingHandler`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x23080`
- `0x63db0`

## string_xrefs

- `0x230b7`: `ImportExportXml/SiteMap/SiteMap`
- `0x23159`: `GetStartedPanePathAdminOutlook`
- `0x2316d`: `GetStartedPanePathAdminOutlook`
- `0x2318a`: `GetStartedPanePathAdminOutlook`
- `0x2319c`: `GetStartedPanePathAdminOutlook`

## pseudocode

```c

```

## disassembly

```asm
0x23080  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x23085  stloc.0
0x23086  ldloc.0
0x23087  ldstr    aImgsIco18Docmg// "/_imgs/ico_18_docmgmt.gif"
0x2308c  ldstr    aImgsDocumentma// "/_imgs/DocumentManagement_16.png"
0x23091  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x23096  ldloc.0
0x23097  ldstr    aImgsArea18Audi// "/_imgs/area/18_audit.gif"
0x2309c  ldstr    aImgsArea16Audi// "/_imgs/area/16_audit.png"
0x230a1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x230a6  ldloc.0
0x230a7  ldstr    aSolutionsOutlo// "Solutions_Outlook_Admin_Visor"
0x230ac  ldstr    aSolutionsOutlo_0// "Solutions_Outlook_Admin_Visor.html"
0x230b1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x230b6  ldarg.1
0x230b7  ldstr    aImportexportxm_47// "ImportExportXml/SiteMap/SiteMap"
0x230bc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x230c1  stloc.1
0x230c2  ldloc.1
0x230c3  brfalse  loc_231E0
0x230c8  ldloc.1
0x230c9  ldstr    aAreaGroupSubar// "Area/Group/SubArea"
0x230ce  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x230d3  stloc.2
0x230d4  ldloc.2
0x230d5  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x230da  stloc.3
0x230db  br       loc_231B5
0x230e0  ldloc.3
0x230e1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x230e6  castclass [System.Xml]System.Xml.XmlNode
0x230eb  stloc.s  4
0x230ed  ldloc.s  4
0x230ef  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x230f4  ldstr    aIcon// "Icon"
0x230f9  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x230fe  brfalse.s loc_23152
0x23100  ldloc.0
0x23101  ldloc.s  4
0x23103  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x23108  ldstr    aIcon// "Icon"
0x2310d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x23112  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x23117  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x2311c  brfalse.s loc_23152
0x2311e  ldloc.s  4
0x23120  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x23125  ldstr    aIcon// "Icon"
0x2312a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2312f  ldloc.0
0x23130  ldloc.s  4
0x23132  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x23137  ldstr    aIcon// "Icon"
0x2313c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x23141  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x23146  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x2314b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x23150  br.s     loc_231B5
0x23152  ldloc.s  4
0x23154  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x23159  ldstr    aGetstartedpane// "GetStartedPanePathAdminOutlook"
0x2315e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x23163  brfalse.s loc_231B5
0x23165  ldloc.0
0x23166  ldloc.s  4
0x23168  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2316d  ldstr    aGetstartedpane// "GetStartedPanePathAdminOutlook"
0x23172  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x23177  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2317c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x23181  brfalse.s loc_231B5
0x23183  ldloc.s  4
0x23185  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2318a  ldstr    aGetstartedpane// "GetStartedPanePathAdminOutlook"
0x2318f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x23194  ldloc.0
0x23195  ldloc.s  4
0x23197  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2319c  ldstr    aGetstartedpane// "GetStartedPanePathAdminOutlook"
0x231a1  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x231a6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x231ab  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x231b0  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x231b5  ldloc.3
0x231b6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x231bb  brtrue   loc_230E0
0x231c0  leave.s  loc_231E0
0x231c2  ldloc.3
0x231c3  isinst   [mscorlib]System.IDisposable
0x231c8  stloc.s  5
0x231ca  ldloc.s  5
0x231cc  brfalse.s loc_231D5
0x231ce  ldloc.s  5
0x231d0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x231d5  endfinally
0x231d6  ldloc.2
0x231d7  brfalse.s loc_231DF
0x231d9  ldloc.2
0x231da  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x231df  endfinally
0x231e0  ldarg.s  6
0x231e2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x231e7  ldstr    aExecutingSolut// "Executing solution package Upgrade hand"...
0x231ec  ldc.i4.1
0x231ed  newarr   [mscorlib]System.Object
0x231f2  dup
0x231f3  ldc.i4.0
0x231f4  ldarg.s  4
0x231f6  stelem.ref
0x231f7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x231fc  ldc.i4.1
0x231fd  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x23202  ret
```
