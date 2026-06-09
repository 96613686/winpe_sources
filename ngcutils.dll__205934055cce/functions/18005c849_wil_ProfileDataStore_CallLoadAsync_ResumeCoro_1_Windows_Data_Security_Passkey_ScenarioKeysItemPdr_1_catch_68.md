# _wil::ProfileDataStore::CallLoadAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$68

- ea: `0x18005c849`
- end: `0x18005c8b7`
- name: `_wil::ProfileDataStore::CallLoadAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$68`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18005c849`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005c88e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005c88e`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005c897`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005c897`

## pseudocode

```c
__int64 __fastcall wil::ProfileDataStore::CallLoadAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch_68(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx

  v2 = *(_QWORD *)(a2 + 120);
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
0x18005c849  mov     [rsp+arg_8], rdx
0x18005c84e  push    rbx
0x18005c84f  push    rbp
0x18005c850  push    rdi
0x18005c851  sub     rsp, 70h
0x18005c855  mov     rbp, rdx
0x18005c858  or      eax, 0FFFFFFFFh
0x18005c85b  mov     rdi, [rbp+78h]
0x18005c85f  mov     [rdi+8], ax
0x18005c863  mov     rax, cs:?g_pfnCaptureRestrictedErrorInformation@coro@details@wil@@3P6APEAXX_EEA
0x18005c86a  test    rax, rax
0x18005c86d  jz      short loc_18005C878
0x18005c86f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c874  mov     [rdi-8], rax
0x18005c878  lea     rbx, [rdi-18h]
0x18005c87c  mov     qword ptr [rbx], 0
0x18005c883  mov     qword ptr [rbx+8], 0
0x18005c88b  mov     rcx, rbx
0x18005c88e  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18005c894  mov     rcx, rbx
0x18005c897  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18005c89d  mov     dword ptr [rdi-20h], 2
0x18005c8a4  mov     rax, 0
0x18005c8ae  add     rsp, 70h
0x18005c8b2  pop     rdi
0x18005c8b3  pop     rbp
0x18005c8b4  pop     rbx
0x18005c8b5  retn
```
