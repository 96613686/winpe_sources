# EapLm::Peer::LegacyEapMethodRuntime::LegacyEapMethodRuntime(_EAP_METHOD_TYPE const &)

- ea: `0x180012b74`
- end: `0x180012c7b`
- name: `??0LegacyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z`
- size: `263`
- prototype: `__int64 __fastcall(EapLm::Peer::LegacyEapMethodRuntime *__hidden this, const struct _EAP_METHOD_TYPE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800113c0`

## callees

- `0x180002af0`
- `0x18001206c`
- `0x180012a28`
- `0x18001978c`

## string_xrefs

- `0x180012c30`: `%windir%\system32\eapgenid.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
EapLm::Peer::LegacyEapMethodRuntime *__fastcall EapLm::Peer::LegacyEapMethodRuntime::LegacyEapMethodRuntime(
        EapLm::Peer::LegacyEapMethodRuntime *this,
        const struct _EAP_METHOD_TYPE *a2)
{
  int v2; // ebx
  _BYTE v5[32]; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v6[32]; // [rsp+58h] [rbp-50h] BYREF
  _BYTE v7[32]; // [rsp+78h] [rbp-30h] BYREF

  v2 = (int)a2;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v7,
    L"InvokePasswordDialog");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v6,
    L"InvokeUsernameDialog");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v5,
    L"Path");
  EapLm::Peer::BaseEapMethodRuntime::BaseEapMethodRuntime(
    (_DWORD)this,
    v2,
    (unsigned int)v5,
    (unsigned int)v6,
    (__int64)v7);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v5);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v6);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v7);
  *(_QWORD *)this = &EapLm::Peer::LegacyEapMethodRuntime::`vftable';
  *((_QWORD *)this + 38) = 0;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (char *)this + 312,
    L"%windir%\\system32\\eapgenid.dll");
  *(_OWORD *)((char *)this + 344) = 0;
  *(_OWORD *)((char *)this + 360) = 0;
  *((_QWORD *)this + 47) = 0;
  return this;
}

```

## disassembly

```asm
0x180012b74  mov     [rsp+arg_8], rbx
0x180012b79  push    rdi
0x180012b7a  sub     rsp, 0A0h
0x180012b81  mov     rax, cs:__security_cookie
0x180012b88  xor     rax, rsp
0x180012b8b  mov     [rsp+0A8h+var_10], rax
0x180012b93  mov     rbx, rdx
0x180012b96  mov     rdi, rcx
0x180012b99  mov     [rsp+0A8h+var_78], rcx
0x180012b9e  lea     rdx, aInvokepassword; "InvokePasswordDialog"
0x180012ba5  lea     rcx, [rsp+0A8h+var_30]
0x180012baa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180012baf  nop
0x180012bb0  lea     rdx, aInvokeusername; "InvokeUsernameDialog"
0x180012bb7  lea     rcx, [rsp+0A8h+var_50]
0x180012bbc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180012bc1  nop
0x180012bc2  lea     rdx, aPath; "Path"
0x180012bc9  lea     rcx, [rsp+0A8h+var_70]
0x180012bce  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180012bd3  nop
0x180012bd4  lea     rax, [rsp+0A8h+var_30]
0x180012bd9  mov     [rsp+0A8h+var_88], rax
0x180012bde  lea     r9, [rsp+0A8h+var_50]
0x180012be3  lea     r8, [rsp+0A8h+var_70]
0x180012be8  mov     rdx, rbx
0x180012beb  mov     rcx, rdi
0x180012bee  call    ??0BaseEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@11@Z; EapLm::Peer::BaseEapMethodRuntime::BaseEapMethodRuntime(_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x180012bf3  nop
0x180012bf4  lea     rcx, [rsp+0A8h+var_70]
0x180012bf9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180012bfe  nop
0x180012bff  lea     rcx, [rsp+0A8h+var_50]
0x180012c04  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180012c09  nop
0x180012c0a  lea     rcx, [rsp+0A8h+var_30]
0x180012c0f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180012c14  lea     rax, ??_7LegacyEapMethodRuntime@Peer@EapLm@@6B@; const EapLm::Peer::LegacyEapMethodRuntime::`vftable'
0x180012c1b  mov     [rdi], rax
0x180012c1e  mov     qword ptr [rdi+130h], 0
0x180012c29  lea     rcx, [rdi+138h]
0x180012c30  lea     rdx, aWindirSystem32; "%windir%\\system32\\eapgenid.dll"
0x180012c37  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180012c3c  xorps   xmm0, xmm0
0x180012c3f  xor     eax, eax
0x180012c41  movups  xmmword ptr [rdi+158h], xmm0
0x180012c48  movups  xmmword ptr [rdi+168h], xmm0
0x180012c4f  mov     [rdi+178h], rax
0x180012c56  mov     rax, rdi
0x180012c59  mov     rcx, [rsp+0A8h+var_10]
0x180012c61  xor     rcx, rsp; StackCookie
0x180012c64  call    __security_check_cookie
0x180012c69  mov     rbx, [rsp+0A8h+arg_8]
0x180012c71  add     rsp, 0A0h
0x180012c78  pop     rdi
0x180012c79  retn
```
