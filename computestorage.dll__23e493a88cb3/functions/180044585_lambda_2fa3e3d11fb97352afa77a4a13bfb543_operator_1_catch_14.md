# __lambda_2fa3e3d11fb97352afa77a4a13bfb543_::operator()_::_1_::catch$14

- ea: `0x180044585`
- end: `0x1800445f3`
- name: `__lambda_2fa3e3d11fb97352afa77a4a13bfb543_::operator()_::_1_::catch$14`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180025638`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800445a6`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800445a6`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800445d4`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800445d4`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800445b6`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800445b6`

## pseudocode

```c
__int64 __fastcall _lambda_2fa3e3d11fb97352afa77a4a13bfb543_::operator()_::_1_::catch_14(__int64 a1, __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(a2 + 208);
  *(_OWORD *)(a2 + 32) = 0;
  __ExceptionPtrCreate((void *)(a2 + 32));
  __ExceptionPtrCurrentException((void *)(a2 + 32));
  Concurrency::details::_Task_impl_base::_CancelWithException(v3, (const struct std::exception_ptr *)(a2 + 32));
  __ExceptionPtrDestroy((void *)(a2 + 32));
  return 0;
}

```

## disassembly

```asm
0x180044585  mov     [rsp+arg_8], rdx
0x18004458a  push    rbx
0x18004458b  push    rbp
0x18004458c  sub     rsp, 28h
0x180044590  mov     rbp, rdx
0x180044593  mov     rbx, [rbp+0D0h]
0x18004459a  xorps   xmm1, xmm1
0x18004459d  movdqu  xmmword ptr [rbp+20h], xmm1
0x1800445a2  lea     rcx, [rbp+20h]
0x1800445a6  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800445ad  nop     dword ptr [rax+rax+00h]
0x1800445b2  lea     rcx, [rbp+20h]
0x1800445b6  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800445bd  nop     dword ptr [rax+rax+00h]
0x1800445c2  nop
0x1800445c3  lea     rdx, [rbp+20h]; struct std::exception_ptr *
0x1800445c7  mov     rcx, rbx; this
0x1800445ca  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x1800445cf  nop
0x1800445d0  lea     rcx, [rbp+20h]
0x1800445d4  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800445db  nop     dword ptr [rax+rax+00h]
0x1800445e0  nop
0x1800445e1  mov     rax, 0
0x1800445eb  add     rsp, 28h
0x1800445ef  pop     rbp
0x1800445f0  pop     rbx
0x1800445f1  retn
```
