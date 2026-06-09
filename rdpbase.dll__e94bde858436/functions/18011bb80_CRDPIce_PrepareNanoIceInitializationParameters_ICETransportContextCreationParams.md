# CRDPIce::PrepareNanoIceInitializationParameters(ICETransportContextCreationParams *)

- ea: `0x18011bb80`
- end: `0x18011c719`
- name: `?PrepareNanoIceInitializationParameters@CRDPIce@@AEAAJPEAUICETransportContextCreationParams@@@Z`
- size: `2969`
- prototype: `__int64 __fastcall(CRDPIce *__hidden this, struct ICETransportContextCreationParams *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18011a2f0`

## callees

- `0x180001aa0`
- `0x180004e6c`
- `0x1800787d4`
- `0x180078820`
- `0x180078c20`
- `0x18007969c`
- `0x180117040`
- `0x18011a3b8`
- `0x18011bb80`
- `0x1801614c4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18011befd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18011befd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18011bbfb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18011bbfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c0b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c187`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c305`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c3d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c54b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c62a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c0b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c187`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c305`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c3d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c54b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c62a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18011c099`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18011c16e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18011c2e8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18011c3c3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18011c52e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18011c60d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18011c099`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18011c16e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18011c2e8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18011c3c3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18011c52e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18011c60d`

## string_xrefs

- `0x18011bfea`: `iceServerConfigJson memory allocation failed`
- `0x18011c27d`: `aadIdAuthToken length`
- `0x18011c3f5`: `aadIdAuthTokenUTF8 utf8 conversion`
- `0x18011c322`: `aadIdAuthToken utf8 length`

## pseudocode

```c
__int64 __fastcall CRDPIce::PrepareNanoIceInitializationParameters(
        CRDPIce *this,
        struct ICETransportContextCreationParams *a2)
{
  int v2; // eax
  int v4; // r15d
  int v6; // r12d
  int v7; // r13d
  const WCHAR *v8; // r8
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rdx
  FeatureFlag *v11; // rcx
  int v12; // r9d
  _DWORD *v13; // r14
  __int64 *v14; // rdi
  int v15; // ecx
  int v16; // eax
  __int64 *v17; // rax
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // rdx
  void *v21; // rcx
  void *v22; // rcx
  int v23; // edx
  void *v24; // r13
  void *v25; // r15
  void *v26; // r12
  unsigned int v27; // edi
  GUID v28; // xmm6
  __int64 v29; // rcx
  LPCWCH v30; // rax
  int v31; // r15d
  int v32; // eax
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  size_t v36; // rcx
  void *v37; // rax
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  __int64 v41; // rcx
  LPCWCH v42; // rax
  int v43; // r15d
  int v44; // eax
  int v45; // ecx
  int v46; // r8d
  int v47; // r9d
  size_t v48; // rcx
  void *v49; // rax
  int v50; // ecx
  int v51; // r8d
  int v52; // r9d
  __int64 v53; // rcx
  LPCWCH v54; // rax
  int v55; // r14d
  int v56; // eax
  int v57; // ecx
  int v58; // r8d
  int v59; // r9d
  size_t v60; // rcx
  void *v61; // rax
  int v62; // ecx
  int v63; // r8d
  int v64; // r9d
  int v65; // ecx
  int cbMultiByte; // [rsp+50h] [rbp-B0h] BYREF
  LPCWCH lpWideCharStr; // [rsp+58h] [rbp-A8h] BYREF
  LPCWCH v69; // [rsp+60h] [rbp-A0h] BYREF
  LPCWCH v70; // [rsp+68h] [rbp-98h] BYREF
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  int v72; // [rsp+78h] [rbp-88h] BYREF
  int v73; // [rsp+7Ch] [rbp-84h] BYREF
  GUID ActivityId; // [rsp+80h] [rbp-80h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+90h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-60h] BYREF
  char *v77; // [rsp+B0h] [rbp-50h]
  int v78; // [rsp+B8h] [rbp-48h]
  int v79; // [rsp+BCh] [rbp-44h]
  const char *v80; // [rsp+C0h] [rbp-40h]
  __int64 v81; // [rsp+C8h] [rbp-38h]
  GUID *p_ActivityId; // [rsp+D0h] [rbp-30h]
  __int64 v83; // [rsp+D8h] [rbp-28h]
  int *v84; // [rsp+E0h] [rbp-20h]
  __int64 v85; // [rsp+E8h] [rbp-18h]
  int *v86; // [rsp+F0h] [rbp-10h]
  __int64 v87; // [rsp+F8h] [rbp-8h]

  v2 = *((_DWORD *)a2 + 6);
  v4 = *((_DWORD *)a2 + 21);
  v6 = *((_DWORD *)a2 + 22);
  v7 = *((_DWORD *)a2 + 23);
  lpWideCharStr = (LPCWCH)*((_QWORD *)a2 + 5);
  v69 = (LPCWCH)*((_QWORD *)a2 + 8);
  v8 = (const WCHAR *)*((_QWORD *)a2 + 9);
  *((_DWORD *)this + 52) = v2;
  ActivityId = 0;
  v73 = v2;
  v70 = v8;
  ActivityId.Data1 = -186646528;
  EventActivityIdControl(1u, &ActivityId);
  v9 = operator new(0xCu);
  v13 = v9;
  if ( v9 )
    *v9 = 50;
  else
    v13 = 0;
  v13[2] = 3;
  v14 = (__int64 *)((char *)this + 280);
  v13[1] = 100;
  if ( (*((_BYTE *)a2 + 32) & 2) != 0 )
    *v14 |= 2uLL;
  if ( v73 && FeatureFlag::IsEnabled(v11, v10) )
  {
    v15 = 1;
    v14 = (__int64 *)((char *)this + 280);
  }
  else
  {
    v15 = 0;
  }
  v72 = v15;
  if ( v4 )
  {
    v14 = (__int64 *)((char *)this + 280);
    *((_QWORD *)this + 35) = *((unsigned int *)this + 70) | 0x2000LL;
  }
  if ( v6 )
    *v14 = *(unsigned int *)v14 | 0x20000LL;
  if ( v7 )
    *v14 = *(unsigned int *)v14 | 0x40000LL;
  if ( v15 )
    *v14 = *(unsigned int *)v14 | 2LL;
  if ( (*((_BYTE *)a2 + 32) & 1) != 0 )
    *v14 = *(unsigned int *)v14 | 1LL;
  if ( (*((_BYTE *)a2 + 32) & 0x10) != 0 )
    *((_QWORD *)this + 35) = *(unsigned int *)v14 | 0x10LL;
  if ( (*((_BYTE *)a2 + 32) & 0x20) != 0 )
    *((_QWORD *)this + 35) = *((unsigned int *)this + 70) | 0x20LL;
  if ( (*((_BYTE *)a2 + 32) & 0x40) != 0 )
    *((_QWORD *)this + 35) = *((unsigned int *)this + 70) | 0x40LL;
  if ( (*((_DWORD *)a2 + 8) & 0x100) != 0 )
    *((_QWORD *)this + 35) = *((unsigned int *)this + 70) | 0x100LL;
  if ( *((_DWORD *)a2 + 25) > 1u )
    *((_QWORD *)this + 35) = *((unsigned int *)this + 70) | 0x8000LL;
  v16 = *((_DWORD *)a2 + 2);
  if ( v16 && *(_QWORD *)a2 )
  {
    v17 = (__int64 *)utl::make_unique<char [0],0>(&Block, (unsigned int)(v16 + 1));
    v20 = *v17;
    *v17 = 0;
    v21 = (void *)*((_QWORD *)this + 20);
    *((_QWORD *)this + 20) = v20;
    if ( v21 )
      operator delete(v21);
    if ( Block )
      operator delete(Block);
    v22 = (void *)*((_QWORD *)this + 20);
    if ( !v22 )
    {
      v27 = -2147024882;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v73 = 1523;
        v70 = (LPCWCH)"iceServerConfigJson memory allocation failed";
        v72 = -2147024882;
        v69 = (LPCWCH)"PrepareNanoIceInitializationParameters";
        lpWideCharStr = (LPCWCH)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\ice.cpp";
        Block = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          0,
          (unsigned int)&word_1801CC8D6,
          v18,
          v19,
          (__int64)&Block,
          (__int64)&v72,
          (__int64)&lpWideCharStr,
          (__int64)&v73,
          (__int64)&v69,
          (__int64)&v70);
      }
      return v27;
    }
    memcpy_0(v22, *(const void **)a2, (unsigned int)(*((_DWORD *)a2 + 2) + 1));
    v15 = v72;
    *((_QWORD *)this + 46) = *((_QWORD *)this + 20);
  }
  v23 = v73;
  *((_DWORD *)this + 84) = *((_DWORD *)a2 + 3);
  v24 = 0;
  *((_QWORD *)this + 27) = *((_QWORD *)this + 11);
  v25 = 0;
  v26 = 0;
  *((_QWORD *)this + 28) = *((_QWORD *)this + 12);
  v27 = 0;
  *((_QWORD *)this + 29) = *((_QWORD *)this + 13);
  *((_QWORD *)this + 40) = v13;
  *((_DWORD *)this + 62) = v23 == 0;
  *((_DWORD *)this + 63) = 0;
  *((_DWORD *)this + 94) = *((_DWORD *)a2 + 24);
  *((_OWORD *)this + 16) = 0;
  v28 = ActivityId;
  if ( (unsigned int)CallbackContext > 4 )
  {
    ActivityId.Data1 = *((_DWORD *)this + 62);
    v86 = &v73;
    v84 = &v72;
    p_ActivityId = &ActivityId;
    v80 = "ICE: Init params: fIsClient=%d, controlling=%d";
    *(_DWORD *)&EventDescriptor.Level = 4;
    UserData.Ptr = (ULONGLONG)off_1801E7010;
    v72 = v15;
    v73 = v23;
    v87 = 4;
    v85 = 4;
    v83 = 4;
    v81 = 47;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_1801E7010;
    v77 = byte_1801CD54D;
    UserData.Reserved = 2;
    v78 = 70;
    v79 = 1;
    cbMultiByte = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
  }
  *((GUID *)this + 16) = v28;
  if ( *((_DWORD *)a2 + 12) && lpWideCharStr )
  {
    v29 = 0x7FFFFFFF;
    v30 = lpWideCharStr;
    do
    {
      if ( !*v30 )
        break;
      ++v30;
      --v29;
    }
    while ( v29 );
    v27 = -2147024809;
    if ( v29 )
      v27 = 0;
    v31 = 0x7FFFFFFF - v29;
    if ( !v29 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        cbMultiByte = v27;
        v70 = (LPCWCH)"PrepareNanoIceInitializationParameters";
        v69 = (LPCWCH)"rendezvousURL length";
        lpWideCharStr = (LPCWCH)"Condition failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          0,
          (unsigned int)&byte_1801CCF8F,
          0,
          v12,
          (__int64)&lpWideCharStr,
          (__int64)&v69,
          (__int64)&v70,
          (__int64)&cbMultiByte);
      }
      return v27;
    }
    v27 = -2147024809;
    v32 = WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, v31, 0, 0, 0, 0);
    cbMultiByte = v32;
    if ( v32 <= 0 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        cbMultiByte = GetLastError();
        v70 = (LPCWCH)"PrepareNanoIceInitializationParameters";
        v69 = (LPCWCH)"rendezvousURL utf8 length";
        lpWideCharStr = (LPCWCH)"Condition failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v33,
          (unsigned int)word_1801CD472,
          v34,
          v35,
          (__int64)&lpWideCharStr,
          (__int64)&v69,
          (__int64)&v70,
          (__int64)&cbMultiByte);
      }
      return v27;
    }
    v36 = v32 + 1;
    *(_QWORD *)&ActivityId.Data1 = (int)v36;
    v37 = operator new(v36);
    v24 = v37;
    if ( v37 )
      memset_0(v37, 0, *(size_t *)&ActivityId.Data1);
    else
      v24 = 0;
    if ( WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, v31, (LPSTR)v24, cbMultiByte, 0, 0) <= 0 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        cbMultiByte = GetLastError();
        v70 = (LPCWCH)"PrepareNanoIceInitializationParameters";
        v69 = (LPCWCH)"rendezvousURL utf8 conversion";
        lpWideCharStr = (LPCWCH)"Condition failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v38,
          (unsigned int)byte_1801CCA81,
          v39,
          v40,
          (__int64)&lpWideCharStr,
          (__int64)&v69,
          (__int64)&v70,
          (__int64)&cbMultiByte);
      }
LABEL_61:
      v25 = 0;
LABEL_62:
      if ( v24 )
      {
        operator delete(v24);
        *((_QWORD *)this + 43) = 0;
      }
      if ( v25 )
      {
        operator delete(v25);
        *((_QWORD *)this + 44) = 0;
      }
      if ( v26 )
      {
        operator delete(v26);
        *((_QWORD *)this + 34) = 0;
      }
      return v27;
    }
    *((_QWORD *)this + 43) = v24;
    v27 = 0;
    v25 = 0;
  }
  if ( v69 )
  {
    v41 = 0x7FFFFFFF;
    v42 = v69;
    do
    {
      if ( !*v42 )
        break;
      ++v42;
      --v41;
    }
    while ( v41 );
    v27 = -2147024809;
    if ( v41 )
      v27 = 0;
    v43 = 0x7FFFFFFF - v41;
    if ( !v41 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        cbMultiByte = v27;
        v70 = (LPCWCH)"PrepareNanoIceInitializationParameters";
        v69 = (LPCWCH)"aadIdAuthToken length";
        lpWideCharStr = (LPCWCH)"Condition failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          0,
          (unsigned int)qword_1801CC508,
          0,
          v12,
          (__int64)&lpWideCharStr,
          (__int64)&v69,
          (__int64)&v70,
          (__int64)&cbMultiByte);
      }
      goto LABEL_61;
    }
    v27 = -2147024809;
    v44 = WideCharToMultiByte(0xFDE9u, 0, v69, v43, 0, 0, 0, 0);
    cbMultiByte = v44;
    if ( v44 <= 0 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        cbMultiByte = GetLastError();
        v70 = (LPCWCH)"PrepareNanoIceInitializationParameters";
        v69 = (LPCWCH)"aadIdAuthToken utf8 length";
        lpWideCharStr = (LPCWCH)"Condition failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v45,
          (unsigned int)byte_1801CCB05,
          v46,
          v47,
          (__int64)&lpWideCharStr,
          (__int64)&v69,
          (__int64)&v70,
          (__int64)&cbMultiByte);
      }
      goto LABEL_61;
    }
    v48 = v44 + 1;
    lpWideCharStr = (LPCWCH)(int)v48;
    v49 = operator new(v48);
    Block = v49;
    if ( v49 )
    {
      memset_0(v49, 0, (size_t)lpWideCharStr);
      v49 = Block;
    }
    else
    {
      Block = 0;
    }
    if ( WideCharToMultiByte(0xFDE9u, 0, v69, v43, (LPSTR)v49, cbMultiByte, 0, 0) <= 0 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        cbMultiByte = GetLastError();
        v70 = (LPCWCH)"PrepareNanoIceInitializationParameters";
        v69 = (LPCWCH)"aadIdAuthTokenUTF8 utf8 conversion";
        lpWideCharStr = (LPCWCH)"Condition failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v50,
          (unsigned int)&dword_1801CD034,
          v51,
          v52,
          (__int64)&lpWideCharStr,
          (__int64)&v69,
          (__int64)&v70,
          (__int64)&cbMultiByte);
      }
      v25 = Block;
      goto LABEL_62;
    }
    v25 = Block;
    *((_QWORD *)this + 44) = Block;
    v27 = 0;
  }
  if ( v70 )
  {
    v53 = 0x7FFFFFFF;
    v54 = v70;
    do
    {
      if ( !*v54 )
        break;
      ++v54;
      --v53;
    }
    while ( v53 );
    v27 = -2147024809;
    if ( v53 )
      v27 = 0;
    v55 = 0x7FFFFFFF - v53;
    if ( !v53 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        cbMultiByte = v27;
        v70 = (LPCWCH)"PrepareNanoIceInitializationParameters";
        v69 = (LPCWCH)"activityHint length";
        lpWideCharStr = (LPCWCH)"Condition failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          0,
          (unsigned int)byte_1801CD511,
          0,
          v12,
          (__int64)&lpWideCharStr,
          (__int64)&v69,
          (__int64)&v70,
          (__int64)&cbMultiByte);
      }
      goto LABEL_62;
    }
    v27 = -2147024809;
    v56 = WideCharToMultiByte(0xFDE9u, 0, v70, v55, 0, 0, 0, 0);
    cbMultiByte = v56;
    if ( v56 <= 0 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        cbMultiByte = GetLastError();
        v70 = (LPCWCH)"PrepareNanoIceInitializationParameters";
        v69 = (LPCWCH)"activityHint utf8 length";
        lpWideCharStr = (LPCWCH)"Condition failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v57,
          (unsigned int)&word_1801CCC9E,
          v58,
          v59,
          (__int64)&lpWideCharStr,
          (__int64)&v69,
          (__int64)&v70,
          (__int64)&cbMultiByte);
      }
      goto LABEL_62;
    }
    v60 = v56 + 1;
    v69 = (LPCWCH)(int)v60;
    v61 = operator new(v60);
    v26 = v61;
    if ( v61 )
      memset_0(v61, 0, (size_t)v69);
    else
      v26 = 0;
    if ( WideCharToMultiByte(0xFDE9u, 0, v70, v55, (LPSTR)v26, cbMultiByte, 0, 0) <= 0 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        cbMultiByte = GetLastError();
        v70 = (LPCWCH)"PrepareNanoIceInitializationParameters";
        v69 = (LPCWCH)"activityHintUTF8 utf8 conversion";
        lpWideCharStr = (LPCWCH)"Condition failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v62,
          (unsigned int)&word_1801CD5FE,
          v63,
          v64,
          (__int64)&lpWideCharStr,
          (__int64)&v69,
          (__int64)&v70,
          (__int64)&cbMultiByte);
      }
      goto LABEL_62;
    }
    *((_QWORD *)this + 34) = v26;
    v27 = 0;
  }
  v65 = *((_DWORD *)a2 + 12);
  *((_DWORD *)this + 90) = v65;
  if ( v65 == 4 )
    *((_QWORD *)this + 35) |= 0x800uLL;
  if ( *((_DWORD *)a2 + 20) )
    *((_QWORD *)this + 35) |= 0x400uLL;
  return v27;
}

```

## disassembly

```asm
0x18011bb80  mov     [rsp-8+arg_10], rbx
0x18011bb85  push    rbp
0x18011bb86  push    rsi
0x18011bb87  push    rdi
0x18011bb88  push    r12
0x18011bb8a  push    r13
0x18011bb8c  push    r14
0x18011bb8e  push    r15
0x18011bb90  lea     rbp, [rsp-20h]
0x18011bb95  sub     rsp, 120h
0x18011bb9c  mov     rax, cs:__security_cookie
0x18011bba3  xor     rax, rsp
0x18011bba6  mov     [rbp+50h+var_50], rax
0x18011bbaa  mov     r8, [rdx+28h]
0x18011bbae  xorps   xmm0, xmm0
0x18011bbb1  mov     eax, [rdx+18h]
0x18011bbb4  mov     rsi, rdx
0x18011bbb7  mov     r15d, [rdx+54h]
0x18011bbbb  mov     rbx, rcx
0x18011bbbe  mov     r12d, [rdx+58h]
0x18011bbc2  mov     r13d, [rdx+5Ch]
0x18011bbc6  mov     [rsp+150h+lpWideCharStr], r8
0x18011bbcb  mov     r8, [rdx+40h]
0x18011bbcf  mov     [rsp+150h+var_F0], r8
0x18011bbd4  mov     r8, [rdx+48h]
0x18011bbd8  lea     rdx, [rbp+50h+ActivityId]; ActivityId
0x18011bbdc  mov     [rcx+0D0h], eax
0x18011bbe2  mov     ecx, 1; ControlCode
0x18011bbe7  movups  xmmword ptr [rbp+50h+ActivityId.Data1], xmm0
0x18011bbeb  mov     [rsp+150h+var_D4], eax
0x18011bbef  mov     [rsp+150h+var_E8], r8
0x18011bbf4  mov     [rbp+50h+ActivityId.Data1], 0F4E00000h
0x18011bbfb  call    cs:__imp_EventActivityIdControl
0x18011bc01  mov     ecx, 0Ch; Size
0x18011bc06  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18011bc0b  mov     r14, rax
0x18011bc0e  test    rax, rax
0x18011bc11  jz      short loc_18011BC1B
0x18011bc13  mov     dword ptr [rax], 32h ; '2'
0x18011bc19  jmp     short loc_18011BC1E
0x18011bc1b  xor     r14d, r14d
0x18011bc1e  mov     dword ptr [r14+8], 3
0x18011bc26  lea     rdi, [rbx+118h]
0x18011bc2d  mov     dword ptr [r14+4], 64h ; 'd'
0x18011bc35  test    byte ptr [rsi+20h], 2
0x18011bc39  jz      short loc_18011BC3F
0x18011bc3b  or      qword ptr [rdi], 2
0x18011bc3f  cmp     [rsp+150h+var_D4], 0
0x18011bc44  jz      short loc_18011BC5D
0x18011bc46  call    ?IsEnabled@FeatureFlag@@YA_NPEAG@Z; FeatureFlag::IsEnabled(ushort *)
0x18011bc4b  test    al, al
0x18011bc4d  jz      short loc_18011BC5D
0x18011bc4f  mov     ecx, 1
0x18011bc54  lea     rdi, [rbx+118h]
0x18011bc5b  jmp     short loc_18011BC5F
0x18011bc5d  xor     ecx, ecx
0x18011bc5f  mov     [rsp+150h+var_D8], ecx
0x18011bc63  test    r15d, r15d
0x18011bc66  jz      short loc_18011BC79
0x18011bc68  lea     rdi, [rbx+118h]
0x18011bc6f  mov     eax, [rdi]
0x18011bc71  bts     rax, 0Dh
0x18011bc76  mov     [rdi], rax
0x18011bc79  test    r12d, r12d
0x18011bc7c  jz      short loc_18011BC88
0x18011bc7e  mov     eax, [rdi]
0x18011bc80  bts     rax, 11h
0x18011bc85  mov     [rdi], rax
0x18011bc88  test    r13d, r13d
0x18011bc8b  jz      short loc_18011BC97
0x18011bc8d  mov     eax, [rdi]
0x18011bc8f  bts     rax, 12h
0x18011bc94  mov     [rdi], rax
0x18011bc97  test    ecx, ecx
0x18011bc99  jz      short loc_18011BCA4
0x18011bc9b  mov     eax, [rdi]
0x18011bc9d  or      rax, 2
0x18011bca1  mov     [rdi], rax
0x18011bca4  test    byte ptr [rsi+20h], 1
0x18011bca8  jz      short loc_18011BCB3
0x18011bcaa  mov     eax, [rdi]
0x18011bcac  or      rax, 1
0x18011bcb0  mov     [rdi], rax
0x18011bcb3  test    byte ptr [rsi+20h], 10h
0x18011bcb7  jz      short loc_18011BCC6
0x18011bcb9  mov     eax, [rdi]
0x18011bcbb  or      rax, 10h
0x18011bcbf  mov     [rbx+118h], rax
0x18011bcc6  test    byte ptr [rsi+20h], 20h
0x18011bcca  jz      short loc_18011BCDD
0x18011bccc  mov     eax, [rbx+118h]
0x18011bcd2  or      rax, 20h
0x18011bcd6  mov     [rbx+118h], rax
0x18011bcdd  test    byte ptr [rsi+20h], 40h
0x18011bce1  jz      short loc_18011BCF4
0x18011bce3  mov     eax, [rbx+118h]
0x18011bce9  or      rax, 40h
0x18011bced  mov     [rbx+118h], rax
0x18011bcf4  test    dword ptr [rsi+20h], 100h
0x18011bcfb  jz      short loc_18011BD0F
0x18011bcfd  mov     eax, [rbx+118h]
0x18011bd03  bts     rax, 8
0x18011bd08  mov     [rbx+118h], rax
0x18011bd0f  cmp     dword ptr [rsi+64h], 1
0x18011bd13  jbe     short loc_18011BD27
0x18011bd15  mov     eax, [rbx+118h]
0x18011bd1b  bts     rax, 0Fh
0x18011bd20  mov     [rbx+118h], rax
0x18011bd27  mov     eax, [rsi+8]
0x18011bd2a  test    eax, eax
0x18011bd2c  jz      short loc_18011BDA3
0x18011bd2e  cmp     qword ptr [rsi], 0
0x18011bd32  jz      short loc_18011BDA3
0x18011bd34  lea     edx, [rax+1]
0x18011bd37  lea     rcx, [rsp+150h+Block]
0x18011bd3c  call    ??$make_unique@$$BY0A@D$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@DU?$default_delete@$$BY0A@D@utl@@@0@_K@Z; utl::make_unique<char [0],0>(unsigned __int64)
0x18011bd41  mov     rdx, [rax]
0x18011bd44  mov     qword ptr [rax], 0
0x18011bd4b  mov     rcx, [rbx+0A0h]; Block
0x18011bd52  mov     [rbx+0A0h], rdx
0x18011bd59  test    rcx, rcx
0x18011bd5c  jz      short loc_18011BD63
0x18011bd5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011bd63  mov     rcx, [rsp+150h+Block]; Block
0x18011bd68  test    rcx, rcx
0x18011bd6b  jz      short loc_18011BD72
0x18011bd6d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011bd72  mov     rcx, [rbx+0A0h]; void *
0x18011bd79  test    rcx, rcx
0x18011bd7c  jz      loc_18011BFD6
0x18011bd82  mov     r8d, [rsi+8]
0x18011bd86  mov     rdx, [rsi]; Src
0x18011bd89  inc     r8d; Size
0x18011bd8c  call    memcpy_0
0x18011bd91  mov     rax, [rbx+0A0h]
0x18011bd98  mov     ecx, [rsp+150h+var_D8]
0x18011bd9c  mov     [rbx+170h], rax
0x18011bda3  mov     eax, [rsi+0Ch]
0x18011bda6  xor     r8d, r8d; ActivityId
0x18011bda9  mov     edx, [rsp+150h+var_D4]
0x18011bdad  xorps   xmm0, xmm0
0x18011bdb0  mov     [rbx+150h], eax
0x18011bdb6  test    edx, edx
0x18011bdb8  mov     rax, [rbx+58h]
0x18011bdbc  mov     r13d, r8d
0x18011bdbf  mov     [rbx+0D8h], rax
0x18011bdc6  mov     r15d, r8d
0x18011bdc9  mov     rax, [rbx+60h]
0x18011bdcd  mov     r12d, r8d
0x18011bdd0  mov     [rbx+0E0h], rax
0x18011bdd7  mov     edi, r8d
0x18011bdda  mov     rax, [rbx+68h]
0x18011bdde  mov     [rbx+0E8h], rax
0x18011bde5  mov     eax, r8d
0x18011bde8  setz    al
0x18011bdeb  mov     [rbx+140h], r14
0x18011bdf2  mov     [rbx+0F8h], eax
0x18011bdf8  mov     [rbx+0FCh], r8d
0x18011bdff  mov     eax, [rsi+60h]
0x18011be02  mov     [rbx+178h], eax
0x18011be08  movups  xmmword ptr [rbx+100h], xmm0
0x18011be0f  mov     eax, cs:CallbackContext
0x18011be15  movaps  [rsp+150h+var_40], xmm6
0x18011be1d  movaps  xmm6, xmmword ptr [rbp+50h+ActivityId.Data1]
0x18011be21  cmp     eax, 4
0x18011be24  jbe     loc_18011BF06
0x18011be2a  mov     eax, [rbx+0F8h]
0x18011be30  xor     r9d, r9d; RelatedActivityId
0x18011be33  mov     [rbp+50h+ActivityId.Data1], eax
0x18011be36  lea     rax, [rsp+150h+var_D4]
0x18011be3b  mov     [rbp+50h+var_60], rax
0x18011be3f  lea     rax, [rsp+150h+var_D8]
0x18011be44  mov     [rbp+50h+var_70], rax
0x18011be48  lea     rax, [rbp+50h+ActivityId]
0x18011be4c  mov     [rbp+50h+var_80], rax
0x18011be50  lea     rax, aIceInitParamsF; "ICE: Init params: fIsClient=%d, control"...
0x18011be57  mov     [rbp+50h+var_90], rax
0x18011be5b  movzx   eax, cs:word_1801CD543
0x18011be62  mov     dword ptr [rbp+50h+EventDescriptor.Level], eax
0x18011be65  mov     rax, cs:off_1801E7010
0x18011be6c  mov     [rbp+50h+var_B0.Ptr], rax
0x18011be70  mov     [rsp+150h+var_D8], ecx
0x18011be74  lea     rcx, _TraceLoggingMetadata
0x18011be7b  mov     [rsp+150h+var_D4], edx
0x18011be7f  lea     rdx, [rbp+50h+EventDescriptor]; EventDescriptor
0x18011be83  mov     [rbp+50h+var_58], 4
0x18011be8b  mov     [rbp+50h+var_68], 4
0x18011be93  mov     [rbp+50h+var_78], 4
0x18011be9b  mov     [rbp+50h+var_88], 2Fh ; '/'
0x18011bea3  mov     dword ptr [rbp+50h+EventDescriptor.Id], 0B000000h
0x18011beaa  mov     [rbp+50h+EventDescriptor.Keyword], r8
0x18011beae  movzx   eax, word ptr [rax]
0x18011beb1  mov     [rbp+50h+var_B0.Size], eax
0x18011beb4  lea     rax, byte_1801CD54D
0x18011bebb  mov     [rbp+50h+var_A0], rax
0x18011bebf  lea     rax, _TraceLoggingMetadataEnd
0x18011bec6  sub     eax, ecx
0x18011bec8  mov     dword ptr [rbp+50h+var_B0.0Ch], 2
0x18011becf  mov     [rbp+50h+var_98], 46h ; 'F'
0x18011bed6  mov     [rbp+50h+var_94], 1
0x18011bedd  mov     [rsp+150h+cbMultiByte], eax
0x18011bee1  mov     eax, [rsp+150h+cbMultiByte]
0x18011bee5  mov     rcx, cs:RegHandle; RegHandle
0x18011beec  lea     rax, [rbp+50h+var_B0]
0x18011bef0  mov     [rsp+150h+UserData], rax; UserData
0x18011bef5  mov     [rsp+150h+UserDataCount], 6; UserDataCount
0x18011befd  call    cs:__imp_EventWriteTransfer
0x18011bf03  xor     r8d, r8d
0x18011bf06  movups  xmmword ptr [rbx+100h], xmm6
0x18011bf0d  mov     r14d, 7FFFFFFFh
0x18011bf13  movaps  xmm6, [rsp+150h+var_40]
0x18011bf1b  cmp     [rsi+30h], edi
0x18011bf1e  jz      loc_18011C21B
0x18011bf24  mov     rdx, [rsp+150h+lpWideCharStr]
0x18011bf29  test    rdx, rdx
0x18011bf2c  jz      loc_18011C21B
0x18011bf32  mov     ecx, r14d
0x18011bf35  mov     rax, rdx
0x18011bf38  cmp     [rax], di
0x18011bf3b  jz      short loc_18011BF47
0x18011bf3d  add     rax, 2
0x18011bf41  sub     rcx, 1
0x18011bf45  jnz     short loc_18011BF38
0x18011bf47  test    rcx, rcx
0x18011bf4a  mov     edi, 80070057h
0x18011bf4f  mov     r15, r14
0x18011bf52  cmovnz  edi, r8d
0x18011bf56  sub     r15, rcx
0x18011bf59  test    rcx, rcx
0x18011bf5c  cmovz   r15, r8
0x18011bf60  jnz     loc_18011C073
0x18011bf66  mov     eax, cs:CallbackContext
0x18011bf6c  cmp     eax, 3
0x18011bf6f  jbe     loc_18011C6F0
0x18011bf75  lea     rax, aPreparenanoice; "PrepareNanoIceInitializationParameters"
0x18011bf7c  mov     [rsp+150h+cbMultiByte], edi
0x18011bf80  mov     [rsp+150h+var_E8], rax
0x18011bf85  lea     rdx, byte_1801CCF8F
0x18011bf8c  lea     rax, aRendezvousurlL; "rendezvousURL length"
0x18011bf93  mov     [rsp+150h+var_F0], rax
0x18011bf98  lea     rax, aConditionFaile; "Condition failed but continue"
0x18011bf9f  mov     [rsp+150h+lpWideCharStr], rax
0x18011bfa4  lea     rax, [rsp+150h+cbMultiByte]
0x18011bfa9  mov     [rsp+150h+lpUsedDefaultChar], rax
0x18011bfae  lea     rax, [rsp+150h+var_E8]
0x18011bfb3  mov     [rsp+150h+lpDefaultChar], rax
0x18011bfb8  lea     rax, [rsp+150h+var_F0]
0x18011bfbd  mov     [rsp+150h+UserData], rax
0x18011bfc2  lea     rax, [rsp+150h+lpWideCharStr]
0x18011bfc7  mov     qword ptr [rsp+150h+UserDataCount], rax
0x18011bfcc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18011bfd1  jmp     loc_18011C6F0
0x18011bfd6  mov     eax, cs:CallbackContext
0x18011bfdc  mov     edi, 8007000Eh
0x18011bfe1  cmp     eax, 2
0x18011bfe4  jbe     loc_18011C6F0
0x18011bfea  lea     rax, aIceserverconfi; "iceServerConfigJson memory allocation f"...
0x18011bff1  mov     [rsp+150h+var_D4], 5F3h
0x18011bff9  mov     [rsp+150h+var_E8], rax
0x18011bffe  lea     rdx, word_1801CC8D6
0x18011c005  lea     rax, aPreparenanoice; "PrepareNanoIceInitializationParameters"
0x18011c00c  mov     [rsp+150h+var_D8], edi
0x18011c010  mov     [rsp+150h+var_F0], rax
0x18011c015  lea     rax, aOnecoreTermsrv_59; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18011c01c  mov     [rsp+150h+lpWideCharStr], rax
0x18011c021  lea     rax, aErrorCondition; "Error condition failed"
0x18011c028  mov     [rsp+150h+Block], rax
0x18011c02d  lea     rax, [rsp+150h+var_E8]
0x18011c032  mov     [rsp+150h+var_108], rax
0x18011c037  lea     rax, [rsp+150h+var_F0]
0x18011c03c  mov     [rsp+150h+var_110], rax
0x18011c041  lea     rax, [rsp+150h+var_D4]
0x18011c046  mov     [rsp+150h+lpUsedDefaultChar], rax
0x18011c04b  lea     rax, [rsp+150h+lpWideCharStr]
0x18011c050  mov     [rsp+150h+lpDefaultChar], rax
0x18011c055  lea     rax, [rsp+150h+var_D8]
0x18011c05a  mov     [rsp+150h+UserData], rax
0x18011c05f  lea     rax, [rsp+150h+Block]
0x18011c064  mov     qword ptr [rsp+150h+UserDataCount], rax
0x18011c069  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18011c06e  jmp     loc_18011C6F0
0x18011c073  mov     [rsp+150h+lpUsedDefaultChar], r8; lpUsedDefaultChar
0x18011c078  mov     r9d, r15d; cchWideChar
0x18011c07b  mov     [rsp+150h+lpDefaultChar], r8; lpDefaultChar
0x18011c080  mov     ecx, 0FDE9h; CodePage
0x18011c085  mov     dword ptr [rsp+150h+UserData], r8d; cbMultiByte
0x18011c08a  mov     edi, 80070057h
0x18011c08f  mov     qword ptr [rsp+150h+UserDataCount], r8; lpMultiByteStr
0x18011c094  mov     r8, rdx; lpWideCharStr
0x18011c097  xor     edx, edx; dwFlags
0x18011c099  call    cs:__imp_WideCharToMultiByte
0x18011c09f  mov     [rsp+150h+cbMultiByte], eax
0x18011c0a3  test    eax, eax
0x18011c0a5  jg      short loc_18011C11D
0x18011c0a7  mov     eax, cs:CallbackContext
0x18011c0ad  cmp     eax, 3
0x18011c0b0  jbe     loc_18011C6F0
0x18011c0b6  call    cs:__imp_GetLastError
0x18011c0bc  mov     [rsp+150h+cbMultiByte], eax
0x18011c0c0  lea     rdx, word_1801CD472
  ... truncated ...
```
