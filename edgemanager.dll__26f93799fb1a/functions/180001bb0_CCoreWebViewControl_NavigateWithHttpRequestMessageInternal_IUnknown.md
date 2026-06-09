# CCoreWebViewControl::NavigateWithHttpRequestMessageInternal(IUnknown *)

- ea: `0x180001bb0`
- end: `0x18000278d`
- name: `?NavigateWithHttpRequestMessageInternal@CCoreWebViewControl@@AEAAJPEAUIUnknown@@@Z`
- size: `3037`
- prototype: `__int64 __fastcall(CCoreWebViewControl *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180001b10`

## callees

- `0x180001bb0`
- `0x1800027a0`
- `0x18000b0ec`
- `0x18000deac`
- `0x1800154cc`
- `0x1800163b4`
- `0x18001d850`
- `0x18002b530`
- `0x180035b88`
- `0x180073098`
- `0x180081754`
- `0x180085010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000215d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000215d`
- `iertutil!CreateUri` at `0x1800022c9`
- `iertutil!CreateUri` at `0x1800022c9`
- `OLEAUT32!__imp_SysAllocString` at `0x180001e9f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000209a`
- `OLEAUT32!__imp_SysAllocString` at `0x180001e9f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000209a`
- `OLEAUT32!__imp_SysFreeString` at `0x180001f22`
- `OLEAUT32!__imp_SysFreeString` at `0x1800021f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180002274`
- `OLEAUT32!__imp_SysFreeString` at `0x18000235b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800023cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000251b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800025e5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800026c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800026f7`
- `OLEAUT32!__imp_SysFreeString` at `0x180001f22`
- `OLEAUT32!__imp_SysFreeString` at `0x1800021f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180002274`
- `OLEAUT32!__imp_SysFreeString` at `0x18000235b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800023cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000251b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800025e5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800026c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800026f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001d8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001e70`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001fc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000206b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001d8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001e70`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001fc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000206b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001d02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001ebb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800020b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002212`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000252b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800025f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002707`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001d02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001ebb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800020b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002212`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000252b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800025f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002707`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall CCoreWebViewControl::NavigateWithHttpRequestMessageInternal(
        CCoreWebViewControl *this,
        struct IUnknown *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  HRESULT v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rcx
  HSTRING v15; // rbx
  FARPROC ProcAddress; // rax
  HMODULE WinRTStringLib; // rax
  OLECHAR *v18; // r14
  int v19; // edi
  IUri *v20; // rbx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64); // rbx
  __int64 v23; // rax
  FARPROC v24; // rax
  HMODULE v25; // rax
  const OLECHAR *v26; // rax
  HRESULT v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rdi
  int v30; // ebx
  struct IUriVtbl *lpVtbl; // rax
  HSTRING v32; // rbx
  FARPROC v33; // rax
  HMODULE v34; // rax
  const wchar_t *v35; // rsi
  wchar_t *v36; // r15
  IUri *v37; // rdi
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, __int64); // rbx
  __int64 v40; // rax
  FARPROC v41; // rax
  HMODULE v42; // rax
  const OLECHAR *v43; // rax
  HRESULT v44; // eax
  __int64 v45; // rcx
  __int64 v46; // rax
  int v47; // edx
  int v48; // edx
  wchar_t *v49; // rax
  unsigned __int64 v50; // rax
  wchar_t *v51; // rcx
  __int64 v52; // rdx
  unsigned __int16 *v53; // r8
  unsigned __int16 v54; // r9
  unsigned __int16 *v55; // rcx
  HRESULT v56; // eax
  IUri *v57; // rcx
  bool v58; // di
  HRESULT v59; // eax
  int v60; // ebx
  HRESULT (__stdcall *GetSchemeName)(IUri *, BSTR *); // rax
  int v62; // eax
  OLECHAR *v63; // rsi
  __int64 v64; // rdx
  int v65; // eax
  OLECHAR *v66; // rsi
  int v67; // eax
  IUri *v68; // rcx
  IUri *v69; // rcx
  HRESULT v70; // eax
  _QWORD *v71; // rcx
  __int64 v72; // rcx
  int v73; // eax
  unsigned int v74; // ebx
  HRESULT v75; // eax
  _QWORD *v76; // rcx
  __int64 v77; // rcx
  _QWORD *v78; // rbx
  int v79; // eax
  unsigned int v80; // ebx
  HRESULT v81; // eax
  _QWORD *v82; // rcx
  __int64 v83; // rcx
  int v84; // [rsp+20h] [rbp-99h]
  int v85; // [rsp+20h] [rbp-99h]
  int v86; // [rsp+20h] [rbp-99h]
  int v87; // [rsp+20h] [rbp-99h]
  IUri *ppURI; // [rsp+30h] [rbp-89h] BYREF
  __int64 v89; // [rsp+38h] [rbp-81h] BYREF
  HSTRING string; // [rsp+40h] [rbp-79h] BYREF
  _QWORD *v91; // [rsp+48h] [rbp-71h] BYREF
  __int64 v92; // [rsp+50h] [rbp-69h] BYREF
  IUri *v93; // [rsp+58h] [rbp-61h] BYREF
  HSTRING v94; // [rsp+60h] [rbp-59h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-51h] BYREF
  OLECHAR *v96; // [rsp+70h] [rbp-49h]
  unsigned __int16 v97[40]; // [rsp+80h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v89 = 0;
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_f5762b3c_74d4_4811_b5dc_9f8b4e2f9abf,
         &v89);
  v5 = v4;
  if ( v4 == -2147467262 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x197,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)0x80070057LL,
      v84);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    return 2147942487LL;
  }
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v4,
      v84);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    return v5;
  }
  v91 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v89 + 72LL))(v89, &v91);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A0,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v7,
      v84);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    return v8;
  }
  string = 0;
  v9 = *v91;
  string = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v9 + 48))(v91, &string);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v10,
      v84);
    if ( string )
    {
      v12 = WindowsDeleteString(string);
      if ( v12 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"onecoreuap\\inetcore\\lib\\corewebviewhelpers\\winrthelper.inl",
          (const char *)(unsigned int)v12,
          v85);
      string = 0;
    }
    v13 = v91;
    if ( v91 )
    {
      v91 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
    }
    v14 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return v11;
  }
  v15 = string;
  ProcAddress = (FARPROC)qword_1800B6D48;
  if ( !qword_1800B6D48 )
  {
    WinRTStringLib = (HMODULE)GetWinRTStringLib();
    if ( WinRTStringLib )
    {
      ProcAddress = GetProcAddress(WinRTStringLib, "WindowsGetStringRawBuffer");
      qword_1800B6D48 = (__int64)ProcAddress;
    }
    else
    {
      ProcAddress = (FARPROC)qword_1800B6D48;
    }
    if ( !ProcAddress )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
        (const char *)0x80004001LL,
        v84);
      CWinRTHelper::CStringRef::Free((CWinRTHelper::CStringRef *)&string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
      return 2147500033LL;
    }
  }
  ((void (__fastcall *)(HSTRING, _QWORD))ProcAddress)(v15, 0);
  v18 = 0;
  v96 = 0;
  v92 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v89 + 96LL))(v89, &v92);
  v20 = 0;
  ppURI = 0;
  if ( v19 >= 0 )
  {
    v21 = v92;
    v22 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v92 + 48LL);
    v23 = CWinRTHelper::CStringRef::operator&(&ppURI);
    v19 = v22(v21, v23);
    v20 = ppURI;
  }
  if ( v19 >= 0 )
  {
    v24 = (FARPROC)qword_1800B6D48;
    if ( qword_1800B6D48
      || ((v25 = (HMODULE)GetWinRTStringLib()) == 0
        ? (v24 = (FARPROC)qword_1800B6D48)
        : (FARPROC)(v24 = GetProcAddress(v25, "WindowsGetStringRawBuffer"), qword_1800B6D48 = (__int64)v24),
          v24) )
    {
      v26 = (const OLECHAR *)((__int64 (__fastcall *)(IUri *, _QWORD))v24)(v20, 0);
      v18 = SysAllocString(v26);
      v96 = v18;
      v19 = 0;
    }
    else
    {
      v19 = -2147467263;
    }
    v20 = ppURI;
  }
  if ( v20 )
  {
    v27 = WindowsDeleteString((HSTRING)v20);
    if ( v27 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\inetcore\\lib\\corewebviewhelpers\\winrthelper.inl",
        (const char *)(unsigned int)v27,
        v84);
    ppURI = 0;
  }
  v28 = v92;
  if ( v92 )
  {
    v92 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v19,
      v84);
    if ( v18 )
      SysFreeString(v18);
    CWinRTHelper::CStringRef::Free((CWinRTHelper::CStringRef *)&string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    return (unsigned int)v19;
  }
  v29 = v89;
  v93 = 0;
  v30 = (*(__int64 (__fastcall **)(__int64, IUri **))(*(_QWORD *)v89 + 72LL))(v89, &v93);
  if ( v30 >= 0 )
  {
    v94 = 0;
    lpVtbl = v93->lpVtbl;
    v94 = 0;
    v30 = ((__int64 (__fastcall *)(IUri *, HSTRING *))lpVtbl->HasProperty)(v93, &v94);
    if ( v30 >= 0 )
    {
      v32 = v94;
      v33 = (FARPROC)qword_1800B6D48;
      if ( qword_1800B6D48
        || ((v34 = (HMODULE)GetWinRTStringLib()) == 0
          ? (v33 = (FARPROC)qword_1800B6D48)
          : (FARPROC)(v33 = GetProcAddress(v34, "WindowsGetStringRawBuffer"), qword_1800B6D48 = (__int64)v33),
            v33) )
      {
        v35 = (const wchar_t *)((__int64 (__fastcall *)(HSTRING, _QWORD))v33)(v32, 0);
        v36 = 0;
        v92 = 0;
        v30 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 96LL))(v29, &v92);
        v37 = 0;
        ppURI = 0;
        if ( v30 >= 0 )
        {
          v38 = v92;
          v39 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v92 + 48LL);
          v40 = CWinRTHelper::CStringRef::operator&(&ppURI);
          v30 = v39(v38, v40);
          v37 = ppURI;
        }
        if ( v30 >= 0 )
        {
          v41 = (FARPROC)qword_1800B6D48;
          if ( qword_1800B6D48
            || ((v42 = (HMODULE)GetWinRTStringLib()) == 0
              ? (v41 = (FARPROC)qword_1800B6D48)
              : (FARPROC)(v41 = GetProcAddress(v42, "WindowsGetStringRawBuffer"), qword_1800B6D48 = (__int64)v41),
                v41) )
          {
            v43 = (const OLECHAR *)((__int64 (__fastcall *)(IUri *, _QWORD))v41)(v37, 0);
            v36 = SysAllocString(v43);
            v30 = 0;
          }
          else
          {
            v30 = -2147467263;
          }
          v37 = ppURI;
        }
        if ( v37 )
        {
          v44 = WindowsDeleteString((HSTRING)v37);
          if ( v44 < 0 )
            wil::details::in1diag3::_FailFast_Hr(
              retaddr,
              (void *)0x66,
              (unsigned int)"onecoreuap\\inetcore\\lib\\corewebviewhelpers\\winrthelper.inl",
              (const char *)(unsigned int)v44,
              v84);
          ppURI = 0;
        }
        v45 = v92;
        if ( v92 )
        {
          v92 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        }
        if ( v30 >= 0 )
        {
          v46 = 0;
          do
          {
            v47 = v35[v46++];
            v48 = v47 - aPost[v46 - 1];
          }
          while ( !v48 && v46 != 5 );
          if ( v48 )
          {
            if ( wcscmp_0(v35, L"GET") )
              v30 = -2147024809;
          }
          else
          {
            memset(v97, 0, 66);
            v49 = wcschr(v36, 0x3Au);
            if ( v49 )
            {
              v50 = v49 - v36;
              if ( v50 <= 0x7FFFFFFE )
              {
                v51 = v36;
                v52 = 32;
                v53 = v97;
                do
                {
                  if ( !v50 )
                    break;
                  v54 = *v51;
                  if ( !*v51 )
                    break;
                  ++v51;
                  *v53++ = v54;
                  --v50;
                  --v52;
                }
                while ( v52 );
                v55 = v53 - 1;
                if ( v52 )
                  v55 = v53;
                *v55 = 0;
                if ( v52
                  && (unsigned int)CUriUtils::_IsAsciiStringInList(
                                     v97,
                                     (const unsigned __int16 *const *const)&off_1800B6210,
                                     3u) )
                {
                  v30 = -2147024809;
                }
              }
            }
          }
          SysFreeString(v36);
        }
      }
      else
      {
        v30 = -2147467263;
      }
    }
    if ( v94 )
    {
      v56 = WindowsDeleteString(v94);
      if ( v56 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"onecoreuap\\inetcore\\lib\\corewebviewhelpers\\winrthelper.inl",
          (const char *)(unsigned int)v56,
          v84);
    }
  }
  v57 = v93;
  if ( v93 )
  {
    v93 = 0;
    ((void (__fastcall *)(IUri *))v57->lpVtbl->Release)(v57);
  }
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AC,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)0x80070057LL,
      v84);
    if ( v18 )
      SysFreeString(v18);
    CWinRTHelper::CStringRef::Free((CWinRTHelper::CStringRef *)&string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    return 2147942487LL;
  }
  LODWORD(v92) = 0;
  v58 = 0;
  v93 = 0;
  if ( !v18 )
    goto LABEL_128;
  ppURI = 0;
  v59 = CreateUri(v18, 0x3002B80u, 0, &ppURI);
  v60 = v59;
  if ( v59 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B5,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v59,
      v84);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppURI);
    goto LABEL_127;
  }
  bstrString = 0;
  GetSchemeName = ppURI->lpVtbl->GetSchemeName;
  if ( *((_BYTE *)this + 145) )
  {
    v62 = ((__int64 (__fastcall *)(IUri *, BSTR *))GetSchemeName)(ppURI, &bstrString);
    v63 = bstrString;
    if ( v62 )
    {
      v60 = -2147418113;
    }
    else
    {
      v60 = -2147467260;
      if ( (unsigned int)CUriUtils::_IsAsciiStringInList(
                           bstrString,
                           (const unsigned __int16 *const *const)&off_1800B61A0,
                           9u) )
        v60 = 0;
    }
    if ( v63 )
      SysFreeString(v63);
    if ( v60 < 0 )
    {
      v64 = 696;
LABEL_110:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v64,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
        (const char *)(unsigned int)v60,
        v84);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppURI);
      goto LABEL_127;
    }
  }
  else
  {
    v65 = ((__int64 (__fastcall *)(IUri *, BSTR *))GetSchemeName)(ppURI, &bstrString);
    v66 = bstrString;
    if ( v65 )
    {
      v60 = -2147418113;
    }
    else
    {
      v60 = -2147467260;
      if ( (unsigned int)CUriUtils::_IsAsciiStringInList(
                           bstrString,
                           (const unsigned __int16 *const *const)&off_1800B6160,
                           8u) )
        v60 = 0;
    }
    if ( v66 )
      SysFreeString(v66);
    if ( v60 < 0 )
    {
      v64 = 700;
      goto LABEL_110;
    }
  }
  LODWORD(v94) = 0;
  v67 = (*(__int64 (__fastcall **)(_QWORD, IUri *, HSTRING *))(**((_QWORD **)this + 6) + 520LL))(
          *((_QWORD *)this + 6),
          ppURI,
          &v94);
  v60 = v67;
  if ( v67 >= 0 )
  {
    if ( (_DWORD)v94 )
    {
      v93 = ppURI;
      v60 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C8,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
        (const char *)0x80070057LL,
        v84);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppURI);
      v60 = -2147024809;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C0,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v67,
      v84);
    v68 = ppURI;
    if ( ppURI )
    {
      ppURI = 0;
      ((void (__fastcall *)(IUri *))v68->lpVtbl->Release)(v68);
    }
  }
LABEL_127:
  if ( v60 >= 0 )
  {
LABEL_128:
    memset(&v97[4], 0, 56);
    *(_QWORD *)v97 = v93;
    v60 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64 *))(**((_QWORD **)this + 7) + 24LL))(
            *((_QWORD *)this + 7),
            *((_QWORD *)this + 6),
            v97,
            &v92);
    if ( v60 >= 0 )
      v58 = (_DWORD)v92 == 0;
  }
  v69 = v93;
  if ( v93 )
  {
    v93 = 0;
    ((void (__fastcall *)(IUri *))v69->lpVtbl->Release)(v69);
  }
  if ( v58 )
  {
    v73 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 472LL))(*((_QWORD *)this + 6));
    v74 = v73;
    if ( v73 >= 0 )
    {
      v78 = (_QWORD *)*((_QWORD *)this + 16);
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<CoreWebviewPermissionContextEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::shared_ptr<CoreWebviewPermissionContextEntry>>,void *>>>(
        (char *)this + 128,
        (char *)this + 128,
        v78[1]);
      v78[1] = v78;
      *v78 = v78;
      v78[2] = v78;
      *((_QWORD *)this + 17) = 0;
      v79 = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown *))(**((_QWORD **)this + 6) + 208LL))(
              *((_QWORD *)this + 6),
              a2);
      v80 = v79;
      if ( v79 >= 0 )
      {
        if ( v18 )
          SysFreeString(v18);
        if ( string )
        {
          v81 = WindowsDeleteString(string);
          if ( v81 < 0 )
            wil::details::in1diag3::_FailFast_Hr(
              retaddr,
              (void *)0x66,
              (unsigned int)"onecoreuap\\inetcore\\lib\\corewebviewhelpers\\winrthelper.inl",
              (const char *)(unsigned int)v81,
              v84);
          string = 0;
        }
        v82 = v91;
        if ( v91 )
        {
          v91 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v82 + 16LL))(v82);
        }
        v83 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
        }
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B2,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
          (const char *)(unsigned int)v79,
          v84);
        if ( v18 )
          SysFreeString(v18);
        CWinRTHelper::CStringRef::Free((CWinRTHelper::CStringRef *)&string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
        return v80;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D7,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
        (const char *)(unsigned int)v73,
        v84);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
        (const char *)v74,
        v86);
      if ( v18 )
        SysFreeString(v18);
      if ( string )
      {
        v75 = WindowsDeleteString(string);
        if ( v75 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x66,
            (unsigned int)"onecoreuap\\inetcore\\lib\\corewebviewhelpers\\winrthelper.inl",
            (const char *)(unsigned int)v75,
            v87);
        string = 0;
      }
      v76 = v91;
      if ( v91 )
      {
        v91 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v76 + 16LL))(v76);
      }
      v77 = v89;
      if ( v89 )
      {
        v89 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
      }
      return v74;
    }
  }
  else
  {
    if ( v60 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AE,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
        (const char *)(unsigned int)v60,
        v84);
    if ( v18 )
      SysFreeString(v18);
    if ( string )
    {
      v70 = WindowsDeleteString(string);
      if ( v70 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"onecoreuap\\inetcore\\lib\\corewebviewhelpers\\winrthelper.inl",
          (const char *)(unsigned int)v70,
          v84);
      string = 0;
    }
    v71 = v91;
    if ( v91 )
    {
      v91 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v71 + 16LL))(v71);
    }
    v72 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    }
    return (unsigned int)v60;
  }
}

```

## disassembly

```asm
0x180001bb0  mov     [rsp-8+arg_10], rbx
0x180001bb5  push    rbp
0x180001bb6  push    rsi
0x180001bb7  push    rdi
0x180001bb8  push    r12
0x180001bba  push    r13
0x180001bbc  push    r14
0x180001bbe  push    r15
0x180001bc0  lea     rbp, [rsp-27h]
0x180001bc5  sub     rsp, 0E0h
0x180001bcc  mov     rax, cs:__security_cookie
0x180001bd3  xor     rax, rsp
0x180001bd6  mov     [rbp+57h+var_40], rax
0x180001bda  mov     r12, rdx
0x180001bdd  mov     r13, rcx
0x180001be0  xor     esi, esi
0x180001be2  mov     [rsp+110h+var_D8], rsi
0x180001be7  mov     rax, [rdx]
0x180001bea  lea     r8, [rsp+110h+var_D8]
0x180001bef  lea     rdx, _GUID_f5762b3c_74d4_4811_b5dc_9f8b4e2f9abf
0x180001bf6  mov     rcx, r12
0x180001bf9  mov     rax, [rax]
0x180001bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c01  mov     ebx, eax
0x180001c03  cmp     eax, 80004002h
0x180001c08  jnz     short loc_180001C39
0x180001c0a  mov     rcx, [rbp+5Fh]; this
0x180001c0e  mov     edi, 80070057h
0x180001c13  mov     r9d, edi; char *
0x180001c16  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180001c1d  mov     edx, 197h; void *
0x180001c22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001c27  nop
0x180001c28  lea     rcx, [rsp+110h+var_D8]
0x180001c2d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180001c32  mov     eax, edi
0x180001c34  jmp     loc_180002766
0x180001c39  test    ebx, ebx
0x180001c3b  jns     short loc_180001C67
0x180001c3d  mov     rcx, [rbp+5Fh]; this
0x180001c41  mov     r9d, ebx; char *
0x180001c44  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180001c4b  mov     edx, 19Bh; void *
0x180001c50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001c55  nop
0x180001c56  lea     rcx, [rsp+110h+var_D8]
0x180001c5b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180001c60  mov     eax, ebx
0x180001c62  jmp     loc_180002766
0x180001c67  mov     [rbp+57h+var_C8], rsi
0x180001c6b  mov     rcx, [rsp+110h+var_D8]
0x180001c70  mov     rax, [rcx]
0x180001c73  lea     rdx, [rbp+57h+var_C8]
0x180001c77  mov     rax, [rax+48h]
0x180001c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c80  mov     ebx, eax
0x180001c82  test    eax, eax
0x180001c84  jns     short loc_180001CBA
0x180001c86  mov     rcx, [rbp+5Fh]; this
0x180001c8a  mov     r9d, eax; char *
0x180001c8d  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180001c94  mov     edx, 1A0h; void *
0x180001c99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001c9e  nop
0x180001c9f  lea     rcx, [rbp+57h+var_C8]
0x180001ca3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180001ca8  nop
0x180001ca9  lea     rcx, [rsp+110h+var_D8]
0x180001cae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180001cb3  mov     eax, ebx
0x180001cb5  jmp     loc_180002766
0x180001cba  mov     [rbp+57h+string], rsi
0x180001cbe  mov     rcx, [rbp+57h+var_C8]
0x180001cc2  mov     rax, [rcx]
0x180001cc5  mov     [rbp+57h+string], rsi
0x180001cc9  lea     rdx, [rbp+57h+string]
0x180001ccd  mov     rax, [rax+30h]
0x180001cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cd6  mov     ebx, eax
0x180001cd8  test    eax, eax
0x180001cda  jns     loc_180001D66
0x180001ce0  mov     rcx, [rbp+5Fh]; this
0x180001ce4  mov     r9d, eax; char *
0x180001ce7  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180001cee  mov     edx, 1A3h; void *
0x180001cf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001cf8  nop
0x180001cf9  mov     rcx, [rbp+57h+string]; string
0x180001cfd  test    rcx, rcx
0x180001d00  jz      short loc_180001D29
0x180001d02  call    cs:__imp_WindowsDeleteString
0x180001d08  mov     rcx, [rbp+5Fh]; this
0x180001d0c  test    eax, eax
0x180001d0e  jns     short loc_180001D25
0x180001d10  mov     r9d, eax; char *
0x180001d13  lea     r8, aOnecoreuapInet_18; "onecoreuap\\inetcore\\lib\\corewebviewh"...
0x180001d1a  mov     edx, 66h ; 'f'; void *
0x180001d1f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180001d25  mov     [rbp+57h+string], rsi
0x180001d29  mov     rcx, [rbp+57h+var_C8]
0x180001d2d  test    rcx, rcx
0x180001d30  jz      short loc_180001D43
0x180001d32  mov     [rbp+57h+var_C8], rsi
0x180001d36  mov     rax, [rcx]
0x180001d39  mov     rax, [rax+10h]
0x180001d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d42  nop
0x180001d43  mov     rcx, [rsp+110h+var_D8]
0x180001d48  test    rcx, rcx
0x180001d4b  jz      short loc_180001D5F
0x180001d4d  mov     [rsp+110h+var_D8], rsi
0x180001d52  mov     rax, [rcx]
0x180001d55  mov     rax, [rax+10h]
0x180001d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d5e  nop
0x180001d5f  mov     eax, ebx
0x180001d61  jmp     loc_180002766
0x180001d66  mov     rbx, [rbp+57h+string]
0x180001d6a  mov     rax, cs:qword_1800B6D48
0x180001d71  test    rax, rax
0x180001d74  jnz     short loc_180001DE9
0x180001d76  call    GetWinRTStringLib
0x180001d7b  test    rax, rax
0x180001d7e  jz      short loc_180001D99
0x180001d80  lea     rdx, ProcName; "WindowsGetStringRawBuffer"
0x180001d87  mov     rcx, rax; hModule
0x180001d8a  call    cs:__imp_GetProcAddress
0x180001d90  mov     cs:qword_1800B6D48, rax
0x180001d97  jmp     short loc_180001DA0
0x180001d99  mov     rax, cs:qword_1800B6D48
0x180001da0  test    rax, rax
0x180001da3  jnz     short loc_180001DE9
0x180001da5  mov     rcx, [rbp+5Fh]; this
0x180001da9  mov     r9d, 80004001h; char *
0x180001daf  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180001db6  mov     edx, 1A6h; void *
0x180001dbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001dc0  nop
0x180001dc1  lea     rcx, [rbp+57h+string]; this
0x180001dc5  call    ?Free@CStringRef@CWinRTHelper@@QEAAXXZ; CWinRTHelper::CStringRef::Free(void)
0x180001dca  nop
0x180001dcb  lea     rcx, [rbp+57h+var_C8]
0x180001dcf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180001dd4  nop
0x180001dd5  lea     rcx, [rsp+110h+var_D8]
0x180001dda  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180001ddf  mov     eax, 80004001h
0x180001de4  jmp     loc_180002766
0x180001de9  xor     edx, edx
0x180001deb  mov     rcx, rbx
0x180001dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001df3  nop
0x180001df4  mov     r14, rsi
0x180001df7  mov     [rbp+57h+var_A0], rsi
0x180001dfb  mov     rcx, [rsp+110h+var_D8]
0x180001e00  mov     [rbp+57h+var_C0], rsi
0x180001e04  mov     rax, [rcx]
0x180001e07  lea     rdx, [rbp+57h+var_C0]
0x180001e0b  mov     rax, [rax+60h]
0x180001e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e14  mov     edi, eax
0x180001e16  mov     rbx, rsi
0x180001e19  mov     [rsp+110h+ppURI], rbx
0x180001e1e  test    eax, eax
0x180001e20  js      short loc_180001E4C
0x180001e22  mov     rdi, [rbp+57h+var_C0]
0x180001e26  mov     rax, [rdi]
0x180001e29  mov     rbx, [rax+30h]
0x180001e2d  lea     rcx, [rsp+110h+ppURI]
0x180001e32  call    ??ICStringRef@CWinRTHelper@@QEAAPEAPEAUHSTRING__@@XZ; CWinRTHelper::CStringRef::operator&(void)
0x180001e37  mov     rdx, rax
0x180001e3a  mov     rcx, rdi
0x180001e3d  mov     rax, rbx
0x180001e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e45  mov     edi, eax
0x180001e47  mov     rbx, [rsp+110h+ppURI]
0x180001e4c  test    edi, edi
0x180001e4e  js      short loc_180001EB3
0x180001e50  mov     rax, cs:qword_1800B6D48
0x180001e57  test    rax, rax
0x180001e5a  jnz     short loc_180001E92
0x180001e5c  call    GetWinRTStringLib
0x180001e61  test    rax, rax
0x180001e64  jz      short loc_180001E7F
0x180001e66  lea     rdx, ProcName; "WindowsGetStringRawBuffer"
0x180001e6d  mov     rcx, rax; hModule
0x180001e70  call    cs:__imp_GetProcAddress
0x180001e76  mov     cs:qword_1800B6D48, rax
0x180001e7d  jmp     short loc_180001E86
0x180001e7f  mov     rax, cs:qword_1800B6D48
0x180001e86  test    rax, rax
0x180001e89  jnz     short loc_180001E92
0x180001e8b  mov     edi, 80004001h
0x180001e90  jmp     short loc_180001EAE
0x180001e92  xor     edx, edx
0x180001e94  mov     rcx, rbx
0x180001e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e9c  mov     rcx, rax; psz
0x180001e9f  call    cs:__imp_SysAllocString
0x180001ea5  mov     r14, rax
0x180001ea8  mov     [rbp+57h+var_A0], rax
0x180001eac  mov     edi, esi
0x180001eae  mov     rbx, [rsp+110h+ppURI]
0x180001eb3  test    rbx, rbx
0x180001eb6  jz      short loc_180001EE3
0x180001eb8  mov     rcx, rbx; string
0x180001ebb  call    cs:__imp_WindowsDeleteString
0x180001ec1  mov     rcx, [rbp+5Fh]; this
0x180001ec5  test    eax, eax
0x180001ec7  jns     short loc_180001EDE
0x180001ec9  mov     r9d, eax; char *
0x180001ecc  lea     r8, aOnecoreuapInet_18; "onecoreuap\\inetcore\\lib\\corewebviewh"...
0x180001ed3  mov     edx, 66h ; 'f'; void *
0x180001ed8  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180001ede  mov     [rsp+110h+ppURI], rsi
0x180001ee3  mov     rcx, [rbp+57h+var_C0]
0x180001ee7  test    rcx, rcx
0x180001eea  jz      short loc_180001EFD
0x180001eec  mov     [rbp+57h+var_C0], rsi
0x180001ef0  mov     rax, [rcx]
0x180001ef3  mov     rax, [rax+10h]
0x180001ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001efc  nop
0x180001efd  test    edi, edi
0x180001eff  jns     short loc_180001F4E
0x180001f01  mov     rcx, [rbp+5Fh]; this
0x180001f05  mov     r9d, edi; char *
0x180001f08  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180001f0f  mov     edx, 1AAh; void *
0x180001f14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001f19  nop
0x180001f1a  test    r14, r14
0x180001f1d  jz      short loc_180001F29
0x180001f1f  mov     rcx, r14; bstrString
0x180001f22  call    cs:__imp_SysFreeString
0x180001f28  nop
0x180001f29  lea     rcx, [rbp+57h+string]; this
0x180001f2d  call    ?Free@CStringRef@CWinRTHelper@@QEAAXXZ; CWinRTHelper::CStringRef::Free(void)
0x180001f32  nop
0x180001f33  lea     rcx, [rbp+57h+var_C8]
0x180001f37  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180001f3c  nop
0x180001f3d  lea     rcx, [rsp+110h+var_D8]
0x180001f42  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180001f47  mov     eax, edi
0x180001f49  jmp     loc_180002766
0x180001f4e  mov     rdi, [rsp+110h+var_D8]
0x180001f53  mov     [rbp+57h+var_B8], rsi
0x180001f57  mov     rax, [rdi]
0x180001f5a  lea     rdx, [rbp+57h+var_B8]
0x180001f5e  mov     rcx, rdi
0x180001f61  mov     rax, [rax+48h]
0x180001f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f6a  mov     ebx, eax
0x180001f6c  mov     r15d, 80070057h
0x180001f72  test    eax, eax
0x180001f74  js      loc_180002235
0x180001f7a  mov     [rbp+57h+var_B0], rsi
0x180001f7e  mov     rcx, [rbp+57h+var_B8]
0x180001f82  mov     rax, [rcx]
0x180001f85  mov     [rbp+57h+var_B0], rsi
0x180001f89  lea     rdx, [rbp+57h+var_B0]
0x180001f8d  mov     rax, [rax+30h]
0x180001f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f96  mov     ebx, eax
0x180001f98  test    eax, eax
0x180001f9a  js      loc_180002209
0x180001fa0  mov     rbx, [rbp+57h+var_B0]
0x180001fa4  mov     rax, cs:qword_1800B6D48
0x180001fab  test    rax, rax
0x180001fae  jnz     short loc_180001FE9
0x180001fb0  call    GetWinRTStringLib
0x180001fb5  test    rax, rax
0x180001fb8  jz      short loc_180001FD3
0x180001fba  lea     rdx, ProcName; "WindowsGetStringRawBuffer"
0x180001fc1  mov     rcx, rax; hModule
0x180001fc4  call    cs:__imp_GetProcAddress
0x180001fca  mov     cs:qword_1800B6D48, rax
0x180001fd1  jmp     short loc_180001FDA
0x180001fd3  mov     rax, cs:qword_1800B6D48
0x180001fda  test    rax, rax
0x180001fdd  jnz     short loc_180001FE9
0x180001fdf  mov     ebx, 80004001h
0x180001fe4  jmp     loc_180002209
0x180001fe9  xor     edx, edx
0x180001feb  mov     rcx, rbx
0x180001fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ff3  mov     rsi, rax
0x180001ff6  xor     r15d, r15d
0x180001ff9  mov     [rbp+57h+var_C0], r15
0x180001ffd  mov     rax, [rdi]
0x180002000  lea     rdx, [rbp+57h+var_C0]
0x180002004  mov     rcx, rdi
0x180002007  mov     rax, [rax+60h]
0x18000200b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002010  mov     ebx, eax
0x180002012  xor     edi, edi
0x180002014  mov     [rsp+110h+ppURI], rdi
0x180002019  test    eax, eax
0x18000201b  js      short loc_180002047
  ... truncated ...
```
