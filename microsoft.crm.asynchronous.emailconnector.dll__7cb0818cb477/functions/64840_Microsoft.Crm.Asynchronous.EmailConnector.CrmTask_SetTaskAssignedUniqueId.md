# Microsoft.Crm.Asynchronous.EmailConnector.CrmTask::SetTaskAssignedUniqueId

- ea: `0x64840`
- end: `0x64886`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmTask::SetTaskAssignedUniqueId`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x64840`
- `0x6e500`
- `0x6e620`
- `0x701d0`
- `0x70330`
- `0x70460`
- `0x704a0`

## string_xrefs

- `0x64846`: `crmtaskassigneduniqueid`
- `0x64857`: `crmtaskassigneduniqueid`
- `0x64866`: `crmtaskassigneduniqueid`
- `0x64877`: `crmtaskassigneduniqueid`

## pseudocode

```c

```

## disassembly

```asm
0x64840  ldarg.0
0x64841  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x64846  ldstr    aCrmtaskassigne// "crmtaskassigneduniqueid"
0x6484b  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x64850  stloc.0
0x64851  ldarg.0
0x64852  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_OriginalProperties()
0x64857  ldstr    aCrmtaskassigne// "crmtaskassigneduniqueid"
0x6485c  ldloc.0
0x6485d  ldnull
0x6485e  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::IsPropertyChanged(string propertyName, string newValue, [opt] class Microsoft.Crm.Asynchronous.EmailConnector.PropertyCompare comparer)
0x64863  brfalse.s loc_64884
0x64865  ldarg.0
0x64866  ldstr    aCrmtaskassigne// "crmtaskassigneduniqueid"
0x6486b  ldloc.0
0x6486c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::SetPropertyValue(string propertyName, string propertyValue)
0x64871  ldarg.0
0x64872  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_OriginalProperties()
0x64877  ldstr    aCrmtaskassigne// "crmtaskassigneduniqueid"
0x6487c  ldloc.0
0x6487d  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::AddProperty(string propertyName, string propertyValue)
0x64882  ldc.i4.1
0x64883  ret
0x64884  ldc.i4.0
0x64885  ret
```
