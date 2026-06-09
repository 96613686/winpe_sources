# _Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_92025865ef304844afd880c1a9e1f846__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$5

- ea: `0x180044aa1`
- end: `0x180044b10`
- name: `_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_92025865ef304844afd880c1a9e1f846__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$5`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180025638`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180044ac3`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180044ac3`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180044af1`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180044af1`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180044ad3`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180044ad3`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_92025865ef304844afd880c1a9e1f846__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch_5(
        __int64 a1,
        __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(*(_QWORD *)(a2 + 48) + 8LL);
  *(_OWORD *)(a2 + 48) = 0;
  __ExceptionPtrCreate((void *)(a2 + 48));
  __ExceptionPtrCurrentException((void *)(a2 + 48));
  Concurrency::details::_Task_impl_base::_CancelWithException(v3, (const struct std::exception_ptr *)(a2 + 48));
  __ExceptionPtrDestroy((void *)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x180044aa1  mov     [rsp+arg_8], rdx
0x180044aa6  push    rbx
0x180044aa7  push    rbp
0x180044aa8  sub     rsp, 38h
0x180044aac  mov     rbp, rdx
0x180044aaf  mov     rax, [rbp+30h]
0x180044ab3  mov     rbx, [rax+8]
0x180044ab7  xorps   xmm1, xmm1
0x180044aba  movdqu  xmmword ptr [rbp+30h], xmm1
0x180044abf  lea     rcx, [rbp+30h]
0x180044ac3  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180044aca  nop     dword ptr [rax+rax+00h]
0x180044acf  lea     rcx, [rbp+30h]
0x180044ad3  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180044ada  nop     dword ptr [rax+rax+00h]
0x180044adf  nop
0x180044ae0  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x180044ae4  mov     rcx, rbx; this
0x180044ae7  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x180044aec  nop
0x180044aed  lea     rcx, [rbp+30h]
0x180044af1  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180044af8  nop     dword ptr [rax+rax+00h]
0x180044afd  nop
0x180044afe  mov     rax, 0
0x180044b08  add     rsp, 38h
0x180044b0c  pop     rbp
0x180044b0d  pop     rbx
0x180044b0e  retn
```
