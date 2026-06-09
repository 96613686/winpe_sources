# Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::Delete

- ea: `0x9910`
- end: `0x992f`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::Delete`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x5060`
- `0x5080`
- `0x9a80`

## pseudocode

```c

```

## disassembly

```asm
0x9910  ldarg.1
0x9911  ldstr    aEntityname// "entityName"
0x9916  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfNullOrEmpty(string argument, string name)
0x991b  ldarg.2
0x991c  ldstr    aEntityid// "entityId"
0x9921  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid argument, string name)
0x9926  ldarg.0
0x9927  ldarg.1
0x9928  ldarg.2
0x9929  call     instance void Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::DeleteInternal(string entityName, valuetype [mscorlib]System.Guid id)
0x992e  ret
```
