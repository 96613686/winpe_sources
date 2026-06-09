# Microsoft.Crm.Asynchronous.EmailConnector.CrmTaskItem::SetTaskStartDate

- ea: `0x64e30`
- end: `0x64e81`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmTaskItem::SetTaskStartDate`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x64e30`
- `0x6e150`
- `0x6e500`
- `0x6e620`
- `0x701d0`
- `0x70330`
- `0x70460`
- `0x704a0`

## string_xrefs

- `0x64e47`: `scheduledstart`
- `0x64e61`: `scheduledstart`
- `0x64e72`: `scheduledstart`
- `0x64e36`: `taskstartdate`

## pseudocode

```c

```

## disassembly

```asm
0x64e30  ldarg.0
0x64e31  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x64e36  ldstr    aTaskstartdate// "taskstartdate"
0x64e3b  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x64e40  stloc.0
0x64e41  ldarg.0
0x64e42  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_OriginalProperties()
0x64e47  ldstr    aScheduledstart// "scheduledstart"
0x64e4c  ldloc.0
0x64e4d  ldnull
0x64e4e  ldftn    bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::IsTaskStartDatePropertyChanged(string oldValue, string newValue)
0x64e54  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.PropertyCompare::.ctor(object object, native int method)
0x64e59  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::IsPropertyChanged(string propertyName, string newValue, [opt] class Microsoft.Crm.Asynchronous.EmailConnector.PropertyCompare comparer)
0x64e5e  brfalse.s loc_64E7F
0x64e60  ldarg.0
0x64e61  ldstr    aScheduledstart// "scheduledstart"
0x64e66  ldloc.0
0x64e67  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::SetPropertyValue(string propertyName, string propertyValue)
0x64e6c  ldarg.0
0x64e6d  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_OriginalProperties()
0x64e72  ldstr    aScheduledstart// "scheduledstart"
0x64e77  ldloc.0
0x64e78  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::AddProperty(string propertyName, string propertyValue)
0x64e7d  ldc.i4.1
0x64e7e  ret
0x64e7f  ldc.i4.0
0x64e80  ret
```
