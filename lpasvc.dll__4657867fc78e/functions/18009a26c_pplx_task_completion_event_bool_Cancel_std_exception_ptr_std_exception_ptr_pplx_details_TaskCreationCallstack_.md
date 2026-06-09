# pplx::task_completion_event<bool>::_Cancel<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)

- ea: `0x18009a26c`
- end: `0x18009a2d8`
- name: `??$_Cancel@Vexception_ptr@std@@@?$task_completion_event@_N@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z`
- size: `108`
- prototype: `char __fastcall(__int64, void *, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180048d90`
- `0x180048f00`
- `0x1800c3f58`
- `0x1800c3fd4`

## callees

- `0x18009a26c`
- `0x18009be44`
- `0x1800ba294`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18009a2c0`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18009a2c0`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18009a295`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18009a295`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall pplx::task_completion_event<bool>::_Cancel<std::exception_ptr>(__int64 a1, void *a2, __int64 a3)
{
  char v6; // bl
  __int128 v8; // [rsp+20h] [rbp-18h] BYREF

  v8 = 0;
  __ExceptionPtrCopy(&v8, a2);
  if ( (unsigned __int8)pplx::task_completion_event<bool>::_StoreException<std::exception_ptr>(a1, &v8, a3) )
    v6 = pplx::task_completion_event<unsigned __int64>::_CancelInternal(a1);
  else
    v6 = 0;
  __ExceptionPtrDestroy(a2);
  return v6;
}

```

## disassembly

```asm
0x18009a26c  mov     rax, rsp
0x18009a26f  mov     [rax+8], rbx
0x18009a273  mov     [rax+18h], rsi
0x18009a277  mov     [rax+10h], rdx
0x18009a27b  push    rdi
0x18009a27c  sub     rsp, 30h
0x18009a280  mov     rbx, r8
0x18009a283  mov     rdi, rdx
0x18009a286  mov     rsi, rcx
0x18009a289  xorps   xmm0, xmm0
0x18009a28c  movdqu  xmmword ptr [rax-18h], xmm0
0x18009a291  lea     rcx, [rax-18h]
0x18009a295  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18009a29b  mov     r8, rbx
0x18009a29e  lea     rdx, [rsp+38h+var_18]
0x18009a2a3  mov     rcx, rsi
0x18009a2a6  call    ??$_StoreException@Vexception_ptr@std@@@?$task_completion_event@_N@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z; pplx::task_completion_event<bool>::_StoreException<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)
0x18009a2ab  test    al, al
0x18009a2ad  jz      short loc_18009A2BB
0x18009a2af  mov     rcx, rsi
0x18009a2b2  call    ?_CancelInternal@?$task_completion_event@_K@pplx@@AEBA_NXZ; pplx::task_completion_event<unsigned __int64>::_CancelInternal(void)
0x18009a2b7  mov     bl, al
0x18009a2b9  jmp     short loc_18009A2BD
0x18009a2bb  xor     bl, bl
0x18009a2bd  mov     rcx, rdi
0x18009a2c0  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18009a2c6  mov     al, bl
0x18009a2c8  mov     rbx, [rsp+38h+arg_0]
0x18009a2cd  mov     rsi, [rsp+38h+arg_10]
0x18009a2d2  add     rsp, 30h
0x18009a2d6  pop     rdi
0x18009a2d7  retn
```
