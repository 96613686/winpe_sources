# Microsoft.Crm.Service.ObjectModel.SubjectService::GetSubjectHierarchy

- ea: `0xb250`
- end: `0xb381`
- name: `Microsoft.Crm.Service.ObjectModel.SubjectService::GetSubjectHierarchy`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6230`

## callees

- `0xb250`

## string_xrefs

- `0xb2b2`: `d:\dbs\sh\dccm2\1101_190851\cmd\5\src\Service\ObjectModel\Services\CS\SubjectService.cs`
- `0xb31a`: `Exception when executing reader: {0} Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0xb250  ldnull
0xb251  stloc.0
0xb252  ldnull
0xb253  stloc.1
0xb254  ldstr    aSubject_0// "Subject"
0xb259  ldarg.1
0xb25a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xb25f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0xb264  stloc.2
0xb265  ldarg.1
0xb266  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0xb26b  stloc.0
0xb26c  ldloc.0
0xb26d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xb272  ldloc.0
0xb273  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb278  ldstr    aExecPGetsubjec// "exec p_GetSubjectHierarchy '{0}'"
0xb27d  ldc.i4.1
0xb27e  newarr   [mscorlib]System.Object
0xb283  dup
0xb284  ldc.i4.0
0xb285  ldarga.s 0
0xb287  ldstr    aB// "B"
0xb28c  call     instance string [mscorlib]System.Guid::ToString(string)
0xb291  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb296  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xb29b  stelem.ref
0xb29c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb2a1  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0xb2a6  stloc.1
0xb2a7  ldloc.1
0xb2a8  ldc.i4   0x8E
0xb2ad  ldstr    aGetsubjecthier// "GetSubjectHierarchy"
0xb2b2  ldstr    aDDbsShDccm2110_2// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0xb2b7  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xb2bc  stloc.s  5
0xb2be  br.s     loc_B2EE
0xb2c0  ldarg.1
0xb2c1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xb2c6  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Subject::.ctor(valuetype [mscorlib]System.Guid)
0xb2cb  stloc.s  4
0xb2cd  ldloc.s  4
0xb2cf  ldstr    aSubjectid// "subjectid"
0xb2d4  ldloc.s  5
0xb2d6  ldstr    aSubjectid// "subjectid"
0xb2db  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xb2e0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xb2e5  ldloc.2
0xb2e6  ldloc.s  4
0xb2e8  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0xb2ed  pop
0xb2ee  ldloc.s  5
0xb2f0  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xb2f5  brtrue.s loc_B2C0
0xb2f7  ldloc.s  5
0xb2f9  callvirt instance void [System.Data]System.Data.IDataReader::Close()
0xb2fe  leave.s  loc_B30C
0xb300  ldloc.s  5
0xb302  brfalse.s loc_B30B
0xb304  ldloc.s  5
0xb306  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb30b  endfinally
0xb30c  leave.s  loc_B33F
0xb30e  stloc.s  6
0xb310  ldloc.s  6
0xb312  ldarg.1
0xb313  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xb318  ldc.i4.s 0x1D
0xb31a  ldstr    aExceptionWhenE_0// "Exception when executing reader: {0} Ex"...
0xb31f  ldc.i4.2
0xb320  newarr   [mscorlib]System.Object
0xb325  dup
0xb326  ldc.i4.0
0xb327  ldloc.1
0xb328  stelem.ref
0xb329  dup
0xb32a  ldc.i4.1
0xb32b  ldloc.s  6
0xb32d  stelem.ref
0xb32e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb333  rethrow
0xb335  ldloc.0
0xb336  brfalse.s loc_B33E
0xb338  ldloc.0
0xb339  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0xb33e  endfinally
0xb33f  ldloc.2
0xb340  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xb345  newarr   [mscorlib]System.Guid
0xb34a  stloc.3
0xb34b  ldc.i4.0
0xb34c  stloc.s  7
0xb34e  br.s     loc_B375
0xb350  ldloc.3
0xb351  ldloc.s  7
0xb353  ldloc.2
0xb354  ldloc.s  7
0xb356  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0xb35b  ldstr    aSubjectid// "subjectid"
0xb360  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xb365  unbox.any [mscorlib]System.Guid
0xb36a  stelem   [mscorlib]System.Guid
0xb36f  ldloc.s  7
0xb371  ldc.i4.1
0xb372  add
0xb373  stloc.s  7
0xb375  ldloc.s  7
0xb377  ldloc.2
0xb378  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xb37d  blt.s    loc_B350
0xb37f  ldloc.3
0xb380  ret
```
