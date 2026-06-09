# Microsoft.Crm.CrmLive.Services.ServiceInstanceService::RetrieveOrganizationsForServiceComponentStatus

- ea: `0x132f0`
- end: `0x13350`
- name: `Microsoft.Crm.CrmLive.Services.ServiceInstanceService::RetrieveOrganizationsForServiceComponentStatus`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x12fa0`

## callees

- `0x132f0`

## string_xrefs

- `0x132fd`: `ServiceComponentId`
- `0x1331d`: `ServiceInstance`
- `0x13337`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`
- `0x13332`: `RetrieveOrganizationsForServiceComponentStatus`

## pseudocode

```c

```

## disassembly

```asm
0x132f0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x132f5  stloc.0
0x132f6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x132fb  stloc.1
0x132fc  ldloc.1
0x132fd  ldstr    aServicecompone// "ServiceComponentId"
0x13302  ldarg.0
0x13303  box      [mscorlib]System.Guid
0x13308  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1330d  ldc.i4.1
0x1330e  newarr   [mscorlib]System.String
0x13313  dup
0x13314  ldc.i4.0
0x13315  ldstr    aOrganizationid_0// "OrganizationId"
0x1331a  stelem.ref
0x1331b  stloc.2
0x1331c  ldloc.0
0x1331d  ldstr    aServiceinstanc// "ServiceInstance"
0x13322  ldloc.2
0x13323  ldc.i4.1
0x13324  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x13329  dup
0x1332a  ldc.i4.0
0x1332b  ldloc.1
0x1332c  stelem.ref
0x1332d  ldc.i4   0x1DF
0x13332  ldstr    aRetrieveorgani_1// "RetrieveOrganizationsForServiceComponen"...
0x13337  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x1333c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x13341  stloc.3
0x13342  leave.s  loc_1334E
0x13344  ldloc.0
0x13345  brfalse.s loc_1334D
0x13347  ldloc.0
0x13348  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1334d  endfinally
0x1334e  ldloc.3
0x1334f  ret
```
