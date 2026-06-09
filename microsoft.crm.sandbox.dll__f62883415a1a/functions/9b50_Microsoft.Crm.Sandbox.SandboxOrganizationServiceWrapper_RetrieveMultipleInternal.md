# Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::RetrieveMultipleInternal

- ea: `0x9b50`
- end: `0x9b8f`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::RetrieveMultipleInternal`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x99d0`

## callees

- `0x9aa0`
- `0x9b50`

## pseudocode

```c

```

## disassembly

```asm
0x9b50  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0x9b55  stloc.0
0x9b56  ldloc.0
0x9b57  ldarg.1
0x9b58  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x9b5d  ldarg.0
0x9b5e  ldloc.0
0x9b5f  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::ExecuteInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request)
0x9b64  stloc.1
0x9b65  ldloc.1
0x9b66  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x9b6b  ldstr    aEntitycollecti// "EntityCollection"
0x9b70  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x9b75  brfalse.s loc_9B8D
0x9b77  ldloc.1
0x9b78  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x9b7d  ldstr    aEntitycollecti// "EntityCollection"
0x9b82  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x9b87  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection
0x9b8c  ret
0x9b8d  ldnull
0x9b8e  ret
```
