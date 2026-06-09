# ImportTranslationDataAccess::RemoveImportTranslationFileData

- ea: `0x20070`
- end: `0x200c6`
- name: `ImportTranslationDataAccess::RemoveImportTranslationFileData`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0xa940`

## callees

- `0x20070`

## string_xrefs

- `0x20070`: `UPDATE AsyncOperationBase SET Data = @data WHERE AsyncOperationId = @asyncOperationId`

## pseudocode

```c

```

## disassembly

```asm
0x20070  ldstr    aUpdateAsyncope// "UPDATE AsyncOperationBase SET Data = @d"...
0x20075  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x2007a  stloc.0
0x2007b  ldloc.0
0x2007c  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x20081  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x20086  dup
0x20087  ldstr    aData// "@data"
0x2008c  ldsfld   string [mscorlib]System.String::Empty
0x20091  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x20096  pop
0x20097  ldstr    aAsyncoperation// "@asyncOperationId"
0x2009c  ldarg.1
0x2009d  box      [mscorlib]System.Guid
0x200a2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x200a7  pop
0x200a8  ldarg.0
0x200a9  ldloc.0
0x200aa  ldloca.s 1
0x200ac  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x200b2  ldloc.1
0x200b3  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x200b8  pop
0x200b9  leave.s  loc_200C5
0x200bb  ldloc.0
0x200bc  brfalse.s loc_200C4
0x200be  ldloc.0
0x200bf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x200c4  endfinally
0x200c5  ret
```
