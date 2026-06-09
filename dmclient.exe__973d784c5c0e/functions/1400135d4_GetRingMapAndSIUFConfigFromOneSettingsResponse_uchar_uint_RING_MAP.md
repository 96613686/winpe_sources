# GetRingMapAndSIUFConfigFromOneSettingsResponse(uchar *,uint,_RING_MAP * *)

- ea: `0x1400135d4`
- end: `0x140013eb6`
- name: `?GetRingMapAndSIUFConfigFromOneSettingsResponse@@YAJPEAEIPEAPEAU_RING_MAP@@@Z`
- size: `2274`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned int cbMultiByte, struct _RING_MAP **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400143cc`

## callees

- `0x140001418`
- `0x14000ac50`
- `0x14000d9b0`
- `0x1400135d4`
- `0x140019610`
- `0x14001a010`

## import_xrefs

- `msvcrt!_wtoi64` at `0x140013dab`
- `msvcrt!_wtoi64` at `0x140013dab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140013758`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140013895`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140013758`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140013895`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013741`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013879`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013deb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013e1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013741`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013879`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013deb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013e1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013dff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013e30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013dff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013e30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400137a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400137a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140013b97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140013dc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140013b97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140013dc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400138ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140013ad6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400138ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140013ad6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140013d9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140013d9c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400138ed`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400138ed`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14001365d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140013791`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14001365d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140013791`

## string_xrefs

- `0x1400138c3`: `Windows.Data.Json.JsonObject`
- `0x140013a47`: `Json not parsed`
- `0x1400136dd`: `GetRingMapAndSIUFConfigFromOneSettingsResponse`
- `0x14001380e`: `GetRingMapAndSIUFConfigFromOneSettingsResponse`
- `0x140013a91`: `GetRingMapAndSIUFConfigFromOneSettingsResponse`
- `0x140013b6e`: `GetRingMapAndSIUFConfigFromOneSettingsResponse`
- `0x140013d4e`: `StringCchCopy failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetRingMapAndSIUFConfigFromOneSettingsResponse(
        LPCCH lpMultiByteStr,
        int cbMultiByte,
        struct _RING_MAP **a3)
{
  WCHAR *v5; // r12
  signed int ActivationFactory; // ebx
  int v7; // eax
  int cchWideChar; // r14d
  signed int LastError; // eax
  int v10; // r8d
  int v11; // r9d
  unsigned int v12; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *lpWideCharStr; // rax
  signed int v15; // eax
  int v16; // r8d
  int v17; // r9d
  HANDLE v18; // rax
  unsigned int *v19; // rax
  unsigned int *v20; // r15
  HRESULT v21; // eax
  int v22; // edx
  unsigned int v23; // r8d
  int v24; // r8d
  int v25; // r9d
  int v26; // ecx
  char *v27; // rax
  char *v28; // rdx
  __int64 (__fastcall *v29)(__int64, _QWORD, __int64 **, char *); // rbx
  __int64 v30; // rax
  __int64 v31; // rbx
  HRESULT v32; // eax
  int v33; // edx
  unsigned int v34; // r8d
  __int64 i; // r13
  __int64 (__fastcall *v36)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v37; // rax
  unsigned int v38; // eax
  int v39; // r9d
  __int64 v40; // rbx
  __int64 v41; // rax
  unsigned __int16 * near *v42; // rcx
  __int64 v43; // rdx
  unsigned int *v44; // r8
  __int16 v45; // r9
  unsigned int *v46; // rcx
  const wchar_t *StringRawBuffer; // rax
  HANDLE v48; // rax
  HANDLE v49; // rax
  unsigned int v51; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v52; // [rsp+54h] [rbp-65h] BYREF
  char v53[8]; // [rsp+58h] [rbp-61h] BYREF
  HSTRING v54; // [rsp+60h] [rbp-59h] BYREF
  __int64 v55; // [rsp+68h] [rbp-51h] BYREF
  const char *v56; // [rsp+70h] [rbp-49h] BYREF
  const char *v57; // [rsp+78h] [rbp-41h] BYREF
  __int64 v58; // [rsp+80h] [rbp-39h] BYREF
  __int64 *v59; // [rsp+88h] [rbp-31h] BYREF
  __int64 v60; // [rsp+90h] [rbp-29h] BYREF
  __int64 v61; // [rsp+98h] [rbp-21h] BYREF
  struct _RING_MAP **v62; // [rsp+A0h] [rbp-19h]
  __int64 v63; // [rsp+A8h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-9h] BYREF
  HSTRING string; // [rsp+C8h] [rbp+Fh] BYREF

  v62 = a3;
  v5 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v53[0] = 0;
  v63 = 0;
  if ( !lpMultiByteStr || !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  if ( !cbMultiByte )
    return (unsigned int)-2147024809;
  v7 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, cbMultiByte, 0, 0);
  cchWideChar = v7;
  if ( !v7 )
  {
    LastError = GetLastError();
    ActivationFactory = LastError;
    if ( LastError > 0 )
      ActivationFactory = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_140028000 > 2
      && (qword_140028010 & 0x400000000000LL) != 0
      && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
    {
      v54 = (HSTRING)0x1000000;
      v52 = 837;
      v56 = "GetRingMapAndSIUFConfigFromOneSettingsResponse";
      v57 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
      v51 = ActivationFactory;
      v55 = (__int64)"MultiByteToWideChar failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_140028018,
        (unsigned int)byte_140023BA9,
        v10,
        v11,
        (__int64)&v55,
        (__int64)&v51,
        (__int64)&v57,
        (__int64)&v56,
        (__int64)&v52,
        (__int64)&v54);
    }
    goto LABEL_72;
  }
  v12 = 2 * v7;
  ProcessHeap = GetProcessHeap();
  lpWideCharStr = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v12);
  v5 = lpWideCharStr;
  v55 = (__int64)lpWideCharStr;
  if ( lpWideCharStr )
  {
    if ( !MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, cbMultiByte, lpWideCharStr, cchWideChar) )
    {
      v15 = GetLastError();
      ActivationFactory = v15;
      if ( v15 > 0 )
        ActivationFactory = (unsigned __int16)v15 | 0x80070000;
      if ( (unsigned int)dword_140028000 > 2
        && (qword_140028010 & 0x400000000000LL) != 0
        && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v55 = 0x1000000;
        v51 = 859;
        v57 = "GetRingMapAndSIUFConfigFromOneSettingsResponse";
        v56 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
        v52 = ActivationFactory;
        v54 = (HSTRING)"MultiByteToWideChar failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028018,
          (unsigned int)&byte_14002379F,
          v16,
          v17,
          (__int64)&v54,
          (__int64)&v52,
          (__int64)&v56,
          (__int64)&v57,
          (__int64)&v51,
          (__int64)&v55);
      }
      goto LABEL_72;
    }
    v18 = GetProcessHeap();
    v19 = (unsigned int *)HeapAlloc(v18, 8u, 0x388u);
    v20 = v19;
    if ( v19 )
    {
      v19[1] = 904;
      *v19 = 0;
      string = 0;
      v21 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
      if ( v21 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v21, v22, v23);
        JUMPOUT(0x140013EB5LL);
      }
      ActivationFactory = RoGetActivationFactory(string, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v58);
      if ( ActivationFactory >= 0 )
      {
        v29 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 **, char *))(*(_QWORD *)v58 + 56LL);
        v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v55);
        ActivationFactory = v29(v58, *(_QWORD *)(v30 + 24), &v59, v53);
        if ( ActivationFactory >= 0 )
        {
          if ( v53[0] )
          {
            v31 = *v59;
            string = 0;
            v32 = WindowsCreateStringReference(L"settings", 8u, &hstringHeader, &string);
            if ( v32 < 0 )
            {
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v32, v33, v34);
              __debugbreak();
            }
            ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v31 + 64))(v59, string, &v60);
            if ( ActivationFactory >= 0 )
            {
              for ( i = 0; i != 8; ++i )
              {
                v54 = 0;
                v51 = *v20;
                v36 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v60 + 80LL);
                WindowsDeleteString(0);
                v54 = 0;
                v37 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                        &hstringHeader,
                        &(&DefaultRingNames)[i]);
                v38 = v36(v60, *(_QWORD *)(v37 + 24), &v54);
                if ( v38 )
                {
                  if ( v38 != -2089484279
                    && (unsigned int)dword_140028000 > 2
                    && (qword_140028010 & 0x400000000000LL) != 0
                    && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
                  {
                    v55 = 0x1000000;
                    v51 = 926;
                    v57 = "GetRingMapAndSIUFConfigFromOneSettingsResponse";
                    v56 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
                    v52 = v38;
                    v61 = (__int64)"GetNamedString failed";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                      qword_140028010,
                      (unsigned int)byte_1400239D3,
                      v38,
                      v39,
                      (__int64)&v61,
                      (__int64)&v52,
                      (__int64)&v56,
                      (__int64)&v57,
                      (__int64)&v51,
                      (__int64)&v55);
                  }
                }
                else
                {
                  v40 = 28LL * v51;
                  v41 = 2147483646;
                  v42 = (&DefaultRingNames)[i];
                  v43 = 51;
                  v44 = &v20[v40 + 2];
                  do
                  {
                    if ( !v41 )
                      break;
                    v45 = *(_WORD *)v42;
                    if ( !*(_WORD *)v42 )
                      break;
                    v42 = (unsigned __int16 * near *)((char *)v42 + 2);
                    *(_WORD *)v44 = v45;
                    v44 = (unsigned int *)((char *)v44 + 2);
                    --v41;
                    --v43;
                  }
                  while ( v43 );
                  v46 = (unsigned int *)((char *)v44 - 2);
                  if ( v43 )
                    v46 = v44;
                  *(_WORD *)v46 = 0;
                  if ( v43 )
                  {
                    StringRawBuffer = WindowsGetStringRawBuffer(v54, 0);
                    *(_QWORD *)&v20[v40 + 28] = _wtoi64(StringRawBuffer);
                    ++*v20;
                  }
                  else if ( (unsigned int)dword_140028000 > 2
                         && (qword_140028010 & 0x400000000000LL) != 0
                         && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
                  {
                    v61 = 0x1000000;
                    v51 = 941;
                    v55 = (__int64)"GetRingMapAndSIUFConfigFromOneSettingsResponse";
                    v57 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
                    v52 = v43 == 0 ? 0x8007007A : 0;
                    v56 = "StringCchCopy failed";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                      qword_140028018,
                      (unsigned int)&byte_140023A8F,
                      (_DWORD)v44,
                      v52,
                      (__int64)&v56,
                      (__int64)&v52,
                      (__int64)&v57,
                      (__int64)&v55,
                      (__int64)&v51,
                      (__int64)&v61);
                  }
                }
                WindowsDeleteString(v54);
              }
              if ( *v20 )
              {
                *v62 = (struct _RING_MAP *)v20;
                ActivationFactory = 0;
                goto LABEL_72;
              }
              ActivationFactory = 6148405;
              goto LABEL_70;
            }
            if ( (unsigned int)dword_140028000 <= 2
              || (v26 = qword_140028018, (qword_140028010 & 0x400000000000LL) == 0)
              || (qword_140028018 & 0x400000000000LL) != qword_140028018 )
            {
LABEL_70:
              v48 = GetProcessHeap();
              HeapFree(v48, 0, v20);
              goto LABEL_72;
            }
            v51 = 908;
            v52 = ActivationFactory;
            v27 = "GetNamedObject failed";
            v28 = byte_140023D21;
          }
          else
          {
            ActivationFactory = -2147467259;
            if ( (unsigned int)dword_140028000 <= 2 )
              goto LABEL_70;
            v26 = qword_140028018;
            if ( (qword_140028010 & 0x400000000000LL) == 0 || (qword_140028018 & 0x400000000000LL) != qword_140028018 )
              goto LABEL_70;
            v51 = 899;
            v52 = -2147467259;
            v27 = "Json not parsed";
            v28 = byte_140023E45;
          }
        }
        else
        {
          if ( (unsigned int)dword_140028000 <= 2 )
            goto LABEL_70;
          v26 = qword_140028018;
          if ( (qword_140028010 & 0x400000000000LL) == 0 || (qword_140028018 & 0x400000000000LL) != qword_140028018 )
            goto LABEL_70;
          v51 = 892;
          v52 = ActivationFactory;
          v27 = "TryParse failed";
          v28 = &byte_140023C07;
        }
      }
      else
      {
        if ( (unsigned int)dword_140028000 <= 2 )
          goto LABEL_70;
        v26 = qword_140028010;
        if ( (qword_140028010 & 0x400000000000LL) == 0 || (qword_140028018 & 0x400000000000LL) != qword_140028018 )
          goto LABEL_70;
        v51 = 882;
        v52 = ActivationFactory;
        v27 = "GetActivationFactory failed";
        v28 = byte_14002385B;
      }
      v54 = (HSTRING)v27;
      v56 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
      v57 = "GetRingMapAndSIUFConfigFromOneSettingsResponse";
      v55 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v26,
        (_DWORD)v28,
        v24,
        v25,
        (__int64)&v54,
        (__int64)&v52,
        (__int64)&v56,
        (__int64)&v57,
        (__int64)&v51,
        (__int64)&v55);
      goto LABEL_70;
    }
  }
  ActivationFactory = -2147024882;
LABEL_72:
  if ( v5 )
  {
    v49 = GetProcessHeap();
    HeapFree(v49, 0, v5);
  }
  if ( v58 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
  if ( v59 )
    (*(void (__fastcall **)(__int64 *))(*v59 + 16))(v59);
  if ( v60 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1400135d4  mov     [rsp-8+arg_18], rbx
0x1400135d9  push    rbp
0x1400135da  push    rsi
0x1400135db  push    rdi
0x1400135dc  push    r12
0x1400135de  push    r13
0x1400135e0  push    r14
0x1400135e2  push    r15
0x1400135e4  lea     rbp, [rsp-27h]
0x1400135e9  sub     rsp, 0E0h
0x1400135f0  mov     rax, cs:__security_cookie
0x1400135f7  xor     rax, rsp
0x1400135fa  mov     [rbp+57h+var_40], rax
0x1400135fe  mov     [rbp+57h+var_70], r8
0x140013602  mov     edi, edx
0x140013604  mov     rsi, rcx
0x140013607  xor     r15d, r15d
0x14001360a  mov     r12d, r15d
0x14001360d  mov     [rbp+57h+var_90], r15
0x140013611  mov     [rbp+57h+var_88], r15
0x140013615  mov     [rbp+57h+var_80], r15
0x140013619  mov     [rbp+57h+var_B8], r15b
0x14001361d  mov     [rbp+57h+var_68], r15
0x140013621  test    rcx, rcx
0x140013624  jnz     short loc_140013630
0x140013626  mov     ebx, 80004003h
0x14001362b  jmp     loc_140013E7C
0x140013630  test    r8, r8
0x140013633  jz      short loc_140013626
0x140013635  mov     [r8], r15
0x140013638  test    edi, edi
0x14001363a  jnz     short loc_140013646
0x14001363c  mov     ebx, 80070057h
0x140013641  jmp     loc_140013E7C
0x140013646  mov     [rsp+110h+cchWideChar], r15d; cchWideChar
0x14001364b  mov     [rsp+110h+lpWideCharStr], r15; lpWideCharStr
0x140013650  mov     r9d, edi; cbMultiByte
0x140013653  mov     r8, rsi; lpMultiByteStr
0x140013656  xor     edx, edx; dwFlags
0x140013658  mov     ecx, 0FDE9h; CodePage
0x14001365d  call    cs:__imp_MultiByteToWideChar
0x140013664  nop     dword ptr [rax+rax+00h]
0x140013669  mov     r14d, eax
0x14001366c  test    eax, eax
0x14001366e  jnz     loc_14001373E
0x140013674  call    cs:__imp_GetLastError
0x14001367b  nop     dword ptr [rax+rax+00h]
0x140013680  mov     ebx, eax
0x140013682  test    eax, eax
0x140013684  jle     short loc_14001368F
0x140013686  movzx   ebx, ax
0x140013689  or      ebx, 80070000h
0x14001368f  mov     eax, cs:dword_140028000
0x140013695  cmp     eax, 2
0x140013698  jbe     loc_140013E17
0x14001369e  mov     rcx, cs:qword_140028018
0x1400136a5  mov     rax, cs:qword_140028010
0x1400136ac  mov     rdi, 400000000000h
0x1400136b6  test    rdi, rax
0x1400136b9  jz      loc_140013E17
0x1400136bf  mov     rax, rcx
0x1400136c2  and     rax, rdi
0x1400136c5  cmp     rax, rcx
0x1400136c8  jnz     loc_140013E17
0x1400136ce  mov     [rbp+57h+var_B0], 1000000h
0x1400136d6  mov     [rbp+57h+var_BC], 345h
0x1400136dd  lea     rsi, aGetringmapands; "GetRingMapAndSIUFConfigFromOneSettingsR"...
0x1400136e4  mov     [rbp+57h+var_A0], rsi
0x1400136e8  lea     r14, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x1400136ef  mov     [rbp+57h+var_98], r14
0x1400136f3  mov     [rbp+57h+var_C0], ebx
0x1400136f6  lea     rax, aMultibytetowid; "MultiByteToWideChar failed"
0x1400136fd  mov     [rbp+57h+var_A8], rax
0x140013701  lea     rax, [rbp+57h+var_B0]
0x140013705  mov     [rsp+110h+var_C8], rax
0x14001370a  lea     rax, [rbp+57h+var_BC]
0x14001370e  mov     [rsp+110h+var_D0], rax
0x140013713  lea     rax, [rbp+57h+var_A0]
0x140013717  mov     [rsp+110h+var_D8], rax
0x14001371c  lea     rax, [rbp+57h+var_98]
0x140013720  mov     [rsp+110h+var_E0], rax
0x140013725  lea     rax, [rbp+57h+var_C0]
0x140013729  mov     qword ptr [rsp+110h+cchWideChar], rax
0x14001372e  lea     rax, [rbp+57h+var_A8]
0x140013732  lea     rdx, byte_140023BA9
0x140013739  jmp     loc_14001386A
0x14001373e  lea     ebx, [rax+rax]
0x140013741  call    cs:__imp_GetProcessHeap
0x140013748  nop     dword ptr [rax+rax+00h]
0x14001374d  mov     rcx, rax; hHeap
0x140013750  mov     r8d, ebx; dwBytes
0x140013753  mov     edx, 8; dwFlags
0x140013758  call    cs:__imp_HeapAlloc
0x14001375f  nop     dword ptr [rax+rax+00h]
0x140013764  mov     r12, rax
0x140013767  mov     [rbp+57h+var_A8], rax
0x14001376b  test    rax, rax
0x14001376e  jnz     short loc_14001377A
0x140013770  mov     ebx, 8007000Eh
0x140013775  jmp     loc_140013E17
0x14001377a  mov     [rsp+110h+cchWideChar], r14d; cchWideChar
0x14001377f  mov     [rsp+110h+lpWideCharStr], rax; lpWideCharStr
0x140013784  mov     r9d, edi; cbMultiByte
0x140013787  mov     r8, rsi; lpMultiByteStr
0x14001378a  xor     edx, edx; dwFlags
0x14001378c  mov     ecx, 0FDE9h; CodePage
0x140013791  call    cs:__imp_MultiByteToWideChar
0x140013798  nop     dword ptr [rax+rax+00h]
0x14001379d  test    eax, eax
0x14001379f  jnz     loc_140013879
0x1400137a5  call    cs:__imp_GetLastError
0x1400137ac  nop     dword ptr [rax+rax+00h]
0x1400137b1  mov     ebx, eax
0x1400137b3  test    eax, eax
0x1400137b5  jle     short loc_1400137C0
0x1400137b7  movzx   ebx, ax
0x1400137ba  or      ebx, 80070000h
0x1400137c0  mov     eax, cs:dword_140028000
0x1400137c6  cmp     eax, 2
0x1400137c9  jbe     loc_140013E17
0x1400137cf  mov     rcx, cs:qword_140028018
0x1400137d6  mov     rax, cs:qword_140028010
0x1400137dd  mov     rdi, 400000000000h
0x1400137e7  test    rdi, rax
0x1400137ea  jz      loc_140013E17
0x1400137f0  mov     rax, rcx
0x1400137f3  and     rax, rdi
0x1400137f6  cmp     rax, rcx
0x1400137f9  jnz     loc_140013E17
0x1400137ff  mov     [rbp+57h+var_A8], 1000000h
0x140013807  mov     [rbp+57h+var_C0], 35Bh
0x14001380e  lea     rsi, aGetringmapands; "GetRingMapAndSIUFConfigFromOneSettingsR"...
0x140013815  mov     [rbp+57h+var_98], rsi
0x140013819  lea     r14, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140013820  mov     [rbp+57h+var_A0], r14
0x140013824  mov     [rbp+57h+var_BC], ebx
0x140013827  lea     rax, aMultibytetowid; "MultiByteToWideChar failed"
0x14001382e  mov     [rbp+57h+var_B0], rax
0x140013832  lea     rax, [rbp+57h+var_A8]
0x140013836  mov     [rsp+110h+var_C8], rax
0x14001383b  lea     rax, [rbp+57h+var_C0]
0x14001383f  mov     [rsp+110h+var_D0], rax
0x140013844  lea     rax, [rbp+57h+var_98]
0x140013848  mov     [rsp+110h+var_D8], rax
0x14001384d  lea     rax, [rbp+57h+var_A0]
0x140013851  mov     [rsp+110h+var_E0], rax
0x140013856  lea     rax, [rbp+57h+var_BC]
0x14001385a  mov     qword ptr [rsp+110h+cchWideChar], rax
0x14001385f  lea     rax, [rbp+57h+var_B0]
0x140013863  lea     rdx, byte_14002379F
0x14001386a  mov     [rsp+110h+lpWideCharStr], rax
0x14001386f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140013874  jmp     loc_140013E17
0x140013879  call    cs:__imp_GetProcessHeap
0x140013880  nop     dword ptr [rax+rax+00h]
0x140013885  mov     rcx, rax; hHeap
0x140013888  mov     ebx, 388h
0x14001388d  mov     r8d, ebx; dwBytes
0x140013890  mov     edx, 8; dwFlags
0x140013895  call    cs:__imp_HeapAlloc
0x14001389c  nop     dword ptr [rax+rax+00h]
0x1400138a1  mov     r15, rax
0x1400138a4  xor     edi, edi
0x1400138a6  test    rax, rax
0x1400138a9  jz      loc_140013770
0x1400138af  mov     [rax+4], ebx
0x1400138b2  mov     [rax], edi
0x1400138b4  mov     [rbp+57h+string], rdi
0x1400138b8  lea     r9, [rbp+57h+string]; string
0x1400138bc  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1400138c0  lea     edx, [rdi+1Ch]; length
0x1400138c3  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1400138ca  call    cs:__imp_WindowsCreateStringReference
0x1400138d1  nop     dword ptr [rax+rax+00h]
0x1400138d6  test    eax, eax
0x1400138d8  js      loc_140013EAE
0x1400138de  lea     r8, [rbp+57h+var_90]
0x1400138e2  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x1400138e9  mov     rcx, [rbp+57h+string]
0x1400138ed  call    cs:__imp_RoGetActivationFactory
0x1400138f4  nop     dword ptr [rax+rax+00h]
0x1400138f9  mov     ebx, eax
0x1400138fb  test    eax, eax
0x1400138fd  jns     short loc_14001395B
0x1400138ff  mov     ecx, cs:dword_140028000
0x140013905  cmp     ecx, 2
0x140013908  jbe     loc_140013DEB
0x14001390e  mov     rdx, cs:qword_140028018
0x140013915  mov     rcx, cs:qword_140028010
0x14001391c  mov     rdi, 400000000000h
0x140013926  test    rdi, rcx
0x140013929  jz      loc_140013DEB
0x14001392f  mov     rax, rdx
0x140013932  and     rax, rdi
0x140013935  cmp     rax, rdx
0x140013938  jnz     loc_140013DEB
0x14001393e  mov     [rbp+57h+var_C0], 372h
0x140013945  mov     [rbp+57h+var_BC], ebx
0x140013948  lea     rax, aGetactivationf; "GetActivationFactory failed"
0x14001394f  lea     rdx, byte_14002385B
0x140013956  jmp     loc_140013A55
0x14001395b  mov     rax, [rbp+57h+var_90]
0x14001395f  mov     rcx, [rax]
0x140013962  mov     rbx, [rcx+38h]
0x140013966  lea     rdx, [rbp+57h+var_A8]
0x14001396a  lea     rcx, [rbp+57h+hstringHeader]
0x14001396e  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x140013973  nop
0x140013974  lea     r9, [rbp+57h+var_B8]
0x140013978  lea     r8, [rbp+57h+var_88]
0x14001397c  mov     rdx, [rax+18h]
0x140013980  mov     rcx, [rbp+57h+var_90]
0x140013984  mov     rax, rbx
0x140013987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001398c  mov     ebx, eax
0x14001398e  test    eax, eax
0x140013990  jns     short loc_1400139EB
0x140013992  mov     eax, cs:dword_140028000
0x140013998  cmp     eax, 2
0x14001399b  jbe     loc_140013DEB
0x1400139a1  mov     rcx, cs:qword_140028018
0x1400139a8  mov     rax, cs:qword_140028010
0x1400139af  mov     rdi, 400000000000h
0x1400139b9  test    rdi, rax
0x1400139bc  jz      loc_140013DEB
0x1400139c2  mov     rax, rcx
0x1400139c5  and     rax, rdi
0x1400139c8  cmp     rax, rcx
0x1400139cb  jnz     loc_140013DEB
0x1400139d1  mov     [rbp+57h+var_C0], 37Ch
0x1400139d8  mov     [rbp+57h+var_BC], ebx
0x1400139db  lea     rax, aTryparseFailed; "TryParse failed"
0x1400139e2  lea     rdx, byte_140023C07
0x1400139e9  jmp     short loc_140013A55
0x1400139eb  cmp     [rbp+57h+var_B8], dil
0x1400139ef  jnz     loc_140013AB7
0x1400139f5  mov     ebx, 80004005h
0x1400139fa  mov     eax, cs:dword_140028000
0x140013a00  cmp     eax, 2
0x140013a03  jbe     loc_140013DEB
0x140013a09  mov     rcx, cs:qword_140028018
0x140013a10  mov     rax, cs:qword_140028010
0x140013a17  mov     rdi, 400000000000h
0x140013a21  test    rdi, rax
0x140013a24  jz      loc_140013DEB
0x140013a2a  mov     rax, rcx
0x140013a2d  and     rax, rdi
0x140013a30  cmp     rax, rcx
0x140013a33  jnz     loc_140013DEB
0x140013a39  mov     [rbp+57h+var_C0], 383h
0x140013a40  mov     [rbp+57h+var_BC], 80004005h
0x140013a47  lea     rax, aJsonNotParsed; "Json not parsed"
0x140013a4e  lea     rdx, byte_140023E45
0x140013a55  mov     [rbp+57h+var_B0], rax
0x140013a59  lea     rax, [rbp+57h+var_A8]
0x140013a5d  mov     [rsp+110h+var_C8], rax
0x140013a62  lea     rax, [rbp+57h+var_C0]
0x140013a66  mov     [rsp+110h+var_D0], rax
0x140013a6b  lea     rax, [rbp+57h+var_98]
0x140013a6f  mov     [rsp+110h+var_D8], rax
0x140013a74  lea     rax, [rbp+57h+var_A0]
0x140013a78  mov     [rsp+110h+var_E0], rax
0x140013a7d  lea     rax, [rbp+57h+var_BC]
0x140013a81  mov     qword ptr [rsp+110h+cchWideChar], rax
0x140013a86  lea     rax, [rbp+57h+var_B0]
0x140013a8a  lea     r14, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140013a91  lea     rsi, aGetringmapands; "GetRingMapAndSIUFConfigFromOneSettingsR"...
0x140013a98  mov     [rsp+110h+lpWideCharStr], rax
0x140013a9d  mov     [rbp+57h+var_A0], r14
0x140013aa1  mov     [rbp+57h+var_98], rsi
0x140013aa5  mov     [rbp+57h+var_A8], 1000000h
0x140013aad  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140013ab2  jmp     loc_140013DEB
0x140013ab7  mov     rax, [rbp+57h+var_88]
0x140013abb  mov     rbx, [rax]
0x140013abe  mov     [rbp+57h+string], rdi
0x140013ac2  lea     r9, [rbp+57h+string]; string
0x140013ac6  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x140013aca  mov     edx, 8; length
0x140013acf  lea     rcx, aSettings; "settings"
0x140013ad6  call    cs:__imp_WindowsCreateStringReference
0x140013add  nop     dword ptr [rax+rax+00h]
0x140013ae2  test    eax, eax
0x140013ae4  js      loc_140013EA6
0x140013aea  lea     r8, [rbp+57h+var_80]
0x140013aee  mov     rdx, [rbp+57h+string]
0x140013af2  mov     rcx, [rbp+57h+var_88]
0x140013af6  mov     rax, [rbx+40h]
0x140013afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013aff  mov     ebx, eax
0x140013b01  test    eax, eax
0x140013b03  jns     short loc_140013B61
0x140013b05  mov     eax, cs:dword_140028000
0x140013b0b  cmp     eax, 2
0x140013b0e  jbe     loc_140013DEB
0x140013b14  mov     rcx, cs:qword_140028018
0x140013b1b  mov     rax, cs:qword_140028010
0x140013b22  mov     rdi, 400000000000h
0x140013b2c  test    rdi, rax
0x140013b2f  jz      loc_140013DEB
  ... truncated ...
```
