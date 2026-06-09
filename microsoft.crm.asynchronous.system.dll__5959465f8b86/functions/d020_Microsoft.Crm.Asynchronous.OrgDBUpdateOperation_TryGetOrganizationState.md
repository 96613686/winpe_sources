# Microsoft.Crm.Asynchronous.OrgDBUpdateOperation::TryGetOrganizationState

- ea: `0xd020`
- end: `0xd06a`
- name: `Microsoft.Crm.Asynchronous.OrgDBUpdateOperation::TryGetOrganizationState`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0xced0`

## callees

- `0x8f00`
- `0x8f30`
- `0xd020`

## pseudocode

```c

```

## disassembly

```asm
0xd020  ldarg.2
0xd021  ldc.i4.1
0xd022  stind.i4
0xd023  call     class [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrganizationController [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrganizationController::get_Instance()
0xd028  ldarg.0
0xd029  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xd02e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xd033  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrganizationController::Retrieve(valuetype [mscorlib]System.Guid)
0xd038  stloc.0
0xd039  ldloc.0
0xd03a  brfalse.s loc_D044
0xd03c  ldarg.2
0xd03d  ldloc.0
0xd03e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_State()
0xd043  stind.i4
0xd044  ldc.i4.1
0xd045  stloc.1
0xd046  leave.s  loc_D068
0xd048  stloc.2
0xd049  call     class Microsoft.Crm.Asynchronous.OrgDBUpdateEventSource Microsoft.Crm.Asynchronous.OrgDBUpdateEventSource::get_Instance()
0xd04e  ldloc.2
0xd04f  callvirt instance string [mscorlib]System.Object::ToString()
0xd054  ldarg.0
0xd055  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xd05a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xd05f  callvirt instance void Microsoft.Crm.Asynchronous.OrgDBUpdateEventSource::OrgDBUpdateJobFetchStateFailed(string exceptionMessage, valuetype [mscorlib]System.Guid organizationId)
0xd064  ldc.i4.0
0xd065  stloc.1
0xd066  leave.s  loc_D068
0xd068  ldloc.1
0xd069  ret
```
