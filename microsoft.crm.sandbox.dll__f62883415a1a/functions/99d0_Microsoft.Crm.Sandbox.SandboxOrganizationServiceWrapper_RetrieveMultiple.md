# Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::RetrieveMultiple

- ea: `0x99d0`
- end: `0x99e3`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::RetrieveMultiple`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x5040`
- `0x9b50`

## pseudocode

```c

```

## disassembly

```asm
0x99d0  ldarg.1
0x99d1  ldstr    aQuery// "query"
0x99d6  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfNull(object argument, string name)
0x99db  ldarg.0
0x99dc  ldarg.1
0x99dd  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::RetrieveMultipleInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase query)
0x99e2  ret
```
