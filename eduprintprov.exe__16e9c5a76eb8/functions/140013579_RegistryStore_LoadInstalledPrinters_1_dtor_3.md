# _RegistryStore::LoadInstalledPrinters_::_1_::dtor$3

- ea: `0x140013579`
- end: `0x140013585`
- name: `_RegistryStore::LoadInstalledPrinters_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x140004e30`

## pseudocode

```c
__int64 __fastcall RegistryStore::LoadInstalledPrinters_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 152));
}

```

## disassembly

```asm
0x140013579  lea     rcx, [rdx+98h]
0x140013580  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
