# Microsoft.Crm.Asynchronous.JobDataAccess::ReadJobParameters

- ea: `0x23b0`
- end: `0x23fd`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::ReadJobParameters`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2dc0`
- `0x3200`
- `0x3290`

## callees

- `0x23b0`

## pseudocode

```c

```

## disassembly

```asm
0x23b0  ldsflda  valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Asynchronous.JobDataAccess::_readJobParameters
0x23b5  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x23ba  brtrue.s loc_23F2
0x23bc  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x23c1  stloc.0
0x23c2  ldloc.0
0x23c3  ldstr    aIfExistsSelect_0// "IF EXISTS (SELECT * from sys.columns WH"...
0x23c8  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x23cd  ldc.i4.1
0x23ce  ldarg.0
0x23cf  ldloc.0
0x23d0  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x23d5  unbox.any [mscorlib]System.Int32
0x23da  ceq
0x23dc  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x23e1  stsfld   valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Asynchronous.JobDataAccess::_readJobParameters
0x23e6  leave.s  loc_23F2
0x23e8  ldloc.0
0x23e9  brfalse.s loc_23F1
0x23eb  ldloc.0
0x23ec  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23f1  endfinally
0x23f2  ldsflda  valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Asynchronous.JobDataAccess::_readJobParameters
0x23f7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x23fc  ret
```
