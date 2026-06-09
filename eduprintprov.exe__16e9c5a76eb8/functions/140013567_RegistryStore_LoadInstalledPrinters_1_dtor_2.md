# _RegistryStore::LoadInstalledPrinters_::_1_::dtor$2

- ea: `0x140013567`
- end: `0x140013573`
- name: `_RegistryStore::LoadInstalledPrinters_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x14000c540`

## pseudocode

```c
__int64 __fastcall RegistryStore::LoadInstalledPrinters_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::list<std::wstring>::~list<std::wstring>(a2 + 128);
}

```

## disassembly

```asm
0x140013567  lea     rcx, [rdx+80h]
0x14001356e  jmp     ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
```
