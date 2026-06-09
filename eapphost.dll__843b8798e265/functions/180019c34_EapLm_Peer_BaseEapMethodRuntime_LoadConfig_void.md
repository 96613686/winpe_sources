# EapLm::Peer::BaseEapMethodRuntime::LoadConfig(void)

- ea: `0x180019c34`
- end: `0x180019d7c`
- name: `?LoadConfig@BaseEapMethodRuntime@Peer@EapLm@@IEAAXXZ`
- size: `328`
- prototype: `void __fastcall(EapLm::Peer::BaseEapMethodRuntime *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180019bc0`

## callees

- `0x180002af0`
- `0x18001204c`
- `0x18001206c`
- `0x1800198ec`
- `0x180019c34`
- `0x18001e7c0`
- `0x180031314`
- `0x180031424`
- `0x18003165c`
- `0x180031740`
- `0x180039010`

## string_xrefs

- `0x180019d0b`: `LoadConfig`
- `0x180019cc5`: `RegistryKey::Open`

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
  __int64 v9; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h]

  v2 = (*(__int64 (__fastcall **)(EapLm::Peer::BaseEapMethodRuntime *, __int64 *))(*(_QWORD *)this + 128LL))(this, &v9);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::operator=((char *)this + 32, v2);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(&v9);
  v9 = 0;
  v10 = 1;
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 32);
  if ( (unsigned int)RegistryKey::Open((RegistryKey *)&v9, HKEY_LOCAL_MACHINE, v3, 1) )
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
0x180019c34  mov     [rsp+arg_8], rbx
0x180019c39  push    rdi
0x180019c3a  sub     rsp, 50h
0x180019c3e  mov     rax, cs:__security_cookie
0x180019c45  xor     rax, rsp
0x180019c48  mov     [rsp+58h+var_18], rax
0x180019c4d  mov     rbx, rcx
0x180019c50  mov     rax, [rcx]
0x180019c53  lea     rdx, [rsp+58h+var_38]
0x180019c58  mov     rax, [rax+80h]
0x180019c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c64  lea     rdi, [rbx+20h]
0x180019c68  mov     rdx, rax
0x180019c6b  mov     rcx, rdi
0x180019c6e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::operator=(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&)
0x180019c73  lea     rcx, [rsp+58h+var_38]
0x180019c78  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180019c7d  mov     [rsp+58h+var_38], 0
0x180019c86  mov     [rsp+58h+var_30], 1
0x180019c8e  mov     rcx, rdi
0x180019c91  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180019c96  mov     r9d, 1
0x180019c9c  mov     r8, rax
0x180019c9f  mov     rdx, 0FFFFFFFF80000002h
0x180019ca6  lea     rcx, [rsp+58h+var_38]
0x180019cab  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180019cb0  test    eax, eax
0x180019cb2  jz      short loc_180019CD2
0x180019cb4  mov     rcx, rdi
0x180019cb7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180019cbc  mov     r8d, 80070057h; int
0x180019cc2  mov     rdx, rax; wchar_t *
0x180019cc5  lea     rcx, aRegistrykeyOpe; "RegistryKey::Open"
0x180019ccc  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180019cd2  lea     rdi, [rbx+0B0h]
0x180019cd9  mov     rcx, rdi
0x180019cdc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180019ce1  lea     r8, [rbx+90h]
0x180019ce8  mov     rdx, rax
0x180019ceb  lea     rcx, [rsp+58h+var_38]
0x180019cf0  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x180019cf5  cmp     eax, 1
0x180019cf8  jnz     short loc_180019D18
0x180019cfa  mov     rcx, rdi
0x180019cfd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180019d02  mov     r8d, 80070057h; int
0x180019d08  mov     rdx, rax; wchar_t *
0x180019d0b  lea     rcx, aLoadconfig; "LoadConfig"
0x180019d12  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180019d18  lea     rcx, [rbx+0D0h]
0x180019d1f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180019d24  lea     r8, [rbx+89h]
0x180019d2b  mov     rdx, rax
0x180019d2e  lea     rcx, [rsp+58h+var_38]
0x180019d33  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEA_N@Z; RegistryKey::QueryValue(wchar_t const *,bool &)
0x180019d38  lea     rcx, [rbx+0F0h]
0x180019d3f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180019d44  lea     r8, [rbx+8Ah]
0x180019d4b  mov     rdx, rax
0x180019d4e  lea     rcx, [rsp+58h+var_38]
0x180019d53  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEA_N@Z; RegistryKey::QueryValue(wchar_t const *,bool &)
0x180019d58  nop
0x180019d59  lea     rcx, [rsp+58h+var_38]; this
0x180019d5e  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x180019d63  mov     rcx, [rsp+58h+var_18]
0x180019d68  xor     rcx, rsp; StackCookie
0x180019d6b  call    __security_check_cookie
0x180019d70  mov     rbx, [rsp+58h+arg_8]
0x180019d75  add     rsp, 50h
0x180019d79  pop     rdi
0x180019d7a  retn
```
