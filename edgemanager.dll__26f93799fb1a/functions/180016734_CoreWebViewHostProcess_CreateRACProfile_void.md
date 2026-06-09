# CoreWebViewHostProcess::CreateRACProfile(void)

- ea: `0x180016734`
- end: `0x180016a4a`
- name: `?CreateRACProfile@CoreWebViewHostProcess@@AEAAXXZ`
- size: `790`
- prototype: `void __fastcall(CoreWebViewHostProcess *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001646c`

## callees

- `0x180007ee0`
- `0x18000b0ec`
- `0x18000d194`
- `0x180016734`
- `0x180016a50`
- `0x180016bec`
- `0x180017768`
- `0x180017cac`
- `0x18002b530`
- `0x180035b88`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001677d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016a0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001677d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016a0f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800167d9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800167d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CoreWebViewHostProcess::CreateRACProfile(CoreWebViewHostProcess *this)
{
  CoreWebViewHostProcess *v1; // r14
  int ActivationFactory; // eax
  __int64 v3; // rdi
  int (__fastcall *v4)(__int64, HSTRING, char *); // rbx
  CoreWebViewHostProcess *v5; // rsi
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rcx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, char *); // rbx
  int v13; // eax
  __int64 v14; // rcx
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v16)(_QWORD, GUID *, __int64 *); // rbx
  int v17; // eax
  int v18; // eax
  int v19; // [rsp+20h] [rbp-29h]
  __int64 v20; // [rsp+30h] [rbp-19h] BYREF
  HSTRING string; // [rsp+38h] [rbp-11h] BYREF
  __int64 v22; // [rsp+40h] [rbp-9h] BYREF
  __int64 v23; // [rsp+48h] [rbp-1h] BYREF
  GUID *v24; // [rsp+50h] [rbp+7h] BYREF
  HSTRING v25; // [rsp+58h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+17h] BYREF
  __int64 v27; // [rsp+78h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v1 = this;
  v24 = 0;
  LOBYTE(this) = *((_BYTE *)this + 112);
  GetCapabilities(this, &v24);
  WindowsDeleteString(0);
  string = 0;
  CoreWebViewHostProcess::GetRACProfileNameInternal(v1, &string);
  v22 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  v27 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.Core.RestrictedAppContainer",
    0x35u,
    0x34u);
  ActivationFactory = RoGetActivationFactory(v27, &GUID_5d2ee1bb_ac42_4a34_90ce_52b83440477e, &v22);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewhostprocess.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v19);
  v3 = v22;
  v4 = *(int (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v22 + 72LL);
  v5 = (CoreWebViewHostProcess *)((char *)v1 + 136);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)v1 + 136);
  if ( v4(v3, string, (char *)v1 + 136) >= 0 && (v6 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v5) != 0 )
  {
    v20 = 0;
    v7 = (*v6)[8](v6, v24, &v20);
    if ( v7 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewhostprocess.cpp",
        (const char *)(unsigned int)v7,
        v19);
    v8 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(v20);
    if ( v8 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewhostprocess.cpp",
        (const char *)(unsigned int)v8,
        v19);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  }
  else
  {
    v20 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, HSTRING, GUID *, __int64 *))(*(_QWORD *)v22 + 56LL))(
           v22,
           string,
           v24,
           &v20);
    if ( v9 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xDC,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewhostprocess.cpp",
        (const char *)(unsigned int)v9,
        v19);
    v10 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>(v20);
    if ( v10 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xE0,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewhostprocess.cpp",
        (const char *)(unsigned int)v10,
        v19);
    v11 = v20;
    v12 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v20 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)v1 + 136);
    v13 = v12(v11, (char *)v1 + 136);
    if ( v13 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xE1,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewhostprocess.cpp",
        (const char *)(unsigned int)v13,
        v19);
    v14 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  v23 = 0;
  v15 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v5;
  v16 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v5;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  v17 = v16(v15, &GUID_9a8f222b_12c6_42b8_9c51_a390e368e0d6, &v23);
  if ( v17 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewhostprocess.cpp",
      (const char *)(unsigned int)v17,
      v19);
  v25 = 0;
  CoreWebViewHostProcess::DetermineEnterpriseId(v1, &v25);
  v18 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v23 + 48LL))(v23, v25);
  if ( v18 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewhostprocess.cpp",
      (const char *)(unsigned int)v18,
      v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
}

```

## disassembly

```asm
0x180016734  mov     [rsp-8+arg_8], rbx
0x180016739  mov     [rsp-8+arg_10], rsi
0x18001673e  push    rbp
0x18001673f  push    rdi
0x180016740  push    r14
0x180016742  lea     rbp, [rsp-47h]
0x180016747  sub     rsp, 90h
0x18001674e  mov     rax, cs:__security_cookie
0x180016755  xor     rax, rsp
0x180016758  mov     [rbp+57h+var_20], rax
0x18001675c  mov     r14, rcx
0x18001675f  mov     [rbp+57h+var_50], 0
0x180016767  lea     rdx, [rbp+57h+var_50]
0x18001676b  mov     cl, [rcx+70h]
0x18001676e  call    GetCapabilities
0x180016773  mov     [rbp+57h+string], 0
0x18001677b  xor     ecx, ecx; string
0x18001677d  call    cs:__imp_WindowsDeleteString
0x180016783  mov     [rbp+57h+string], 0
0x18001678b  lea     rdx, [rbp+57h+string]; HSTRING *
0x18001678f  mov     rcx, r14; this
0x180016792  call    ?GetRACProfileNameInternal@CoreWebViewHostProcess@@AEAAXPEAPEAUHSTRING__@@@Z; CoreWebViewHostProcess::GetRACProfileNameInternal(HSTRING__ * *)
0x180016797  mov     [rbp+57h+var_60], 0
0x18001679f  lea     rcx, [rbp+57h+var_60]
0x1800167a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800167a8  mov     [rbp+57h+var_28], 0
0x1800167b0  mov     r9d, 34h ; '4'; unsigned int
0x1800167b6  lea     r8d, [r9+1]; unsigned int
0x1800167ba  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Core_RestrictedAppContainer@@3QBGB; "Windows.ApplicationModel.Core.Restricte"...
0x1800167c1  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800167c5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800167ca  lea     r8, [rbp+57h+var_60]
0x1800167ce  lea     rdx, _GUID_5d2ee1bb_ac42_4a34_90ce_52b83440477e
0x1800167d5  mov     rcx, [rbp+57h+var_28]
0x1800167d9  call    cs:__imp_RoGetActivationFactory
0x1800167df  mov     rcx, [rbp+5Fh]; this
0x1800167e3  test    eax, eax
0x1800167e5  jns     short loc_1800167FC
0x1800167e7  mov     r9d, eax; char *
0x1800167ea  lea     r8, aOnecoreuapInet_39; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800167f1  mov     edx, 0D2h; void *
0x1800167f6  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800167fc  mov     rdi, [rbp+57h+var_60]
0x180016800  mov     rax, [rdi]
0x180016803  mov     rbx, [rax+48h]
0x180016807  lea     rsi, [r14+88h]
0x18001680e  mov     rcx, rsi
0x180016811  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016816  mov     r8, rsi
0x180016819  mov     rdx, [rbp+57h+string]
0x18001681d  mov     rcx, rdi
0x180016820  mov     rax, rbx
0x180016823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016828  test    eax, eax
0x18001682a  js      short loc_1800168A1
0x18001682c  mov     rcx, [rsi]
0x18001682f  test    rcx, rcx
0x180016832  jz      short loc_1800168A1
0x180016834  mov     [rbp+57h+var_70], 0
0x18001683c  mov     rax, [rcx]
0x18001683f  lea     r8, [rbp+57h+var_70]
0x180016843  mov     rdx, [rbp+57h+var_50]
0x180016847  mov     rax, [rax+40h]
0x18001684b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016850  mov     rcx, [rbp+5Fh]; this
0x180016854  test    eax, eax
0x180016856  jns     short loc_18001686D
0x180016858  mov     r9d, eax; char *
0x18001685b  lea     r8, aOnecoreuapInet_39; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180016862  mov     edx, 0E8h; void *
0x180016867  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001686d  mov     rcx, [rbp+57h+var_70]
0x180016871  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x180016876  mov     rcx, [rbp+5Fh]; this
0x18001687a  test    eax, eax
0x18001687c  jns     short loc_180016893
0x18001687e  mov     r9d, eax; char *
0x180016881  lea     r8, aOnecoreuapInet_39; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180016888  mov     edx, 0EAh; void *
0x18001688d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180016893  lea     rcx, [rbp+57h+var_70]
0x180016897  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001689c  jmp     loc_180016964
0x1800168a1  mov     [rbp+57h+var_70], 0
0x1800168a9  mov     rcx, [rbp+57h+var_60]
0x1800168ad  mov     rax, [rcx]
0x1800168b0  lea     r9, [rbp+57h+var_70]
0x1800168b4  mov     r8, [rbp+57h+var_50]
0x1800168b8  mov     rdx, [rbp+57h+string]
0x1800168bc  mov     rax, [rax+38h]
0x1800168c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168c5  mov     rcx, [rbp+5Fh]; this
0x1800168c9  test    eax, eax
0x1800168cb  jns     short loc_1800168E2
0x1800168cd  mov     r9d, eax; char *
0x1800168d0  lea     r8, aOnecoreuapInet_39; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800168d7  mov     edx, 0DCh; void *
0x1800168dc  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800168e2  mov     rcx, [rbp+57h+var_70]
0x1800168e6  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *> *,tagCOWAIT_FLAGS,void *)
0x1800168eb  mov     rcx, [rbp+5Fh]; this
0x1800168ef  test    eax, eax
0x1800168f1  jns     short loc_180016908
0x1800168f3  mov     r9d, eax; char *
0x1800168f6  lea     r8, aOnecoreuapInet_39; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800168fd  mov     edx, 0E0h; void *
0x180016902  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180016908  mov     rdi, [rbp+57h+var_70]
0x18001690c  mov     rax, [rdi]
0x18001690f  mov     rbx, [rax+40h]
0x180016913  mov     rcx, rsi
0x180016916  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001691b  mov     rdx, rsi
0x18001691e  mov     rcx, rdi
0x180016921  mov     rax, rbx
0x180016924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016929  mov     rcx, [rbp+5Fh]; this
0x18001692d  test    eax, eax
0x18001692f  jns     short loc_180016946
0x180016931  mov     r9d, eax; char *
0x180016934  lea     r8, aOnecoreuapInet_39; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001693b  mov     edx, 0E1h; void *
0x180016940  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180016946  mov     rcx, [rbp+57h+var_70]
0x18001694a  test    rcx, rcx
0x18001694d  jz      short loc_180016964
0x18001694f  mov     [rbp+57h+var_70], 0
0x180016957  mov     rax, [rcx]
0x18001695a  mov     rax, [rax+10h]
0x18001695e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016963  nop
0x180016964  mov     [rbp+57h+var_58], 0
0x18001696c  mov     rdi, [rsi]
0x18001696f  mov     rax, [rdi]
0x180016972  mov     rbx, [rax]
0x180016975  lea     rcx, [rbp+57h+var_58]
0x180016979  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001697e  lea     r8, [rbp+57h+var_58]
0x180016982  lea     rdx, _GUID_9a8f222b_12c6_42b8_9c51_a390e368e0d6
0x180016989  mov     rcx, rdi
0x18001698c  mov     rax, rbx
0x18001698f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016994  nop
0x180016995  mov     rcx, [rbp+5Fh]; this
0x180016999  test    eax, eax
0x18001699b  jns     short loc_1800169B2
0x18001699d  mov     r9d, eax; char *
0x1800169a0  lea     r8, aOnecoreuapInet_39; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800169a7  mov     edx, 0EEh; void *
0x1800169ac  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800169b2  mov     [rbp+57h+var_48], 0
0x1800169ba  lea     rdx, [rbp+57h+var_48]; HSTRING *
0x1800169be  mov     rcx, r14; this
0x1800169c1  call    ?DetermineEnterpriseId@CoreWebViewHostProcess@@AEAAXPEAPEAUHSTRING__@@@Z; CoreWebViewHostProcess::DetermineEnterpriseId(HSTRING__ * *)
0x1800169c6  mov     rcx, [rbp+57h+var_58]
0x1800169ca  mov     rax, [rcx]
0x1800169cd  mov     rdx, [rbp+57h+var_48]
0x1800169d1  mov     rax, [rax+30h]
0x1800169d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169da  mov     rcx, [rbp+5Fh]; this
0x1800169de  test    eax, eax
0x1800169e0  jns     short loc_1800169F7
0x1800169e2  mov     r9d, eax; char *
0x1800169e5  lea     r8, aOnecoreuapInet_39; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800169ec  mov     edx, 0F2h; void *
0x1800169f1  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800169f7  lea     rcx, [rbp+57h+var_58]
0x1800169fb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016a00  nop
0x180016a01  lea     rcx, [rbp+57h+var_60]
0x180016a05  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016a0a  nop
0x180016a0b  mov     rcx, [rbp+57h+string]; string
0x180016a0f  call    cs:__imp_WindowsDeleteString
0x180016a15  mov     [rbp+57h+string], 0
0x180016a1d  lea     rcx, [rbp+57h+var_50]
0x180016a21  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016a26  mov     rcx, [rbp+57h+var_20]
0x180016a2a  xor     rcx, rsp; StackCookie
0x180016a2d  call    __security_check_cookie
0x180016a32  lea     r11, [rsp+0A0h+var_10]
0x180016a3a  mov     rbx, [r11+28h]
0x180016a3e  mov     rsi, [r11+30h]
0x180016a42  mov     rsp, r11
0x180016a45  pop     r14
0x180016a47  pop     rdi
0x180016a48  pop     rbp
0x180016a49  retn
```
