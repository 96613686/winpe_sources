# Microsoft.Crm.Asynchronous.QueueManager::RemoveSpecialTransition

- ea: `0xa950`
- end: `0xa976`
- name: `Microsoft.Crm.Asynchronous.QueueManager::RemoveSpecialTransition`
- size: `38`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x50a0`
- `0x53b0`
- `0xa7a0`

## callees

- `0xa950`
- `0xa990`

## pseudocode

```c

```

## disassembly

```asm
0xa950  ldarg.0
0xa951  ldfld    object Microsoft.Crm.Asynchronous.QueueManager::_specialTransitionsLock
0xa956  stloc.0
0xa957  ldc.i4.0
0xa958  stloc.1
0xa959  ldloc.0
0xa95a  ldloca.s 1
0xa95c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xa961  ldarg.0
0xa962  ldarg.1
0xa963  ldarg.2
0xa964  call     instance void Microsoft.Crm.Asynchronous.QueueManager::RemoveSpecialTransitionNoLock(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid eventId)
0xa969  leave.s  loc_A975
0xa96b  ldloc.1
0xa96c  brfalse.s loc_A974
0xa96e  ldloc.0
0xa96f  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xa974  endfinally
0xa975  ret
```
