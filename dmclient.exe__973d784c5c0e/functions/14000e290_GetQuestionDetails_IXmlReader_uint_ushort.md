# GetQuestionDetails(IXmlReader *,uint *,ushort *)

- ea: `0x14000e290`
- end: `0x14000ecba`
- name: `?GetQuestionDetails@@YAJPEAUIXmlReader@@PEAIPEAG@Z`
- size: `2602`
- prototype: `int(struct IXmlReader *, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000ee98`

## callees

- `0x140001418`
- `0x14000ac50`
- `0x14000b904`
- `0x14000d9b0`
- `0x14000e290`
- `0x1400131f8`
- `0x140016818`
- `0x140016c84`
- `0x140018850`
- `0x1400195e2`
- `0x140019610`
- `0x14001a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000ec74`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000ec74`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000e5ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000e5ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e596`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ec0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ec34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e596`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ec0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ec34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ec23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ec48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ec23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ec48`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14000e961`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14000e961`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e84c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e8c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e92e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e996`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ea33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e84c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e8c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e92e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e996`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ea33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000e7d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000e874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000e7d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000e874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000e8f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000e8f8`

## string_xrefs

- `0x14000e399`: `Failed to read the SiufData node`
- `0x14000ebae`: `Failed in StringCchCopyNW`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetQuestionDetails(struct IXmlReader *a1, unsigned int *a2, unsigned __int16 *a3)
{
  HSTRING v6; // r15
  _WORD *v7; // r12
  signed int WideStringFromBase64; // ebx
  int v9; // r9d
  int v10; // r8d
  int v11; // r9d
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  const char **v15; // rax
  char *v16; // rdx
  unsigned __int64 v17; // rsi
  unsigned __int64 v18; // rdi
  HANDLE ProcessHeap; // rax
  _WORD *v20; // rax
  unsigned __int64 v21; // rsi
  __int16 *v22; // rax
  _WORD *v23; // rdx
  __int16 v24; // cx
  _WORD *v25; // rcx
  __int64 v26; // rax
  int v27; // r8d
  int v28; // r9d
  const char *v29; // rax
  __int64 *v30; // rbx
  __int64 v31; // rdi
  HRESULT v32; // eax
  int v33; // edx
  unsigned int v34; // r8d
  int v35; // eax
  _QWORD *v36; // rcx
  _QWORD *v37; // rbx
  __int64 v38; // rdi
  HRESULT v39; // eax
  int v40; // edx
  unsigned int v41; // r8d
  int v42; // eax
  _QWORD *v43; // rcx
  const OLECHAR *StringRawBuffer; // rax
  _QWORD *v45; // rcx
  HRESULT v46; // eax
  _QWORD *v47; // rcx
  _QWORD *v48; // rcx
  void *v49; // rdi
  HANDLE v50; // rax
  HANDLE v51; // rax
  __int64 *v52; // rcx
  HSTRING *v54; // [rsp+30h] [rbp-A9h]
  const char **v55; // [rsp+38h] [rbp-A1h]
  __int64 *v56; // [rsp+48h] [rbp-91h]
  UINT32 length; // [rsp+70h] [rbp-69h] BYREF
  _QWORD *v58; // [rsp+78h] [rbp-61h] BYREF
  HSTRING v59; // [rsp+80h] [rbp-59h] BYREF
  const char *v60; // [rsp+88h] [rbp-51h] BYREF
  __int64 v61; // [rsp+90h] [rbp-49h] BYREF
  const char *v62; // [rsp+98h] [rbp-41h] BYREF
  __int64 v63; // [rsp+A0h] [rbp-39h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp-31h] BYREF
  DWORD cchString; // [rsp+B0h] [rbp-29h] BYREF
  int v66; // [rsp+B4h] [rbp-25h] BYREF
  LPCWSTR pszString; // [rsp+B8h] [rbp-21h] BYREF
  GUID pclsid; // [rsp+C0h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-9h] BYREF
  HSTRING string; // [rsp+E8h] [rbp+Fh] BYREF

  v6 = 0;
  v59 = 0;
  lpMem = 0;
  length = 0;
  v7 = 0;
  pszString = 0;
  cchString = 0;
  pclsid = 0;
  if ( !a1 || !a2 || !a3 )
    return (unsigned int)-2147467261;
  memset_0(a3, 0, 0x4Au);
  *a2 = 1;
  v66 = 0;
  WideStringFromBase64 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))a1->lpVtbl->Read)(a1, &v66);
  if ( WideStringFromBase64 < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2
      && (qword_140028010 & 0x400000000000LL) != 0
      && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
    {
      lpMem = (LPVOID)0x1000000;
      length = 103;
      v59 = (HSTRING)"GetQuestionDetails";
      v60 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
      LODWORD(v58) = WideStringFromBase64;
      v61 = (__int64)"Failed to read the SiufData node";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_140028010,
        (unsigned int)&byte_140022B2F,
        qword_140028018,
        v9,
        (__int64)&v61,
        (__int64)&v58,
        (__int64)&v60,
        (__int64)&v59,
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
    if ( (unsigned int)dword_140028000 > 2
      && (qword_140028010 & 0x400000000000LL) != 0
      && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
    {
      v61 = 0x1000000;
      LODWORD(v58) = 110;
      v60 = "GetQuestionDetails";
      lpMem = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
      length = WideStringFromBase64;
      v59 = (HSTRING)"Failed to get SiufData node value";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_140028018,
        (unsigned int)byte_140022AD1,
        v10,
        v11,
        (__int64)&v59,
        (__int64)&length,
        (__int64)&lpMem,
        (__int64)&v60,
        (__int64)&v58,
        (__int64)&v61);
    }
    return (unsigned int)WideStringFromBase64;
  }
  WideStringFromBase64 = GetWideStringFromBase64(pszString, cchString, (unsigned __int16 **)&lpMem, &length);
  if ( WideStringFromBase64 < 0 )
  {
    if ( (unsigned int)dword_140028000 <= 2 )
      goto LABEL_80;
    v14 = qword_140028018;
    if ( (qword_140028010 & 0x400000000000LL) == 0 || (qword_140028018 & 0x400000000000LL) != qword_140028018 )
      goto LABEL_80;
    v61 = 0x1000000;
    LODWORD(v58) = 118;
    v60 = "GetQuestionDetails";
    v59 = (HSTRING)"onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
    v62 = "Failed in GetWideStringFromBase64";
    v56 = &v61;
    v55 = &v60;
    v54 = &v59;
    v15 = &v62;
    v16 = (char *)&dword_1400223AC;
    goto LABEL_79;
  }
  v17 = length;
  v18 = ((unsigned __int64)length + 2) >> 1;
  ProcessHeap = GetProcessHeap();
  v20 = HeapAlloc(ProcessHeap, 8u, 2 * v18);
  v7 = v20;
  v62 = (const char *)v20;
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
        v22 = (__int16 *)lpMem;
        v23 = v7;
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
          v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v62);
          WideStringFromBase64 = Windows::Internal::Feedback::SiufPayloadImpl::Parse(
                                   *(HSTRING *)(v26 + 24),
                                   (struct Windows::Internal::Feedback::SiufPayloadImpl **)&v59);
          if ( WideStringFromBase64 < 0 )
          {
            if ( (unsigned int)dword_140028000 > 2
              && (qword_140028010 & 0x400000000000LL) != 0
              && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
            {
              v62 = (const char *)0x1000000;
              LODWORD(v58) = 139;
              v61 = (__int64)"GetQuestionDetails";
              v60 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
              length = WideStringFromBase64;
              v63 = (__int64)"Failed to parse SIUF Payload.";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                qword_140028018,
                (unsigned int)byte_140022783,
                v27,
                v28,
                (__int64)&v63,
                (__int64)&length,
                (__int64)&v60,
                (__int64)&v61,
                (__int64)&v58,
                (__int64)&v62);
            }
            v6 = v59;
            goto LABEL_80;
          }
          v6 = v59;
          WideStringFromBase64 = Windows::Internal::Feedback::SiufPayloadImpl::GetVersion(
                                   (Windows::Internal::Feedback::SiufPayloadImpl *)v59,
                                   a2);
          if ( WideStringFromBase64 < 0 )
          {
            if ( (unsigned int)dword_140028000 <= 2 )
              goto LABEL_80;
            v14 = qword_140028018;
            if ( (qword_140028010 & 0x400000000000LL) == 0 || (qword_140028018 & 0x400000000000LL) != qword_140028018 )
              goto LABEL_80;
            LODWORD(v58) = 146;
            v62 = "GetQuestionDetails";
            v61 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
            v29 = "Failed to get GetVersion.";
            v16 = &byte_1400226C7;
            goto LABEL_78;
          }
          length = 0;
          pclsid = 0;
          v58 = 0;
          v30 = *(__int64 **)v6;
          v31 = **(_QWORD **)v6;
          string = 0;
          v32 = WindowsCreateStringReference(L"Question", 8u, &hstringHeader, &string);
          if ( v32 >= 0 )
          {
            v35 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD **))(v31 + 64))(v30, string, &v58);
            WideStringFromBase64 = v35;
            if ( v35 < 0 )
            {
              SuifTraceLogging::WriteErrorTraceFormat(
                v35,
                334,
                "Windows::Internal::Feedback::SiufPayloadImpl::GetQuestionVersion",
                (wchar_t *)L"GetNamedObject failed to get Question object");
              v36 = v58;
              if ( v58 )
              {
                v58 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
              }
              goto LABEL_62;
            }
            v59 = 0;
            v37 = v58;
            v38 = *v58;
            WindowsDeleteString(0);
            v59 = 0;
            string = 0;
            v39 = WindowsCreateStringReference(L"QuestionVersion", 0xFu, &hstringHeader, &string);
            if ( v39 >= 0 )
            {
              v42 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, HSTRING *))(v38 + 80))(v37, string, &v59);
              WideStringFromBase64 = v42;
              if ( v42 >= 0 )
              {
                StringRawBuffer = WindowsGetStringRawBuffer(v59, &length);
                if ( length == 38 )
                {
                  v46 = CLSIDFromString(StringRawBuffer, &pclsid);
                  WideStringFromBase64 = v46;
                  if ( v46 >= 0 )
                  {
                    WindowsDeleteString(v59);
                    v59 = 0;
                    v48 = v58;
                    if ( v58 )
                    {
                      v58 = 0;
                      (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
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
                      goto LABEL_80;
                    if ( (unsigned int)dword_140028000 <= 2 )
                      goto LABEL_80;
                    v14 = qword_140028018;
                    if ( (qword_140028010 & 0x400000000000LL) == 0
                      || (qword_140028018 & 0x400000000000LL) != qword_140028018 )
                    {
                      goto LABEL_80;
                    }
                    LODWORD(v58) = 167;
                    v62 = "GetQuestionDetails";
                    v61 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                    v29 = "Failed in StringCbPrintf.";
                    v16 = &byte_14002283F;
LABEL_78:
                    v60 = v29;
                    v56 = &v63;
                    v55 = &v62;
                    v54 = (HSTRING *)&v61;
                    v15 = &v60;
                    v63 = 0x1000000;
LABEL_79:
                    length = WideStringFromBase64;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                      v14,
                      (_DWORD)v16,
                      v12,
                      v13,
                      (__int64)v15,
                      (__int64)&length,
                      (__int64)v54,
                      (__int64)v55,
                      (__int64)&v58,
                      (__int64)v56);
                    goto LABEL_80;
                  }
                  SuifTraceLogging::WriteErrorTraceFormat(
                    v46,
                    355,
                    "Windows::Internal::Feedback::SiufPayloadImpl::GetQuestionVersion",
                    (wchar_t *)L"Failed to convert QuestionVersion from string to GUID");
                  WindowsDeleteString(v59);
                  v59 = 0;
                  v47 = v58;
                  if ( v58 )
                  {
                    v58 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
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
                  WindowsDeleteString(v59);
                  v59 = 0;
                  v45 = v58;
                  if ( v58 )
                  {
                    v58 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
                  }
                }
              }
              else
              {
                SuifTraceLogging::WriteErrorTraceFormat(
                  v42,
                  341,
                  "Windows::Internal::Feedback::SiufPayloadImpl::GetQuestionVersion",
                  (wchar_t *)L"GetNamedString failed to get QuestionVersion.");
                WindowsDeleteString(v59);
                v59 = 0;
                v43 = v58;
                if ( v58 )
                {
                  v58 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v43 + 16LL))(v43);
                }
              }
LABEL_62:
              if ( (unsigned int)dword_140028000 <= 2 )
                goto LABEL_80;
              v14 = qword_140028018;
              if ( (qword_140028010 & 0x400000000000LL) == 0 || (qword_140028018 & 0x400000000000LL) != qword_140028018 )
                goto LABEL_80;
              LODWORD(v58) = 153;
              v62 = "GetQuestionDetails";
              v61 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
              v29 = "Failed to get GetQuestionVersion.";
              v16 = (char *)&dword_140022524;
              goto LABEL_78;
            }
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v39, v40, v41);
          }
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v32, v33, v34);
          JUMPOUT(0x14000ECB9LL);
        }
      }
    }
    else
    {
      WideStringFromBase64 = -2147024809;
    }
    if ( (unsigned int)dword_140028000 <= 2 )
      goto LABEL_80;
    v14 = qword_140028018;
    if ( (qword_140028010 & 0x400000000000LL) == 0 || (qword_140028018 & 0x400000000000LL) != qword_140028018 )
      goto LABEL_80;
    LODWORD(v58) = 131;
    v62 = "GetQuestionDetails";
    v61 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
    v29 = "Failed in StringCchCopyNW";
    v16 = byte_140022959;
    goto LABEL_78;
  }
  WideStringFromBase64 = -2147024882;
LABEL_80:
  v49 = lpMem;
  if ( lpMem )
  {
    v50 = GetProcessHeap();
    HeapFree(v50, 0, v49);
  }
  if ( v7 )
  {
    v51 = GetProcessHeap();
    HeapFree(v51, 0, v7);
  }
  if ( v6 )
  {
    v52 = *(__int64 **)v6;
    if ( *(_QWORD *)v6 )
    {
      *(_QWORD *)v6 = 0;
      (*(void (__fastcall **)(__int64 *))(*v52 + 16))(v52);
    }
    operator delete(v6);
  }
  return (unsigned int)WideStringFromBase64;
}

```

## disassembly

```asm
0x14000e290  mov     [rsp-8+arg_18], rbx
0x14000e295  push    rbp
0x14000e296  push    rsi
0x14000e297  push    rdi
0x14000e298  push    r12
0x14000e29a  push    r13
0x14000e29c  push    r14
0x14000e29e  push    r15
0x14000e2a0  lea     rbp, [rsp-27h]
0x14000e2a5  sub     rsp, 100h
0x14000e2ac  mov     rax, cs:__security_cookie
0x14000e2b3  xor     rax, rsp
0x14000e2b6  mov     [rbp+57h+var_40], rax
0x14000e2ba  mov     r13, r8
0x14000e2bd  mov     r14, rdx
0x14000e2c0  mov     rdi, rcx
0x14000e2c3  xor     esi, esi
0x14000e2c5  mov     r15d, esi
0x14000e2c8  mov     [rbp+57h+var_B0], rsi
0x14000e2cc  mov     [rbp+57h+lpMem], rsi
0x14000e2d0  mov     [rbp+57h+length], esi
0x14000e2d3  mov     r12d, esi
0x14000e2d6  mov     [rbp+57h+pszString], rsi
0x14000e2da  mov     [rbp+57h+cchString], esi
0x14000e2dd  xorps   xmm0, xmm0
0x14000e2e0  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x14000e2e4  test    rcx, rcx
0x14000e2e7  jnz     short loc_14000E2F3
0x14000e2e9  mov     ebx, 80004003h
0x14000e2ee  jmp     loc_14000EC80
0x14000e2f3  test    r14, r14
0x14000e2f6  jz      short loc_14000E2E9
0x14000e2f8  test    r13, r13
0x14000e2fb  jz      short loc_14000E2E9
0x14000e2fd  xor     edx, edx; Val
0x14000e2ff  lea     r8d, [rdx+4Ah]; Size
0x14000e303  mov     rcx, r13; void *
0x14000e306  call    memset_0
0x14000e30b  mov     dword ptr [r14], 1
0x14000e312  mov     [rbp+57h+var_7C], esi
0x14000e315  mov     rax, [rdi]
0x14000e318  lea     rdx, [rbp+57h+var_7C]
0x14000e31c  mov     rcx, rdi
0x14000e31f  mov     rax, [rax+30h]
0x14000e323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e328  mov     ebx, eax
0x14000e32a  test    eax, eax
0x14000e32c  jns     loc_14000E3EB
0x14000e332  mov     ecx, cs:dword_140028000
0x14000e338  cmp     ecx, 2
0x14000e33b  jbe     loc_14000EC80
0x14000e341  mov     r8, cs:qword_140028018
0x14000e348  mov     rcx, cs:qword_140028010
0x14000e34f  mov     rdx, 400000000000h
0x14000e359  test    rdx, rcx
0x14000e35c  jz      loc_14000EC80
0x14000e362  mov     rax, r8
0x14000e365  and     rax, rdx
0x14000e368  cmp     rax, r8
0x14000e36b  jnz     loc_14000EC80
0x14000e371  mov     [rbp+57h+lpMem], 1000000h
0x14000e379  mov     [rbp+57h+length], 67h ; 'g'
0x14000e380  lea     rax, aGetquestiondet; "GetQuestionDetails"
0x14000e387  mov     [rbp+57h+var_B0], rax
0x14000e38b  lea     rax, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000e392  mov     [rbp+57h+var_A8], rax
0x14000e396  mov     dword ptr [rbp+57h+var_B8], ebx
0x14000e399  lea     rax, aFailedToReadTh; "Failed to read the SiufData node"
0x14000e3a0  mov     [rbp+57h+var_A0], rax
0x14000e3a4  lea     rax, [rbp+57h+lpMem]
0x14000e3a8  mov     [rsp+130h+var_E8], rax
0x14000e3ad  lea     rax, [rbp+57h+length]
0x14000e3b1  mov     [rsp+130h+var_F0], rax
0x14000e3b6  lea     rax, [rbp+57h+var_B0]
0x14000e3ba  mov     [rsp+130h+var_F8], rax
0x14000e3bf  lea     rax, [rbp+57h+var_A8]
0x14000e3c3  mov     [rsp+130h+var_100], rax
0x14000e3c8  lea     rax, [rbp+57h+var_B8]
0x14000e3cc  mov     [rsp+130h+var_108], rax
0x14000e3d1  lea     rax, [rbp+57h+var_A0]
0x14000e3d5  lea     rdx, byte_140022B2F
0x14000e3dc  mov     [rsp+130h+var_110], rax
0x14000e3e1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000e3e6  jmp     loc_14000EC80
0x14000e3eb  mov     rax, [rdi]
0x14000e3ee  lea     r8, [rbp+57h+cchString]
0x14000e3f2  lea     rdx, [rbp+57h+pszString]
0x14000e3f6  mov     rcx, rdi
0x14000e3f9  mov     rax, [rax+80h]
0x14000e400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e405  mov     ebx, eax
0x14000e407  test    eax, eax
0x14000e409  jns     loc_14000E4BE
0x14000e40f  mov     eax, cs:dword_140028000
0x14000e415  cmp     eax, 2
0x14000e418  jbe     loc_14000EC80
0x14000e41e  mov     rcx, cs:qword_140028018
0x14000e425  mov     rax, cs:qword_140028010
0x14000e42c  mov     rdx, 400000000000h
0x14000e436  test    rdx, rax
0x14000e439  jz      loc_14000EC80
0x14000e43f  mov     rax, rcx
0x14000e442  and     rax, rdx
0x14000e445  cmp     rax, rcx
0x14000e448  jnz     loc_14000EC80
0x14000e44e  mov     [rbp+57h+var_A0], 1000000h
0x14000e456  mov     dword ptr [rbp+57h+var_B8], 6Eh ; 'n'
0x14000e45d  lea     rax, aGetquestiondet; "GetQuestionDetails"
0x14000e464  mov     [rbp+57h+var_A8], rax
0x14000e468  lea     rax, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000e46f  mov     [rbp+57h+lpMem], rax
0x14000e473  mov     [rbp+57h+length], ebx
0x14000e476  lea     rax, aFailedToGetSiu_0; "Failed to get SiufData node value"
0x14000e47d  mov     [rbp+57h+var_B0], rax
0x14000e481  lea     rax, [rbp+57h+var_A0]
0x14000e485  mov     [rsp+130h+var_E8], rax
0x14000e48a  lea     rax, [rbp+57h+var_B8]
0x14000e48e  mov     [rsp+130h+var_F0], rax
0x14000e493  lea     rax, [rbp+57h+var_A8]
0x14000e497  mov     [rsp+130h+var_F8], rax
0x14000e49c  lea     rax, [rbp+57h+lpMem]
0x14000e4a0  mov     [rsp+130h+var_100], rax
0x14000e4a5  lea     rax, [rbp+57h+length]
0x14000e4a9  mov     [rsp+130h+var_108], rax
0x14000e4ae  lea     rax, [rbp+57h+var_B0]
0x14000e4b2  lea     rdx, byte_140022AD1
0x14000e4b9  jmp     loc_14000E3DC
0x14000e4be  lea     r9, [rbp+57h+length]; unsigned int *
0x14000e4c2  lea     r8, [rbp+57h+lpMem]; unsigned __int16 **
0x14000e4c6  mov     edx, [rbp+57h+cchString]; cchString
0x14000e4c9  mov     rcx, [rbp+57h+pszString]; pszString
0x14000e4cd  call    ?GetWideStringFromBase64@@YAJPEBGIPEAPEAGPEAI@Z; GetWideStringFromBase64(ushort const *,uint,ushort * *,uint *)
0x14000e4d2  mov     ebx, eax
0x14000e4d4  test    eax, eax
0x14000e4d6  jns     loc_14000E588
0x14000e4dc  mov     eax, cs:dword_140028000
0x14000e4e2  cmp     eax, 2
0x14000e4e5  jbe     loc_14000EC06
0x14000e4eb  mov     rcx, cs:qword_140028018
0x14000e4f2  mov     rax, cs:qword_140028010
0x14000e4f9  mov     rdx, 400000000000h
0x14000e503  test    rdx, rax
0x14000e506  jz      loc_14000EC06
0x14000e50c  mov     rax, rcx
0x14000e50f  and     rax, rdx
0x14000e512  cmp     rax, rcx
0x14000e515  jnz     loc_14000EC06
0x14000e51b  mov     [rbp+57h+var_A0], 1000000h
0x14000e523  mov     dword ptr [rbp+57h+var_B8], 76h ; 'v'
0x14000e52a  lea     rax, aGetquestiondet; "GetQuestionDetails"
0x14000e531  mov     [rbp+57h+var_A8], rax
0x14000e535  lea     rax, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000e53c  mov     [rbp+57h+var_B0], rax
0x14000e540  lea     rax, aFailedInGetwid; "Failed in GetWideStringFromBase64"
0x14000e547  mov     [rbp+57h+var_98], rax
0x14000e54b  lea     rax, [rbp+57h+var_A0]
0x14000e54f  mov     [rsp+130h+var_E8], rax
0x14000e554  lea     rax, [rbp+57h+var_B8]
0x14000e558  mov     [rsp+130h+var_F0], rax
0x14000e55d  lea     rax, [rbp+57h+var_A8]
0x14000e561  mov     [rsp+130h+var_F8], rax
0x14000e566  lea     rax, [rbp+57h+var_B0]
0x14000e56a  mov     [rsp+130h+var_100], rax
0x14000e56f  lea     rax, [rbp+57h+length]
0x14000e573  mov     [rsp+130h+var_108], rax
0x14000e578  lea     rax, [rbp+57h+var_98]
0x14000e57c  lea     rdx, dword_1400223AC
0x14000e583  jmp     loc_14000EBF9
0x14000e588  mov     esi, [rbp+57h+length]
0x14000e58b  lea     rdi, [rsi+2]
0x14000e58f  shr     rdi, 1
0x14000e592  lea     rbx, [rdi+rdi]
0x14000e596  call    cs:__imp_GetProcessHeap
0x14000e59d  nop     dword ptr [rax+rax+00h]
0x14000e5a2  mov     rcx, rax; hHeap
0x14000e5a5  mov     r8, rbx; dwBytes
0x14000e5a8  mov     edx, 8; dwFlags
0x14000e5ad  call    cs:__imp_HeapAlloc
0x14000e5b4  nop     dword ptr [rax+rax+00h]
0x14000e5b9  mov     r12, rax
0x14000e5bc  mov     [rbp+57h+var_98], rax
0x14000e5c0  test    rax, rax
0x14000e5c3  jnz     short loc_14000E5D1
0x14000e5c5  mov     ebx, 8007000Eh
0x14000e5ca  xor     esi, esi
0x14000e5cc  jmp     loc_14000EC06
0x14000e5d1  test    rdi, rdi
0x14000e5d4  jz      loc_14000EB47
0x14000e5da  cmp     rdi, 7FFFFFFFh
0x14000e5e1  jbe     short loc_14000E5EF
0x14000e5e3  mov     ebx, 80070057h
0x14000e5e8  xor     esi, esi
0x14000e5ea  jmp     loc_14000EB53
0x14000e5ef  shr     rsi, 1
0x14000e5f2  cmp     rsi, 7FFFFFFEh
0x14000e5f9  ja      short loc_14000E5E3
0x14000e5fb  mov     rax, [rbp+57h+lpMem]
0x14000e5ff  mov     rdx, r12
0x14000e602  test    rsi, rsi
0x14000e605  jz      short loc_14000E623
0x14000e607  movzx   ecx, word ptr [rax]
0x14000e60a  test    cx, cx
0x14000e60d  jz      short loc_14000E623
0x14000e60f  add     rax, 2
0x14000e613  mov     [rdx], cx
0x14000e616  add     rdx, 2
0x14000e61a  dec     rsi
0x14000e61d  sub     rdi, 1
0x14000e621  jnz     short loc_14000E602
0x14000e623  mov     rax, rdi
0x14000e626  neg     rax
0x14000e629  sbb     ebx, ebx
0x14000e62b  not     ebx
0x14000e62d  and     ebx, 8007007Ah
0x14000e633  lea     rcx, [rdx-2]
0x14000e637  xor     esi, esi
0x14000e639  test    rdi, rdi
0x14000e63c  cmovnz  rcx, rdx
0x14000e640  mov     [rcx], si
0x14000e643  jz      loc_14000EB56
0x14000e649  lea     rdx, [rbp+57h+var_98]
0x14000e64d  lea     rcx, [rbp+57h+hstringHeader]
0x14000e651  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x14000e656  nop
0x14000e657  lea     rdx, [rbp+57h+var_B0]; struct Windows::Internal::Feedback::SiufPayloadImpl **
0x14000e65b  mov     rcx, [rax+18h]; HSTRING
0x14000e65f  call    ?Parse@SiufPayloadImpl@Feedback@Internal@Windows@@SAJPEAUHSTRING__@@PEAPEAV1234@@Z; Windows::Internal::Feedback::SiufPayloadImpl::Parse(HSTRING__ *,Windows::Internal::Feedback::SiufPayloadImpl * *)
0x14000e664  mov     ebx, eax
0x14000e666  test    eax, eax
0x14000e668  jns     loc_14000E727
0x14000e66e  mov     eax, cs:dword_140028000
0x14000e674  cmp     eax, 2
0x14000e677  jbe     loc_14000E71E
0x14000e67d  mov     rcx, cs:qword_140028018
0x14000e684  mov     rax, cs:qword_140028010
0x14000e68b  mov     rdx, 400000000000h
0x14000e695  test    rdx, rax
0x14000e698  jz      loc_14000E71E
0x14000e69e  mov     rax, rcx
0x14000e6a1  and     rax, rdx
0x14000e6a4  cmp     rax, rcx
0x14000e6a7  jnz     short loc_14000E71E
0x14000e6a9  mov     [rbp+57h+var_98], 1000000h
0x14000e6b1  mov     dword ptr [rbp+57h+var_B8], 8Bh
0x14000e6b8  lea     rax, aGetquestiondet; "GetQuestionDetails"
0x14000e6bf  mov     [rbp+57h+var_A0], rax
0x14000e6c3  lea     rax, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000e6ca  mov     [rbp+57h+var_A8], rax
0x14000e6ce  mov     [rbp+57h+length], ebx
0x14000e6d1  lea     rax, aFailedToParseS; "Failed to parse SIUF Payload."
0x14000e6d8  mov     [rbp+57h+var_90], rax
0x14000e6dc  lea     rax, [rbp+57h+var_98]
0x14000e6e0  mov     [rsp+130h+var_E8], rax
0x14000e6e5  lea     rax, [rbp+57h+var_B8]
0x14000e6e9  mov     [rsp+130h+var_F0], rax
0x14000e6ee  lea     rax, [rbp+57h+var_A0]
0x14000e6f2  mov     [rsp+130h+var_F8], rax
0x14000e6f7  lea     rax, [rbp+57h+var_A8]
0x14000e6fb  mov     [rsp+130h+var_100], rax
0x14000e700  lea     rax, [rbp+57h+length]
0x14000e704  mov     [rsp+130h+var_108], rax
0x14000e709  lea     rax, [rbp+57h+var_90]
0x14000e70d  mov     [rsp+130h+var_110], rax
0x14000e712  lea     rdx, byte_140022783
0x14000e719  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000e71e  mov     r15, [rbp+57h+var_B0]
0x14000e722  jmp     loc_14000EC06
0x14000e727  mov     rdx, r14; unsigned int *
0x14000e72a  mov     r15, [rbp+57h+var_B0]
0x14000e72e  mov     rcx, r15; this
0x14000e731  call    ?GetVersion@SiufPayloadImpl@Feedback@Internal@Windows@@QEAAJPEAI@Z; Windows::Internal::Feedback::SiufPayloadImpl::GetVersion(uint *)
0x14000e736  mov     ebx, eax
0x14000e738  test    eax, eax
0x14000e73a  jns     short loc_14000E7AB
0x14000e73c  mov     eax, cs:dword_140028000
0x14000e742  cmp     eax, 2
0x14000e745  jbe     loc_14000EC06
0x14000e74b  mov     rcx, cs:qword_140028018
0x14000e752  mov     rax, cs:qword_140028010
0x14000e759  mov     rdx, 400000000000h
0x14000e763  test    rdx, rax
0x14000e766  jz      loc_14000EC06
0x14000e76c  mov     rax, rcx
0x14000e76f  and     rax, rdx
0x14000e772  cmp     rax, rcx
0x14000e775  jnz     loc_14000EC06
0x14000e77b  mov     dword ptr [rbp+57h+var_B8], 92h
0x14000e782  lea     rax, aGetquestiondet; "GetQuestionDetails"
0x14000e789  mov     [rbp+57h+var_98], rax
0x14000e78d  lea     rax, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000e794  mov     [rbp+57h+var_A0], rax
0x14000e798  lea     rax, aFailedToGetGet_0; "Failed to get GetVersion."
0x14000e79f  lea     rdx, byte_1400226C7
0x14000e7a6  jmp     loc_14000EBBC
0x14000e7ab  mov     [rbp+57h+length], esi
0x14000e7ae  xorps   xmm0, xmm0
0x14000e7b1  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x14000e7b5  mov     [rbp+57h+var_B8], rsi
0x14000e7b9  mov     rbx, [r15]
0x14000e7bc  mov     rdi, [rbx]
  ... truncated ...
```
