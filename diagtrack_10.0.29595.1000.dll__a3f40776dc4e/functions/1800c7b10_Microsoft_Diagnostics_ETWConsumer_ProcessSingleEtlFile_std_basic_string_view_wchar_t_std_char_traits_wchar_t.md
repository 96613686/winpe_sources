# Microsoft::Diagnostics::ETWConsumer::ProcessSingleEtlFile(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x1800c7b10`
- end: `0x1800c86ff`
- name: `?ProcessSingleEtlFile@ETWConsumer@Diagnostics@Microsoft@@AEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `3055`
- prototype: ``
- caller_count: `1`
- callee_count: `41`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c7468`

## callees

- `0x180002a28`
- `0x180002b90`
- `0x1800036cc`
- `0x180020e6c`
- `0x18002b7c0`
- `0x18002b7fc`
- `0x18002cb04`
- `0x18002df00`
- `0x18003c66c`
- `0x18004add0`
- `0x18004b6ac`
- `0x18005d660`
- `0x18005fb44`
- `0x1800624ac`
- `0x180064e8c`
- `0x18006962c`
- `0x18008a4ec`
- `0x18008a51c`
- `0x18008a580`
- `0x18008a5d8`
- `0x18008ab10`
- `0x18009c8c0`
- `0x1800b47f0`
- `0x1800c7b10`
- `0x1800c96d4`
- `0x1800d11c0`
- `0x1800f7eb8`
- `0x1800ff4dc`
- `0x180101880`
- `0x180133918`
- `0x180142fcc`
- `0x1801a38f4`
- `0x1801abcac`
- `0x1801c9ee4`
- `0x1801cc990`
- `0x1801cd84c`
- `0x1801cfc7c`
- `0x1801dd5d0`
- `0x1801e14d0`
- `0x18020aac0`
- `0x18020bab8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7d07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7d07`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800c818d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800c818d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800c7e9b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800c866b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800c7e9b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800c866b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800c861e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800c861e`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x1800c80be`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x1800c80be`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x1800c7ce6`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x1800c7ce6`

## string_xrefs

- `0x1800c7e61`: `onecore\base\telemetry\utc\service\triggers\etwconsumer.cpp`
- `0x1800c7ead`: `onecore\base\telemetry\utc\service\triggers\etwconsumer.cpp`
- `0x1800c7ed1`: `onecore\base\telemetry\utc\service\triggers\etwconsumer.cpp`
- `0x1800c819f`: `onecore\base\telemetry\utc\service\triggers\etwconsumer.cpp`
- `0x1800c852a`: `onecore\base\telemetry\utc\service\triggers\etwconsumer.cpp`
- `0x1800c8630`: `onecore\base\telemetry\utc\service\triggers\etwconsumer.cpp`
- `0x1800c867d`: `onecore\base\telemetry\utc\service\triggers\etwconsumer.cpp`
- `0x1800c869d`: `onecore\base\telemetry\utc\service\triggers\etwconsumer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::ETWConsumer::ProcessSingleEtlFile(__int64 a1, _QWORD *a2)
{
  __int64 last_of; // rax
  __int64 v5; // rbx
  __int64 v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // rax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  WCHAR *v12; // rax
  TRACEHANDLE v13; // rax
  ULONG64 v14; // rbx
  signed int v15; // esi
  signed int LastError; // eax
  __int64 v17; // rax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  const WCHAR *v22; // rcx
  const char *v23; // r9
  unsigned int v24; // ebx
  _WORD *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rax
  unsigned __int64 UbiTime; // rsi
  signed int v31; // eax
  __int64 v32; // rax
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  const WCHAR *v36; // rcx
  const char *v37; // r9
  __int64 TopResult; // rax
  int v39; // eax
  const WCHAR *v40; // rdx
  const WCHAR *v41; // rcx
  const char *v42; // r9
  const WCHAR *v43; // rcx
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-C78h]
  int v46; // [rsp+20h] [rbp-C78h]
  __int128 v47; // [rsp+40h] [rbp-C58h] BYREF
  _QWORD v48[2]; // [rsp+50h] [rbp-C48h] BYREF
  __int128 v49; // [rsp+60h] [rbp-C38h] BYREF
  char *v50; // [rsp+70h] [rbp-C28h]
  __int64 v51; // [rsp+78h] [rbp-C20h] BYREF
  ULONG64 HandleArray; // [rsp+80h] [rbp-C18h] BYREF
  __int128 v53; // [rsp+88h] [rbp-C10h]
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+A0h] [rbp-BF8h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+260h] [rbp-A38h] BYREF
  unsigned __int64 v56; // [rsp+278h] [rbp-A20h]
  LPCWSTR lpNewFileName[2]; // [rsp+280h] [rbp-A18h] BYREF
  __int64 v58; // [rsp+290h] [rbp-A08h]
  unsigned __int64 v59; // [rsp+298h] [rbp-A00h]
  __int128 FileInformation; // [rsp+2A0h] [rbp-9F8h] BYREF
  __int128 v61; // [rsp+2B0h] [rbp-9E8h]
  int v62; // [rsp+2C0h] [rbp-9D8h]
  _BYTE Src[32]; // [rsp+2C8h] [rbp-9D0h] BYREF
  _BYTE v64[24]; // [rsp+2E8h] [rbp-9B0h] BYREF
  __int64 v65; // [rsp+300h] [rbp-998h]
  __int64 v66; // [rsp+310h] [rbp-988h]
  int v67[282]; // [rsp+330h] [rbp-968h] BYREF
  int v68[14]; // [rsp+798h] [rbp-500h] BYREF
  int v69[282]; // [rsp+7D0h] [rbp-4C8h] BYREF
  int v70[14]; // [rsp+C38h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C98h] [rbp+0h]

  std::wstring::wstring(lpFileName);
  *(_QWORD *)&v49 = L"Unknown";
  *((_QWORD *)&v49 + 1) = 7;
  last_of = std::wstring_view::find_last_of(a2, L"\\", -1);
  v5 = last_of;
  if ( last_of == -1 )
  {
    v53 = *(_OWORD *)a2;
  }
  else
  {
    v53 = *(_OWORD *)std::wstring_view::substr(a2, &v47, last_of + 1, -1);
    v6 = std::wstring_view::find_last_of(a2, L"\\", v5 - 1);
    if ( v6 != -1 )
      v49 = *(_OWORD *)std::wstring_view::substr(a2, &v47, v6 + 1, v5 - v6 - 1);
  }
  v47 = *(_OWORD *)&off_1803874D0;
  if ( (unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(&v47) )
  {
    v7 = 0;
    if ( (unsigned int)dword_1804543B0 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 3) )
    {
      v8 = _tlgWrapBinary<wchar_t,2>(&v47, *a2, *((unsigned int *)a2 + 2));
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(
        v9,
        (unsigned int)byte_1803FA625,
        v10,
        v11,
        v8);
    }
LABEL_47:
    v47 = *(_OWORD *)&off_1803874C0;
    if ( (unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(&v47) )
    {
      std::wstring::wstring(lpNewFileName);
      *(_QWORD *)&v47 = L".bk";
      *((_QWORD *)&v47 + 1) = 3;
      *(_QWORD *)&v49 = L".etl";
      *((_QWORD *)&v49 + 1) = 4;
      Microsoft::Diagnostics::Utils::String::ReplaceAllImpl<wchar_t>(lpNewFileName);
      v40 = (const WCHAR *)lpNewFileName;
      if ( v59 > 7 )
        v40 = lpNewFileName[0];
      v41 = (const WCHAR *)lpFileName;
      if ( v56 > 7 )
        v41 = lpFileName[0];
      if ( !MoveFileExW(v41, v40, 1u) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x856,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwconsumer.cpp",
          v42);
      std::wstring::_Tidy_deallocate(lpNewFileName);
    }
    else
    {
      v43 = (const WCHAR *)lpFileName;
      if ( v56 > 7 )
        v43 = lpFileName[0];
      if ( !DeleteFileW(v43) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x85A,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwconsumer.cpp",
          v44);
    }
    if ( (v7 & 0x80000000) == 0 )
    {
      std::wstring::_Tidy_deallocate(lpFileName);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x85C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwconsumer.cpp",
        (const char *)v7,
        v45);
      std::wstring::_Tidy_deallocate(lpFileName);
      return v7;
    }
  }
  Microsoft::Diagnostics::BlackBox::LogEvent(&xmmword_180462AB0, 5, 0, 0, 0);
  memset_0(&Logfile, 0, sizeof(Logfile));
  v12 = (WCHAR *)lpFileName;
  if ( v56 > 7 )
    v12 = (WCHAR *)lpFileName[0];
  Logfile.LogFileName = v12;
  Logfile.EventCallback = (PEVENT_CALLBACK)Microsoft::Diagnostics::ETWConsumer::StaticEtlEtwEventCallback;
  Logfile.BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)Microsoft::Diagnostics::ETWConsumer::StaticEtwBufferCallback;
  Logfile.LogFileMode = 0x10000000;
  Logfile.Context = (PVOID)a1;
  v51 = -1;
  v13 = OpenTraceW(&Logfile);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,unsigned long (unsigned __int64),&unsigned long CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>::reset(
    &v51,
    v13);
  v14 = v51;
  if ( v51 == -1 )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v15 = 0;
  }
  LODWORD(v50) = v15;
  if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 3) )
  {
    v17 = _tlgWrapBinary<wchar_t,2>(&v47, *a2, *((unsigned int *)a2 + 2));
    LODWORD(v48[0]) = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
      v18,
      (unsigned int)byte_1803FA5DB,
      v19,
      v20,
      (__int64)v48,
      v17);
  }
  if ( v15 >= 0 )
  {
    *(_QWORD *)(a1 + 2184) = 0;
    if ( *(_QWORD *)(a1 + 2192) <= 7u )
      v26 = (_WORD *)(a1 + 2168);
    else
      v26 = *(_WORD **)(a1 + 2168);
    *v26 = 0;
    std::wstring::wstring(Src);
    std::wstring::_Append<wchar_t>(Src);
    *(_OWORD *)lpNewFileName = 0;
    v58 = 0;
    v59 = 15;
    LOBYTE(lpNewFileName[0]) = 0;
    v47 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v48);
    Microsoft::Diagnostics::Utils::FileSystem::ReadStringFromFile(&v47, v27, 0xFFFFFFFFLL, lpNewFileName);
    if ( v58 )
    {
      v47 = *(_OWORD *)std::string::operator std::string_view(lpNewFileName, v48);
      v28 = Microsoft::Diagnostics::Utils::String::MultiByteStringToWideString(v64, &v47);
      std::wstring::operator=(a1 + 2168, v28);
      std::wstring::_Tidy_deallocate(v64);
    }
    memset_0(v64, 0, 0x40u);
    v29 = Microsoft::Diagnostics::ETWConsumer::EtlLogStats::EtlLogStats((Microsoft::Diagnostics::ETWConsumer::EtlLogStats *)v64);
    Microsoft::Diagnostics::ETWConsumer::EtlLogStats::operator=(a1 + 536, v29);
    if ( v65 )
      std::_Deallocate<16>(v65, 20 * ((v66 - v65) / 20));
    UbiTime = Microsoft::Diagnostics::Utils::Time::QueryUbiTime();
    *(_WORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 52LL) = -1;
    HandleArray = v14;
    v31 = ProcessTrace(&HandleArray, 1u, 0, 0);
    v7 = v31;
    if ( v31 > 0 )
      v7 = (unsigned __int16)v31 | 0x80070000;
    if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 3) )
    {
      v32 = _tlgWrapBinary<wchar_t,2>(&v47, *a2, *((unsigned int *)a2 + 2));
      LODWORD(v48[0]) = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
        v33,
        (unsigned int)byte_1803FA669,
        v34,
        v35,
        (__int64)v48,
        v32);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,unsigned long (unsigned __int64),&unsigned long CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>::reset(
      &v51,
      -1);
    Microsoft::Diagnostics::BlackBox::LogEvent(&xmmword_180462AB0, 6, 0, 0, 0);
    FileInformation = 0;
    v61 = 0;
    v62 = 0;
    v36 = (const WCHAR *)lpFileName;
    if ( v56 > 7 )
      v36 = lpFileName[0];
    if ( !GetFileAttributesExW(v36, GetFileExInfoStandard, &FileInformation) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x83A,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwconsumer.cpp",
        v37);
    v48[0] = L"ETWConsumer_EtlSingleFileSummary_1";
    v48[1] = 34;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
      (unsigned int)v67,
      (unsigned int)v48,
      0x1000000,
      0,
      0,
      0,
      0);
    LODWORD(v48[0]) = v62;
    HIDWORD(v48[0]) = HIDWORD(v61);
    *(_QWORD *)&v47 = L"FileName";
    *((_QWORD *)&v47 + 1) = 8;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v67, (int)v68);
    *(_QWORD *)&v47 = L"FileSizeBytes";
    *((_QWORD *)&v47 + 1) = 13;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v67, (int)v68);
    *(_QWORD *)&v47 = L"NumberOfEvents";
    *((_QWORD *)&v47 + 1) = 14;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(v67, v68, &v47, a1 + 536);
    v48[0] = Microsoft::Diagnostics::Utils::Time::QueryUbiTime() / 0x2710 - UbiTime / 0x2710;
    *(_QWORD *)&v47 = L"ProcessingTimeMs";
    *((_QWORD *)&v47 + 1) = 16;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v67, (int)v68);
    *(_QWORD *)&v47 = L"NumberOfBuffers";
    *((_QWORD *)&v47 + 1) = 15;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(v67, v68, &v47, a1 + 540);
    *(_QWORD *)&v47 = L"EventsLost";
    *((_QWORD *)&v47 + 1) = 10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(
      v67,
      v68,
      &v47,
      &Logfile.LogfileHeader.EventsLost);
    *(_QWORD *)&v47 = L"DroppedBuffers";
    *((_QWORD *)&v47 + 1) = 14;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(
      v67,
      v68,
      &v47,
      &Logfile.LogfileHeader.BuffersLost);
    Microsoft::Diagnostics::ModeEstimator<_GUID>::GetTopResult(a1 + 544);
    *(_QWORD *)&v47 = L"TopProvider";
    *((_QWORD *)&v47 + 1) = 11;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v67, (int)v68);
    *(_QWORD *)&v47 = L"TopProviderCount";
    *((_QWORD *)&v47 + 1) = 16;
    TopResult = Microsoft::Diagnostics::ModeEstimator<_GUID>::GetTopResult(a1 + 544);
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(v67, v68, &v47, TopResult + 16);
    v48[0] = *(_QWORD *)(a1 + 584);
    *(_QWORD *)&v47 = L"LogBeginTime";
    *((_QWORD *)&v47 + 1) = 12;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_FILETIME>((int)v67, (int)v68);
    v48[0] = *(_QWORD *)(a1 + 592);
    *(_QWORD *)&v47 = L"LogEndTime";
    *((_QWORD *)&v47 + 1) = 10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_FILETIME>((int)v67, (int)v68);
    *(_QWORD *)&v47 = L"Type";
    *((_QWORD *)&v47 + 1) = 4;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v67, (int)v68);
    v39 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v67);
    if ( v39 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x84F,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwconsumer.cpp",
        (const char *)(unsigned int)v39,
        v45);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v67);
    std::string::_Tidy_deallocate(lpNewFileName);
    std::wstring::_Tidy_deallocate(Src);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,unsigned long (unsigned __int64),&unsigned long CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,unsigned long (unsigned __int64),&unsigned long CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>(&v51);
    goto LABEL_47;
  }
  *(_QWORD *)&v49 = L"ETWConsumer_FailedToProcessETLFile_0";
  *((_QWORD *)&v49 + 1) = 36;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
    (unsigned int)v69,
    (unsigned int)&v49,
    0x1000000,
    0,
    0,
    0,
    0);
  *(_QWORD *)&v49 = L"ErrorCode";
  *((_QWORD *)&v49 + 1) = 9;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((int)v69, (int)v70);
  *(_QWORD *)&v49 = L"Filename";
  *((_QWORD *)&v49 + 1) = 8;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v69, (int)v70);
  v47 = 0;
  Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(v48, &v47);
  v21 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v69);
  if ( v21 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x80B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwconsumer.cpp",
      (const char *)(unsigned int)v21,
      v46);
  *(_WORD *)(a1 + 600) = 5;
  ++*(_DWORD *)(a1 + 604);
  v22 = (const WCHAR *)lpFileName;
  if ( v56 > 7 )
    v22 = lpFileName[0];
  if ( !DeleteFileW(v22) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x80E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwconsumer.cpp",
      v23);
  v24 = (unsigned int)v50;
  if ( (int)v50 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwconsumer.cpp",
      (const char *)(unsigned int)v50,
      v46);
  Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v69);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,unsigned long (unsigned __int64),&unsigned long CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,unsigned long (unsigned __int64),&unsigned long CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>(&v51);
  std::wstring::_Tidy_deallocate(lpFileName);
  return v24;
}

```

## disassembly

```asm
0x1800c7b10  mov     [rsp+arg_10], rbx
0x1800c7b15  mov     [rsp+arg_18], rsi
0x1800c7b1a  push    rdi
0x1800c7b1b  push    r12
0x1800c7b1d  push    r14
0x1800c7b1f  sub     rsp, 0C80h
0x1800c7b26  mov     rax, cs:__security_cookie
0x1800c7b2d  xor     rax, rsp
0x1800c7b30  mov     [rsp+0C98h+var_28], rax
0x1800c7b38  mov     rdi, rdx
0x1800c7b3b  mov     r14, rcx
0x1800c7b3e  lea     rcx, [rsp+0C98h+lpFileName]
0x1800c7b46  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1800c7b4b  nop
0x1800c7b4c  lea     rax, aUnknown_2; "Unknown"
0x1800c7b53  mov     qword ptr [rsp+0C98h+var_C38], rax
0x1800c7b58  mov     qword ptr [rsp+0C98h+var_C38+8], 7
0x1800c7b61  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800c7b65  mov     r8, rsi
0x1800c7b68  lea     rdx, asc_18039BD30; "\\"
0x1800c7b6f  mov     rcx, rdi
0x1800c7b72  call    ?find_last_of@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA_KQEB_W_K@Z; std::wstring_view::find_last_of(wchar_t const * const,unsigned __int64)
0x1800c7b77  mov     rbx, rax
0x1800c7b7a  cmp     rax, rsi
0x1800c7b7d  jnz     short loc_1800C7B8D
0x1800c7b7f  movups  xmm0, xmmword ptr [rdi]
0x1800c7b82  movdqu  [rsp+0C98h+var_C10], xmm0
0x1800c7b8b  jmp     short loc_1800C7BE6
0x1800c7b8d  lea     r8, [rax+1]
0x1800c7b91  mov     r9, rsi
0x1800c7b94  lea     rdx, [rsp+0C98h+var_C58]
0x1800c7b99  mov     rcx, rdi
0x1800c7b9c  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x1800c7ba1  movups  xmm0, xmmword ptr [rax]
0x1800c7ba4  movdqu  [rsp+0C98h+var_C10], xmm0
0x1800c7bad  lea     r8, [rbx-1]
0x1800c7bb1  lea     rdx, asc_18039BD30; "\\"
0x1800c7bb8  mov     rcx, rdi
0x1800c7bbb  call    ?find_last_of@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA_KQEB_W_K@Z; std::wstring_view::find_last_of(wchar_t const * const,unsigned __int64)
0x1800c7bc0  cmp     rax, rsi
0x1800c7bc3  jz      short loc_1800C7BE6
0x1800c7bc5  sub     rbx, rax
0x1800c7bc8  lea     r9, [rbx-1]
0x1800c7bcc  lea     r8, [rax+1]
0x1800c7bd0  lea     rdx, [rsp+0C98h+var_C58]
0x1800c7bd5  mov     rcx, rdi
0x1800c7bd8  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x1800c7bdd  movups  xmm0, xmmword ptr [rax]
0x1800c7be0  movdqu  [rsp+0C98h+var_C38], xmm0
0x1800c7be6  movups  xmm0, xmmword ptr cs:off_1803874D0; "DeleteEtlFilesWithoutProcessing"
0x1800c7bed  movdqu  [rsp+0C98h+var_C58], xmm0
0x1800c7bf3  lea     rcx, [rsp+0C98h+var_C58]
0x1800c7bf8  call    ?IsTestHookEnabled@General@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(std::wstring_view)
0x1800c7bfd  test    al, al
0x1800c7bff  jz      short loc_1800C7C50
0x1800c7c01  xor     ebx, ebx
0x1800c7c03  mov     eax, cs:dword_1804543B0
0x1800c7c09  cmp     eax, 3
0x1800c7c0c  jbe     loc_1800C8570
0x1800c7c12  lea     edx, [rbx+3]
0x1800c7c15  lea     rcx, dword_1804543B0
0x1800c7c1c  call    _tlgKeywordOn
0x1800c7c21  test    al, al
0x1800c7c23  jz      loc_1800C8570
0x1800c7c29  mov     r8d, [rdi+8]
0x1800c7c2d  mov     rdx, [rdi]
0x1800c7c30  lea     rcx, [rsp+0C98h+var_C58]
0x1800c7c35  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x1800c7c3a  mov     qword ptr [rsp+0C98h+var_C78], rax
0x1800c7c3f  lea     rdx, byte_1803FA625
0x1800c7c46  call    ??$Write@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &)
0x1800c7c4b  jmp     loc_1800C8570
0x1800c7c50  mov     r12d, 5
0x1800c7c56  xor     r8d, r8d
0x1800c7c59  mov     qword ptr [rsp+0C98h+var_C78], r8
0x1800c7c5e  xor     r9d, r9d
0x1800c7c61  movzx   edx, r12w
0x1800c7c65  lea     rcx, xmmword_180462AB0
0x1800c7c6c  call    ?LogEvent@BlackBox@Diagnostics@Microsoft@@QEAAXVBBTrace@23@G_K1@Z; Microsoft::Diagnostics::BlackBox::LogEvent(Microsoft::Diagnostics::BBTrace,ushort,unsigned __int64,unsigned __int64)
0x1800c7c71  xor     edx, edx; Val
0x1800c7c73  mov     r8d, 1C0h; Size
0x1800c7c79  lea     rcx, [rsp+0C98h+Logfile]; void *
0x1800c7c81  call    memset_0
0x1800c7c86  lea     rax, [rsp+0C98h+lpFileName]
0x1800c7c8e  cmp     [rsp+0C98h+var_A20], 7
0x1800c7c97  cmova   rax, [rsp+0C98h+lpFileName]
0x1800c7ca0  mov     [rsp+0C98h+Logfile.LogFileName], rax
0x1800c7ca8  lea     rax, ?StaticEtlEtwEventCallback@ETWConsumer@Diagnostics@Microsoft@@CAXPEAU_EVENT_RECORD@@@Z; Microsoft::Diagnostics::ETWConsumer::StaticEtlEtwEventCallback(_EVENT_RECORD *)
0x1800c7caf  mov     qword ptr [rsp+0C98h+Logfile.1A8h], rax
0x1800c7cb7  lea     rax, ?StaticEtwBufferCallback@ETWConsumer@Diagnostics@Microsoft@@CAKPEAU_EVENT_TRACE_LOGFILEW@@@Z; Microsoft::Diagnostics::ETWConsumer::StaticEtwBufferCallback(_EVENT_TRACE_LOGFILEW *)
0x1800c7cbe  mov     [rsp+0C98h+Logfile.BufferCallback], rax
0x1800c7cc6  mov     dword ptr [rsp+0C98h+Logfile.1Ch], 10000000h
0x1800c7cd1  mov     [rsp+0C98h+Logfile.Context], r14
0x1800c7cd9  mov     [rsp+0C98h+var_C20], rsi
0x1800c7cde  lea     rcx, [rsp+0C98h+Logfile]; Logfile
0x1800c7ce6  call    cs:__imp_OpenTraceW
0x1800c7cec  mov     rdx, rax
0x1800c7cef  lea     rcx, [rsp+0C98h+var_C20]
0x1800c7cf4  call    ?reset@?$unique_storage@U?$resource_policy@_K$$A6AK_K@Z$1?CloseTrace@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,ulong (unsigned __int64),&CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>::reset(unsigned __int64)
0x1800c7cf9  mov     rbx, [rsp+0C98h+var_C20]
0x1800c7cfe  cmp     rbx, rsi
0x1800c7d01  jz      short loc_1800C7D07
0x1800c7d03  xor     esi, esi
0x1800c7d05  jmp     short loc_1800C7D1C
0x1800c7d07  call    cs:__imp_GetLastError
0x1800c7d0d  mov     esi, eax
0x1800c7d0f  test    eax, eax
0x1800c7d11  jle     short loc_1800C7D1C
0x1800c7d13  movzx   esi, ax
0x1800c7d16  or      esi, 80070000h
0x1800c7d1c  mov     dword ptr [rsp+0C98h+var_C28], esi
0x1800c7d20  mov     eax, cs:dword_1804543B0
0x1800c7d26  cmp     eax, 4
0x1800c7d29  jbe     short loc_1800C7D70
0x1800c7d2b  mov     edx, 3
0x1800c7d30  lea     rcx, dword_1804543B0
0x1800c7d37  call    _tlgKeywordOn
0x1800c7d3c  test    al, al
0x1800c7d3e  jz      short loc_1800C7D70
0x1800c7d40  mov     r8d, [rdi+8]
0x1800c7d44  mov     rdx, [rdi]
0x1800c7d47  lea     rcx, [rsp+0C98h+var_C58]
0x1800c7d4c  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x1800c7d51  mov     dword ptr [rsp+0C98h+var_C48], esi
0x1800c7d55  mov     [rsp+0C98h+var_C70], rax
0x1800c7d5a  lea     rax, [rsp+0C98h+var_C48]
0x1800c7d5f  mov     qword ptr [rsp+0C98h+var_C78], rax
0x1800c7d64  lea     rdx, byte_1803FA5DB
0x1800c7d6b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperArray<1> const &)
0x1800c7d70  test    esi, esi
0x1800c7d72  jns     loc_1800C7F10
0x1800c7d78  xor     al, al
0x1800c7d7a  xor     cl, cl
0x1800c7d7c  lea     rdx, aEtwconsumerFai; "ETWConsumer_FailedToProcessETLFile_0"
0x1800c7d83  mov     qword ptr [rsp+0C98h+var_C38], rdx
0x1800c7d88  mov     qword ptr [rsp+0C98h+var_C38+8], 24h ; '$'
0x1800c7d91  mov     r8d, 1000000h
0x1800c7d97  mov     [rsp+0C98h+var_C68], al
0x1800c7d9b  mov     byte ptr [rsp+0C98h+var_C70], al
0x1800c7d9f  mov     byte ptr [rsp+0C98h+var_C78], cl; int
0x1800c7da3  mov     r9, 400000000000h
0x1800c7dad  lea     rdx, [rsp+0C98h+var_C38]
0x1800c7db2  lea     rcx, [rsp+0C98h+var_4C8]
0x1800c7dba  call    ??0AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@12@VTriggerLatency@12@_N@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency,bool)
0x1800c7dbf  nop
0x1800c7dc0  lea     rax, aErrorcode; "ErrorCode"
0x1800c7dc7  mov     qword ptr [rsp+0C98h+var_C38], rax
0x1800c7dcc  mov     qword ptr [rsp+0C98h+var_C38+8], 9
0x1800c7dd5  lea     r9, [rsp+0C98h+var_C28]
0x1800c7dda  lea     r8, [rsp+0C98h+var_C38]
0x1800c7ddf  lea     rdx, [rsp+0C98h+var_60]; int
0x1800c7de7  lea     rcx, [rsp+0C98h+var_4C8]; int
0x1800c7def  call    ??$AddField@J@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBJ@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,long const &)
0x1800c7df4  lea     rax, aFilename; "Filename"
0x1800c7dfb  mov     qword ptr [rsp+0C98h+var_C38], rax
0x1800c7e00  mov     qword ptr [rsp+0C98h+var_C38+8], 8
0x1800c7e09  lea     r9, [rsp+0C98h+var_C10]
0x1800c7e11  lea     r8, [rsp+0C98h+var_C38]
0x1800c7e16  lea     rdx, [rsp+0C98h+var_60]; int
0x1800c7e1e  lea     rcx, [rsp+0C98h+var_4C8]; int
0x1800c7e26  call    ??$AddField@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV45@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring_view const &)
0x1800c7e2b  xorps   xmm0, xmm0
0x1800c7e2e  movdqa  [rsp+0C98h+var_C58], xmm0
0x1800c7e34  lea     rdx, [rsp+0C98h+var_C58]
0x1800c7e39  lea     rcx, [rsp+0C98h+var_C48]
0x1800c7e3e  call    ??$MakeEnumSet@VPersistSyntheticOptions@Diagnostics@Microsoft@@@Enum@Utils@Diagnostics@Microsoft@@SA?AV?$bitset@$01@std@@V?$initializer_list@VPersistSyntheticOptions@Diagnostics@Microsoft@@@5@@Z; Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(std::initializer_list<Microsoft::Diagnostics::PersistSyntheticOptions>)
0x1800c7e43  mov     edx, [rax]
0x1800c7e45  lea     rcx, [rsp+0C98h+var_4C8]; this
0x1800c7e4d  call    ?PersistSyntheticEvent@AsimovEventSerializer@Diagnostics@Microsoft@@SAJAEAVAsimovSyntheticEvent@23@V?$bitset@$01@std@@@Z; Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent(Microsoft::Diagnostics::AsimovSyntheticEvent &,std::bitset<2>)
0x1800c7e52  mov     rcx, [rsp+0C98h]; this
0x1800c7e5a  test    eax, eax
0x1800c7e5c  jns     short loc_1800C7E72
0x1800c7e5e  mov     r9d, eax; char *
0x1800c7e61  lea     r8, aOnecoreBaseTel_274; "onecore\\base\\telemetry\\utc\\service"...
0x1800c7e68  mov     edx, 80Bh; void *
0x1800c7e6d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c7e72  mov     [r14+258h], r12w
0x1800c7e7a  inc     dword ptr [r14+25Ch]
0x1800c7e81  lea     rcx, [rsp+0C98h+lpFileName]
0x1800c7e89  cmp     [rsp+0C98h+var_A20], 7
0x1800c7e92  cmova   rcx, [rsp+0C98h+lpFileName]; lpFileName
0x1800c7e9b  call    cs:__imp_DeleteFileW
0x1800c7ea1  mov     rcx, [rsp+0C98h]; this
0x1800c7ea9  test    eax, eax
0x1800c7eab  jnz     short loc_1800C7EBE
0x1800c7ead  lea     r8, aOnecoreBaseTel_274; "onecore\\base\\telemetry\\utc\\service"...
0x1800c7eb4  mov     edx, 80Eh; void *
0x1800c7eb9  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800c7ebe  mov     ebx, dword ptr [rsp+0C98h+var_C28]
0x1800c7ec2  test    ebx, ebx
0x1800c7ec4  jns     short loc_1800C7EE3
0x1800c7ec6  mov     rcx, [rsp+0C98h]; this
0x1800c7ece  mov     r9d, ebx; char *
0x1800c7ed1  lea     r8, aOnecoreBaseTel_274; "onecore\\base\\telemetry\\utc\\service"...
0x1800c7ed8  mov     edx, 80Fh; void *
0x1800c7edd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7ee2  nop
0x1800c7ee3  lea     rcx, [rsp+0C98h+var_4C8]; this
0x1800c7eeb  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x1800c7ef0  nop
0x1800c7ef1  lea     rcx, [rsp+0C98h+var_C20]
0x1800c7ef6  call    ??1?$unique_storage@U?$resource_policy@_K$$A6AK_K@Z$1?CloseTrace@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,ulong (unsigned __int64),&CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,ulong (unsigned __int64),&CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>(void)
0x1800c7efb  nop
0x1800c7efc  lea     rcx, [rsp+0C98h+lpFileName]
0x1800c7f04  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c7f09  mov     eax, ebx
0x1800c7f0b  jmp     loc_1800C86D5
0x1800c7f10  lea     rsi, [r14+878h]
0x1800c7f17  mov     qword ptr [rsi+10h], 0
0x1800c7f1f  cmp     qword ptr [rsi+18h], 7
0x1800c7f24  jbe     short loc_1800C7F2B
0x1800c7f26  mov     rcx, [rsi]
0x1800c7f29  jmp     short loc_1800C7F2E
0x1800c7f2b  mov     rcx, rsi
0x1800c7f2e  xor     eax, eax
0x1800c7f30  mov     [rcx], ax
0x1800c7f33  mov     rdx, rdi
0x1800c7f36  lea     rcx, [rsp+0C98h+Src]
0x1800c7f3e  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1800c7f43  nop
0x1800c7f44  mov     r8d, 11h
0x1800c7f4a  mov     rdx, cs:?k_alternateStreamCVName@ETWConsumer@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::ETWConsumer::k_alternateStreamCVName
0x1800c7f51  lea     rcx, [rsp+0C98h+Src]; Src
0x1800c7f59  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800c7f5e  xorps   xmm0, xmm0
0x1800c7f61  movups  xmmword ptr [rsp+0C98h+lpNewFileName], xmm0
0x1800c7f69  mov     [rsp+0C98h+var_A08], 0
0x1800c7f75  mov     [rsp+0C98h+var_A00], 0Fh
0x1800c7f81  mov     byte ptr [rsp+0C98h+lpNewFileName], 0
0x1800c7f89  lea     rdx, [rsp+0C98h+var_C48]
0x1800c7f8e  lea     rcx, [rsp+0C98h+Src]
0x1800c7f96  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800c7f9b  movups  xmm0, xmmword ptr [rax]
0x1800c7f9e  movdqu  [rsp+0C98h+var_C58], xmm0
0x1800c7fa4  lea     r9, [rsp+0C98h+lpNewFileName]
0x1800c7fac  or      r8d, 0FFFFFFFFh
0x1800c7fb0  lea     rcx, [rsp+0C98h+var_C58]
0x1800c7fb5  call    ?ReadStringFromFile@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@KKAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; Microsoft::Diagnostics::Utils::FileSystem::ReadStringFromFile(std::wstring_view,ulong,ulong,std::string &)
0x1800c7fba  cmp     [rsp+0C98h+var_A08], 0
0x1800c7fc3  jz      short loc_1800C800A
0x1800c7fc5  lea     rdx, [rsp+0C98h+var_C48]
0x1800c7fca  lea     rcx, [rsp+0C98h+lpNewFileName]
0x1800c7fd2  call    ??B?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string_view@DU?$char_traits@D@std@@@1@XZ; std::string::operator std::string_view(void)
0x1800c7fd7  movups  xmm0, xmmword ptr [rax]
0x1800c7fda  movdqu  [rsp+0C98h+var_C58], xmm0
0x1800c7fe0  lea     rdx, [rsp+0C98h+var_C58]
0x1800c7fe5  lea     rcx, [rsp+0C98h+var_9B0]
0x1800c7fed  call    ?MultiByteStringToWideString@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::MultiByteStringToWideString(std::string_view,ulong)
0x1800c7ff2  mov     rdx, rax
0x1800c7ff5  mov     rcx, rsi
0x1800c7ff8  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800c7ffd  lea     rcx, [rsp+0C98h+var_9B0]
0x1800c8005  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c800a  xor     edx, edx; Val
0x1800c800c  lea     r8d, [rdx+40h]; Size
0x1800c8010  lea     rcx, [rsp+0C98h+var_9B0]; void *
0x1800c8018  call    memset_0
0x1800c801d  lea     rcx, [rsp+0C98h+var_9B0]; this
0x1800c8025  call    ??0EtlLogStats@ETWConsumer@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ETWConsumer::EtlLogStats::EtlLogStats(void)
0x1800c802a  nop
0x1800c802b  lea     r12, [r14+218h]
0x1800c8032  mov     rdx, rax
0x1800c8035  mov     rcx, r12
0x1800c8038  call    ??4EtlLogStats@ETWConsumer@Diagnostics@Microsoft@@QEAAAEAU0123@$$QEAU0123@@Z; Microsoft::Diagnostics::ETWConsumer::EtlLogStats::operator=(Microsoft::Diagnostics::ETWConsumer::EtlLogStats &&)
0x1800c803d  nop
0x1800c803e  mov     rcx, [rsp+0C98h+var_998]
0x1800c8046  test    rcx, rcx
0x1800c8049  jz      short loc_1800C807E
0x1800c804b  mov     rdx, [rsp+0C98h+var_988]
0x1800c8053  sub     rdx, rcx
0x1800c8056  mov     rax, 6666666666666667h
0x1800c8060  imul    rdx
0x1800c8063  sar     rdx, 3
0x1800c8067  mov     rax, rdx
0x1800c806a  shr     rax, 3Fh
0x1800c806e  add     rdx, rax
0x1800c8071  lea     rdx, [rdx+rdx*4]
0x1800c8075  shl     rdx, 2
0x1800c8079  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c807e  call    ?QueryUbiTime@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::QueryUbiTime(void)
0x1800c8083  mov     rsi, rax
0x1800c8086  mov     edx, cs:_tls_index
0x1800c808c  mov     rcx, gs:58h
0x1800c8095  mov     eax, 34h ; '4'
0x1800c809a  mov     rdx, [rcx+rdx*8]
0x1800c809e  mov     word ptr [rax+rdx], 0FFFFh
0x1800c80a4  mov     [rsp+0C98h+HandleArray], rbx
0x1800c80ac  xor     r9d, r9d; EndTime
0x1800c80af  xor     r8d, r8d; StartTime
0x1800c80b2  lea     edx, [r9+1]; HandleCount
0x1800c80b6  lea     rcx, [rsp+0C98h+HandleArray]; HandleArray
0x1800c80be  call    cs:__imp_ProcessTrace
0x1800c80c4  mov     ebx, eax
0x1800c80c6  test    eax, eax
0x1800c80c8  jle     short loc_1800C80D3
0x1800c80ca  movzx   ebx, ax
0x1800c80cd  or      ebx, 80070000h
0x1800c80d3  mov     eax, cs:dword_1804543B0
0x1800c80d9  cmp     eax, 4
0x1800c80dc  jbe     short loc_1800C8123
  ... truncated ...
```
