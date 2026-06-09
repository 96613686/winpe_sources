# Microsoft.Crm.ScaleGroupApi.Controllers.UserSecurityRoleController::AssignRoleToUserUsingSdk

- ea: `0x4fd0`
- end: `0x5044`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.UserSecurityRoleController::AssignRoleToUserUsingSdk`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x4e70`

## callees

- `0xe80`
- `0xeb0`
- `0x4fd0`

## string_xrefs

- `0x500b`: `Role {0} is already assigned to User {1}, association failed with error {3}`

## pseudocode

```c

```

## disassembly

```asm
0x4fd0  ldarg.0
0x4fd1  call     class Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::CreateInstance(valuetype [mscorlib]System.Guid orgId)
0x4fd6  stloc.0
0x4fd7  ldloc.0
0x4fd8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::get_Sdk()
0x4fdd  ldstr    aSystemuser// "systemuser"
0x4fe2  ldarg.2
0x4fe3  ldstr    aSystemuserrole_0// "systemuserroles_association"
0x4fe8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship::.ctor(string)
0x4fed  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReferenceCollection::.ctor()
0x4ff2  dup
0x4ff3  ldstr    aRole// "role"
0x4ff8  ldarg.1
0x4ff9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x4ffe  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::Add(var<u1>)
0x5003  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Associate(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReferenceCollection)
0x5008  leave.s  loc_5043
0x500a  stloc.1
0x500b  ldstr    aRole0IsAlready// "Role {0} is already assigned to User {1"...
0x5010  ldarg.1
0x5011  box      [mscorlib]System.Guid
0x5016  ldarg.2
0x5017  box      [mscorlib]System.Guid
0x501c  ldloc.1
0x501d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5022  call     string [mscorlib]System.String::Format(string, object, object, object)
0x5027  stloc.2
0x5028  ldloc.1
0x5029  ldarg.0
0x502a  ldc.i4.6
0x502b  ldloc.2
0x502c  ldc.i4.0
0x502d  newarr   [mscorlib]System.Object
0x5032  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5037  leave.s  loc_5043
0x5039  ldloc.0
0x503a  brfalse.s loc_5042
0x503c  ldloc.0
0x503d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5042  endfinally
0x5043  ret
```
