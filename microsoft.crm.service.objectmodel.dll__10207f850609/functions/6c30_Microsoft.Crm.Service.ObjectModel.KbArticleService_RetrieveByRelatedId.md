# Microsoft.Crm.Service.ObjectModel.KbArticleService::RetrieveByRelatedId

- ea: `0x6c30`
- end: `0x6d52`
- name: `Microsoft.Crm.Service.ObjectModel.KbArticleService::RetrieveByRelatedId`
- size: `290`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6c10`
- `0x6c20`

## callees

- `0x6c30`

## string_xrefs

- `0x6c9d`: `d:\dbs\sh\dccm2\1101_190851\cmd\5\src\Service\ObjectModel\Services\CS\KbArticleService.cs`
- `0x6d2b`: `Exception when executing Reader: {0} Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x6c30  ldnull
0x6c31  stloc.0
0x6c32  ldnull
0x6c33  stloc.1
0x6c34  ldstr    aKbarticle// "KbArticle"
0x6c39  ldarg.3
0x6c3a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6c3f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x6c44  stloc.2
0x6c45  ldloc.2
0x6c46  ldc.i4.0
0x6c47  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::set_TotalRecordCount(int32)
0x6c4c  ldarg.3
0x6c4d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x6c52  stloc.0
0x6c53  ldloc.0
0x6c54  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x6c59  ldloc.0
0x6c5a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6c5f  ldstr    aExec01// "exec {0} '{1}'"
0x6c64  ldc.i4.2
0x6c65  newarr   [mscorlib]System.Object
0x6c6a  dup
0x6c6b  ldc.i4.0
0x6c6c  ldarg.2
0x6c6d  stelem.ref
0x6c6e  dup
0x6c6f  ldc.i4.1
0x6c70  ldarga.s 1
0x6c72  ldstr    aB// "B"
0x6c77  call     instance string [mscorlib]System.Guid::ToString(string)
0x6c7c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6c81  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x6c86  stelem.ref
0x6c87  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6c8c  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x6c91  stloc.1
0x6c92  ldloc.1
0x6c93  ldc.i4   0xE4
0x6c98  ldstr    aRetrievebyrela// "RetrieveByRelatedId"
0x6c9d  ldstr    aDDbsShDccm2110_0// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x6ca2  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x6ca7  stloc.s  4
0x6ca9  br.s     loc_6CFF
0x6cab  ldarg.3
0x6cac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6cb1  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KbArticle::.ctor(valuetype [mscorlib]System.Guid)
0x6cb6  stloc.3
0x6cb7  ldloc.3
0x6cb8  ldstr    aKbarticleid// "kbarticleid"
0x6cbd  ldloc.s  4
0x6cbf  ldstr    aKbarticleid// "kbarticleid"
0x6cc4  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x6cc9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6cce  ldloc.3
0x6ccf  ldstr    aTitle// "title"
0x6cd4  ldloc.s  4
0x6cd6  ldstr    aTitle// "title"
0x6cdb  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x6ce0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6ce5  ldloc.2
0x6ce6  ldloc.3
0x6ce7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x6cec  pop
0x6ced  ldloc.2
0x6cee  dup
0x6cef  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_TotalRecordCount()
0x6cf4  stloc.s  5
0x6cf6  ldloc.s  5
0x6cf8  ldc.i4.1
0x6cf9  add
0x6cfa  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::set_TotalRecordCount(int32)
0x6cff  ldloc.s  4
0x6d01  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x6d06  brtrue.s loc_6CAB
0x6d08  ldloc.s  4
0x6d0a  callvirt instance void [System.Data]System.Data.IDataReader::Close()
0x6d0f  leave.s  loc_6D1D
0x6d11  ldloc.s  4
0x6d13  brfalse.s loc_6D1C
0x6d15  ldloc.s  4
0x6d17  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d1c  endfinally
0x6d1d  leave.s  loc_6D50
0x6d1f  stloc.s  6
0x6d21  ldloc.s  6
0x6d23  ldarg.3
0x6d24  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6d29  ldc.i4.s 0x1D
0x6d2b  ldstr    aExceptionWhenE// "Exception when executing Reader: {0} Ex"...
0x6d30  ldc.i4.2
0x6d31  newarr   [mscorlib]System.Object
0x6d36  dup
0x6d37  ldc.i4.0
0x6d38  ldloc.1
0x6d39  stelem.ref
0x6d3a  dup
0x6d3b  ldc.i4.1
0x6d3c  ldloc.s  6
0x6d3e  stelem.ref
0x6d3f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6d44  rethrow
0x6d46  ldloc.0
0x6d47  brfalse.s loc_6D4F
0x6d49  ldloc.0
0x6d4a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x6d4f  endfinally
0x6d50  ldloc.2
0x6d51  ret
```
