# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetAttributeDataTypeInfo

- ea: `0x7bb0`
- end: `0x7c1d`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetAttributeDataTypeInfo`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x7bb0`
- `0x7cf0`
- `0x89f0`

## pseudocode

```c

```

## disassembly

```asm
0x7bb0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x7bb5  stloc.0
0x7bb6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7bbb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x7bc0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x7bc5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7bca  ldarg.1
0x7bcb  ldc.i4.1
0x7bcc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x7bd1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x7bd6  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.IDictionary::GetEnumerator()
0x7bdb  stloc.1
0x7bdc  br.s     loc_7C0E
0x7bde  ldloc.1
0x7bdf  callvirt instance object [mscorlib]System.Collections.IDictionaryEnumerator::get_Value()
0x7be4  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0x7be9  stloc.2
0x7bea  ldloc.2
0x7beb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x7bf0  stloc.3
0x7bf1  ldarg.0
0x7bf2  ldloc.2
0x7bf3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x7bf8  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x7bfd  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::GetAttributeDataTypeName(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType attributeType)
0x7c02  stloc.s  4
0x7c04  ldarg.0
0x7c05  ldloc.0
0x7c06  ldloc.3
0x7c07  ldloc.s  4
0x7c09  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::AppendAttributeTypeInfo(class [mscorlib]System.Text.StringBuilder sb, string attributeName, string dataType)
0x7c0e  ldloc.1
0x7c0f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7c14  brtrue.s loc_7BDE
0x7c16  ldloc.0
0x7c17  callvirt instance string [mscorlib]System.Object::ToString()
0x7c1c  ret
```
