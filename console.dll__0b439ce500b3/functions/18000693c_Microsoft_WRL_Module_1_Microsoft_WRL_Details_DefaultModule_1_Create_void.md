# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)

- ea: `0x18000693c`
- end: `0x180006974`
- name: `?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ`
- size: `56`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001160`
- `0x180006d80`
- `0x180006db0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006954`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006954`

## pseudocode

```c
__int64 *Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create()
{
  __int64 *result; // rax

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    `Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
    0,
    0);
  result = &Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_;
  byte_180023978 = 1;
  return result;
}

```

## disassembly

```asm
0x18000693c  sub     rsp, 28h
0x180006940  xor     r9d, r9d; Context
0x180006943  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@45@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000694a  xor     r8d, r8d; Parameter
0x18000694d  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180006954  call    cs:__imp_InitOnceExecuteOnce
0x18000695b  nop     dword ptr [rax+rax+00h]
0x180006960  lea     rax, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006967  mov     cs:byte_180023978, 1
0x18000696e  add     rsp, 28h
0x180006972  retn
```
