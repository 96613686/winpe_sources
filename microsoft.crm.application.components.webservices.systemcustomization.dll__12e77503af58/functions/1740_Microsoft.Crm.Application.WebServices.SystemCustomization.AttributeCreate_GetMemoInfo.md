# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetMemoInfo

- ea: `0x1740`
- end: `0x17c4`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetMemoInfo`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`

## callees

- `0x200`
- `0x240`
- `0x270`
- `0x1740`

## pseudocode

```c

```

## disassembly

```asm
0x1740  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1745  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x174a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x174f  stloc.0
0x1750  ldarg.1
0x1751  brfalse.s loc_175B
0x1753  ldarg.1
0x1754  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x1759  br.s     loc_176B
0x175b  ldarg.0
0x175c  ldstr    aFormat// "format"
0x1761  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MemoAttributeFormats::get_None()
0x1766  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x176b  stloc.1
0x176c  ldloc.1
0x176d  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MemoAttributeFormats::get_EmailBody()
0x1772  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1777  brtrue.s loc_1789
0x1779  ldloc.1
0x177a  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MemoAttributeFormats::get_InternalExtentData()
0x177f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1784  brfalse.s loc_1791
0x1786  ldarg.1
0x1787  brfalse.s loc_1791
0x1789  ldloc.1
0x178a  ldloc.0
0x178b  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.MemoAttributeInfo::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1790  ret
0x1791  ldarg.1
0x1792  brtrue.s loc_17A2
0x1794  ldarg.0
0x1795  ldstr    aLength// "length"
0x179a  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x179f  stloc.2
0x17a0  br.s     loc_17BB
0x17a2  ldarg.1
0x17a3  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MemoAttributeMetadata
0x17a8  stloc.3
0x17a9  ldarg.0
0x17aa  ldstr    aLength// "length"
0x17af  ldloc.3
0x17b0  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.TextAttributeMetadata::get_MaxLength()
0x17b5  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name, int32 defaultValue)
0x17ba  stloc.2
0x17bb  ldloc.2
0x17bc  ldloc.1
0x17bd  ldloc.0
0x17be  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.MemoAttributeInfo::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17c3  ret
```
