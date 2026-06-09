# Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::get_Context

- ea: `0x2b80`
- end: `0x2b9a`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::get_Context`
- size: `26`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2980`
- `0x29f0`

## callees

- `0x2b80`

## string_xrefs

- `0x2b88`: `Context is not initialized or already cleaned up.`

## pseudocode

```c

```

## disassembly

```asm
0x2b80  ldarg.0
0x2b81  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_context
0x2b86  brtrue.s loc_2B93
0x2b88  ldstr    aContextIsNotIn// "Context is not initialized or already c"...
0x2b8d  call     class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxFault::GetFaultException(string)
0x2b92  throw
0x2b93  ldarg.0
0x2b94  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_context
0x2b99  ret
```
