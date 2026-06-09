# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::CreateLinkedAttribute

- ea: `0x1ed0`
- end: `0x1fcc`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::CreateLinkedAttribute`
- size: `252`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x390`
- `0x20e0`

## callees

- `0x220`
- `0x310`
- `0x420`
- `0x1ed0`

## string_xrefs

- `0x1ee1`: `linkedattributedisplayname`
- `0x1eed`: `linkedattributeschemaname`

## pseudocode

```c

```

## disassembly

```asm
0x1ed0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ed5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1eda  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1edf  stloc.0
0x1ee0  ldarg.1
0x1ee1  ldstr    aLinkedattribut_1// "linkedattributedisplayname"
0x1ee6  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x1eeb  stloc.1
0x1eec  ldarg.1
0x1eed  ldstr    aLinkedattribut_2// "linkedattributeschemaname"
0x1ef2  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x1ef7  stloc.2
0x1ef8  ldarg.1
0x1ef9  ldstr    aRecurrencebase// "recurrenceBaseId"
0x1efe  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f03  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name, valuetype [mscorlib]System.Guid defaultValue)
0x1f08  stloc.3
0x1f09  ldloc.3
0x1f0a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f0f  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1f14  brfalse  loc_1FC6
0x1f19  ldarg.1
0x1f1a  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetAttributeInfo(class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x1f1f  stloc.s  4
0x1f21  ldloc.s  4
0x1f23  ldloc.3
0x1f24  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_EntityId(valuetype [mscorlib]System.Guid)
0x1f29  ldloc.s  4
0x1f2b  ldloc.2
0x1f2c  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetSchemaName(string)
0x1f31  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_Name(string)
0x1f36  ldstr    aDisplaynames// "displaynames"
0x1f3b  ldstr    aDisplayname// "displayname"
0x1f40  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor(string, string)
0x1f45  stloc.s  5
0x1f47  ldloc.s  4
0x1f49  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::get_DisplayNames()
0x1f4e  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::GetEnumerator()
0x1f53  stloc.s  6
0x1f55  br.s     loc_1F7A
0x1f57  ldloc.s  6
0x1f59  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1f5e  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label
0x1f63  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_LanguageCode()
0x1f68  ldloc.1
0x1f69  ldloc.0
0x1f6a  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f6f  stloc.s  7
0x1f71  ldloc.s  5
0x1f73  ldloc.s  7
0x1f75  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x1f7a  ldloc.s  6
0x1f7c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f81  brtrue.s loc_1F57
0x1f83  leave.s  loc_1F9A
0x1f85  ldloc.s  6
0x1f87  isinst   [mscorlib]System.IDisposable
0x1f8c  stloc.s  8
0x1f8e  ldloc.s  8
0x1f90  brfalse.s loc_1F99
0x1f92  ldloc.s  8
0x1f94  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f99  endfinally
0x1f9a  ldloc.s  4
0x1f9c  ldloc.s  5
0x1f9e  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_DisplayNames(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection)
0x1fa3  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeService::.ctor()
0x1fa8  ldloc.3
0x1fa9  ldloc.s  4
0x1fab  ldarg.0
0x1fac  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1fb1  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1fb6  brtrue.s loc_1FBB
0x1fb8  ldarg.0
0x1fb9  br.s     loc_1FC0
0x1fbb  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x1fc0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeService::Create(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo, valuetype [mscorlib]System.Guid)
0x1fc5  ret
0x1fc6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1fcb  ret
```
