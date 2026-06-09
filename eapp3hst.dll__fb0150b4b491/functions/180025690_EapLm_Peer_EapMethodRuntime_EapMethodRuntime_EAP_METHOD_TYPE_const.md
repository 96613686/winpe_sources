# EapLm::Peer::EapMethodRuntime::EapMethodRuntime(_EAP_METHOD_TYPE const &)

- ea: `0x180025690`
- end: `0x180025788`
- name: `??0EapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z`
- size: `248`
- prototype: `EapLm::Peer::EapMethodRuntime *__fastcall(EapLm::Peer::EapMethodRuntime *this, const struct _EAP_METHOD_TYPE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180021c20`

## callees

- `0x1800017a0`
- `0x18000213c`
- `0x18000d098`
- `0x18000eb94`
- `0x180016c54`
- `0x18002951c`

## string_xrefs

- `0x1800256de`: `PeerDllPath`

## pseudocode

```c
EapLm::Peer::EapMethodRuntime *__fastcall EapLm::Peer::EapMethodRuntime::EapMethodRuntime(
        EapLm::Peer::EapMethodRuntime *this,
        const struct _EAP_METHOD_TYPE *a2)
{
  int v2; // ebx
  _BYTE v5[32]; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v6[32]; // [rsp+58h] [rbp-50h] BYREF
  _BYTE v7[32]; // [rsp+78h] [rbp-30h] BYREF

  v2 = (int)a2;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v7,
    (__int64)L"PeerInvokePasswordDialog");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v6,
    (__int64)L"PeerInvokeUsernameDialog");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v5,
    (__int64)L"PeerDllPath");
  EapLm::Peer::BaseEapMethodRuntime::BaseEapMethodRuntime(
    (_DWORD)this,
    v2,
    (unsigned int)v5,
    (unsigned int)v6,
    (__int64)v7);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v5);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v6);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v7);
  *(_QWORD *)this = &EapLm::Peer::EapMethodRuntime::`vftable';
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>((char *)this + 448);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>((char *)this + 480);
  memset_0((char *)this + 304, 0, 0x78u);
  return this;
}

```

## disassembly

```asm
0x180025690  mov     [rsp+arg_8], rbx
0x180025695  push    rdi
0x180025696  sub     rsp, 0A0h
0x18002569d  mov     rax, cs:__security_cookie
0x1800256a4  xor     rax, rsp
0x1800256a7  mov     [rsp+0A8h+var_10], rax
0x1800256af  mov     rbx, rdx
0x1800256b2  mov     rdi, rcx
0x1800256b5  mov     [rsp+0A8h+var_78], rcx
0x1800256ba  lea     rdx, aPeerinvokepass; "PeerInvokePasswordDialog"
0x1800256c1  lea     rcx, [rsp+0A8h+var_30]
0x1800256c6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800256cb  nop
0x1800256cc  lea     rdx, aPeerinvokeuser; "PeerInvokeUsernameDialog"
0x1800256d3  lea     rcx, [rsp+0A8h+var_50]
0x1800256d8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800256dd  nop
0x1800256de  lea     rdx, aPeerdllpath; "PeerDllPath"
0x1800256e5  lea     rcx, [rsp+0A8h+var_70]
0x1800256ea  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800256ef  nop
0x1800256f0  lea     rax, [rsp+0A8h+var_30]
0x1800256f5  mov     [rsp+0A8h+var_88], rax
0x1800256fa  lea     r9, [rsp+0A8h+var_50]
0x1800256ff  lea     r8, [rsp+0A8h+var_70]
0x180025704  mov     rdx, rbx
0x180025707  mov     rcx, rdi
0x18002570a  call    ??0BaseEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@11@Z; EapLm::Peer::BaseEapMethodRuntime::BaseEapMethodRuntime(_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18002570f  nop
0x180025710  lea     rcx, [rsp+0A8h+var_70]
0x180025715  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002571a  nop
0x18002571b  lea     rcx, [rsp+0A8h+var_50]
0x180025720  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180025725  nop
0x180025726  lea     rcx, [rsp+0A8h+var_30]
0x18002572b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180025730  lea     rax, ??_7EapMethodRuntime@Peer@EapLm@@6B@; const EapLm::Peer::EapMethodRuntime::`vftable'
0x180025737  mov     [rdi], rax
0x18002573a  lea     rcx, [rdi+1C0h]
0x180025741  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x180025746  lea     rcx, [rdi+1E0h]
0x18002574d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x180025752  lea     rcx, [rdi+130h]; void *
0x180025759  xor     edx, edx; Val
0x18002575b  lea     r8d, [rdx+78h]; Size
0x18002575f  call    memset_0
0x180025764  mov     rax, rdi
0x180025767  mov     rcx, [rsp+0A8h+var_10]
0x18002576f  xor     rcx, rsp; StackCookie
0x180025772  call    __security_check_cookie
0x180025777  mov     rbx, [rsp+0A8h+arg_8]
0x18002577f  add     rsp, 0A0h
0x180025786  pop     rdi
0x180025787  retn
```
