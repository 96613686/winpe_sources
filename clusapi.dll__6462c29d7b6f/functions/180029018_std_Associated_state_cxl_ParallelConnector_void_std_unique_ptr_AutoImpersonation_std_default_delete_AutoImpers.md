# std::_Associated_state<cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation,std::default_delete<AutoImpersonation>>,ClusterHandleConnector>::BoxedValueAndException>::_Set_exception(std::exception_ptr,bool)

- ea: `0x180029018`
- end: `0x1800290c3`
- name: `?_Set_exception@?$_Associated_state@UBoxedValueAndException@?$ParallelConnector@PEAXV?$unique_ptr@VAutoImpersonation@@U?$default_delete@VAutoImpersonation@@@std@@@std@@UClusterHandleConnector@@@cxl@@@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800290cc`

## callees

- `0x18001cf28`
- `0x18001e56c`
- `0x180029018`
- `0x18002927c`
- `0x1800b5010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002904d`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002904d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180029092`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800290a7`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180029092`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800290a7`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18002906f`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18002906f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::_Associated_state<cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation>,ClusterHandleConnector>::BoxedValueAndException>::_Set_exception(
        _BYTE *a1,
        void *a2)
{
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v5[24]; // [rsp+30h] [rbp-18h] BYREF

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v5, a1 + 48);
  v4 = 0;
  __ExceptionPtrCopy(&v4, a2);
  if ( a1[209] )
    std::_Throw_future_error2(3);
  __ExceptionPtrAssign(a1 + 32, &v4);
  (*(void (__fastcall **)(_BYTE *, _BYTE *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, v5, 0);
  __ExceptionPtrDestroy(&v4);
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v5);
  __ExceptionPtrDestroy(a2);
}

```

## disassembly

```asm
0x180029018  mov     [rsp+arg_10], rbx
0x18002901d  mov     [rsp+arg_8], rdx
0x180029022  push    rdi
0x180029023  sub     rsp, 40h
0x180029027  mov     rdi, rdx
0x18002902a  mov     rbx, rcx
0x18002902d  lea     rdx, [rcx+30h]
0x180029031  lea     rcx, [rsp+48h+var_18]
0x180029036  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18002903b  nop
0x18002903c  xorps   xmm0, xmm0
0x18002903f  movdqu  [rsp+48h+var_28], xmm0
0x180029045  mov     rdx, rdi
0x180029048  lea     rcx, [rsp+48h+var_28]
0x18002904d  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180029053  lea     rax, [rsp+48h+var_28]
0x180029058  mov     [rsp+48h+arg_0], rax
0x18002905d  cmp     byte ptr [rbx+0D1h], 0
0x180029064  jnz     short loc_1800290B8
0x180029066  lea     rcx, [rbx+20h]
0x18002906a  lea     rdx, [rsp+48h+var_28]
0x18002906f  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180029075  mov     rax, [rbx]
0x180029078  xor     r8d, r8d
0x18002907b  lea     rdx, [rsp+48h+var_18]
0x180029080  mov     rcx, rbx
0x180029083  mov     rax, [rax+28h]
0x180029087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002908c  nop
0x18002908d  lea     rcx, [rsp+48h+var_28]
0x180029092  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180029098  nop
0x180029099  lea     rcx, [rsp+48h+var_18]
0x18002909e  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1800290a3  nop
0x1800290a4  mov     rcx, rdi
0x1800290a7  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800290ad  mov     rbx, [rsp+48h+arg_10]
0x1800290b2  add     rsp, 40h
0x1800290b6  pop     rdi
0x1800290b7  retn
0x1800290b8  mov     ecx, 3
0x1800290bd  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
```
