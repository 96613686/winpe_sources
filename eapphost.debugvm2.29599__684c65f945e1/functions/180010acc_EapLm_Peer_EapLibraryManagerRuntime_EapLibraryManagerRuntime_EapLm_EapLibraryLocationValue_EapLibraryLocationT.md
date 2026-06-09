# EapLm::Peer::EapLibraryManagerRuntime::EapLibraryManagerRuntime(EapLm::EapLibraryLocationValue::EapLibraryLocationType)

- ea: `0x180010acc`
- end: `0x180010b85`
- name: `??0EapLibraryManagerRuntime@Peer@EapLm@@AEAA@W4EapLibraryLocationType@EapLibraryLocationValue@2@@Z`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180010e54`

## callees

- `0x180002a90`
- `0x180010c9c`
- `0x180011908`
- `0x1800122a8`
- `0x180019d08`
- `0x18002efc4`

## string_xrefs

- `0x180010aec`: `ConfigUIPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EapLm::Peer::EapLibraryManagerRuntime::EapLibraryManagerRuntime(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  _BYTE v6[32]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v7[32]; // [rsp+50h] [rbp-38h] BYREF

  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v7,
    L"ConfigUIPath");
  v2 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
         v6,
         L"PeerFriendlyName");
  EapLm::BaseEapLibraryManager::BaseEapLibraryManager(a1, v3, v2, v7, a1);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v7);
  *(_QWORD *)a1 = &EapLm::Peer::EapLibraryManagerRuntime::`vftable';
  `vector constructor iterator'(
    (void *)(a1 + 160),
    0x18u,
    0x21u,
    (void *(*)(void *))EapLm::Peer::EapThirdPartyProcess::EapThirdPartyProcess);
  CriticalSection::CriticalSection((CriticalSection *)(a1 + 960), 0x64u);
  *(_DWORD *)(a1 + 952) = 0;
  return a1;
}

```

## disassembly

```asm
0x180010acc  push    rbx
0x180010ace  sub     rsp, 80h
0x180010ad5  mov     rax, cs:__security_cookie
0x180010adc  xor     rax, rsp
0x180010adf  mov     [rsp+88h+var_18], rax
0x180010ae4  mov     rbx, rcx
0x180010ae7  mov     [rsp+88h+var_68], rcx
0x180010aec  lea     rdx, aConfiguipath; "ConfigUIPath"
0x180010af3  lea     rcx, [rsp+88h+var_38]
0x180010af8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180010afd  nop
0x180010afe  lea     rdx, aPeerfriendlyna; "PeerFriendlyName"
0x180010b05  lea     rcx, [rsp+88h+var_58]
0x180010b0a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180010b0f  lea     r9, [rsp+88h+var_38]
0x180010b14  mov     r8, rax
0x180010b17  mov     rcx, rbx
0x180010b1a  call    ??0BaseEapLibraryManager@EapLm@@IEAA@W4EapLibraryLocationType@EapLibraryLocationValue@1@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEBV45@@Z; EapLm::BaseEapLibraryManager::BaseEapLibraryManager(EapLm::EapLibraryLocationValue::EapLibraryLocationType,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x180010b1f  nop
0x180010b20  lea     rcx, [rsp+88h+var_38]
0x180010b25  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180010b2a  nop
0x180010b2b  lea     rax, ??_7EapLibraryManagerRuntime@Peer@EapLm@@6B@; const EapLm::Peer::EapLibraryManagerRuntime::`vftable'
0x180010b32  mov     [rbx], rax
0x180010b35  lea     rcx, [rbx+0A0h]; void *
0x180010b3c  lea     r9, ??0EapThirdPartyProcess@Peer@EapLm@@QEAA@XZ; void *(*)(void *)
0x180010b43  mov     edx, 18h; unsigned __int64
0x180010b48  lea     r8d, [rdx+9]; unsigned __int64
0x180010b4c  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180010b51  lea     rcx, [rbx+3C0h]; this
0x180010b58  mov     edx, 64h ; 'd'; unsigned int
0x180010b5d  call    ??0CriticalSection@@QEAA@I@Z; CriticalSection::CriticalSection(uint)
0x180010b62  mov     dword ptr [rbx+3B8h], 0
0x180010b6c  mov     rax, rbx
0x180010b6f  mov     rcx, [rsp+88h+var_18]
0x180010b74  xor     rcx, rsp; StackCookie
0x180010b77  call    __security_check_cookie
0x180010b7c  add     rsp, 80h
0x180010b83  pop     rbx
0x180010b84  retn
```
