# Microsoft.Crm.Common.Application.Platform.ActivityBase::GetPartyListProperties

- ea: `0x28c0`
- end: `0x2937`
- name: `Microsoft.Crm.Common.Application.Platform.ActivityBase::GetPartyListProperties`
- size: `119`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2a30`
- `0x6d90`

## callees

- `0x28c0`

## pseudocode

```c

```

## disassembly

```asm
0x28c0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x28c5  stloc.0
0x28c6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x28cb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x28d0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x28d5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x28da  ldarg.0
0x28db  ldc.i4.1
0x28dc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x28e1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x28e6  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x28eb  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x28f0  stloc.1
0x28f1  br.s     loc_291A
0x28f3  ldloc.1
0x28f4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x28f9  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0x28fe  stloc.2
0x28ff  ldloc.2
0x2900  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x2905  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x290a  ldc.i4.s 0xB
0x290c  bne.un.s loc_291A
0x290e  ldloc.0
0x290f  ldloc.2
0x2910  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x2915  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x291a  ldloc.1
0x291b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2920  brtrue.s loc_28F3
0x2922  leave.s  loc_2935
0x2924  ldloc.1
0x2925  isinst   [mscorlib]System.IDisposable
0x292a  stloc.3
0x292b  ldloc.3
0x292c  brfalse.s loc_2934
0x292e  ldloc.3
0x292f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2934  endfinally
0x2935  ldloc.0
0x2936  ret
```
