# Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::BackgroundThread

- ea: `0x5350`
- end: `0x5374`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::BackgroundThread`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5350`

## callees

- `0x5350`
- `0x5380`

## pseudocode

```c

```

## disassembly

```asm
0x5350  ldsfld   class [mscorlib]System.Threading.AutoResetEvent Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::_autoEventBackgroundThread
0x5355  ldc.i4.0
0x5356  ldc.i4.0
0x5357  ldc.i4.s 0x1E
0x5359  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x535e  ldc.i4.0
0x535f  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(valuetype [mscorlib]System.TimeSpan, bool)
0x5364  brtrue.s loc_5373
0x5366  ldarg.0
0x5367  unbox.any [mscorlib]System.Int32
0x536c  call     void Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::TryAddAccounts(int32 minReadyAccounts)
0x5371  br.s     Microsoft.Crm.Sandbox.SandboxWorkerAccountManager__BackgroundThread
0x5373  ret
```
