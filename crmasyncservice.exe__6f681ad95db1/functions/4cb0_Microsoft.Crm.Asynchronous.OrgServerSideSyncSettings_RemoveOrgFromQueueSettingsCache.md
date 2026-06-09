# Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::RemoveOrgFromQueueSettingsCache

- ea: `0x4cb0`
- end: `0x4cbd`
- name: `Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::RemoveOrgFromQueueSettingsCache`
- size: `13`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x4c40`
- `0x4cd0`

## pseudocode

```c

```

## disassembly

```asm
0x4cb0  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings> Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::orgQueueSettingsCache
0x4cb5  ldarg.0
0x4cb6  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings>::Remove(var<u1>)
0x4cbb  pop
0x4cbc  ret
```
