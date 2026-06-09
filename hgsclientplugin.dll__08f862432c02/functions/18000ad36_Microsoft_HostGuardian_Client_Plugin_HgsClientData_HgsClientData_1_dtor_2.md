# _Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData_::_1_::dtor$2

- ea: `0x18000ad36`
- end: `0x18000ad46`
- name: `_Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData_::_1_::dtor$2`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800062ec`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  std::vector<std::wstring>::~vector<std::wstring>(*(_QWORD *)(a2 + 32) + 64LL);
}

```

## disassembly

```asm
0x18000ad36  mov     rcx, [rdx+20h]
0x18000ad3d  add     rcx, 40h ; '@'
0x18000ad41  jmp     ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
