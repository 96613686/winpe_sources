# Microsoft.Crm.Metadata.EntityService::DeleteFilterTemplate

- ea: `0x37250`
- end: `0x3739d`
- name: `Microsoft.Crm.Metadata.EntityService::DeleteFilterTemplate`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x36c60`

## callees

- `0x37250`

## string_xrefs

- `0x3735b`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\EntityService.cs`
- `0x3733f`: `delete from SavedQueryBase Where ReturnedTypeCode = @returnedtypecode and (QueryType = @querytype or QueryType = @querytype2)`
- `0x37356`: `DeleteFilterTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x37250  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SavedQueryService::.ctor()
0x37255  ldstr    aSavedquery// "SavedQuery"
0x3725a  ldarg.2
0x3725b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x37260  stloc.0
0x37261  ldloc.0
0x37262  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x37267  ldstr    aQuerytype// "querytype"
0x3726c  ldc.i4.0
0x3726d  ldc.i4   0x2000
0x37272  box      [mscorlib]System.Int32
0x37277  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x3727c  pop
0x3727d  ldloc.0
0x3727e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x37283  ldstr    aReturnedtypeco// "returnedtypecode"
0x37288  ldc.i4.0
0x37289  ldarg.1
0x3728a  box      [mscorlib]System.Int32
0x3728f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x37294  pop
0x37295  ldloc.0
0x37296  ldarg.2
0x37297  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3729c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x372a1  stloc.1
0x372a2  br.s     loc_372D6
0x372a4  ldloc.1
0x372a5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x372aa  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SavedQuery
0x372af  ldstr    aSavedqueryid// "savedqueryid"
0x372b4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x372b9  unbox.any [mscorlib]System.Guid
0x372be  ldstr    aSavedquery// "SavedQuery"
0x372c3  ldarg.2
0x372c4  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x372c9  stloc.2
0x372ca  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::.ctor()
0x372cf  ldloc.2
0x372d0  ldarg.2
0x372d1  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::DeleteAllLocLabel(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x372d6  ldloc.1
0x372d7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x372dc  brtrue.s loc_372A4
0x372de  leave.s  loc_372F1
0x372e0  ldloc.1
0x372e1  isinst   [mscorlib]System.IDisposable
0x372e6  stloc.3
0x372e7  ldloc.3
0x372e8  brfalse.s loc_372F0
0x372ea  ldloc.3
0x372eb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x372f0  endfinally
0x372f1  ldarg.2
0x372f2  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x372f7  stloc.s  4
0x372f9  ldloc.s  4
0x372fb  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x37300  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x37305  dup
0x37306  ldstr    aReturnedtypeco_0// "@returnedtypecode"
0x3730b  ldarg.1
0x3730c  box      [mscorlib]System.Int32
0x37311  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x37316  pop
0x37317  dup
0x37318  ldstr    aQuerytype_0// "@querytype"
0x3731d  ldc.i4   0x2000
0x37322  box      [mscorlib]System.Int32
0x37327  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3732c  pop
0x3732d  ldstr    aQuerytype2// "@querytype2"
0x37332  ldc.i4.s 0x10
0x37334  box      [mscorlib]System.Int32
0x37339  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3733e  pop
0x3733f  ldstr    aDeleteFromSave// "delete from SavedQueryBase Where Return"...
0x37344  stloc.s  5
0x37346  ldloc.s  4
0x37348  ldloc.s  5
0x3734a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x3734f  ldloc.s  4
0x37351  ldc.i4   0x16E9
0x37356  ldstr    aDeletefilterte// "DeleteFilterTemplate"
0x3735b  ldstr    aDA1SSrcCoreObj_3// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0x37360  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x37365  pop
0x37366  leave.s  loc_3739C
0x37368  stloc.s  6
0x3736a  ldloc.s  6
0x3736c  ldarg.2
0x3736d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x37372  ldc.i4.s 0x19
0x37374  ldstr    aExceptionWhenE_0// "Exception when executing non-query: {0}"...
0x37379  ldc.i4.2
0x3737a  newarr   [mscorlib]System.Object
0x3737f  dup
0x37380  ldc.i4.0
0x37381  ldloc.s  4
0x37383  stelem.ref
0x37384  dup
0x37385  ldc.i4.1
0x37386  ldloc.s  6
0x37388  stelem.ref
0x37389  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3738e  rethrow
0x37390  ldloc.s  4
0x37392  brfalse.s loc_3739B
0x37394  ldloc.s  4
0x37396  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3739b  endfinally
0x3739c  ret
```
