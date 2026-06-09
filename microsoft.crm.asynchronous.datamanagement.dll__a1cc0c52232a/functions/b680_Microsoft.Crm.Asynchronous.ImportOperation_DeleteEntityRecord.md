# Microsoft.Crm.Asynchronous.ImportOperation::DeleteEntityRecord

- ea: `0xb680`
- end: `0xb6a1`
- name: `Microsoft.Crm.Asynchronous.ImportOperation::DeleteEntityRecord`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xb400`

## pseudocode

```c

```

## disassembly

```asm
0xb680  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.DeleteRequest::.ctor()
0xb685  stloc.0
0xb686  ldloc.0
0xb687  ldarg.1
0xb688  ldarg.2
0xb689  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0xb68e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.DeleteRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0xb693  ldarg.0
0xb694  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0xb699  ldloc.0
0xb69a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0xb69f  pop
0xb6a0  ret
```
