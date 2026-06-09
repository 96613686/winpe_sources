# Microsoft.Crm.Sandbox.SandboxSdkClientCache`1::.ctor

- ea: `0x9c00`
- end: `0x9c1e`
- name: `Microsoft.Crm.Sandbox.SandboxSdkClientCache`1::.ctor`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x8180`

## pseudocode

```c

```

## disassembly

```asm
0x9c00  ldarg.0
0x9c01  call     instance void [mscorlib]System.Object::.ctor()
0x9c06  ldarg.0
0x9c07  newobj   instance void Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::.ctor()
0x9c0c  call     instance void class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::set_WorkerConfiguration(class Microsoft.Crm.Sandbox.SandboxWorkerConfiguration)
0x9c11  ldarg.0
0x9c12  ldc.i4.0
0x9c13  newobj   instance void [mscorlib]System.Threading.AutoResetEvent::.ctor(bool)
0x9c18  call     instance void class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::set_AutoEventCleanupThread(class [mscorlib]System.Threading.AutoResetEvent)
0x9c1d  ret
```
