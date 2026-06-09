# DllCanUnloadNow

- ea: `0x180008a90`
- end: `0x180008ae5`
- name: `DllCanUnloadNow`
- size: `85`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007f30`
- `0x180008a90`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008aaa`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008aaa`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180008ad5`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180008ad5`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT v0; // ebx
  struct Microsoft::WRL::Details::ModuleBase *v1; // rdx
  bool v2; // r9

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  v0 = 1;
  byte_18004AEA8 = 1;
  if ( Microsoft::WRL::Details::TerminateMap(
         (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
         v1,
         0,
         v2) )
  {
    return NdrDllCanUnloadNow(&gPFactory);
  }
  return v0;
}

```

## disassembly

```asm
0x180008a90  push    rbx
0x180008a92  sub     rsp, 20h
0x180008a96  xor     r9d, r9d; Context
0x180008a99  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180008aa0  xor     r8d, r8d; Parameter
0x180008aa3  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180008aaa  call    cs:__imp_InitOnceExecuteOnce
0x180008ab0  mov     ebx, 1
0x180008ab5  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180008abc  xor     r8d, r8d; unsigned __int16 *
0x180008abf  mov     cs:byte_18004AEA8, bl
0x180008ac5  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180008aca  test    al, al
0x180008acc  jz      short loc_180008ADD
0x180008ace  lea     rcx, gPFactory; pPSFactoryBuffer
0x180008ad5  call    cs:__imp_NdrDllCanUnloadNow
0x180008adb  mov     ebx, eax
0x180008add  mov     eax, ebx
0x180008adf  add     rsp, 20h
0x180008ae3  pop     rbx
0x180008ae4  retn
```
