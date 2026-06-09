# Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::RemoveOrgFromOrgSettingsLightCache

- ea: `0x4ca0`
- end: `0x4caf`
- name: `Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::RemoveOrgFromOrgSettingsLightCache`
- size: `15`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x4c40`
- `0x4cc0`

## pseudocode

```c

```

## disassembly

```asm
0x4ca0  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings> Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::orgSettingsLightCache
0x4ca5  ldarg.0
0x4ca6  ldloca.s 0
0x4ca8  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings>::TryRemove(var<u1>, !!T0)
0x4cad  pop
0x4cae  ret
```
