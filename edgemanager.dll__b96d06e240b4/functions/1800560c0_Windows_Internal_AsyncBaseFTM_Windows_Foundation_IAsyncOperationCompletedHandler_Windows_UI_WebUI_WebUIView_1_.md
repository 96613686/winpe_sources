# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::WebUI::WebUIView *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800560c0`
- end: `0x18005625b`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVWebUIView@WebUI@UI@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180056270`

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
- `0x180055480`
- `0x1800560c0`
- `0x1800564a4`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800561a5`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800561a5`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800561d4`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800561d4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::WebUI::WebUIView *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::UI::WebUI::WebUIView *>>(
                &v10,
                &pUnk) >= 0 )
    {
      v13 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v13, *(_DWORD *)(a1 + 56), -2);
      v14 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::WebUI::WebUIView *>>::Localize(
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
0x1800560c0  push    rbp
0x1800560c2  push    rbx
0x1800560c3  push    rdi
0x1800560c4  mov     rbp, rsp
0x1800560c7  sub     rsp, 50h
0x1800560cb  mov     rbx, rcx
0x1800560ce  xor     edi, edi
0x1800560d0  lea     edx, [rdi+1]
0x1800560d3  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackOnCoreWebViewContentLoadingOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackOnCoreWebViewContentLoadingOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800560d8  cmp     [rcx+98h], edi
0x1800560de  jle     loc_180056251
0x1800560e4  mov     eax, edx
0x1800560e6  lock xadd [rcx+10h], eax
0x1800560eb  inc     eax
0x1800560ed  cmp     eax, edx
0x1800560ef  jnz     loc_180056251
0x1800560f5  mov     [rbp+var_20], rcx
0x1800560f9  lea     rcx, [rbp+var_20]
0x1800560fd  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180056102  nop
0x180056103  mov     [rbp+pUnk], rdi
0x180056107  mov     rcx, rbx
0x18005610a  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackOnFocusedElementRectAvailableOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackOnFocusedElementRectAvailableOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18005610f  lea     rdx, [rbp+pUnk]
0x180056113  lea     rcx, [rbp+var_20]
0x180056117  call    ??$As@U?$IAsyncOperation@PEAVWebUIView@WebUI@UI@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAVWebUIView@WebUI@UI@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::UI::WebUI::WebUIView *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::UI::WebUI::WebUIView *>>>)
0x18005611c  test    eax, eax
0x18005611e  js      loc_18005623E
0x180056124  mov     [rbp+arg_0], 0FFFFFFFEh
0x18005612b  mov     ecx, [rbx+38h]
0x18005612e  mov     eax, [rbp+arg_0]
0x180056131  lock cmpxchg [rbp+arg_0], ecx
0x180056136  mov     [rbp+arg_8], rdi
0x18005613a  lea     rcx, [rbp+arg_8]
0x18005613e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180056143  lea     rcx, [rbx+78h]
0x180056147  lea     r8, [rbp+arg_8]
0x18005614b  call    ?Localize@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAVWebUIView@WebUI@UI@Windows@@@Foundation@Windows@@@Internal@Windows@@IEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::WebUI::WebUIView *>>::Localize(_GUID const &,void * *)
0x180056150  test    eax, eax
0x180056152  js      loc_180056234
0x180056158  mov     rcx, rbx
0x18005615b  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackOnCoreWebViewScriptNotifyOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackOnCoreWebViewScriptNotifyOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x180056160  mov     [rbp+arg_10], rdi
0x180056164  lea     rcx, [rbp+arg_10]
0x180056168  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005616d  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180056171  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180056175  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18005617a  mov     [rbp+ppstm], rdi
0x18005617e  mov     [rbp+var_10], edi
0x180056181  cmp     [rbp+arg_10], rdi
0x180056185  jz      short loc_1800561DF
0x180056187  cmp     [rbp+arg_8], rdi
0x18005618b  jz      short loc_1800561DF
0x18005618d  mov     rdi, [rbp+pUnk]
0x180056191  lea     rcx, [rbp+ppstm]
0x180056195  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005619a  lea     r8, [rbp+ppstm]; ppstm
0x18005619e  mov     edx, 1; fDeleteOnRelease
0x1800561a3  xor     ecx, ecx; hGlobal
0x1800561a5  call    cs:__imp_CreateStreamOnHGlobal
0x1800561ab  mov     [rbp+var_10], eax
0x1800561ae  test    eax, eax
0x1800561b0  js      short loc_1800561E6
0x1800561b2  mov     [rsp+50h+mshlflags], 1; mshlflags
0x1800561ba  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x1800561c3  xor     r9d, r9d; dwDestContext
0x1800561c6  mov     r8, rdi; pUnk
0x1800561c9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800561d0  mov     rcx, [rbp+ppstm]; pStm
0x1800561d4  call    cs:__imp_CoMarshalInterface
0x1800561da  mov     [rbp+var_10], eax
0x1800561dd  jmp     short loc_1800561E6
0x1800561df  mov     [rbp+var_10], 80004002h
0x1800561e6  mov     rcx, [rbp+arg_8]
0x1800561ea  mov     rax, [rcx]
0x1800561ed  mov     r8d, [rbp+arg_0]
0x1800561f1  mov     rdx, [rbp+pUnk]
0x1800561f5  mov     rax, [rax+18h]
0x1800561f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561fe  mov     r8, [rbx+90h]
0x180056205  mov     rdx, [rbp+arg_8]
0x180056209  mov     ecx, eax
0x18005620b  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180056210  mov     edi, eax
0x180056212  mov     rcx, rbx
0x180056215  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackOnEngagementStateChangeOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackOnEngagementStateChangeOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18005621a  call    ?TraceCompletionNotificationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackOnCoreWebViewFrameNavigationCompletedOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackOnCoreWebViewFrameNavigationCompletedOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18005621f  nop
0x180056220  lea     rcx, [rbp+ppstm]
0x180056224  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAVWebViewControl@Interop@UI@Web@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVWebViewControl@Interop@UI@Web@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Web::UI::Interop::WebViewControl *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Web::UI::Interop::WebViewControl *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Web::UI::Interop::WebViewControl *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Web::UI::Interop::WebViewControl *>>(void)
0x180056229  nop
0x18005622a  lea     rcx, [rbp+arg_10]
0x18005622e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180056233  nop
0x180056234  lea     rcx, [rbp+arg_8]
0x180056238  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005623d  nop
0x18005623e  lea     rcx, [rbp+pUnk]
0x180056242  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180056247  nop
0x180056248  lea     rcx, [rbp+var_20]
0x18005624c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180056251  mov     eax, edi
0x180056253  add     rsp, 50h
0x180056257  pop     rdi
0x180056258  pop     rbx
0x180056259  pop     rbp
0x18005625a  retn
```
