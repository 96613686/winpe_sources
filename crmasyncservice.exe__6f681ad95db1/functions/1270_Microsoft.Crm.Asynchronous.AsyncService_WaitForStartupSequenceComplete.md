# Microsoft.Crm.Asynchronous.AsyncService::WaitForStartupSequenceComplete

- ea: `0x1270`
- end: `0x12ad`
- name: `Microsoft.Crm.Asynchronous.AsyncService::WaitForStartupSequenceComplete`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1210`
- `0x12c0`

## callees

- `0x1270`

## string_xrefs

- `0x12a1`: `Service did not finish startup sequence in expected time`

## pseudocode

```c

```

## disassembly

```asm
0x1270  ldarg.0
0x1271  ldfld    class [mscorlib]System.Threading.ManualResetEventSlim Microsoft.Crm.Asynchronous.AsyncService::_startSequenceCompleted
0x1276  callvirt instance bool [mscorlib]System.Threading.ManualResetEventSlim::get_IsSet()
0x127b  brtrue.s loc_12AC
0x127d  ldarg.0
0x127e  ldfld    class [mscorlib]System.Threading.ManualResetEventSlim Microsoft.Crm.Asynchronous.AsyncService::_startSequenceCompleted
0x1283  ldc.r8   5.0
0x128c  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x1291  stloc.0
0x1292  ldloca.s 0
0x1294  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x1299  conv.i4
0x129a  callvirt instance bool [mscorlib]System.Threading.ManualResetEventSlim::Wait(int32)
0x129f  brtrue.s loc_12AC
0x12a1  ldstr    aServiceDidNotF// "Service did not finish startup sequence"...
0x12a6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x12ab  throw
0x12ac  ret
```
