# EapLm::Peer::ThirdPartyEapMethodRuntime::ThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE const &,IThirdPartyEapDispatcherPeerRuntime *)

- ea: `0x180017e7c`
- end: `0x180017f77`
- name: `??0ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@PEAUIThirdPartyEapDispatcherPeerRuntime@@@Z`
- size: `251`
- prototype: `__int64 __fastcall(EapLm::Peer::ThirdPartyEapMethodRuntime *__hidden this, const struct _EAP_METHOD_TYPE *, struct IThirdPartyEapDispatcherPeerRuntime *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18001177c`

## callees

- `0x180002af0`
- `0x180004af8`
- `0x18001206c`
- `0x180012a28`
- `0x18001978c`
- `0x1800300cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017f4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017f4e`

## string_xrefs

- `0x180017eca`: `PeerDllPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
  LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v7, (char *)this + 312);
  *((_QWORD *)this + 38) = a3;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 16));
  return this;
}

```

## disassembly

```asm
0x180017e7c  push    rbp
0x180017e7e  push    rbx
0x180017e7f  push    rsi
0x180017e80  push    rdi
0x180017e81  lea     rbp, [rsp-3Fh]
0x180017e86  sub     rsp, 0A8h
0x180017e8d  mov     rax, cs:__security_cookie
0x180017e94  xor     rax, rsp
0x180017e97  mov     [rbp+57h+var_28], rax
0x180017e9b  mov     rdi, r8
0x180017e9e  mov     rbx, rdx
0x180017ea1  mov     rsi, rcx
0x180017ea4  mov     [rbp+57h+var_90], rcx
0x180017ea8  lea     rdx, aPeerinvokepass; "PeerInvokePasswordDialog"
0x180017eaf  lea     rcx, [rbp+57h+var_48]
0x180017eb3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017eb8  nop
0x180017eb9  lea     rdx, aPeerinvokeuser; "PeerInvokeUsernameDialog"
0x180017ec0  lea     rcx, [rbp+57h+var_68]
0x180017ec4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017ec9  nop
0x180017eca  lea     rdx, aPeerdllpath; "PeerDllPath"
0x180017ed1  lea     rcx, [rbp+57h+var_88]
0x180017ed5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017eda  nop
0x180017edb  lea     rax, [rbp+57h+var_48]
0x180017edf  mov     [rsp+0C0h+var_A0], rax
0x180017ee4  lea     r9, [rbp+57h+var_68]
0x180017ee8  lea     r8, [rbp+57h+var_88]
0x180017eec  mov     rdx, rbx
0x180017eef  mov     rcx, rsi
0x180017ef2  call    ??0BaseEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@11@Z; EapLm::Peer::BaseEapMethodRuntime::BaseEapMethodRuntime(_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x180017ef7  nop
0x180017ef8  lea     rcx, [rbp+57h+var_88]
0x180017efc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017f01  nop
0x180017f02  lea     rcx, [rbp+57h+var_68]
0x180017f06  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017f0b  nop
0x180017f0c  lea     rcx, [rbp+57h+var_48]
0x180017f10  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017f15  lea     rax, ??_7ThirdPartyEapMethodRuntime@Peer@EapLm@@6B@; const EapLm::Peer::ThirdPartyEapMethodRuntime::`vftable'
0x180017f1c  mov     [rsi], rax
0x180017f1f  lea     rbx, [rsi+138h]
0x180017f26  mov     edx, 64h ; 'd'; unsigned int
0x180017f2b  mov     rcx, rbx; this
0x180017f2e  call    ??0CriticalSection@@QEAA@I@Z; CriticalSection::CriticalSection(uint)
0x180017f33  mov     rdx, rbx
0x180017f36  lea     rcx, [rbp+57h+var_90]
0x180017f3a  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x180017f3f  mov     [rsi+130h], rdi
0x180017f46  mov     rcx, [rbp+57h+var_90]
0x180017f4a  add     rcx, 10h; lpCriticalSection
0x180017f4e  call    cs:__imp_LeaveCriticalSection
0x180017f55  nop     dword ptr [rax+rax+00h]
0x180017f5a  nop
0x180017f5b  mov     rax, rsi
0x180017f5e  mov     rcx, [rbp+57h+var_28]
0x180017f62  xor     rcx, rsp; StackCookie
0x180017f65  call    __security_check_cookie
0x180017f6a  add     rsp, 0A8h
0x180017f71  pop     rdi
0x180017f72  pop     rsi
0x180017f73  pop     rbx
0x180017f74  pop     rbp
0x180017f75  retn
```
