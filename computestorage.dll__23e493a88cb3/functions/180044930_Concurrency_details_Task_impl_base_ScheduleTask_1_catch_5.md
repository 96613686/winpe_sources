# _Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch$5

- ea: `0x180044930`
- end: `0x1800449a2`
- name: `_Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch$5`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180025638`
- `0x180044930`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180044955`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180044955`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180044983`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180044983`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180044965`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180044965`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch_5(__int64 a1, __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(a2 + 48);
  if ( !*((_QWORD *)v3 + 2) )
  {
    *(_OWORD *)(a2 + 32) = 0;
    __ExceptionPtrCreate((void *)(a2 + 32));
    __ExceptionPtrCurrentException((void *)(a2 + 32));
    Concurrency::details::_Task_impl_base::_CancelWithException(v3, (const struct std::exception_ptr *)(a2 + 32));
    __ExceptionPtrDestroy((void *)(a2 + 32));
  }
  return 0;
}

```

## disassembly

```asm
0x180044930  mov     [rsp+arg_8], rdx
0x180044935  push    rbx
0x180044936  push    rbp
0x180044937  sub     rsp, 28h
0x18004493b  mov     rbp, rdx
0x18004493e  mov     rbx, [rbp+30h]
0x180044942  cmp     qword ptr [rbx+10h], 0
0x180044947  jnz     short loc_180044990
0x180044949  xorps   xmm1, xmm1
0x18004494c  movdqu  xmmword ptr [rbp+20h], xmm1
0x180044951  lea     rcx, [rbp+20h]
0x180044955  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18004495c  nop     dword ptr [rax+rax+00h]
0x180044961  lea     rcx, [rbp+20h]
0x180044965  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18004496c  nop     dword ptr [rax+rax+00h]
0x180044971  nop
0x180044972  lea     rdx, [rbp+20h]; struct std::exception_ptr *
0x180044976  mov     rcx, rbx; this
0x180044979  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x18004497e  nop
0x18004497f  lea     rcx, [rbp+20h]
0x180044983  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18004498a  nop     dword ptr [rax+rax+00h]
0x18004498f  nop
0x180044990  mov     rax, 0
0x18004499a  add     rsp, 28h
0x18004499e  pop     rbp
0x18004499f  pop     rbx
0x1800449a0  retn
```
