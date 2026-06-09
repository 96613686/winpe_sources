# Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::.ctor

- ea: `0x9880`
- end: `0x989c`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::.ctor`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x9740`

## pseudocode

```c

```

## disassembly

```asm
0x9880  ldarg.0
0x9881  call     instance void [mscorlib]System.Object::.ctor()
0x9886  ldarg.0
0x9887  ldarg.1
0x9888  stfld    class Microsoft.Crm.Sandbox.ISandboxOrganizationService Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::_fullTrustService
0x988d  ldarg.0
0x988e  ldarg.2
0x988f  stfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::_proxyTypesAssembly
0x9894  ldarg.0
0x9895  ldarg.3
0x9896  stfld    object Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::_traceSettings
0x989b  ret
```
