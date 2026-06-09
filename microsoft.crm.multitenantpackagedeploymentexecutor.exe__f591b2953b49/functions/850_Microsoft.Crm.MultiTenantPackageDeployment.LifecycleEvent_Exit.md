# Microsoft.Crm.MultiTenantPackageDeployment.LifecycleEvent::Exit

- ea: `0x850`
- end: `0x862`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.LifecycleEvent::Exit`
- size: `18`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x600`
- `0x650`

## callees

- `0x1d50`

## pseudocode

```c

```

## disassembly

```asm
0x850  call     string [mscorlib]System.Environment::get_CommandLine()
0x855  ldstr    aExit// "exit"
0x85a  ldarg.0
0x85b  ldarg.1
0x85c  call     void Microsoft.Crm.MultiTenantPackageDeployment.SetupTelemetry::PDLifecycle(string cmdline, string eventName, string reason, [opt] class [mscorlib]System.Exception ex)
0x861  ret
```
