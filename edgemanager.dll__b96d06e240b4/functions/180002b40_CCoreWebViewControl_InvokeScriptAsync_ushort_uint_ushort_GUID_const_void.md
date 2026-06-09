# CCoreWebViewControl::InvokeScriptAsync(ushort *,uint,ushort * *,_GUID const &,void * *)

- ea: `0x180002b40`
- end: `0x180002f87`
- name: `?InvokeScriptAsync@CCoreWebViewControl@@UEAAJPEAGIPEAPEAGAEBU_GUID@@PEAPEAX@Z`
- size: `1095`
- prototype: `__int64 __fastcall(CCoreWebViewControl *__hidden this, unsigned __int16 *, unsigned int, unsigned __int16 **, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180002a50`
- `0x180002b40`
- `0x18000b0ec`
- `0x1800154cc`
- `0x18001eaac`
- `0x18002b5e4`
- `0x180035b88`
- `0x180035ba8`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180002d76`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180002d76`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180002c26`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180002c26`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002dd3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002dd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CCoreWebViewControl::InvokeScriptAsync(
        CCoreWebViewControl *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 **a4,
        const struct _GUID *a5,
        void **a6)
{
  __int64 v10; // rcx
  _QWORD *v12; // rbx
  _QWORD *v13; // rax
  const char *v14; // r9
  _QWORD *v15; // rsi
  LPUNKNOWN v16; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rax
  __int64 v18; // rcx
  LPUNKNOWN v19; // rcx
  HRESULT Instance; // ebx
  __int64 v21; // rsi
  __int64 (__fastcall *v22)(__int64, unsigned __int16 *, _QWORD, unsigned __int16 **); // r13
  __int64 v23; // rcx
  int v24; // eax
  unsigned int v25; // esi
  int v26; // eax
  int v27; // eax
  __int64 v28; // rcx
  int ppv; // [rsp+20h] [rbp-48h]
  LPUNKNOWN ppunkMarshal; // [rsp+40h] [rbp-28h] BYREF
  HRESULT (__stdcall *v31)(IUnknown *, const IID *const, void **); // [rsp+48h] [rbp-20h]
  _QWORD *v32; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  __int64 v34; // [rsp+B0h] [rbp+48h] BYREF

  v34 = 0;
  v32 = 0;
  if ( *((_QWORD *)this + 5) )
  {
    v12 = 0;
    v13 = operator new(0xF8u, (const struct std::nothrow_t *)&std::nothrow);
    v15 = v13;
    if ( v13 )
    {
      *v13 = &Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable';
      v13[2] = 0;
      v13[3] = 0;
      *((_DWORD *)v13 + 8) = 0;
      v13[5] = 0;
      v13[6] = 0;
      *((_DWORD *)v13 + 14) = -1;
      *((_DWORD *)v13 + 15) = 0;
      *((_DWORD *)v13 + 16) = 1;
      v13[9] = 0;
      v13[12] = &Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CoreWebViewComponentCallbackLogMessageOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CoreWebViewComponentCallbackLogMessageOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
      v13[15] = 0;
      ppunkMarshal = 0;
      if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
      {
        v16 = ppunkMarshal;
        QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
        v31 = QueryInterface;
        v18 = v15[15];
        if ( v18 )
        {
          v15[15] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          QueryInterface = v31;
        }
        ((void (__fastcall *)(LPUNKNOWN, GUID *, _QWORD *))QueryInterface)(
          v16,
          &GUID_00000003_0000_0000_c000_000000000046,
          v15 + 15);
      }
      v19 = ppunkMarshal;
      if ( ppunkMarshal )
      {
        ppunkMarshal = 0;
        ((void (__fastcall *)(LPUNKNOWN))v19->lpVtbl->Release)(v19);
      }
      Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<IInspectable *>,Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,Windows::UI::Core::IDispatchedHandler>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Foundation::IAsyncOperation<IInspectable *>,Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,Windows::UI::Core::IDispatchedHandler>>::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<IInspectable *>,Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,Windows::UI::Core::IDispatchedHandler>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Foundation::IAsyncOperation<IInspectable *>,Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,Windows::UI::Core::IDispatchedHandler>>(v15 + 16);
      v15[20] = 1;
      *v15 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>::`vftable';
      v15[10] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>::`vftable'{for `IWeakReferenceSource'};
      v15[11] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>'};
      v15[12] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>>'};
      v15[16] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>>'};
      v15[17] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'};
      v15[18] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::UI::Core::IDispatchedHandler>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *v15 = &CCoreWebViewTaskHelpers::TCoreWebViewAsyncOperationHelper<HSTRING__ *,HSTRING__ *>::`vftable';
      v15[10] = &CCoreWebViewTaskHelpers::TCoreWebViewAsyncOperationHelper<HSTRING__ *,HSTRING__ *>::`vftable'{for `IWeakReferenceSource'};
      v15[11] = &CCoreWebViewTaskHelpers::TCoreWebViewAsyncOperationHelper<HSTRING__ *,HSTRING__ *>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>'};
      v15[12] = &CCoreWebViewTaskHelpers::TCoreWebViewAsyncOperationHelper<HSTRING__ *,HSTRING__ *>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>>'};
      v15[16] = &CCoreWebViewTaskHelpers::TCoreWebViewAsyncOperationHelper<HSTRING__ *,HSTRING__ *>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>>'};
      v15[17] = &CCoreWebViewTaskHelpers::TCoreWebViewAsyncOperationHelper<HSTRING__ *,HSTRING__ *>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'};
      v15[18] = &CCoreWebViewTaskHelpers::TCoreWebViewAsyncOperationHelper<HSTRING__ *,HSTRING__ *>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::UI::Core::IDispatchedHandler>'};
      InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v15 + 22), 0, 0);
      v15[27] = &Windows::Internal::GitPtrImpl<Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperation<HSTRING__ *>>>::`vftable';
      *((_DWORD *)v15 + 56) = 0;
      if ( qword_1800B6E08 )
      {
        Instance = 0;
        _InterlockedIncrement(&Windows::Internal::Details::_git);
      }
      else
      {
        ppunkMarshal = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppunkMarshal);
        Instance = CoCreateInstance(
                     &CLSID_StdGlobalInterfaceTable,
                     0,
                     1u,
                     &GUID_00000146_0000_0000_c000_000000000046,
                     (LPVOID *)&ppunkMarshal);
        if ( Instance >= 0 )
        {
          if ( !_InterlockedCompareExchange64(&qword_1800B6E08, (signed __int64)ppunkMarshal, 0) )
            ppunkMarshal = 0;
          _InterlockedIncrement(&Windows::Internal::Details::_git);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppunkMarshal);
      }
      *((_DWORD *)v15 + 57) = Instance;
      v15[27] = &Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperation<HSTRING__ *>>::`vftable';
      v15[29] = 0;
      v15[30] = 0;
      v12 = v15;
    }
    v32 = v12;
    if ( !v12 )
      wil::details::in1diag3::_FailFast_NullAlloc(
        retaddr,
        (void *)0x2FC,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
        v14);
    v21 = *((_QWORD *)this + 5);
    v22 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, unsigned __int16 **))(*(_QWORD *)v21 + 224LL);
    v23 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = v22(v21, a2, a3, a4);
    v25 = v24;
    if ( v24 >= 0 )
    {
      v26 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD))(*v12 + 160LL))(v12, v34, *((_QWORD *)this + 10));
      if ( v26 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x2FF,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
          (const char *)(unsigned int)v26,
          (int)&GUID_3e1fe603_f897_5263_b328_0806426b8a79);
      v27 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v12)(v12, a5, a6);
      if ( v27 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x300,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
          (const char *)(unsigned int)v27,
          (int)&GUID_3e1fe603_f897_5263_b328_0806426b8a79);
      (*(void (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
      v28 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2FE,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
        (const char *)(unsigned int)v24,
        (int)&GUID_3e1fe603_f897_5263_b328_0806426b8a79);
      (*(void (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
      Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindowStatic>::InternalRelease(&v34);
      return v25;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F7,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)0x8007139FLL,
      ppv);
    v10 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return 2147947423LL;
  }
}

```

## disassembly

```asm
0x180002b40  push    rbp
0x180002b42  push    rbx
0x180002b43  push    rsi
0x180002b44  push    rdi
0x180002b45  push    r12
0x180002b47  push    r13
0x180002b49  push    r14
0x180002b4b  push    r15
0x180002b4d  mov     rbp, rsp
0x180002b50  sub     rsp, 68h
0x180002b54  mov     r14, r9
0x180002b57  mov     r15d, r8d
0x180002b5a  mov     r12, rdx
0x180002b5d  mov     rdi, rcx
0x180002b60  xor     r13d, r13d
0x180002b63  mov     [rbp+arg_0], r13
0x180002b67  mov     [rbp+var_18], r13
0x180002b6b  cmp     [rcx+28h], r13
0x180002b6f  jnz     short loc_180002BB1
0x180002b71  mov     rcx, [rbp+40h]; this
0x180002b75  mov     r9d, 8007139Fh; char *
0x180002b7b  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180002b82  mov     edx, 2F7h; void *
0x180002b87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002b8c  nop
0x180002b8d  mov     rcx, [rbp+arg_0]
0x180002b91  test    rcx, rcx
0x180002b94  jz      short loc_180002BA7
0x180002b96  mov     [rbp+arg_0], r13
0x180002b9a  mov     rdx, [rcx]
0x180002b9d  mov     rax, [rdx+10h]
0x180002ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ba6  nop
0x180002ba7  mov     eax, 8007139Fh
0x180002bac  jmp     loc_180002F76
0x180002bb1  mov     rbx, r13
0x180002bb4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002bbb  mov     ecx, 0F8h; unsigned __int64
0x180002bc0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002bc5  mov     rsi, rax
0x180002bc8  test    rax, rax
0x180002bcb  jz      loc_180002E29
0x180002bd1  lea     rax, ??_7?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?WebViewTaskAsyncOpDefaultName@CCoreWebViewTaskHelpers@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@6B@; const Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'
0x180002bd8  mov     [rsi], rax
0x180002bdb  mov     [rsi+10h], r13
0x180002bdf  mov     [rsi+18h], r13
0x180002be3  mov     [rsi+20h], r13d
0x180002be7  mov     [rsi+28h], r13
0x180002beb  mov     [rsi+30h], r13
0x180002bef  mov     dword ptr [rsi+38h], 0FFFFFFFFh
0x180002bf6  mov     [rsi+3Ch], r13d
0x180002bfa  mov     dword ptr [rsi+40h], 1
0x180002c01  mov     [rsi+48h], r13
0x180002c05  lea     rax, ??_7?$AsyncBaseWithProgressFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackLogMessageOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackLogMessageOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackLogMessageOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackLogMessageOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x180002c0c  mov     [rsi+60h], rax
0x180002c10  mov     qword ptr [rsi+78h], 0
0x180002c18  mov     [rbp+ppunkMarshal], 0
0x180002c20  lea     rdx, [rbp+ppunkMarshal]; ppunkMarshal
0x180002c24  xor     ecx, ecx; punkOuter
0x180002c26  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180002c2c  test    eax, eax
0x180002c2e  js      short loc_180002C73
0x180002c30  mov     rbx, [rbp+ppunkMarshal]
0x180002c34  mov     rax, [rbx]
0x180002c37  mov     rax, [rax]
0x180002c3a  mov     [rbp+var_20], rax
0x180002c3e  mov     rcx, [rsi+78h]
0x180002c42  test    rcx, rcx
0x180002c45  jz      short loc_180002C5F
0x180002c47  mov     qword ptr [rsi+78h], 0
0x180002c4f  mov     rdx, [rcx]
0x180002c52  mov     rax, [rdx+10h]
0x180002c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c5b  mov     rax, [rbp+var_20]
0x180002c5f  lea     r8, [rsi+78h]
0x180002c63  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180002c6a  mov     rcx, rbx
0x180002c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c72  nop
0x180002c73  mov     rcx, [rbp+ppunkMarshal]
0x180002c77  xor     r13d, r13d
0x180002c7a  test    rcx, rcx
0x180002c7d  jz      short loc_180002C90
0x180002c7f  mov     [rbp+ppunkMarshal], r13
0x180002c83  mov     rax, [rcx]
0x180002c86  mov     rax, [rax+10h]
0x180002c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c8f  nop
0x180002c90  lea     rcx, [rsi+80h]
0x180002c97  call    ??0?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$IAsyncOperation@PEAUIInspectable@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIInspectable@@@56@UIDispatchedHandler@Core@UI@6@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@U?$IAsyncOperation@PEAUIInspectable@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIInspectable@@@78@UIDispatchedHandler@Core@UI@8@@234@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<IInspectable *>,Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,Windows::UI::Core::IDispatchedHandler>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Foundation::IAsyncOperation<IInspectable *>,Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,Windows::UI::Core::IDispatchedHandler>>::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<IInspectable *>,Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,Windows::UI::Core::IDispatchedHandler>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Foundation::IAsyncOperation<IInspectable *>,Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,Windows::UI::Core::IDispatchedHandler>>(void)
0x180002c9c  mov     qword ptr [rsi+0A0h], 1
0x180002ca7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?WebViewTaskAsyncOpDefaultName@CCoreWebViewTaskHelpers@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@23@UIAgileObject@@VFtmBase@23@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@89@UIDispatchedHandler@Core@UI@9@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>::`vftable'
0x180002cae  mov     [rsi], rax
0x180002cb1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?WebViewTaskAsyncOpDefaultName@CCoreWebViewTaskHelpers@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@23@UIAgileObject@@VFtmBase@23@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@89@UIDispatchedHandler@Core@UI@9@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>::`vftable'{for `IWeakReferenceSource'}
0x180002cb8  mov     [rsi+50h], rax
0x180002cbc  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?WebViewTaskAsyncOpDefaultName@CCoreWebViewTaskHelpers@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@23@UIAgileObject@@VFtmBase@23@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@89@UIDispatchedHandler@Core@UI@9@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAgileObject@@VFtmBase@23@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@78@UIDispatchedHandler@Core@UI@8@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>'}
0x180002cc3  mov     [rsi+58h], rax
0x180002cc7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?WebViewTaskAsyncOpDefaultName@CCoreWebViewTaskHelpers@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@23@UIAgileObject@@VFtmBase@23@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@89@UIDispatchedHandler@Core@UI@9@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@78@UIDispatchedHandler@Core@UI@8@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>>'}
0x180002cce  mov     [rsi+60h], rax
0x180002cd2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?WebViewTaskAsyncOpDefaultName@CCoreWebViewTaskHelpers@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@23@UIAgileObject@@VFtmBase@23@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@89@UIDispatchedHandler@Core@UI@9@@WRL@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@56@UIDispatchedHandler@Core@UI@6@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@78@UIDispatchedHandler@Core@UI@8@@234@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>>'}
0x180002cd9  mov     [rsi+80h], rax
0x180002ce0  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?WebViewTaskAsyncOpDefaultName@CCoreWebViewTaskHelpers@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@23@UIAgileObject@@VFtmBase@23@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@89@UIDispatchedHandler@Core@UI@9@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'}
0x180002ce7  mov     [rsi+88h], rax
0x180002cee  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?WebViewTaskAsyncOpDefaultName@CCoreWebViewTaskHelpers@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@23@UIAgileObject@@VFtmBase@23@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@89@UIDispatchedHandler@Core@UI@9@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIDispatchedHandler@Core@UI@Windows@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::UI::Core::IDispatchedHandler>'}
0x180002cf5  mov     [rsi+90h], rax
0x180002cfc  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002d03  test    rcx, rcx
0x180002d06  jz      short loc_180002D15
0x180002d08  mov     rax, [rcx]
0x180002d0b  mov     rax, [rax+8]
0x180002d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d14  nop
0x180002d15  lea     rax, ??_7?$TCoreWebViewAsyncOperationHelper@PEAUHSTRING__@@PEAU1@@CCoreWebViewTaskHelpers@@6B@; const CCoreWebViewTaskHelpers::TCoreWebViewAsyncOperationHelper<HSTRING__ *,HSTRING__ *>::`vftable'
0x180002d1c  mov     [rsi], rax
0x180002d1f  lea     rax, ??_7?$TCoreWebViewAsyncOperationHelper@PEAUHSTRING__@@PEAU1@@CCoreWebViewTaskHelpers@@6BIWeakReferenceSource@@@; const CCoreWebViewTaskHelpers::TCoreWebViewAsyncOperationHelper<HSTRING__ *,HSTRING__ *>::`vftable'{for `IWeakReferenceSource'}
0x180002d26  mov     [rsi+50h], rax
0x180002d2a  lea     rax, ??_7?$TCoreWebViewAsyncOperationHelper@PEAUHSTRING__@@PEAU1@@CCoreWebViewTaskHelpers@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAgileObject@@VFtmBase@23@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@78@UIDispatchedHandler@Core@UI@8@@Details@WRL@Microsoft@@@; const CCoreWebViewTaskHelpers::TCoreWebViewAsyncOperationHelper<HSTRING__ *,HSTRING__ *>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAgileObject,Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>'}
0x180002d31  mov     [rsi+58h], rax
0x180002d35  lea     rax, ??_7?$TCoreWebViewAsyncOperationHelper@PEAUHSTRING__@@PEAU1@@CCoreWebViewTaskHelpers@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@78@UIDispatchedHandler@Core@UI@8@@Details@23@@Details@WRL@Microsoft@@@; const CCoreWebViewTaskHelpers::TCoreWebViewAsyncOperationHelper<HSTRING__ *,HSTRING__ *>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>>'}
0x180002d3c  mov     [rsi+60h], rax
0x180002d40  lea     rax, ??_7?$TCoreWebViewAsyncOperationHelper@PEAUHSTRING__@@PEAU1@@CCoreWebViewTaskHelpers@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@56@UIDispatchedHandler@Core@UI@6@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@78@UIDispatchedHandler@Core@UI@8@@234@@Details@WRL@Microsoft@@@; const CCoreWebViewTaskHelpers::TCoreWebViewAsyncOperationHelper<HSTRING__ *,HSTRING__ *>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::UI::Core::IDispatchedHandler>>'}
0x180002d47  mov     [rsi+80h], rax
0x180002d4e  lea     rax, ??_7?$TCoreWebViewAsyncOperationHelper@PEAUHSTRING__@@PEAU1@@CCoreWebViewTaskHelpers@@6B?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@@; const CCoreWebViewTaskHelpers::TCoreWebViewAsyncOperationHelper<HSTRING__ *,HSTRING__ *>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'}
0x180002d55  mov     [rsi+88h], rax
0x180002d5c  lea     rax, ??_7?$TCoreWebViewAsyncOperationHelper@PEAUHSTRING__@@PEAU1@@CCoreWebViewTaskHelpers@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIDispatchedHandler@Core@UI@Windows@@@Details@WRL@Microsoft@@@; const CCoreWebViewTaskHelpers::TCoreWebViewAsyncOperationHelper<HSTRING__ *,HSTRING__ *>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::UI::Core::IDispatchedHandler>'}
0x180002d63  mov     [rsi+90h], rax
0x180002d6a  lea     rcx, [rsi+0B0h]; lpCriticalSection
0x180002d71  xor     r8d, r8d; Flags
0x180002d74  xor     edx, edx; dwSpinCount
0x180002d76  call    cs:__imp_InitializeCriticalSectionEx
0x180002d7c  lea     rax, ??_7?$GitPtrImpl@V?$GitPtrSupportsAgile@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::GitPtrImpl<Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperation<HSTRING__ *>>>::`vftable'
0x180002d83  mov     [rsi+0D8h], rax
0x180002d8a  mov     [rsi+0E0h], r13d
0x180002d91  cmp     cs:qword_1800B6E08, 0
0x180002d99  jz      short loc_180002DA7
0x180002d9b  mov     ebx, r13d
0x180002d9e  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x180002da5  jmp     short loc_180002E04
0x180002da7  mov     [rbp+ppunkMarshal], r13
0x180002dab  lea     rcx, [rbp+ppunkMarshal]
0x180002daf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180002db4  lea     rax, [rbp+ppunkMarshal]
0x180002db8  mov     [rsp+68h+ppv], rax; ppv
0x180002dbd  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180002dc4  xor     edx, edx; pUnkOuter
0x180002dc6  mov     r8d, 1; dwClsContext
0x180002dcc  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180002dd3  call    cs:__imp_CoCreateInstance
0x180002dd9  mov     ebx, eax
0x180002ddb  test    eax, eax
0x180002ddd  js      short loc_180002DFB
0x180002ddf  mov     rcx, [rbp+ppunkMarshal]
0x180002de3  xor     eax, eax
0x180002de5  lock cmpxchg cs:qword_1800B6E08, rcx
0x180002dee  jnz     short loc_180002DF4
0x180002df0  mov     [rbp+ppunkMarshal], r13
0x180002df4  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x180002dfb  lea     rcx, [rbp+ppunkMarshal]
0x180002dff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180002e04  mov     [rsi+0E4h], ebx
0x180002e0a  lea     rax, ??_7?$GitPtrSupportsAgile@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@Internal@Windows@@6B@; const Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperation<HSTRING__ *>>::`vftable'
0x180002e11  mov     [rsi+0D8h], rax
0x180002e18  mov     [rsi+0E8h], r13
0x180002e1f  mov     [rsi+0F0h], r13
0x180002e26  mov     rbx, rsi
0x180002e29  mov     [rbp+var_18], rbx
0x180002e2d  mov     rcx, [rbp+40h]; this
0x180002e31  test    rbx, rbx
0x180002e34  jnz     short loc_180002E48
0x180002e36  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180002e3d  mov     edx, 2FCh; void *
0x180002e42  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x180002e48  mov     rsi, [rdi+28h]
0x180002e4c  mov     rax, [rsi]
0x180002e4f  mov     r13, [rax+0E0h]
0x180002e56  mov     rcx, [rbp+arg_0]
0x180002e5a  test    rcx, rcx
0x180002e5d  jz      short loc_180002E74
0x180002e5f  mov     [rbp+arg_0], 0
0x180002e67  mov     rax, [rcx]
0x180002e6a  mov     rax, [rax+10h]
0x180002e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e73  nop
0x180002e74  lea     rax, [rbp+arg_0]
0x180002e78  mov     [rsp+68h+var_40], rax
0x180002e7d  lea     rax, _GUID_3e1fe603_f897_5263_b328_0806426b8a79
0x180002e84  mov     [rsp+68h+ppv], rax; int
0x180002e89  mov     r9, r14
0x180002e8c  mov     r8d, r15d
0x180002e8f  mov     rdx, r12
0x180002e92  mov     rcx, rsi
0x180002e95  mov     rax, r13
0x180002e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e9d  mov     esi, eax
0x180002e9f  test    eax, eax
0x180002ea1  jns     short loc_180002EDC
0x180002ea3  mov     rcx, [rbp+40h]; this
0x180002ea7  mov     r9d, eax; char *
0x180002eaa  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180002eb1  mov     edx, 2FEh; void *
0x180002eb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002ebb  nop
0x180002ebc  mov     rcx, [rbx]
0x180002ebf  mov     rax, [rcx+10h]
0x180002ec3  mov     rcx, rbx
0x180002ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ecb  nop
0x180002ecc  lea     rcx, [rbp+arg_0]
0x180002ed0  call    ?InternalRelease@?$ComPtr@UICoreWindowStatic@Core@UI@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindowStatic>::InternalRelease(void)
0x180002ed5  mov     eax, esi
0x180002ed7  jmp     loc_180002F76
0x180002edc  mov     rax, [rbx]
0x180002edf  mov     r8, [rdi+50h]
0x180002ee3  mov     rdx, [rbp+arg_0]
0x180002ee7  mov     rcx, rbx
0x180002eea  mov     rax, [rax+0A0h]
0x180002ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef6  mov     rcx, [rbp+40h]; this
0x180002efa  test    eax, eax
0x180002efc  jns     short loc_180002F13
0x180002efe  mov     r9d, eax; char *
0x180002f01  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180002f08  mov     edx, 2FFh; void *
0x180002f0d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180002f13  mov     rax, [rbx]
0x180002f16  mov     r8, [rbp+arg_28]
0x180002f1a  mov     rdx, [rbp+arg_20]
0x180002f1e  mov     rcx, rbx
0x180002f21  mov     rax, [rax]
0x180002f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f29  mov     rcx, [rbp+40h]; this
0x180002f2d  test    eax, eax
0x180002f2f  jns     short loc_180002F46
0x180002f31  mov     r9d, eax; char *
0x180002f34  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180002f3b  mov     edx, 300h; void *
0x180002f40  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180002f46  mov     rax, [rbx]
0x180002f49  mov     rcx, rbx
0x180002f4c  mov     rax, [rax+10h]
0x180002f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f55  nop
0x180002f56  mov     rcx, [rbp+arg_0]
0x180002f5a  test    rcx, rcx
0x180002f5d  jz      short loc_180002F74
0x180002f5f  mov     [rbp+arg_0], 0
0x180002f67  mov     rax, [rcx]
0x180002f6a  mov     rax, [rax+10h]
0x180002f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f73  nop
0x180002f74  xor     eax, eax
0x180002f76  add     rsp, 68h
0x180002f7a  pop     r15
0x180002f7c  pop     r14
0x180002f7e  pop     r13
0x180002f80  pop     r12
0x180002f82  pop     rdi
0x180002f83  pop     rsi
0x180002f84  pop     rbx
0x180002f85  pop     rbp
0x180002f86  retn
```
