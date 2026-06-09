# _wil::ProfileDataStore::SaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$33

- ea: `0x18005e76b`
- end: `0x18005e7d9`
- name: `_wil::ProfileDataStore::SaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$33`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18005e76b`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005e7b0`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005e7b0`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005e7b9`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005e7b9`

## pseudocode

```c
__int64 __fastcall wil::ProfileDataStore::SaveAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch_33(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx

  v2 = *(_QWORD *)(a2 + 120);
  *(_WORD *)(v2 + 8) = -1;
  if ( wil::details::coro::g_pfnCaptureRestrictedErrorInformation )
    *(_QWORD *)(v2 - 16) = wil::details::coro::g_pfnCaptureRestrictedErrorInformation();
  v3 = (_QWORD *)(v2 - 72);
  *v3 = 0;
  v3[1] = 0;
  __ExceptionPtrCreate((void *)(v2 - 72));
  __ExceptionPtrCurrentException((void *)(v2 - 72));
  *(_DWORD *)(v2 - 80) = 2;
  return 0;
}

```

## disassembly

```asm
0x18005e76b  mov     [rsp+arg_8], rdx
0x18005e770  push    rbx
0x18005e771  push    rbp
0x18005e772  push    rdi
0x18005e773  sub     rsp, 50h
0x18005e777  mov     rbp, rdx
0x18005e77a  or      eax, 0FFFFFFFFh
0x18005e77d  mov     rdi, [rbp+78h]
0x18005e781  mov     [rdi+8], ax
0x18005e785  mov     rax, cs:?g_pfnCaptureRestrictedErrorInformation@coro@details@wil@@3P6APEAXX_EEA
0x18005e78c  test    rax, rax
0x18005e78f  jz      short loc_18005E79A
0x18005e791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e796  mov     [rdi-10h], rax
0x18005e79a  lea     rbx, [rdi-48h]
0x18005e79e  mov     qword ptr [rbx], 0
0x18005e7a5  mov     qword ptr [rbx+8], 0
0x18005e7ad  mov     rcx, rbx
0x18005e7b0  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18005e7b6  mov     rcx, rbx
0x18005e7b9  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18005e7bf  mov     dword ptr [rdi-50h], 2
0x18005e7c6  mov     rax, 0
0x18005e7d0  add     rsp, 50h
0x18005e7d4  pop     rdi
0x18005e7d5  pop     rbp
0x18005e7d6  pop     rbx
0x18005e7d7  retn
```
