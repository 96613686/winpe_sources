# HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)

- ea: `0x18001e6b0`
- end: `0x18001e6e1`
- name: `??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(HWSecurityRegistryManager::RegistryKeyEntry *__hidden this)`
- caller_count: `20`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800031b0`
- `0x18001de0c`
- `0x18001e60c`
- `0x18001e690`
- `0x180020d0e`
- `0x180020d44`
- `0x180020d68`
- `0x180020d8c`
- `0x180020db0`
- `0x180020dd4`
- `0x180020df8`
- `0x180020e1c`
- `0x180020e40`
- `0x180020e64`
- `0x180020e88`
- `0x180020eac`
- `0x180020ed0`
- `0x180020ef4`
- `0x180020f18`
- `0x180020f3c`

## callees

- `0x18001aaa0`

## pseudocode

```c
void __fastcall HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(
        HWSecurityRegistryManager::RegistryKeyEntry *this)
{
  std::wstring::_Tidy_deallocate((char *)this + 104);
  std::wstring::_Tidy_deallocate((char *)this + 64);
  std::wstring::_Tidy_deallocate((char *)this + 32);
  std::wstring::_Tidy_deallocate(this);
}

```

## disassembly

```asm
0x18001e6b0  push    rbx
0x18001e6b2  sub     rsp, 20h
0x18001e6b6  mov     rbx, rcx
0x18001e6b9  add     rcx, 68h ; 'h'
0x18001e6bd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e6c2  lea     rcx, [rbx+40h]
0x18001e6c6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e6cb  lea     rcx, [rbx+20h]
0x18001e6cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e6d4  mov     rcx, rbx
0x18001e6d7  add     rsp, 20h
0x18001e6db  pop     rbx
0x18001e6dc  jmp     ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
