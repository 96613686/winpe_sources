# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::IPropertyValue *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x18017fe10`
- end: `0x18017ffb2`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUIPropertyValue@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180180140`

## callees

- `0x18000dcd4`
- `0x180012b74`
- `0x18017b4ac`
- `0x18017db84`
- `0x18017f200`
- `0x18017fe10`
- `0x1801801e0`
- `0x180180e18`
- `0x180182ac8`
- `0x180182af8`
- `0x180182b9c`
- `0x180182fa0`
- `0x1801830c4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18017fef5`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18017fef5`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18017ff24`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18017ff24`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::IPropertyValue *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // edi
  unsigned int v3; // edx
  __int64 v4; // rdx
  bool v5; // dl
  IUnknown *v6; // rdi
  unsigned int v7; // eax
  __int64 v9; // [rsp+30h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-18h] BYREF
  HRESULT v11; // [rsp+40h] [rbp-10h]
  unsigned int v12; // [rsp+70h] [rbp+20h] BYREF
  struct IUnknown *v13; // [rsp+78h] [rbp+28h] BYREF
  struct IRpcOptions *v14; // [rsp+80h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const SetAllConstantsForInputTypeToDefaultAsyncCasualityName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    v9 = a1;
    wil::com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>::~com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>(&v9);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::IPropertyValue *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Foundation::IPropertyValue *>>(
                &v9,
                &pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::IPropertyValue *>>::CopyLocal(
                  a1 + 120,
                  v4,
                  &v13) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const SetAllConstantsForInputTypeToDefaultAsyncCasualityName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v14 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
        RpcOptionsHelper::GetRpcOptions(v13, v5, &v14);
        ppstm = 0;
        v11 = 0;
        if ( v14 && v13 )
        {
          v6 = pUnk;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
          v11 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v11 >= 0 )
            v11 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v6, 0, 0, 1u);
        }
        else
        {
          v11 = -2147467262;
        }
        v7 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v13->lpVtbl[1].QueryInterface)(
               v13,
               pUnk,
               v12);
        v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
               v7,
               v13,
               *(_QWORD *)(a1 + 128));
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<HSTRING__ *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<HSTRING__ *> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Foundation::IPropertyValue *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::IPropertyValue *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Foundation::IPropertyValue *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::IPropertyValue *>>(&ppstm);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x18017fe10  push    rbp
0x18017fe12  push    rbx
0x18017fe13  push    rdi
0x18017fe14  mov     rbp, rsp
0x18017fe17  sub     rsp, 50h
0x18017fe1b  mov     rbx, rcx
0x18017fe1e  xor     edi, edi
0x18017fe20  lea     edx, [rdi+1]
0x18017fe23  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetAllConstantsForInputTypeToDefaultAsyncCasualityName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const SetAllConstantsForInputTypeToDefaultAsyncCasualityName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18017fe28  cmp     [rbx+88h], edi
0x18017fe2e  jle     loc_18017FFA8
0x18017fe34  mov     eax, edx
0x18017fe36  lock xadd [rbx+10h], eax
0x18017fe3b  inc     eax
0x18017fe3d  cmp     eax, edx
0x18017fe3f  jnz     loc_18017FFA8
0x18017fe45  mov     [rbp+var_20], rbx
0x18017fe49  lea     rcx, [rbp+var_20]
0x18017fe4d  call    ??1?$com_ptr_t@VAsyncHRESULTPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>::~com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>(void)
0x18017fe52  nop
0x18017fe53  mov     [rbp+pUnk], rdi
0x18017fe57  mov     rcx, rbx
0x18017fe5a  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIPropertyValue@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::IPropertyValue *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18017fe5f  lea     rdx, [rbp+pUnk]
0x18017fe63  lea     rcx, [rbp+var_20]
0x18017fe67  call    ??$As@U?$IAsyncOperation@PEAUIPropertyValue@Foundation@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAUIPropertyValue@Foundation@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Foundation::IPropertyValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Foundation::IPropertyValue *>>>)
0x18017fe6c  test    eax, eax
0x18017fe6e  js      loc_18017FF8E
0x18017fe74  mov     [rbp+arg_0], 0FFFFFFFEh
0x18017fe7b  mov     ecx, [rbx+38h]
0x18017fe7e  mov     eax, [rbp+arg_0]
0x18017fe81  lock cmpxchg [rbp+arg_0], ecx
0x18017fe86  mov     [rbp+arg_8], rdi
0x18017fe8a  lea     rcx, [rbp+arg_8]
0x18017fe8e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017fe93  lea     rcx, [rbx+78h]
0x18017fe97  lea     r8, [rbp+arg_8]
0x18017fe9b  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAUIPropertyValue@Foundation@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::IPropertyValue *>>::CopyLocal(_GUID const &,void * *)
0x18017fea0  test    eax, eax
0x18017fea2  js      loc_18017FF84
0x18017fea8  mov     rcx, rbx
0x18017feab  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetAllConstantsForInputTypeToDefaultAsyncCasualityName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const SetAllConstantsForInputTypeToDefaultAsyncCasualityName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x18017feb0  mov     [rbp+arg_10], rdi
0x18017feb4  lea     rcx, [rbp+arg_10]
0x18017feb8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017febd  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x18017fec1  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x18017fec5  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18017feca  mov     [rbp+ppstm], rdi
0x18017fece  mov     [rbp+var_10], edi
0x18017fed1  cmp     [rbp+arg_10], rdi
0x18017fed5  jz      short loc_18017FF2F
0x18017fed7  cmp     [rbp+arg_8], rdi
0x18017fedb  jz      short loc_18017FF2F
0x18017fedd  mov     rdi, [rbp+pUnk]
0x18017fee1  lea     rcx, [rbp+ppstm]
0x18017fee5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017feea  lea     r8, [rbp+ppstm]; ppstm
0x18017feee  mov     edx, 1; fDeleteOnRelease
0x18017fef3  xor     ecx, ecx; hGlobal
0x18017fef5  call    cs:__imp_CreateStreamOnHGlobal
0x18017fefb  mov     [rbp+var_10], eax
0x18017fefe  test    eax, eax
0x18017ff00  js      short loc_18017FF36
0x18017ff02  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18017ff0a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x18017ff13  xor     r9d, r9d; dwDestContext
0x18017ff16  mov     r8, rdi; pUnk
0x18017ff19  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18017ff20  mov     rcx, [rbp+ppstm]; pStm
0x18017ff24  call    cs:__imp_CoMarshalInterface
0x18017ff2a  mov     [rbp+var_10], eax
0x18017ff2d  jmp     short loc_18017FF36
0x18017ff2f  mov     [rbp+var_10], 80004002h
0x18017ff36  mov     rcx, [rbp+arg_8]
0x18017ff3a  mov     rax, [rcx]
0x18017ff3d  mov     r8d, [rbp+arg_0]
0x18017ff41  mov     rdx, [rbp+pUnk]
0x18017ff45  mov     rax, [rax+18h]
0x18017ff49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017ff4e  mov     r8, [rbx+80h]
0x18017ff55  mov     rdx, [rbp+arg_8]
0x18017ff59  mov     ecx, eax
0x18017ff5b  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18017ff60  mov     edi, eax
0x18017ff62  mov     rcx, rbx
0x18017ff65  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<HSTRING__ *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18017ff6a  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<HSTRING__ *> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18017ff6f  nop
0x18017ff70  lea     rcx, [rbp+ppstm]
0x18017ff74  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAUIPropertyValue@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIPropertyValue@Foundation@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Foundation::IPropertyValue *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::IPropertyValue *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Foundation::IPropertyValue *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::IPropertyValue *>>(void)
0x18017ff79  nop
0x18017ff7a  lea     rcx, [rbp+arg_10]
0x18017ff7e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017ff83  nop
0x18017ff84  lea     rcx, [rbp+arg_8]
0x18017ff88  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017ff8d  nop
0x18017ff8e  lea     rcx, [rbp+pUnk]
0x18017ff92  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017ff97  nop
0x18017ff98  mov     rax, [rbx]
0x18017ff9b  mov     rcx, rbx
0x18017ff9e  mov     rax, [rax+10h]
0x18017ffa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017ffa7  nop
0x18017ffa8  mov     eax, edi
0x18017ffaa  add     rsp, 50h
0x18017ffae  pop     rdi
0x18017ffaf  pop     rbx
0x18017ffb0  pop     rbp
0x18017ffb1  retn
```
