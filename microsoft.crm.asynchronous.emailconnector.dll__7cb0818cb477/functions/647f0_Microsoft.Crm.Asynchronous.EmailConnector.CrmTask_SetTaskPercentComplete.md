# Microsoft.Crm.Asynchronous.EmailConnector.CrmTask::SetTaskPercentComplete

- ea: `0x647f0`
- end: `0x64836`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmTask::SetTaskPercentComplete`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x647f0`
- `0x6e500`
- `0x6e620`
- `0x701d0`
- `0x70330`
- `0x70460`
- `0x704a0`

## string_xrefs

- `0x647f6`: `percentcomplete`
- `0x64807`: `percentcomplete`
- `0x64816`: `percentcomplete`
- `0x64827`: `percentcomplete`

## pseudocode

```c

```

## disassembly

```asm
0x647f0  ldarg.0
0x647f1  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x647f6  ldstr    aPercentcomplet// "percentcomplete"
0x647fb  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x64800  stloc.0
0x64801  ldarg.0
0x64802  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_OriginalProperties()
0x64807  ldstr    aPercentcomplet// "percentcomplete"
0x6480c  ldloc.0
0x6480d  ldnull
0x6480e  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::IsPropertyChanged(string propertyName, string newValue, [opt] class Microsoft.Crm.Asynchronous.EmailConnector.PropertyCompare comparer)
0x64813  brfalse.s loc_64834
0x64815  ldarg.0
0x64816  ldstr    aPercentcomplet// "percentcomplete"
0x6481b  ldloc.0
0x6481c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::SetPropertyValue(string propertyName, string propertyValue)
0x64821  ldarg.0
0x64822  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_OriginalProperties()
0x64827  ldstr    aPercentcomplet// "percentcomplete"
0x6482c  ldloc.0
0x6482d  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::AddProperty(string propertyName, string propertyValue)
0x64832  ldc.i4.1
0x64833  ret
0x64834  ldc.i4.0
0x64835  ret
```
