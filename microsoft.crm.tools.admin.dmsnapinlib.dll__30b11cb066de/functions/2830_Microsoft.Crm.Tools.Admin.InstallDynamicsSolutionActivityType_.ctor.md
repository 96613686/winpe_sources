# Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionActivityType::.ctor

- ea: `0x2830`
- end: `0x283e`
- name: `Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x2831`: `InstallDynamicsSolution`

## pseudocode

```c

```

## disassembly

```asm
0x2830  ldarg.0
0x2831  ldstr    aInstalldynamic// "InstallDynamicsSolution"
0x2836  ldc.i4.1
0x2837  ldc.i4.1
0x2838  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionActivityType>::.ctor(string, bool, bool)
0x283d  ret
```
