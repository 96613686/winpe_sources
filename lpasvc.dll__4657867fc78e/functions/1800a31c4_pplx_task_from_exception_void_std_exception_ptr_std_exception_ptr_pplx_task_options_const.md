# pplx::task_from_exception<void,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)

- ea: `0x1800a31c4`
- end: `0x1800a3267`
- name: `??$task_from_exception@XVexception_ptr@std@@@pplx@@YA?AV?$task@X@0@Vexception_ptr@std@@AEBVtask_options@0@@Z`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c42e0`

## callees

- `0x180061c50`
- `0x1800636dc`
- `0x1800a21b0`
- `0x1800a5230`
- `0x1800a687c`
- `0x1800c3fd4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a324b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a324b`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800a31ff`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800a31ff`

## pseudocode

```c
__int64 __fastcall pplx::task_from_exception<void,std::exception_ptr>(
        __int64 a1,
        void *a2,
        const struct pplx::task_options *a3)
{
  __int64 v6; // rbx
  __int64 v7; // r8
  __int128 v9; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v10[16]; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v11[104]; // [rsp+48h] [rbp-11h] BYREF

  pplx::task_completion_event<unsigned char>::task_completion_event<unsigned char>(v10);
  v9 = 0;
  __ExceptionPtrCopy(&v9, a2);
  pplx::task_completion_event<void>::set_exception(v10, &v9);
  v6 = pplx::task_options::task_options((pplx::task_options *)v11, a3);
  std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(&v9, v10, v7);
  pplx::create_task<pplx::task_completion_event<void>>(a1, &v9, v6);
  std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(v10);
  __ExceptionPtrDestroy(a2);
  return a1;
}

```

## disassembly

```asm
0x1800a31c4  mov     [rsp-8+arg_10], rbx
0x1800a31c9  mov     [rsp-8+arg_8], rdx
0x1800a31ce  push    rbp
0x1800a31cf  push    rsi
0x1800a31d0  push    rdi
0x1800a31d1  lea     rbp, [rsp-47h]
0x1800a31d6  sub     rsp, 0A0h
0x1800a31dd  mov     rbx, r8
0x1800a31e0  mov     rdi, rdx
0x1800a31e3  mov     rsi, rcx
0x1800a31e6  lea     rcx, [rbp+57h+var_78]
0x1800a31ea  call    ??0?$task_completion_event@E@pplx@@QEAA@XZ; pplx::task_completion_event<uchar>::task_completion_event<uchar>(void)
0x1800a31ef  nop
0x1800a31f0  xorps   xmm0, xmm0
0x1800a31f3  movdqu  [rbp+57h+var_90], xmm0
0x1800a31f8  mov     rdx, rdi
0x1800a31fb  lea     rcx, [rbp+57h+var_90]
0x1800a31ff  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800a3205  lea     rdx, [rbp+57h+var_90]
0x1800a3209  lea     rcx, [rbp+57h+var_78]
0x1800a320d  call    ?set_exception@?$task_completion_event@X@pplx@@QEBA_NVexception_ptr@std@@@Z; pplx::task_completion_event<void>::set_exception(std::exception_ptr)
0x1800a3212  mov     rdx, rbx; struct pplx::task_options *
0x1800a3215  lea     rcx, [rbp+57h+var_68]; this
0x1800a3219  call    ??0task_options@pplx@@QEAA@AEBV01@@Z; pplx::task_options::task_options(pplx::task_options const &)
0x1800a321e  mov     rbx, rax
0x1800a3221  lea     rdx, [rbp+57h+var_78]
0x1800a3225  lea     rcx, [rbp+57h+var_90]
0x1800a3229  call    ??0?$shared_ptr@VWnfMessage@LPA@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(std::shared_ptr<LPA::WnfMessage> const &)
0x1800a322e  mov     r8, rbx
0x1800a3231  lea     rdx, [rbp+57h+var_90]
0x1800a3235  mov     rcx, rsi
0x1800a3238  call    ??$create_task@V?$task_completion_event@X@pplx@@@pplx@@YA?AV?$task@X@0@V?$task_completion_event@X@0@Vtask_options@0@@Z; pplx::create_task<pplx::task_completion_event<void>>(pplx::task_completion_event<void>,pplx::task_options)
0x1800a323d  nop
0x1800a323e  lea     rcx, [rbp+57h+var_78]
0x1800a3242  call    ??1?$shared_ptr@UApduHelperNotificationHandler@LPA@@@std@@QEAA@XZ; std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(void)
0x1800a3247  nop
0x1800a3248  mov     rcx, rdi
0x1800a324b  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800a3251  mov     rax, rsi
0x1800a3254  mov     rbx, [rsp+0B0h+arg_10]
0x1800a325c  add     rsp, 0A0h
0x1800a3263  pop     rdi
0x1800a3264  pop     rsi
0x1800a3265  pop     rbp
0x1800a3266  retn
```
