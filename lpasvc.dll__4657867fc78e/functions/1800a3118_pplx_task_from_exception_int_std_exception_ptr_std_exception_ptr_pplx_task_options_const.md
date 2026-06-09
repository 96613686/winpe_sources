# pplx::task_from_exception<int,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)

- ea: `0x1800a3118`
- end: `0x1800a31bb`
- name: `??$task_from_exception@HVexception_ptr@std@@@pplx@@YA?AV?$task@H@0@Vexception_ptr@std@@AEBVtask_options@0@@Z`
- size: `163`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a1fc8`
- `0x1800a9310`
- `0x1800fa452`

## callees

- `0x180061c50`
- `0x1800636dc`
- `0x1800a2118`
- `0x1800a2788`
- `0x1800a687c`
- `0x1800c3f58`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a319f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a319f`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800a3153`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800a3153`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall pplx::task_from_exception<int,std::exception_ptr>(
        __int64 a1,
        void *a2,
        const struct pplx::task_options *a3)
{
  __int64 v6; // rbx
  __int64 v7; // r8
  __int128 v9; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v10[16]; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v11[104]; // [rsp+48h] [rbp-11h] BYREF

  std::make_shared<pplx::details::_Task_completion_event_impl<int>,>(v10);
  v9 = 0;
  __ExceptionPtrCopy(&v9, a2);
  pplx::task_completion_event<int>::set_exception(v10, &v9);
  v6 = pplx::task_options::task_options((pplx::task_options *)v11, a3);
  std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(&v9, v10, v7);
  pplx::create_task<pplx::task_completion_event<int>>(a1, &v9, v6);
  std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(v10);
  __ExceptionPtrDestroy(a2);
  return a1;
}

```

## disassembly

```asm
0x1800a3118  mov     [rsp-8+arg_10], rbx
0x1800a311d  mov     [rsp-8+arg_8], rdx
0x1800a3122  push    rbp
0x1800a3123  push    rsi
0x1800a3124  push    rdi
0x1800a3125  lea     rbp, [rsp-47h]
0x1800a312a  sub     rsp, 0A0h
0x1800a3131  mov     rbx, r8
0x1800a3134  mov     rdi, rdx
0x1800a3137  mov     rsi, rcx
0x1800a313a  lea     rcx, [rbp+57h+var_78]
0x1800a313e  call    ??$make_shared@U?$_Task_completion_event_impl@H@details@pplx@@$$V@std@@YA?AV?$shared_ptr@U?$_Task_completion_event_impl@H@details@pplx@@@0@XZ; std::make_shared<pplx::details::_Task_completion_event_impl<int>,>(void)
0x1800a3143  nop
0x1800a3144  xorps   xmm0, xmm0
0x1800a3147  movdqu  [rbp+57h+var_90], xmm0
0x1800a314c  mov     rdx, rdi
0x1800a314f  lea     rcx, [rbp+57h+var_90]
0x1800a3153  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800a3159  lea     rdx, [rbp+57h+var_90]
0x1800a315d  lea     rcx, [rbp+57h+var_78]
0x1800a3161  call    ?set_exception@?$task_completion_event@H@pplx@@QEBA_NVexception_ptr@std@@@Z; pplx::task_completion_event<int>::set_exception(std::exception_ptr)
0x1800a3166  mov     rdx, rbx; struct pplx::task_options *
0x1800a3169  lea     rcx, [rbp+57h+var_68]; this
0x1800a316d  call    ??0task_options@pplx@@QEAA@AEBV01@@Z; pplx::task_options::task_options(pplx::task_options const &)
0x1800a3172  mov     rbx, rax
0x1800a3175  lea     rdx, [rbp+57h+var_78]
0x1800a3179  lea     rcx, [rbp+57h+var_90]
0x1800a317d  call    ??0?$shared_ptr@VWnfMessage@LPA@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(std::shared_ptr<LPA::WnfMessage> const &)
0x1800a3182  mov     r8, rbx
0x1800a3185  lea     rdx, [rbp+57h+var_90]
0x1800a3189  mov     rcx, rsi
0x1800a318c  call    ??$create_task@V?$task_completion_event@H@pplx@@@pplx@@YA?AV?$task@H@0@V?$task_completion_event@H@0@Vtask_options@0@@Z; pplx::create_task<pplx::task_completion_event<int>>(pplx::task_completion_event<int>,pplx::task_options)
0x1800a3191  nop
0x1800a3192  lea     rcx, [rbp+57h+var_78]
0x1800a3196  call    ??1?$shared_ptr@UApduHelperNotificationHandler@LPA@@@std@@QEAA@XZ; std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(void)
0x1800a319b  nop
0x1800a319c  mov     rcx, rdi
0x1800a319f  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800a31a5  mov     rax, rsi
0x1800a31a8  mov     rbx, [rsp+0B0h+arg_10]
0x1800a31b0  add     rsp, 0A0h
0x1800a31b7  pop     rdi
0x1800a31b8  pop     rsi
0x1800a31b9  pop     rbp
0x1800a31ba  retn
```
