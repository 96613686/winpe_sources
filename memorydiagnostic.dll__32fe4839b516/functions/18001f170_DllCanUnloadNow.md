# DllCanUnloadNow

- ea: `0x18001f170`
- end: `0x18001f1e7`
- name: `DllCanUnloadNow`
- size: `119`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18001f10c`
- `0x18001f170`
- `0x180024010`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x18001f19c`
- `KERNEL32!InitOnceExecuteOnce` at `0x18001f19c`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT v0; // ebx

  v0 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_57054134>::GetImpl'::`2'::impl) )
  {
    InitOnceExecuteOnce(
      &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
      _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_180030E68 = 1;
    if ( (*(unsigned int (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                   + 24))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_) )
      return 1;
  }
  LOBYTE(v0) = _InterlockedCompareExchange(&CWinTaskHandler::s_cInstances, 0, 0) != 0;
  return v0;
}

```

## disassembly

```asm
0x18001f170  push    rbx
0x18001f172  sub     rsp, 20h
0x18001f176  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57054134@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134> `wil::Feature<__WilFeatureTraits_Feature_57054134>::GetImpl(void)'::`2'::impl
0x18001f17d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::__private_IsEnabled(void)
0x18001f182  xor     ebx, ebx
0x18001f184  test    al, al
0x18001f186  jz      short loc_18001F1D1
0x18001f188  xor     r9d, r9d; Context
0x18001f18b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001f192  xor     r8d, r8d; Parameter
0x18001f195  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18001f19c  call    cs:__imp_InitOnceExecuteOnce
0x18001f1a3  nop     dword ptr [rax+rax+00h]
0x18001f1a8  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18001f1af  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18001f1b6  mov     cs:byte_180030E68, 1
0x18001f1bd  mov     rax, [rax+18h]
0x18001f1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1c6  test    eax, eax
0x18001f1c8  jz      short loc_18001F1D1
0x18001f1ca  mov     ebx, 1
0x18001f1cf  jmp     short loc_18001F1DE
0x18001f1d1  xor     eax, eax
0x18001f1d3  lock cmpxchg cs:?s_cInstances@CWinTaskHandler@@0JC, ebx; long volatile CWinTaskHandler::s_cInstances
0x18001f1db  setnz   bl
0x18001f1de  mov     eax, ebx
0x18001f1e0  add     rsp, 20h
0x18001f1e4  pop     rbx
0x18001f1e5  retn
```
