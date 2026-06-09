# _wil::ProfileDataStore::BatchSaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$23

- ea: `0x18005a3fe`
- end: `0x18005a46f`
- name: `_wil::ProfileDataStore::BatchSaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$23`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18005a3fe`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005a446`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005a446`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005a44f`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005a44f`

## pseudocode

```c
__int64 __fastcall wil::ProfileDataStore::BatchSaveAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch_23(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx

  v2 = *(_QWORD *)(a2 + 224);
  *(_WORD *)(v2 + 8) = -1;
  if ( wil::details::coro::g_pfnCaptureRestrictedErrorInformation )
    *(_QWORD *)(v2 - 16) = wil::details::coro::g_pfnCaptureRestrictedErrorInformation();
  v3 = (_QWORD *)(v2 - 40);
  *v3 = 0;
  v3[1] = 0;
  __ExceptionPtrCreate((void *)(v2 - 40));
  __ExceptionPtrCurrentException((void *)(v2 - 40));
  *(_DWORD *)(v2 - 48) = 2;
  return 0;
}

```

## disassembly

```asm
0x18005a3fe  mov     [rsp+arg_8], rdx
0x18005a403  push    rbx
0x18005a404  push    rbp
0x18005a405  push    rdi
0x18005a406  sub     rsp, 30h
0x18005a40a  mov     rbp, rdx
0x18005a40d  or      eax, 0FFFFFFFFh
0x18005a410  mov     rdi, [rbp+0E0h]
0x18005a417  mov     [rdi+8], ax
0x18005a41b  mov     rax, cs:?g_pfnCaptureRestrictedErrorInformation@coro@details@wil@@3P6APEAXX_EEA
0x18005a422  test    rax, rax
0x18005a425  jz      short loc_18005A430
0x18005a427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a42c  mov     [rdi-10h], rax
0x18005a430  lea     rbx, [rdi-28h]
0x18005a434  mov     qword ptr [rbx], 0
0x18005a43b  mov     qword ptr [rbx+8], 0
0x18005a443  mov     rcx, rbx
0x18005a446  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18005a44c  mov     rcx, rbx
0x18005a44f  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18005a455  mov     dword ptr [rdi-30h], 2
0x18005a45c  mov     rax, 0
0x18005a466  add     rsp, 30h
0x18005a46a  pop     rdi
0x18005a46b  pop     rbp
0x18005a46c  pop     rbx
0x18005a46d  retn
```
