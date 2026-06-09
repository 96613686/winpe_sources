# Microsoft.Crm.Application.WebServices.WorkflowWebService::SetRegardingObjectDefault

- ea: `0x8e00`
- end: `0x8f00`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::SetRegardingObjectDefault`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4b20`

## callees

- `0x8e00`

## pseudocode

```c

```

## disassembly

```asm
0x8e00  ldarg.1
0x8e01  call     bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::IsGlobalCustomOperation(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x8e06  brfalse.s loc_8E09
0x8e08  ret
0x8e09  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8e0e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x8e13  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x8e18  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8e1d  ldarg.2
0x8e1e  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::get_EntityName()
0x8e23  ldc.i4.1
0x8e24  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x8e29  stloc.0
0x8e2a  ldloc.0
0x8e2b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x8e30  ldstr    aRegardingobjec// "regardingobjectid"
0x8e35  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0x8e3a  brfalse  loc_8EFF
0x8e3f  ldarg.1
0x8e40  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IMetadataProvider [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_MetadataProvider()
0x8e45  ldarg.1
0x8e46  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0x8e4b  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IMetadataProvider::GetEntityPrimaryKeyLogicalName(string)
0x8e50  stloc.1
0x8e51  ldloc.0
0x8e52  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ReferencesFrom()
0x8e57  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x8e5c  stloc.2
0x8e5d  br.s     loc_8EDE
0x8e5f  ldloc.2
0x8e60  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8e65  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship
0x8e6a  stloc.3
0x8e6b  ldloc.3
0x8e6c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x8e71  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x8e76  ldarg.1
0x8e77  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0x8e7c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8e81  brfalse.s loc_8EDE
0x8e83  ldloc.3
0x8e84  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedAttribute()
0x8e89  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8e8e  ldloc.1
0x8e8f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8e94  brfalse.s loc_8EDE
0x8e96  ldloc.3
0x8e97  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x8e9c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8ea1  ldstr    aRegardingobjec// "regardingobjectid"
0x8ea6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8eab  brfalse.s loc_8EDE
0x8ead  ldarg.1
0x8eae  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x8eb3  ldloc.1
0x8eb4  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x8eb9  stloc.s  4
0x8ebb  ldarg.1
0x8ebc  ldc.i4.0
0x8ebd  ldc.i4.1
0x8ebe  newarr   [mscorlib]System.Object
0x8ec3  dup
0x8ec4  ldc.i4.0
0x8ec5  ldloc.s  4
0x8ec7  stelem.ref
0x8ec8  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x8ecd  stloc.s  5
0x8ecf  ldarg.2
0x8ed0  ldstr    aRegardingobjec// "regardingobjectid"
0x8ed5  ldloc.s  5
0x8ed7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x8edc  leave.s  loc_8EFF
0x8ede  ldloc.2
0x8edf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8ee4  brtrue   loc_8E5F
0x8ee9  leave.s  loc_8EFF
0x8eeb  ldloc.2
0x8eec  isinst   [mscorlib]System.IDisposable
0x8ef1  stloc.s  6
0x8ef3  ldloc.s  6
0x8ef5  brfalse.s loc_8EFE
0x8ef7  ldloc.s  6
0x8ef9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8efe  endfinally
0x8eff  ret
```
