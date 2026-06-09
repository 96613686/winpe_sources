# std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::~pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(void)

- ea: `0x18001e690`
- end: `0x18001e699`
- name: `??1?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(char *)`
- caller_count: `15`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020d20`
- `0x180020d56`
- `0x180020d7a`
- `0x180020d9e`
- `0x180020dc2`
- `0x180020de6`
- `0x180020e0a`
- `0x180020e2e`
- `0x180020e52`
- `0x180020e76`
- `0x180020e9a`
- `0x180020ebe`
- `0x180020ee2`
- `0x180020f06`
- `0x180020f2a`

## callees

- `0x18001e6b0`

## pseudocode

```c
void __fastcall std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::~pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
        char *a1)
{
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)(a1 + 8));
}

```

## disassembly

```asm
0x18001e690  add     rcx, 8; this
0x18001e694  jmp     ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
```
