# DllCanUnloadNow

- ea: `0x18001de10`
- end: `0x18001de7d`
- name: `DllCanUnloadNow`
- size: `109`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18001ddb0`
- `0x18001de10`
- `0x180023010`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x18001de38`
- `KERNEL32!InitOnceExecuteOnce` at `0x18001de38`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57054134>::GetImpl'::`2'::impl)
    && (InitOnceExecuteOnce(
          &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
          _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
          0,
          0),
        byte_18002F9B8 = 1,
        (*(unsigned int (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                  + 24))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)) )
  {
    LODWORD(v0) = 1;
  }
  else
  {
    return _InterlockedCompareExchange(&CWinTaskHandler::s_cInstances, 0, 0) != 0;
  }
  return v0;
}

```

## disassembly

```asm
0x18001de10  sub     rsp, 28h
0x18001de14  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57054134@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134> `wil::Feature<__WilFeatureTraits_Feature_57054134>::GetImpl(void)'::`2'::impl
0x18001de1b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::__private_IsEnabled(void)
0x18001de20  test    al, al
0x18001de22  jz      short loc_18001DE67
0x18001de24  xor     r9d, r9d; Context
0x18001de27  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001de2e  xor     r8d, r8d; Parameter
0x18001de31  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18001de38  call    cs:__imp_InitOnceExecuteOnce
0x18001de3e  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18001de45  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18001de4c  mov     cs:byte_18002F9B8, 1
0x18001de53  mov     rax, [rax+18h]
0x18001de57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de5c  test    eax, eax
0x18001de5e  jz      short loc_18001DE67
0x18001de60  mov     eax, 1
0x18001de65  jmp     short loc_18001DE78
0x18001de67  xor     eax, eax
0x18001de69  xor     ecx, ecx
0x18001de6b  lock cmpxchg cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x18001de73  mov     eax, ecx
0x18001de75  setnz   al
0x18001de78  add     rsp, 28h
0x18001de7c  retn
```
