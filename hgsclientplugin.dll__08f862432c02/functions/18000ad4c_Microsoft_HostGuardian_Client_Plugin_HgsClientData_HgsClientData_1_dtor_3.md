# _Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData_::_1_::dtor$3

- ea: `0x18000ad4c`
- end: `0x18000ad5c`
- name: `_Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData_::_1_::dtor$3`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800062ec`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  std::vector<std::wstring>::~vector<std::wstring>(*(_QWORD *)(a2 + 32) + 88LL);
}

```

## disassembly

```asm
0x18000ad4c  mov     rcx, [rdx+20h]
0x18000ad53  add     rcx, 58h ; 'X'
0x18000ad57  jmp     ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
