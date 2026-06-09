# DllCanUnloadNow

- ea: `0x1800035d0`
- end: `0x18000360f`
- name: `DllCanUnloadNow`
- size: `63`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800034b4`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x1800035e8`
- `KERNEL32!InitOnceExecuteOnce` at `0x1800035e8`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  struct Microsoft::WRL::Details::ModuleBase *v0; // rdx
  bool v1; // r9

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_180010438 = 1;
  return !Microsoft::WRL::Details::TerminateMap(
            (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
            v0,
            0,
            v1);
}

```

## disassembly

```asm
0x1800035d0  sub     rsp, 28h
0x1800035d4  xor     r9d, r9d; Context
0x1800035d7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800035de  xor     r8d, r8d; Parameter
0x1800035e1  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800035e8  call    cs:__imp_InitOnceExecuteOnce
0x1800035ee  xor     r8d, r8d; unsigned __int16 *
0x1800035f1  mov     cs:byte_180010438, 1
0x1800035f8  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x1800035ff  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180003604  movzx   eax, al
0x180003607  xor     eax, 1
0x18000360a  add     rsp, 28h
0x18000360e  retn
```
