# EapLm::Peer::LegacyEapMethodRuntime::LegacyEapMethodRuntime(_EAP_METHOD_TYPE const &)

- ea: `0x1800123f0`
- end: `0x1800124f6`
- name: `??0LegacyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(EapLm::Peer::LegacyEapMethodRuntime *__hidden this, const struct _EAP_METHOD_TYPE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180010d10`

## callees

- `0x180002a90`
- `0x180011908`
- `0x1800122a8`
- `0x180018dd8`

## string_xrefs

- `0x1800124ac`: `%windir%\system32\eapgenid.dll`

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
0x1800123f0  mov     [rsp+arg_8], rbx
0x1800123f5  push    rdi
0x1800123f6  sub     rsp, 0A0h
0x1800123fd  mov     rax, cs:__security_cookie
0x180012404  xor     rax, rsp
0x180012407  mov     [rsp+0A8h+var_10], rax
0x18001240f  mov     rbx, rdx
0x180012412  mov     rdi, rcx
0x180012415  mov     [rsp+0A8h+var_78], rcx
0x18001241a  lea     rdx, aInvokepassword; "InvokePasswordDialog"
0x180012421  lea     rcx, [rsp+0A8h+var_30]
0x180012426  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001242b  nop
0x18001242c  lea     rdx, aInvokeusername; "InvokeUsernameDialog"
0x180012433  lea     rcx, [rsp+0A8h+var_50]
0x180012438  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001243d  nop
0x18001243e  lea     rdx, aPath; "Path"
0x180012445  lea     rcx, [rsp+0A8h+var_70]
0x18001244a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001244f  nop
0x180012450  lea     rax, [rsp+0A8h+var_30]
0x180012455  mov     [rsp+0A8h+var_88], rax
0x18001245a  lea     r9, [rsp+0A8h+var_50]
0x18001245f  lea     r8, [rsp+0A8h+var_70]
0x180012464  mov     rdx, rbx
0x180012467  mov     rcx, rdi
0x18001246a  call    ??0BaseEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@11@Z; EapLm::Peer::BaseEapMethodRuntime::BaseEapMethodRuntime(_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001246f  nop
0x180012470  lea     rcx, [rsp+0A8h+var_70]
0x180012475  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001247a  nop
0x18001247b  lea     rcx, [rsp+0A8h+var_50]
0x180012480  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180012485  nop
0x180012486  lea     rcx, [rsp+0A8h+var_30]
0x18001248b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180012490  lea     rax, ??_7LegacyEapMethodRuntime@Peer@EapLm@@6B@; const EapLm::Peer::LegacyEapMethodRuntime::`vftable'
0x180012497  mov     [rdi], rax
0x18001249a  mov     qword ptr [rdi+130h], 0
0x1800124a5  lea     rcx, [rdi+138h]
0x1800124ac  lea     rdx, aWindirSystem32; "%windir%\\system32\\eapgenid.dll"
0x1800124b3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800124b8  xorps   xmm0, xmm0
0x1800124bb  xor     eax, eax
0x1800124bd  movups  xmmword ptr [rdi+158h], xmm0
0x1800124c4  movups  xmmword ptr [rdi+168h], xmm0
0x1800124cb  mov     [rdi+178h], rax
0x1800124d2  mov     rax, rdi
0x1800124d5  mov     rcx, [rsp+0A8h+var_10]
0x1800124dd  xor     rcx, rsp; StackCookie
0x1800124e0  call    __security_check_cookie
0x1800124e5  mov     rbx, [rsp+0A8h+arg_8]
0x1800124ed  add     rsp, 0A0h
0x1800124f4  pop     rdi
0x1800124f5  retn
```
