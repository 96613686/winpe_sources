# EapLm::Peer::BaseEapMethodRuntime::LoadConfig(void)

- ea: `0x18001926c`
- end: `0x1800193b3`
- name: `?LoadConfig@BaseEapMethodRuntime@Peer@EapLm@@IEAAXXZ`
- size: `327`
- prototype: `void __fastcall(EapLm::Peer::BaseEapMethodRuntime *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180019200`

## callees

- `0x180002a90`
- `0x1800118e8`
- `0x180011908`
- `0x180018f34`
- `0x18001926c`
- `0x18001dcbc`
- `0x1800300fc`
- `0x1800301fc`
- `0x18003044c`
- `0x180030530`
- `0x180038010`

## string_xrefs

- `0x180019343`: `LoadConfig`
- `0x1800192fd`: `RegistryKey::Open`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EapLm::Peer::BaseEapMethodRuntime::LoadConfig(EapLm::Peer::BaseEapMethodRuntime *this)
{
  __int64 v2; // rax
  const WCHAR *v3; // rax
  const wchar_t *v4; // rax
  __int64 v5; // rax
  const wchar_t *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  HKEY v9; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h]

  v2 = (*(__int64 (__fastcall **)(EapLm::Peer::BaseEapMethodRuntime *, HKEY *))(*(_QWORD *)this + 128LL))(this, &v9);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::operator=((char *)this + 32, v2);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)&v9);
  v9 = 0;
  v10 = 1;
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  if ( (unsigned int)RegistryKey::Open((__int64)&v9, HKEY_LOCAL_MACHINE, v3, 1) )
  {
    v4 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    EapHost::EapException::Throw(L"RegistryKey::Open", v4, -2147024809);
  }
  v5 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  if ( (unsigned int)RegistryKey::QueryValue(&v9, v5, (char *)this + 144) == 1 )
  {
    v6 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    EapHost::EapException::Throw(L"LoadConfig", v6, -2147024809);
  }
  v7 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  RegistryKey::QueryValue(&v9, v7, (char *)this + 137);
  v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  RegistryKey::QueryValue(&v9, v8, (char *)this + 138);
  RegistryKey::Clear(&v9);
}

```

## disassembly

```asm
0x18001926c  mov     [rsp+arg_8], rbx
0x180019271  push    rdi
0x180019272  sub     rsp, 50h
0x180019276  mov     rax, cs:__security_cookie
0x18001927d  xor     rax, rsp
0x180019280  mov     [rsp+58h+var_18], rax
0x180019285  mov     rbx, rcx
0x180019288  mov     rax, [rcx]
0x18001928b  lea     rdx, [rsp+58h+var_38]
0x180019290  mov     rax, [rax+80h]
0x180019297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001929c  lea     rdi, [rbx+20h]
0x1800192a0  mov     rdx, rax
0x1800192a3  mov     rcx, rdi
0x1800192a6  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::operator=(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&)
0x1800192ab  lea     rcx, [rsp+58h+var_38]
0x1800192b0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x1800192b5  mov     [rsp+58h+var_38], 0
0x1800192be  mov     [rsp+58h+var_30], 1
0x1800192c6  mov     rcx, rdi
0x1800192c9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800192ce  mov     r9d, 1
0x1800192d4  mov     r8, rax
0x1800192d7  mov     rdx, 0FFFFFFFF80000002h
0x1800192de  lea     rcx, [rsp+58h+var_38]
0x1800192e3  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1800192e8  test    eax, eax
0x1800192ea  jz      short loc_18001930A
0x1800192ec  mov     rcx, rdi
0x1800192ef  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800192f4  mov     r8d, 80070057h; int
0x1800192fa  mov     rdx, rax; wchar_t *
0x1800192fd  lea     rcx, aRegistrykeyOpe; "RegistryKey::Open"
0x180019304  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x18001930a  lea     rdi, [rbx+0B0h]
0x180019311  mov     rcx, rdi
0x180019314  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180019319  lea     r8, [rbx+90h]
0x180019320  mov     rdx, rax
0x180019323  lea     rcx, [rsp+58h+var_38]
0x180019328  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001932d  cmp     eax, 1
0x180019330  jnz     short loc_180019350
0x180019332  mov     rcx, rdi
0x180019335  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001933a  mov     r8d, 80070057h; int
0x180019340  mov     rdx, rax; wchar_t *
0x180019343  lea     rcx, aLoadconfig; "LoadConfig"
0x18001934a  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180019350  lea     rcx, [rbx+0D0h]
0x180019357  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001935c  lea     r8, [rbx+89h]
0x180019363  mov     rdx, rax
0x180019366  lea     rcx, [rsp+58h+var_38]
0x18001936b  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEA_N@Z; RegistryKey::QueryValue(wchar_t const *,bool &)
0x180019370  lea     rcx, [rbx+0F0h]
0x180019377  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001937c  lea     r8, [rbx+8Ah]
0x180019383  mov     rdx, rax
0x180019386  lea     rcx, [rsp+58h+var_38]
0x18001938b  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEA_N@Z; RegistryKey::QueryValue(wchar_t const *,bool &)
0x180019390  nop
0x180019391  lea     rcx, [rsp+58h+var_38]; this
0x180019396  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001939b  mov     rcx, [rsp+58h+var_18]
0x1800193a0  xor     rcx, rsp; StackCookie
0x1800193a3  call    __security_check_cookie
0x1800193a8  mov     rbx, [rsp+58h+arg_8]
0x1800193ad  add     rsp, 50h
0x1800193b1  pop     rdi
0x1800193b2  retn
```
