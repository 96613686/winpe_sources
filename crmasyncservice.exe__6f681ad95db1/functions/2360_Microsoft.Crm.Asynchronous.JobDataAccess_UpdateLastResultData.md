# Microsoft.Crm.Asynchronous.JobDataAccess::UpdateLastResultData

- ea: `0x2360`
- end: `0x23ad`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::UpdateLastResultData`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2400`

## callees

- `0x2360`

## pseudocode

```c

```

## disassembly

```asm
0x2360  ldsflda  valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Asynchronous.JobDataAccess::_updatelastResultData
0x2365  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x236a  brtrue.s loc_23A2
0x236c  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x2371  stloc.0
0x2372  ldloc.0
0x2373  ldstr    aIfExistsSelect// "IF EXISTS (SELECT * from sys.columns WH"...
0x2378  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x237d  ldc.i4.1
0x237e  ldarg.0
0x237f  ldloc.0
0x2380  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x2385  unbox.any [mscorlib]System.Int32
0x238a  ceq
0x238c  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x2391  stsfld   valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Asynchronous.JobDataAccess::_updatelastResultData
0x2396  leave.s  loc_23A2
0x2398  ldloc.0
0x2399  brfalse.s loc_23A1
0x239b  ldloc.0
0x239c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23a1  endfinally
0x23a2  ldsflda  valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Asynchronous.JobDataAccess::_updatelastResultData
0x23a7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x23ac  ret
```
