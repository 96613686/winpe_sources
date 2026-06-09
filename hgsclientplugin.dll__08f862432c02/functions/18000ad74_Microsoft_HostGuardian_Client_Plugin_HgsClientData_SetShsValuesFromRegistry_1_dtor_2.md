# _Microsoft::HostGuardian::Client::Plugin::HgsClientData::SetShsValuesFromRegistry_::_1_::dtor$2

- ea: `0x18000ad74`
- end: `0x18000ad80`
- name: `_Microsoft::HostGuardian::Client::Plugin::HgsClientData::SetShsValuesFromRegistry_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800062ec`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::Plugin::HgsClientData::SetShsValuesFromRegistry_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  std::vector<std::wstring>::~vector<std::wstring>(a2 + 72);
}

```

## disassembly

```asm
0x18000ad74  lea     rcx, [rdx+48h]
0x18000ad7b  jmp     ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
