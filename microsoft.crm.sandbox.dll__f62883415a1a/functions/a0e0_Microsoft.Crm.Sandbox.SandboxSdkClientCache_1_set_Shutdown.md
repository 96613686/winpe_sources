# Microsoft.Crm.Sandbox.SandboxSdkClientCache`1::set_Shutdown

- ea: `0xa0e0`
- end: `0xa0f7`
- name: `Microsoft.Crm.Sandbox.SandboxSdkClientCache`1::set_Shutdown`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xa0e0`

## pseudocode

```c

```

## disassembly

```asm
0xa0e0  ldarg.1
0xa0e1  brfalse.s loc_A0EF
0xa0e3  ldarg.0
0xa0e4  call     instance class [mscorlib]System.Threading.AutoResetEvent class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::get_AutoEventCleanupThread()
0xa0e9  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0xa0ee  pop
0xa0ef  ldarg.0
0xa0f0  ldarg.1
0xa0f1  stfld    bool class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_shutdown
0xa0f6  ret
```
