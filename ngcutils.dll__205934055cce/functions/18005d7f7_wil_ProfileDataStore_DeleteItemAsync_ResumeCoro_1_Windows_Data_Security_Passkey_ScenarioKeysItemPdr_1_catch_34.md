# _wil::ProfileDataStore::DeleteItemAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$34

- ea: `0x18005d7f7`
- end: `0x18005d865`
- name: `_wil::ProfileDataStore::DeleteItemAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$34`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18005d7f7`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005d83c`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005d83c`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005d845`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005d845`

## pseudocode

```c
__int64 __fastcall wil::ProfileDataStore::DeleteItemAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch_34(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx

  v2 = *(_QWORD *)(a2 + 96);
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
0x18005d7f7  mov     [rsp+arg_8], rdx
0x18005d7fc  push    rbx
0x18005d7fd  push    rbp
0x18005d7fe  push    rdi
0x18005d7ff  sub     rsp, 40h
0x18005d803  mov     rbp, rdx
0x18005d806  or      eax, 0FFFFFFFFh
0x18005d809  mov     rdi, [rbp+60h]
0x18005d80d  mov     [rdi+8], ax
0x18005d811  mov     rax, cs:?g_pfnCaptureRestrictedErrorInformation@coro@details@wil@@3P6APEAXX_EEA
0x18005d818  test    rax, rax
0x18005d81b  jz      short loc_18005D826
0x18005d81d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d822  mov     [rdi-10h], rax
0x18005d826  lea     rbx, [rdi-48h]
0x18005d82a  mov     qword ptr [rbx], 0
0x18005d831  mov     qword ptr [rbx+8], 0
0x18005d839  mov     rcx, rbx
0x18005d83c  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18005d842  mov     rcx, rbx
0x18005d845  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18005d84b  mov     dword ptr [rdi-50h], 2
0x18005d852  mov     rax, 0
0x18005d85c  add     rsp, 40h
0x18005d860  pop     rdi
0x18005d861  pop     rbp
0x18005d862  pop     rbx
0x18005d863  retn
```
