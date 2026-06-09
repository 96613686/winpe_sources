# pplx::task_from_exception<bool,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)

- ea: `0x1800a331c`
- end: `0x1800a33bf`
- name: `??$task_from_exception@_NVexception_ptr@std@@@pplx@@YA?AV?$task@_N@0@Vexception_ptr@std@@AEBVtask_options@0@@Z`
- size: `163`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180023a70`
- `0x1800a9588`
- `0x1800f3190`
- `0x1800f5b50`
- `0x1800f5ef0`
- `0x1800fa5aa`

## callees

- `0x180061c50`
- `0x1800636dc`
- `0x1800a22e0`
- `0x1800a2808`
- `0x1800a687c`
- `0x1800c3f58`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a33a3`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a33a3`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800a3357`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800a3357`

## pseudocode

```c
__int64 __fastcall pplx::task_from_exception<bool,std::exception_ptr>(
        __int64 a1,
        void *a2,
        const struct pplx::task_options *a3)
{
  __int64 v6; // rbx
  __int64 v7; // r8
  __int128 v9; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v10[16]; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v11[104]; // [rsp+48h] [rbp-11h] BYREF

  std::make_shared<pplx::details::_Task_completion_event_impl<bool>,>(v10);
  v9 = 0;
  __ExceptionPtrCopy(&v9, a2);
  pplx::task_completion_event<int>::set_exception(v10, &v9);
  v6 = pplx::task_options::task_options((pplx::task_options *)v11, a3);
  std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(&v9, v10, v7);
  pplx::create_task<pplx::task_completion_event<bool>>(a1, &v9, v6);
  std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(v10);
  __ExceptionPtrDestroy(a2);
  return a1;
}

```

## disassembly

```asm
0x1800a331c  mov     [rsp-8+arg_10], rbx
0x1800a3321  mov     [rsp-8+arg_8], rdx
0x1800a3326  push    rbp
0x1800a3327  push    rsi
0x1800a3328  push    rdi
0x1800a3329  lea     rbp, [rsp-47h]
0x1800a332e  sub     rsp, 0A0h
0x1800a3335  mov     rbx, r8
0x1800a3338  mov     rdi, rdx
0x1800a333b  mov     rsi, rcx
0x1800a333e  lea     rcx, [rbp+57h+var_78]
0x1800a3342  call    ??$make_shared@U?$_Task_completion_event_impl@_N@details@pplx@@$$V@std@@YA?AV?$shared_ptr@U?$_Task_completion_event_impl@_N@details@pplx@@@0@XZ; std::make_shared<pplx::details::_Task_completion_event_impl<bool>,>(void)
0x1800a3347  nop
0x1800a3348  xorps   xmm0, xmm0
0x1800a334b  movdqu  [rbp+57h+var_90], xmm0
0x1800a3350  mov     rdx, rdi
0x1800a3353  lea     rcx, [rbp+57h+var_90]
0x1800a3357  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800a335d  lea     rdx, [rbp+57h+var_90]
0x1800a3361  lea     rcx, [rbp+57h+var_78]
0x1800a3365  call    ?set_exception@?$task_completion_event@H@pplx@@QEBA_NVexception_ptr@std@@@Z; pplx::task_completion_event<int>::set_exception(std::exception_ptr)
0x1800a336a  mov     rdx, rbx; struct pplx::task_options *
0x1800a336d  lea     rcx, [rbp+57h+var_68]; this
0x1800a3371  call    ??0task_options@pplx@@QEAA@AEBV01@@Z; pplx::task_options::task_options(pplx::task_options const &)
0x1800a3376  mov     rbx, rax
0x1800a3379  lea     rdx, [rbp+57h+var_78]
0x1800a337d  lea     rcx, [rbp+57h+var_90]
0x1800a3381  call    ??0?$shared_ptr@VWnfMessage@LPA@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(std::shared_ptr<LPA::WnfMessage> const &)
0x1800a3386  mov     r8, rbx
0x1800a3389  lea     rdx, [rbp+57h+var_90]
0x1800a338d  mov     rcx, rsi
0x1800a3390  call    ??$create_task@V?$task_completion_event@_N@pplx@@@pplx@@YA?AV?$task@_N@0@V?$task_completion_event@_N@0@Vtask_options@0@@Z; pplx::create_task<pplx::task_completion_event<bool>>(pplx::task_completion_event<bool>,pplx::task_options)
0x1800a3395  nop
0x1800a3396  lea     rcx, [rbp+57h+var_78]
0x1800a339a  call    ??1?$shared_ptr@UApduHelperNotificationHandler@LPA@@@std@@QEAA@XZ; std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(void)
0x1800a339f  nop
0x1800a33a0  mov     rcx, rdi
0x1800a33a3  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800a33a9  mov     rax, rsi
0x1800a33ac  mov     rbx, [rsp+0B0h+arg_10]
0x1800a33b4  add     rsp, 0A0h
0x1800a33bb  pop     rdi
0x1800a33bc  pop     rsi
0x1800a33bd  pop     rbp
0x1800a33be  retn
```
