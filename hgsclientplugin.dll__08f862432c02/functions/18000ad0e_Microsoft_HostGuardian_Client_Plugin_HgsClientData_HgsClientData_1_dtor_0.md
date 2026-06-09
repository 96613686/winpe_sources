# _Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData_::_1_::dtor$0

- ea: `0x18000ad0e`
- end: `0x18000ad1a`
- name: `_Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006260`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::wstring::~wstring(*(char ***)(a2 + 32));
}

```

## disassembly

```asm
0x18000ad0e  mov     rcx, [rdx+20h]
0x18000ad15  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
