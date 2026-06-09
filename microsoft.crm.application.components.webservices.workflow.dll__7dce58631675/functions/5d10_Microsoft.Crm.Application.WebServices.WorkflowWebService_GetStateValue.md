# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetStateValue

- ea: `0x5d10`
- end: `0x5d7e`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetStateValue`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5b30`

## callees

- `0x5d10`

## pseudocode

```c

```

## disassembly

```asm
0x5d10  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5d15  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x5d1a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x5d1f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5d24  ldarg.1
0x5d25  ldc.i4.1
0x5d26  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x5d2b  ldstr    aStatecode// "statecode"
0x5d30  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x5d35  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata
0x5d3a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IStateOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata::get_StateOptions()
0x5d3f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption>::GetEnumerator()
0x5d44  stloc.0
0x5d45  br.s     loc_5D66
0x5d47  ldloc.0
0x5d48  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption>::get_Current()
0x5d4d  stloc.1
0x5d4e  ldarg.2
0x5d4f  ldloc.1
0x5d50  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption::get_InvariantName()
0x5d55  ldc.i4.4
0x5d56  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x5d5b  brtrue.s loc_5D66
0x5d5d  ldloc.1
0x5d5e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x5d63  stloc.2
0x5d64  leave.s  loc_5D7C
0x5d66  ldloc.0
0x5d67  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5d6c  brtrue.s loc_5D47
0x5d6e  leave.s  loc_5D7A
0x5d70  ldloc.0
0x5d71  brfalse.s loc_5D79
0x5d73  ldloc.0
0x5d74  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d79  endfinally
0x5d7a  ldc.i4.0
0x5d7b  ret
0x5d7c  ldloc.2
0x5d7d  ret
```
