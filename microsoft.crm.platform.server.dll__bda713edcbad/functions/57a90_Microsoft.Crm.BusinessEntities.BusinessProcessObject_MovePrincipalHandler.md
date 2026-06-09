# Microsoft.Crm.BusinessEntities.BusinessProcessObject::MovePrincipalHandler

- ea: `0x57a90`
- end: `0x57c5a`
- name: `Microsoft.Crm.BusinessEntities.BusinessProcessObject::MovePrincipalHandler`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x8df80`

## callees

- `0x13990`
- `0x13b10`
- `0x18520`
- `0x18530`
- `0x18540`
- `0x18800`
- `0x1ae30`
- `0x574d0`
- `0x57a90`
- `0x5b500`
- `0x5cf40`
- `0x61160`
- `0x61180`
- `0x66af0`
- `0x67cf0`

## string_xrefs

- `0x57a99`: `MovePrincipalHandler`
- `0x57abb`: `non-user-owned entity can not participate in MovePrincipal operation`

## pseudocode

```c

```

## disassembly

```asm
0x57a90  ldc.i4.1
0x57a91  ldarg.s  4
0x57a93  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x57a98  ldarg.3
0x57a99  ldstr    aMoveprincipalh// "MovePrincipalHandler"
0x57a9e  ldc.i4.0
0x57a9f  ldnull
0x57aa0  call     void Microsoft.Crm.BusinessEntities.BusinessProcessObject::CaptureQueryDetailsUsingEntityMetadata(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.DataPerformance.InitiatorType initiator, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, string operationName, [opt] bool isLeadingWildCardQuery, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> securityQueryDetails)
0x57aa5  ldarg.3
0x57aa6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x57aab  ldarg.s  4
0x57aad  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x57ab2  stloc.0
0x57ab3  ldarg.3
0x57ab4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsUserOwned()
0x57ab9  brtrue.s loc_57ACB
0x57abb  ldstr    aNonUserOwnedEn// "non-user-owned entity can not participa"...
0x57ac0  ldc.i4   0x8004023B
0x57ac5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x57aca  throw
0x57acb  ldloc.0
0x57acc  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x57ad1  ldstr    aOwnerid// "ownerid"
0x57ad6  ldc.i4.0
0x57ad7  ldarg.1
0x57ad8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x57add  box      [mscorlib]System.Guid
0x57ae2  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x57ae7  pop
0x57ae8  ldloc.0
0x57ae9  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x57aee  ldstr    aOwneridtype// "owneridtype"
0x57af3  ldc.i4.0
0x57af4  ldarg.1
0x57af5  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x57afa  box      [mscorlib]System.Int32
0x57aff  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x57b04  pop
0x57b05  ldarg.s  4
0x57b07  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x57b0c  ldstr    aUserquery// "UserQuery"
0x57b11  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x57b16  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x57b1b  ldarg.3
0x57b1c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x57b21  bne.un.s loc_57B74
0x57b23  ldloc.0
0x57b24  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x57b29  ldstr    aQuerytype// "querytype"
0x57b2e  ldc.i4.1
0x57b2f  ldc.i4   0x200
0x57b34  box      [mscorlib]System.Int32
0x57b39  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x57b3e  pop
0x57b3f  ldloc.0
0x57b40  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x57b45  ldstr    aQuerytype// "querytype"
0x57b4a  ldc.i4.1
0x57b4b  ldc.i4   0x100
0x57b50  box      [mscorlib]System.Int32
0x57b55  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x57b5a  pop
0x57b5b  ldloc.0
0x57b5c  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x57b61  ldstr    aQuerytype// "querytype"
0x57b66  ldc.i4.1
0x57b67  ldc.i4.s 0x10
0x57b69  box      [mscorlib]System.Int32
0x57b6e  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x57b73  pop
0x57b74  ldarg.3
0x57b75  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x57b7a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x57b7f  stloc.1
0x57b80  ldloc.0
0x57b81  ldarg.3
0x57b82  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x57b87  ldarg.s  4
0x57b89  newobj   instance void Microsoft.Crm.Query.ColumnSetExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57b8e  callvirt instance void Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class Microsoft.Crm.Query.ColumnSetExpression value)
0x57b93  ldloc.0
0x57b94  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x57b99  ldloc.1
0x57b9a  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x57b9f  ldarg.3
0x57ba0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x57ba5  ldarg.s  4
0x57ba7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x57bac  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x57bb1  stloc.2
0x57bb2  ldarg.0
0x57bb3  ldloc.2
0x57bb4  ldloc.0
0x57bb5  ldc.i4.1
0x57bb6  ldarg.s  4
0x57bb8  call     instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::DoRetrieveMultipleWithoutPaging(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection entities, class Microsoft.Crm.Query.EntityExpression entityExp, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget queryTarget, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57bbd  ldarg.s  4
0x57bbf  ldc.i4.1
0x57bc0  newobj   instance void Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class Microsoft.Crm.BusinessEntities.ExecutionContext context, bool switchAuditingInfo)
0x57bc5  stloc.3
0x57bc6  ldloc.2
0x57bc7  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x57bcc  stloc.s  4
0x57bce  br.s     loc_57C2F
0x57bd0  ldloc.s  4
0x57bd2  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x57bd7  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x57bdc  stloc.s  5
0x57bde  ldarg.s  4
0x57be0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x57be5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0x57bea  ldloc.s  5
0x57bec  ldloc.1
0x57bed  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x57bf2  unbox.any [mscorlib]System.Guid
0x57bf7  ldarg.3
0x57bf8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x57bfd  ldarg.s  4
0x57bff  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x57c04  stloc.s  6
0x57c06  ldarg.0
0x57c07  ldloc.s  6
0x57c09  ldarg.2
0x57c0a  ldarg.s  4
0x57c0c  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::Assign(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class Microsoft.Crm.BusinessEntities.SecurityPrincipal assignee, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57c11  ldarg.s  4
0x57c13  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x57c18  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0x57c1d  leave.s  loc_57C2F
0x57c1f  pop
0x57c20  ldarg.s  4
0x57c22  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x57c27  ldc.i4.0
0x57c28  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::RollbackTransaction(bool)
0x57c2d  rethrow
0x57c2f  ldloc.s  4
0x57c31  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x57c36  brtrue.s loc_57BD0
0x57c38  leave.s  loc_57C59
0x57c3a  ldloc.s  4
0x57c3c  isinst   [mscorlib]System.IDisposable
0x57c41  stloc.s  7
0x57c43  ldloc.s  7
0x57c45  brfalse.s loc_57C4E
0x57c47  ldloc.s  7
0x57c49  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x57c4e  endfinally
0x57c4f  ldloc.3
0x57c50  brfalse.s loc_57C58
0x57c52  ldloc.3
0x57c53  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x57c58  endfinally
0x57c59  ret
```
