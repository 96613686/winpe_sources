# Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveEmailTemplatesCommand::.ctor_0

- ea: `0x66e0`
- end: `0x67c6`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveEmailTemplatesCommand::.ctor_0`
- size: `230`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3110`
- `0x66d0`

## callees

- `0x66e0`

## string_xrefs

- `0x66fe`: `<?xml version='1.0'?><fetch><entity name='template'><attribute name='templateid'/><attribute name='templatetypecode'/><attribute name='title'/><attribute name='subject'/><attribute name='subjectpresentationxml'/>`
- `0x670a`: `<attribute name='description'/><attribute name='createdby'/><attribute name='createdon'/><attribute name='openrate'/><attribute name='replyrate'/><attribute name='usedcount'/><attribute name='isrecommended'/><filter type='and'>`
- `0x675a`: `<condition attribute='templatetypecode' operator='eq' value='`
- `0x678a`: `<condition attribute='templatetypecode' operator='eq' value='8'/>`

## pseudocode

```c

```

## disassembly

```asm
0x66e0  ldarg.0
0x66e1  ldstr    aContact// "contact"
0x66e6  ldarg.3
0x66e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x66ec  ldarg.3
0x66ed  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.ExecuteFetchCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x66f2  ldc.i4   0x400
0x66f7  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x66fc  stloc.0
0x66fd  ldloc.0
0x66fe  ldstr    aXmlVersion10Fe// "<?xml version='1.0'?><fetch><entity nam"...
0x6703  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6708  pop
0x6709  ldloc.0
0x670a  ldstr    aAttributeNameD// "<attribute name='description'/><attribu"...
0x670f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6714  pop
0x6715  ldarg.1
0x6716  ldc.i4.0
0x6717  ble.s    loc_6749
0x6719  ldloc.0
0x671a  ldstr    aFilterTypeAndC// "<filter type='and'><condition attribute"...
0x671f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6724  pop
0x6725  ldloc.0
0x6726  ldarga.s 1
0x6728  ldstr    aD// "D"
0x672d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6732  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x6737  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x673c  pop
0x673d  ldloc.0
0x673e  ldstr    aFilter// "'/></filter>"
0x6743  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6748  pop
0x6749  ldloc.0
0x674a  ldstr    aFilterTypeOr// "<filter type='or'>"
0x674f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6754  pop
0x6755  ldarg.2
0x6756  ldc.i4.8
0x6757  beq.s    loc_6789
0x6759  ldloc.0
0x675a  ldstr    aConditionAttri// "<condition attribute='templatetypecode'"...
0x675f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6764  pop
0x6765  ldloc.0
0x6766  ldarga.s 2
0x6768  ldstr    aD// "D"
0x676d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6772  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x6777  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x677c  pop
0x677d  ldloc.0
0x677e  ldstr    asc_AD02// "'/>"
0x6783  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6788  pop
0x6789  ldloc.0
0x678a  ldstr    aConditionAttri_0// "<condition attribute='templatetypecode'"...
0x678f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6794  pop
0x6795  ldloc.0
0x6796  ldstr    aFilterFilter// "</filter></filter>"
0x679b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x67a0  pop
0x67a1  ldloc.0
0x67a2  ldstr    aOrderAttribute// "<order attribute='title' descending='fa"...
0x67a7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x67ac  pop
0x67ad  ldloc.0
0x67ae  ldstr    aEntityFetch// "</entity></fetch>"
0x67b3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x67b8  pop
0x67b9  ldarg.0
0x67ba  ldloc.0
0x67bb  callvirt instance string [mscorlib]System.Object::ToString()
0x67c0  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.ExecuteFetchCommand::CreateFetchRequest(string)
0x67c5  ret
```
