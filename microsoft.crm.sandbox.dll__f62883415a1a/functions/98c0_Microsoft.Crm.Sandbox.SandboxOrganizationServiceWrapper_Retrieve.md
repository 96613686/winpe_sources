# Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::Retrieve

- ea: `0x98c0`
- end: `0x98eb`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::Retrieve`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x5040`
- `0x5060`
- `0x5080`
- `0x9a20`

## pseudocode

```c

```

## disassembly

```asm
0x98c0  ldarg.1
0x98c1  ldstr    aEntityname// "entityName"
0x98c6  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfNullOrEmpty(string argument, string name)
0x98cb  ldarg.2
0x98cc  ldstr    aEntityid// "entityId"
0x98d1  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid argument, string name)
0x98d6  ldarg.3
0x98d7  ldstr    aColumnset// "columnSet"
0x98dc  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfNull(object argument, string name)
0x98e1  ldarg.0
0x98e2  ldarg.1
0x98e3  ldarg.2
0x98e4  ldarg.3
0x98e5  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::RetrieveInternal(string entityName, valuetype [mscorlib]System.Guid id, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet columnSet)
0x98ea  ret
```
