# Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::RetrieveInternal

- ea: `0x9a20`
- end: `0x9a56`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::RetrieveInternal`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x98c0`

## callees

- `0x9aa0`

## pseudocode

```c

```

## disassembly

```asm
0x9a20  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::.ctor()
0x9a25  stloc.0
0x9a26  ldloc.0
0x9a27  ldarg.1
0x9a28  ldarg.2
0x9a29  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x9a2e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x9a33  ldloc.0
0x9a34  ldarg.3
0x9a35  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x9a3a  ldarg.0
0x9a3b  ldloc.0
0x9a3c  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::ExecuteInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request)
0x9a41  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x9a46  ldstr    aEntity_0// "Entity"
0x9a4b  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x9a50  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x9a55  ret
```
