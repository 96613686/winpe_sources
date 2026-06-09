# <>c__DisplayClass6_0::<UpdateUsingUpdatePlan>b__0

- ea: `0x8aa00`
- end: `0x8ab1a`
- name: `<>c__DisplayClass6_0::<UpdateUsingUpdatePlan>b__0`
- size: `282`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x13990`
- `0x1ef80`
- `0x222b0`
- `0x54760`
- `0x547e0`
- `0x54c30`
- `0x66ae0`
- `0x8aa00`

## string_xrefs

- `0x8aa54`: `UpdateUsingUpdatePlan not supported for SolutionAware or OrgShareableEntities`
- `0x8aadc`: `Updated {0} rows for entity '{1}'`

## pseudocode

```c

```

## disassembly

```asm
0x8aa00  ldarg.0
0x8aa01  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity <>c__DisplayClass6_0::entity
0x8aa06  ldstr    aEntity_0// "entity"
0x8aa0b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8aa10  ldarg.0
0x8aa11  ldfld    class Microsoft.Crm.Query.FilterExpression <>c__DisplayClass6_0::filter
0x8aa16  ldstr    aFilter// "filter"
0x8aa1b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8aa20  ldarg.0
0x8aa21  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass6_0::context
0x8aa26  ldstr    aContext// "context"
0x8aa2b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8aa30  ldarg.0
0x8aa31  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity <>c__DisplayClass6_0::entity
0x8aa36  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x8aa3b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsSolutionAware()
0x8aa40  brtrue.s loc_8AA54
0x8aa42  ldarg.0
0x8aa43  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity <>c__DisplayClass6_0::entity
0x8aa48  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x8aa4d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsShareableAcrossOrgs()
0x8aa52  brfalse.s loc_8AA5F
0x8aa54  ldstr    aUpdateusingupd// "UpdateUsingUpdatePlan not supported for"...
0x8aa59  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x8aa5e  throw
0x8aa5f  ldarg.0
0x8aa60  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity <>c__DisplayClass6_0::entity
0x8aa65  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x8aa6a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x8aa6f  ldarg.0
0x8aa70  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass6_0::context
0x8aa75  newobj   instance void Microsoft.Crm.Query.ColumnSetExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8aa7a  stloc.0
0x8aa7b  ldarg.0
0x8aa7c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity <>c__DisplayClass6_0::entity
0x8aa81  ldloc.0
0x8aa82  call     void Microsoft.Crm.Platform.Server.DataEngine.EntityCrudManager::FillColumnSetForUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.Query.ColumnSetExpression columnSet)
0x8aa87  ldarg.0
0x8aa88  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass6_0::context
0x8aa8d  stloc.1
0x8aa8e  ldarg.0
0x8aa8f  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity <>c__DisplayClass6_0::entity
0x8aa94  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x8aa99  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x8aa9e  ldloc.0
0x8aa9f  ldarg.0
0x8aaa0  ldfld    class Microsoft.Crm.Query.FilterExpression <>c__DisplayClass6_0::filter
0x8aaa5  ldloc.1
0x8aaa6  newobj   instance void Microsoft.Crm.Query.UpdatePlan::.ctor(string entityPlatformName, class Microsoft.Crm.Query.ColumnSetExpression 'cs', class Microsoft.Crm.Query.FilterExpression criteria, class Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x8aaab  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x8aab0  stloc.2
0x8aab1  ldarg.0
0x8aab2  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity <>c__DisplayClass6_0::entity
0x8aab7  ldloc.2
0x8aab8  call     void Microsoft.Crm.Platform.Server.DataEngine.EntityCrudManager::SetCommandTimeoutIfConfigured(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [System.Data]System.Data.IDbCommand command)
0x8aabd  ldloc.2
0x8aabe  ldarg.0
0x8aabf  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass6_0::context
0x8aac4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x8aac9  call     int32 Microsoft.Crm.Platform.Server.DataEngine.SqlDataAccessManager::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x8aace  stloc.3
0x8aacf  ldarg.0
0x8aad0  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass6_0::context
0x8aad5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8aada  ldc.i4.s 0x1D
0x8aadc  ldstr    aUpdated0RowsFo// "Updated {0} rows for entity '{1}'"
0x8aae1  ldc.i4.2
0x8aae2  newarr   [mscorlib]System.Object
0x8aae7  dup
0x8aae8  ldc.i4.0
0x8aae9  ldloc.3
0x8aaea  box      [mscorlib]System.Int32
0x8aaef  stelem.ref
0x8aaf0  dup
0x8aaf1  ldc.i4.1
0x8aaf2  ldarg.0
0x8aaf3  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity <>c__DisplayClass6_0::entity
0x8aaf8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x8aafd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x8ab02  stelem.ref
0x8ab03  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8ab08  ldloc.3
0x8ab09  stloc.s  4
0x8ab0b  leave.s  loc_8AB17
0x8ab0d  ldloc.2
0x8ab0e  brfalse.s loc_8AB16
0x8ab10  ldloc.2
0x8ab11  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ab16  endfinally
0x8ab17  ldloc.s  4
0x8ab19  ret
```
