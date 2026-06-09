# EapLm::Peer::ThirdPartyEapMethodRuntime::ThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE const &,IThirdPartyEapDispatcherPeerRuntime *)

- ea: `0x180027d9c`
- end: `0x180027e90`
- name: `??0ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@PEAUIThirdPartyEapDispatcherPeerRuntime@@@Z`
- size: `244`
- prototype: `EapLm::Peer::ThirdPartyEapMethodRuntime *__fastcall(EapLm::Peer::ThirdPartyEapMethodRuntime *this, const struct _EAP_METHOD_TYPE *, struct IThirdPartyEapDispatcherPeerRuntime *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180021fc4`

## callees

- `0x1800017a0`
- `0x18000d098`
- `0x18000eb94`
- `0x180012050`
- `0x180012d18`
- `0x18002951c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027e6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027e6e`

## string_xrefs

- `0x180027dea`: `PeerDllPath`

## pseudocode

```c
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
    (__int64)v10,
    (__int64)L"PeerInvokePasswordDialog");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v9,
    (__int64)L"PeerInvokeUsernameDialog");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v8,
    (__int64)L"PeerDllPath");
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
0x180027d9c  push    rbp
0x180027d9e  push    rbx
0x180027d9f  push    rsi
0x180027da0  push    rdi
0x180027da1  lea     rbp, [rsp-3Fh]
0x180027da6  sub     rsp, 0A8h
0x180027dad  mov     rax, cs:__security_cookie
0x180027db4  xor     rax, rsp
0x180027db7  mov     [rbp+57h+var_28], rax
0x180027dbb  mov     rdi, r8
0x180027dbe  mov     rbx, rdx
0x180027dc1  mov     rsi, rcx
0x180027dc4  mov     [rbp+57h+var_90], rcx
0x180027dc8  lea     rdx, aPeerinvokepass; "PeerInvokePasswordDialog"
0x180027dcf  lea     rcx, [rbp+57h+var_48]
0x180027dd3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180027dd8  nop
0x180027dd9  lea     rdx, aPeerinvokeuser; "PeerInvokeUsernameDialog"
0x180027de0  lea     rcx, [rbp+57h+var_68]
0x180027de4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180027de9  nop
0x180027dea  lea     rdx, aPeerdllpath; "PeerDllPath"
0x180027df1  lea     rcx, [rbp+57h+var_88]
0x180027df5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180027dfa  nop
0x180027dfb  lea     rax, [rbp+57h+var_48]
0x180027dff  mov     [rsp+0C0h+var_A0], rax
0x180027e04  lea     r9, [rbp+57h+var_68]
0x180027e08  lea     r8, [rbp+57h+var_88]
0x180027e0c  mov     rdx, rbx
0x180027e0f  mov     rcx, rsi
0x180027e12  call    ??0BaseEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@11@Z; EapLm::Peer::BaseEapMethodRuntime::BaseEapMethodRuntime(_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x180027e17  nop
0x180027e18  lea     rcx, [rbp+57h+var_88]
0x180027e1c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180027e21  nop
0x180027e22  lea     rcx, [rbp+57h+var_68]
0x180027e26  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180027e2b  nop
0x180027e2c  lea     rcx, [rbp+57h+var_48]
0x180027e30  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180027e35  lea     rax, ??_7ThirdPartyEapMethodRuntime@Peer@EapLm@@6B@; const EapLm::Peer::ThirdPartyEapMethodRuntime::`vftable'
0x180027e3c  mov     [rsi], rax
0x180027e3f  lea     rbx, [rsi+138h]
0x180027e46  mov     edx, 64h ; 'd'; unsigned int
0x180027e4b  mov     rcx, rbx; this
0x180027e4e  call    ??0CriticalSection@@QEAA@I@Z; CriticalSection::CriticalSection(uint)
0x180027e53  mov     rdx, rbx
0x180027e56  lea     rcx, [rbp+57h+var_90]
0x180027e5a  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x180027e5f  mov     [rsi+130h], rdi
0x180027e66  mov     rcx, [rbp+57h+var_90]
0x180027e6a  add     rcx, 10h; lpCriticalSection
0x180027e6e  call    cs:__imp_LeaveCriticalSection
0x180027e74  nop
0x180027e75  mov     rax, rsi
0x180027e78  mov     rcx, [rbp+57h+var_28]
0x180027e7c  xor     rcx, rsp; StackCookie
0x180027e7f  call    __security_check_cookie
0x180027e84  add     rsp, 0A8h
0x180027e8b  pop     rdi
0x180027e8c  pop     rsi
0x180027e8d  pop     rbx
0x180027e8e  pop     rbp
0x180027e8f  retn
```
