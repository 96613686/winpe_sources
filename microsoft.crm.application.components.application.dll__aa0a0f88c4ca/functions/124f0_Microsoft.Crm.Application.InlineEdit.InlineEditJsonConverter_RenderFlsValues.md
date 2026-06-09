# Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::RenderFlsValues

- ea: `0x124f0`
- end: `0x1263d`
- name: `Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::RenderFlsValues`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x12490`

## callees

- `0x124f0`
- `0x12640`
- `0x14420`
- `0x14440`
- `0x14470`

## string_xrefs

- `0x125a7`: `securedcreate`
- `0x12577`: `securedupdate`
- `0x125d7`: `securedread`

## pseudocode

```c

```

## disassembly

```asm
0x124f0  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x124f5  stloc.0
0x124f6  ldarg.0
0x124f7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x124fc  stloc.1
0x124fd  br       loc_12624
0x12502  ldloc.1
0x12503  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x12508  stloc.2
0x12509  ldarg.1
0x1250a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x1250f  ldloc.2
0x12510  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x12515  stloc.3
0x12516  ldloc.3
0x12517  ldarg.1
0x12518  call     bool Microsoft.Crm.Application.InlineEdit.PrivilegeHelper::IsAttributeSecuredRead(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata metadata, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0x1251d  stloc.s  4
0x1251f  ldloc.3
0x12520  ldarg.1
0x12521  call     bool Microsoft.Crm.Application.InlineEdit.PrivilegeHelper::IsAttributeSecuredUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata metadata, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0x12526  stloc.s  5
0x12528  ldloc.3
0x12529  call     bool Microsoft.Crm.Application.InlineEdit.PrivilegeHelper::IsAttributeSecuredCreate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata metadata)
0x1252e  stloc.s  6
0x12530  ldloc.s  4
0x12532  ldloc.s  5
0x12534  or
0x12535  ldloc.s  6
0x12537  or
0x12538  brfalse  loc_1261D
0x1253d  ldarg.2
0x1253e  ldstr    asc_F6B30// "\""
0x12543  ldloc.2
0x12544  ldstr    asc_F6B30// "\""
0x12549  call     string [mscorlib]System.String::Concat(string, string, string)
0x1254e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12553  pop
0x12554  ldarg.2
0x12555  ldstr    asc_1144A6// ":{"
0x1255a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1255f  pop
0x12560  ldloc.s  5
0x12562  brfalse.s loc_12590
0x12564  ldarg.2
0x12565  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1256a  ldstr    a01_2// "\"{0}\":\"{1}\","
0x1256f  ldc.i4.2
0x12570  newarr   [mscorlib]System.Object
0x12575  dup
0x12576  ldc.i4.0
0x12577  ldstr    aSecuredupdate// "securedupdate"
0x1257c  stelem.ref
0x1257d  dup
0x1257e  ldc.i4.1
0x1257f  ldstr    a1_0// "1"
0x12584  stelem.ref
0x12585  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1258a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1258f  pop
0x12590  ldloc.s  6
0x12592  brfalse.s loc_125C0
0x12594  ldarg.2
0x12595  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1259a  ldstr    a01_2// "\"{0}\":\"{1}\","
0x1259f  ldc.i4.2
0x125a0  newarr   [mscorlib]System.Object
0x125a5  dup
0x125a6  ldc.i4.0
0x125a7  ldstr    aSecuredcreate// "securedcreate"
0x125ac  stelem.ref
0x125ad  dup
0x125ae  ldc.i4.1
0x125af  ldstr    a1_0// "1"
0x125b4  stelem.ref
0x125b5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x125ba  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x125bf  pop
0x125c0  ldloc.s  4
0x125c2  brfalse.s loc_125FF
0x125c4  ldarg.2
0x125c5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x125ca  ldstr    a01_2// "\"{0}\":\"{1}\","
0x125cf  ldc.i4.2
0x125d0  newarr   [mscorlib]System.Object
0x125d5  dup
0x125d6  ldc.i4.0
0x125d7  ldstr    aSecuredread// "securedread"
0x125dc  stelem.ref
0x125dd  dup
0x125de  ldc.i4.1
0x125df  ldstr    a1_0// "1"
0x125e4  stelem.ref
0x125e5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x125ea  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x125ef  pop
0x125f0  ldarg.1
0x125f1  ldloc.3
0x125f2  ldarg.2
0x125f3  ldstr    asc_11422C// "*******"
0x125f8  call     void Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::WriteDataValueForAttribute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata metadata, class [mscorlib]System.Text.StringBuilder jsonBuilder, string dataValue)
0x125fd  br.s     loc_1260C
0x125ff  ldarg.1
0x12600  ldloc.3
0x12601  ldarg.2
0x12602  ldsfld   string [mscorlib]System.String::Empty
0x12607  call     void Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::WriteDataValueForAttribute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata metadata, class [mscorlib]System.Text.StringBuilder jsonBuilder, string dataValue)
0x1260c  ldarg.2
0x1260d  ldstr    asc_1144C6// "},"
0x12612  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12617  pop
0x12618  ldarg.3
0x12619  ldc.i4.1
0x1261a  stind.i1
0x1261b  br.s     loc_12624
0x1261d  ldloc.0
0x1261e  ldloc.2
0x1261f  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x12624  ldloc.1
0x12625  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1262a  brtrue   loc_12502
0x1262f  leave.s  loc_1263B
0x12631  ldloc.1
0x12632  brfalse.s loc_1263A
0x12634  ldloc.1
0x12635  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1263a  endfinally
0x1263b  ldloc.0
0x1263c  ret
```
