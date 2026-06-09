# Windows::Internal::WebView::CoreWebViewComponentCallback::Initialize(ICoreWebViewEventSink *,ICoreWebViewHost *,ICoreWebViewConsoleLogger *,ICoreWebViewWebVR *,IWebDriverHost2 *,Windows::UI::Core::ICoreDispatcher *)

- ea: `0x180002fc0`
- end: `0x18000353b`
- name: `?Initialize@CoreWebViewComponentCallback@WebView@Internal@Windows@@UEAAXPEAUICoreWebViewEventSink@@PEAUICoreWebViewHost@@PEAUICoreWebViewConsoleLogger@@PEAUICoreWebViewWebVR@@PEAUIWebDriverHost2@@PEAUICoreDispatcher@Core@UI@4@@Z`
- size: `1403`
- prototype: `void __fastcall(Windows::Internal::WebView::CoreWebViewComponentCallback *__hidden this, struct ICoreWebViewEventSink *, struct ICoreWebViewHost *, struct ICoreWebViewConsoleLogger *, struct ICoreWebViewWebVR *, struct IWebDriverHost2 *, struct Windows::UI::Core::ICoreDispatcher *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800451b0`

## callees

- `0x180002fc0`
- `0x1800090b4`
- `0x18000b0ec`
- `0x180018b30`
- `0x18001f278`
- `0x18002b530`
- `0x18002b5e4`
- `0x180035b88`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003252`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000349d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000349d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000326c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000326c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000329e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000329e`

## string_xrefs

- `0x180002fff`: `onecoreuap\inetcore\edgemanager\webview\corewebview\corewebviewcomponentcallback.cpp`
- `0x18000301f`: `onecoreuap\inetcore\edgemanager\webview\corewebview\corewebviewcomponentcallback.cpp`
- `0x18000303f`: `onecoreuap\inetcore\edgemanager\webview\corewebview\corewebviewcomponentcallback.cpp`
- `0x18000305f`: `onecoreuap\inetcore\edgemanager\webview\corewebview\corewebviewcomponentcallback.cpp`
- `0x18000307f`: `onecoreuap\inetcore\edgemanager\webview\corewebview\corewebviewcomponentcallback.cpp`
- `0x18000309f`: `onecoreuap\inetcore\edgemanager\webview\corewebview\corewebviewcomponentcallback.cpp`
- `0x1800032af`: `onecoreuap\inetcore\edgemanager\webview\corewebview\corewebviewcomponentcallback.cpp`
- `0x180003300`: `onecoreuap\inetcore\edgemanager\webview\corewebview\corewebviewcomponentcallback.cpp`
- `0x18000331f`: `onecoreuap\inetcore\edgemanager\webview\corewebview\corewebviewcomponentcallback.cpp`
- `0x18000336c`: `onecoreuap\inetcore\edgemanager\webview\corewebview\corewebviewcomponentcallback.cpp`
- `0x180003529`: `onecoreuap\inetcore\edgemanager\webview\corewebview\corewebviewcomponentcallback.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Windows::Internal::WebView::CoreWebViewComponentCallback::Initialize(
        Windows::Internal::WebView::CoreWebViewComponentCallback *this,
        struct ICoreWebViewEventSink *a2,
        struct ICoreWebViewHost *a3,
        struct ICoreWebViewConsoleLogger *a4,
        struct ICoreWebViewWebVR *a5,
        struct IWebDriverHost2 *a6,
        struct Windows::UI::Core::ICoreDispatcher *a7)
{
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  struct Windows::UI::Core::ICoreDispatcher *v15; // rbx
  __int64 v16; // rcx
  HSTRING v17; // rbx
  __int64 v18; // rcx
  int ActivationFactory; // eax
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, struct ICoreWebViewHost **); // rsi
  struct ICoreWebViewHost *v22; // rcx
  int v23; // eax
  const char *v24; // r9
  struct ICoreWebViewHost *v25; // rbx
  __int64 (__fastcall *v26)(struct ICoreWebViewHost *, __int64 *); // rsi
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rcx
  struct ICoreWebViewHost *v31; // rcx
  struct _RTL_CRITICAL_SECTION_DEBUG *v32; // rsi
  __int64 v33; // rcx
  struct _RTL_CRITICAL_SECTION *v34; // rax
  struct _RTL_CRITICAL_SECTION *v35; // rbx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  struct ICoreWebViewHost *v37; // [rsp+20h] [rbp-40h] BYREF
  __int64 v38; // [rsp+28h] [rbp-38h] BYREF
  __int64 v39; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  if ( *((_QWORD *)this + 19) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcomponentcallback.cpp",
      (const char *)a4);
  if ( *((_QWORD *)this + 20) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcomponentcallback.cpp",
      (const char *)a4);
  if ( *((_QWORD *)this + 21) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcomponentcallback.cpp",
      (const char *)a4);
  if ( *((_QWORD *)this + 22) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcomponentcallback.cpp",
      (const char *)a4);
  if ( *((_QWORD *)this + 18) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcomponentcallback.cpp",
      (const char *)a4);
  if ( *((_QWORD *)this + 17) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcomponentcallback.cpp",
      (const char *)a4);
  if ( a2 )
  {
    (*(void (__fastcall **)(struct ICoreWebViewEventSink *))(*(_QWORD *)a2 + 8LL))(a2);
    v11 = *((_QWORD *)this + 19);
    *((_QWORD *)this + 19) = a2;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  if ( *((struct ICoreWebViewHost **)this + 20) != a3 )
  {
    v37 = a3;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v37);
    v37 = (struct ICoreWebViewHost *)*((_QWORD *)this + 20);
    *((_QWORD *)this + 20) = a3;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  }
  if ( *((struct ICoreWebViewConsoleLogger **)this + 21) != a4 )
  {
    if ( a4 )
      (*(void (__fastcall **)(struct ICoreWebViewConsoleLogger *))(*(_QWORD *)a4 + 8LL))(a4);
    v12 = *((_QWORD *)this + 21);
    *((_QWORD *)this + 21) = a4;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( *((struct ICoreWebViewWebVR **)this + 22) != a5 )
  {
    if ( a5 )
      (*(void (__fastcall **)(struct ICoreWebViewWebVR *))(*(_QWORD *)a5 + 8LL))(a5);
    v13 = *((_QWORD *)this + 22);
    *((_QWORD *)this + 22) = a5;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( *((struct IWebDriverHost2 **)this + 23) != a6 )
  {
    v37 = a6;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v37);
    v14 = *((_QWORD *)this + 23);
    *((_QWORD *)this + 23) = a6;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = a7;
  if ( *((struct Windows::UI::Core::ICoreDispatcher **)this + 18) == a7 )
  {
    v15 = (struct Windows::UI::Core::ICoreDispatcher *)*((_QWORD *)this + 18);
  }
  else
  {
    if ( a7 )
      (*(void (__fastcall **)(struct Windows::UI::Core::ICoreDispatcher *))(*(_QWORD *)a7 + 8LL))(a7);
    v16 = *((_QWORD *)this + 18);
    *((_QWORD *)this + 18) = a7;
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v15 = (struct Windows::UI::Core::ICoreDispatcher *)*((_QWORD *)this + 18);
    }
  }
  if ( !v15 )
  {
    v37 = 0;
    v39 = 0;
    v38 = 0;
    if ( WindowsCreateStringReference(L"Windows.UI.Core.CoreWindow", 0x1Au, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v17 = string;
    v18 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    ActivationFactory = RoGetActivationFactory(v17, &GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1, &v39);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcomponentcallback.cpp",
        (const char *)(unsigned int)ActivationFactory,
        (int)v37);
    v20 = v39;
    v21 = *(__int64 (__fastcall **)(__int64, struct ICoreWebViewHost **))(*(_QWORD *)v39 + 48LL);
    v22 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(struct ICoreWebViewHost *))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v21(v20, &v37);
    if ( v23 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1C,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcomponentcallback.cpp",
        (const char *)(unsigned int)v23,
        (int)v37);
    v25 = v37;
    if ( !v37 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1D,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcomponentcallback.cpp",
        v24);
    v26 = *(__int64 (__fastcall **)(struct ICoreWebViewHost *, __int64 *))(*(_QWORD *)v37 + 72LL);
    v27 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = v26(v25, &v38);
    if ( v28 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1E,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcomponentcallback.cpp",
        (const char *)(unsigned int)v28,
        (int)v37);
    v29 = v38;
    if ( v38 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
      v29 = v38;
    }
    *((_QWORD *)this + 18) = v29;
    if ( v29 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(struct ICoreWebViewHost *))(*(_QWORD *)v31 + 16LL))(v31);
    }
  }
  v32 = (struct _RTL_CRITICAL_SECTION_DEBUG *)*((_QWORD *)this + 18);
  v33 = *((_QWORD *)this + 17);
  if ( v33 )
  {
    *((_QWORD *)this + 17) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  *((_QWORD *)this + 17) = 0;
  v34 = (struct _RTL_CRITICAL_SECTION *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  v35 = v34;
  if ( !v34 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcomponentcallback.cpp",
      (const char *)0x8007000ELL,
      (int)v37);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAgileObject>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAgileObject>(v34);
  v35->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IUnknown>::`vftable';
  *(_QWORD *)&v35->LockCount = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IUnknown>::`vftable'{for `IUnknown'};
  v35->OwningThread = &SyncCallHelper::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  v35->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&SyncCallHelper::`vftable';
  *(_QWORD *)&v35->LockCount = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IUnknown>::`vftable'{for `IUnknown'};
  v35->OwningThread = &SyncCallHelper::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  InitializeCriticalSectionEx(v35 + 1, 0, 0);
  v35[2].DebugInfo = 0;
  v37 = (struct ICoreWebViewHost *)v35;
  LOBYTE(v35[2].LockCount) = 1;
  if ( v32 )
  {
    (*(void (__fastcall **)(struct _RTL_CRITICAL_SECTION_DEBUG *))(*(_QWORD *)&v32->Type + 8LL))(v32);
    DebugInfo = v35[2].DebugInfo;
    v35[2].DebugInfo = v32;
    if ( DebugInfo )
      (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)&DebugInfo->Type + 16LL))(DebugInfo);
  }
  ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v35->DebugInfo->CriticalSection)(v35);
  *((_QWORD *)this + 17) = v35;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
}

```

## disassembly

```asm
0x180002fc0  mov     [rsp-18h+arg_8], rbx
0x180002fc5  mov     [rsp-18h+arg_10], rsi
0x180002fca  push    rbp
0x180002fcb  push    rdi
0x180002fcc  push    r14
0x180002fce  mov     rbp, rsp
0x180002fd1  sub     rsp, 60h
0x180002fd5  mov     rax, cs:__security_cookie
0x180002fdc  xor     rax, rsp
0x180002fdf  mov     [rbp+var_8], rax
0x180002fe3  mov     rbx, r9
0x180002fe6  mov     r14, r8
0x180002fe9  mov     rsi, rdx
0x180002fec  mov     rdi, rcx
0x180002fef  mov     rax, [rcx+98h]
0x180002ff6  mov     rcx, [rbp+18h]; this
0x180002ffa  test    rax, rax
0x180002ffd  jz      short loc_180003011
0x180002fff  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180003006  mov     edx, 60h ; '`'; void *
0x18000300b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180003011  mov     rcx, [rbp+18h]; this
0x180003015  cmp     qword ptr [rdi+0A0h], 0
0x18000301d  jz      short loc_180003031
0x18000301f  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180003026  mov     edx, 61h ; 'a'; void *
0x18000302b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180003031  mov     rcx, [rbp+18h]; this
0x180003035  cmp     qword ptr [rdi+0A8h], 0
0x18000303d  jz      short loc_180003051
0x18000303f  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180003046  mov     edx, 62h ; 'b'; void *
0x18000304b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180003051  mov     rcx, [rbp+18h]; this
0x180003055  cmp     qword ptr [rdi+0B0h], 0
0x18000305d  jz      short loc_180003071
0x18000305f  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180003066  mov     edx, 63h ; 'c'; void *
0x18000306b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180003071  mov     rcx, [rbp+18h]; this
0x180003075  cmp     qword ptr [rdi+90h], 0
0x18000307d  jz      short loc_180003091
0x18000307f  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180003086  mov     edx, 64h ; 'd'; void *
0x18000308b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180003091  mov     rcx, [rbp+18h]; this
0x180003095  cmp     qword ptr [rdi+88h], 0
0x18000309d  jz      short loc_1800030B1
0x18000309f  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800030a6  mov     edx, 65h ; 'e'; void *
0x1800030ab  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800030b1  cmp     rax, rsi
0x1800030b4  jz      short loc_1800030EB
0x1800030b6  test    rsi, rsi
0x1800030b9  jz      short loc_1800030CB
0x1800030bb  mov     rax, [rdx]
0x1800030be  mov     rcx, rsi
0x1800030c1  mov     rax, [rax+8]
0x1800030c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ca  nop
0x1800030cb  mov     rcx, [rdi+98h]
0x1800030d2  mov     [rdi+98h], rsi
0x1800030d9  test    rcx, rcx
0x1800030dc  jz      short loc_1800030EB
0x1800030de  mov     rax, [rcx]
0x1800030e1  mov     rax, [rax+10h]
0x1800030e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ea  nop
0x1800030eb  cmp     [rdi+0A0h], r14
0x1800030f2  jz      short loc_18000311C
0x1800030f4  mov     [rbp+var_40], r14
0x1800030f8  lea     rcx, [rbp+var_40]
0x1800030fc  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180003101  mov     rax, [rdi+0A0h]
0x180003108  mov     [rbp+var_40], rax
0x18000310c  mov     [rdi+0A0h], r14
0x180003113  lea     rcx, [rbp+var_40]
0x180003117  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000311c  cmp     [rdi+0A8h], rbx
0x180003123  jz      short loc_18000315A
0x180003125  test    rbx, rbx
0x180003128  jz      short loc_18000313A
0x18000312a  mov     rax, [rbx]
0x18000312d  mov     rcx, rbx
0x180003130  mov     rax, [rax+8]
0x180003134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003139  nop
0x18000313a  mov     rcx, [rdi+0A8h]
0x180003141  mov     [rdi+0A8h], rbx
0x180003148  test    rcx, rcx
0x18000314b  jz      short loc_18000315A
0x18000314d  mov     rax, [rcx]
0x180003150  mov     rax, [rax+10h]
0x180003154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003159  nop
0x18000315a  mov     rbx, [rbp+arg_20]
0x18000315e  cmp     [rdi+0B0h], rbx
0x180003165  jz      short loc_18000319C
0x180003167  test    rbx, rbx
0x18000316a  jz      short loc_18000317C
0x18000316c  mov     rax, [rbx]
0x18000316f  mov     rcx, rbx
0x180003172  mov     rax, [rax+8]
0x180003176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000317b  nop
0x18000317c  mov     rcx, [rdi+0B0h]
0x180003183  mov     [rdi+0B0h], rbx
0x18000318a  test    rcx, rcx
0x18000318d  jz      short loc_18000319C
0x18000318f  mov     rax, [rcx]
0x180003192  mov     rax, [rax+10h]
0x180003196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000319b  nop
0x18000319c  mov     rbx, [rbp+arg_28]
0x1800031a0  cmp     [rdi+0B8h], rbx
0x1800031a7  jz      short loc_1800031D6
0x1800031a9  mov     [rbp+var_40], rbx
0x1800031ad  lea     rcx, [rbp+var_40]
0x1800031b1  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800031b6  mov     rcx, [rdi+0B8h]
0x1800031bd  mov     [rdi+0B8h], rbx
0x1800031c4  test    rcx, rcx
0x1800031c7  jz      short loc_1800031D6
0x1800031c9  mov     rax, [rcx]
0x1800031cc  mov     rax, [rax+10h]
0x1800031d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031d5  nop
0x1800031d6  mov     rax, [rdi+90h]
0x1800031dd  mov     rbx, [rbp+arg_30]
0x1800031e1  cmp     rax, rbx
0x1800031e4  jz      short loc_180003223
0x1800031e6  test    rbx, rbx
0x1800031e9  jz      short loc_1800031FB
0x1800031eb  mov     rax, [rbx]
0x1800031ee  mov     rcx, rbx
0x1800031f1  mov     rax, [rax+8]
0x1800031f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031fa  nop
0x1800031fb  mov     rcx, [rdi+90h]
0x180003202  mov     [rdi+90h], rbx
0x180003209  test    rcx, rcx
0x18000320c  jz      short loc_180003221
0x18000320e  mov     rax, [rcx]
0x180003211  mov     rax, [rax+10h]
0x180003215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000321a  mov     rbx, [rdi+90h]
0x180003221  jmp     short loc_180003226
0x180003223  mov     rbx, rax
0x180003226  xor     r14d, r14d
0x180003229  test    rbx, rbx
0x18000322c  jnz     loc_1800033E8
0x180003232  mov     [rbp+var_40], r14
0x180003236  mov     [rbp+var_30], r14
0x18000323a  mov     [rbp+var_38], r14
0x18000323e  lea     r9, [rbp+string]; string
0x180003242  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180003246  mov     edx, 1Ah; length
0x18000324b  lea     rcx, ?RuntimeClass_Windows_UI_Core_CoreWindow@@3QBGB; "Windows.UI.Core.CoreWindow"
0x180003252  call    cs:__imp_WindowsCreateStringReference
0x180003258  test    eax, eax
0x18000325a  jns     short loc_180003272
0x18000325c  xor     r9d, r9d; lpArguments
0x18000325f  xor     r8d, r8d; nNumberOfArguments
0x180003262  mov     edx, 1; dwExceptionFlags
0x180003267  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000326c  call    cs:__imp_RaiseException
0x180003272  mov     rbx, [rbp+string]
0x180003276  mov     rcx, [rbp+var_30]
0x18000327a  test    rcx, rcx
0x18000327d  jz      short loc_180003290
0x18000327f  mov     [rbp+var_30], r14
0x180003283  mov     rax, [rcx]
0x180003286  mov     rax, [rax+10h]
0x18000328a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000328f  nop
0x180003290  lea     r8, [rbp+var_30]
0x180003294  lea     rdx, _GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1
0x18000329b  mov     rcx, rbx
0x18000329e  call    cs:__imp_RoGetActivationFactory
0x1800032a4  mov     rcx, [rbp+18h]; this
0x1800032a8  test    eax, eax
0x1800032aa  jns     short loc_1800032C1
0x1800032ac  mov     r9d, eax; char *
0x1800032af  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800032b6  mov     edx, 1Bh; void *
0x1800032bb  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800032c1  mov     rbx, [rbp+var_30]
0x1800032c5  mov     rax, [rbx]
0x1800032c8  mov     rsi, [rax+30h]
0x1800032cc  mov     rcx, [rbp+var_40]
0x1800032d0  test    rcx, rcx
0x1800032d3  jz      short loc_1800032E6
0x1800032d5  mov     [rbp+var_40], r14
0x1800032d9  mov     rdx, [rcx]
0x1800032dc  mov     rax, [rdx+10h]
0x1800032e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032e5  nop
0x1800032e6  lea     rdx, [rbp+var_40]
0x1800032ea  mov     rcx, rbx
0x1800032ed  mov     rax, rsi
0x1800032f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032f5  mov     rcx, [rbp+18h]; this
0x1800032f9  test    eax, eax
0x1800032fb  jns     short loc_180003312
0x1800032fd  mov     r9d, eax; char *
0x180003300  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180003307  mov     edx, 1Ch; void *
0x18000330c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180003312  mov     rcx, [rbp+18h]; this
0x180003316  mov     rbx, [rbp+var_40]
0x18000331a  test    rbx, rbx
0x18000331d  jnz     short loc_180003331
0x18000331f  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180003326  mov     edx, 1Dh; void *
0x18000332b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180003331  mov     rax, [rbx]
0x180003334  mov     rsi, [rax+48h]
0x180003338  mov     rcx, [rbp+var_38]
0x18000333c  test    rcx, rcx
0x18000333f  jz      short loc_180003352
0x180003341  mov     [rbp+var_38], r14
0x180003345  mov     rdx, [rcx]
0x180003348  mov     rax, [rdx+10h]
0x18000334c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003351  nop
0x180003352  lea     rdx, [rbp+var_38]
0x180003356  mov     rcx, rbx
0x180003359  mov     rax, rsi
0x18000335c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003361  mov     rcx, [rbp+18h]; this
0x180003365  test    eax, eax
0x180003367  jns     short loc_18000337E
0x180003369  mov     r9d, eax; char *
0x18000336c  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180003373  mov     edx, 1Eh; void *
0x180003378  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000337e  mov     rcx, [rbp+var_38]
0x180003382  test    rcx, rcx
0x180003385  jz      short loc_180003397
0x180003387  mov     rax, [rcx]
0x18000338a  mov     rax, [rax+8]
0x18000338e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003393  mov     rcx, [rbp+var_38]
0x180003397  mov     [rdi+90h], rcx
0x18000339e  test    rcx, rcx
0x1800033a1  jz      short loc_1800033B4
0x1800033a3  mov     [rbp+var_38], r14
0x1800033a7  mov     rax, [rcx]
0x1800033aa  mov     rax, [rax+10h]
0x1800033ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033b3  nop
0x1800033b4  mov     rcx, [rbp+var_30]
0x1800033b8  test    rcx, rcx
0x1800033bb  jz      short loc_1800033CE
0x1800033bd  mov     [rbp+var_30], r14
0x1800033c1  mov     rax, [rcx]
0x1800033c4  mov     rax, [rax+10h]
0x1800033c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033cd  nop
0x1800033ce  mov     rcx, [rbp+var_40]
0x1800033d2  test    rcx, rcx
0x1800033d5  jz      short loc_1800033E8
0x1800033d7  mov     [rbp+var_40], r14
0x1800033db  mov     rax, [rcx]
0x1800033de  mov     rax, [rax+10h]
0x1800033e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033e7  nop
0x1800033e8  mov     rsi, [rdi+90h]
0x1800033ef  mov     rcx, [rdi+88h]
0x1800033f6  test    rcx, rcx
0x1800033f9  jz      short loc_18000340F
0x1800033fb  mov     [rdi+88h], r14
0x180003402  mov     rax, [rcx]
0x180003405  mov     rax, [rax+10h]
0x180003409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000340e  nop
0x18000340f  mov     [rdi+88h], r14
0x180003416  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000341d  mov     ecx, 60h ; '`'; unsigned __int64
0x180003422  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003427  mov     rbx, rax
0x18000342a  test    rax, rax
0x18000342d  jz      loc_18000351F
0x180003433  mov     rcx, rax
0x180003436  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAgileObject@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAgileObject>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAgileObject>(void)
0x18000343b  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IUnknown>::`vftable'
0x180003442  mov     [rbx], rcx
0x180003445  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6BIUnknown@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IUnknown>::`vftable'{for `IUnknown'}
0x18000344c  mov     [rbx+8], rax
0x180003450  lea     rax, ??_7SyncCallHelper@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const SyncCallHelper::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x180003457  mov     [rbx+10h], rax
0x18000345b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180003462  test    rcx, rcx
0x180003465  jz      short loc_180003474
0x180003467  mov     rax, [rcx]
0x18000346a  mov     rax, [rax+8]
0x18000346e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003473  nop
0x180003474  lea     rax, ??_7SyncCallHelper@@6B@; const SyncCallHelper::`vftable'
0x18000347b  mov     [rbx], rax
  ... truncated ...
```
