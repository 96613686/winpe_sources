# Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupOperationQueue::PersistToDatabase

- ea: `0x84d90`
- end: `0x84f5f`
- name: `Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupOperationQueue::PersistToDatabase`
- size: `463`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x85240`
- `0x85430`
- `0x85640`

## callees

- `0x66ae0`
- `0x67cf0`
- `0x84cc0`
- `0x84ce0`
- `0x84d90`

## string_xrefs

- `0x84da6`: `INSERT INTO [dbo].[RollupJobBase]\n([SourceEntityTypeCode] \n,[RollupPropertiesId] \n,[RegardingObjectId] \n,[RegardingObjectTypeCode]) \nVALUES `
- `0x84f2a`: `RollupTriggerPlugin.RollupOperationQueue.PersistToDatabase encountered a SQL exception when inserting records : {0}`

## pseudocode

```c

```

## disassembly

```asm
0x84d90  ldarg.0
0x84d91  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupOperation> Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupOperationQueue::_queue
0x84d96  brfalse.s loc_84DA5
0x84d98  ldarg.0
0x84d99  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupOperation> Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupOperationQueue::_queue
0x84d9e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupOperation>::get_Count()
0x84da3  brtrue.s loc_84DA6
0x84da5  ret
0x84da6  ldstr    aInsertIntoDboR// "INSERT INTO [dbo].[RollupJobBase]\r\n(["...
0x84dab  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x84db0  stloc.0
0x84db1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter>::.ctor()
0x84db6  stloc.1
0x84db7  ldc.i4.0
0x84db8  stloc.2
0x84db9  ldc.i4.0
0x84dba  stloc.3
0x84dbb  br       loc_84EB5
0x84dc0  ldarg.0
0x84dc1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupOperation> Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupOperationQueue::_queue
0x84dc6  ldloc.3
0x84dc7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupOperation>::get_Item(!!T0)
0x84dcc  stloc.s  4
0x84dce  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RollupPropertiesCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RollupPropertiesCache::Instance()
0x84dd3  ldloc.s  4
0x84dd5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupOperation::get_RollupAttributeId()
0x84dda  ldarg.1
0x84ddb  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData>::LookupEntry(void, var<u1>)
0x84de0  stloc.s  5
0x84de2  ldloc.s  5
0x84de4  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RollupStateCode [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData::get_StateCode()
0x84de9  brtrue   loc_84EB1
0x84dee  ldc.i4.1
0x84def  stloc.2
0x84df0  ldloc.0
0x84df1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x84df6  ldstr    aW0X0Y0Z0// " (@w{0},@x{0},@y{0},@z{0}),"
0x84dfb  ldc.i4.1
0x84dfc  newarr   [mscorlib]System.Object
0x84e01  dup
0x84e02  ldc.i4.0
0x84e03  ldloc.3
0x84e04  box      [mscorlib]System.Int32
0x84e09  stelem.ref
0x84e0a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x84e0f  pop
0x84e10  ldloc.1
0x84e11  ldstr    aW// "@w"
0x84e16  ldloc.3
0x84e17  box      [mscorlib]System.Int32
0x84e1c  call     string [mscorlib]System.String::Concat(object, object)
0x84e21  ldloc.s  5
0x84e23  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData::get_RollupEntityTypeCode()
0x84e28  box      [mscorlib]System.Int32
0x84e2d  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x84e32  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter>::Add(var<u1>)
0x84e37  ldloc.1
0x84e38  ldstr    aX_0// "@x"
0x84e3d  ldloc.3
0x84e3e  box      [mscorlib]System.Int32
0x84e43  call     string [mscorlib]System.String::Concat(object, object)
0x84e48  ldloc.s  4
0x84e4a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupOperation::get_RollupAttributeId()
0x84e4f  box      [mscorlib]System.Guid
0x84e54  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x84e59  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter>::Add(var<u1>)
0x84e5e  ldloc.1
0x84e5f  ldstr    aY// "@y"
0x84e64  ldloc.3
0x84e65  box      [mscorlib]System.Int32
0x84e6a  call     string [mscorlib]System.String::Concat(object, object)
0x84e6f  ldloc.s  4
0x84e71  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupOperation::get_Parent()
0x84e76  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x84e7b  box      [mscorlib]System.Guid
0x84e80  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x84e85  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter>::Add(var<u1>)
0x84e8a  ldloc.1
0x84e8b  ldstr    aZ_0// "@z"
0x84e90  ldloc.3
0x84e91  box      [mscorlib]System.Int32
0x84e96  call     string [mscorlib]System.String::Concat(object, object)
0x84e9b  ldloc.s  5
0x84e9d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData::get_RollupEntityTypeCode()
0x84ea2  box      [mscorlib]System.Int32
0x84ea7  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x84eac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter>::Add(var<u1>)
0x84eb1  ldloc.3
0x84eb2  ldc.i4.1
0x84eb3  add
0x84eb4  stloc.3
0x84eb5  ldloc.3
0x84eb6  ldarg.0
0x84eb7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupOperation> Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupOperationQueue::_queue
0x84ebc  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupOperation>::get_Count()
0x84ec1  blt      loc_84DC0
0x84ec6  ldloc.2
0x84ec7  brtrue.s loc_84ECA
0x84ec9  ret
0x84eca  ldloc.0
0x84ecb  ldloc.0
0x84ecc  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x84ed1  ldc.i4.1
0x84ed2  sub
0x84ed3  ldc.i4.1
0x84ed4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Remove(int32, int32)
0x84ed9  pop
0x84eda  ldarg.1
0x84edb  ldc.i4.0
0x84edc  newobj   instance void Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class Microsoft.Crm.BusinessEntities.ExecutionContext context, bool switchAuditingInfo)
0x84ee1  stloc.s  6
0x84ee3  ldarg.1
0x84ee4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x84ee9  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand()
0x84eee  stloc.s  7
0x84ef0  ldloc.s  7
0x84ef2  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x84ef7  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x84efc  ldloc.1
0x84efd  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter>::ToArray()
0x84f02  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameterCollection::AddRange(class [System.Data]System.Data.SqlClient.SqlParameter[])
0x84f07  ldloc.s  7
0x84f09  ldloc.0
0x84f0a  callvirt instance string [mscorlib]System.Object::ToString()
0x84f0f  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x84f14  ldloc.s  7
0x84f16  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x84f1b  pop
0x84f1c  leave.s  loc_84F5E
0x84f1e  stloc.s  8
0x84f20  ldloc.s  8
0x84f22  ldarg.1
0x84f23  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x84f28  ldc.i4.s 0x1D
0x84f2a  ldstr    aRolluptriggerp// "RollupTriggerPlugin.RollupOperationQueu"...
0x84f2f  ldc.i4.1
0x84f30  newarr   [mscorlib]System.Object
0x84f35  dup
0x84f36  ldc.i4.0
0x84f37  ldloc.s  8
0x84f39  callvirt instance string [mscorlib]System.Exception::get_Message()
0x84f3e  stelem.ref
0x84f3f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x84f44  rethrow
0x84f46  ldloc.s  7
0x84f48  brfalse.s loc_84F51
0x84f4a  ldloc.s  7
0x84f4c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x84f51  endfinally
0x84f52  ldloc.s  6
0x84f54  brfalse.s loc_84F5D
0x84f56  ldloc.s  6
0x84f58  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x84f5d  endfinally
0x84f5e  ret
```
