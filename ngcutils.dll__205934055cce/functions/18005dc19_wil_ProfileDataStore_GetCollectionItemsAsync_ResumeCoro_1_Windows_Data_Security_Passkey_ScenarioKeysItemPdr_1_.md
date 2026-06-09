# _wil::ProfileDataStore::GetCollectionItemsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$37

- ea: `0x18005dc19`
- end: `0x18005dc87`
- name: `_wil::ProfileDataStore::GetCollectionItemsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$37`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18005dc19`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005dc5e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005dc5e`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005dc67`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005dc67`

## pseudocode

```c
__int64 __fastcall wil::ProfileDataStore::GetCollectionItemsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch_37(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx

  v2 = *(_QWORD *)(a2 + 80);
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
0x18005dc19  mov     [rsp+arg_8], rdx
0x18005dc1e  push    rbx
0x18005dc1f  push    rbp
0x18005dc20  push    rdi
0x18005dc21  sub     rsp, 40h
0x18005dc25  mov     rbp, rdx
0x18005dc28  or      eax, 0FFFFFFFFh
0x18005dc2b  mov     rdi, [rbp+50h]
0x18005dc2f  mov     [rdi+8], ax
0x18005dc33  mov     rax, cs:?g_pfnCaptureRestrictedErrorInformation@coro@details@wil@@3P6APEAXX_EEA
0x18005dc3a  test    rax, rax
0x18005dc3d  jz      short loc_18005DC48
0x18005dc3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dc44  mov     [rdi-10h], rax
0x18005dc48  lea     rbx, [rdi-58h]
0x18005dc4c  mov     qword ptr [rbx], 0
0x18005dc53  mov     qword ptr [rbx+8], 0
0x18005dc5b  mov     rcx, rbx
0x18005dc5e  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18005dc64  mov     rcx, rbx
0x18005dc67  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18005dc6d  mov     dword ptr [rdi-60h], 2
0x18005dc74  mov     rax, 0
0x18005dc7e  add     rsp, 40h
0x18005dc82  pop     rdi
0x18005dc83  pop     rbp
0x18005dc84  pop     rbx
0x18005dc85  retn
```
