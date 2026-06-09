# EapLm::Peer::EapMethodRuntime::EapMethodRuntime(_EAP_METHOD_TYPE const &)

- ea: `0x180015648`
- end: `0x180015741`
- name: `??0EapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(EapLm::Peer::EapMethodRuntime *__hidden this, const struct _EAP_METHOD_TYPE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800113c0`

## callees

- `0x180002af0`
- `0x1800034cc`
- `0x180011218`
- `0x18001206c`
- `0x180012a28`
- `0x18001978c`

## string_xrefs

- `0x180015696`: `PeerDllPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
EapLm::Peer::EapMethodRuntime *__fastcall EapLm::Peer::EapMethodRuntime::EapMethodRuntime(
        EapLm::Peer::EapMethodRuntime *this,
        const struct _EAP_METHOD_TYPE *a2)
{
  int v2; // ebx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  _BYTE v11[32]; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v12[32]; // [rsp+58h] [rbp-50h] BYREF
  _BYTE v13[32]; // [rsp+78h] [rbp-30h] BYREF

  v2 = (int)a2;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v13,
    L"PeerInvokePasswordDialog");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v12,
    L"PeerInvokeUsernameDialog");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v11,
    L"PeerDllPath");
  EapLm::Peer::BaseEapMethodRuntime::BaseEapMethodRuntime(
    (_DWORD)this,
    v2,
    (unsigned int)v11,
    (unsigned int)v12,
    (__int64)v13);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v11);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v12);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v13);
  *(_QWORD *)this = &EapLm::Peer::EapMethodRuntime::`vftable';
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (char *)this + 448,
    v4,
    v5,
    v6);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (char *)this + 480,
    v7,
    v8,
    v9);
  memset_0((char *)this + 304, 0, 0x78u);
  return this;
}

```

## disassembly

```asm
0x180015648  mov     [rsp+arg_8], rbx
0x18001564d  push    rdi
0x18001564e  sub     rsp, 0A0h
0x180015655  mov     rax, cs:__security_cookie
0x18001565c  xor     rax, rsp
0x18001565f  mov     [rsp+0A8h+var_10], rax
0x180015667  mov     rbx, rdx
0x18001566a  mov     rdi, rcx
0x18001566d  mov     [rsp+0A8h+var_78], rcx
0x180015672  lea     rdx, aPeerinvokepass; "PeerInvokePasswordDialog"
0x180015679  lea     rcx, [rsp+0A8h+var_30]
0x18001567e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180015683  nop
0x180015684  lea     rdx, aPeerinvokeuser; "PeerInvokeUsernameDialog"
0x18001568b  lea     rcx, [rsp+0A8h+var_50]
0x180015690  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180015695  nop
0x180015696  lea     rdx, aPeerdllpath; "PeerDllPath"
0x18001569d  lea     rcx, [rsp+0A8h+var_70]
0x1800156a2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800156a7  nop
0x1800156a8  lea     rax, [rsp+0A8h+var_30]
0x1800156ad  mov     [rsp+0A8h+var_88], rax
0x1800156b2  lea     r9, [rsp+0A8h+var_50]
0x1800156b7  lea     r8, [rsp+0A8h+var_70]
0x1800156bc  mov     rdx, rbx
0x1800156bf  mov     rcx, rdi
0x1800156c2  call    ??0BaseEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@11@Z; EapLm::Peer::BaseEapMethodRuntime::BaseEapMethodRuntime(_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x1800156c7  nop
0x1800156c8  lea     rcx, [rsp+0A8h+var_70]
0x1800156cd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x1800156d2  nop
0x1800156d3  lea     rcx, [rsp+0A8h+var_50]
0x1800156d8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x1800156dd  nop
0x1800156de  lea     rcx, [rsp+0A8h+var_30]
0x1800156e3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x1800156e8  lea     rax, ??_7EapMethodRuntime@Peer@EapLm@@6B@; const EapLm::Peer::EapMethodRuntime::`vftable'
0x1800156ef  mov     [rdi], rax
0x1800156f2  lea     rcx, [rdi+1C0h]
0x1800156f9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x1800156fe  lea     rcx, [rdi+1E0h]
0x180015705  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18001570a  lea     rcx, [rdi+130h]; void *
0x180015711  xor     edx, edx; Val
0x180015713  lea     r8d, [rdx+78h]; Size
0x180015717  call    memset_0
0x18001571c  mov     rax, rdi
0x18001571f  mov     rcx, [rsp+0A8h+var_10]
0x180015727  xor     rcx, rsp; StackCookie
0x18001572a  call    __security_check_cookie
0x18001572f  mov     rbx, [rsp+0A8h+arg_8]
0x180015737  add     rsp, 0A0h
0x18001573e  pop     rdi
0x18001573f  retn
```
