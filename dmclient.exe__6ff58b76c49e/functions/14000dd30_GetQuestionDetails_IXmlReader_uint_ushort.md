# GetQuestionDetails(IXmlReader *,uint *,ushort *)

- ea: `0x14000dd30`
- end: `0x14000e749`
- name: `?GetQuestionDetails@@YAJPEAUIXmlReader@@PEAIPEAG@Z`
- size: `2585`
- prototype: `__int64 __fastcall(struct IXmlReader *, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000e924`

## callees

- `0x140001414`
- `0x14000a9f0`
- `0x14000b5c4`
- `0x14000dd30`
- `0x140012864`
- `0x140017a80`
- `0x140017d90`
- `0x140017fbc`
- `0x1400187b2`
- `0x1400187e0`
- `0x140019010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000e6ec`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000e6ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000e047`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000e047`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e036`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e69f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e6b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e036`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e69f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e6b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e6ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e6c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e6ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e6c6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14000e403`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14000e403`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000e3a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000e3a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000e10f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000e29d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000e32e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000e10f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000e29d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000e32e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e30c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e375`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e3d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e432`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e4c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e30c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e375`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e3d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e432`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e4c9`

## string_xrefs

- `0x14000de36`: `Failed to read the SiufData node`
- `0x14000e63e`: `Failed in StringCchCopyNW`

## pseudocode

```c
__int64 __fastcall GetQuestionDetails(struct IXmlReader *a1, unsigned int *a2, unsigned __int16 *a3)
{
  HSTRING v6; // r15
  signed int WideStringFromBase64; // ebx
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // r9
  WCHAR *v13; // r12
  __int64 v14; // rcx
  const char **v15; // rax
  char *v16; // rdx
  unsigned __int64 v17; // rsi
  unsigned __int64 v18; // rdi
  HANDLE ProcessHeap; // rax
  WCHAR *v20; // rax
  unsigned __int64 v21; // rsi
  WCHAR *v22; // rax
  WCHAR *v23; // rdx
  WCHAR v24; // cx
  WCHAR *v25; // rcx
  unsigned __int64 v26; // rdx
  HRESULT v27; // eax
  int v28; // edx
  unsigned int v29; // r8d
  __int64 v30; // r8
  __int64 v31; // r9
  const char *v32; // rax
  __int64 *v33; // rbx
  __int64 v34; // rdi
  HRESULT v35; // eax
  int v36; // edx
  unsigned int v37; // r8d
  int v38; // eax
  _QWORD *v39; // rcx
  _QWORD *v40; // rbx
  __int64 v41; // rdi
  HRESULT v42; // eax
  int v43; // edx
  unsigned int v44; // r8d
  int v45; // eax
  _QWORD *v46; // rcx
  const OLECHAR *StringRawBuffer; // rax
  _QWORD *v48; // rcx
  HRESULT v49; // eax
  _QWORD *v50; // rcx
  _QWORD *v51; // rcx
  void *v52; // rdi
  HANDLE v53; // rax
  HANDLE v54; // rax
  __int64 *v55; // rcx
  const unsigned __int16 **v57; // [rsp+30h] [rbp-A9h]
  const char **v58; // [rsp+38h] [rbp-A1h]
  __int64 *v59; // [rsp+48h] [rbp-91h]
  UINT32 length; // [rsp+70h] [rbp-69h] BYREF
  _QWORD *v61; // [rsp+78h] [rbp-61h] BYREF
  HSTRING v62; // [rsp+80h] [rbp-59h] BYREF
  const char *v63; // [rsp+88h] [rbp-51h] BYREF
  __int64 v64; // [rsp+90h] [rbp-49h] BYREF
  const char *v65; // [rsp+98h] [rbp-41h] BYREF
  __int64 v66; // [rsp+A0h] [rbp-39h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp-31h] BYREF
  DWORD cchString; // [rsp+B0h] [rbp-29h] BYREF
  int v69; // [rsp+B4h] [rbp-25h] BYREF
  LPCWSTR pszString; // [rsp+B8h] [rbp-21h] BYREF
  GUID pclsid; // [rsp+C0h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-9h] BYREF
  HSTRING string; // [rsp+E8h] [rbp+Fh] BYREF

  v6 = 0;
  v62 = 0;
  lpMem = 0;
  length = 0;
  pszString = 0;
  cchString = 0;
  pclsid = 0;
  if ( !a1 || !a2 || !a3 )
    return (unsigned int)-2147467261;
  memset_0(a3, 0, 0x4Au);
  *a2 = 1;
  v69 = 0;
  WideStringFromBase64 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))a1->lpVtbl->Read)(a1, &v69);
  if ( WideStringFromBase64 < 0 )
  {
    if ( (unsigned int)dword_140027000 > 2
      && (qword_140027010 & 0x400000000000LL) != 0
      && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
    {
      lpMem = (LPVOID)0x1000000;
      length = 103;
      v62 = (HSTRING)"GetQuestionDetails";
      v63 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
      LODWORD(v61) = WideStringFromBase64;
      v64 = (__int64)"Failed to read the SiufData node";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_140027010,
        (__int64)&byte_140021B27,
        qword_140027018,
        v8,
        (const unsigned __int16 **)&v64,
        (__int64)&v61,
        (const unsigned __int16 **)&v63,
        (const unsigned __int16 **)&v62,
        (__int64)&length,
        (__int64)&lpMem);
    }
    return (unsigned int)WideStringFromBase64;
  }
  WideStringFromBase64 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, DWORD *))a1->lpVtbl->GetValue)(
                           a1,
                           &pszString,
                           &cchString);
  if ( WideStringFromBase64 < 0 )
  {
    if ( (unsigned int)dword_140027000 > 2
      && (qword_140027010 & 0x400000000000LL) != 0
      && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
    {
      v64 = 0x1000000;
      LODWORD(v61) = 110;
      v63 = "GetQuestionDetails";
      lpMem = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
      length = WideStringFromBase64;
      v62 = (HSTRING)"Failed to get SiufData node value";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_140027018,
        (__int64)byte_140021AC9,
        v9,
        v10,
        (const unsigned __int16 **)&v62,
        (__int64)&length,
        (const unsigned __int16 **)&lpMem,
        (const unsigned __int16 **)&v63,
        (__int64)&v61,
        (__int64)&v64);
    }
    return (unsigned int)WideStringFromBase64;
  }
  WideStringFromBase64 = GetWideStringFromBase64(pszString, cchString, (unsigned __int16 **)&lpMem, &length);
  if ( WideStringFromBase64 < 0 )
  {
    v13 = 0;
    if ( (unsigned int)dword_140027000 <= 2 )
      goto LABEL_85;
    v14 = qword_140027018;
    if ( (qword_140027010 & 0x400000000000LL) == 0 || (qword_140027018 & 0x400000000000LL) != qword_140027018 )
      goto LABEL_85;
    v64 = 0x1000000;
    LODWORD(v61) = 118;
    v63 = "GetQuestionDetails";
    v62 = (HSTRING)"onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
    v65 = "Failed in GetWideStringFromBase64";
    v59 = &v64;
    v58 = &v63;
    v57 = (const unsigned __int16 **)&v62;
    v15 = &v65;
    v16 = (char *)&dword_1400213A4;
    goto LABEL_84;
  }
  v17 = length;
  v18 = ((unsigned __int64)length + 2) >> 1;
  ProcessHeap = GetProcessHeap();
  v20 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2 * v18);
  v13 = v20;
  if ( v20 )
  {
    if ( v18 )
    {
      if ( v18 > 0x7FFFFFFF || (v21 = v17 >> 1, v21 > 0x7FFFFFFE) )
      {
        WideStringFromBase64 = -2147024809;
        *v20 = 0;
      }
      else
      {
        v22 = (WCHAR *)lpMem;
        v23 = v13;
        do
        {
          if ( !v21 )
            break;
          v24 = *v22;
          if ( !*v22 )
            break;
          ++v22;
          *v23++ = v24;
          --v21;
          --v18;
        }
        while ( v18 );
        WideStringFromBase64 = v18 == 0 ? 0x8007007A : 0;
        v25 = v23 - 1;
        if ( v18 )
          v25 = v23;
        *v25 = 0;
        if ( v18 )
        {
          string = 0;
          v26 = -1;
          do
            ++v26;
          while ( v13[v26] );
          if ( v26 > 0xFFFFFFFF )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v26, v11);
            __debugbreak();
          }
          if ( (int)v26 + 1 < (unsigned int)v26 )
          {
LABEL_98:
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v26, v11);
            JUMPOUT(0x14000E748LL);
          }
          v27 = WindowsCreateStringReference(v13, v26, &hstringHeader, &string);
          if ( v27 < 0 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v27, v28, v29);
          }
          else
          {
            WideStringFromBase64 = Windows::Internal::Feedback::SiufPayloadImpl::Parse(
                                     string,
                                     (struct Windows::Internal::Feedback::SiufPayloadImpl **)&v62);
            if ( WideStringFromBase64 < 0 )
            {
              if ( (unsigned int)dword_140027000 > 2
                && (qword_140027010 & 0x400000000000LL) != 0
                && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
              {
                v65 = (const char *)0x1000000;
                LODWORD(v61) = 139;
                v64 = (__int64)"GetQuestionDetails";
                v63 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                length = WideStringFromBase64;
                v66 = (__int64)"Failed to parse SIUF Payload.";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                  qword_140027018,
                  (__int64)byte_14002177B,
                  v30,
                  v31,
                  (const unsigned __int16 **)&v66,
                  (__int64)&length,
                  (const unsigned __int16 **)&v63,
                  (const unsigned __int16 **)&v64,
                  (__int64)&v61,
                  (__int64)&v65);
              }
              v6 = v62;
              goto LABEL_85;
            }
            v6 = v62;
            WideStringFromBase64 = Windows::Internal::Feedback::SiufPayloadImpl::GetVersion(
                                     (Windows::Internal::Feedback::SiufPayloadImpl *)v62,
                                     a2);
            if ( WideStringFromBase64 < 0 )
            {
              if ( (unsigned int)dword_140027000 <= 2 )
                goto LABEL_85;
              v14 = qword_140027018;
              if ( (qword_140027010 & 0x400000000000LL) == 0 || (qword_140027018 & 0x400000000000LL) != qword_140027018 )
                goto LABEL_85;
              LODWORD(v61) = 146;
              v65 = "GetQuestionDetails";
              v64 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
              v32 = "Failed to get GetVersion.";
              v16 = &byte_1400216BF;
              goto LABEL_83;
            }
            length = 0;
            pclsid = 0;
            v61 = 0;
            v33 = *(__int64 **)v6;
            v34 = **(_QWORD **)v6;
            string = 0;
            v35 = WindowsCreateStringReference(L"Question", 8u, &hstringHeader, &string);
            if ( v35 >= 0 )
            {
              v38 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD **))(v34 + 64))(v33, string, &v61);
              WideStringFromBase64 = v38;
              if ( v38 < 0 )
              {
                SuifTraceLogging::WriteErrorTraceFormat(
                  v38,
                  334,
                  "Windows::Internal::Feedback::SiufPayloadImpl::GetQuestionVersion",
                  (wchar_t *)L"GetNamedObject failed to get Question object");
                v39 = v61;
                if ( v61 )
                {
                  v61 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v39 + 16LL))(v39);
                }
                goto LABEL_67;
              }
              v62 = 0;
              v40 = v61;
              v41 = *v61;
              WindowsDeleteString(0);
              v62 = 0;
              string = 0;
              v42 = WindowsCreateStringReference(L"QuestionVersion", 0xFu, &hstringHeader, &string);
              if ( v42 >= 0 )
              {
                v45 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, HSTRING *))(v41 + 80))(v40, string, &v62);
                WideStringFromBase64 = v45;
                if ( v45 >= 0 )
                {
                  StringRawBuffer = WindowsGetStringRawBuffer(v62, &length);
                  if ( length == 38 )
                  {
                    v49 = CLSIDFromString(StringRawBuffer, &pclsid);
                    WideStringFromBase64 = v49;
                    if ( v49 >= 0 )
                    {
                      WindowsDeleteString(v62);
                      v62 = 0;
                      v51 = v61;
                      if ( v61 )
                      {
                        v61 = 0;
                        (*(void (__fastcall **)(_QWORD *))(*v51 + 16LL))(v51);
                      }
                      WideStringFromBase64 = StringCchPrintfW(
                                               a3,
                                               0x25u,
                                               L"%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
                                               pclsid.Data1,
                                               pclsid.Data2,
                                               pclsid.Data3,
                                               pclsid.Data4[0],
                                               pclsid.Data4[1],
                                               pclsid.Data4[2],
                                               pclsid.Data4[3],
                                               pclsid.Data4[4],
                                               pclsid.Data4[5],
                                               pclsid.Data4[6],
                                               pclsid.Data4[7]);
                      if ( WideStringFromBase64 >= 0 )
                        goto LABEL_85;
                      if ( (unsigned int)dword_140027000 <= 2 )
                        goto LABEL_85;
                      v14 = qword_140027018;
                      if ( (qword_140027010 & 0x400000000000LL) == 0
                        || (qword_140027018 & 0x400000000000LL) != qword_140027018 )
                      {
                        goto LABEL_85;
                      }
                      LODWORD(v61) = 167;
                      v65 = "GetQuestionDetails";
                      v64 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                      v32 = "Failed in StringCbPrintf.";
                      v16 = &byte_140021837;
LABEL_83:
                      v63 = v32;
                      v59 = &v66;
                      v58 = &v65;
                      v57 = (const unsigned __int16 **)&v64;
                      v15 = &v63;
                      v66 = 0x1000000;
LABEL_84:
                      length = WideStringFromBase64;
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                        v14,
                        (__int64)v16,
                        v11,
                        v12,
                        (const unsigned __int16 **)v15,
                        (__int64)&length,
                        v57,
                        (const unsigned __int16 **)v58,
                        (__int64)&v61,
                        (__int64)v59);
                      goto LABEL_85;
                    }
                    SuifTraceLogging::WriteErrorTraceFormat(
                      v49,
                      355,
                      "Windows::Internal::Feedback::SiufPayloadImpl::GetQuestionVersion",
                      (wchar_t *)L"Failed to convert QuestionVersion from string to GUID");
                    WindowsDeleteString(v62);
                    v62 = 0;
                    v50 = v61;
                    if ( v61 )
                    {
                      v61 = 0;
                      (*(void (__fastcall **)(_QWORD *))(*v50 + 16LL))(v50);
                    }
                  }
                  else
                  {
                    WideStringFromBase64 = -2147024809;
                    SuifTraceLogging::WriteErrorTraceFormat(
                      -2147024809,
                      351,
                      "Windows::Internal::Feedback::SiufPayloadImpl::GetQuestionVersion",
                      (wchar_t *)L"QuestionVersion string length is not the expected value.");
                    WindowsDeleteString(v62);
                    v62 = 0;
                    v48 = v61;
                    if ( v61 )
                    {
                      v61 = 0;
                      (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
                    }
                  }
                }
                else
                {
                  SuifTraceLogging::WriteErrorTraceFormat(
                    v45,
                    341,
                    "Windows::Internal::Feedback::SiufPayloadImpl::GetQuestionVersion",
                    (wchar_t *)L"GetNamedString failed to get QuestionVersion.");
                  WindowsDeleteString(v62);
                  v62 = 0;
                  v46 = v61;
                  if ( v61 )
                  {
                    v61 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
                  }
                }
LABEL_67:
                if ( (unsigned int)dword_140027000 <= 2 )
                  goto LABEL_85;
                v14 = qword_140027018;
                if ( (qword_140027010 & 0x400000000000LL) == 0
                  || (qword_140027018 & 0x400000000000LL) != qword_140027018 )
                {
                  goto LABEL_85;
                }
                LODWORD(v61) = 153;
                v65 = "GetQuestionDetails";
                v64 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                v32 = "Failed to get GetQuestionVersion.";
                v16 = (char *)&dword_14002151C;
                goto LABEL_83;
              }
              goto LABEL_97;
            }
          }
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v35, v36, v37);
LABEL_97:
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v42, v43, v44);
          goto LABEL_98;
        }
      }
    }
    else
    {
      WideStringFromBase64 = -2147024809;
    }
    if ( (unsigned int)dword_140027000 <= 2 )
      goto LABEL_85;
    v14 = qword_140027018;
    if ( (qword_140027010 & 0x400000000000LL) == 0 || (qword_140027018 & 0x400000000000LL) != qword_140027018 )
      goto LABEL_85;
    LODWORD(v61) = 131;
    v65 = "GetQuestionDetails";
    v64 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
    v32 = "Failed in StringCchCopyNW";
    v16 = byte_140021951;
    goto LABEL_83;
  }
  WideStringFromBase64 = -2147024882;
LABEL_85:
  v52 = lpMem;
  if ( lpMem )
  {
    v53 = GetProcessHeap();
    HeapFree(v53, 0, v52);
  }
  if ( v13 )
  {
    v54 = GetProcessHeap();
    HeapFree(v54, 0, v13);
  }
  if ( v6 )
  {
    v55 = *(__int64 **)v6;
    if ( *(_QWORD *)v6 )
    {
      *(_QWORD *)v6 = 0;
      (*(void (__fastcall **)(__int64 *))(*v55 + 16))(v55);
    }
    operator delete(v6);
  }
  return (unsigned int)WideStringFromBase64;
}

```

## disassembly

```asm
0x14000dd30  mov     [rsp-8+arg_18], rbx
0x14000dd35  push    rbp
0x14000dd36  push    rsi
0x14000dd37  push    rdi
0x14000dd38  push    r12
0x14000dd3a  push    r13
0x14000dd3c  push    r14
0x14000dd3e  push    r15
0x14000dd40  lea     rbp, [rsp-27h]
0x14000dd45  sub     rsp, 100h
0x14000dd4c  mov     rax, cs:__security_cookie
0x14000dd53  xor     rax, rsp
0x14000dd56  mov     [rbp+57h+var_40], rax
0x14000dd5a  mov     r13, r8
0x14000dd5d  mov     r14, rdx
0x14000dd60  mov     rdi, rcx
0x14000dd63  xor     esi, esi
0x14000dd65  mov     r15d, esi
0x14000dd68  mov     [rbp+57h+var_B0], rsi
0x14000dd6c  mov     [rbp+57h+lpMem], rsi
0x14000dd70  mov     [rbp+57h+length], esi
0x14000dd73  mov     [rbp+57h+pszString], rsi
0x14000dd77  mov     [rbp+57h+cchString], esi
0x14000dd7a  xorps   xmm0, xmm0
0x14000dd7d  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x14000dd81  test    rcx, rcx
0x14000dd84  jnz     short loc_14000DD90
0x14000dd86  mov     ebx, 80004003h
0x14000dd8b  jmp     loc_14000E6F2
0x14000dd90  test    r14, r14
0x14000dd93  jz      short loc_14000DD86
0x14000dd95  test    r13, r13
0x14000dd98  jz      short loc_14000DD86
0x14000dd9a  xor     edx, edx; Val
0x14000dd9c  lea     r8d, [rdx+4Ah]; Size
0x14000dda0  mov     rcx, r13; void *
0x14000dda3  call    memset_0
0x14000dda8  mov     dword ptr [r14], 1
0x14000ddaf  mov     [rbp+57h+var_7C], esi
0x14000ddb2  mov     rax, [rdi]
0x14000ddb5  lea     rdx, [rbp+57h+var_7C]
0x14000ddb9  mov     rcx, rdi
0x14000ddbc  mov     rax, [rax+30h]
0x14000ddc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ddc5  mov     ebx, eax
0x14000ddc7  test    eax, eax
0x14000ddc9  jns     loc_14000DE88
0x14000ddcf  mov     ecx, cs:dword_140027000
0x14000ddd5  cmp     ecx, 2
0x14000ddd8  jbe     loc_14000E6F2
0x14000ddde  mov     r8, cs:qword_140027018
0x14000dde5  mov     rcx, cs:qword_140027010
0x14000ddec  mov     rdx, 400000000000h
0x14000ddf6  test    rdx, rcx
0x14000ddf9  jz      loc_14000E6F2
0x14000ddff  mov     rax, r8
0x14000de02  and     rax, rdx
0x14000de05  cmp     rax, r8
0x14000de08  jnz     loc_14000E6F2
0x14000de0e  mov     [rbp+57h+lpMem], 1000000h
0x14000de16  mov     [rbp+57h+length], 67h ; 'g'
0x14000de1d  lea     rax, aGetquestiondet; "GetQuestionDetails"
0x14000de24  mov     [rbp+57h+var_B0], rax
0x14000de28  lea     rax, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000de2f  mov     [rbp+57h+var_A8], rax
0x14000de33  mov     dword ptr [rbp+57h+var_B8], ebx
0x14000de36  lea     rax, aFailedToReadTh; "Failed to read the SiufData node"
0x14000de3d  mov     [rbp+57h+var_A0], rax
0x14000de41  lea     rax, [rbp+57h+lpMem]
0x14000de45  mov     [rsp+130h+var_E8], rax
0x14000de4a  lea     rax, [rbp+57h+length]
0x14000de4e  mov     [rsp+130h+var_F0], rax
0x14000de53  lea     rax, [rbp+57h+var_B0]
0x14000de57  mov     [rsp+130h+var_F8], rax
0x14000de5c  lea     rax, [rbp+57h+var_A8]
0x14000de60  mov     [rsp+130h+var_100], rax
0x14000de65  lea     rax, [rbp+57h+var_B8]
0x14000de69  mov     [rsp+130h+var_108], rax
0x14000de6e  lea     rax, [rbp+57h+var_A0]
0x14000de72  lea     rdx, byte_140021B27
0x14000de79  mov     [rsp+130h+var_110], rax
0x14000de7e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000de83  jmp     loc_14000E6F2
0x14000de88  mov     rax, [rdi]
0x14000de8b  lea     r8, [rbp+57h+cchString]
0x14000de8f  lea     rdx, [rbp+57h+pszString]
0x14000de93  mov     rcx, rdi
0x14000de96  mov     rax, [rax+80h]
0x14000de9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dea2  mov     ebx, eax
0x14000dea4  test    eax, eax
0x14000dea6  jns     loc_14000DF5B
0x14000deac  mov     eax, cs:dword_140027000
0x14000deb2  cmp     eax, 2
0x14000deb5  jbe     loc_14000E6F2
0x14000debb  mov     rcx, cs:qword_140027018
0x14000dec2  mov     rax, cs:qword_140027010
0x14000dec9  mov     rdx, 400000000000h
0x14000ded3  test    rdx, rax
0x14000ded6  jz      loc_14000E6F2
0x14000dedc  mov     rax, rcx
0x14000dedf  and     rax, rdx
0x14000dee2  cmp     rax, rcx
0x14000dee5  jnz     loc_14000E6F2
0x14000deeb  mov     [rbp+57h+var_A0], 1000000h
0x14000def3  mov     dword ptr [rbp+57h+var_B8], 6Eh ; 'n'
0x14000defa  lea     rax, aGetquestiondet; "GetQuestionDetails"
0x14000df01  mov     [rbp+57h+var_A8], rax
0x14000df05  lea     rax, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000df0c  mov     [rbp+57h+lpMem], rax
0x14000df10  mov     [rbp+57h+length], ebx
0x14000df13  lea     rax, aFailedToGetSiu_0; "Failed to get SiufData node value"
0x14000df1a  mov     [rbp+57h+var_B0], rax
0x14000df1e  lea     rax, [rbp+57h+var_A0]
0x14000df22  mov     [rsp+130h+var_E8], rax
0x14000df27  lea     rax, [rbp+57h+var_B8]
0x14000df2b  mov     [rsp+130h+var_F0], rax
0x14000df30  lea     rax, [rbp+57h+var_A8]
0x14000df34  mov     [rsp+130h+var_F8], rax
0x14000df39  lea     rax, [rbp+57h+lpMem]
0x14000df3d  mov     [rsp+130h+var_100], rax
0x14000df42  lea     rax, [rbp+57h+length]
0x14000df46  mov     [rsp+130h+var_108], rax
0x14000df4b  lea     rax, [rbp+57h+var_B0]
0x14000df4f  lea     rdx, byte_140021AC9
0x14000df56  jmp     loc_14000DE79
0x14000df5b  lea     r9, [rbp+57h+length]; unsigned int *
0x14000df5f  lea     r8, [rbp+57h+lpMem]; unsigned __int16 **
0x14000df63  mov     edx, [rbp+57h+cchString]; cchString
0x14000df66  mov     rcx, [rbp+57h+pszString]; pszString
0x14000df6a  call    ?GetWideStringFromBase64@@YAJPEBGIPEAPEAGPEAI@Z; GetWideStringFromBase64(ushort const *,uint,ushort * *,uint *)
0x14000df6f  mov     ebx, eax
0x14000df71  test    eax, eax
0x14000df73  jns     loc_14000E028
0x14000df79  mov     r12, rsi
0x14000df7c  mov     eax, cs:dword_140027000
0x14000df82  cmp     eax, 2
0x14000df85  jbe     loc_14000E696
0x14000df8b  mov     rcx, cs:qword_140027018
0x14000df92  mov     rax, cs:qword_140027010
0x14000df99  mov     rdx, 400000000000h
0x14000dfa3  test    rdx, rax
0x14000dfa6  jz      loc_14000E696
0x14000dfac  mov     rax, rcx
0x14000dfaf  and     rax, rdx
0x14000dfb2  cmp     rax, rcx
0x14000dfb5  jnz     loc_14000E696
0x14000dfbb  mov     [rbp+57h+var_A0], 1000000h
0x14000dfc3  mov     dword ptr [rbp+57h+var_B8], 76h ; 'v'
0x14000dfca  lea     rax, aGetquestiondet; "GetQuestionDetails"
0x14000dfd1  mov     [rbp+57h+var_A8], rax
0x14000dfd5  lea     rax, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000dfdc  mov     [rbp+57h+var_B0], rax
0x14000dfe0  lea     rax, aFailedInGetwid; "Failed in GetWideStringFromBase64"
0x14000dfe7  mov     [rbp+57h+var_98], rax
0x14000dfeb  lea     rax, [rbp+57h+var_A0]
0x14000dfef  mov     [rsp+130h+var_E8], rax
0x14000dff4  lea     rax, [rbp+57h+var_B8]
0x14000dff8  mov     [rsp+130h+var_F0], rax
0x14000dffd  lea     rax, [rbp+57h+var_A8]
0x14000e001  mov     [rsp+130h+var_F8], rax
0x14000e006  lea     rax, [rbp+57h+var_B0]
0x14000e00a  mov     [rsp+130h+var_100], rax
0x14000e00f  lea     rax, [rbp+57h+length]
0x14000e013  mov     [rsp+130h+var_108], rax
0x14000e018  lea     rax, [rbp+57h+var_98]
0x14000e01c  lea     rdx, dword_1400213A4
0x14000e023  jmp     loc_14000E689
0x14000e028  mov     esi, [rbp+57h+length]
0x14000e02b  lea     rdi, [rsi+2]
0x14000e02f  shr     rdi, 1
0x14000e032  lea     rbx, [rdi+rdi]
0x14000e036  call    cs:__imp_GetProcessHeap
0x14000e03c  mov     rcx, rax; hHeap
0x14000e03f  mov     r8, rbx; dwBytes
0x14000e042  mov     edx, 8; dwFlags
0x14000e047  call    cs:__imp_HeapAlloc
0x14000e04d  mov     r12, rax
0x14000e050  test    rax, rax
0x14000e053  jnz     short loc_14000E061
0x14000e055  mov     ebx, 8007000Eh
0x14000e05a  xor     esi, esi
0x14000e05c  jmp     loc_14000E696
0x14000e061  test    rdi, rdi
0x14000e064  jz      loc_14000E5D7
0x14000e06a  cmp     rdi, 7FFFFFFFh
0x14000e071  jbe     short loc_14000E07F
0x14000e073  mov     ebx, 80070057h
0x14000e078  xor     esi, esi
0x14000e07a  jmp     loc_14000E5E3
0x14000e07f  shr     rsi, 1
0x14000e082  cmp     rsi, 7FFFFFFEh
0x14000e089  ja      short loc_14000E073
0x14000e08b  mov     rax, [rbp+57h+lpMem]
0x14000e08f  mov     rdx, r12
0x14000e092  test    rsi, rsi
0x14000e095  jz      short loc_14000E0B3
0x14000e097  movzx   ecx, word ptr [rax]
0x14000e09a  test    cx, cx
0x14000e09d  jz      short loc_14000E0B3
0x14000e09f  add     rax, 2
0x14000e0a3  mov     [rdx], cx
0x14000e0a6  add     rdx, 2
0x14000e0aa  dec     rsi
0x14000e0ad  sub     rdi, 1
0x14000e0b1  jnz     short loc_14000E092
0x14000e0b3  mov     rax, rdi
0x14000e0b6  neg     rax
0x14000e0b9  sbb     ebx, ebx
0x14000e0bb  not     ebx
0x14000e0bd  and     ebx, 8007007Ah
0x14000e0c3  lea     rcx, [rdx-2]
0x14000e0c7  xor     esi, esi
0x14000e0c9  test    rdi, rdi
0x14000e0cc  cmovnz  rcx, rdx
0x14000e0d0  mov     [rcx], si
0x14000e0d3  jz      loc_14000E5E6
0x14000e0d9  mov     [rbp+57h+string], rsi
0x14000e0dd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000e0e1  inc     rdx; int
0x14000e0e4  cmp     [r12+rdx*2], si
0x14000e0e9  jnz     short loc_14000E0E1
0x14000e0eb  mov     eax, 0FFFFFFFFh
0x14000e0f0  cmp     rdx, rax
0x14000e0f3  ja      loc_14000E71B
0x14000e0f9  lea     eax, [rdx+1]
0x14000e0fc  cmp     eax, edx
0x14000e0fe  jb      loc_14000E73E
0x14000e104  lea     r9, [rbp+57h+string]; string
0x14000e108  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14000e10c  mov     rcx, r12; sourceString
0x14000e10f  call    cs:__imp_WindowsCreateStringReference
0x14000e115  test    eax, eax
0x14000e117  js      loc_14000E726
0x14000e11d  lea     rdx, [rbp+57h+var_B0]; struct Windows::Internal::Feedback::SiufPayloadImpl **
0x14000e121  mov     rcx, [rbp+57h+string]; HSTRING
0x14000e125  call    ?Parse@SiufPayloadImpl@Feedback@Internal@Windows@@SAJPEAUHSTRING__@@PEAPEAV1234@@Z; Windows::Internal::Feedback::SiufPayloadImpl::Parse(HSTRING__ *,Windows::Internal::Feedback::SiufPayloadImpl * *)
0x14000e12a  mov     ebx, eax
0x14000e12c  test    eax, eax
0x14000e12e  jns     loc_14000E1ED
0x14000e134  mov     eax, cs:dword_140027000
0x14000e13a  cmp     eax, 2
0x14000e13d  jbe     loc_14000E1E4
0x14000e143  mov     rcx, cs:qword_140027018
0x14000e14a  mov     rax, cs:qword_140027010
0x14000e151  mov     rdx, 400000000000h
0x14000e15b  test    rdx, rax
0x14000e15e  jz      loc_14000E1E4
0x14000e164  mov     rax, rcx
0x14000e167  and     rax, rdx
0x14000e16a  cmp     rax, rcx
0x14000e16d  jnz     short loc_14000E1E4
0x14000e16f  mov     [rbp+57h+var_98], 1000000h
0x14000e177  mov     dword ptr [rbp+57h+var_B8], 8Bh
0x14000e17e  lea     rax, aGetquestiondet; "GetQuestionDetails"
0x14000e185  mov     [rbp+57h+var_A0], rax
0x14000e189  lea     rax, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000e190  mov     [rbp+57h+var_A8], rax
0x14000e194  mov     [rbp+57h+length], ebx
0x14000e197  lea     rax, aFailedToParseS; "Failed to parse SIUF Payload."
0x14000e19e  mov     [rbp+57h+var_90], rax
0x14000e1a2  lea     rax, [rbp+57h+var_98]
0x14000e1a6  mov     [rsp+130h+var_E8], rax
0x14000e1ab  lea     rax, [rbp+57h+var_B8]
0x14000e1af  mov     [rsp+130h+var_F0], rax
0x14000e1b4  lea     rax, [rbp+57h+var_A0]
0x14000e1b8  mov     [rsp+130h+var_F8], rax
0x14000e1bd  lea     rax, [rbp+57h+var_A8]
0x14000e1c1  mov     [rsp+130h+var_100], rax
0x14000e1c6  lea     rax, [rbp+57h+length]
0x14000e1ca  mov     [rsp+130h+var_108], rax
0x14000e1cf  lea     rax, [rbp+57h+var_90]
0x14000e1d3  mov     [rsp+130h+var_110], rax
0x14000e1d8  lea     rdx, byte_14002177B
0x14000e1df  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000e1e4  mov     r15, [rbp+57h+var_B0]
0x14000e1e8  jmp     loc_14000E696
0x14000e1ed  mov     rdx, r14; unsigned int *
0x14000e1f0  mov     r15, [rbp+57h+var_B0]
0x14000e1f4  mov     rcx, r15; this
0x14000e1f7  call    ?GetVersion@SiufPayloadImpl@Feedback@Internal@Windows@@QEAAJPEAI@Z; Windows::Internal::Feedback::SiufPayloadImpl::GetVersion(uint *)
0x14000e1fc  mov     ebx, eax
0x14000e1fe  test    eax, eax
0x14000e200  jns     short loc_14000E271
0x14000e202  mov     eax, cs:dword_140027000
0x14000e208  cmp     eax, 2
0x14000e20b  jbe     loc_14000E696
0x14000e211  mov     rcx, cs:qword_140027018
0x14000e218  mov     rax, cs:qword_140027010
0x14000e21f  mov     rdx, 400000000000h
0x14000e229  test    rdx, rax
0x14000e22c  jz      loc_14000E696
0x14000e232  mov     rax, rcx
0x14000e235  and     rax, rdx
0x14000e238  cmp     rax, rcx
0x14000e23b  jnz     loc_14000E696
0x14000e241  mov     dword ptr [rbp+57h+var_B8], 92h
0x14000e248  lea     rax, aGetquestiondet; "GetQuestionDetails"
0x14000e24f  mov     [rbp+57h+var_98], rax
0x14000e253  lea     rax, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
  ... truncated ...
```
