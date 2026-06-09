# pplx::task_from_exception<unsigned __int64,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)

- ea: `0x1800a3270`
- end: `0x1800a3313`
- name: `??$task_from_exception@_KVexception_ptr@std@@@pplx@@YA?AV?$task@_K@0@Vexception_ptr@std@@AEBVtask_options@0@@Z`
- size: `163`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180020730`
- `0x180023860`
- `0x1800a2070`
- `0x1800a944c`
- `0x1800f30a0`
- `0x1800f5c10`
- `0x1800f5e70`
- `0x1800fa4fe`

## callees

- `0x180061c50`
- `0x1800636dc`
- `0x1800a2248`
- `0x1800a27c8`
- `0x1800a687c`
- `0x1800c3f58`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a32f7`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a32f7`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800a32ab`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800a32ab`

## pseudocode

```c
__int64 __fastcall pplx::task_from_exception<unsigned __int64,std::exception_ptr>(
        __int64 a1,
        void *a2,
        const struct pplx::task_options *a3)
{
  __int64 v6; // rbx
  __int64 v7; // r8
  __int128 v9; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v10[16]; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v11[104]; // [rsp+48h] [rbp-11h] BYREF

  std::make_shared<pplx::details::_Task_completion_event_impl<unsigned __int64>,>(v10);
  v9 = 0;
  __ExceptionPtrCopy(&v9, a2);
  pplx::task_completion_event<int>::set_exception(v10, &v9);
  v6 = pplx::task_options::task_options((pplx::task_options *)v11, a3);
  std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(&v9, v10, v7);
  pplx::create_task<pplx::task_completion_event<unsigned __int64>>(a1, &v9, v6);
  std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(v10);
  __ExceptionPtrDestroy(a2);
  return a1;
}

```

## disassembly

```asm
0x1800a3270  mov     [rsp-8+arg_10], rbx
0x1800a3275  mov     [rsp-8+arg_8], rdx
0x1800a327a  push    rbp
0x1800a327b  push    rsi
0x1800a327c  push    rdi
0x1800a327d  lea     rbp, [rsp-47h]
0x1800a3282  sub     rsp, 0A0h
0x1800a3289  mov     rbx, r8
0x1800a328c  mov     rdi, rdx
0x1800a328f  mov     rsi, rcx
0x1800a3292  lea     rcx, [rbp+57h+var_78]
0x1800a3296  call    ??$make_shared@U?$_Task_completion_event_impl@_K@details@pplx@@$$V@std@@YA?AV?$shared_ptr@U?$_Task_completion_event_impl@_K@details@pplx@@@0@XZ; std::make_shared<pplx::details::_Task_completion_event_impl<unsigned __int64>,>(void)
0x1800a329b  nop
0x1800a329c  xorps   xmm0, xmm0
0x1800a329f  movdqu  [rbp+57h+var_90], xmm0
0x1800a32a4  mov     rdx, rdi
0x1800a32a7  lea     rcx, [rbp+57h+var_90]
0x1800a32ab  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800a32b1  lea     rdx, [rbp+57h+var_90]
0x1800a32b5  lea     rcx, [rbp+57h+var_78]
0x1800a32b9  call    ?set_exception@?$task_completion_event@H@pplx@@QEBA_NVexception_ptr@std@@@Z; pplx::task_completion_event<int>::set_exception(std::exception_ptr)
0x1800a32be  mov     rdx, rbx; struct pplx::task_options *
0x1800a32c1  lea     rcx, [rbp+57h+var_68]; this
0x1800a32c5  call    ??0task_options@pplx@@QEAA@AEBV01@@Z; pplx::task_options::task_options(pplx::task_options const &)
0x1800a32ca  mov     rbx, rax
0x1800a32cd  lea     rdx, [rbp+57h+var_78]
0x1800a32d1  lea     rcx, [rbp+57h+var_90]
0x1800a32d5  call    ??0?$shared_ptr@VWnfMessage@LPA@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(std::shared_ptr<LPA::WnfMessage> const &)
0x1800a32da  mov     r8, rbx
0x1800a32dd  lea     rdx, [rbp+57h+var_90]
0x1800a32e1  mov     rcx, rsi
0x1800a32e4  call    ??$create_task@V?$task_completion_event@_K@pplx@@@pplx@@YA?AV?$task@_K@0@V?$task_completion_event@_K@0@Vtask_options@0@@Z; pplx::create_task<pplx::task_completion_event<unsigned __int64>>(pplx::task_completion_event<unsigned __int64>,pplx::task_options)
0x1800a32e9  nop
0x1800a32ea  lea     rcx, [rbp+57h+var_78]
0x1800a32ee  call    ??1?$shared_ptr@UApduHelperNotificationHandler@LPA@@@std@@QEAA@XZ; std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(void)
0x1800a32f3  nop
0x1800a32f4  mov     rcx, rdi
0x1800a32f7  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800a32fd  mov     rax, rsi
0x1800a3300  mov     rbx, [rsp+0B0h+arg_10]
0x1800a3308  add     rsp, 0A0h
0x1800a330f  pop     rdi
0x1800a3310  pop     rsi
0x1800a3311  pop     rbp
0x1800a3312  retn
```
