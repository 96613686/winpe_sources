# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Web::UI::Interop::WebViewControl *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800526d0`
- end: `0x18005286b`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVWebViewControl@Interop@UI@Web@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180052b00`

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
- `0x18004eeb4`
- `0x1800526d0`
- `0x180052b8c`
- `0x1800535f4`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800527b5`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800527b5`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800527e4`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800527e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Web::UI::Interop::WebViewControl *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Web::UI::Interop::WebViewControl *>>(
                &v10,
                &pUnk) >= 0 )
    {
      v13 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v13, *(_DWORD *)(a1 + 56), -2);
      v14 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Web::UI::Interop::WebViewControl *>>::Localize(
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
0x1800526d0  push    rbp
0x1800526d2  push    rbx
0x1800526d3  push    rdi
0x1800526d4  mov     rbp, rsp
0x1800526d7  sub     rsp, 50h
0x1800526db  mov     rbx, rcx
0x1800526de  xor     edi, edi
0x1800526e0  lea     edx, [rdi+1]
0x1800526e3  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackOnCoreWebViewContentLoadingOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackOnCoreWebViewContentLoadingOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800526e8  cmp     [rcx+98h], edi
0x1800526ee  jle     loc_180052861
0x1800526f4  mov     eax, edx
0x1800526f6  lock xadd [rcx+10h], eax
0x1800526fb  inc     eax
0x1800526fd  cmp     eax, edx
0x1800526ff  jnz     loc_180052861
0x180052705  mov     [rbp+var_20], rcx
0x180052709  lea     rcx, [rbp+var_20]
0x18005270d  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180052712  nop
0x180052713  mov     [rbp+pUnk], rdi
0x180052717  mov     rcx, rbx
0x18005271a  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackOnFocusedElementRectAvailableOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackOnFocusedElementRectAvailableOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18005271f  lea     rdx, [rbp+pUnk]
0x180052723  lea     rcx, [rbp+var_20]
0x180052727  call    ??$As@U?$IAsyncOperation@PEAVWebViewControl@Interop@UI@Web@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAVWebViewControl@Interop@UI@Web@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Web::UI::Interop::WebViewControl *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Web::UI::Interop::WebViewControl *>>>)
0x18005272c  test    eax, eax
0x18005272e  js      loc_18005284E
0x180052734  mov     [rbp+arg_0], 0FFFFFFFEh
0x18005273b  mov     ecx, [rbx+38h]
0x18005273e  mov     eax, [rbp+arg_0]
0x180052741  lock cmpxchg [rbp+arg_0], ecx
0x180052746  mov     [rbp+arg_8], rdi
0x18005274a  lea     rcx, [rbp+arg_8]
0x18005274e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052753  lea     rcx, [rbx+78h]
0x180052757  lea     r8, [rbp+arg_8]
0x18005275b  call    ?Localize@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAVWebViewControl@Interop@UI@Web@Windows@@@Foundation@Windows@@@Internal@Windows@@IEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Web::UI::Interop::WebViewControl *>>::Localize(_GUID const &,void * *)
0x180052760  test    eax, eax
0x180052762  js      loc_180052844
0x180052768  mov     rcx, rbx
0x18005276b  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackOnCoreWebViewScriptNotifyOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackOnCoreWebViewScriptNotifyOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x180052770  mov     [rbp+arg_10], rdi
0x180052774  lea     rcx, [rbp+arg_10]
0x180052778  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005277d  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180052781  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180052785  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18005278a  mov     [rbp+ppstm], rdi
0x18005278e  mov     [rbp+var_10], edi
0x180052791  cmp     [rbp+arg_10], rdi
0x180052795  jz      short loc_1800527EF
0x180052797  cmp     [rbp+arg_8], rdi
0x18005279b  jz      short loc_1800527EF
0x18005279d  mov     rdi, [rbp+pUnk]
0x1800527a1  lea     rcx, [rbp+ppstm]
0x1800527a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800527aa  lea     r8, [rbp+ppstm]; ppstm
0x1800527ae  mov     edx, 1; fDeleteOnRelease
0x1800527b3  xor     ecx, ecx; hGlobal
0x1800527b5  call    cs:__imp_CreateStreamOnHGlobal
0x1800527bb  mov     [rbp+var_10], eax
0x1800527be  test    eax, eax
0x1800527c0  js      short loc_1800527F6
0x1800527c2  mov     [rsp+50h+mshlflags], 1; mshlflags
0x1800527ca  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x1800527d3  xor     r9d, r9d; dwDestContext
0x1800527d6  mov     r8, rdi; pUnk
0x1800527d9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800527e0  mov     rcx, [rbp+ppstm]; pStm
0x1800527e4  call    cs:__imp_CoMarshalInterface
0x1800527ea  mov     [rbp+var_10], eax
0x1800527ed  jmp     short loc_1800527F6
0x1800527ef  mov     [rbp+var_10], 80004002h
0x1800527f6  mov     rcx, [rbp+arg_8]
0x1800527fa  mov     rax, [rcx]
0x1800527fd  mov     r8d, [rbp+arg_0]
0x180052801  mov     rdx, [rbp+pUnk]
0x180052805  mov     rax, [rax+18h]
0x180052809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005280e  mov     r8, [rbx+90h]
0x180052815  mov     rdx, [rbp+arg_8]
0x180052819  mov     ecx, eax
0x18005281b  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180052820  mov     edi, eax
0x180052822  mov     rcx, rbx
0x180052825  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackOnEngagementStateChangeOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackOnEngagementStateChangeOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18005282a  call    ?TraceCompletionNotificationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackOnCoreWebViewFrameNavigationCompletedOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackOnCoreWebViewFrameNavigationCompletedOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18005282f  nop
0x180052830  lea     rcx, [rbp+ppstm]
0x180052834  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAVWebViewControl@Interop@UI@Web@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVWebViewControl@Interop@UI@Web@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Web::UI::Interop::WebViewControl *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Web::UI::Interop::WebViewControl *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Web::UI::Interop::WebViewControl *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Web::UI::Interop::WebViewControl *>>(void)
0x180052839  nop
0x18005283a  lea     rcx, [rbp+arg_10]
0x18005283e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052843  nop
0x180052844  lea     rcx, [rbp+arg_8]
0x180052848  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005284d  nop
0x18005284e  lea     rcx, [rbp+pUnk]
0x180052852  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052857  nop
0x180052858  lea     rcx, [rbp+var_20]
0x18005285c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052861  mov     eax, edi
0x180052863  add     rsp, 50h
0x180052867  pop     rdi
0x180052868  pop     rbx
0x180052869  pop     rbp
0x18005286a  retn
```
