# Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context

- ea: `0x22d0`
- end: `0x22ea`
- name: `Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context`
- size: `26`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f70`
- `0x2030`
- `0x21f0`
- `0x2240`
- `0x2480`
- `0x2680`
- `0x2780`

## callees

- `0x22d0`

## string_xrefs

- `0x22d8`: `Context is not initialized or already cleaned up.`

## pseudocode

```c

```

## disassembly

```asm
0x22d0  ldarg.0
0x22d1  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::_context
0x22d6  brtrue.s loc_22E3
0x22d8  ldstr    aContextIsNotIn// "Context is not initialized or already c"...
0x22dd  call     class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxFault::GetFaultException(string)
0x22e2  throw
0x22e3  ldarg.0
0x22e4  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::_context
0x22e9  ret
```
