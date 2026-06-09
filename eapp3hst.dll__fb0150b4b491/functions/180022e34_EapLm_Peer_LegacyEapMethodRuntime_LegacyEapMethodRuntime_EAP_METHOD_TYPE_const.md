# EapLm::Peer::LegacyEapMethodRuntime::LegacyEapMethodRuntime(_EAP_METHOD_TYPE const &)

- ea: `0x180022e34`
- end: `0x180022f3a`
- name: `??0LegacyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z`
- size: `262`
- prototype: `EapLm::Peer::LegacyEapMethodRuntime *__fastcall(EapLm::Peer::LegacyEapMethodRuntime *this, const struct _EAP_METHOD_TYPE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180021c20`

## callees

- `0x1800017a0`
- `0x18000d098`
- `0x18000eb94`
- `0x18002951c`

## string_xrefs

- `0x180022ef0`: `%windir%\system32\eapgenid.dll`

## pseudocode

```c
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
    (__int64)v7,
    (__int64)L"InvokePasswordDialog");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v6,
    (__int64)L"InvokeUsernameDialog");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v5,
    (__int64)L"Path");
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
    (__int64)this + 312,
    (__int64)L"%windir%\\system32\\eapgenid.dll");
  *(_OWORD *)((char *)this + 344) = 0;
  *(_OWORD *)((char *)this + 360) = 0;
  *((_QWORD *)this + 47) = 0;
  return this;
}

```

## disassembly

```asm
0x180022e34  mov     [rsp+arg_8], rbx
0x180022e39  push    rdi
0x180022e3a  sub     rsp, 0A0h
0x180022e41  mov     rax, cs:__security_cookie
0x180022e48  xor     rax, rsp
0x180022e4b  mov     [rsp+0A8h+var_10], rax
0x180022e53  mov     rbx, rdx
0x180022e56  mov     rdi, rcx
0x180022e59  mov     [rsp+0A8h+var_78], rcx
0x180022e5e  lea     rdx, aInvokepassword; "InvokePasswordDialog"
0x180022e65  lea     rcx, [rsp+0A8h+var_30]
0x180022e6a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180022e6f  nop
0x180022e70  lea     rdx, aInvokeusername; "InvokeUsernameDialog"
0x180022e77  lea     rcx, [rsp+0A8h+var_50]
0x180022e7c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180022e81  nop
0x180022e82  lea     rdx, aPath; "Path"
0x180022e89  lea     rcx, [rsp+0A8h+var_70]
0x180022e8e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180022e93  nop
0x180022e94  lea     rax, [rsp+0A8h+var_30]
0x180022e99  mov     [rsp+0A8h+var_88], rax
0x180022e9e  lea     r9, [rsp+0A8h+var_50]
0x180022ea3  lea     r8, [rsp+0A8h+var_70]
0x180022ea8  mov     rdx, rbx
0x180022eab  mov     rcx, rdi
0x180022eae  call    ??0BaseEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@11@Z; EapLm::Peer::BaseEapMethodRuntime::BaseEapMethodRuntime(_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x180022eb3  nop
0x180022eb4  lea     rcx, [rsp+0A8h+var_70]
0x180022eb9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180022ebe  nop
0x180022ebf  lea     rcx, [rsp+0A8h+var_50]
0x180022ec4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180022ec9  nop
0x180022eca  lea     rcx, [rsp+0A8h+var_30]
0x180022ecf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180022ed4  lea     rax, ??_7LegacyEapMethodRuntime@Peer@EapLm@@6B@; const EapLm::Peer::LegacyEapMethodRuntime::`vftable'
0x180022edb  mov     [rdi], rax
0x180022ede  mov     qword ptr [rdi+130h], 0
0x180022ee9  lea     rcx, [rdi+138h]
0x180022ef0  lea     rdx, aWindirSystem32; "%windir%\\system32\\eapgenid.dll"
0x180022ef7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180022efc  xorps   xmm0, xmm0
0x180022eff  xor     eax, eax
0x180022f01  movups  xmmword ptr [rdi+158h], xmm0
0x180022f08  movups  xmmword ptr [rdi+168h], xmm0
0x180022f0f  mov     [rdi+178h], rax
0x180022f16  mov     rax, rdi
0x180022f19  mov     rcx, [rsp+0A8h+var_10]
0x180022f21  xor     rcx, rsp; StackCookie
0x180022f24  call    __security_check_cookie
0x180022f29  mov     rbx, [rsp+0A8h+arg_8]
0x180022f31  add     rsp, 0A0h
0x180022f38  pop     rdi
0x180022f39  retn
```
