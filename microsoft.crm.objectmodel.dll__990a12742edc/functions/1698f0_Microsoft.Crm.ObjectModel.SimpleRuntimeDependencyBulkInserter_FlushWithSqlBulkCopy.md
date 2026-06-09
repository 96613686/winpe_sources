# Microsoft.Crm.ObjectModel.SimpleRuntimeDependencyBulkInserter::FlushWithSqlBulkCopy

- ea: `0x1698f0`
- end: `0x1699e2`
- name: `Microsoft.Crm.ObjectModel.SimpleRuntimeDependencyBulkInserter::FlushWithSqlBulkCopy`
- size: `242`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x16a030`
- `0x16a160`
- `0x16a2c0`

## callees

- `0x1698f0`

## string_xrefs

- `0x169902`: `RequiredComponentNodeId`
- `0x169907`: `RequiredComponentNodeId`
- `0x169918`: `RequiredComponentType`
- `0x16991d`: `RequiredComponentType`
- `0x16992e`: `DependentComponentNodeId`
- `0x169933`: `DependentComponentNodeId`
- `0x169944`: `DependentComponentType`
- `0x169949`: `DependentComponentType`
- `0x16995a`: `RequiredComponentModifiedTime`
- `0x16995f`: `RequiredComponentModifiedTime`
- `0x169970`: `CreatedTime`
- `0x169975`: `CreatedTime`

## pseudocode

```c

```

## disassembly

```asm
0x1698f0  ldarg.1
0x1698f1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_Connection()
0x1698f6  callvirt instance class [System.Data]System.Data.SqlClient.SqlBulkCopy [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateBulkCopy()
0x1698fb  stloc.0
0x1698fc  ldloc.0
0x1698fd  callvirt instance class [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMappingCollection [System.Data]System.Data.SqlClient.SqlBulkCopy::get_ColumnMappings()
0x169902  ldstr    aRequiredcompon_6// "RequiredComponentNodeId"
0x169907  ldstr    aRequiredcompon_6// "RequiredComponentNodeId"
0x16990c  callvirt instance class [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMapping [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMappingCollection::Add(string, string)
0x169911  pop
0x169912  ldloc.0
0x169913  callvirt instance class [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMappingCollection [System.Data]System.Data.SqlClient.SqlBulkCopy::get_ColumnMappings()
0x169918  ldstr    aRequiredcompon_7// "RequiredComponentType"
0x16991d  ldstr    aRequiredcompon_7// "RequiredComponentType"
0x169922  callvirt instance class [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMapping [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMappingCollection::Add(string, string)
0x169927  pop
0x169928  ldloc.0
0x169929  callvirt instance class [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMappingCollection [System.Data]System.Data.SqlClient.SqlBulkCopy::get_ColumnMappings()
0x16992e  ldstr    aDependentcompo_7// "DependentComponentNodeId"
0x169933  ldstr    aDependentcompo_7// "DependentComponentNodeId"
0x169938  callvirt instance class [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMapping [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMappingCollection::Add(string, string)
0x16993d  pop
0x16993e  ldloc.0
0x16993f  callvirt instance class [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMappingCollection [System.Data]System.Data.SqlClient.SqlBulkCopy::get_ColumnMappings()
0x169944  ldstr    aDependentcompo_8// "DependentComponentType"
0x169949  ldstr    aDependentcompo_8// "DependentComponentType"
0x16994e  callvirt instance class [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMapping [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMappingCollection::Add(string, string)
0x169953  pop
0x169954  ldloc.0
0x169955  callvirt instance class [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMappingCollection [System.Data]System.Data.SqlClient.SqlBulkCopy::get_ColumnMappings()
0x16995a  ldstr    aRequiredcompon_8// "RequiredComponentModifiedTime"
0x16995f  ldstr    aRequiredcompon_8// "RequiredComponentModifiedTime"
0x169964  callvirt instance class [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMapping [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMappingCollection::Add(string, string)
0x169969  pop
0x16996a  ldloc.0
0x16996b  callvirt instance class [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMappingCollection [System.Data]System.Data.SqlClient.SqlBulkCopy::get_ColumnMappings()
0x169970  ldstr    aCreatedtime// "CreatedTime"
0x169975  ldstr    aCreatedtime// "CreatedTime"
0x16997a  callvirt instance class [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMapping [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMappingCollection::Add(string, string)
0x16997f  pop
0x169980  ldloc.0
0x169981  callvirt instance class [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMappingCollection [System.Data]System.Data.SqlClient.SqlBulkCopy::get_ColumnMappings()
0x169986  ldstr    aDependencyid_0// "DependencyId"
0x16998b  ldstr    aDependencyid_0// "DependencyId"
0x169990  callvirt instance class [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMapping [System.Data]System.Data.SqlClient.SqlBulkCopyColumnMappingCollection::Add(string, string)
0x169995  pop
0x169996  ldloc.0
0x169997  ldc.i4   0x9C40
0x16999c  callvirt instance void [System.Data]System.Data.SqlClient.SqlBulkCopy::set_BatchSize(int32)
0x1699a1  ldloc.0
0x1699a2  ldloc.0
0x1699a3  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlBulkCopy::get_BulkCopyTimeout()
0x1699a8  ldc.i4   0x12C
0x1699ad  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x1699b2  callvirt instance void [System.Data]System.Data.SqlClient.SqlBulkCopy::set_BulkCopyTimeout(int32)
0x1699b7  ldloc.0
0x1699b8  ldarg.0
0x1699b9  call     instance string [Microsoft.Crm]Microsoft.Crm.BusinessEntities.SimpleBulkInserterWithType::get_TableName()
0x1699be  callvirt instance void [System.Data]System.Data.SqlClient.SqlBulkCopy::set_DestinationTableName(string)
0x1699c3  ldarg.1
0x1699c4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_Connection()
0x1699c9  ldloc.0
0x1699ca  ldarg.0
0x1699cb  call     instance class [System.Data]System.Data.DataTable [Microsoft.Crm]Microsoft.Crm.BusinessEntities.SimpleBulkInserterWithType::get_InsertTable()
0x1699d0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::WriteBulkCopyToDatabase(class [System.Data]System.Data.SqlClient.SqlBulkCopy, class [System.Data]System.Data.DataTable)
0x1699d5  leave.s  loc_1699E1
0x1699d7  ldloc.0
0x1699d8  brfalse.s loc_1699E0
0x1699da  ldloc.0
0x1699db  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1699e0  endfinally
0x1699e1  ret
```
