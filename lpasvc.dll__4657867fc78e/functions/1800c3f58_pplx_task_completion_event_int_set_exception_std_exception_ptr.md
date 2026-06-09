# pplx::task_completion_event<int>::set_exception(std::exception_ptr)

- ea: `0x1800c3f58`
- end: `0x1800c3fcd`
- name: `?set_exception@?$task_completion_event@H@pplx@@QEBA_NVexception_ptr@std@@@Z`
- size: `117`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023e20`
- `0x1800a3118`
- `0x1800a3270`
- `0x1800a331c`
- `0x1800f3260`

## callees

- `0x18009a26c`
- `0x1800a7fdc`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800c3fba`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800c3fba`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c3f92`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c3f92`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall pplx::task_completion_event<int>::set_exception(__int64 a1, void *a2)
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
0x1800c3f58  mov     r11, rsp
0x1800c3f5b  mov     [r11+8], rbx
0x1800c3f5f  mov     [r11+10h], rdx
0x1800c3f63  push    rdi
0x1800c3f64  sub     rsp, 50h
0x1800c3f68  mov     rdi, rdx
0x1800c3f6b  mov     rbx, rcx
0x1800c3f6e  mov     rax, [rsp+58h]
0x1800c3f73  xorps   xmm0, xmm0
0x1800c3f76  movdqu  [rsp+58h+var_20], xmm0
0x1800c3f7c  mov     qword ptr [r11-10h], 0
0x1800c3f84  mov     [r11-28h], rax
0x1800c3f88  movdqu  [rsp+58h+var_38], xmm0
0x1800c3f8e  lea     rcx, [r11-38h]
0x1800c3f92  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800c3f98  lea     r8, [rsp+58h+var_28]
0x1800c3f9d  lea     rdx, [rsp+58h+var_38]
0x1800c3fa2  mov     rcx, rbx
0x1800c3fa5  call    ??$_Cancel@Vexception_ptr@std@@@?$task_completion_event@_N@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z; pplx::task_completion_event<bool>::_Cancel<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)
0x1800c3faa  mov     bl, al
0x1800c3fac  lea     rcx, [rsp+58h+var_20]
0x1800c3fb1  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x1800c3fb6  nop
0x1800c3fb7  mov     rcx, rdi
0x1800c3fba  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800c3fc0  mov     al, bl
0x1800c3fc2  mov     rbx, [rsp+58h+arg_0]
0x1800c3fc7  add     rsp, 50h
0x1800c3fcb  pop     rdi
0x1800c3fcc  retn
```
