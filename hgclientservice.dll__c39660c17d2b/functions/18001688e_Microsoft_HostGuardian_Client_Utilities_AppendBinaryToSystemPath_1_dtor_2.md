# _Microsoft::HostGuardian::Client::Utilities::AppendBinaryToSystemPath_::_1_::dtor$2

- ea: `0x18001688e`
- end: `0x1800168b4`
- name: `_Microsoft::HostGuardian::Client::Utilities::AppendBinaryToSystemPath_::_1_::dtor$2`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004274`
- `0x18001688e`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Utilities::AppendBinaryToSystemPath_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 80) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 80) &= ~1u;
    return std::wstring::~wstring(*(char ***)(a2 + 96));
  }
  return result;
}

```

## disassembly

```asm
0x18001688e  push    rbp
0x180016890  sub     rsp, 20h
0x180016894  mov     rbp, rdx
0x180016897  mov     eax, [rbp+50h]
0x18001689a  and     eax, 1
0x18001689d  test    eax, eax
0x18001689f  jz      short loc_1800168AE
0x1800168a1  and     dword ptr [rbp+50h], 0FFFFFFFEh
0x1800168a5  mov     rcx, [rbp+60h]
0x1800168a9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800168ae  add     rsp, 20h
0x1800168b2  pop     rbp
0x1800168b3  retn
```
