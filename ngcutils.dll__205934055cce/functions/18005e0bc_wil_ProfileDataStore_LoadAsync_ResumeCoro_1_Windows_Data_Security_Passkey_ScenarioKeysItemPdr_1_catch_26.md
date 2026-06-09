# _wil::ProfileDataStore::LoadAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$26

- ea: `0x18005e0bc`
- end: `0x18005e12d`
- name: `_wil::ProfileDataStore::LoadAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$26`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18005e0bc`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005e104`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005e104`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005e10d`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005e10d`

## pseudocode

```c
__int64 __fastcall wil::ProfileDataStore::LoadAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch_26(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx

  v2 = *(_QWORD *)(a2 + 288);
  *(_WORD *)(v2 + 8) = -1;
  if ( wil::details::coro::g_pfnCaptureRestrictedErrorInformation )
    *(_QWORD *)(v2 - 8) = wil::details::coro::g_pfnCaptureRestrictedErrorInformation();
  v3 = (_QWORD *)(v2 - 24);
  *v3 = 0;
  v3[1] = 0;
  __ExceptionPtrCreate((void *)(v2 - 24));
  __ExceptionPtrCurrentException((void *)(v2 - 24));
  *(_DWORD *)(v2 - 32) = 2;
  return 0;
}

```

## disassembly

```asm
0x18005e0bc  mov     [rsp+arg_8], rdx
0x18005e0c1  push    rbx
0x18005e0c2  push    rbp
0x18005e0c3  push    rdi
0x18005e0c4  sub     rsp, 40h
0x18005e0c8  mov     rbp, rdx
0x18005e0cb  or      eax, 0FFFFFFFFh
0x18005e0ce  mov     rdi, [rbp+120h]
0x18005e0d5  mov     [rdi+8], ax
0x18005e0d9  mov     rax, cs:?g_pfnCaptureRestrictedErrorInformation@coro@details@wil@@3P6APEAXX_EEA
0x18005e0e0  test    rax, rax
0x18005e0e3  jz      short loc_18005E0EE
0x18005e0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e0ea  mov     [rdi-8], rax
0x18005e0ee  lea     rbx, [rdi-18h]
0x18005e0f2  mov     qword ptr [rbx], 0
0x18005e0f9  mov     qword ptr [rbx+8], 0
0x18005e101  mov     rcx, rbx
0x18005e104  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18005e10a  mov     rcx, rbx
0x18005e10d  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18005e113  mov     dword ptr [rdi-20h], 2
0x18005e11a  mov     rax, 0
0x18005e124  add     rsp, 40h
0x18005e128  pop     rdi
0x18005e129  pop     rbp
0x18005e12a  pop     rbx
0x18005e12b  retn
```
