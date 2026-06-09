# EapLm::Peer::BaseEapMethodRuntime::LoadConfig(void)

- ea: `0x18002990c`
- end: `0x180029a53`
- name: `?LoadConfig@BaseEapMethodRuntime@Peer@EapLm@@IEAAXXZ`
- size: `327`
- prototype: `void __fastcall(EapLm::Peer::BaseEapMethodRuntime *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800298a0`

## callees

- `0x1800017a0`
- `0x18000eb74`
- `0x18000eb94`
- `0x180015534`
- `0x180029678`
- `0x18002990c`
- `0x18002a7dc`
- `0x18002a8dc`
- `0x18002ab2c`
- `0x18002ac10`
- `0x180034010`

## string_xrefs

- `0x1800299e3`: `LoadConfig`
- `0x18002999d`: `RegistryKey::Open`

## pseudocode

```c
void __fastcall EapLm::Peer::BaseEapMethodRuntime::LoadConfig(EapLm::Peer::BaseEapMethodRuntime *this)
{
  __int64 v2; // rax
  __int64 v3; // rax
  const wchar_t *v4; // rax
  __int64 v5; // rax
  const wchar_t *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h]

  v2 = (*(__int64 (__fastcall **)(EapLm::Peer::BaseEapMethodRuntime *, __int64 *))(*(_QWORD *)this + 128LL))(this, &v9);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::operator=((char *)this + 32, v2);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(&v9);
  v9 = 0;
  v10 = 1;
  v3 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 32);
  if ( (unsigned int)RegistryKey::Open(&v9, -2147483646, v3, 1) )
  {
    v4 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 32);
    EapHost::EapException::Throw(L"RegistryKey::Open", v4, -2147024809);
  }
  v5 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 176);
  if ( (unsigned int)RegistryKey::QueryValue(&v9, v5, (char *)this + 144) == 1 )
  {
    v6 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 176);
    EapHost::EapException::Throw(L"LoadConfig", v6, -2147024809);
  }
  v7 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 208);
  RegistryKey::QueryValue(&v9, v7, (char *)this + 137);
  v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 240);
  RegistryKey::QueryValue(&v9, v8, (char *)this + 138);
  RegistryKey::Clear((RegistryKey *)&v9);
}

```

## disassembly

```asm
0x18002990c  mov     [rsp+arg_8], rbx
0x180029911  push    rdi
0x180029912  sub     rsp, 50h
0x180029916  mov     rax, cs:__security_cookie
0x18002991d  xor     rax, rsp
0x180029920  mov     [rsp+58h+var_18], rax
0x180029925  mov     rbx, rcx
0x180029928  mov     rax, [rcx]
0x18002992b  lea     rdx, [rsp+58h+var_38]
0x180029930  mov     rax, [rax+80h]
0x180029937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002993c  lea     rdi, [rbx+20h]
0x180029940  mov     rdx, rax
0x180029943  mov     rcx, rdi
0x180029946  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::operator=(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&)
0x18002994b  lea     rcx, [rsp+58h+var_38]
0x180029950  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180029955  mov     [rsp+58h+var_38], 0
0x18002995e  mov     [rsp+58h+var_30], 1
0x180029966  mov     rcx, rdi
0x180029969  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002996e  mov     r9d, 1
0x180029974  mov     r8, rax
0x180029977  mov     rdx, 0FFFFFFFF80000002h
0x18002997e  lea     rcx, [rsp+58h+var_38]
0x180029983  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180029988  test    eax, eax
0x18002998a  jz      short loc_1800299AA
0x18002998c  mov     rcx, rdi
0x18002998f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180029994  mov     r8d, 80070057h; int
0x18002999a  mov     rdx, rax; wchar_t *
0x18002999d  lea     rcx, aRegistrykeyOpe; "RegistryKey::Open"
0x1800299a4  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x1800299aa  lea     rdi, [rbx+0B0h]
0x1800299b1  mov     rcx, rdi
0x1800299b4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800299b9  lea     r8, [rbx+90h]
0x1800299c0  mov     rdx, rax
0x1800299c3  lea     rcx, [rsp+58h+var_38]
0x1800299c8  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x1800299cd  cmp     eax, 1
0x1800299d0  jnz     short loc_1800299F0
0x1800299d2  mov     rcx, rdi
0x1800299d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800299da  mov     r8d, 80070057h; int
0x1800299e0  mov     rdx, rax; wchar_t *
0x1800299e3  lea     rcx, aLoadconfig; "LoadConfig"
0x1800299ea  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x1800299f0  lea     rcx, [rbx+0D0h]
0x1800299f7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800299fc  lea     r8, [rbx+89h]
0x180029a03  mov     rdx, rax
0x180029a06  lea     rcx, [rsp+58h+var_38]
0x180029a0b  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEA_N@Z; RegistryKey::QueryValue(wchar_t const *,bool &)
0x180029a10  lea     rcx, [rbx+0F0h]
0x180029a17  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180029a1c  lea     r8, [rbx+8Ah]
0x180029a23  mov     rdx, rax
0x180029a26  lea     rcx, [rsp+58h+var_38]
0x180029a2b  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEA_N@Z; RegistryKey::QueryValue(wchar_t const *,bool &)
0x180029a30  nop
0x180029a31  lea     rcx, [rsp+58h+var_38]; this
0x180029a36  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x180029a3b  mov     rcx, [rsp+58h+var_18]
0x180029a40  xor     rcx, rsp; StackCookie
0x180029a43  call    __security_check_cookie
0x180029a48  mov     rbx, [rsp+58h+arg_8]
0x180029a4d  add     rsp, 50h
0x180029a51  pop     rdi
0x180029a52  retn
```
