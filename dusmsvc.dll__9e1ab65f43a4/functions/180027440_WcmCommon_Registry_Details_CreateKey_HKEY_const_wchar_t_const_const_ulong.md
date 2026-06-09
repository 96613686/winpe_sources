# WcmCommon::Registry::Details::CreateKey(HKEY__ * const,wchar_t const * const,ulong)

- ea: `0x180027440`
- end: `0x180027520`
- name: `?CreateKey@Details@Registry@WcmCommon@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAUHKEY__@@QEB_WK@Z`
- size: `224`
- prototype: `_QWORD *__fastcall(_QWORD *, HKEY, const WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027528`

## callees

- `0x180007c90`
- `0x1800172c8`
- `0x180026f54`
- `0x180027440`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800274c8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800274c8`

## string_xrefs

- `0x1800274e9`: `onecore\private\net\inc\wcm\wcm_registry_details.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall WcmCommon::Registry::Details::CreateKey(_QWORD *a1, HKEY a2, const WCHAR *a3)
{
  unsigned int v4; // edi
  DWORD dwOptions; // [rsp+20h] [rbp-78h]
  _QWORD *v7; // [rsp+58h] [rbp-40h] BYREF
  HKEY v8; // [rsp+60h] [rbp-38h] BYREF
  char v9; // [rsp+68h] [rbp-30h]
  _QWORD *v10; // [rsp+70h] [rbp-28h]
  DWORD v11; // [rsp+78h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v10 = a1;
  *a1 = 0;
  v11 = 0;
  v7 = a1;
  v8 = 0;
  v9 = 1;
  v4 = RegCreateKeyExW(a2, a3, 0, 0, 0, 0xF003Fu, 0, &v8, &v11);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v7);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_registry_details.h",
      (const char *)v4,
      dwOptions);
  return a1;
}

```

## disassembly

```asm
0x180027440  mov     r11, rsp
0x180027443  mov     [r11+20h], rbx
0x180027447  push    rdi
0x180027448  sub     rsp, 90h
0x18002744f  mov     rax, cs:__security_cookie
0x180027456  xor     rax, rsp
0x180027459  mov     [rsp+98h+var_18], rax
0x180027461  mov     r10, r8
0x180027464  mov     rax, rdx
0x180027467  mov     rbx, rcx
0x18002746a  mov     [r11-28h], rcx
0x18002746e  mov     [rsp+98h+var_48], 0
0x180027476  xor     ecx, ecx
0x180027478  mov     [rbx], rcx
0x18002747b  mov     [rsp+98h+var_48], 1
0x180027483  mov     [rsp+98h+var_20], ecx
0x180027487  mov     [r11-40h], rbx
0x18002748b  mov     [r11-38h], rcx
0x18002748f  mov     [rsp+98h+var_30], 1
0x180027494  lea     rcx, [r11-20h]
0x180027498  mov     [r11-58h], rcx
0x18002749c  lea     rcx, [r11-38h]
0x1800274a0  mov     [r11-60h], rcx
0x1800274a4  mov     qword ptr [r11-68h], 0
0x1800274ac  mov     [rsp+98h+samDesired], 0F003Fh; samDesired
0x1800274b4  mov     [rsp+98h+dwOptions], 0; unsigned int
0x1800274bc  xor     r9d, r9d; lpClass
0x1800274bf  xor     r8d, r8d; Reserved
0x1800274c2  mov     rdx, r10; lpSubKey
0x1800274c5  mov     rcx, rax; hKey
0x1800274c8  call    cs:__imp_RegCreateKeyExW
0x1800274ce  mov     edi, eax
0x1800274d0  lea     rcx, [rsp+98h+var_40]
0x1800274d5  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800274da  test    edi, edi
0x1800274dc  jz      short loc_1800274FB
0x1800274de  mov     rcx, [rsp+98h]; this
0x1800274e6  mov     r9d, edi; char *
0x1800274e9  lea     r8, aOnecorePrivate_3; "onecore\\private\\net\\inc\\wcm\\wcm_re"...
0x1800274f0  mov     edx, 45h ; 'E'; void *
0x1800274f5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800274fb  mov     rax, rbx
0x1800274fe  mov     rcx, [rsp+98h+var_18]
0x180027506  xor     rcx, rsp; StackCookie
0x180027509  call    __security_check_cookie
0x18002750e  mov     rbx, [rsp+98h+arg_18]
0x180027516  add     rsp, 90h
0x18002751d  pop     rdi
0x18002751e  retn
```
