# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::Create(void)

- ea: `0x180004f8c`
- end: `0x180004fbd`
- name: `?Create@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVServiceModule@Internal@Windows@@XZ`
- size: `49`
- prototype: `__int64 *()`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800014c0`
- `0x180004820`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180004fa4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180004fa4`

## pseudocode

```c
__int64 *Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::Create()
{
  __int64 *result; // rax

  InitOnceExecuteOnce(
    &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::initOnceOutOfProc_,
    _lambda_0436b89998ddae64b987abcfc9f7e79b_::_lambda_invoker_cdecl_,
    0,
    0);
  result = &Microsoft::WRL::Details::StaticStorage<Windows::Internal::ServiceModule,1,int>::instance_;
  byte_1800198F8 = 1;
  return result;
}

```

## disassembly

```asm
0x180004f8c  sub     rsp, 28h
0x180004f90  xor     r9d, r9d; Context
0x180004f93  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_0436b89998ddae64b987abcfc9f7e79b_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180004f9a  xor     r8d, r8d; Parameter
0x180004f9d  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180004fa4  call    cs:__imp_InitOnceExecuteOnce
0x180004faa  lea     rax, ?instance_@?$StaticStorage@VServiceModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::ServiceModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::ServiceModule,1,int>::instance_
0x180004fb1  mov     cs:byte_1800198F8, 1
0x180004fb8  add     rsp, 28h
0x180004fbc  retn
```
