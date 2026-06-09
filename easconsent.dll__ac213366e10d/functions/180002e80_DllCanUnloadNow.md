# DllCanUnloadNow

- ea: `0x180002e80`
- end: `0x180002f18`
- name: `DllCanUnloadNow`
- size: `152`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002d64`
- `0x180002e80`
- `0x180004010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180002ece`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180002ece`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180002e98`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180002eee`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180002e98`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180002eee`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT CanUnloadNow; // ecx
  struct Microsoft::WRL::Details::ModuleBase *v1; // rdx

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_180007688 = 1;
  if ( (*(unsigned int (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                              + 24LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_) )
    return 1;
  CanUnloadNow = NdrDllCanUnloadNow(&gPFactory);
  if ( !CanUnloadNow )
  {
    InitOnceExecuteOnce(
      &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
      _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_180007688 = 1;
    return !Microsoft::WRL::Details::TerminateMap(
              (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
              v1,
              0);
  }
  return CanUnloadNow;
}

```

## disassembly

```asm
0x180002e80  sub     rsp, 28h
0x180002e84  xor     r9d, r9d; Context
0x180002e87  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180002e8e  xor     r8d, r8d; Parameter
0x180002e91  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180002e98  call    cs:__imp_InitOnceExecuteOnce
0x180002e9e  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180002ea5  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180002eac  mov     cs:byte_180007688, 1
0x180002eb3  mov     rax, [rax+18h]
0x180002eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ebc  test    eax, eax
0x180002ebe  jz      short loc_180002EC7
0x180002ec0  mov     ecx, 1
0x180002ec5  jmp     short loc_180002F11
0x180002ec7  lea     rcx, gPFactory; pPSFactoryBuffer
0x180002ece  call    cs:__imp_NdrDllCanUnloadNow
0x180002ed4  mov     ecx, eax
0x180002ed6  test    eax, eax
0x180002ed8  jnz     short loc_180002F11
0x180002eda  xor     r9d, r9d; Context
0x180002edd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180002ee4  xor     r8d, r8d; Parameter
0x180002ee7  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180002eee  call    cs:__imp_InitOnceExecuteOnce
0x180002ef4  xor     r8d, r8d; unsigned __int16 *
0x180002ef7  mov     cs:byte_180007688, 1
0x180002efe  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180002f05  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180002f0a  xor     ecx, ecx
0x180002f0c  test    al, al
0x180002f0e  setz    cl
0x180002f11  mov     eax, ecx
0x180002f13  add     rsp, 28h
0x180002f17  retn
```
