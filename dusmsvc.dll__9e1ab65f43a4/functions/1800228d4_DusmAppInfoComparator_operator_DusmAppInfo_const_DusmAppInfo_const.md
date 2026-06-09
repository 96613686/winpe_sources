# DusmAppInfoComparator::operator()(DusmAppInfo const &,DusmAppInfo const &)

- ea: `0x1800228d4`
- end: `0x18002292d`
- name: `??RDusmAppInfoComparator@@QEBA_NAEBUDusmAppInfo@@0@Z`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180021454`
- `0x1800216a4`
- `0x18002178c`

## callees

- `0x180012fcc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18002291c`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18002291c`

## pseudocode

```c
bool __fastcall DusmAppInfoComparator::operator()(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdx
  const WCHAR *v4; // rax
  __int64 v5; // r8
  __int64 v6; // rdx
  LPCWCH lpString2; // r9

  std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3);
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v3);
  return CompareStringEx(&LocaleName, 0x10u, v4, *(_DWORD *)(v6 + 16), lpString2, *(_DWORD *)(v5 + 16), 0, 0, 0) == 1;
}

```

## disassembly

```asm
0x1800228d4  sub     rsp, 58h
0x1800228d8  mov     rcx, r8
0x1800228db  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800228e0  mov     rcx, rdx
0x1800228e3  mov     r9, rax
0x1800228e6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800228eb  xor     ecx, ecx
0x1800228ed  mov     [rsp+58h+lParam], rcx; lParam
0x1800228f2  mov     [rsp+58h+lpReserved], rcx; lpReserved
0x1800228f7  mov     [rsp+58h+lpVersionInformation], rcx; lpVersionInformation
0x1800228fc  mov     ecx, [r8+10h]
0x180022900  mov     r8, rax; lpString1
0x180022903  mov     [rsp+58h+cchCount2], ecx; cchCount2
0x180022907  lea     rcx, LocaleName; lpLocaleName
0x18002290e  mov     [rsp+58h+lpString2], r9; lpString2
0x180022913  mov     r9d, [rdx+10h]; cchCount1
0x180022917  mov     edx, 10h; dwCmpFlags
0x18002291c  call    cs:__imp_CompareStringEx
0x180022922  cmp     eax, 1
0x180022925  setz    al
0x180022928  add     rsp, 58h
0x18002292c  retn
```
