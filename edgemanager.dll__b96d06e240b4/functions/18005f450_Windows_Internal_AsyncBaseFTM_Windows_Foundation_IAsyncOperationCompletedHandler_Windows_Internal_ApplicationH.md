# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::ApplicationHosting::ICoreApplicationBridge *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x18005f450`
- end: `0x18005f5eb`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUICoreApplicationBridge@ApplicationHosting@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005f600`

## callees

- `0x180007b90`
- `0x1800090b4`
- `0x18000b0ec`
- `0x1800233c0`
- `0x180046bf8`
- `0x180049f38`
- `0x18004c6d8`
- `0x18004c708`
- `0x18004d5e4`
- `0x180052b8c`
- `0x18005ccf0`
- `0x18005f450`
- `0x18005fe24`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18005f535`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18005f535`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18005f564`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18005f564`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::ApplicationHosting::ICoreApplicationBridge *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // edi
  unsigned int v3; // edx
  __int64 v4; // rcx
  __int64 v5; // rdx
  bool v6; // dl
  IUnknown *v7; // rdi
  unsigned int v8; // eax
  __int64 v10; // [rsp+30h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-18h] BYREF
  HRESULT v12; // [rsp+40h] [rbp-10h]
  unsigned int v13; // [rsp+70h] [rbp+20h] BYREF
  struct IUnknown *v14; // [rsp+78h] [rbp+28h] BYREF
  struct IRpcOptions *v15; // [rsp+80h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CoreWebViewComponentCallbackOnCoreWebViewContentLoadingOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(v4 + 152) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 16), v3) + 1 == v3 )
  {
    v10 = v4;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v10);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CoreWebViewComponentCallbackOnFocusedElementRectAvailableOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Internal::ApplicationHosting::ICoreApplicationBridge *>>(
                &v10,
                &pUnk) >= 0 )
    {
      v13 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v13, *(_DWORD *)(a1 + 56), -2);
      v14 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::ApplicationHosting::ICoreApplicationBridge *>>::Localize(
                  a1 + 120,
                  v5,
                  &v14) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CoreWebViewComponentCallbackOnCoreWebViewScriptNotifyOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v15 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
        RpcOptionsHelper::GetRpcOptions(v14, v6, &v15);
        ppstm = 0;
        v12 = 0;
        if ( v15 && v14 )
        {
          v7 = pUnk;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
          v12 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v12 >= 0 )
            v12 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v7, 0, 0, 1u);
        }
        else
        {
          v12 = -2147467262;
        }
        v8 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v14->lpVtbl[1].QueryInterface)(
               v14,
               pUnk,
               v13);
        v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
               v8,
               v14,
               *(_QWORD *)(a1 + 144));
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CoreWebViewComponentCallbackOnEngagementStateChangeOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CoreWebViewComponentCallbackOnCoreWebViewFrameNavigationCompletedOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Web::UI::Interop::WebViewControl *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Web::UI::Interop::WebViewControl *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Web::UI::Interop::WebViewControl *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Web::UI::Interop::WebViewControl *>>(&ppstm);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
  }
  return v2;
}

```

## disassembly

```asm
0x18005f450  push    rbp
0x18005f452  push    rbx
0x18005f453  push    rdi
0x18005f454  mov     rbp, rsp
0x18005f457  sub     rsp, 50h
0x18005f45b  mov     rbx, rcx
0x18005f45e  xor     edi, edi
0x18005f460  lea     edx, [rdi+1]
0x18005f463  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackOnCoreWebViewContentLoadingOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackOnCoreWebViewContentLoadingOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18005f468  cmp     [rcx+98h], edi
0x18005f46e  jle     loc_18005F5E1
0x18005f474  mov     eax, edx
0x18005f476  lock xadd [rcx+10h], eax
0x18005f47b  inc     eax
0x18005f47d  cmp     eax, edx
0x18005f47f  jnz     loc_18005F5E1
0x18005f485  mov     [rbp+var_20], rcx
0x18005f489  lea     rcx, [rbp+var_20]
0x18005f48d  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18005f492  nop
0x18005f493  mov     [rbp+pUnk], rdi
0x18005f497  mov     rcx, rbx
0x18005f49a  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackOnFocusedElementRectAvailableOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackOnFocusedElementRectAvailableOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18005f49f  lea     rdx, [rbp+pUnk]
0x18005f4a3  lea     rcx, [rbp+var_20]
0x18005f4a7  call    ??$As@U?$IAsyncOperation@PEAUICoreApplicationBridge@ApplicationHosting@Internal@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAUICoreApplicationBridge@ApplicationHosting@Internal@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Internal::ApplicationHosting::ICoreApplicationBridge *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Internal::ApplicationHosting::ICoreApplicationBridge *>>>)
0x18005f4ac  test    eax, eax
0x18005f4ae  js      loc_18005F5CE
0x18005f4b4  mov     [rbp+arg_0], 0FFFFFFFEh
0x18005f4bb  mov     ecx, [rbx+38h]
0x18005f4be  mov     eax, [rbp+arg_0]
0x18005f4c1  lock cmpxchg [rbp+arg_0], ecx
0x18005f4c6  mov     [rbp+arg_8], rdi
0x18005f4ca  lea     rcx, [rbp+arg_8]
0x18005f4ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f4d3  lea     rcx, [rbx+78h]
0x18005f4d7  lea     r8, [rbp+arg_8]
0x18005f4db  call    ?Localize@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAUICoreApplicationBridge@ApplicationHosting@Internal@Windows@@@Foundation@Windows@@@Internal@Windows@@IEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::ApplicationHosting::ICoreApplicationBridge *>>::Localize(_GUID const &,void * *)
0x18005f4e0  test    eax, eax
0x18005f4e2  js      loc_18005F5C4
0x18005f4e8  mov     rcx, rbx
0x18005f4eb  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackOnCoreWebViewScriptNotifyOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackOnCoreWebViewScriptNotifyOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x18005f4f0  mov     [rbp+arg_10], rdi
0x18005f4f4  lea     rcx, [rbp+arg_10]
0x18005f4f8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f4fd  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x18005f501  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x18005f505  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18005f50a  mov     [rbp+ppstm], rdi
0x18005f50e  mov     [rbp+var_10], edi
0x18005f511  cmp     [rbp+arg_10], rdi
0x18005f515  jz      short loc_18005F56F
0x18005f517  cmp     [rbp+arg_8], rdi
0x18005f51b  jz      short loc_18005F56F
0x18005f51d  mov     rdi, [rbp+pUnk]
0x18005f521  lea     rcx, [rbp+ppstm]
0x18005f525  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f52a  lea     r8, [rbp+ppstm]; ppstm
0x18005f52e  mov     edx, 1; fDeleteOnRelease
0x18005f533  xor     ecx, ecx; hGlobal
0x18005f535  call    cs:__imp_CreateStreamOnHGlobal
0x18005f53b  mov     [rbp+var_10], eax
0x18005f53e  test    eax, eax
0x18005f540  js      short loc_18005F576
0x18005f542  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18005f54a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x18005f553  xor     r9d, r9d; dwDestContext
0x18005f556  mov     r8, rdi; pUnk
0x18005f559  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18005f560  mov     rcx, [rbp+ppstm]; pStm
0x18005f564  call    cs:__imp_CoMarshalInterface
0x18005f56a  mov     [rbp+var_10], eax
0x18005f56d  jmp     short loc_18005F576
0x18005f56f  mov     [rbp+var_10], 80004002h
0x18005f576  mov     rcx, [rbp+arg_8]
0x18005f57a  mov     rax, [rcx]
0x18005f57d  mov     r8d, [rbp+arg_0]
0x18005f581  mov     rdx, [rbp+pUnk]
0x18005f585  mov     rax, [rax+18h]
0x18005f589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f58e  mov     r8, [rbx+90h]
0x18005f595  mov     rdx, [rbp+arg_8]
0x18005f599  mov     ecx, eax
0x18005f59b  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18005f5a0  mov     edi, eax
0x18005f5a2  mov     rcx, rbx
0x18005f5a5  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackOnEngagementStateChangeOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackOnEngagementStateChangeOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18005f5aa  call    ?TraceCompletionNotificationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackOnCoreWebViewFrameNavigationCompletedOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackOnCoreWebViewFrameNavigationCompletedOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18005f5af  nop
0x18005f5b0  lea     rcx, [rbp+ppstm]
0x18005f5b4  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAVWebViewControl@Interop@UI@Web@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVWebViewControl@Interop@UI@Web@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Web::UI::Interop::WebViewControl *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Web::UI::Interop::WebViewControl *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Web::UI::Interop::WebViewControl *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Web::UI::Interop::WebViewControl *>>(void)
0x18005f5b9  nop
0x18005f5ba  lea     rcx, [rbp+arg_10]
0x18005f5be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f5c3  nop
0x18005f5c4  lea     rcx, [rbp+arg_8]
0x18005f5c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f5cd  nop
0x18005f5ce  lea     rcx, [rbp+pUnk]
0x18005f5d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f5d7  nop
0x18005f5d8  lea     rcx, [rbp+var_20]
0x18005f5dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f5e1  mov     eax, edi
0x18005f5e3  add     rsp, 50h
0x18005f5e7  pop     rdi
0x18005f5e8  pop     rbx
0x18005f5e9  pop     rbp
0x18005f5ea  retn
```
