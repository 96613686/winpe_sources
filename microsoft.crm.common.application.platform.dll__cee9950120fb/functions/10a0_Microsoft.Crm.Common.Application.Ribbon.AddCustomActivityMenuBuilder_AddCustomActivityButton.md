# Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::AddCustomActivityButton

- ea: `0x10a0`
- end: `0x11c4`
- name: `Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::AddCustomActivityButton`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xff0`

## callees

- `0x10a0`
- `0x11d0`

## pseudocode

```c

```

## disassembly

```asm
0x10a0  ldarg.1
0x10a1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x10a6  stloc.0
0x10a7  ldarg.0
0x10a8  ldarg.1
0x10a9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x10ae  ldarg.0
0x10af  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_CommandPrefix()
0x10b4  ldloc.0
0x10b5  call     string [mscorlib]System.String::Concat(string, string)
0x10ba  call     instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::GetAddActivityCommand(string activityTypeName, string commandId)
0x10bf  stloc.1
0x10c0  ldarg.3
0x10c1  ldloc.1
0x10c2  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::Add(var<u1>)
0x10c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10cc  ldstr    a01// "{0}{1}"
0x10d1  ldc.i4.2
0x10d2  newarr   [mscorlib]System.Object
0x10d7  dup
0x10d8  ldc.i4.0
0x10d9  ldarg.0
0x10da  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_IdPrefix()
0x10df  stelem.ref
0x10e0  dup
0x10e1  ldc.i4.1
0x10e2  ldloc.0
0x10e3  stelem.ref
0x10e4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10e9  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::.ctor(string)
0x10ee  stloc.2
0x10ef  ldarg.0
0x10f0  ldfld    bool Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::_replaceLocalStrings
0x10f5  brtrue.s loc_1120
0x10f7  ldloc.0
0x10f8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10fd  brtrue.s loc_1120
0x10ff  ldloc.2
0x1100  ldloc.2
0x1101  ldstr    aEntitydisplayn// "{!EntityDisplayName:"
0x1106  ldloc.0
0x1107  ldstr    asc_882A// "}"
0x110c  call     string [mscorlib]System.String::Concat(string, string, string)
0x1111  dup
0x1112  stloc.3
0x1113  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_LabelText(string)
0x1118  ldloc.3
0x1119  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_Alt(string)
0x111e  br.s     loc_1149
0x1120  ldloc.2
0x1121  ldloc.2
0x1122  ldarg.1
0x1123  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x1128  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x112d  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x1132  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1137  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x113c  dup
0x113d  stloc.3
0x113e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_LabelText(string)
0x1143  ldloc.3
0x1144  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_Alt(string)
0x1149  ldloc.2
0x114a  ldloc.2
0x114b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::get_LabelText()
0x1150  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_ToolTipTitle(string)
0x1155  ldloc.2
0x1156  ldstr    asc_882E// ""
0x115b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_ToolTipDescription(string)
0x1160  ldloc.2
0x1161  ldloc.1
0x1162  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x1167  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_Command(string)
0x116c  ldloc.2
0x116d  ldarg.0
0x116e  ldloc.0
0x116f  ldc.i4.5
0x1170  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::GetNewEntityIconPath(string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType)
0x1175  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_Image16by16(string)
0x117a  ldloc.2
0x117b  ldarg.0
0x117c  ldloc.0
0x117d  ldc.i4.6
0x117e  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::GetNewEntityIconPath(string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType)
0x1183  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_Image32by32(string)
0x1188  ldloc.2
0x1189  ldarg.s  4
0x118b  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1190  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_Sequence(valuetype [mscorlib]System.Nullable`1<int32>)
0x1195  ldloc.2
0x1196  ldstr    aCustomactivity// "CustomActivity"
0x119b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Button::set_ModernImage(string)
0x11a0  ldarg.2
0x11a1  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_Children()
0x11a6  ldloc.2
0x11a7  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer>::Add(var<u1>)
0x11ac  ldarg.0
0x11ad  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_controlToCommandMap
0x11b2  ldloc.2
0x11b3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_ID()
0x11b8  ldloc.1
0x11b9  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x11be  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x11c3  ret
```
