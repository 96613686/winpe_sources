# std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::~pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(void)

- ea: `0x18001e6a0`
- end: `0x18001e6a9`
- name: `??1?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(char *)`
- caller_count: `92`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020fa5`
- `0x180020fc9`
- `0x180020fed`
- `0x180021011`
- `0x180021035`
- `0x180021059`
- `0x18002107d`
- `0x1800210a1`
- `0x1800210c5`
- `0x1800210e9`
- `0x18002110d`
- `0x180021131`
- `0x180021155`
- `0x180021179`
- `0x18002119d`
- `0x1800211c1`
- `0x1800211e5`
- `0x180021209`
- `0x18002122d`
- `0x180021251`
- `0x180021275`
- `0x180021299`
- `0x1800212bd`
- `0x1800212e1`
- `0x180021305`
- `0x180021329`
- `0x18002134d`
- `0x180021371`
- `0x180021395`
- `0x1800213b9`
- `0x1800213dd`
- `0x180021401`
- `0x180021425`
- `0x180021449`
- `0x18002146d`
- `0x180021491`
- `0x1800214b5`
- `0x1800214d9`
- `0x1800214fd`
- `0x180021521`
- `0x180021545`
- `0x180021569`
- `0x18002158d`
- `0x1800215b1`
- `0x1800215d5`
- `0x1800215f9`
- `0x18002161d`
- `0x180021641`
- `0x180021665`
- `0x180021689`

## callees

- `0x18001aaa0`

## pseudocode

```c
void __fastcall std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::~pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
        char *a1)
{
  std::wstring::_Tidy_deallocate(a1 + 16);
}

```

## disassembly

```asm
0x18001e6a0  add     rcx, 10h
0x18001e6a4  jmp     ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
