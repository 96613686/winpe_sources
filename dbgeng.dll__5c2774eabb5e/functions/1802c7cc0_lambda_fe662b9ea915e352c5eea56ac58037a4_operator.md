# _lambda_fe662b9ea915e352c5eea56ac58037a4_::operator()

- ea: `0x1802c7cc0`
- end: `0x1802c7f60`
- name: `_lambda_fe662b9ea915e352c5eea56ac58037a4_::operator()`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802c4264`

## callees

- `0x18007fca0`
- `0x180080424`
- `0x180080468`
- `0x1800ac8b0`
- `0x1800ac8d8`
- `0x1800e5728`
- `0x1800f0f40`
- `0x1800f13ec`
- `0x1800f1720`
- `0x1802c6e48`
- `0x1802c6e94`
- `0x1802c7cc0`
- `0x1802e3d18`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802c7eb7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802c7eb7`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x1802c7d79`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x1802c7d79`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x1802c7de3`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x1802c7de3`
- `api-ms-win-core-localregistry-l1-1-0!RegGetValueW` at `0x1802c7e6b`
- `api-ms-win-core-localregistry-l1-1-0!RegGetValueW` at `0x1802c7e6b`

## string_xrefs

- `0x1802c7d06`: `SOFTWARE\Classes\CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_fe662b9ea915e352c5eea56ac58037a4_::operator()(__int64 a1)
{
  __int64 v2; // rdx
  const WCHAR *v3; // rax
  int v4; // ebx
  bool v5; // sf
  __int64 v6; // rdx
  LSTATUS v7; // eax
  unsigned __int64 v8; // rax
  void *v9; // rdi
  LSTATUS ValueW; // eax
  const struct std::nothrow_t *v11; // rdx
  const struct std::nothrow_t *v12; // rdx
  int phkResult; // [rsp+20h] [rbp-49h]
  int phkResulta; // [rsp+20h] [rbp-49h]
  DWORD cbData; // [rsp+40h] [rbp-29h] BYREF
  DWORD Type; // [rsp+44h] [rbp-25h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-21h] BYREF
  HKEY *p_hKey; // [rsp+50h] [rbp-19h] BYREF
  HKEY v20; // [rsp+58h] [rbp-11h] BYREF
  char v21; // [rsp+60h] [rbp-9h]
  __int64 v22; // [rsp+68h] [rbp-1h]
  _BYTE v23[32]; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v22 = -2;
  if ( **(_QWORD **)a1 && *(_QWORD *)(*(_QWORD *)(a1 + 8) + 120LL) )
  {
    std::wstring::wstring(v23);
    std::wstring::append(v23, *(_QWORD *)(a1 + 8) + 104LL);
    std::wstring::append(v23, L"\\InprocServer32");
    hKey = 0;
    p_hKey = &hKey;
    v20 = 0;
    v21 = 1;
    v3 = (const WCHAR *)std::wstring::c_str(v23, v2);
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20119u, &v20);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    v5 = v4 < 0;
    if ( v4 )
    {
      if ( v4 > 0 )
      {
        v4 = (unsigned __int16)v4 | 0x80070000;
        v5 = v4 < 0;
      }
      if ( !v5 )
        goto LABEL_30;
      v6 = 6803;
    }
    else
    {
      cbData = 0;
      Type = 0;
      v7 = RegQueryValueExW(hKey, &strIn, 0, &Type, 0, &cbData);
      v4 = v7;
      if ( v7 )
      {
        if ( v7 > 0 )
          v4 = (unsigned __int16)v7 | 0x80070000;
      }
      else if ( Type == 1 && cbData )
      {
        v8 = 2LL * (cbData + 1);
        if ( !is_mul_ok(cbData + 1, 2u) )
          v8 = -1;
        v9 = operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
        if ( v9 )
        {
          ValueW = RegGetValueW(hKey, 0, &strIn, 2u, 0, v9, &cbData);
          v4 = ValueW;
          if ( ValueW )
          {
            if ( ValueW > 0 )
              v4 = (unsigned __int16)ValueW | 0x80070000;
            if ( v4 < 0 )
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1AB1,
                (unsigned int)"onecore\\sdktools\\debuggers\\ntsd64\\target.cpp",
                (const char *)(unsigned int)v4,
                phkResulta);
            operator delete(v9, v11);
          }
          else
          {
            if ( _wcsicmp((const wchar_t *)v9, **(const wchar_t ***)a1) || !FileExists(**(const unsigned __int16 ***)a1) )
            {
              operator delete(v9, v12);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              std::wstring::_Tidy_deallocate(v23);
              return 2147500037LL;
            }
            operator delete(v9, v12);
            v4 = 0;
          }
        }
        else
        {
          v4 = -2147024882;
        }
        goto LABEL_30;
      }
      if ( v4 >= 0 )
      {
LABEL_30:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::wstring::_Tidy_deallocate(v23);
        return (unsigned int)v4;
      }
      v6 = 6816;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\sdktools\\debuggers\\ntsd64\\target.cpp",
      (const char *)(unsigned int)v4,
      phkResult);
    goto LABEL_30;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1802c7cc0  push    rbp
0x1802c7cc2  push    rbx
0x1802c7cc3  push    rsi
0x1802c7cc4  push    rdi
0x1802c7cc5  lea     rbp, [rsp-3Fh]
0x1802c7cca  sub     rsp, 0A8h
0x1802c7cd1  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x1802c7cd9  mov     rax, cs:__security_cookie
0x1802c7ce0  xor     rax, rsp
0x1802c7ce3  mov     [rbp+57h+var_30], rax
0x1802c7ce7  mov     rsi, rcx
0x1802c7cea  mov     rax, [rcx]
0x1802c7ced  cmp     qword ptr [rax], 0
0x1802c7cf1  jz      loc_1802C7F42
0x1802c7cf7  mov     rax, [rcx+8]
0x1802c7cfb  cmp     qword ptr [rax+78h], 0
0x1802c7d00  jz      loc_1802C7F42
0x1802c7d06  lea     rdx, aSoftwareClasse; "SOFTWARE\\Classes\\CLSID\\"
0x1802c7d0d  lea     rcx, [rbp+57h+var_50]
0x1802c7d11  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1802c7d16  nop
0x1802c7d17  mov     rdx, [rsi+8]
0x1802c7d1b  add     rdx, 68h ; 'h'
0x1802c7d1f  lea     rcx, [rbp+57h+var_50]
0x1802c7d23  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1802c7d28  lea     rdx, aInprocserver32; "\\InprocServer32"
0x1802c7d2f  lea     rcx, [rbp+57h+var_50]
0x1802c7d33  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1802c7d38  mov     [rbp+57h+hKey], 0
0x1802c7d40  lea     rax, [rbp+57h+hKey]
0x1802c7d44  mov     [rbp+57h+var_70], rax
0x1802c7d48  mov     [rbp+57h+var_68], 0
0x1802c7d50  mov     [rbp+57h+var_60], 1
0x1802c7d54  lea     rcx, [rbp+57h+var_50]
0x1802c7d58  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1802c7d5d  mov     rdx, rax; lpSubKey
0x1802c7d60  lea     rax, [rbp+57h+var_68]
0x1802c7d64  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1802c7d69  mov     r9d, 20119h; samDesired
0x1802c7d6f  xor     r8d, r8d; ulOptions
0x1802c7d72  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1802c7d79  call    cs:__imp_RegOpenKeyExW
0x1802c7d80  nop     dword ptr [rax+rax+00h]
0x1802c7d85  mov     ebx, eax
0x1802c7d87  lea     rcx, [rbp+57h+var_70]
0x1802c7d8b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1802c7d90  test    ebx, ebx
0x1802c7d92  jz      short loc_1802C7DB1
0x1802c7d94  jle     short loc_1802C7DA1
0x1802c7d96  movzx   ebx, bx
0x1802c7d99  or      ebx, 80070000h
0x1802c7d9f  test    ebx, ebx
0x1802c7da1  jns     loc_1802C7F2B
0x1802c7da7  mov     edx, 1A93h
0x1802c7dac  jmp     loc_1802C7F18
0x1802c7db1  mov     [rbp+57h+cbData], 0
0x1802c7db8  mov     [rbp+57h+Type], 0
0x1802c7dbf  lea     rax, [rbp+57h+cbData]
0x1802c7dc3  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x1802c7dc8  mov     [rsp+0C0h+phkResult], 0; int
0x1802c7dd1  lea     r9, [rbp+57h+Type]; lpType
0x1802c7dd5  xor     r8d, r8d; lpReserved
0x1802c7dd8  lea     rdx, strIn; lpValueName
0x1802c7ddf  mov     rcx, [rbp+57h+hKey]; hKey
0x1802c7de3  call    cs:__imp_RegQueryValueExW
0x1802c7dea  nop     dword ptr [rax+rax+00h]
0x1802c7def  mov     ebx, eax
0x1802c7df1  test    eax, eax
0x1802c7df3  jnz     loc_1802C7F04
0x1802c7df9  cmp     [rbp+57h+Type], 1
0x1802c7dfd  jnz     loc_1802C7F0F
0x1802c7e03  mov     eax, [rbp+57h+cbData]
0x1802c7e06  test    eax, eax
0x1802c7e08  jz      loc_1802C7F0F
0x1802c7e0e  lea     ecx, [rax+1]
0x1802c7e11  mov     ebx, 2
0x1802c7e16  mov     eax, ebx
0x1802c7e18  mul     rcx
0x1802c7e1b  lea     rcx, [rbx-3]
0x1802c7e1f  cmovb   rax, rcx
0x1802c7e23  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1802c7e2a  mov     rcx, rax; unsigned __int64
0x1802c7e2d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1802c7e32  mov     rdi, rax
0x1802c7e35  test    rax, rax
0x1802c7e38  jnz     short loc_1802C7E44
0x1802c7e3a  mov     ebx, 8007000Eh
0x1802c7e3f  jmp     loc_1802C7F2B
0x1802c7e44  lea     rax, [rbp+57h+cbData]
0x1802c7e48  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1802c7e4d  mov     [rsp+0C0h+lpcbData], rdi; pvData
0x1802c7e52  mov     [rsp+0C0h+phkResult], 0; int
0x1802c7e5b  mov     r9d, ebx; dwFlags
0x1802c7e5e  lea     r8, strIn; lpValue
0x1802c7e65  xor     edx, edx; lpSubKey
0x1802c7e67  mov     rcx, [rbp+57h+hKey]; hkey
0x1802c7e6b  call    cs:__imp_RegGetValueW
0x1802c7e72  nop     dword ptr [rax+rax+00h]
0x1802c7e77  mov     ebx, eax
0x1802c7e79  test    eax, eax
0x1802c7e7b  jz      short loc_1802C7EAE
0x1802c7e7d  jle     short loc_1802C7E88
0x1802c7e7f  movzx   ebx, ax
0x1802c7e82  or      ebx, 80070000h
0x1802c7e88  test    ebx, ebx
0x1802c7e8a  jns     short loc_1802C7EA4
0x1802c7e8c  mov     rcx, [rbp+5Fh]; this
0x1802c7e90  mov     r9d, ebx; char *
0x1802c7e93  lea     r8, aOnecoreSdktool_7; "onecore\\sdktools\\debuggers\\ntsd64\\t"...
0x1802c7e9a  mov     edx, 1AB1h; void *
0x1802c7e9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802c7ea4  mov     rcx, rdi; void *
0x1802c7ea7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1802c7eac  jmp     short loc_1802C7F2B
0x1802c7eae  mov     rdx, [rsi]
0x1802c7eb1  mov     rdx, [rdx]; String2
0x1802c7eb4  mov     rcx, rdi; String1
0x1802c7eb7  call    cs:__imp__wcsicmp
0x1802c7ebe  nop     dword ptr [rax+rax+00h]
0x1802c7ec3  test    eax, eax
0x1802c7ec5  jnz     short loc_1802C7EE2
0x1802c7ec7  mov     rcx, [rsi]
0x1802c7eca  mov     rcx, [rcx]; unsigned __int16 *
0x1802c7ecd  call    ?FileExists@@YA_NPEBG@Z; FileExists(ushort const *)
0x1802c7ed2  test    al, al
0x1802c7ed4  jz      short loc_1802C7EE2
0x1802c7ed6  mov     rcx, rdi; void *
0x1802c7ed9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1802c7ede  xor     ebx, ebx
0x1802c7ee0  jmp     short loc_1802C7F2B
0x1802c7ee2  mov     rcx, rdi; void *
0x1802c7ee5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1802c7eea  lea     rcx, [rbp+57h+hKey]
0x1802c7eee  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1802c7ef3  nop
0x1802c7ef4  lea     rcx, [rbp+57h+var_50]
0x1802c7ef8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802c7efd  mov     eax, 80004005h
0x1802c7f02  jmp     short loc_1802C7F47
0x1802c7f04  jle     short loc_1802C7F0F
0x1802c7f06  movzx   ebx, ax
0x1802c7f09  or      ebx, 80070000h
0x1802c7f0f  test    ebx, ebx
0x1802c7f11  jns     short loc_1802C7F2B
0x1802c7f13  mov     edx, 1AA0h; void *
0x1802c7f18  mov     r9d, ebx; char *
0x1802c7f1b  lea     r8, aOnecoreSdktool_7; "onecore\\sdktools\\debuggers\\ntsd64\\t"...
0x1802c7f22  mov     rcx, [rbp+5Fh]; this
0x1802c7f26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802c7f2b  lea     rcx, [rbp+57h+hKey]
0x1802c7f2f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1802c7f34  nop
0x1802c7f35  lea     rcx, [rbp+57h+var_50]
0x1802c7f39  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802c7f3e  mov     eax, ebx
0x1802c7f40  jmp     short loc_1802C7F47
0x1802c7f42  mov     eax, 80070057h
0x1802c7f47  mov     rcx, [rbp+57h+var_30]
0x1802c7f4b  xor     rcx, rsp; StackCookie
0x1802c7f4e  call    __security_check_cookie
0x1802c7f53  add     rsp, 0A8h
0x1802c7f5a  pop     rdi
0x1802c7f5b  pop     rsi
0x1802c7f5c  pop     rbx
0x1802c7f5d  pop     rbp
0x1802c7f5e  retn
```
