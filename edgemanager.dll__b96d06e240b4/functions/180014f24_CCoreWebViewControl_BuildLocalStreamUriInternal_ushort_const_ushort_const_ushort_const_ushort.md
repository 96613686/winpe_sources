# CCoreWebViewControl::BuildLocalStreamUriInternal(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180014f24`
- end: `0x1800154c5`
- name: `?BuildLocalStreamUriInternal@CCoreWebViewControl@@AEAAJPEBG00PEAPEAG@Z`
- size: `1441`
- prototype: `__int64 __fastcall(CCoreWebViewControl *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039380`
- `0x180039414`

## callees

- `0x1800027a0`
- `0x1800073a0`
- `0x180007530`
- `0x18000b0ec`
- `0x180013c90`
- `0x180014f24`
- `0x1800154cc`
- `0x180016368`
- `0x1800163b4`
- `0x180016400`
- `0x18002b530`
- `0x180035b88`
- `0x18004e120`
- `0x180081700`
- `0x180085010`

## import_xrefs

- `iertutil!CreateUri` at `0x18001523d`
- `iertutil!CreateUri` at `0x18001523d`
- `urlmon!CoInternetCombineUrl` at `0x1800151f4`
- `urlmon!CoInternetCombineUrl` at `0x1800151f4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001538d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001539e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800153f6`
- `OLEAUT32!__imp_SysFreeString` at `0x180015407`
- `OLEAUT32!__imp_SysFreeString` at `0x180015452`
- `OLEAUT32!__imp_SysFreeString` at `0x180015463`
- `OLEAUT32!__imp_SysFreeString` at `0x18001538d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001539e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800153f6`
- `OLEAUT32!__imp_SysFreeString` at `0x180015407`
- `OLEAUT32!__imp_SysFreeString` at `0x180015452`
- `OLEAUT32!__imp_SysFreeString` at `0x180015463`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CCoreWebViewControl::BuildLocalStreamUriInternal(
        CCoreWebViewControl *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  int v8; // eax
  const struct _GUID *v9; // rdx
  const unsigned __int16 *v10; // rcx
  int ActivationFactory; // eax
  void *v12; // rdi
  __int64 (__fastcall *v13)(void *, HSTRING, _QWORD, __int64 *); // rbx
  int v14; // eax
  void *v15; // rdi
  __int64 (__fastcall *v16)(void *, __int64, __int64); // rbx
  __int64 v17; // rax
  int v18; // eax
  const unsigned __int16 **v19; // r8
  int v20; // eax
  __int64 v21; // r9
  int v22; // eax
  int v23; // eax
  unsigned __int64 v24; // rdx
  int IsValidLocalStreamHost; // eax
  unsigned int v26; // ebx
  int v27; // eax
  HRESULT v28; // eax
  HRESULT v29; // eax
  IUri *v30; // rdi
  HRESULT (__stdcall *GetSchemeName)(IUri *, BSTR *); // rbx
  int v32; // eax
  BSTR v33; // rax
  __int64 v34; // rdx
  int v35; // edx
  int v36; // ecx
  IUri *v37; // rdi
  HRESULT (__stdcall *GetHost)(IUri *, BSTR *); // rbx
  int v39; // eax
  BSTR v40; // rax
  __int64 v41; // rdx
  int v42; // edx
  int v43; // ecx
  int v44; // eax
  int cchResult; // [rsp+20h] [rbp-E0h]
  int cchResulta; // [rsp+20h] [rbp-E0h]
  int cchResultb; // [rsp+20h] [rbp-E0h]
  int cchResultc; // [rsp+20h] [rbp-E0h]
  BSTR v50; // [rsp+40h] [rbp-C0h] BYREF
  IUri *ppURI; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  void *v53; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v54; // [rsp+60h] [rbp-A0h] BYREF
  IEWinRTUtil *v55; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  HSTRING__ v57[2]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR pszStr1[2088]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pwzBaseUrl[2088]; // [rsp+10D0h] [rbp+FD0h] BYREF
  WCHAR pszResult[2088]; // [rsp+2120h] [rbp+2020h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+31C8h] [rbp+30C8h]

  string = 0;
  v8 = CWinRTHelper::CStringRef::CopyFromWideString(&string, a2);
  if ( v8 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1CF,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v8,
      cchResult);
  v53 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  ActivationFactory = CWinRTHelper::GetActivationFactory(v10, v9, &v53);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1D4,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)ActivationFactory,
      cchResult);
  v54 = 0;
  v12 = v53;
  v13 = *(__int64 (__fastcall **)(void *, HSTRING, _QWORD, __int64 *))(*(_QWORD *)v53 + 120LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  v14 = v13(v12, string, 0, &v54);
  if ( v14 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1DA,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v14,
      cchResult);
  v55 = 0;
  v15 = v53;
  v16 = *(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)v53 + 96LL);
  v17 = CWinRTHelper::CStringRef::operator&(&v55);
  v18 = v16(v15, v54, v17);
  if ( v18 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v18,
      cchResult);
  *(_QWORD *)&v57[0].unused = 0;
  v20 = IEWinRTUtil::HStringToLPCWSTR(v55, v57, v19);
  if ( v20 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v20,
      cchResult);
  pszStr1[0] = 0;
  v21 = *((_QWORD *)this + 14);
  if ( a4 )
  {
    v23 = StringCchPrintfW(pszStr1, 0x825u, L"%ws_%ws_%ws", v21);
    if ( v23 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1F7,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
        (const char *)(unsigned int)v23,
        (int)a4);
  }
  else
  {
    cchResulta = v57[0].unused;
    v22 = StringCchPrintfW(pszStr1, 0x825u, L"%ws_%ws", v21);
    if ( v22 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1ED,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
        (const char *)(unsigned int)v22,
        cchResulta);
  }
  v24 = -1;
  do
    ++v24;
  while ( pszStr1[v24] );
  IsValidLocalStreamHost = CUriUtils::_IsValidLocalStreamHost(pszStr1, v24, *((unsigned __int16 **)this + 14), 0, 0);
  v26 = IsValidLocalStreamHost;
  if ( IsValidLocalStreamHost < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)IsValidLocalStreamHost,
      cchResultb);
LABEL_56:
    CWinRTHelper::CStringRef::Free((CWinRTHelper::CStringRef *)&v55);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    CWinRTHelper::CStringRef::Free((CWinRTHelper::CStringRef *)&string);
    return v26;
  }
  pwzBaseUrl[0] = 0;
  v27 = StringCchPrintfW(pwzBaseUrl, 0x825u, L"%ws://%ws/", L"ms-local-stream");
  if ( v27 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x201,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v27,
      (int)pszStr1);
  pszResult[0] = 0;
  v28 = CoInternetCombineUrl(pwzBaseUrl, a3, 0, pszResult, 0x825u, 0, 0);
  if ( v28 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x20E,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v28,
      cchResultc);
  ppURI = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppURI);
  v29 = CreateUri(pszResult, 0x3002B80u, 0, &ppURI);
  v26 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x212,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v29,
      cchResultc);
LABEL_55:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppURI);
    goto LABEL_56;
  }
  v50 = 0;
  v30 = ppURI;
  GetSchemeName = ppURI->lpVtbl->GetSchemeName;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v50,
    0);
  v32 = ((__int64 (__fastcall *)(IUri *, BSTR *))GetSchemeName)(v30, &v50);
  if ( v32 )
  {
    if ( v32 == 1 )
    {
      v34 = 542;
      goto LABEL_29;
    }
  }
  else
  {
    v33 = v50;
    if ( !v50 )
    {
      v34 = 537;
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
        (const char *)0x80070057LL,
        cchResultc);
LABEL_47:
      if ( v50 )
        SysFreeString(v50);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppURI);
      v26 = -2147024809;
      goto LABEL_56;
    }
    do
    {
      v35 = *(BSTR)((char *)v33 + (char *)L"ms-local-stream" - (char *)v50);
      v36 = *v33 - v35;
      if ( v36 )
        break;
      ++v33;
    }
    while ( v35 );
    if ( v36 )
    {
      v34 = 538;
      goto LABEL_29;
    }
  }
  bstrString = 0;
  v37 = ppURI;
  GetHost = ppURI->lpVtbl->GetHost;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &bstrString,
    0);
  v39 = ((__int64 (__fastcall *)(IUri *, BSTR *))GetHost)(v37, &bstrString);
  if ( v39 )
  {
    if ( v39 == 1 )
    {
      v41 = 554;
LABEL_45:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v41,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
        (const char *)0x80070057LL,
        cchResultc);
      if ( bstrString )
        SysFreeString(bstrString);
      goto LABEL_47;
    }
  }
  else
  {
    v40 = bstrString;
    if ( !bstrString )
    {
      v41 = 549;
      goto LABEL_45;
    }
    do
    {
      v42 = *(BSTR)((char *)v40 + (char *)pszStr1 - (char *)bstrString);
      v43 = *v40 - v42;
      if ( v43 )
        break;
      ++v40;
    }
    while ( v42 );
    if ( v43 )
    {
      v41 = 550;
      goto LABEL_45;
    }
  }
  v44 = ((__int64 (__fastcall *)(IUri *, unsigned __int16 **))ppURI->lpVtbl->GetAbsoluteUri)(ppURI, a5);
  v26 = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22D,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v44,
      cchResultc);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v50 )
      SysFreeString(v50);
    goto LABEL_55;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v50 )
    SysFreeString(v50);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppURI);
  CWinRTHelper::CStringRef::Free((CWinRTHelper::CStringRef *)&v55);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  CWinRTHelper::CStringRef::Free((CWinRTHelper::CStringRef *)&string);
  return 0;
}

```

## disassembly

```asm
0x180014f24  push    rbp
0x180014f26  push    rbx
0x180014f27  push    rsi
0x180014f28  push    rdi
0x180014f29  push    r12
0x180014f2b  push    r13
0x180014f2d  push    r14
0x180014f2f  push    r15
0x180014f31  lea     rbp, [rsp-3088h]
0x180014f39  mov     eax, 3188h
0x180014f3e  call    _alloca_probe
0x180014f43  sub     rsp, rax
0x180014f46  mov     rax, cs:__security_cookie
0x180014f4d  xor     rax, rsp
0x180014f50  mov     [rbp+30C0h+var_50], rax
0x180014f57  mov     r14, r9
0x180014f5a  mov     r15, r8
0x180014f5d  mov     rsi, rcx
0x180014f60  mov     r12, [rbp+30C0h+arg_20]
0x180014f67  xor     r13d, r13d
0x180014f6a  mov     [rsp+31C0h+string], r13
0x180014f6f  lea     rcx, [rsp+31C0h+string]; string
0x180014f74  call    ?CopyFromWideString@CStringRef@CWinRTHelper@@QEAAJPEBG@Z; CWinRTHelper::CStringRef::CopyFromWideString(ushort const *)
0x180014f79  mov     rcx, [rbp+30C8h]; this
0x180014f80  test    eax, eax
0x180014f82  jns     short loc_180014F99
0x180014f84  mov     r9d, eax; char *
0x180014f87  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180014f8e  mov     edx, 1CFh; void *
0x180014f93  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180014f99  mov     [rsp+31C0h+var_3168], r13
0x180014f9e  lea     rcx, [rsp+31C0h+var_3168]
0x180014fa3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014fa8  lea     r8, [rsp+31C0h+var_3168]; void **
0x180014fad  call    ?GetActivationFactory@CWinRTHelper@@SAJPEBGAEBU_GUID@@PEAPEAX@Z; CWinRTHelper::GetActivationFactory(ushort const *,_GUID const &,void * *)
0x180014fb2  mov     rcx, [rbp+30C8h]; this
0x180014fb9  test    eax, eax
0x180014fbb  jns     short loc_180014FD2
0x180014fbd  mov     r9d, eax; char *
0x180014fc0  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180014fc7  mov     edx, 1D4h; void *
0x180014fcc  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180014fd2  mov     [rsp+31C0h+var_3160], r13
0x180014fd7  mov     rdi, [rsp+31C0h+var_3168]
0x180014fdc  mov     rax, [rdi]
0x180014fdf  mov     rbx, [rax+78h]
0x180014fe3  lea     rcx, [rsp+31C0h+var_3160]
0x180014fe8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014fed  lea     r9, [rsp+31C0h+var_3160]
0x180014ff2  xor     r8d, r8d
0x180014ff5  mov     rdx, [rsp+31C0h+string]
0x180014ffa  mov     rcx, rdi
0x180014ffd  mov     rax, rbx
0x180015000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015005  mov     rcx, [rbp+30C8h]; this
0x18001500c  test    eax, eax
0x18001500e  jns     short loc_180015025
0x180015010  mov     r9d, eax; char *
0x180015013  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001501a  mov     edx, 1DAh; void *
0x18001501f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180015025  mov     [rsp+31C0h+var_3158], r13
0x18001502a  mov     rdi, [rsp+31C0h+var_3168]
0x18001502f  mov     rax, [rdi]
0x180015032  mov     rbx, [rax+60h]
0x180015036  lea     rcx, [rsp+31C0h+var_3158]
0x18001503b  call    ??ICStringRef@CWinRTHelper@@QEAAPEAPEAUHSTRING__@@XZ; CWinRTHelper::CStringRef::operator&(void)
0x180015040  mov     r8, rax
0x180015043  mov     rdx, [rsp+31C0h+var_3160]
0x180015048  mov     rcx, rdi
0x18001504b  mov     rax, rbx
0x18001504e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015053  mov     rcx, [rbp+30C8h]; this
0x18001505a  test    eax, eax
0x18001505c  jns     short loc_180015073
0x18001505e  mov     r9d, eax; char *
0x180015061  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180015068  mov     edx, 1DDh; void *
0x18001506d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180015073  mov     qword ptr [rsp+31C0h+var_3148.unused], r13
0x180015078  lea     rdx, [rsp+31C0h+var_3148]; HSTRING
0x18001507d  mov     rcx, [rsp+31C0h+var_3158]; this
0x180015082  call    ?HStringToLPCWSTR@IEWinRTUtil@@YAJPEAUHSTRING__@@PEAPEBG@Z; IEWinRTUtil::HStringToLPCWSTR(HSTRING__ *,ushort const * *)
0x180015087  mov     rcx, [rbp+30C8h]; this
0x18001508e  test    eax, eax
0x180015090  jns     short loc_1800150A7
0x180015092  mov     r9d, eax; char *
0x180015095  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001509c  mov     edx, 1E1h; void *
0x1800150a1  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800150a7  mov     [rbp+30C0h+pszStr1], r13w
0x1800150ac  mov     r9, [rsi+70h]
0x1800150b0  mov     rax, qword ptr [rsp+31C0h+var_3148.unused]
0x1800150b5  mov     edi, 825h
0x1800150ba  lea     rcx, [rbp+30C0h+pszStr1]; unsigned __int16 *
0x1800150be  mov     edx, edi; unsigned __int64
0x1800150c0  test    r14, r14
0x1800150c3  jnz     short loc_1800150F6
0x1800150c5  mov     qword ptr [rsp+31C0h+cchResult], rax; int
0x1800150ca  lea     r8, aWsWs; "%ws_%ws"
0x1800150d1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800150d6  mov     rcx, [rbp+30C8h]; this
0x1800150dd  test    eax, eax
0x1800150df  jns     short loc_18001512C
0x1800150e1  mov     r9d, eax; char *
0x1800150e4  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800150eb  mov     edx, 1EDh; void *
0x1800150f0  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800150f6  mov     [rsp+31C0h+pcchResult], rax
0x1800150fb  mov     qword ptr [rsp+31C0h+cchResult], r14; int
0x180015100  lea     r8, aWsWsWs; "%ws_%ws_%ws"
0x180015107  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001510c  mov     rcx, [rbp+30C8h]; this
0x180015113  test    eax, eax
0x180015115  jns     short loc_18001512C
0x180015117  mov     r9d, eax; char *
0x18001511a  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180015121  mov     edx, 1F7h; void *
0x180015126  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001512c  lea     rax, [rbp+30C0h+pszStr1]
0x180015130  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180015134  inc     rdx; unsigned __int64
0x180015137  cmp     [rax+rdx*2], r13w
0x18001513c  jnz     short loc_180015134
0x18001513e  mov     qword ptr [rsp+31C0h+cchResult], r13; int
0x180015143  xor     r9d, r9d; unsigned __int64
0x180015146  mov     r8, [rsi+70h]; unsigned __int16 *
0x18001514a  lea     rcx, [rbp+30C0h+pszStr1]; pszStr1
0x18001514e  call    ?_IsValidLocalStreamHost@CUriUtils@@CAJPEBG_KPEAG_KPEAH@Z; CUriUtils::_IsValidLocalStreamHost(ushort const *,unsigned __int64,ushort *,unsigned __int64,int *)
0x180015153  mov     ebx, eax
0x180015155  test    eax, eax
0x180015157  jns     short loc_180015179
0x180015159  mov     rcx, [rbp+30C8h]; this
0x180015160  mov     r9d, eax; char *
0x180015163  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001516a  mov     edx, 1FCh; void *
0x18001516f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015174  jmp     loc_180015419
0x180015179  mov     [rbp+30C0h+pwzBaseUrl], r13w
0x180015181  lea     rax, [rbp+30C0h+pszStr1]
0x180015185  mov     qword ptr [rsp+31C0h+cchResult], rax; int
0x18001518a  lea     rsi, aMsLocalStream_0; "ms-local-stream"
0x180015191  mov     r9, rsi
0x180015194  lea     r8, aWsWs_0; "%ws://%ws/"
0x18001519b  mov     rdx, rdi; unsigned __int64
0x18001519e  lea     rcx, [rbp+30C0h+pwzBaseUrl]; unsigned __int16 *
0x1800151a5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800151aa  mov     rcx, [rbp+30C8h]; this
0x1800151b1  test    eax, eax
0x1800151b3  jns     short loc_1800151CA
0x1800151b5  mov     r9d, eax; char *
0x1800151b8  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800151bf  mov     edx, 201h; void *
0x1800151c4  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800151ca  mov     [rbp+30C0h+pszResult], r13w
0x1800151d2  mov     [rsp+31C0h+dwReserved], r13d; dwReserved
0x1800151d7  mov     [rsp+31C0h+pcchResult], r13; pcchResult
0x1800151dc  mov     [rsp+31C0h+cchResult], edi; int
0x1800151e0  lea     r9, [rbp+30C0h+pszResult]; pszResult
0x1800151e7  xor     r8d, r8d; dwCombineFlags
0x1800151ea  mov     rdx, r15; pwzRelativeUrl
0x1800151ed  lea     rcx, [rbp+30C0h+pwzBaseUrl]; pwzBaseUrl
0x1800151f4  call    cs:__imp_CoInternetCombineUrl
0x1800151fa  mov     rcx, [rbp+30C8h]; this
0x180015201  test    eax, eax
0x180015203  jns     short loc_18001521A
0x180015205  mov     r9d, eax; char *
0x180015208  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001520f  mov     edx, 20Eh; void *
0x180015214  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001521a  mov     [rsp+31C0h+ppURI], r13
0x18001521f  lea     rcx, [rsp+31C0h+ppURI]
0x180015224  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180015229  lea     r9, [rsp+31C0h+ppURI]; ppURI
0x18001522e  xor     r8d, r8d; dwReserved
0x180015231  mov     edx, 3002B80h; dwFlags
0x180015236  lea     rcx, [rbp+30C0h+pszResult]; pwzURI
0x18001523d  call    cs:__imp_CreateUri
0x180015243  mov     ebx, eax
0x180015245  test    eax, eax
0x180015247  jns     short loc_180015269
0x180015249  mov     rcx, [rbp+30C8h]; this
0x180015250  mov     r9d, eax; char *
0x180015253  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001525a  mov     edx, 212h; void *
0x18001525f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015264  jmp     loc_18001540E
0x180015269  mov     [rsp+31C0h+var_3180], r13
0x18001526e  mov     rdi, [rsp+31C0h+ppURI]
0x180015273  mov     rax, [rdi]
0x180015276  mov     rbx, [rax+98h]
0x18001527d  xor     edx, edx
0x18001527f  lea     rcx, [rsp+31C0h+var_3180]
0x180015284  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015289  lea     rdx, [rsp+31C0h+var_3180]
0x18001528e  mov     rcx, rdi
0x180015291  mov     rax, rbx
0x180015294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015299  test    eax, eax
0x18001529b  jnz     short loc_1800152EB
0x18001529d  mov     rax, [rsp+31C0h+var_3180]
0x1800152a2  test    rax, rax
0x1800152a5  jnz     short loc_1800152CA
0x1800152a7  mov     edx, 219h; void *
0x1800152ac  mov     rcx, [rbp+30C8h]; this
0x1800152b3  mov     r9d, 80070057h; char *
0x1800152b9  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800152c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800152c5  jmp     loc_180015394
0x1800152ca  sub     rsi, rax
0x1800152cd  movzx   ecx, word ptr [rax]
0x1800152d0  movzx   edx, word ptr [rax+rsi]
0x1800152d4  sub     ecx, edx
0x1800152d6  jnz     short loc_1800152E0
0x1800152d8  add     rax, 2
0x1800152dc  test    edx, edx
0x1800152de  jnz     short loc_1800152CD
0x1800152e0  test    ecx, ecx
0x1800152e2  jz      short loc_1800152F7
0x1800152e4  mov     edx, 21Ah
0x1800152e9  jmp     short loc_1800152AC
0x1800152eb  cmp     eax, 1
0x1800152ee  jnz     short loc_1800152F7
0x1800152f0  mov     edx, 21Eh
0x1800152f5  jmp     short loc_1800152AC
0x1800152f7  mov     [rsp+31C0h+bstrString], r13
0x1800152fc  mov     rdi, [rsp+31C0h+ppURI]
0x180015301  mov     rax, [rdi]
0x180015304  mov     rbx, [rax+68h]
0x180015308  xor     edx, edx
0x18001530a  lea     rcx, [rsp+31C0h+bstrString]
0x18001530f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015314  lea     rdx, [rsp+31C0h+bstrString]
0x180015319  mov     rcx, rdi
0x18001531c  mov     rax, rbx
0x18001531f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015324  test    eax, eax
0x180015326  jnz     short loc_18001535F
0x180015328  mov     rax, [rsp+31C0h+bstrString]
0x18001532d  test    rax, rax
0x180015330  jnz     short loc_180015339
0x180015332  mov     edx, 225h
0x180015337  jmp     short loc_180015369
0x180015339  lea     r8, [rbp+30C0h+pszStr1]
0x18001533d  sub     r8, rax
0x180015340  movzx   ecx, word ptr [rax]
0x180015343  movzx   edx, word ptr [rax+r8]
0x180015348  sub     ecx, edx
0x18001534a  jnz     short loc_180015354
0x18001534c  add     rax, 2
0x180015350  test    edx, edx
0x180015352  jnz     short loc_180015340
0x180015354  test    ecx, ecx
0x180015356  jz      short loc_1800153B6
0x180015358  mov     edx, 226h
0x18001535d  jmp     short loc_180015369
0x18001535f  cmp     eax, 1
0x180015362  jnz     short loc_1800153B6
0x180015364  mov     edx, 22Ah; void *
0x180015369  mov     r9d, 80070057h; char *
0x18001536f  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180015376  mov     rcx, [rbp+30C8h]; this
0x18001537d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015382  nop
0x180015383  mov     rcx, [rsp+31C0h+bstrString]; bstrString
0x180015388  test    rcx, rcx
0x18001538b  jz      short loc_180015394
0x18001538d  call    cs:__imp_SysFreeString
0x180015393  nop
0x180015394  mov     rcx, [rsp+31C0h+var_3180]; bstrString
0x180015399  test    rcx, rcx
0x18001539c  jz      short loc_1800153A5
0x18001539e  call    cs:__imp_SysFreeString
0x1800153a4  nop
0x1800153a5  lea     rcx, [rsp+31C0h+ppURI]
0x1800153aa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800153af  mov     ebx, 80070057h
0x1800153b4  jmp     short loc_180015419
0x1800153b6  mov     rcx, [rsp+31C0h+ppURI]
0x1800153bb  mov     rax, [rcx]
0x1800153be  mov     rdx, r12
0x1800153c1  mov     rax, [rax+38h]
0x1800153c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153ca  mov     ebx, eax
0x1800153cc  test    eax, eax
0x1800153ce  jns     short loc_180015448
0x1800153d0  mov     rcx, [rbp+30C8h]; this
0x1800153d7  mov     r9d, eax; char *
0x1800153da  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800153e1  mov     edx, 22Dh; void *
0x1800153e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800153eb  nop
0x1800153ec  mov     rcx, [rsp+31C0h+bstrString]; bstrString
0x1800153f1  test    rcx, rcx
0x1800153f4  jz      short loc_1800153FD
0x1800153f6  call    cs:__imp_SysFreeString
0x1800153fc  nop
0x1800153fd  mov     rcx, [rsp+31C0h+var_3180]; bstrString
0x180015402  test    rcx, rcx
0x180015405  jz      short loc_18001540E
  ... truncated ...
```
