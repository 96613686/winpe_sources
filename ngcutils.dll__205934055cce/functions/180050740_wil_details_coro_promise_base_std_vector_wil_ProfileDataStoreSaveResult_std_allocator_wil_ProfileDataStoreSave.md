# wil::details::coro::promise_base<std::vector<wil::ProfileDataStoreSaveResult,std::allocator<wil::ProfileDataStoreSaveResult>>>::unhandled_exception(void)

- ea: `0x180050740`
- end: `0x180050799`
- name: `?unhandled_exception@?$promise_base@V?$vector@VProfileDataStoreSaveResult@wil@@V?$allocator@VProfileDataStoreSaveResult@wil@@@std@@@std@@@coro@details@wil@@QEAAXXZ`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005b192`

## callees

- `0x180050740`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180050778`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180050778`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180050781`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180050781`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::coro::promise_base<std::vector<wil::ProfileDataStoreSaveResult>>::unhandled_exception(
        _QWORD *a1)
{
  if ( wil::details::coro::g_pfnCaptureRestrictedErrorInformation )
    a1[6] = wil::details::coro::g_pfnCaptureRestrictedErrorInformation();
  a1[3] = 0;
  a1[4] = 0;
  __ExceptionPtrCreate(a1 + 3);
  __ExceptionPtrCurrentException(a1 + 3);
  *((_DWORD *)a1 + 4) = 2;
}

```

## disassembly

```asm
0x180050740  mov     [rsp+arg_0], rbx
0x180050745  push    rdi
0x180050746  sub     rsp, 20h
0x18005074a  mov     rdi, rcx
0x18005074d  mov     rax, cs:?g_pfnCaptureRestrictedErrorInformation@coro@details@wil@@3P6APEAXX_EEA
0x180050754  test    rax, rax
0x180050757  jz      short loc_180050762
0x180050759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005075e  mov     [rdi+30h], rax
0x180050762  lea     rbx, [rdi+18h]
0x180050766  mov     qword ptr [rbx], 0
0x18005076d  mov     qword ptr [rbx+8], 0
0x180050775  mov     rcx, rbx
0x180050778  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18005077e  mov     rcx, rbx
0x180050781  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180050787  mov     dword ptr [rdi+10h], 2
0x18005078e  mov     rbx, [rsp+28h+arg_0]
0x180050793  add     rsp, 20h
0x180050797  pop     rdi
0x180050798  retn
```
