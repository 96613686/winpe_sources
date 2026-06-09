# Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::Update

- ea: `0x98f0`
- end: `0x9903`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::Update`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x5040`
- `0x9a60`

## pseudocode

```c

```

## disassembly

```asm
0x98f0  ldarg.1
0x98f1  ldstr    aEntity// "entity"
0x98f6  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfNull(object argument, string name)
0x98fb  ldarg.0
0x98fc  ldarg.1
0x98fd  call     instance void Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::UpdateInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x9902  ret
```
