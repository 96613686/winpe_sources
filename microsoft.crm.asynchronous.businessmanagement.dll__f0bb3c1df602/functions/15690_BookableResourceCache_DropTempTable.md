# BookableResourceCache::DropTempTable

- ea: `0x15690`
- end: `0x15701`
- name: `BookableResourceCache::DropTempTable`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x14710`

## callees

- `0x8ab0`
- `0x15690`

## string_xrefs

- `0x156b6`: `d:\dbs\sh\dccm2\1101_190851\cmd\77\src\Core\ObjectModel\Async\Handlers\BusinessManagement\ResourceBookingSyncService.cs`
- `0x156b1`: `DropTempTable`
- `0x156e4`: `Drop BookableResourceCache Temp Table {0}`

## pseudocode

```c

```

## disassembly

```asm
0x15690  ldarg.1
0x15691  brfalse.s loc_15700
0x15693  ldarg.1
0x15694  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x15699  stloc.0
0x1569a  ldloc.0
0x1569b  ldstr    aDropTable0// "DROP TABLE #{0}"
0x156a0  ldarg.2
0x156a1  call     string [mscorlib]System.String::Format(string, object)
0x156a6  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x156ab  ldloc.0
0x156ac  ldc.i4   0xC34
0x156b1  ldstr    aDroptemptable// "DropTempTable"
0x156b6  ldstr    aDDbsShDccm2110_1// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x156bb  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x156c0  pop
0x156c1  leave.s  loc_156CD
0x156c3  ldloc.0
0x156c4  brfalse.s loc_156CC
0x156c6  ldloc.0
0x156c7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x156cc  endfinally
0x156cd  leave.s  loc_15700
0x156cf  stloc.1
0x156d0  ldnull
0x156d1  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x156d6  ldc.i4.6
0x156d7  ldstr    a01_2// "{0} - {1}"
0x156dc  ldc.i4.2
0x156dd  newarr   [mscorlib]System.Object
0x156e2  dup
0x156e3  ldc.i4.0
0x156e4  ldstr    aDropBookablere// "Drop BookableResourceCache Temp Table {"...
0x156e9  ldarg.2
0x156ea  call     string [mscorlib]System.String::Format(string, object)
0x156ef  stelem.ref
0x156f0  dup
0x156f1  ldc.i4.1
0x156f2  ldloc.1
0x156f3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x156f8  stelem.ref
0x156f9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x156fe  leave.s  loc_15700
0x15700  ret
```
