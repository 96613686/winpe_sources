# GetRingMapAndSIUFConfigFromOneSettingsResponse(uchar *,uint,_RING_MAP * *)

- ea: `0x140013b84`
- end: `0x14001449d`
- name: `?GetRingMapAndSIUFConfigFromOneSettingsResponse@@YAJPEAEIPEAPEAU_RING_MAP@@@Z`
- size: `2329`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, int cbMultiByte, struct _RING_MAP **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015aec`

## callees

- `0x140001414`
- `0x14000a9f0`
- `0x140013b84`
- `0x1400187e0`
- `0x140019010`

## import_xrefs

- `msvcrt!_wtoi64` at `0x140014382`
- `msvcrt!_wtoi64` at `0x140014382`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140013cfd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140013e23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140013cfd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140013e23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013cec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013e0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400143b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400143d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013cec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013e0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400143b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400143d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400143c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400143e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400143c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400143e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013c25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013d38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013c25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013d38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140014379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140014379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140013e59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140013f1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140014089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001418b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140013e59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140013f1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140014089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001418b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001413d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140014394`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001413d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140014394`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140013e76`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140013e76`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140013c11`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140013d2a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140013c11`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140013d2a`

## string_xrefs

- `0x140013e52`: `Windows.Data.Json.JsonObject`
- `0x140013ffd`: `Json not parsed`
- `0x140013c88`: `GetRingMapAndSIUFConfigFromOneSettingsResponse`
- `0x140013d97`: `GetRingMapAndSIUFConfigFromOneSettingsResponse`
- `0x140014047`: `GetRingMapAndSIUFConfigFromOneSettingsResponse`
- `0x140014118`: `GetRingMapAndSIUFConfigFromOneSettingsResponse`
- `0x14001432b`: `StringCchCopy failed`

## pseudocode

```c
__int64 __fastcall GetRingMapAndSIUFConfigFromOneSettingsResponse(
        LPCCH lpMultiByteStr,
        int cbMultiByte,
        struct _RING_MAP **a3)
{
  unsigned int v5; // r13d
  signed int ActivationFactory; // ebx
  int v7; // eax
  int cchWideChar; // r14d
  WCHAR *v9; // r12
  signed int LastError; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *lpWideCharStr; // rax
  signed int v16; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  HANDLE v19; // rax
  unsigned int *v20; // rax
  unsigned int *v21; // r15
  HRESULT v22; // eax
  int v23; // edx
  unsigned int v24; // r8d
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rcx
  char *v28; // rax
  char *v29; // rdx
  __int64 v30; // rbx
  unsigned __int64 v31; // rdx
  HRESULT v32; // eax
  int v33; // edx
  unsigned int v34; // r8d
  __int64 v35; // rbx
  HRESULT v36; // eax
  int v37; // edx
  unsigned int v38; // r8d
  __int64 v39; // rbx
  const WCHAR *v40; // rcx
  unsigned __int64 v41; // rdx
  HRESULT v42; // eax
  int v43; // edx
  unsigned int v44; // r8d
  unsigned int v45; // eax
  __int64 v46; // r9
  __int64 v47; // rbx
  __int64 v48; // rax
  unsigned __int16 * near *v49; // rcx
  __int64 v50; // rdx
  unsigned int *v51; // r8
  __int16 v52; // r9
  unsigned int *v53; // rcx
  const wchar_t *StringRawBuffer; // rax
  HANDLE v55; // rax
  HANDLE v56; // rax
  unsigned int v58; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v59; // [rsp+54h] [rbp-65h] BYREF
  char v60[8]; // [rsp+58h] [rbp-61h] BYREF
  HSTRING v61; // [rsp+60h] [rbp-59h] BYREF
  const char *v62; // [rsp+68h] [rbp-51h] BYREF
  const char *v63; // [rsp+70h] [rbp-49h] BYREF
  __int64 v64; // [rsp+78h] [rbp-41h] BYREF
  __int64 *v65; // [rsp+80h] [rbp-39h] BYREF
  __int64 *v66; // [rsp+88h] [rbp-31h] BYREF
  __int64 *v67; // [rsp+90h] [rbp-29h] BYREF
  __int64 v68; // [rsp+98h] [rbp-21h] BYREF
  struct _RING_MAP **v69; // [rsp+A0h] [rbp-19h]
  __int64 v70; // [rsp+A8h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-9h] BYREF
  HSTRING string; // [rsp+C8h] [rbp+Fh] BYREF

  v69 = a3;
  v5 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v60[0] = 0;
  v70 = 0;
  if ( !lpMultiByteStr || !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  if ( !cbMultiByte )
    return (unsigned int)-2147024809;
  v7 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, cbMultiByte, 0, 0);
  cchWideChar = v7;
  if ( !v7 )
  {
    v9 = 0;
    LastError = GetLastError();
    ActivationFactory = LastError;
    if ( LastError > 0 )
      ActivationFactory = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_140027000 > 2
      && (qword_140027010 & 0x400000000000LL) != 0
      && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
    {
      v61 = (HSTRING)0x1000000;
      v59 = 837;
      v62 = "GetRingMapAndSIUFConfigFromOneSettingsResponse";
      v63 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
      v58 = ActivationFactory;
      v64 = (__int64)"MultiByteToWideChar failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_140027018,
        (__int64)byte_140022BA1,
        v11,
        v12,
        (const unsigned __int16 **)&v64,
        (__int64)&v58,
        (const unsigned __int16 **)&v63,
        (const unsigned __int16 **)&v62,
        (__int64)&v59,
        (__int64)&v61);
    }
    goto LABEL_22;
  }
  v13 = 2 * v7;
  ProcessHeap = GetProcessHeap();
  lpWideCharStr = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v13);
  v9 = lpWideCharStr;
  if ( !lpWideCharStr )
  {
    ActivationFactory = -2147024882;
    goto LABEL_83;
  }
  if ( MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, cbMultiByte, lpWideCharStr, cchWideChar) )
  {
    v19 = GetProcessHeap();
    v20 = (unsigned int *)HeapAlloc(v19, 8u, 0x388u);
    v21 = v20;
    if ( !v20 )
    {
      ActivationFactory = -2147024882;
LABEL_82:
      v56 = GetProcessHeap();
      HeapFree(v56, 0, v9);
      goto LABEL_83;
    }
    v20[1] = 904;
    *v20 = 0;
    string = 0;
    v22 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
    if ( v22 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
      __debugbreak();
    }
    ActivationFactory = RoGetActivationFactory(string, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v65);
    if ( ActivationFactory >= 0 )
    {
      v30 = *v65;
      string = 0;
      v31 = -1;
      do
        ++v31;
      while ( v9[v31] );
      if ( v31 > 0xFFFFFFFF )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v31, v25);
        __debugbreak();
      }
      if ( (int)v31 + 1 < (unsigned int)v31 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v31, v25);
        __debugbreak();
      }
      v32 = WindowsCreateStringReference(v9, v31, &hstringHeader, &string);
      if ( v32 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v32, v33, v34);
        __debugbreak();
      }
      ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 **, char *))(v30 + 56))(
                            v65,
                            string,
                            &v66,
                            v60);
      if ( ActivationFactory >= 0 )
      {
        if ( v60[0] )
        {
          v35 = *v66;
          string = 0;
          v36 = WindowsCreateStringReference(L"settings", 8u, &hstringHeader, &string);
          if ( v36 < 0 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v36, v37, v38);
LABEL_95:
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v42, v43, v44);
            __debugbreak();
          }
          ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 **))(v35 + 64))(v66, string, &v67);
          if ( ActivationFactory >= 0 )
          {
            do
            {
              v61 = 0;
              v58 = *v21;
              v39 = *v67;
              WindowsDeleteString(0);
              v61 = 0;
              string = 0;
              v40 = (const WCHAR *)(&DefaultRingNames)[v5];
              v41 = -1;
              do
                ++v41;
              while ( v40[v41] );
              if ( v41 > 0xFFFFFFFF )
              {
                Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v41, 0);
                JUMPOUT(0x14001449CLL);
              }
              if ( (int)v41 + 1 < (unsigned int)v41 )
              {
                Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v41, 0);
                __debugbreak();
              }
              v42 = WindowsCreateStringReference(v40, v41, &hstringHeader, &string);
              if ( v42 < 0 )
                goto LABEL_95;
              v45 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING *))(v39 + 80))(v67, string, &v61);
              if ( v45 )
              {
                if ( v45 != -2089484279
                  && (unsigned int)dword_140027000 > 2
                  && (qword_140027010 & 0x400000000000LL) != 0
                  && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
                {
                  v64 = 0x1000000;
                  v58 = 926;
                  v63 = "GetRingMapAndSIUFConfigFromOneSettingsResponse";
                  v62 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
                  v59 = v45;
                  v68 = (__int64)"GetNamedString failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                    qword_140027010,
                    (__int64)byte_1400229CB,
                    v45,
                    v46,
                    (const unsigned __int16 **)&v68,
                    (__int64)&v59,
                    (const unsigned __int16 **)&v62,
                    (const unsigned __int16 **)&v63,
                    (__int64)&v58,
                    (__int64)&v64);
                }
              }
              else
              {
                v47 = 28LL * v58;
                v48 = 2147483646;
                v49 = (&DefaultRingNames)[v5];
                v50 = 51;
                v51 = &v21[v47 + 2];
                do
                {
                  if ( !v48 )
                    break;
                  v52 = *(_WORD *)v49;
                  if ( !*(_WORD *)v49 )
                    break;
                  v49 = (unsigned __int16 * near *)((char *)v49 + 2);
                  *(_WORD *)v51 = v52;
                  v51 = (unsigned int *)((char *)v51 + 2);
                  --v48;
                  --v50;
                }
                while ( v50 );
                v53 = (unsigned int *)((char *)v51 - 2);
                if ( v50 )
                  v53 = v51;
                *(_WORD *)v53 = 0;
                if ( v50 )
                {
                  StringRawBuffer = WindowsGetStringRawBuffer(v61, 0);
                  *(_QWORD *)&v21[v47 + 28] = _wtoi64(StringRawBuffer);
                  ++*v21;
                }
                else if ( (unsigned int)dword_140027000 > 2
                       && (qword_140027010 & 0x400000000000LL) != 0
                       && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
                {
                  v68 = 0x1000000;
                  v58 = 941;
                  v64 = (__int64)"GetRingMapAndSIUFConfigFromOneSettingsResponse";
                  v63 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
                  v59 = v50 == 0 ? 0x8007007A : 0;
                  v62 = "StringCchCopy failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                    qword_140027018,
                    (__int64)&byte_140022A87,
                    (__int64)v51,
                    v59,
                    (const unsigned __int16 **)&v62,
                    (__int64)&v59,
                    (const unsigned __int16 **)&v63,
                    (const unsigned __int16 **)&v64,
                    (__int64)&v58,
                    (__int64)&v68);
                }
              }
              WindowsDeleteString(v61);
              ++v5;
            }
            while ( v5 < 8 );
            if ( *v21 )
            {
              *v69 = (struct _RING_MAP *)v21;
              ActivationFactory = 0;
              goto LABEL_82;
            }
            ActivationFactory = 6148405;
            goto LABEL_80;
          }
          if ( (unsigned int)dword_140027000 <= 2
            || (v27 = qword_140027018, (qword_140027010 & 0x400000000000LL) == 0)
            || (qword_140027018 & 0x400000000000LL) != qword_140027018 )
          {
LABEL_80:
            v55 = GetProcessHeap();
            HeapFree(v55, 0, v21);
            goto LABEL_82;
          }
          v58 = 908;
          v59 = ActivationFactory;
          v28 = "GetNamedObject failed";
          v29 = byte_140022D19;
        }
        else
        {
          ActivationFactory = -2147467259;
          if ( (unsigned int)dword_140027000 <= 2 )
            goto LABEL_80;
          v27 = qword_140027018;
          if ( (qword_140027010 & 0x400000000000LL) == 0 || (qword_140027018 & 0x400000000000LL) != qword_140027018 )
            goto LABEL_80;
          v58 = 899;
          v59 = -2147467259;
          v28 = "Json not parsed";
          v29 = byte_140022E3D;
        }
      }
      else
      {
        if ( (unsigned int)dword_140027000 <= 2 )
          goto LABEL_80;
        v27 = qword_140027018;
        if ( (qword_140027010 & 0x400000000000LL) == 0 || (qword_140027018 & 0x400000000000LL) != qword_140027018 )
          goto LABEL_80;
        v58 = 892;
        v59 = ActivationFactory;
        v28 = "TryParse failed";
        v29 = &byte_140022BFF;
      }
    }
    else
    {
      if ( (unsigned int)dword_140027000 <= 2 )
        goto LABEL_80;
      v27 = qword_140027010;
      if ( (qword_140027010 & 0x400000000000LL) == 0 || (qword_140027018 & 0x400000000000LL) != qword_140027018 )
        goto LABEL_80;
      v58 = 882;
      v59 = ActivationFactory;
      v28 = "GetActivationFactory failed";
      v29 = byte_140022853;
    }
    v61 = (HSTRING)v28;
    v62 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
    v63 = "GetRingMapAndSIUFConfigFromOneSettingsResponse";
    v64 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v27,
      (__int64)v29,
      v25,
      v26,
      (const unsigned __int16 **)&v61,
      (__int64)&v59,
      (const unsigned __int16 **)&v62,
      (const unsigned __int16 **)&v63,
      (__int64)&v58,
      (__int64)&v64);
    goto LABEL_80;
  }
  v16 = GetLastError();
  ActivationFactory = v16;
  if ( v16 > 0 )
    ActivationFactory = (unsigned __int16)v16 | 0x80070000;
  if ( (unsigned int)dword_140027000 > 2
    && (qword_140027010 & 0x400000000000LL) != 0
    && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
  {
    v64 = 0x1000000;
    v58 = 859;
    v63 = "GetRingMapAndSIUFConfigFromOneSettingsResponse";
    v62 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
    v59 = ActivationFactory;
    v61 = (HSTRING)"MultiByteToWideChar failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      qword_140027018,
      (__int64)&byte_140022797,
      v17,
      v18,
      (const unsigned __int16 **)&v61,
      (__int64)&v59,
      (const unsigned __int16 **)&v62,
      (const unsigned __int16 **)&v63,
      (__int64)&v58,
      (__int64)&v64);
  }
LABEL_22:
  if ( v9 )
    goto LABEL_82;
LABEL_83:
  if ( v65 )
    (*(void (__fastcall **)(__int64 *))(*v65 + 16))(v65);
  if ( v66 )
    (*(void (__fastcall **)(__int64 *))(*v66 + 16))(v66);
  if ( v67 )
    (*(void (__fastcall **)(__int64 *))(*v67 + 16))(v67);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x140013b84  mov     [rsp-8+arg_18], rbx
0x140013b89  push    rbp
0x140013b8a  push    rsi
0x140013b8b  push    rdi
0x140013b8c  push    r12
0x140013b8e  push    r13
0x140013b90  push    r14
0x140013b92  push    r15
0x140013b94  lea     rbp, [rsp-27h]
0x140013b99  sub     rsp, 0E0h
0x140013ba0  mov     rax, cs:__security_cookie
0x140013ba7  xor     rax, rsp
0x140013baa  mov     [rbp+57h+var_40], rax
0x140013bae  mov     rax, r8
0x140013bb1  mov     [rbp+57h+var_70], rax
0x140013bb5  mov     edi, edx
0x140013bb7  mov     rsi, rcx
0x140013bba  xor     r13d, r13d
0x140013bbd  mov     [rbp+57h+var_90], r13
0x140013bc1  mov     [rbp+57h+var_88], r13
0x140013bc5  mov     [rbp+57h+var_80], r13
0x140013bc9  mov     [rbp+57h+var_B8], r13b
0x140013bcd  mov     [rbp+57h+var_68], r13
0x140013bd1  test    rcx, rcx
0x140013bd4  jnz     short loc_140013BE0
0x140013bd6  mov     ebx, 80004003h
0x140013bdb  jmp     loc_140014428
0x140013be0  test    rax, rax
0x140013be3  jz      short loc_140013BD6
0x140013be5  mov     [r8], r13
0x140013be8  test    edi, edi
0x140013bea  jnz     short loc_140013BF6
0x140013bec  mov     ebx, 80070057h
0x140013bf1  jmp     loc_140014428
0x140013bf6  mov     [rsp+110h+cchWideChar], r13d; cchWideChar
0x140013bfb  mov     [rsp+110h+lpWideCharStr], r13; lpWideCharStr
0x140013c00  mov     r9d, edi; cbMultiByte
0x140013c03  mov     r8, rsi; lpMultiByteStr
0x140013c06  xor     edx, edx; dwFlags
0x140013c08  mov     r15d, 0FDE9h
0x140013c0e  mov     ecx, r15d; CodePage
0x140013c11  call    cs:__imp_MultiByteToWideChar
0x140013c17  mov     r14d, eax
0x140013c1a  test    eax, eax
0x140013c1c  jnz     loc_140013CE9
0x140013c22  mov     r12, r13
0x140013c25  call    cs:__imp_GetLastError
0x140013c2b  mov     ebx, eax
0x140013c2d  test    eax, eax
0x140013c2f  jle     short loc_140013C3A
0x140013c31  movzx   ebx, ax
0x140013c34  or      ebx, 80070000h
0x140013c3a  mov     eax, cs:dword_140027000
0x140013c40  cmp     eax, 2
0x140013c43  jbe     loc_140013DFD
0x140013c49  mov     rcx, cs:qword_140027018
0x140013c50  mov     rax, cs:qword_140027010
0x140013c57  mov     rdi, 400000000000h
0x140013c61  test    rdi, rax
0x140013c64  jz      loc_140013DFD
0x140013c6a  mov     rax, rcx
0x140013c6d  and     rax, rdi
0x140013c70  cmp     rax, rcx
0x140013c73  jnz     loc_140013DFD
0x140013c79  mov     [rbp+57h+var_B0], 1000000h
0x140013c81  mov     [rbp+57h+var_BC], 345h
0x140013c88  lea     rsi, aGetringmapands; "GetRingMapAndSIUFConfigFromOneSettingsR"...
0x140013c8f  mov     [rbp+57h+var_A8], rsi
0x140013c93  lea     r14, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140013c9a  mov     [rbp+57h+var_A0], r14
0x140013c9e  mov     [rbp+57h+var_C0], ebx
0x140013ca1  lea     rax, aMultibytetowid; "MultiByteToWideChar failed"
0x140013ca8  mov     [rbp+57h+var_98], rax
0x140013cac  lea     rax, [rbp+57h+var_B0]
0x140013cb0  mov     [rsp+110h+var_C8], rax
0x140013cb5  lea     rax, [rbp+57h+var_BC]
0x140013cb9  mov     [rsp+110h+var_D0], rax
0x140013cbe  lea     rax, [rbp+57h+var_A8]
0x140013cc2  mov     [rsp+110h+var_D8], rax
0x140013cc7  lea     rax, [rbp+57h+var_A0]
0x140013ccb  mov     [rsp+110h+var_E0], rax
0x140013cd0  lea     rax, [rbp+57h+var_C0]
0x140013cd4  mov     qword ptr [rsp+110h+cchWideChar], rax
0x140013cd9  lea     rax, [rbp+57h+var_98]
0x140013cdd  lea     rdx, byte_140022BA1
0x140013ce4  jmp     loc_140013DF3
0x140013ce9  lea     ebx, [rax+rax]
0x140013cec  call    cs:__imp_GetProcessHeap
0x140013cf2  mov     rcx, rax; hHeap
0x140013cf5  mov     r8d, ebx; dwBytes
0x140013cf8  mov     edx, 8; dwFlags
0x140013cfd  call    cs:__imp_HeapAlloc
0x140013d03  mov     r12, rax
0x140013d06  test    rax, rax
0x140013d09  jnz     short loc_140013D15
0x140013d0b  mov     ebx, 8007000Eh
0x140013d10  jmp     loc_1400143E8
0x140013d15  mov     [rsp+110h+cchWideChar], r14d; cchWideChar
0x140013d1a  mov     [rsp+110h+lpWideCharStr], r12; lpWideCharStr
0x140013d1f  mov     r9d, edi; cbMultiByte
0x140013d22  mov     r8, rsi; lpMultiByteStr
0x140013d25  xor     edx, edx; dwFlags
0x140013d27  mov     ecx, r15d; CodePage
0x140013d2a  call    cs:__imp_MultiByteToWideChar
0x140013d30  test    eax, eax
0x140013d32  jnz     loc_140013E0B
0x140013d38  call    cs:__imp_GetLastError
0x140013d3e  mov     ebx, eax
0x140013d40  test    eax, eax
0x140013d42  jle     short loc_140013D4D
0x140013d44  movzx   ebx, ax
0x140013d47  or      ebx, 80070000h
0x140013d4d  mov     eax, cs:dword_140027000
0x140013d53  cmp     eax, 2
0x140013d56  jbe     loc_140013DFD
0x140013d5c  mov     rcx, cs:qword_140027018
0x140013d63  mov     rax, cs:qword_140027010
0x140013d6a  mov     rdi, 400000000000h
0x140013d74  test    rdi, rax
0x140013d77  jz      loc_140013DFD
0x140013d7d  mov     rax, rcx
0x140013d80  and     rax, rdi
0x140013d83  cmp     rax, rcx
0x140013d86  jnz     short loc_140013DFD
0x140013d88  mov     [rbp+57h+var_98], 1000000h
0x140013d90  mov     [rbp+57h+var_C0], 35Bh
0x140013d97  lea     rsi, aGetringmapands; "GetRingMapAndSIUFConfigFromOneSettingsR"...
0x140013d9e  mov     [rbp+57h+var_A0], rsi
0x140013da2  lea     r14, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140013da9  mov     [rbp+57h+var_A8], r14
0x140013dad  mov     [rbp+57h+var_BC], ebx
0x140013db0  lea     rax, aMultibytetowid; "MultiByteToWideChar failed"
0x140013db7  mov     [rbp+57h+var_B0], rax
0x140013dbb  lea     rax, [rbp+57h+var_98]
0x140013dbf  mov     [rsp+110h+var_C8], rax
0x140013dc4  lea     rax, [rbp+57h+var_C0]
0x140013dc8  mov     [rsp+110h+var_D0], rax
0x140013dcd  lea     rax, [rbp+57h+var_A0]
0x140013dd1  mov     [rsp+110h+var_D8], rax
0x140013dd6  lea     rax, [rbp+57h+var_A8]
0x140013dda  mov     [rsp+110h+var_E0], rax
0x140013ddf  lea     rax, [rbp+57h+var_BC]
0x140013de3  mov     qword ptr [rsp+110h+cchWideChar], rax
0x140013de8  lea     rax, [rbp+57h+var_B0]
0x140013dec  lea     rdx, byte_140022797
0x140013df3  mov     [rsp+110h+lpWideCharStr], rax
0x140013df8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140013dfd  test    r12, r12
0x140013e00  jz      loc_1400143E8
0x140013e06  jmp     loc_1400143D4
0x140013e0b  call    cs:__imp_GetProcessHeap
0x140013e11  mov     rcx, rax; hHeap
0x140013e14  mov     ebx, 388h
0x140013e19  mov     r8d, ebx; dwBytes
0x140013e1c  mov     edi, 8
0x140013e21  mov     edx, edi; dwFlags
0x140013e23  call    cs:__imp_HeapAlloc
0x140013e29  mov     r15, rax
0x140013e2c  test    rax, rax
0x140013e2f  jnz     short loc_140013E3B
0x140013e31  mov     ebx, 8007000Eh
0x140013e36  jmp     loc_1400143D4
0x140013e3b  mov     [rax+4], ebx
0x140013e3e  mov     [rax], r13d
0x140013e41  mov     [rbp+57h+string], r13
0x140013e45  lea     r9, [rbp+57h+string]; string
0x140013e49  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x140013e4d  mov     edx, 1Ch; length
0x140013e52  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x140013e59  call    cs:__imp_WindowsCreateStringReference
0x140013e5f  test    eax, eax
0x140013e61  js      loc_140014467
0x140013e67  lea     r8, [rbp+57h+var_90]
0x140013e6b  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x140013e72  mov     rcx, [rbp+57h+string]
0x140013e76  call    cs:__imp_RoGetActivationFactory
0x140013e7c  mov     ebx, eax
0x140013e7e  test    eax, eax
0x140013e80  jns     short loc_140013EDE
0x140013e82  mov     ecx, cs:dword_140027000
0x140013e88  cmp     ecx, 2
0x140013e8b  jbe     loc_1400143B4
0x140013e91  mov     rdx, cs:qword_140027018
0x140013e98  mov     rcx, cs:qword_140027010
0x140013e9f  mov     rdi, 400000000000h
0x140013ea9  test    rdi, rcx
0x140013eac  jz      loc_1400143B4
0x140013eb2  mov     rax, rdx
0x140013eb5  and     rax, rdi
0x140013eb8  cmp     rax, rdx
0x140013ebb  jnz     loc_1400143B4
0x140013ec1  mov     [rbp+57h+var_C0], 372h
0x140013ec8  mov     [rbp+57h+var_BC], ebx
0x140013ecb  lea     rax, aGetactivationf; "GetActivationFactory failed"
0x140013ed2  lea     rdx, byte_140022853
0x140013ed9  jmp     loc_14001400B
0x140013ede  mov     rax, [rbp+57h+var_90]
0x140013ee2  mov     rbx, [rax]
0x140013ee5  mov     [rbp+57h+string], r13
0x140013ee9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140013eed  inc     rdx; int
0x140013ef0  cmp     [r12+rdx*2], r13w
0x140013ef5  jnz     short loc_140013EED
0x140013ef7  mov     eax, 0FFFFFFFFh
0x140013efc  cmp     rdx, rax
0x140013eff  ja      loc_14001445C
0x140013f05  lea     eax, [rdx+1]
0x140013f08  cmp     eax, edx
0x140013f0a  jb      loc_140014451
0x140013f10  lea     r9, [rbp+57h+string]; string
0x140013f14  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x140013f18  mov     rcx, r12; sourceString
0x140013f1b  call    cs:__imp_WindowsCreateStringReference
0x140013f21  test    eax, eax
0x140013f23  js      loc_14001446F
0x140013f29  lea     r9, [rbp+57h+var_B8]
0x140013f2d  lea     r8, [rbp+57h+var_88]
0x140013f31  mov     rdx, [rbp+57h+string]
0x140013f35  mov     rcx, [rbp+57h+var_90]
0x140013f39  mov     rax, [rbx+38h]
0x140013f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f42  mov     ebx, eax
0x140013f44  test    eax, eax
0x140013f46  jns     short loc_140013FA1
0x140013f48  mov     eax, cs:dword_140027000
0x140013f4e  cmp     eax, 2
0x140013f51  jbe     loc_1400143B4
0x140013f57  mov     rcx, cs:qword_140027018
0x140013f5e  mov     rax, cs:qword_140027010
0x140013f65  mov     rdi, 400000000000h
0x140013f6f  test    rdi, rax
0x140013f72  jz      loc_1400143B4
0x140013f78  mov     rax, rcx
0x140013f7b  and     rax, rdi
0x140013f7e  cmp     rax, rcx
0x140013f81  jnz     loc_1400143B4
0x140013f87  mov     [rbp+57h+var_C0], 37Ch
0x140013f8e  mov     [rbp+57h+var_BC], ebx
0x140013f91  lea     rax, aTryparseFailed; "TryParse failed"
0x140013f98  lea     rdx, byte_140022BFF
0x140013f9f  jmp     short loc_14001400B
0x140013fa1  cmp     [rbp+57h+var_B8], r13b
0x140013fa5  jnz     loc_14001406D
0x140013fab  mov     ebx, 80004005h
0x140013fb0  mov     eax, cs:dword_140027000
0x140013fb6  cmp     eax, 2
0x140013fb9  jbe     loc_1400143B4
0x140013fbf  mov     rcx, cs:qword_140027018
0x140013fc6  mov     rax, cs:qword_140027010
0x140013fcd  mov     rdi, 400000000000h
0x140013fd7  test    rdi, rax
0x140013fda  jz      loc_1400143B4
0x140013fe0  mov     rax, rcx
0x140013fe3  and     rax, rdi
0x140013fe6  cmp     rax, rcx
0x140013fe9  jnz     loc_1400143B4
0x140013fef  mov     [rbp+57h+var_C0], 383h
0x140013ff6  mov     [rbp+57h+var_BC], 80004005h
0x140013ffd  lea     rax, aJsonNotParsed; "Json not parsed"
0x140014004  lea     rdx, byte_140022E3D
0x14001400b  mov     [rbp+57h+var_B0], rax
0x14001400f  lea     rax, [rbp+57h+var_98]
0x140014013  mov     [rsp+110h+var_C8], rax
0x140014018  lea     rax, [rbp+57h+var_C0]
0x14001401c  mov     [rsp+110h+var_D0], rax
0x140014021  lea     rax, [rbp+57h+var_A0]
0x140014025  mov     [rsp+110h+var_D8], rax
0x14001402a  lea     rax, [rbp+57h+var_A8]
0x14001402e  mov     [rsp+110h+var_E0], rax
0x140014033  lea     rax, [rbp+57h+var_BC]
0x140014037  mov     qword ptr [rsp+110h+cchWideChar], rax
0x14001403c  lea     rax, [rbp+57h+var_B0]
0x140014040  lea     r14, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140014047  lea     rsi, aGetringmapands; "GetRingMapAndSIUFConfigFromOneSettingsR"...
0x14001404e  mov     [rsp+110h+lpWideCharStr], rax
0x140014053  mov     [rbp+57h+var_A8], r14
0x140014057  mov     [rbp+57h+var_A0], rsi
0x14001405b  mov     [rbp+57h+var_98], 1000000h
0x140014063  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140014068  jmp     loc_1400143B4
0x14001406d  mov     rax, [rbp+57h+var_88]
0x140014071  mov     rbx, [rax]
0x140014074  mov     [rbp+57h+string], r13
0x140014078  lea     r9, [rbp+57h+string]; string
0x14001407c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x140014080  mov     edx, edi; length
0x140014082  lea     rcx, aSettings; "settings"
0x140014089  call    cs:__imp_WindowsCreateStringReference
0x14001408f  test    eax, eax
0x140014091  js      loc_140014477
0x140014097  lea     r8, [rbp+57h+var_80]
0x14001409b  mov     rdx, [rbp+57h+string]
0x14001409f  mov     rcx, [rbp+57h+var_88]
0x1400140a3  mov     rax, [rbx+40h]
0x1400140a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400140ac  mov     ebx, eax
0x1400140ae  test    eax, eax
0x1400140b0  jns     short loc_14001410E
0x1400140b2  mov     eax, cs:dword_140027000
0x1400140b8  cmp     eax, 2
  ... truncated ...
```
