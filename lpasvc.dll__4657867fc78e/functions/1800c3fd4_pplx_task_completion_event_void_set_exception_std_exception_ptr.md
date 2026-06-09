# pplx::task_completion_event<void>::set_exception(std::exception_ptr)

- ea: `0x1800c3fd4`
- end: `0x1800c4049`
- name: `?set_exception@?$task_completion_event@X@pplx@@QEBA_NVexception_ptr@std@@@Z`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030f70`
- `0x1800a31c4`

## callees

- `0x18009a26c`
- `0x1800a7fdc`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800c4036`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800c4036`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c400e`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c400e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall pplx::task_completion_event<void>::set_exception(__int64 a1, void *a2)
{
  __int128 v5; // [rsp+20h] [rbp-38h] BYREF
  void *v6; // [rsp+30h] [rbp-28h] BYREF
  __int128 v7; // [rsp+38h] [rbp-20h] BYREF
  __int64 v8; // [rsp+48h] [rbp-10h]
  void *retaddr; // [rsp+58h] [rbp+0h]

  v7 = 0;
  v8 = 0;
  v6 = retaddr;
  v5 = 0;
  __ExceptionPtrCopy(&v5, a2);
  LOBYTE(a1) = pplx::task_completion_event<bool>::_Cancel<std::exception_ptr>(a1, &v5, (__int64)&v6);
  std::vector<void *>::_Tidy(&v7);
  __ExceptionPtrDestroy(a2);
  return a1;
}

```

## disassembly

```asm
0x1800c3fd4  mov     r11, rsp
0x1800c3fd7  mov     [r11+18h], rbx
0x1800c3fdb  mov     [r11+10h], rdx
0x1800c3fdf  push    rdi
0x1800c3fe0  sub     rsp, 50h
0x1800c3fe4  mov     rdi, rdx
0x1800c3fe7  mov     rbx, rcx
0x1800c3fea  mov     rax, [rsp+58h]
0x1800c3fef  xorps   xmm0, xmm0
0x1800c3ff2  movdqu  [rsp+58h+var_20], xmm0
0x1800c3ff8  mov     qword ptr [r11-10h], 0
0x1800c4000  mov     [r11-28h], rax
0x1800c4004  movdqu  [rsp+58h+var_38], xmm0
0x1800c400a  lea     rcx, [r11-38h]
0x1800c400e  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800c4014  lea     r8, [rsp+58h+var_28]
0x1800c4019  lea     rdx, [rsp+58h+var_38]
0x1800c401e  mov     rcx, rbx
0x1800c4021  call    ??$_Cancel@Vexception_ptr@std@@@?$task_completion_event@_N@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z; pplx::task_completion_event<bool>::_Cancel<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)
0x1800c4026  mov     bl, al
0x1800c4028  lea     rcx, [rsp+58h+var_20]
0x1800c402d  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x1800c4032  nop
0x1800c4033  mov     rcx, rdi
0x1800c4036  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800c403c  mov     al, bl
0x1800c403e  mov     rbx, [rsp+58h+arg_10]
0x1800c4043  add     rsp, 50h
0x1800c4047  pop     rdi
0x1800c4048  retn
```
