# _wil::ProfileDataStore::CallGetCollectionItemsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$108

- ea: `0x18005baf2`
- end: `0x18005bb60`
- name: `_wil::ProfileDataStore::CallGetCollectionItemsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$108`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18005baf2`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005bb37`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005bb37`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005bb40`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005bb40`

## pseudocode

```c
__int64 __fastcall wil::ProfileDataStore::CallGetCollectionItemsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch_108(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx

  v2 = *(_QWORD *)(a2 + 88);
  *(_WORD *)(v2 + 8) = -1;
  if ( wil::details::coro::g_pfnCaptureRestrictedErrorInformation )
    *(_QWORD *)(v2 - 16) = wil::details::coro::g_pfnCaptureRestrictedErrorInformation();
  v3 = (_QWORD *)(v2 - 88);
  *v3 = 0;
  v3[1] = 0;
  __ExceptionPtrCreate((void *)(v2 - 88));
  __ExceptionPtrCurrentException((void *)(v2 - 88));
  *(_DWORD *)(v2 - 96) = 2;
  return 0;
}

```

## disassembly

```asm
0x18005baf2  mov     [rsp+arg_8], rdx
0x18005baf7  push    rbx
0x18005baf8  push    rbp
0x18005baf9  push    rdi
0x18005bafa  sub     rsp, 50h
0x18005bafe  mov     rbp, rdx
0x18005bb01  or      eax, 0FFFFFFFFh
0x18005bb04  mov     rdi, [rbp+58h]
0x18005bb08  mov     [rdi+8], ax
0x18005bb0c  mov     rax, cs:?g_pfnCaptureRestrictedErrorInformation@coro@details@wil@@3P6APEAXX_EEA
0x18005bb13  test    rax, rax
0x18005bb16  jz      short loc_18005BB21
0x18005bb18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb1d  mov     [rdi-10h], rax
0x18005bb21  lea     rbx, [rdi-58h]
0x18005bb25  mov     qword ptr [rbx], 0
0x18005bb2c  mov     qword ptr [rbx+8], 0
0x18005bb34  mov     rcx, rbx
0x18005bb37  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18005bb3d  mov     rcx, rbx
0x18005bb40  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18005bb46  mov     dword ptr [rdi-60h], 2
0x18005bb4d  mov     rax, 0
0x18005bb57  add     rsp, 50h
0x18005bb5b  pop     rdi
0x18005bb5c  pop     rbp
0x18005bb5d  pop     rbx
0x18005bb5e  retn
```
