# Microsoft.Crm.CrmLive.Services.ServiceComponentSkuService::RetrieveServiceComponentSkuByDescription

- ea: `0x12460`
- end: `0x12495`
- name: `Microsoft.Crm.CrmLive.Services.ServiceComponentSkuService::RetrieveServiceComponentSkuByDescription`
- size: `53`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x124f0`
- `0x12510`
- `0x125b0`

## callees

- `0x120e0`
- `0x12460`

## string_xrefs

- `0x12470`: `ServiceComponentSku`
- `0x1247e`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceComponentSkuService.cs`
- `0x12479`: `RetrieveServiceComponentSkuByDescription`

## pseudocode

```c

```

## disassembly

```asm
0x12460  ldarg.1
0x12461  ldstr    aDescription_0// "description"
0x12466  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1246b  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x12470  ldstr    aServicecompone_4// "ServiceComponentSku"
0x12475  ldarg.1
0x12476  ldnull
0x12477  ldc.i4.s 0x7F
0x12479  ldstr    aRetrieveservic// "RetrieveServiceComponentSkuByDescriptio"...
0x1247e  ldstr    aDA1SSrcCrmlive_24// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x12483  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveById(string, object, string[], int32, string, string)
0x12488  stloc.0
0x12489  ldloc.0
0x1248a  brtrue.s loc_1248E
0x1248c  ldnull
0x1248d  ret
0x1248e  ldloc.0
0x1248f  call     class Microsoft.Crm.CrmLive.Services.ServiceComponentSku Microsoft.Crm.CrmLive.Services.ServiceComponentSku::FromPropertyBag(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag propBag)
0x12494  ret
```
