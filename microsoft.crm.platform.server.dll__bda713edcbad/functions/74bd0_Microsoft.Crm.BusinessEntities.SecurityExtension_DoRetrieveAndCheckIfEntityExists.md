# Microsoft.Crm.BusinessEntities.SecurityExtension::DoRetrieveAndCheckIfEntityExists

- ea: `0x74bd0`
- end: `0x74cde`
- name: `Microsoft.Crm.BusinessEntities.SecurityExtension::DoRetrieveAndCheckIfEntityExists`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x64b40`

## callees

- `0x13eb0`
- `0x184b0`
- `0x18520`
- `0x18540`
- `0x18680`
- `0x18700`
- `0x18800`
- `0x1aa60`
- `0x1ae00`
- `0x1afa0`
- `0x1ef80`
- `0x1fc10`
- `0x240d0`
- `0x5d570`
- `0x5dba0`
- `0x66b00`
- `0x66b10`
- `0x74930`
- `0x74bd0`
- `0x84b20`
- `0x84b90`

## string_xrefs

- `0x74c22`: `ActivityPartyServicebaseFactory`

## pseudocode

```c

```

## disassembly

```asm
0x74bd0  ldc.i4.0
0x74bd1  stloc.0
0x74bd2  ldarg.0
0x74bd3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x74bd8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x74bdd  ldarg.1
0x74bde  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x74be3  stloc.1
0x74be4  ldloc.1
0x74be5  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x74bea  ldarg.0
0x74beb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x74bf0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x74bf5  ldc.i4.0
0x74bf6  ldarg.0
0x74bf7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x74bfc  box      [mscorlib]System.Guid
0x74c01  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x74c06  pop
0x74c07  ldloc.1
0x74c08  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x74c0d  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x74c12  call     class Microsoft.Crm.BusinessEntities.ICrmSecurityExtensionFactory Microsoft.Crm.BusinessEntities.CrmBaseSecurityExtensionFactory::get_Instance()
0x74c17  ldarg.0
0x74c18  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x74c1d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x74c22  ldstr    aActivitypartys// "ActivityPartyServicebaseFactory"
0x74c27  call     object Microsoft.Crm.BusinessEntities.BusinessProcessObject::BusinessProcessReflectionUtiltity(string typeName)
0x74c2c  callvirt instance class Microsoft.Crm.BusinessEntities.ICrmExtension Microsoft.Crm.BusinessEntities.ICrmSecurityExtensionFactory::Get(string platformName, object activityPartyServicebaseFactory)
0x74c31  castclass Microsoft.Crm.BusinessEntities.SecurityExtension
0x74c36  ldarg.1
0x74c37  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x74c3c  ldloc.1
0x74c3d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.EntityExpression::get_Entity()
0x74c42  ldloc.1
0x74c43  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x74c48  ldarg.1
0x74c49  ldloc.1
0x74c4a  callvirt instance bool Microsoft.Crm.Query.EntityExpression::get_NoLock()
0x74c4f  ldnull
0x74c50  ldc.i4.0
0x74c51  ldloca.s 0
0x74c53  ldc.i4.1
0x74c54  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.BusinessEntities.SecurityExtension::CreateSecurityFilter(valuetype [mscorlib]System.Guid user, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, class Microsoft.Crm.Query.FilterExpression existingCriteria, class Microsoft.Crm.BusinessEntities.ExecutionContext context, bool noLock, class Microsoft.Crm.Query.EntitySecurityPOAattributes entitySecurityPOAattributes, valuetype Microsoft.Crm.BusinessEntities.LinkEntityType linkEntityType, [out] valuetype Microsoft.Crm.BusinessEntities.RetrieveMultipleSecuritySqlFormat& securitySqlFormat, bool forRetrieve)
0x74c59  stloc.2
0x74c5a  ldloc.0
0x74c5b  ldc.i4.1
0x74c5c  bne.un.s loc_74C75
0x74c5e  ldloc.2
0x74c5f  callvirt instance class Microsoft.Crm.Query.ConditionExpressionCollection Microsoft.Crm.Query.FilterExpression::get_Conditions()
0x74c64  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.ConditionExpression>::get_Count()
0x74c69  ldc.i4.1
0x74c6a  ble.s    loc_74C75
0x74c6c  ldloc.1
0x74c6d  ldloc.2
0x74c6e  callvirt instance void Microsoft.Crm.Query.EntityExpression::set_SecurityCriteria(class Microsoft.Crm.Query.FilterExpression value)
0x74c73  br.s     loc_74C81
0x74c75  ldloc.1
0x74c76  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x74c7b  ldloc.2
0x74c7c  callvirt instance void Microsoft.Crm.Query.FilterExpression::AddFilter(class Microsoft.Crm.Query.FilterExpression childFilter)
0x74c81  ldarg.1
0x74c82  ldc.i4.1
0x74c83  newobj   instance void Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::.ctor(class Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget queryTarget)
0x74c88  ldloc.1
0x74c89  newobj   instance void Microsoft.Crm.Query.SelectPlan::.ctor(class Microsoft.Crm.Query.ICrmSqlSelectCommandStrategy strategy, class Microsoft.Crm.Query.EntityExpression entity)
0x74c8e  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x74c93  stloc.3
0x74c94  ldarg.1
0x74c95  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x74c9a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x74c9f  ldarg.1
0x74ca0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x74ca5  ldloc.3
0x74ca6  ldarg.1
0x74ca7  call     class [System.Data]System.Data.IDataReader Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteQuery(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x74cac  stloc.s  4
0x74cae  ldloc.s  4
0x74cb0  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x74cb5  stloc.s  5
0x74cb7  leave.s  loc_74CDB
0x74cb9  ldloc.s  4
0x74cbb  brfalse.s loc_74CC4
0x74cbd  ldloc.s  4
0x74cbf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x74cc4  endfinally
0x74cc5  ldarg.1
0x74cc6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x74ccb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x74cd0  endfinally
0x74cd1  ldloc.3
0x74cd2  brfalse.s loc_74CDA
0x74cd4  ldloc.3
0x74cd5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x74cda  endfinally
0x74cdb  ldloc.s  5
0x74cdd  ret
```
