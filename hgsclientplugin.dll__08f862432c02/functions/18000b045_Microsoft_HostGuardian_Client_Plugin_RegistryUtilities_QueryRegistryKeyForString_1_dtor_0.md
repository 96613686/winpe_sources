# _Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForString_::_1_::dtor$0

- ea: `0x18000b045`
- end: `0x18000b06b`
- name: `_Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForString_::_1_::dtor$0`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006260`
- `0x18000b045`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForString_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 80) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 80) &= ~1u;
    return std::wstring::~wstring(*(char ***)(a2 + 88));
  }
  return result;
}

```

## disassembly

```asm
0x18000b045  push    rbp
0x18000b047  sub     rsp, 20h
0x18000b04b  mov     rbp, rdx
0x18000b04e  mov     eax, [rbp+50h]
0x18000b051  and     eax, 1
0x18000b054  test    eax, eax
0x18000b056  jz      short loc_18000B065
0x18000b058  and     dword ptr [rbp+50h], 0FFFFFFFEh
0x18000b05c  mov     rcx, [rbp+58h]
0x18000b060  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b065  add     rsp, 20h
0x18000b069  pop     rbp
0x18000b06a  retn
```
