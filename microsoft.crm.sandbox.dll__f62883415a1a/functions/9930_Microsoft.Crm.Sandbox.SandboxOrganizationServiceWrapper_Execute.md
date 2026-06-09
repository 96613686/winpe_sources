# Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::Execute

- ea: `0x9930`
- end: `0x9943`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::Execute`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x5040`
- `0x9aa0`

## pseudocode

```c

```

## disassembly

```asm
0x9930  ldarg.1
0x9931  ldstr    aRequest// "request"
0x9936  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfNull(object argument, string name)
0x993b  ldarg.0
0x993c  ldarg.1
0x993d  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::ExecuteInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request)
0x9942  ret
```
