# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)

- ea: `0x1800011c0`
- end: `0x1800011f1`
- name: `?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001110`
- `0x180001150`
- `0x180004250`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800011d8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800011d8`

## pseudocode

```c
int *Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create()
{
  int *result; // rax

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    `Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
    0,
    0);
  result = &Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_;
  byte_18000ADF8 = 1;
  return result;
}

```

## disassembly

```asm
0x1800011c0  sub     rsp, 28h
0x1800011c4  xor     r9d, r9d; Context
0x1800011c7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@45@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800011ce  xor     r8d, r8d; Parameter
0x1800011d1  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800011d8  call    cs:__imp_InitOnceExecuteOnce
0x1800011de  lea     rax, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800011e5  mov     cs:byte_18000ADF8, 1
0x1800011ec  add     rsp, 28h
0x1800011f0  retn
```
