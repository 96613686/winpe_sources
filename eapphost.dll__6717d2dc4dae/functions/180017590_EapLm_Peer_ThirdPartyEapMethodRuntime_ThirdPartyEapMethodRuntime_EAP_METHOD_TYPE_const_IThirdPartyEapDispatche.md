# EapLm::Peer::ThirdPartyEapMethodRuntime::ThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE const &,IThirdPartyEapDispatcherPeerRuntime *)

- ea: `0x180017590`
- end: `0x180017684`
- name: `??0ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@PEAUIThirdPartyEapDispatcherPeerRuntime@@@Z`
- size: `244`
- prototype: `EapLm::Peer::ThirdPartyEapMethodRuntime *__fastcall(EapLm::Peer::ThirdPartyEapMethodRuntime *this, const struct _EAP_METHOD_TYPE *, struct IThirdPartyEapDispatcherPeerRuntime *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180011064`

## callees

- `0x180002a90`
- `0x180004988`
- `0x180011908`
- `0x1800122a8`
- `0x180018dd8`
- `0x18002efc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017662`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017662`

## string_xrefs

- `0x1800175de`: `PeerDllPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
EapLm::Peer::ThirdPartyEapMethodRuntime *__fastcall EapLm::Peer::ThirdPartyEapMethodRuntime::ThirdPartyEapMethodRuntime(
        EapLm::Peer::ThirdPartyEapMethodRuntime *this,
        const struct _EAP_METHOD_TYPE *a2,
        struct IThirdPartyEapDispatcherPeerRuntime *a3)
{
  int v4; // ebx
  EapLm::Peer::ThirdPartyEapMethodRuntime *v7; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v9[32]; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v10[32]; // [rsp+78h] [rbp+Fh] BYREF

  v4 = (int)a2;
  v7 = this;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v10,
    L"PeerInvokePasswordDialog");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v9,
    L"PeerInvokeUsernameDialog");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v8,
    L"PeerDllPath");
  EapLm::Peer::BaseEapMethodRuntime::BaseEapMethodRuntime(
    (_DWORD)this,
    v4,
    (unsigned int)v8,
    (unsigned int)v9,
    (__int64)v10);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v8);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v9);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v10);
  *(_QWORD *)this = &EapLm::Peer::ThirdPartyEapMethodRuntime::`vftable';
  CriticalSection::CriticalSection((EapLm::Peer::ThirdPartyEapMethodRuntime *)((char *)this + 312), 0x64u);
  LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v7, (__int64)this + 312);
  *((_QWORD *)this + 38) = a3;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 16));
  return this;
}

```

## disassembly

```asm
0x180017590  push    rbp
0x180017592  push    rbx
0x180017593  push    rsi
0x180017594  push    rdi
0x180017595  lea     rbp, [rsp-3Fh]
0x18001759a  sub     rsp, 0A8h
0x1800175a1  mov     rax, cs:__security_cookie
0x1800175a8  xor     rax, rsp
0x1800175ab  mov     [rbp+57h+var_28], rax
0x1800175af  mov     rdi, r8
0x1800175b2  mov     rbx, rdx
0x1800175b5  mov     rsi, rcx
0x1800175b8  mov     [rbp+57h+var_90], rcx
0x1800175bc  lea     rdx, aPeerinvokepass; "PeerInvokePasswordDialog"
0x1800175c3  lea     rcx, [rbp+57h+var_48]
0x1800175c7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800175cc  nop
0x1800175cd  lea     rdx, aPeerinvokeuser; "PeerInvokeUsernameDialog"
0x1800175d4  lea     rcx, [rbp+57h+var_68]
0x1800175d8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800175dd  nop
0x1800175de  lea     rdx, aPeerdllpath; "PeerDllPath"
0x1800175e5  lea     rcx, [rbp+57h+var_88]
0x1800175e9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800175ee  nop
0x1800175ef  lea     rax, [rbp+57h+var_48]
0x1800175f3  mov     [rsp+0C0h+var_A0], rax
0x1800175f8  lea     r9, [rbp+57h+var_68]
0x1800175fc  lea     r8, [rbp+57h+var_88]
0x180017600  mov     rdx, rbx
0x180017603  mov     rcx, rsi
0x180017606  call    ??0BaseEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@11@Z; EapLm::Peer::BaseEapMethodRuntime::BaseEapMethodRuntime(_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001760b  nop
0x18001760c  lea     rcx, [rbp+57h+var_88]
0x180017610  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017615  nop
0x180017616  lea     rcx, [rbp+57h+var_68]
0x18001761a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001761f  nop
0x180017620  lea     rcx, [rbp+57h+var_48]
0x180017624  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017629  lea     rax, ??_7ThirdPartyEapMethodRuntime@Peer@EapLm@@6B@; const EapLm::Peer::ThirdPartyEapMethodRuntime::`vftable'
0x180017630  mov     [rsi], rax
0x180017633  lea     rbx, [rsi+138h]
0x18001763a  mov     edx, 64h ; 'd'; unsigned int
0x18001763f  mov     rcx, rbx; this
0x180017642  call    ??0CriticalSection@@QEAA@I@Z; CriticalSection::CriticalSection(uint)
0x180017647  mov     rdx, rbx
0x18001764a  lea     rcx, [rbp+57h+var_90]
0x18001764e  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x180017653  mov     [rsi+130h], rdi
0x18001765a  mov     rcx, [rbp+57h+var_90]
0x18001765e  add     rcx, 10h; lpCriticalSection
0x180017662  call    cs:__imp_LeaveCriticalSection
0x180017668  nop
0x180017669  mov     rax, rsi
0x18001766c  mov     rcx, [rbp+57h+var_28]
0x180017670  xor     rcx, rsp; StackCookie
0x180017673  call    __security_check_cookie
0x180017678  add     rsp, 0A8h
0x18001767f  pop     rdi
0x180017680  pop     rsi
0x180017681  pop     rbx
0x180017682  pop     rbp
0x180017683  retn
```
