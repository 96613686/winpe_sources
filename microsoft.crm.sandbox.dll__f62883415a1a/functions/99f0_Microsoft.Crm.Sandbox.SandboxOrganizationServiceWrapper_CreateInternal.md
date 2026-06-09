# Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::CreateInternal

- ea: `0x99f0`
- end: `0x9a19`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::CreateInternal`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x98a0`

## callees

- `0x9aa0`

## pseudocode

```c

```

## disassembly

```asm
0x99f0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateRequest::.ctor()
0x99f5  stloc.0
0x99f6  ldloc.0
0x99f7  ldarg.1
0x99f8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x99fd  ldarg.0
0x99fe  ldloc.0
0x99ff  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::ExecuteInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request)
0x9a04  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x9a09  ldstr    aId// "id"
0x9a0e  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x9a13  unbox.any [mscorlib]System.Guid
0x9a18  ret
```
