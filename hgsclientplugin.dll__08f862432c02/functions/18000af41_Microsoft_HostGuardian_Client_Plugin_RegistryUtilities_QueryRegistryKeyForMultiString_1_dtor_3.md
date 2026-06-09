# _Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForMultiString_::_1_::dtor$3

- ea: `0x18000af41`
- end: `0x18000af4d`
- name: `_Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForMultiString_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006260`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForMultiString_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 104));
}

```

## disassembly

```asm
0x18000af41  lea     rcx, [rdx+68h]
0x18000af48  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
