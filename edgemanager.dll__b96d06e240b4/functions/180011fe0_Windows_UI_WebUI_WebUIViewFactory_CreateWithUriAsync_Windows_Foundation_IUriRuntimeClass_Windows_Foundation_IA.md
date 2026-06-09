# Windows::UI::WebUI::WebUIViewFactory::CreateWithUriAsync(Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::IAsyncOperation<Windows::UI::WebUI::WebUIView *> * *)

- ea: `0x180011fe0`
- end: `0x1800122a2`
- name: `?CreateWithUriAsync@WebUIViewFactory@WebUI@UI@Windows@@UEAAJPEAUIUriRuntimeClass@Foundation@4@PEAPEAU?$IAsyncOperation@PEAVWebUIView@WebUI@UI@Windows@@@64@@Z`
- size: `706`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180055f90`

## callees

- `0x180007ee0`
- `0x18000b0ec`
- `0x180011874`
- `0x180011fe0`
- `0x1800122a8`
- `0x180012384`
- `0x180012434`
- `0x1800127ec`
- `0x1800154cc`
- `0x1800274e0`
- `0x18002b530`
- `0x180035b88`
- `0x1800615bc`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012028`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012048`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800120ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012276`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012028`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012048`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800120ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012276`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800121d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800121d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::WebUI::WebUIViewFactory::CreateWithUriAsync(__int64 a1, __int64 a2, int a3)
{
  HSTRING *HStringFromUri; // rbx
  __int64 v5; // rax
  __int64 v6; // rsi
  __int64 (__fastcall *v7)(__int64, __int64, HSTRING, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rdi
  HSTRING v8; // rbx
  int v9; // ebx
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rdi
  int v13; // eax
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64 *); // rdi
  int v16; // eax
  __int64 v17; // rax
  int v18; // r9d
  int v19; // ebx
  int v20; // [rsp+20h] [rbp-29h]
  int v21; // [rsp+20h] [rbp-29h]
  HSTRING string; // [rsp+30h] [rbp-19h] BYREF
  __int64 v23; // [rsp+38h] [rbp-11h] BYREF
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-9h] BYREF
  HSTRING v25; // [rsp+48h] [rbp-1h] BYREF
  int v26; // [rsp+50h] [rbp+7h]
  __int64 v27; // [rsp+58h] [rbp+Fh] BYREF
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v30; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  string = 0;
  if ( a2 )
  {
    HStringFromUri = (HSTRING *)WebViewControlWinRTHelpers::GetHStringFromUri(&v25);
    WindowsDeleteString(string);
    string = 0;
    string = *HStringFromUri;
    *HStringFromUri = 0;
    WindowsDeleteString(v25);
  }
  else
  {
    Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, L"about:blank", 0xBu);
  }
  v24 = 0;
  v5 = WebViewControlWinRTHelpers::GetActivationFactoryFF<Windows::ApplicationModel::Core::ICoreImmersiveApplication>(&v25);
  v6 = *(_QWORD *)v5;
  v7 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(**(_QWORD **)v5 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  v8 = string;
  v30 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &LocaleName, 1u, 0);
  v9 = v7(v6, v30, v8, &v24);
  v30 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  if ( v9 >= 0 )
  {
    v23 = 0;
    v11 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v24;
    v12 = **v24;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    v13 = v12(v11, &GUID_2e5500b6_66ad_467f_abb5_022a64283d88, &v23);
    if ( v13 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\webuiviewfactory.cpp",
        (const char *)(unsigned int)v13,
        v20);
    AllowASTACallToObject_Windows::ApplicationModel::Core::ICoreApplicationViewInternal_(v23);
    GetCoreApplicationViewInternalPrivateProperty_Windows::UI::WebUI::Private::IWebUIViewCreationContext_(&v28, v23);
    v27 = 0;
    v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
    v15 = **v28;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    v16 = v15(v14, &GUID_93667634_868a_4f98_9f43_ac4ed84523c1, &v27);
    if ( v16 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\webuiviewfactory.cpp",
        (const char *)(unsigned int)v16,
        v20);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 152LL))(v27);
    LODWORD(hstringHeader.Reserved.Reserved1) = GetCurrentThreadId();
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v28;
    if ( v28 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v28)[1])(v28);
    v25 = (HSTRING)4;
    v26 = 0;
    v17 = Windows::Internal::MakeOpLambda_0_Windows::Internal::CMarshaledInterfaceResult_Windows::UI::WebUI::IWebUIView___lambda_4e24ee157e8e1e9331162e7030b06f6a___(&hstringHeader);
    v19 = Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<Windows::UI::WebUI::WebUIView *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::WebUI::WebUIView *>,Windows::Internal::INilDelegate,Windows::Internal::CMarshaledInterfaceResult<Windows::UI::WebUI::IWebUIView>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
            a3,
            (unsigned int)&v25,
            (unsigned int)L"Windows.Foundation.IAsyncOperation`1<Windows.UI.WebUI.WebUIView>",
            v18,
            v17);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hstringHeader.Reserved.Reserved2[8]);
    if ( v19 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\webuiviewfactory.cpp",
        (const char *)(unsigned int)v19,
        v21);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    WindowsDeleteString(string);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\webuiviewfactory.cpp",
      (const char *)(unsigned int)v9,
      v20);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    WindowsDeleteString(string);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x180011fe0  mov     [rsp-8+arg_0], rbx
0x180011fe5  mov     [rsp-8+arg_18], rsi
0x180011fea  push    rbp
0x180011feb  push    rdi
0x180011fec  push    r14
0x180011fee  lea     rbp, [rsp-47h]
0x180011ff3  sub     rsp, 90h
0x180011ffa  mov     rax, cs:__security_cookie
0x180012001  xor     rax, rsp
0x180012004  mov     [rbp+57h+var_18], rax
0x180012008  mov     r14, r8
0x18001200b  mov     [rbp+57h+string], 0
0x180012013  test    rdx, rdx
0x180012016  jz      short loc_180012050
0x180012018  lea     rcx, [rbp+57h+var_58]
0x18001201c  call    ?GetHStringFromUri@WebViewControlWinRTHelpers@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAUIUriRuntimeClass@Foundation@Windows@@@Z; WebViewControlWinRTHelpers::GetHStringFromUri(Windows::Foundation::IUriRuntimeClass *)
0x180012021  mov     rbx, rax
0x180012024  mov     rcx, [rbp+57h+string]; string
0x180012028  call    cs:__imp_WindowsDeleteString
0x18001202e  mov     [rbp+57h+string], 0
0x180012036  mov     rcx, [rbx]
0x180012039  mov     [rbp+57h+string], rcx
0x18001203d  mov     qword ptr [rbx], 0
0x180012044  mov     rcx, [rbp+57h+var_58]; string
0x180012048  call    cs:__imp_WindowsDeleteString
0x18001204e  jmp     short loc_180012066
0x180012050  mov     r8d, 0Bh; unsigned int
0x180012056  lea     rdx, aAboutBlank; "about:blank"
0x18001205d  lea     rcx, [rbp+57h+string]; this
0x180012061  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180012066  mov     [rbp+57h+var_60], 0
0x18001206e  lea     rcx, [rbp+57h+var_58]
0x180012072  call    ??$GetActivationFactoryFF@UICoreImmersiveApplication@Core@ApplicationModel@Windows@@@WebViewControlWinRTHelpers@@YA?AV?$ComPtr@UICoreImmersiveApplication@Core@ApplicationModel@Windows@@@WRL@Microsoft@@PEBG@Z; WebViewControlWinRTHelpers::GetActivationFactoryFF<Windows::ApplicationModel::Core::ICoreImmersiveApplication>(ushort const *)
0x180012077  mov     rsi, [rax]
0x18001207a  mov     rax, [rsi]
0x18001207d  mov     rdi, [rax+38h]
0x180012081  lea     rcx, [rbp+57h+var_60]
0x180012085  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001208a  mov     rbx, [rbp+57h+string]
0x18001208e  mov     [rbp+57h+var_20], 0
0x180012096  xor     r9d, r9d; unsigned int
0x180012099  lea     r8d, [r9+1]; unsigned int
0x18001209d  lea     rdx, LocaleName; sourceString
0x1800120a4  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800120a8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800120ad  lea     r9, [rbp+57h+var_60]
0x1800120b1  mov     r8, rbx
0x1800120b4  mov     rdx, [rbp+57h+var_20]
0x1800120b8  mov     rcx, rsi
0x1800120bb  mov     rax, rdi
0x1800120be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120c3  mov     ebx, eax
0x1800120c5  mov     [rbp+57h+var_20], 0
0x1800120cd  lea     rcx, [rbp+57h+var_58]
0x1800120d1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800120d6  test    ebx, ebx
0x1800120d8  jns     short loc_18001210C
0x1800120da  mov     rcx, [rbp+5Fh]; this
0x1800120de  mov     r9d, ebx; char *
0x1800120e1  lea     r8, aOnecoreuapInet_4; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800120e8  mov     edx, 76h ; 'v'; void *
0x1800120ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800120f2  lea     rcx, [rbp+57h+var_60]
0x1800120f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800120fb  mov     rcx, [rbp+57h+string]; string
0x1800120ff  call    cs:__imp_WindowsDeleteString
0x180012105  mov     eax, ebx
0x180012107  jmp     loc_18001227E
0x18001210c  mov     [rbp+57h+var_68], 0
0x180012114  mov     rbx, [rbp+57h+var_60]
0x180012118  mov     rax, [rbx]
0x18001211b  mov     rdi, [rax]
0x18001211e  lea     rcx, [rbp+57h+var_68]
0x180012122  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180012127  lea     r8, [rbp+57h+var_68]
0x18001212b  lea     rdx, _GUID_2e5500b6_66ad_467f_abb5_022a64283d88
0x180012132  mov     rcx, rbx
0x180012135  mov     rax, rdi
0x180012138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001213d  nop
0x18001213e  mov     rcx, [rbp+5Fh]; this
0x180012142  test    eax, eax
0x180012144  jns     short loc_18001215B
0x180012146  mov     r9d, eax; char *
0x180012149  lea     r8, aOnecoreuapInet_4; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180012150  mov     edx, 82h; void *
0x180012155  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001215b  mov     rcx, [rbp+57h+var_68]
0x18001215f  call    AllowASTACallToObject_Windows__ApplicationModel__Core__ICoreApplicationViewInternal_
0x180012164  mov     rdx, [rbp+57h+var_68]
0x180012168  lea     rcx, [rbp+57h+var_40]
0x18001216c  call    GetCoreApplicationViewInternalPrivateProperty_Windows__UI__WebUI__Private__IWebUIViewCreationContext_
0x180012171  mov     [rbp+57h+var_48], 0
0x180012179  mov     rbx, [rbp+57h+var_40]
0x18001217d  mov     rax, [rbx]
0x180012180  mov     rdi, [rax]
0x180012183  lea     rcx, [rbp+57h+var_48]
0x180012187  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001218c  lea     r8, [rbp+57h+var_48]
0x180012190  lea     rdx, _GUID_93667634_868a_4f98_9f43_ac4ed84523c1
0x180012197  mov     rcx, rbx
0x18001219a  mov     rax, rdi
0x18001219d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121a2  nop
0x1800121a3  mov     rcx, [rbp+5Fh]; this
0x1800121a7  test    eax, eax
0x1800121a9  jns     short loc_1800121C0
0x1800121ab  mov     r9d, eax; char *
0x1800121ae  lea     r8, aOnecoreuapInet_4; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800121b5  mov     edx, 89h; void *
0x1800121ba  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800121c0  mov     rcx, [rbp+57h+var_48]
0x1800121c4  mov     rax, [rcx]
0x1800121c7  mov     rax, [rax+98h]
0x1800121ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121d3  call    cs:__imp_GetCurrentThreadId
0x1800121d9  mov     dword ptr [rbp+57h+hstringHeader.Reserved], eax
0x1800121dc  mov     rcx, [rbp+57h+var_40]
0x1800121e0  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rcx
0x1800121e4  test    rcx, rcx
0x1800121e7  jz      short loc_1800121F6
0x1800121e9  mov     rax, [rcx]
0x1800121ec  mov     rax, [rax+8]
0x1800121f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121f5  nop
0x1800121f6  mov     [rbp+57h+var_58], 4
0x1800121fe  mov     [rbp+57h+var_50], 0
0x180012205  lea     rcx, [rbp+57h+hstringHeader]
0x180012209  call    Windows__Internal__MakeOpLambda_0_Windows__Internal__CMarshaledInterfaceResult_Windows__UI__WebUI__IWebUIView___lambda_4e24ee157e8e1e9331162e7030b06f6a___
0x18001220e  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x180012213  lea     r8, aWindowsFoundat_8; "Windows.Foundation.IAsyncOperation`1<Wi"...
0x18001221a  lea     rdx, [rbp+57h+var_58]
0x18001221e  mov     rcx, r14
0x180012221  call    ??$MakeAsyncHelper@U?$IAsyncOperation@PEAVWebUIView@WebUI@UI@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVWebUIView@WebUI@UI@Windows@@@23@UINilDelegate@Internal@3@V?$CMarshaledInterfaceResult@UIWebUIView@WebUI@UI@Windows@@@63@VComTaskPoolHandler@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@YAJPEAPEAU?$IAsyncOperation@PEAVWebUIView@WebUI@UI@Windows@@@Foundation@1@$$QEAVComTaskPoolHandler@01@QEBGW4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CMarshaledInterfaceResult@UIWebUIView@WebUI@UI@Windows@@@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<Windows::UI::WebUI::WebUIView *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::WebUI::WebUIView *>,Windows::Internal::INilDelegate,Windows::Internal::CMarshaledInterfaceResult<Windows::UI::WebUI::IWebUIView>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Foundation::IAsyncOperation<Windows::UI::WebUI::WebUIView *> * *,Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CMarshaledInterfaceResult<Windows::UI::WebUI::IWebUIView>> *)
0x180012226  mov     ebx, eax
0x180012228  lea     rcx, [rbp+57h+hstringHeader.Reserved+8]
0x18001222c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180012231  test    ebx, ebx
0x180012233  jns     short loc_18001224E
0x180012235  mov     rcx, [rbp+5Fh]; this
0x180012239  mov     r9d, ebx; char *
0x18001223c  lea     r8, aOnecoreuapInet_4; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180012243  mov     edx, 0A6h; void *
0x180012248  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001224e  lea     rcx, [rbp+57h+var_48]
0x180012252  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180012257  lea     rcx, [rbp+57h+var_40]
0x18001225b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180012260  lea     rcx, [rbp+57h+var_68]
0x180012264  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180012269  lea     rcx, [rbp+57h+var_60]
0x18001226d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180012272  mov     rcx, [rbp+57h+string]; string
0x180012276  call    cs:__imp_WindowsDeleteString
0x18001227c  xor     eax, eax
0x18001227e  mov     rcx, [rbp+57h+var_18]
0x180012282  xor     rcx, rsp; StackCookie
0x180012285  call    __security_check_cookie
0x18001228a  lea     r11, [rsp+0A0h+var_10]
0x180012292  mov     rbx, [r11+20h]
0x180012296  mov     rsi, [r11+38h]
0x18001229a  mov     rsp, r11
0x18001229d  pop     r14
0x18001229f  pop     rdi
0x1800122a0  pop     rbp
0x1800122a1  retn
```
