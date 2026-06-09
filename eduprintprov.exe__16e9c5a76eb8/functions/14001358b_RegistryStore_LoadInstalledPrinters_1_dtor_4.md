# _RegistryStore::LoadInstalledPrinters_::_1_::dtor$4

- ea: `0x14001358b`
- end: `0x140013597`
- name: `_RegistryStore::LoadInstalledPrinters_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x14000c540`

## pseudocode

```c
__int64 __fastcall RegistryStore::LoadInstalledPrinters_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::list<std::wstring>::~list<std::wstring>(a2 + 72);
}

```

## disassembly

```asm
0x14001358b  lea     rcx, [rdx+48h]
0x140013592  jmp     ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
```
