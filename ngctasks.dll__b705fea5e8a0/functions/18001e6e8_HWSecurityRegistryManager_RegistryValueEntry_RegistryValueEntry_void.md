# HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry(void)

- ea: `0x18001e6e8`
- end: `0x18001e6f1`
- name: `??1RegistryValueEntry@HWSecurityRegistryManager@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(HWSecurityRegistryManager::RegistryValueEntry *__hidden this)`
- caller_count: `93`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020f93`
- `0x180020fb7`
- `0x180020fdb`
- `0x180020fff`
- `0x180021023`
- `0x180021047`
- `0x18002106b`
- `0x18002108f`
- `0x1800210b3`
- `0x1800210d7`
- `0x1800210fb`
- `0x18002111f`
- `0x180021143`
- `0x180021167`
- `0x18002118b`
- `0x1800211af`
- `0x1800211d3`
- `0x1800211f7`
- `0x18002121b`
- `0x18002123f`
- `0x180021263`
- `0x180021287`
- `0x1800212ab`
- `0x1800212cf`
- `0x1800212f3`
- `0x180021317`
- `0x18002133b`
- `0x18002135f`
- `0x180021383`
- `0x1800213a7`
- `0x1800213cb`
- `0x1800213ef`
- `0x180021413`
- `0x180021437`
- `0x18002145b`
- `0x18002147f`
- `0x1800214a3`
- `0x1800214c7`
- `0x1800214eb`
- `0x18002150f`
- `0x180021533`
- `0x180021557`
- `0x18002157b`
- `0x18002159f`
- `0x1800215c3`
- `0x1800215e7`
- `0x18002160b`
- `0x18002162f`
- `0x180021653`
- `0x180021677`

## callees

- `0x18001aaa0`

## pseudocode

```c
void __fastcall HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry(
        HWSecurityRegistryManager::RegistryValueEntry *this)
{
  std::wstring::_Tidy_deallocate((char *)this + 8);
}

```

## disassembly

```asm
0x18001e6e8  add     rcx, 8
0x18001e6ec  jmp     ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
