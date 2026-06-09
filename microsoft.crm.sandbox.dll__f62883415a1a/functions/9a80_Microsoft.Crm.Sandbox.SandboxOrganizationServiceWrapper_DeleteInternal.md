# Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::DeleteInternal

- ea: `0x9a80`
- end: `0x9a9c`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::DeleteInternal`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9910`

## callees

- `0x9aa0`

## pseudocode

```c

```

## disassembly

```asm
0x9a80  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.DeleteRequest::.ctor()
0x9a85  stloc.0
0x9a86  ldloc.0
0x9a87  ldarg.1
0x9a88  ldarg.2
0x9a89  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x9a8e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.DeleteRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x9a93  ldarg.0
0x9a94  ldloc.0
0x9a95  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::ExecuteInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request)
0x9a9a  pop
0x9a9b  ret
```
