# _wil::ProfileDataStore::CallDeleteItemAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$72

- ea: `0x18005b5e2`
- end: `0x18005b650`
- name: `_wil::ProfileDataStore::CallDeleteItemAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$72`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18005b5e2`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005b627`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005b627`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005b630`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005b630`

## pseudocode

```c
__int64 __fastcall wil::ProfileDataStore::CallDeleteItemAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch_72(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx

  v2 = *(_QWORD *)(a2 + 104);
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
0x18005b5e2  mov     [rsp+arg_8], rdx
0x18005b5e7  push    rbx
0x18005b5e8  push    rbp
0x18005b5e9  push    rdi
0x18005b5ea  sub     rsp, 60h
0x18005b5ee  mov     rbp, rdx
0x18005b5f1  or      eax, 0FFFFFFFFh
0x18005b5f4  mov     rdi, [rbp+68h]
0x18005b5f8  mov     [rdi+8], ax
0x18005b5fc  mov     rax, cs:?g_pfnCaptureRestrictedErrorInformation@coro@details@wil@@3P6APEAXX_EEA
0x18005b603  test    rax, rax
0x18005b606  jz      short loc_18005B611
0x18005b608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b60d  mov     [rdi-10h], rax
0x18005b611  lea     rbx, [rdi-48h]
0x18005b615  mov     qword ptr [rbx], 0
0x18005b61c  mov     qword ptr [rbx+8], 0
0x18005b624  mov     rcx, rbx
0x18005b627  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18005b62d  mov     rcx, rbx
0x18005b630  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18005b636  mov     dword ptr [rdi-50h], 2
0x18005b63d  mov     rax, 0
0x18005b647  add     rsp, 60h
0x18005b64b  pop     rdi
0x18005b64c  pop     rbp
0x18005b64d  pop     rbx
0x18005b64e  retn
```
