# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create(void)

- ea: `0x180004fc4`
- end: `0x180004ff5`
- name: `?Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ`
- size: `49`
- prototype: `__int64 *()`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800014e0`
- `0x180004820`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180004fdc`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180004fdc`

## pseudocode

```c
__int64 *Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create()
{
  __int64 *result; // rax

  InitOnceExecuteOnce(
    &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::initOnceOutOfProc_,
    _lambda_253709c146e3c4eefdc38a0c994771db_::_lambda_invoker_cdecl_,
    0,
    0);
  result = &Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_;
  byte_1800198B0 = 1;
  return result;
}

```

## disassembly

```asm
0x180004fc4  sub     rsp, 28h
0x180004fc8  xor     r9d, r9d; Context
0x180004fcb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_253709c146e3c4eefdc38a0c994771db_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180004fd2  xor     r8d, r8d; Parameter
0x180004fd5  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180004fdc  call    cs:__imp_InitOnceExecuteOnce
0x180004fe2  lea     rax, ?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x180004fe9  mov     cs:byte_1800198B0, 1
0x180004ff0  add     rsp, 28h
0x180004ff4  retn
```
