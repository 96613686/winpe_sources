# CompareLocales(LOCALE_DATA_TYPE,LOCALE_DATA_TYPE)

- ea: `0x180023690`
- end: `0x18002370b`
- name: `?CompareLocales@@YA_NULOCALE_DATA_TYPE@@0@Z`
- size: `123`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022440`
- `0x18002256c`
- `0x180022794`
- `0x180022b68`
- `0x180022d84`

## callees

- `0x180023474`
- `0x180028d80`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800236dd`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800236dd`

## pseudocode

```c
bool __fastcall CompareLocales(__int64 a1, __int64 a2)
{
  const WCHAR *v4; // rax
  LPCWCH lpString2; // rdx
  bool v6; // bl

  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  v6 = CompareStringEx(0, 4u, v4, -1, lpString2, -1, 0, 0, 0) == 1;
  std::wstring::~wstring(a1);
  std::wstring::~wstring(a2);
  return v6;
}

```

## disassembly

```asm
0x180023690  mov     [rsp+arg_10], rbx
0x180023695  mov     [rsp+arg_18], rsi
0x18002369a  push    rdi
0x18002369b  sub     rsp, 50h
0x18002369f  mov     rdi, rcx
0x1800236a2  mov     rsi, rdx
0x1800236a5  mov     rcx, rdx
0x1800236a8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800236ad  mov     rcx, rdi
0x1800236b0  mov     rdx, rax
0x1800236b3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800236b8  xor     ecx, ecx; lpLocaleName
0x1800236ba  or      r9d, 0FFFFFFFFh; cchCount1
0x1800236be  mov     [rsp+58h+lParam], rcx; lParam
0x1800236c3  mov     r8, rax; lpString1
0x1800236c6  mov     [rsp+58h+lpReserved], rcx; lpReserved
0x1800236cb  mov     [rsp+58h+lpVersionInformation], rcx; lpVersionInformation
0x1800236d0  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x1800236d5  mov     [rsp+58h+lpString2], rdx; lpString2
0x1800236da  lea     edx, [rcx+4]; dwCmpFlags
0x1800236dd  call    cs:__imp_CompareStringEx
0x1800236e3  cmp     eax, 1
0x1800236e6  mov     rcx, rdi
0x1800236e9  setz    bl
0x1800236ec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800236f1  mov     rcx, rsi
0x1800236f4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800236f9  mov     rsi, [rsp+58h+arg_18]
0x1800236fe  mov     al, bl
0x180023700  mov     rbx, [rsp+58h+arg_10]
0x180023705  add     rsp, 50h
0x180023709  pop     rdi
0x18002370a  retn
```
