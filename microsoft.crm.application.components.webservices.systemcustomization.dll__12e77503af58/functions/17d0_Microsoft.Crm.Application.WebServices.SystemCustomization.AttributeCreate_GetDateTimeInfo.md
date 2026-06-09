# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetDateTimeInfo

- ea: `0x17d0`
- end: `0x18a6`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetDateTimeInfo`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`

## callees

- `0x190`
- `0x200`
- `0x220`
- `0x17d0`
- `0x1b90`

## pseudocode

```c

```

## disassembly

```asm
0x17d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x17da  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x17df  stloc.0
0x17e0  ldarg.1
0x17e1  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata
0x17e6  stloc.1
0x17e7  ldarg.1
0x17e8  brfalse.s loc_17FD
0x17ea  ldarg.0
0x17eb  ldstr    aFormat// "format"
0x17f0  ldloc.1
0x17f1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x17f6  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x17fb  br.s     loc_1808
0x17fd  ldarg.0
0x17fe  ldstr    aFormat// "format"
0x1803  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x1808  ldarg.0
0x1809  ldstr    aBehavior// "behavior"
0x180e  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x1813  brtrue.s loc_181C
0x1815  ldarg.1
0x1816  brtrue.s loc_181C
0x1818  ldc.i4.1
0x1819  stloc.2
0x181a  br.s     loc_1865
0x181c  ldarg.1
0x181d  brfalse.s loc_1841
0x181f  ldarg.0
0x1820  ldstr    aBehavior// "behavior"
0x1825  ldloc.1
0x1826  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata::get_Behavior()
0x182b  stloc.s  5
0x182d  ldloca.s 5
0x182f  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior
0x1835  callvirt instance string [mscorlib]System.Object::ToString()
0x183a  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x183f  br.s     loc_184C
0x1841  ldarg.0
0x1842  ldstr    aBehavior// "behavior"
0x1847  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x184c  stloc.s  4
0x184e  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior
0x1853  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1858  ldloc.s  4
0x185a  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x185f  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior
0x1864  stloc.2
0x1865  ldloc.2
0x1866  ldloc.0
0x1867  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.DateTimeAttributeInfo::.ctor(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x186c  stloc.3
0x186d  ldarg.0
0x186e  ldstr    aSourcetype// "sourcetype"
0x1873  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x1878  brfalse.s loc_1886
0x187a  ldloc.3
0x187b  ldarg.0
0x187c  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDataSourceType Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetDataSourceFromParameterBag(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag)
0x1881  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_SourceType(int32)
0x1886  ldarg.0
0x1887  ldstr    aFormuladefinit// "formuladefinition"
0x188c  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x1891  brfalse.s loc_18A4
0x1893  ldloc.3
0x1894  ldarg.0
0x1895  ldstr    aFormuladefinit// "formuladefinition"
0x189a  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x189f  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_FormulaDefinition(string)
0x18a4  ldloc.3
0x18a5  ret
```
