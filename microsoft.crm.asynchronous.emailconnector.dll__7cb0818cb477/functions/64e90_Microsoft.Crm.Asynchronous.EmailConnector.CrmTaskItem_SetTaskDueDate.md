# Microsoft.Crm.Asynchronous.EmailConnector.CrmTaskItem::SetTaskDueDate

- ea: `0x64e90`
- end: `0x64ee1`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmTaskItem::SetTaskDueDate`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x64e90`
- `0x6e150`
- `0x6e500`
- `0x6e620`
- `0x701d0`
- `0x70330`
- `0x70460`
- `0x704a0`

## string_xrefs

- `0x64ea7`: `scheduledend`
- `0x64ec1`: `scheduledend`
- `0x64ed2`: `scheduledend`
- `0x64e96`: `taskduedate`

## pseudocode

```c

```

## disassembly

```asm
0x64e90  ldarg.0
0x64e91  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x64e96  ldstr    aTaskduedate// "taskduedate"
0x64e9b  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x64ea0  stloc.0
0x64ea1  ldarg.0
0x64ea2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_OriginalProperties()
0x64ea7  ldstr    aScheduledend// "scheduledend"
0x64eac  ldloc.0
0x64ead  ldnull
0x64eae  ldftn    bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::IsTaskDueDatePropertyChanged(string oldValue, string newValue)
0x64eb4  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.PropertyCompare::.ctor(object object, native int method)
0x64eb9  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::IsPropertyChanged(string propertyName, string newValue, [opt] class Microsoft.Crm.Asynchronous.EmailConnector.PropertyCompare comparer)
0x64ebe  brfalse.s loc_64EDF
0x64ec0  ldarg.0
0x64ec1  ldstr    aScheduledend// "scheduledend"
0x64ec6  ldloc.0
0x64ec7  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::SetPropertyValue(string propertyName, string propertyValue)
0x64ecc  ldarg.0
0x64ecd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_OriginalProperties()
0x64ed2  ldstr    aScheduledend// "scheduledend"
0x64ed7  ldloc.0
0x64ed8  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::AddProperty(string propertyName, string propertyValue)
0x64edd  ldc.i4.1
0x64ede  ret
0x64edf  ldc.i4.0
0x64ee0  ret
```
