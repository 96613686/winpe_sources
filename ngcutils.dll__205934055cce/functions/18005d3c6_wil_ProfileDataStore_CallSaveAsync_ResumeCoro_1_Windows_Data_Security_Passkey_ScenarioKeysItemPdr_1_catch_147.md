# _wil::ProfileDataStore::CallSaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$147

- ea: `0x18005d3c6`
- end: `0x18005d437`
- name: `_wil::ProfileDataStore::CallSaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch$147`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18005d3c6`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005d40e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005d40e`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005d417`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18005d417`

## pseudocode

```c
__int64 __fastcall wil::ProfileDataStore::CallSaveAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr__::_1_::catch_147(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx

  v2 = *(_QWORD *)(a2 + 136);
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
0x18005d3c6  mov     [rsp+arg_8], rdx
0x18005d3cb  push    rbx
0x18005d3cc  push    rbp
0x18005d3cd  push    rdi
0x18005d3ce  sub     rsp, 50h
0x18005d3d2  mov     rbp, rdx
0x18005d3d5  or      eax, 0FFFFFFFFh
0x18005d3d8  mov     rdi, [rbp+88h]
0x18005d3df  mov     [rdi+8], ax
0x18005d3e3  mov     rax, cs:?g_pfnCaptureRestrictedErrorInformation@coro@details@wil@@3P6APEAXX_EEA
0x18005d3ea  test    rax, rax
0x18005d3ed  jz      short loc_18005D3F8
0x18005d3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d3f4  mov     [rdi-10h], rax
0x18005d3f8  lea     rbx, [rdi-48h]
0x18005d3fc  mov     qword ptr [rbx], 0
0x18005d403  mov     qword ptr [rbx+8], 0
0x18005d40b  mov     rcx, rbx
0x18005d40e  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18005d414  mov     rcx, rbx
0x18005d417  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18005d41d  mov     dword ptr [rdi-50h], 2
0x18005d424  mov     rax, 0
0x18005d42e  add     rsp, 50h
0x18005d432  pop     rdi
0x18005d433  pop     rbp
0x18005d434  pop     rbx
0x18005d435  retn
```
