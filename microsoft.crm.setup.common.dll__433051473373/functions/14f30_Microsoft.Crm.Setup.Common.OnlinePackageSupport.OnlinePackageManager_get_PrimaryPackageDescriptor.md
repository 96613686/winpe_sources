# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_PrimaryPackageDescriptor

- ea: `0x14f30`
- end: `0x14f3c`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_PrimaryPackageDescriptor`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x150b0`
- `0x15250`
- `0x15be0`

## callees

- `0x14f10`
- `0x16400`

## pseudocode

```c

```

## disassembly

```asm
0x14f30  ldarg.0
0x14f31  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_PackingList()
0x14f36  callvirt instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList::get_PrimaryPackageDescriptor()
0x14f3b  ret
```
