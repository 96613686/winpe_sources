# Microsoft.Crm.CrmTransaction::VerifyCommitted

- ea: `0x10510`
- end: `0x105a6`
- name: `Microsoft.Crm.CrmTransaction::VerifyCommitted`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x11c20`
- `0x11c80`

## callees

- `0xd150`
- `0xd380`
- `0xd8e0`
- `0x10510`
- `0x1a880`
- `0x1b8d0`
- `0x1eaa0`
- `0x1f4b0`

## string_xrefs

- `0x1051d`: `VerifyCommitted - Encountered disposed Transaction when it should not be disposed`
- `0x1057f`: `VerifyCommitted failed -- clearing connection pool`
- `0x10595`: `VerifyCommitted - Transaction has not been committed`

## pseudocode

```c

```

## disassembly

```asm
0x10510  ldarg.0
0x10511  ldfld    bool Microsoft.Crm.CrmTransaction::disposed
0x10516  brfalse.s loc_10528
0x10518  ldstr    aCrmtransaction// "CrmTransaction"
0x1051d  ldstr    aVerifycommitte// "VerifyCommitted - Encountered disposed "...
0x10522  newobj   instance void Microsoft.Crm.CrmObjectDisposedException::.ctor(string objectName, string message)
0x10527  throw
0x10528  ldarg.0
0x10529  ldfld    int32 Microsoft.Crm.CrmTransaction::startCount
0x1052e  brfalse.s loc_105A5
0x10530  ldarg.0
0x10531  ldfld    class [System.Data]System.Data.IDbTransaction Microsoft.Crm.CrmTransaction::transaction
0x10536  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1053b  ldarg.0
0x1053c  ldnull
0x1053d  stfld    class [System.Data]System.Data.IDbTransaction Microsoft.Crm.CrmTransaction::transaction
0x10542  ldarg.0
0x10543  ldc.i4.0
0x10544  stfld    int32 Microsoft.Crm.CrmTransaction::startCount
0x10549  ldarg.0
0x1054a  ldfld    class Microsoft.Crm.CrmDbConnection Microsoft.Crm.CrmTransaction::connection
0x1054f  callvirt instance valuetype [System.Data]System.Data.IsolationLevel Microsoft.Crm.CrmDbConnection::get_IsolationLevel()
0x10554  ldc.i4   0x1000
0x10559  beq.s    loc_1056B
0x1055b  ldarg.0
0x1055c  ldfld    class Microsoft.Crm.CrmDbConnection Microsoft.Crm.CrmTransaction::connection
0x10561  ldc.i4   0x1000
0x10566  callvirt instance void Microsoft.Crm.CrmDbConnection::SetTransactionIsolationLevel(valuetype [System.Data]System.Data.IsolationLevel il)
0x1056b  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x10570  ldc.i4.s 0x1D
0x10572  ldstr    a0// "{0}"
0x10577  ldc.i4.1
0x10578  newarr   [mscorlib]System.Object
0x1057d  dup
0x1057e  ldc.i4.0
0x1057f  ldstr    aVerifycommitte_0// "VerifyCommitted failed -- clearing conn"...
0x10584  stelem.ref
0x10585  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x1058a  ldarg.0
0x1058b  ldfld    class Microsoft.Crm.CrmDbConnection Microsoft.Crm.CrmTransaction::connection
0x10590  callvirt instance void Microsoft.Crm.CrmDbConnection::Close()
0x10595  ldstr    aVerifycommitte_1// "VerifyCommitted - Transaction has not b"...
0x1059a  ldc.i4   0x80040252
0x1059f  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message, int32 errorCode)
0x105a4  throw
0x105a5  ret
```
