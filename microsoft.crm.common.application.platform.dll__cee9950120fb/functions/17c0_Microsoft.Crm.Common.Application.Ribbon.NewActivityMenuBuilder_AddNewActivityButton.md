# Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::AddNewActivityButton

- ea: `0x17c0`
- end: `0x1928`
- name: `Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::AddNewActivityButton`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x16c0`

## callees

- `0x17c0`
- `0x1930`
- `0x1990`
- `0x1b10`

## pseudocode

```c

```

## disassembly

```asm
0x17c0  ldarg.1
0x17c1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x17c6  stloc.0
0x17c7  ldarg.0
0x17c8  ldarg.1
0x17c9  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x17ce  ldloc.0
0x17cf  ldarg.0
0x17d0  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_CommandPrefix()
0x17d5  ldloc.0
0x17d6  call     string [mscorlib]System.String::Concat(string, string)
0x17db  call     instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::GetNewActivityCommand(int32 activityTypeCode, string logicalName, string commandId)
0x17e0  stloc.1
0x17e1  ldarg.3
0x17e2  ldloc.1
0x17e3  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::Add(var<u1>)
0x17e8  ldarg.0
0x17e9  ldarg.1
0x17ea  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x17ef  ldloc.0
0x17f0  call     instance string Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::GetButtonId(int32 activityTypeCode, string logicalName)
0x17f5  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::.ctor(string)
0x17fa  stloc.2
0x17fb  ldarg.0
0x17fc  ldfld    bool Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::_replaceLocalStrings
0x1801  brtrue.s loc_183B
0x1803  ldloc.0
0x1804  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1809  brtrue.s loc_183B
0x180b  ldstr    aEntitydisplayn// "{!EntityDisplayName:"
0x1810  ldloc.0
0x1811  ldstr    asc_882A// "}"
0x1816  call     string [mscorlib]System.String::Concat(string, string, string)
0x181b  stloc.3
0x181c  ldloc.2
0x181d  ldloc.3
0x181e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_Alt(string)
0x1823  ldloc.2
0x1824  ldloc.3
0x1825  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_ToolTipTitle(string)
0x182a  ldloc.2
0x182b  ldloc.3
0x182c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_LabelText(string)
0x1831  ldloc.2
0x1832  ldarg.s  5
0x1834  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_ToolTipDescription(string)
0x1839  br.s     loc_18BA
0x183b  ldarg.1
0x183c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x1841  ldarg.0
0x1842  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::_resourceCulture
0x1847  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x184c  ldarg.0
0x184d  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0x1852  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1857  stloc.s  4
0x1859  ldloc.2
0x185a  ldloc.s  4
0x185c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_Alt(string)
0x1861  ldloc.2
0x1862  ldloc.s  4
0x1864  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_ToolTipTitle(string)
0x1869  ldarg.s  5
0x186b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1870  brtrue.s loc_189B
0x1872  ldloc.2
0x1873  ldarg.0
0x1874  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::_resourceCulture
0x1879  ldarg.s  5
0x187b  ldc.i4.1
0x187c  newarr   [mscorlib]System.Object
0x1881  dup
0x1882  ldc.i4.0
0x1883  ldloc.s  4
0x1885  ldarg.0
0x1886  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::_resourceCulture
0x188b  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x1890  stelem.ref
0x1891  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1896  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_ToolTipDescription(string)
0x189b  ldarg.0
0x189c  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_IsWebClient()
0x18a1  brfalse.s loc_18AD
0x18a3  ldloc.2
0x18a4  ldloc.s  4
0x18a6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_LabelText(string)
0x18ab  br.s     loc_18BA
0x18ad  ldloc.2
0x18ae  ldloc.s  4
0x18b0  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::EscapeForOutlook(string)
0x18b5  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_LabelText(string)
0x18ba  ldloc.2
0x18bb  ldloc.1
0x18bc  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x18c1  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_Command(string)
0x18c6  ldloc.2
0x18c7  ldarg.0
0x18c8  ldloc.0
0x18c9  ldc.i4.5
0x18ca  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::GetNewEntityIconPath(string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType)
0x18cf  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_Image16by16(string)
0x18d4  ldloc.2
0x18d5  ldarg.0
0x18d6  ldloc.0
0x18d7  ldc.i4.6
0x18d8  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::GetNewEntityIconPath(string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType)
0x18dd  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_Image32by32(string)
0x18e2  ldloc.2
0x18e3  ldarg.s  4
0x18e5  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x18ea  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_Sequence(valuetype [mscorlib]System.Nullable`1<int32>)
0x18ef  ldloc.0
0x18f0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x18f5  brtrue.s loc_1904
0x18f7  ldloc.2
0x18f8  ldarg.0
0x18f9  ldloc.0
0x18fa  call     instance string Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::GetActivityEntityModernImage(string logicalName)
0x18ff  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_ModernImage(string)
0x1904  ldarg.2
0x1905  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_Children()
0x190a  ldloc.2
0x190b  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer>::Add(var<u1>)
0x1910  ldarg.0
0x1911  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_controlToCommandMap
0x1916  ldloc.2
0x1917  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_ID()
0x191c  ldloc.1
0x191d  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x1922  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1927  ret
```
