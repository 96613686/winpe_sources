# Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::AddNewActivityButtons

- ea: `0x16c0`
- end: `0x17b3`
- name: `Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::AddNewActivityButtons`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1500`

## callees

- `0x16c0`
- `0x17c0`

## pseudocode

```c

```

## disassembly

```asm
0x16c0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16c5  ldstr    a0Section1// "{0}Section{1}"
0x16ca  ldc.i4.2
0x16cb  newarr   [mscorlib]System.Object
0x16d0  dup
0x16d1  ldc.i4.0
0x16d2  ldarg.0
0x16d3  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_IdPrefix()
0x16d8  stelem.ref
0x16d9  dup
0x16da  ldc.i4.1
0x16db  ldarg.s  5
0x16dd  box      [mscorlib]System.Int32
0x16e2  stelem.ref
0x16e3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16e8  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.MenuSection::.ctor(string)
0x16ed  stloc.0
0x16ee  ldloc.0
0x16ef  ldarg.s  4
0x16f1  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x16f6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.MenuSection::set_Sequence(valuetype [mscorlib]System.Nullable`1<int32>)
0x16fb  ldloc.0
0x16fc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_ID()
0x1701  ldstr    aControls// ".Controls"
0x1706  call     string [mscorlib]System.String::Concat(string, string)
0x170b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Controls::.ctor(string)
0x1710  stloc.1
0x1711  ldloc.0
0x1712  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_Children()
0x1717  ldloc.1
0x1718  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer>::Add(var<u1>)
0x171d  ldc.i4.s 0xA
0x171f  stloc.2
0x1720  ldstr    aResourcesEntit// "$Resources(EntityDisplayName):"
0x1725  stloc.3
0x1726  ldstr    aMscrmJewelNewS// "Mscrm_Jewel_New_SubMenu_ToolTipDescript"...
0x172b  stloc.s  4
0x172d  ldarg.0
0x172e  ldfld    bool Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::_replaceLocalStrings
0x1733  brtrue.s loc_173F
0x1735  ldloc.3
0x1736  ldloc.s  4
0x1738  call     string [mscorlib]System.String::Concat(string, string)
0x173d  br.s     loc_175A
0x173f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1744  ldstr    aMscrmJewelNewS// "Mscrm_Jewel_New_SubMenu_ToolTipDescript"...
0x1749  ldarg.0
0x174a  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::_resourceCulture
0x174f  ldarg.0
0x1750  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0x1755  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::TryGetCultureString(string, class [mscorlib]System.Globalization.CultureInfo, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x175a  stloc.s  5
0x175c  ldarg.3
0x175d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::GetEnumerator()
0x1762  stloc.s  6
0x1764  br.s     loc_1781
0x1766  ldloc.s  6
0x1768  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Current()
0x176d  stloc.s  7
0x176f  ldarg.0
0x1770  ldloc.s  7
0x1772  ldloc.1
0x1773  ldarg.2
0x1774  ldloc.2
0x1775  ldloc.s  5
0x1777  call     instance void Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::AddNewActivityButton(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata activityMetadata, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Controls menuControls, class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition> commands, int32 buttonSequence, string tooltipDescriptionResourceString)
0x177c  ldloc.2
0x177d  ldc.i4.s 0xA
0x177f  add
0x1780  stloc.2
0x1781  ldloc.s  6
0x1783  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1788  brtrue.s loc_1766
0x178a  leave.s  loc_1798
0x178c  ldloc.s  6
0x178e  brfalse.s loc_1797
0x1790  ldloc.s  6
0x1792  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1797  endfinally
0x1798  ldloc.1
0x1799  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_Children()
0x179e  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer>::get_Count()
0x17a3  ldc.i4.0
0x17a4  ble.s    loc_17B2
0x17a6  ldarg.1
0x17a7  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_Children()
0x17ac  ldloc.0
0x17ad  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer>::Add(var<u1>)
0x17b2  ret
```
