# WcmCommon::Registry::Details::OpenKey(HKEY__ * const,wchar_t const * const,ulong)

- ea: `0x180027b28`
- end: `0x180027beb`
- name: `?OpenKey@Details@Registry@WcmCommon@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAUHKEY__@@QEB_WK@Z`
- size: `195`
- prototype: `_QWORD *__fastcall(_QWORD *, HKEY, const WCHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d3c8`

## callees

- `0x180007c90`
- `0x1800172c8`
- `0x180026f54`
- `0x180026fa0`
- `0x180027b28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027b82`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027b82`

## string_xrefs

- `0x180027bd9`: `onecore\private\net\inc\wcm\wcm_registry_details.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall WcmCommon::Registry::Details::OpenKey(_QWORD *a1, HKEY a2, const WCHAR *a3)
{
  unsigned int v4; // edi
  unsigned int phkResult; // [rsp+20h] [rbp-40h]
  __int64 *v7; // [rsp+38h] [rbp-28h] BYREF
  HKEY v8; // [rsp+40h] [rbp-20h] BYREF
  char v9; // [rsp+48h] [rbp-18h]
  __int64 v10; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v10 = 0;
  v7 = &v10;
  v8 = 0;
  v9 = 1;
  v4 = RegOpenKeyExW(a2, a3, 0, 0xF003Fu, &v8);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v7);
  if ( v4 )
  {
    if ( v4 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x3B,
        (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_registry_details.h",
        (const char *)v4,
        phkResult);
    *a1 = 0;
  }
  else
  {
    *a1 = v10;
    v10 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v10);
  return a1;
}

```

## disassembly

```asm
0x180027b28  push    rbp
0x180027b2a  push    rbx
0x180027b2b  push    rdi
0x180027b2c  mov     rbp, rsp
0x180027b2f  sub     rsp, 60h
0x180027b33  mov     rax, cs:__security_cookie
0x180027b3a  xor     rax, rsp
0x180027b3d  mov     [rbp+var_8], rax
0x180027b41  mov     rax, r8
0x180027b44  mov     r10, rdx
0x180027b47  mov     rbx, rcx
0x180027b4a  mov     [rbp+var_10], rcx
0x180027b4e  mov     [rbp+var_10], 0
0x180027b56  lea     rcx, [rbp+var_10]
0x180027b5a  mov     [rbp+var_28], rcx
0x180027b5e  mov     [rbp+var_20], 0
0x180027b66  mov     [rbp+var_18], 1
0x180027b6a  lea     rcx, [rbp+var_20]
0x180027b6e  mov     qword ptr [rsp+60h+phkResult], rcx; unsigned int
0x180027b73  mov     r9d, 0F003Fh; samDesired
0x180027b79  xor     r8d, r8d; ulOptions
0x180027b7c  mov     rdx, rax; lpSubKey
0x180027b7f  mov     rcx, r10; hKey
0x180027b82  call    cs:__imp_RegOpenKeyExW
0x180027b88  mov     edi, eax
0x180027b8a  lea     rcx, [rbp+var_28]
0x180027b8e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180027b93  test    edi, edi
0x180027b95  jnz     short loc_180027BC6
0x180027b97  mov     rcx, [rbp+var_10]
0x180027b9b  mov     [rbx], rcx
0x180027b9e  mov     [rbp+var_10], 0
0x180027ba6  lea     rcx, [rbp+var_10]
0x180027baa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180027baf  mov     rax, rbx
0x180027bb2  mov     rcx, [rbp+var_8]
0x180027bb6  xor     rcx, rsp; StackCookie
0x180027bb9  call    __security_check_cookie
0x180027bbe  add     rsp, 60h
0x180027bc2  pop     rdi
0x180027bc3  pop     rbx
0x180027bc4  pop     rbp
0x180027bc5  retn
0x180027bc6  cmp     edi, 2
0x180027bc9  jnz     short loc_180027BD2
0x180027bcb  xor     eax, eax
0x180027bcd  mov     [rbx], rax
0x180027bd0  jmp     short loc_180027BA6
0x180027bd2  mov     rcx, [rbp+18h]; this
0x180027bd6  mov     r9d, edi; char *
0x180027bd9  lea     r8, aOnecorePrivate_3; "onecore\\private\\net\\inc\\wcm\\wcm_re"...
0x180027be0  mov     edx, 3Bh ; ';'; void *
0x180027be5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
