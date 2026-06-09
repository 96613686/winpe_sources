# EapLm::Peer::EapMethodRuntime::EapMethodRuntime(_EAP_METHOD_TYPE const &)

- ea: `0x180014e0c`
- end: `0x180014f04`
- name: `??0EapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z`
- size: `248`
- prototype: `__int64 __fastcall(EapLm::Peer::EapMethodRuntime *__hidden this, const struct _EAP_METHOD_TYPE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180010d10`

## callees

- `0x180002a90`
- `0x18000343c`
- `0x180010aa8`
- `0x180011908`
- `0x1800122a8`
- `0x180018dd8`

## string_xrefs

- `0x180014e5a`: `PeerDllPath`

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
0x180014e0c  mov     [rsp+arg_8], rbx
0x180014e11  push    rdi
0x180014e12  sub     rsp, 0A0h
0x180014e19  mov     rax, cs:__security_cookie
0x180014e20  xor     rax, rsp
0x180014e23  mov     [rsp+0A8h+var_10], rax
0x180014e2b  mov     rbx, rdx
0x180014e2e  mov     rdi, rcx
0x180014e31  mov     [rsp+0A8h+var_78], rcx
0x180014e36  lea     rdx, aPeerinvokepass; "PeerInvokePasswordDialog"
0x180014e3d  lea     rcx, [rsp+0A8h+var_30]
0x180014e42  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180014e47  nop
0x180014e48  lea     rdx, aPeerinvokeuser; "PeerInvokeUsernameDialog"
0x180014e4f  lea     rcx, [rsp+0A8h+var_50]
0x180014e54  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180014e59  nop
0x180014e5a  lea     rdx, aPeerdllpath; "PeerDllPath"
0x180014e61  lea     rcx, [rsp+0A8h+var_70]
0x180014e66  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180014e6b  nop
0x180014e6c  lea     rax, [rsp+0A8h+var_30]
0x180014e71  mov     [rsp+0A8h+var_88], rax
0x180014e76  lea     r9, [rsp+0A8h+var_50]
0x180014e7b  lea     r8, [rsp+0A8h+var_70]
0x180014e80  mov     rdx, rbx
0x180014e83  mov     rcx, rdi
0x180014e86  call    ??0BaseEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@11@Z; EapLm::Peer::BaseEapMethodRuntime::BaseEapMethodRuntime(_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x180014e8b  nop
0x180014e8c  lea     rcx, [rsp+0A8h+var_70]
0x180014e91  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180014e96  nop
0x180014e97  lea     rcx, [rsp+0A8h+var_50]
0x180014e9c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180014ea1  nop
0x180014ea2  lea     rcx, [rsp+0A8h+var_30]
0x180014ea7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180014eac  lea     rax, ??_7EapMethodRuntime@Peer@EapLm@@6B@; const EapLm::Peer::EapMethodRuntime::`vftable'
0x180014eb3  mov     [rdi], rax
0x180014eb6  lea     rcx, [rdi+1C0h]
0x180014ebd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x180014ec2  lea     rcx, [rdi+1E0h]
0x180014ec9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x180014ece  lea     rcx, [rdi+130h]; void *
0x180014ed5  xor     edx, edx; Val
0x180014ed7  lea     r8d, [rdx+78h]; Size
0x180014edb  call    memset_0
0x180014ee0  mov     rax, rdi
0x180014ee3  mov     rcx, [rsp+0A8h+var_10]
0x180014eeb  xor     rcx, rsp; StackCookie
0x180014eee  call    __security_check_cookie
0x180014ef3  mov     rbx, [rsp+0A8h+arg_8]
0x180014efb  add     rsp, 0A0h
0x180014f02  pop     rdi
0x180014f03  retn
```
