# cxl::CaseInsensitive_LessThan::operator()(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180093f6c`
- end: `0x180094045`
- name: `??RCaseInsensitive_LessThan@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18009639c`
- `0x18009644c`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001cc2c`
- `0x18001d284`
- `0x180028f30`
- `0x180093f6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093fe4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180093fc6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180093fc6`

## string_xrefs

- `0x180093fd0`: `CompareStringW`

## pseudocode

```c
bool __fastcall cxl::CaseInsensitive_LessThan::operator()(__int64 a1, __int64 a2, __int64 a3)
{
  const WCHAR *lpString2; // rbx
  const WCHAR *v6; // rax
  int v7; // eax
  __int64 v8; // rbx
  _DWORD v10[2]; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v11[40]; // [rsp+38h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+60h] [rbp-88h] BYREF

  lpString2 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  v7 = CompareStringW(0x400u, 1u, v6, *(_DWORD *)(a2 + 16), lpString2, *(_DWORD *)(a3 + 16));
  if ( !v7 )
  {
    v8 = std::wstring::wstring(v11, L"CompareStringW");
    v10[0] = GetLastError();
    v10[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v10, v8);
    throw (cxl::Exception *)pExceptionObject;
  }
  return v7 == 1;
}

```

## disassembly

```asm
0x180093f6c  mov     [rsp+arg_0], rbx
0x180093f71  mov     [rsp+arg_18], rsi
0x180093f76  push    rdi
0x180093f77  sub     rsp, 0E0h
0x180093f7e  mov     rax, cs:__security_cookie
0x180093f85  xor     rax, rsp
0x180093f88  mov     [rsp+0E8h+var_18], rax
0x180093f90  mov     rdi, r8
0x180093f93  mov     rsi, rdx
0x180093f96  mov     rcx, r8
0x180093f99  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180093f9e  mov     rbx, rax
0x180093fa1  mov     rcx, rsi
0x180093fa4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180093fa9  mov     ecx, [rdi+10h]
0x180093fac  mov     [rsp+0E8h+cchCount2], ecx; cchCount2
0x180093fb0  mov     [rsp+0E8h+lpString2], rbx; lpString2
0x180093fb5  mov     r9d, [rsi+10h]; cchCount1
0x180093fb9  mov     r8, rax; lpString1
0x180093fbc  mov     edx, 1; dwCmpFlags
0x180093fc1  mov     ecx, 400h; Locale
0x180093fc6  call    cs:__imp_CompareStringW
0x180093fcc  test    eax, eax
0x180093fce  jnz     short loc_18009401A
0x180093fd0  lea     rdx, aComparestringw; "CompareStringW"
0x180093fd7  lea     rcx, [rsp+0E8h+var_B0]
0x180093fdc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180093fe1  mov     rbx, rax
0x180093fe4  call    cs:__imp_GetLastError
0x180093fea  mov     [rsp+0E8h+var_B8], eax
0x180093fee  mov     [rsp+0E8h+var_B4], 0
0x180093ff6  mov     r8, rbx
0x180093ff9  lea     rdx, [rsp+0E8h+var_B8]
0x180093ffe  lea     rcx, [rsp+0E8h+pExceptionObject]
0x180094003  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180094008  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009400f  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180094014  call    _CxxThrowException_0
0x18009401a  cmp     eax, 1
0x18009401d  setz    al
0x180094020  mov     rcx, [rsp+0E8h+var_18]
0x180094028  xor     rcx, rsp; StackCookie
0x18009402b  call    __security_check_cookie
0x180094030  lea     r11, [rsp+0E8h+var_8]
0x180094038  mov     rbx, [r11+10h]
0x18009403c  mov     rsi, [r11+28h]
0x180094040  mov     rsp, r11
0x180094043  pop     rdi
0x180094044  retn
```
