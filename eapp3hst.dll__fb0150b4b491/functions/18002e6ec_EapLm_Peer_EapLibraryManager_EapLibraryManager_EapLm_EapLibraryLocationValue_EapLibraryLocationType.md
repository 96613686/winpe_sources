# EapLm::Peer::EapLibraryManager::EapLibraryManager(EapLm::EapLibraryLocationValue::EapLibraryLocationType)

- ea: `0x18002e6ec`
- end: `0x18002e767`
- name: `??0EapLibraryManager@Peer@EapLm@@IEAA@W4EapLibraryLocationType@EapLibraryLocationValue@2@@Z`
- size: `123`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016c78`
- `0x180021d64`

## callees

- `0x1800017a0`
- `0x18000d098`
- `0x18000eb94`
- `0x18002b680`

## string_xrefs

- `0x18002e709`: `ConfigUIPath`

## pseudocode

```c
_QWORD *__fastcall EapLm::Peer::EapLibraryManager::EapLibraryManager(_QWORD *a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  _BYTE v5[32]; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v6[32]; // [rsp+48h] [rbp-30h] BYREF

  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v6,
    (__int64)L"ConfigUIPath");
  v2 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
         (__int64)v5,
         (__int64)L"PeerFriendlyName");
  EapLm::BaseEapLibraryManager::BaseEapLibraryManager((__int64)a1, v3, v2, (__int64)v6);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v6);
  *a1 = &EapLm::Peer::EapLibraryManager::`vftable';
  return a1;
}

```

## disassembly

```asm
0x18002e6ec  push    rbx
0x18002e6ee  sub     rsp, 70h
0x18002e6f2  mov     rax, cs:__security_cookie
0x18002e6f9  xor     rax, rsp
0x18002e6fc  mov     [rsp+78h+var_10], rax
0x18002e701  mov     rbx, rcx
0x18002e704  mov     [rsp+78h+var_58], rcx
0x18002e709  lea     rdx, aConfiguipath; "ConfigUIPath"
0x18002e710  lea     rcx, [rsp+78h+var_30]
0x18002e715  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18002e71a  nop
0x18002e71b  lea     rdx, aPeerfriendlyna; "PeerFriendlyName"
0x18002e722  lea     rcx, [rsp+78h+var_50]
0x18002e727  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18002e72c  lea     r9, [rsp+78h+var_30]
0x18002e731  mov     r8, rax
0x18002e734  mov     rcx, rbx
0x18002e737  call    ??0BaseEapLibraryManager@EapLm@@IEAA@W4EapLibraryLocationType@EapLibraryLocationValue@1@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEBV45@@Z; EapLm::BaseEapLibraryManager::BaseEapLibraryManager(EapLm::EapLibraryLocationValue::EapLibraryLocationType,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18002e73c  nop
0x18002e73d  lea     rcx, [rsp+78h+var_30]
0x18002e742  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002e747  lea     rax, ??_7EapLibraryManager@Peer@EapLm@@6B@; const EapLm::Peer::EapLibraryManager::`vftable'
0x18002e74e  mov     [rbx], rax
0x18002e751  mov     rax, rbx
0x18002e754  mov     rcx, [rsp+78h+var_10]
0x18002e759  xor     rcx, rsp; StackCookie
0x18002e75c  call    __security_check_cookie
0x18002e761  add     rsp, 70h
0x18002e765  pop     rbx
0x18002e766  retn
```
