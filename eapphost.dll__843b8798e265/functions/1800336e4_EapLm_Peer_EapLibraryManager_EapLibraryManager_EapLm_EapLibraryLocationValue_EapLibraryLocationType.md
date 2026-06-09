# EapLm::Peer::EapLibraryManager::EapLibraryManager(EapLm::EapLibraryLocationValue::EapLibraryLocationType)

- ea: `0x1800336e4`
- end: `0x180033760`
- name: `??0EapLibraryManager@Peer@EapLm@@IEAA@W4EapLibraryLocationType@EapLibraryLocationValue@2@@Z`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180011504`

## callees

- `0x180002af0`
- `0x18001206c`
- `0x180012a28`
- `0x18001a6ec`

## string_xrefs

- `0x180033701`: `ConfigUIPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall EapLm::Peer::EapLibraryManager::EapLibraryManager(_QWORD *a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  _BYTE v5[32]; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v6[32]; // [rsp+48h] [rbp-30h] BYREF

  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v6,
    L"ConfigUIPath");
  v2 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
         v5,
         L"PeerFriendlyName");
  EapLm::BaseEapLibraryManager::BaseEapLibraryManager(a1, v3, v2, v6);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v6);
  *a1 = &EapLm::Peer::EapLibraryManager::`vftable';
  return a1;
}

```

## disassembly

```asm
0x1800336e4  push    rbx
0x1800336e6  sub     rsp, 70h
0x1800336ea  mov     rax, cs:__security_cookie
0x1800336f1  xor     rax, rsp
0x1800336f4  mov     [rsp+78h+var_10], rax
0x1800336f9  mov     rbx, rcx
0x1800336fc  mov     [rsp+78h+var_58], rcx
0x180033701  lea     rdx, aConfiguipath; "ConfigUIPath"
0x180033708  lea     rcx, [rsp+78h+var_30]
0x18003370d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180033712  nop
0x180033713  lea     rdx, aPeerfriendlyna; "PeerFriendlyName"
0x18003371a  lea     rcx, [rsp+78h+var_50]
0x18003371f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180033724  lea     r9, [rsp+78h+var_30]
0x180033729  mov     r8, rax
0x18003372c  mov     rcx, rbx
0x18003372f  call    ??0BaseEapLibraryManager@EapLm@@IEAA@W4EapLibraryLocationType@EapLibraryLocationValue@1@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEBV45@@Z; EapLm::BaseEapLibraryManager::BaseEapLibraryManager(EapLm::EapLibraryLocationValue::EapLibraryLocationType,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x180033734  nop
0x180033735  lea     rcx, [rsp+78h+var_30]
0x18003373a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18003373f  lea     rax, ??_7EapLibraryManager@Peer@EapLm@@6B@; const EapLm::Peer::EapLibraryManager::`vftable'
0x180033746  mov     [rbx], rax
0x180033749  mov     rax, rbx
0x18003374c  mov     rcx, [rsp+78h+var_10]
0x180033751  xor     rcx, rsp; StackCookie
0x180033754  call    __security_check_cookie
0x180033759  add     rsp, 70h
0x18003375d  pop     rbx
0x18003375e  retn
```
