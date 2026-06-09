# Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::AddCustomActivityButtons

- ea: `0xff0`
- end: `0x10a0`
- name: `Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::AddCustomActivityButtons`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf50`

## callees

- `0xff0`
- `0x10a0`

## pseudocode

```c

```

## disassembly

```asm
0xff0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xff5  ldstr    a0Section1// "{0}Section{1}"
0xffa  ldc.i4.2
0xffb  newarr   [mscorlib]System.Object
0x1000  dup
0x1001  ldc.i4.0
0x1002  ldarg.0
0x1003  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_IdPrefix()
0x1008  stelem.ref
0x1009  dup
0x100a  ldc.i4.1
0x100b  ldarg.s  5
0x100d  box      [mscorlib]System.Int32
0x1012  stelem.ref
0x1013  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1018  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.MenuSection::.ctor(string)
0x101d  stloc.0
0x101e  ldloc.0
0x101f  ldarg.s  4
0x1021  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1026  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.MenuSection::set_Sequence(valuetype [mscorlib]System.Nullable`1<int32>)
0x102b  ldloc.0
0x102c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_ID()
0x1031  ldstr    aControls// ".Controls"
0x1036  call     string [mscorlib]System.String::Concat(string, string)
0x103b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Controls::.ctor(string)
0x1040  stloc.1
0x1041  ldloc.0
0x1042  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_Children()
0x1047  ldloc.1
0x1048  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer>::Add(var<u1>)
0x104d  ldc.i4.s 0xA
0x104f  stloc.2
0x1050  ldarg.3
0x1051  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::GetEnumerator()
0x1056  stloc.3
0x1057  br.s     loc_1071
0x1059  ldloc.3
0x105a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Current()
0x105f  stloc.s  4
0x1061  ldarg.0
0x1062  ldloc.s  4
0x1064  ldloc.1
0x1065  ldarg.2
0x1066  ldloc.2
0x1067  call     instance void Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::AddCustomActivityButton(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata activityMetadata, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Controls menuControls, class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition> commands, int32 buttonSequence)
0x106c  ldloc.2
0x106d  ldc.i4.s 0xA
0x106f  add
0x1070  stloc.2
0x1071  ldloc.3
0x1072  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1077  brtrue.s loc_1059
0x1079  leave.s  loc_1085
0x107b  ldloc.3
0x107c  brfalse.s loc_1084
0x107e  ldloc.3
0x107f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1084  endfinally
0x1085  ldloc.1
0x1086  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_Children()
0x108b  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer>::get_Count()
0x1090  ldc.i4.0
0x1091  ble.s    loc_109F
0x1093  ldarg.1
0x1094  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_Children()
0x1099  ldloc.0
0x109a  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer>::Add(var<u1>)
0x109f  ret
```
