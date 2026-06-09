# _Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData_::_1_::dtor$1

- ea: `0x18000ad20`
- end: `0x18000ad30`
- name: `_Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData_::_1_::dtor$1`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006260`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return std::wstring::~wstring((char **)(*(_QWORD *)(a2 + 32) + 32LL));
}

```

## disassembly

```asm
0x18000ad20  mov     rcx, [rdx+20h]
0x18000ad27  add     rcx, 20h ; ' '
0x18000ad2b  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
