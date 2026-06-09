# Microsoft.Crm.CrmLive.Services.ServiceInstanceService::RetrieveServiceInstancesForOrganization

- ea: `0x13480`
- end: `0x134d1`
- name: `Microsoft.Crm.CrmLive.Services.ServiceInstanceService::RetrieveServiceInstancesForOrganization`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x134e0`

## callees

- `0x13480`

## string_xrefs

- `0x1349e`: `ServiceInstance`
- `0x134b8`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`
- `0x134b3`: `RetrieveServiceInstancesForOrganization`

## pseudocode

```c

```

## disassembly

```asm
0x13480  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x13485  stloc.0
0x13486  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1348b  stloc.1
0x1348c  ldloc.1
0x1348d  ldstr    aOrganizationid_0// "OrganizationId"
0x13492  ldarg.0
0x13493  box      [mscorlib]System.Guid
0x13498  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1349d  ldloc.0
0x1349e  ldstr    aServiceinstanc// "ServiceInstance"
0x134a3  ldnull
0x134a4  ldc.i4.1
0x134a5  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x134aa  dup
0x134ab  ldc.i4.0
0x134ac  ldloc.1
0x134ad  stelem.ref
0x134ae  ldc.i4   0x230
0x134b3  ldstr    aRetrieveservic_0// "RetrieveServiceInstancesForOrganization"
0x134b8  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x134bd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x134c2  stloc.2
0x134c3  leave.s  loc_134CF
0x134c5  ldloc.0
0x134c6  brfalse.s loc_134CE
0x134c8  ldloc.0
0x134c9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x134ce  endfinally
0x134cf  ldloc.2
0x134d0  ret
```
