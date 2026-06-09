# Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationAction::Do

- ea: `0x7880`
- end: `0x7926`
- name: `Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationAction::Do`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x64b0`
- `0x6520`
- `0x6550`
- `0x7820`
- `0x7880`
- `0x7930`
- `0x91b0`

## string_xrefs

- `0x78cb`: `AddFederation task did not complete after waiting 30 minutes`
- `0x78e8`: `AddFederation task faulted`

## pseudocode

```c

```

## disassembly

```asm
0x7880  ldarg.0
0x7881  ldarg.0
0x7882  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x7887  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x788c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x7891  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0x7896  ldarg.0
0x7897  ldfld    class Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationActionAsync Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationAction::_asyncAction
0x789c  brfalse.s loc_7904
0x789e  ldarg.0
0x789f  ldfld    class Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationActionAsync Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationAction::_asyncAction
0x78a4  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationActionAsync::get_Task()
0x78a9  brfalse.s loc_7904
0x78ab  ldarg.0
0x78ac  ldfld    class Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationActionAsync Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationAction::_asyncAction
0x78b1  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationActionAsync::get_Task()
0x78b6  ldc.r8   30.0
0x78bf  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x78c4  callvirt instance bool [mscorlib]System.Threading.Tasks.Task::Wait(valuetype [mscorlib]System.TimeSpan)
0x78c9  brtrue.s loc_78D6
0x78cb  ldstr    aAddfederationT// "AddFederation task did not complete aft"...
0x78d0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x78d5  throw
0x78d6  ldarg.0
0x78d7  ldfld    class Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationActionAsync Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationAction::_asyncAction
0x78dc  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationActionAsync::get_Task()
0x78e1  callvirt instance bool [mscorlib]System.Threading.Tasks.Task::get_IsFaulted()
0x78e6  brfalse.s loc_7903
0x78e8  ldstr    aAddfederationT_0// "AddFederation task faulted"
0x78ed  ldarg.0
0x78ee  ldfld    class Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationActionAsync Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationAction::_asyncAction
0x78f3  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationActionAsync::get_Task()
0x78f8  callvirt instance class [mscorlib]System.AggregateException [mscorlib]System.Threading.Tasks.Task::get_Exception()
0x78fd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x7902  throw
0x7903  ret
0x7904  ldarg.0
0x7905  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x790a  call     void Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationAction::DoInternal(class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties organizationProperties)
0x790f  ldarg.0
0x7910  ldarg.0
0x7911  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x7916  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x791b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x7920  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0x7925  ret
```
