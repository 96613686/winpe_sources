# Microsoft.Crm.CrmLive.Services.ServiceInstanceService::Retrieve

- ea: `0x128c0`
- end: `0x1290c`
- name: `Microsoft.Crm.CrmLive.Services.ServiceInstanceService::Retrieve`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x128d8`: `ServiceComponentId`
- `0x128f3`: `ServiceInstance`
- `0x12901`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x128c0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x128c5  stloc.0
0x128c6  ldloc.0
0x128c7  ldstr    aOrganizationid_0// "OrganizationId"
0x128cc  ldarg.1
0x128cd  box      [mscorlib]System.Guid
0x128d2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x128d7  ldloc.0
0x128d8  ldstr    aServicecompone// "ServiceComponentId"
0x128dd  ldarg.2
0x128de  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x128e3  ldc.i4.1
0x128e4  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x128e9  dup
0x128ea  ldc.i4.0
0x128eb  ldloc.0
0x128ec  stelem.ref
0x128ed  stloc.1
0x128ee  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x128f3  ldstr    aServiceinstanc// "ServiceInstance"
0x128f8  ldnull
0x128f9  ldloc.1
0x128fa  ldc.i4.s 0x44
0x128fc  ldstr    aRetrieve// "Retrieve"
0x12901  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x12906  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x1290b  ret
```
