# Microsoft.Crm.Asynchronous.BulkDeleteOperation::GetBusinessUnitId

- ea: `0x1710`
- end: `0x1778`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::GetBusinessUnitId`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1f350`

## pseudocode

```c

```

## disassembly

```asm
0x1710  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::.ctor()
0x1715  stloc.0
0x1716  ldloc.0
0x1717  ldc.i4.2
0x1718  newarr   [mscorlib]System.String
0x171d  dup
0x171e  ldc.i4.0
0x171f  ldstr    aBusinessunitid// "businessunitid"
0x1724  stelem.ref
0x1725  dup
0x1726  ldc.i4.1
0x1727  ldstr    aOrganizationid// "organizationid"
0x172c  stelem.ref
0x172d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x1732  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x1737  ldloc.0
0x1738  ldstr    aSystemuser// "systemuser"
0x173d  ldarg.1
0x173e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OwnerId()
0x1743  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x1748  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x174d  ldarg.0
0x174e  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperation::_crmService
0x1753  ldloc.0
0x1754  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x1759  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveResponse
0x175e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveResponse::get_Entity()
0x1763  ldstr    aBusinessunitid// "businessunitid"
0x1768  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x176d  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x1772  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1777  ret
```
