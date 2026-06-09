# Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::Create

- ea: `0x98a0`
- end: `0x98b3`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::Create`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x5040`
- `0x99f0`

## pseudocode

```c

```

## disassembly

```asm
0x98a0  ldarg.1
0x98a1  ldstr    aEntity// "entity"
0x98a6  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfNull(object argument, string name)
0x98ab  ldarg.0
0x98ac  ldarg.1
0x98ad  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::CreateInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x98b2  ret
```
