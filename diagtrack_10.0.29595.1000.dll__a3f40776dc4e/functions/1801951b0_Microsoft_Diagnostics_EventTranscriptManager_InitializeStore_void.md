# Microsoft::Diagnostics::EventTranscriptManager::InitializeStore(void)

- ea: `0x1801951b0`
- end: `0x180195b71`
- name: `?InitializeStore@EventTranscriptManager@Diagnostics@Microsoft@@AEAAJXZ`
- size: `2497`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::EventTranscriptManager *__hidden this)`
- caller_count: `1`
- callee_count: `43`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1803096c4`

## callees

- `0x1800029a8`
- `0x180013438`
- `0x18002b7c0`
- `0x18002df00`
- `0x180039e6c`
- `0x18004f6d0`
- `0x180050ce4`
- `0x1800520d8`
- `0x180055730`
- `0x180064e8c`
- `0x18006dd44`
- `0x18008a4ec`
- `0x18009c8c0`
- `0x1800e9a00`
- `0x1800fe234`
- `0x18010125c`
- `0x180102bbc`
- `0x18011c2ec`
- `0x180129fe0`
- `0x18012bea8`
- `0x18012ed60`
- `0x18013cca4`
- `0x180142fcc`
- `0x1801951b0`
- `0x1801b21e4`
- `0x1801b4dc4`
- `0x1801b5ef0`
- `0x1801ca5e0`
- `0x1801d32b4`
- `0x1801dd8c8`
- `0x1801ddb8c`
- `0x180206a14`
- `0x18020aac0`
- `0x1802b0d58`
- `0x180307080`
- `0x180307574`
- `0x180307a94`
- `0x180309808`
- `0x18030bb80`
- `0x18030c42c`
- `0x18030c6fc`
- `0x18030d494`
- `0x18030d6d8`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1801953a7`
- `msvcp_win!_Mtx_unlock` at `0x180195510`
- `msvcp_win!_Mtx_unlock` at `0x1801953a7`
- `msvcp_win!_Mtx_unlock` at `0x180195510`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18019534c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18019534c`

## string_xrefs

- `0x180195213`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1801952e9`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x180195419`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x18019545c`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x180195530`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x180195571`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x180195634`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x180195a0e`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x180195a4d`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x180195a89`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x180195ac8`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x180195b04`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1801959b9`: `CREATE TABLE IF NOT EXISTS events_persisted (\n                        sid                             TEXT,\n                        timestamp                       INTEGER,\n                        payload                         TEXT,\n                        full_event_name                 TEXT,\n                        full_event_name_hash            INTEGER,\n                        event_keywords                  INTEGER,\n                        is_core                         INTEGER,\n`
- `0x1801959c0`: `CREATE TABLE IF NOT EXISTS events_persisted (\n                        sid                             TEXT,\n                        timestamp                       INTEGER,\n                        payload                         TEXT,\n                        full_event_name                 TEXT,\n                        full_event_name_hash            INTEGER,\n                        event_keywords                  INTEGER,\n                        is_core                         INTEGER,\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Microsoft::Diagnostics::EventTranscriptManager::InitializeStore(
        Microsoft::Diagnostics::EventTranscriptManager *this,
        __int64 a2,
        int a3,
        int a4)
{
  Microsoft::Diagnostics::EventTranscriptManager *v4; // rdi
  __int64 result; // rax
  Microsoft::Diagnostics::SqlConnection **v7; // rsi
  Microsoft::Diagnostics::LifetimeManager *v8; // rcx
  Microsoft::Diagnostics::TelemetryAssert *TelemetryAssert; // rcx
  const char *v10; // r9
  const WCHAR *v11; // rcx
  Microsoft::Diagnostics::SqlConnection **v12; // r15
  __int64 v13; // rax
  wil *v14; // rcx
  int v15; // eax
  Microsoft::Diagnostics::SqlConnection *v16; // rdx
  int v17; // eax
  unsigned int v18; // r14d
  char v19; // r13
  __int64 v20; // rax
  int v21; // eax
  unsigned int v22; // r14d
  int v23; // eax
  unsigned int v24; // r14d
  __int64 v25; // rax
  __int128 *v26; // rax
  __int64 v27; // rax
  __int64 v28; // r15
  __int64 v29; // rax
  unsigned int v30; // eax
  unsigned __int64 v31; // r14
  const char *v32; // r9
  unsigned __int64 v33; // r12
  double v34; // xmm1_8
  double v35; // xmm0_8
  __int64 v36; // r15
  float v37; // xmm1_4
  float v38; // xmm0_4
  int v39; // ecx
  int v40; // r8d
  char IsEnabled; // al
  const char *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  unsigned int v45; // esi
  int v46; // eax
  unsigned int v47; // esi
  int v48; // eax
  unsigned int v49; // esi
  int v50; // eax
  unsigned int v51; // esi
  int v52; // eax
  unsigned int v53; // edi
  int v54; // edi
  Microsoft::Diagnostics::EventTranscriptManager *v55; // rbx
  __int64 v56; // rdx
  int v57; // eax
  unsigned int v58; // ebx
  int v59; // [rsp+20h] [rbp-1A8h]
  int v60; // [rsp+20h] [rbp-1A8h]
  unsigned int v61; // [rsp+30h] [rbp-198h] BYREF
  char v62; // [rsp+34h] [rbp-194h]
  const char *v63; // [rsp+40h] [rbp-188h] BYREF
  __int64 v64; // [rsp+48h] [rbp-180h]
  __int128 v65; // [rsp+60h] [rbp-168h] BYREF
  unsigned __int64 v66[2]; // [rsp+70h] [rbp-158h] BYREF
  const char *v67; // [rsp+80h] [rbp-148h] BYREF
  Microsoft::Diagnostics::EventTranscriptManager *v68; // [rsp+88h] [rbp-140h]
  _BYTE v69[32]; // [rsp+90h] [rbp-138h] BYREF
  _BYTE v70[32]; // [rsp+B0h] [rbp-118h] BYREF
  _BYTE v71[16]; // [rsp+D0h] [rbp-F8h] BYREF
  LPCWSTR pszPath[4]; // [rsp+E0h] [rbp-E8h] BYREF
  _BYTE v73[48]; // [rsp+100h] [rbp-C8h] BYREF
  _BYTE v74[48]; // [rsp+130h] [rbp-98h] BYREF
  _BYTE v75[48]; // [rsp+160h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  v4 = this;
  v68 = this;
  if ( *((_BYTE *)this + 1981) )
    gsl::details::terminate(this);
  if ( !*((_BYTE *)this + 1980) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8F8,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
      (const char *)0x80070426LL,
      v60);
    return 2147943462LL;
  }
  try
  {
    v7 = (Microsoft::Diagnostics::SqlConnection **)((char *)this + 2272);
    if ( *((_QWORD *)this + 284) )
    {
      if ( (unsigned int)dword_1804543B0 > 2 )
      {
        v67 = "InitializeStore";
        v66[0] = (unsigned __int64)"m_dbPersistConnection == nullptr";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)this,
          (unsigned int)byte_180401825,
          a3,
          a4,
          (__int64)v66,
          (__int64)&v67);
      }
      if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
      {
        TelemetryAssert = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(v8);
        Microsoft::Diagnostics::TelemetryAssert::Assert(TelemetryAssert);
      }
      if ( *v7 )
      {
        if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x100000) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_1804543B0,
            byte_1804017A1);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x902,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)0x8000FFFFLL,
          v60);
        return 2147549183LL;
      }
    }
    Microsoft::Diagnostics::EventTranscriptManager::GetTranscriptFilePathExpanded(v4, v71);
    std::wstring::wstring(pszPath);
    v11 = (const WCHAR *)pszPath;
    if ( pszPath[3] > (LPCWSTR)7 )
      v11 = pszPath[0];
    v67 = (const char *)v7;
    v12 = v7;
    *(_QWORD *)&v65 = v7;
    if ( PathFileExistsW(v11) )
    {
      try
      {
        v61 = 65792;
        v63 = (char *)v4 + 2192;
        std::_Mutex_base::lock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)v4 + 2192));
        v13 = std::make_unique<Microsoft::Diagnostics::SqlConnection,std::wstring &,Microsoft::Diagnostics::SqlConnection::Options &,0>(
                v66,
                pszPath,
                &v61);
        std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::operator=<std::default_delete<Microsoft::Diagnostics::SqlConnection>,0>(
          v7,
          v13);
        std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::~unique_ptr<Microsoft::Diagnostics::SqlConnection>(v66);
        _Mtx_unlock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)v4 + 2192));
      }
      catch ( ... )
      {
        v54 = wil::ResultFromCaughtException(v14);
        v61 = v54;
        v55 = v68;
        std::_Mutex_base::lock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)v68 + 2192));
        v56 = *((_QWORD *)v55 + 284);
        *((_QWORD *)v55 + 284) = 0;
        if ( v56 )
          std::default_delete<Microsoft::Diagnostics::SqlConnection>::operator()();
        _Mtx_unlock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)v55 + 2192));
        v57 = Microsoft::Diagnostics::EventTranscriptManager::TryDeleteStoreFiles(v55);
        v58 = v57;
        if ( v57 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x91D,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
            (const char *)(unsigned int)v57,
            v59);
          v61 = v58;
          goto LABEL_77;
        }
        if ( v54 >= 0 )
        {
          v12 = (Microsoft::Diagnostics::SqlConnection **)v65;
          v7 = (Microsoft::Diagnostics::SqlConnection **)v65;
          v4 = v68;
          goto LABEL_18;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x91F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v54,
          v59);
LABEL_77:
        std::wstring::_Tidy_deallocate(pszPath);
        return v61;
      }
LABEL_18:
      Microsoft::Diagnostics::SqlConnection::UpdateWalJournalSize(*v7, 0, 0x3E8u);
      v15 = Microsoft::Diagnostics::EventTranscriptManager::VerifyStoreConfiguration(v4);
      if ( v15 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x925,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v15,
          v60);
        Microsoft::Diagnostics::EventTranscriptManager::FinalizeStatements(v4);
        v16 = *v7;
        *v7 = 0;
        if ( v16 )
          std::default_delete<Microsoft::Diagnostics::SqlConnection>::operator()();
        v17 = Microsoft::Diagnostics::EventTranscriptManager::TryDeleteStoreFiles(v4);
        v18 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x92A,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
            (const char *)(unsigned int)v17,
            v60);
          std::wstring::_Tidy_deallocate(pszPath);
          return v18;
        }
        if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x100000) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_1804543B0,
            &word_180401666);
      }
    }
    if ( *v7 )
    {
      v19 = 0;
    }
    else
    {
      v61 = 65793;
      v63 = (char *)v4 + 2192;
      std::_Mutex_base::lock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)v4 + 2192));
      v20 = std::make_unique<Microsoft::Diagnostics::SqlConnection,std::wstring &,Microsoft::Diagnostics::SqlConnection::Options &,0>(
              &v65,
              pszPath,
              &v61);
      std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::operator=<std::default_delete<Microsoft::Diagnostics::SqlConnection>,0>(
        v12,
        v20);
      std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::~unique_ptr<Microsoft::Diagnostics::SqlConnection>(&v65);
      _Mtx_unlock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)v4 + 2192));
      v21 = Microsoft::Diagnostics::EventTranscriptManager::SetNewStoreConfiguration(v4);
      v22 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x941,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v21,
          v60);
        std::wstring::_Tidy_deallocate(pszPath);
        return v22;
      }
      v23 = Microsoft::Diagnostics::EventTranscriptManager::VerifyStoreConfiguration(v4);
      v24 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x942,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v23,
          v60);
        std::wstring::_Tidy_deallocate(pszPath);
        return v24;
      }
      v19 = 1;
    }
    v62 = v19;
    v65 = *(_OWORD *)std::wstring::operator std::wstring_view(qword_1804634C0, v66);
    v63 = "PRAGMA page_size;";
    v64 = 17;
    Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v73, *v7, &v63, &v65);
    v25 = Microsoft::Diagnostics::SqliteStatement::Bind<>(v73, &v63);
    Microsoft::Diagnostics::SqliteBoundStatement::Step(v25, v69);
    std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(&v63);
    if ( !v69[24] )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x94E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
        (const char *)0x8000FFFFLL,
        v60);
      std::optional<Microsoft::Diagnostics::SqliteQueryResult>::~optional<Microsoft::Diagnostics::SqliteQueryResult>(v69);
      Microsoft::Diagnostics::SqliteStatement::~SqliteStatement((Microsoft::Diagnostics::SqliteStatement *)v73);
      std::wstring::_Tidy_deallocate(pszPath);
      return 2147549183LL;
    }
    *((_DWORD *)v4 + 384) = Microsoft::Diagnostics::SqliteQueryResult::Next<long>(v69);
    std::optional<Microsoft::Diagnostics::SqliteQueryResult>::~optional<Microsoft::Diagnostics::SqliteQueryResult>(v69);
    Microsoft::Diagnostics::SqliteStatement::~SqliteStatement((Microsoft::Diagnostics::SqliteStatement *)v73);
    if ( !v19 )
    {
      v26 = (__int128 *)std::wstring::operator std::wstring_view(qword_1804634C0, v66);
      try
      {
        v65 = *v26;
        v63 = "PRAGMA page_count;";
        v64 = 18;
        Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v75, *v7, &v63, &v65);
        v27 = Microsoft::Diagnostics::SqliteStatement::Bind<>(v75, v69);
        Microsoft::Diagnostics::SqliteBoundStatement::Step(v27, v73);
        std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(v69);
        v28 = Microsoft::Diagnostics::SqliteQueryResult::Next<unsigned __int64>(v73);
        v65 = *(_OWORD *)std::wstring::operator std::wstring_view(qword_1804634C0, v66);
        v63 = "PRAGMA freelist_count;";
        v64 = 22;
        Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v74, *v7, &v63, &v65);
        v29 = Microsoft::Diagnostics::SqliteStatement::Bind<>(v74, v69);
        Microsoft::Diagnostics::SqliteBoundStatement::Step(v29, v70);
        std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(v69);
        *(_QWORD *)&v65 = Microsoft::Diagnostics::SqliteQueryResult::Next<unsigned __int64>(v70);
        std::optional<Microsoft::Diagnostics::SqliteQueryResult>::~optional<Microsoft::Diagnostics::SqliteQueryResult>(v70);
        Microsoft::Diagnostics::SqliteStatement::~SqliteStatement((Microsoft::Diagnostics::SqliteStatement *)v74);
        std::optional<Microsoft::Diagnostics::SqliteQueryResult>::~optional<Microsoft::Diagnostics::SqliteQueryResult>(v73);
        Microsoft::Diagnostics::SqliteStatement::~SqliteStatement((Microsoft::Diagnostics::SqliteStatement *)v75);
        v61 = *((_DWORD *)v4 + 384);
        v30 = Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get((char *)v4 + 1296);
        if ( v30 < 0x80 )
          v30 = 128;
        v31 = (unsigned __int64)v30 << 20;
        v66[0] = 0;
        Microsoft::Diagnostics::EventTranscriptManager::GetStoreFileSize(v4, v66);
        v33 = v66[0];
        if ( (v66[0] & 0x8000000000000000uLL) != 0LL )
          v34 = (double)(int)(v66[0] & 1 | (v66[0] >> 1)) + (double)(int)(v66[0] & 1 | (v66[0] >> 1));
        else
          v34 = (double)SLODWORD(v66[0]);
        if ( (v31 & 0x8000000000000000uLL) != 0LL )
          v35 = (double)(int)(v31 & 1 | (v31 >> 1)) + (double)(int)(v31 & 1 | (v31 >> 1));
        else
          v35 = (double)(int)v31;
        if ( v34 > v35 * 1.03 )
        {
          v36 = v61 * (v28 - v65);
          v37 = v36 < 0
              ? (float)(v36 & 1 | (unsigned int)((unsigned __int64)v36 >> 1))
              + (float)(v36 & 1 | (unsigned int)((unsigned __int64)v36 >> 1))
              : (float)(int)v36;
          v38 = (v31 & 0x8000000000000000uLL) != 0LL
              ? (float)(int)(v31 & 1 | (v31 >> 1)) + (float)(int)(v31 & 1 | (v31 >> 1))
              : (float)(int)v31;
          if ( (float)((float)(v38 / 100.0) * 80.0) > v37 )
          {
            v63 = "VACUUM;";
            v64 = 7;
            Microsoft::Diagnostics::SqlConnection::Exec(*v7, &v63);
            if ( (unsigned int)dword_1804543B0 > 5 )
            {
              if ( (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x100000) )
              {
                *(_QWORD *)&v65 = v31;
                v66[0] = v33;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                  v39,
                  (unsigned int)&unk_1804016D0,
                  v40,
                  (_DWORD)v32,
                  (__int64)v66,
                  (__int64)&v65);
              }
            }
          }
        }
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x986,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          v32);
        if ( (unsigned int)dword_1804543B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x100000) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_1804543B0,
            &byte_180401737);
        v19 = v62;
        v7 = (Microsoft::Diagnostics::SqlConnection **)v67;
        v4 = v68;
      }
    }
    v63 = "PRAGMA foreign_keys = ON";
    v64 = 24;
    Microsoft::Diagnostics::SqlConnection::Exec(*v7, &v63);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_DmaUtcUpdate>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DmaUtcUpdate>::GetImpl'::`2'::impl);
    v42 = "CREATE TABLE IF NOT EXISTS events_persisted (\n"
          "                        sid                             TEXT,\n"
          "                        timestamp                       INTEGER,\n"
          "                        payload                         TEXT,\n"
          "                        full_event_name                 TEXT,\n"
          "                        full_event_name_hash            INTEGER,\n"
          "                        event_keywords                  INTEGER,\n"
          "                        is_core                         INTEGER,\n"
          "                        provider_group_id               INTEGER,\n"
          "                        logging_binary_name             TEXT,\n"
          "                        friendly_logging_binary_name    TEXT,\n"
          "                        compressed_payload_size         INTEGER,\n"
          "                        producer_id                     INTEGER,\n"
          "                        extra1                          TEXT,\n"
          "                        extra2                          TEXT,\n"
          "                        extra3                          TEXT,\n"
          "                        FOREIGN KEY(provider_group_id)  REFERENCES provider_groups(group_id),\n"
          "                        CONSTRAINT fk_producer_id\n"
          "                            FOREIGN KEY(producer_id)\n"
          "                            REFERENCES producers(producer_id)\n"
          "                            ON DELETE CASCADE);\n"
          "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_sid ON events_persisted(sid);\n"
          "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_full_event_name_hash ON events_persisted(f"
          "ull_event_name_hash);\n"
          "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_timestamp ON events_persisted(timestamp);\n"
          "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_logging_binary_name ON events_persisted(lo"
          "gging_binary_name);\n"
          "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_producer_id ON events_persisted(producer_i"
          "d);\n"
          "                    CREATE TABLE IF NOT EXISTS provider_groups (\n"
          "                        group_id                        INTEGER PRIMARY KEY AUTOINCREMENT,\n"
          "                        group_guid                      TEXT);\n"
          "                    CREATE TABLE IF NOT EXISTS event_tags (\n"
          "                        full_event_name_hash            INTEGER,\n"
          "                        tag_id                          INTEGER);\n"
          "                    CREATE INDEX IF NOT EXISTS idx_event_tags_full_event_name_hash ON event_tags(full_event_na"
          "me_hash);\n"
          "                    CREATE TABLE IF NOT EXISTS tag_descriptions (\n"
          "                        tag_id                          INTEGER,\n"
          "                        locale_name                     TEXT,\n"
          "                        tag_name                        TEXT,\n"
          "                        description                     TEXT);\n"
          "                    CREATE TABLE IF NOT EXISTS producers (\n"
          "                        producer_id                     INTEGER PRIMARY KEY,\n"
          "                        producer_id_name                TEXT);\n"
          "                    CREATE TABLE IF NOT EXISTS event_categories (\n"
          "                        full_event_name_hash            INTEGER,\n"
          "                        category_id                     INTEGER,\n"
          "                        CONSTRAINT fk_category_id\n"
          "                            FOREIGN KEY(category_id)\n"
          "                            REFERENCES categories(category_id)\n"
          "                            ON DELETE CASCADE);\n"
          "                    CREATE INDEX IF NOT EXISTS idx_event_categories_full_event_name_hash ON event_categories(f"
          "ull_event_name_hash);\n"
          "                    CREATE TABLE IF NOT EXISTS categories (\n"
          "                        category_id                     INTEGER PRIMARY KEY AUTOINCREMENT,\n"
          "                        category_id_text                TEXT,\n"
          "                        producer_id                     INTEGER,\n"
          "                        CONSTRAINT fk_producer_id\n"
          "                            FOREIGN KEY(producer_id)\n"
          "                            REFERENCES producers(producer_id)\n"
          "                            ON DELETE CASCADE);\n"
          "                    ";
    if ( !IsEnabled )
      v42 = "CREATE TABLE IF NOT EXISTS events_persisted (\n"
            "                        sid                             TEXT,\n"
            "                        timestamp                       INTEGER,\n"
            "                        payload                         TEXT,\n"
            "                        full_event_name                 TEXT,\n"
            "                        full_event_name_hash            INTEGER,\n"
            "                        event_keywords                  INTEGER,\n"
            "                        is_core                         INTEGER,\n"
            "                        provider_group_id               INTEGER,\n"
            "                        logging_binary_name             TEXT,\n"
            "                        friendly_logging_binary_name    TEXT,\n"
            "                        compressed_payload_size         INTEGER,\n"
            "                        producer_id                     INTEGER,\n"
            "                        extra1                          TEXT,\n"
            "                        extra2                          TEXT,\n"
            "                        extra3                          TEXT,\n"
            "                        FOREIGN KEY(provider_group_id)  REFERENCES provider_groups(group_id),\n"
            "                        CONSTRAINT fk_producer_id\n"
            "                            FOREIGN KEY(producer_id)\n"
            "                            REFERENCES producers(producer_id)\n"
            "                            ON DELETE CASCADE);\n"
            "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_sid ON events_persisted(sid);\n"
            "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_full_event_name_hash ON events_persisted"
            "(full_event_name_hash);\n"
            "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_timestamp ON events_persisted(timestamp)"
            ";\n"
            "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_logging_binary_name ON events_persisted("
            "logging_binary_name);\n"
            "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_producer_id ON events_persisted(producer"
            "_id);\n"
            "                    CREATE TABLE IF NOT EXISTS provider_groups (\n"
            "                        group_id                        INTEGER PRIMARY KEY AUTOINCREMENT,\n"
            "                        group_guid                      TEXT);\n"
            "                    CREATE TABLE IF NOT EXISTS event_tags (\n"
            "                        full_event_name_hash            INTEGER,\n"
            "                        tag_id                          INTEGER);\n"
            "                    CREATE INDEX IF NOT EXISTS idx_event_tags_full_event_name_hash ON event_tags(full_event_"
            "name_hash);\n"
            "                    CREATE TABLE IF NOT EXISTS tag_descriptions (\n"
            "                        tag_id                          INTEGER,\n"
            "                        locale_name                     TEXT,\n"
            "                        tag_name                        TEXT,\n"
            "                        description                     TEXT);\n"
            "                    CREATE TABLE IF NOT EXISTS producers (\n"
            "                        producer_id                     INTEGER PRIMARY KEY AUTOINCREMENT,\n"
            "                        producer_id_text                TEXT);\n"
            "                    CREATE TABLE IF NOT EXISTS event_categories (\n"
            "                        full_event_name_hash            INTEGER,\n"
            "                        category_id                     INTEGER,\n"
            "                        CONSTRAINT fk_category_id\n"
            "                            FOREIGN KEY(category_id)\n"
            "                            REFERENCES categories(category_id)\n"
            "                            ON DELETE CASCADE);\n"
            "                    CREATE INDEX IF NOT EXISTS idx_event_categories_full_event_name_hash ON event_categories"
            "(full_event_name_hash);\n"
            "                    CREATE TABLE IF NOT EXISTS categories (\n"
            "                        category_id                     INTEGER PRIMARY KEY AUTOINCREMENT,\n"
            "                        category_id_text                TEXT,\n"
            "                        producer_id                     INTEGER,\n"
            "                        CONSTRAINT fk_producer_id\n"
            "                            FOREIGN KEY(producer_id)\n"
            "                            REFERENCES producers(producer_id)\n"
            "                            ON DELETE CASCADE);\n"
            "                    ";
    v43 = -1;
    do
      ++v43;
    while ( v42[v43] );
    v63 = v42;
    v64 = v43;
    Microsoft::Diagnostics::SqlConnection::Exec(*v7, &v63);
    if ( v19 )
    {
      v44 = Microsoft::Diagnostics::EventTranscriptManager::PrePopulateProviderGroups(v4);
      v45 = v44;
      if ( v44 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA0C,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v44,
          v60);
        std::wstring::_Tidy_deallocate(pszPath);
        return v45;
      }
      v46 = Microsoft::Diagnostics::EventTranscriptManager::PrePopulateProducers(v4);
      v47 = v46;
      if ( v46 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA0D,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v46,
          v60);
        std::wstring::_Tidy_deallocate(pszPath);
        return v47;
      }
    }
    else
    {
      v48 = Microsoft::Diagnostics::EventTranscriptManager::CacheCategoryIds(v4);
      v49 = v48;
      if ( v48 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA12,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v48,
          v60);
        std::wstring::_Tidy_deallocate(pszPath);
        return v49;
      }
    }
    v50 = Microsoft::Diagnostics::EventTranscriptManager::CacheGroupIds(v4);
    v51 = v50;
    if ( v50 >= 0 )
    {
      v52 = Microsoft::Diagnostics::EventTranscriptManager::CacheProducerIds(v4);
      v53 = v52;
      if ( v52 >= 0 )
      {
        std::wstring::_Tidy_deallocate(pszPath);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA16,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v52,
          v60);
        std::wstring::_Tidy_deallocate(pszPath);
        result = v53;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
        (const char *)(unsigned int)v50,
        v60);
      std::wstring::_Tidy_deallocate(pszPath);
      result = v51;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA18,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1801951b0  mov     [rsp+arg_8], rbx
0x1801951b5  mov     [rsp+arg_10], rsi
0x1801951ba  push    rdi
0x1801951bb  push    r12
0x1801951bd  push    r13
0x1801951bf  push    r14
0x1801951c1  push    r15
0x1801951c3  sub     rsp, 1A0h
0x1801951ca  mov     rax, cs:__security_cookie
0x1801951d1  xor     rax, rsp
0x1801951d4  mov     [rsp+1C8h+var_38], rax
0x1801951dc  mov     rdi, rcx
0x1801951df  mov     [rsp+1C8h+var_140], rcx
0x1801951e7  mov     al, [rcx+7BDh]
0x1801951ed  nop
0x1801951ee  xor     ebx, ebx
0x1801951f0  test    al, al
0x1801951f2  jnz     loc_180195B6A
0x1801951f8  mov     al, [rcx+7BCh]
0x1801951fe  nop
0x1801951ff  test    al, al
0x180195201  jnz     short loc_18019522B
0x180195203  mov     rcx, [rsp+1C8h]; this
0x18019520b  mov     ebx, 80070426h
0x180195210  mov     r9d, ebx; char *
0x180195213  lea     r8, aOnecoreBaseTel_213; "onecore\\base\\telemetry\\utc\\service"...
0x18019521a  mov     edx, 8F8h; void *
0x18019521f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195224  mov     eax, ebx
0x180195226  jmp     loc_180195B37
0x18019522b  lea     rsi, [rcx+8E0h]
0x180195232  cmp     [rsi], rbx
0x180195235  jz      loc_180195301
0x18019523b  mov     eax, cs:dword_1804543B0
0x180195241  cmp     eax, 2
0x180195244  jbe     short loc_180195284
0x180195246  lea     rax, aInitializestor; "InitializeStore"
0x18019524d  mov     [rsp+1C8h+var_148], rax
0x180195255  lea     rax, aMDbpersistconn; "m_dbPersistConnection == nullptr"
0x18019525c  mov     [rsp+1C8h+var_158], rax
0x180195261  lea     rax, [rsp+1C8h+var_148]
0x180195269  mov     [rsp+1C8h+var_1A0], rax
0x18019526e  lea     rax, [rsp+1C8h+var_158]
0x180195273  mov     qword ptr [rsp+1C8h+var_1A8], rax; int
0x180195278  lea     rdx, byte_180401825
0x18019527f  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180195284  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18019528b  call    ?IsTelemetryAssertReady@LifetimeManager@Diagnostics@Microsoft@@QEAA_NXZ; Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady(void)
0x180195290  test    al, al
0x180195292  jz      short loc_1801952A1
0x180195294  call    ?GetTelemetryAssert@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTelemetryAssert@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(void)
0x180195299  mov     rcx, rax; this
0x18019529c  call    ?Assert@TelemetryAssert@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::TelemetryAssert::Assert(void)
0x1801952a1  cmp     [rsi], rbx
0x1801952a4  jz      short loc_180195301
0x1801952a6  mov     eax, cs:dword_1804543B0
0x1801952ac  cmp     eax, 5
0x1801952af  jbe     short loc_1801952D9
0x1801952b1  mov     edx, 100000h
0x1801952b6  lea     rcx, dword_1804543B0
0x1801952bd  call    _tlgKeywordOn
0x1801952c2  test    al, al
0x1801952c4  jz      short loc_1801952D9
0x1801952c6  lea     rdx, byte_1804017A1
0x1801952cd  lea     rcx, dword_1804543B0
0x1801952d4  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801952d9  mov     rcx, [rsp+1C8h]; this
0x1801952e1  mov     ebx, 8000FFFFh
0x1801952e6  mov     r9d, ebx; char *
0x1801952e9  lea     r8, aOnecoreBaseTel_213; "onecore\\base\\telemetry\\utc\\service"...
0x1801952f0  mov     edx, 902h; void *
0x1801952f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801952fa  mov     eax, ebx
0x1801952fc  jmp     loc_180195B37
0x180195301  lea     rdx, [rsp+1C8h+var_F8]
0x180195309  mov     rcx, rdi
0x18019530c  call    ?GetTranscriptFilePathExpanded@EventTranscriptManager@Diagnostics@Microsoft@@AEAA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; Microsoft::Diagnostics::EventTranscriptManager::GetTranscriptFilePathExpanded(void)
0x180195311  mov     rdx, rax
0x180195314  lea     rcx, [rsp+1C8h+pszPath]
0x18019531c  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x180195321  nop
0x180195322  lea     rcx, [rsp+1C8h+pszPath]
0x18019532a  cmp     [rsp+1C8h+var_D0], 7
0x180195333  cmova   rcx, [rsp+1C8h+pszPath]; pszPath
0x18019533c  mov     [rsp+1C8h+var_148], rsi
0x180195344  mov     r15, rsi
0x180195347  mov     qword ptr [rsp+1C8h+var_168], rsi
0x18019534c  call    cs:__imp_PathFileExistsW
0x180195352  test    eax, eax
0x180195354  jz      loc_1801954B6
0x18019535a  mov     [rsp+1C8h+var_198], 10100h
0x180195362  lea     r14, [rdi+890h]
0x180195369  mov     [rsp+1C8h+var_188], r14
0x18019536e  mov     rcx, r14; this
0x180195371  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180195376  nop
0x180195377  lea     r8, [rsp+1C8h+var_198]
0x18019537c  lea     rdx, [rsp+1C8h+pszPath]
0x180195384  lea     rcx, [rsp+1C8h+var_158]
0x180195389  call    ??$make_unique@VSqlConnection@Diagnostics@Microsoft@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAUOptions@123@$0A@@std@@YA?AV?$unique_ptr@VSqlConnection@Diagnostics@Microsoft@@U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEAUOptions@SqlConnection@Diagnostics@Microsoft@@@Z; std::make_unique<Microsoft::Diagnostics::SqlConnection,std::wstring &,Microsoft::Diagnostics::SqlConnection::Options &,0>(std::wstring &,Microsoft::Diagnostics::SqlConnection::Options &)
0x18019538e  mov     rdx, rax
0x180195391  mov     rcx, rsi
0x180195394  call    ??$?4U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@$0A@@?$unique_ptr@VSqlConnection@Diagnostics@Microsoft@@U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::operator=<std::default_delete<Microsoft::Diagnostics::SqlConnection>,0>(std::unique_ptr<Microsoft::Diagnostics::SqlConnection> &&)
0x180195399  lea     rcx, [rsp+1C8h+var_158]
0x18019539e  call    ??1?$unique_ptr@VSqlConnection@Diagnostics@Microsoft@@U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::~unique_ptr<Microsoft::Diagnostics::SqlConnection>(void)
0x1801953a3  nop
0x1801953a4  mov     rcx, r14; _Mtx_t
0x1801953a7  call    cs:__imp__Mtx_unlock
0x1801953ad  nop
0x1801953ae  jmp     short loc_1801953EE
0x1801953b0  lea     rcx, [rsp+1C8h+pszPath]
0x1801953b8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801953bd  mov     eax, [rsp+1C8h+var_198]
0x1801953c1  jmp     loc_180195B37
0x1801953c6  lea     rcx, [rsp+1C8h+pszPath]
0x1801953ce  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801953d3  mov     eax, [rsp+1C8h+var_198]
0x1801953d7  jmp     loc_180195B37
0x1801953dc  xor     ebx, ebx
0x1801953de  mov     r15, qword ptr [rsp+1C8h+var_168]
0x1801953e3  mov     rsi, r15
0x1801953e6  mov     rdi, [rsp+1C8h+var_140]
0x1801953ee  xor     edx, edx; unsigned int
0x1801953f0  mov     r8d, 3E8h; unsigned int
0x1801953f6  mov     rcx, [rsi]; this
0x1801953f9  call    ?UpdateWalJournalSize@SqlConnection@Diagnostics@Microsoft@@QEAAXKK@Z; Microsoft::Diagnostics::SqlConnection::UpdateWalJournalSize(ulong,ulong)
0x1801953fe  mov     rcx, rdi; this
0x180195401  call    ?VerifyStoreConfiguration@EventTranscriptManager@Diagnostics@Microsoft@@AEBAJXZ; Microsoft::Diagnostics::EventTranscriptManager::VerifyStoreConfiguration(void)
0x180195406  mov     rcx, [rsp+1C8h]; this
0x18019540e  test    eax, eax
0x180195410  jns     loc_1801954B6
0x180195416  mov     r9d, eax; char *
0x180195419  lea     r8, aOnecoreBaseTel_213; "onecore\\base\\telemetry\\utc\\service"...
0x180195420  mov     edx, 925h; void *
0x180195425  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18019542a  mov     rcx, rdi; this
0x18019542d  call    ?FinalizeStatements@EventTranscriptManager@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::EventTranscriptManager::FinalizeStatements(void)
0x180195432  mov     rdx, [rsi]
0x180195435  mov     [rsi], rbx
0x180195438  test    rdx, rdx
0x18019543b  jz      short loc_180195442
0x18019543d  call    ??R?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@QEBAXPEAVSqlConnection@Diagnostics@Microsoft@@@Z; std::default_delete<Microsoft::Diagnostics::SqlConnection>::operator()(Microsoft::Diagnostics::SqlConnection *)
0x180195442  mov     rcx, rdi; this
0x180195445  call    ?TryDeleteStoreFiles@EventTranscriptManager@Diagnostics@Microsoft@@AEAAJXZ; Microsoft::Diagnostics::EventTranscriptManager::TryDeleteStoreFiles(void)
0x18019544a  mov     r14d, eax
0x18019544d  test    eax, eax
0x18019544f  jns     short loc_180195483
0x180195451  mov     rcx, [rsp+1C8h]; this
0x180195459  mov     r9d, eax; char *
0x18019545c  lea     r8, aOnecoreBaseTel_213; "onecore\\base\\telemetry\\utc\\service"...
0x180195463  mov     edx, 92Ah; void *
0x180195468  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019546d  nop
0x18019546e  lea     rcx, [rsp+1C8h+pszPath]
0x180195476  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019547b  mov     eax, r14d
0x18019547e  jmp     loc_180195B37
0x180195483  mov     eax, cs:dword_1804543B0
0x180195489  cmp     eax, 5
0x18019548c  jbe     short loc_1801954B6
0x18019548e  mov     edx, 100000h
0x180195493  lea     rcx, dword_1804543B0
0x18019549a  call    _tlgKeywordOn
0x18019549f  test    al, al
0x1801954a1  jz      short loc_1801954B6
0x1801954a3  lea     rdx, word_180401666
0x1801954aa  lea     rcx, dword_1804543B0
0x1801954b1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801954b6  cmp     [rsi], rbx
0x1801954b9  jz      short loc_1801954C3
0x1801954bb  mov     r13b, bl
0x1801954be  jmp     loc_18019559B
0x1801954c3  mov     [rsp+1C8h+var_198], 10101h
0x1801954cb  lea     r14, [rdi+890h]
0x1801954d2  mov     [rsp+1C8h+var_188], r14
0x1801954d7  mov     rcx, r14; this
0x1801954da  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801954df  nop
0x1801954e0  lea     r8, [rsp+1C8h+var_198]
0x1801954e5  lea     rdx, [rsp+1C8h+pszPath]
0x1801954ed  lea     rcx, [rsp+1C8h+var_168]
0x1801954f2  call    ??$make_unique@VSqlConnection@Diagnostics@Microsoft@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAUOptions@123@$0A@@std@@YA?AV?$unique_ptr@VSqlConnection@Diagnostics@Microsoft@@U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEAUOptions@SqlConnection@Diagnostics@Microsoft@@@Z; std::make_unique<Microsoft::Diagnostics::SqlConnection,std::wstring &,Microsoft::Diagnostics::SqlConnection::Options &,0>(std::wstring &,Microsoft::Diagnostics::SqlConnection::Options &)
0x1801954f7  mov     rdx, rax
0x1801954fa  mov     rcx, r15
0x1801954fd  call    ??$?4U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@$0A@@?$unique_ptr@VSqlConnection@Diagnostics@Microsoft@@U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::operator=<std::default_delete<Microsoft::Diagnostics::SqlConnection>,0>(std::unique_ptr<Microsoft::Diagnostics::SqlConnection> &&)
0x180195502  lea     rcx, [rsp+1C8h+var_168]
0x180195507  call    ??1?$unique_ptr@VSqlConnection@Diagnostics@Microsoft@@U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::~unique_ptr<Microsoft::Diagnostics::SqlConnection>(void)
0x18019550c  nop
0x18019550d  mov     rcx, r14; _Mtx_t
0x180195510  call    cs:__imp__Mtx_unlock
0x180195516  mov     rcx, rdi; this
0x180195519  call    ?SetNewStoreConfiguration@EventTranscriptManager@Diagnostics@Microsoft@@AEBAJXZ; Microsoft::Diagnostics::EventTranscriptManager::SetNewStoreConfiguration(void)
0x18019551e  mov     r14d, eax
0x180195521  test    eax, eax
0x180195523  jns     short loc_180195557
0x180195525  mov     rcx, [rsp+1C8h]; this
0x18019552d  mov     r9d, eax; char *
0x180195530  lea     r8, aOnecoreBaseTel_213; "onecore\\base\\telemetry\\utc\\service"...
0x180195537  mov     edx, 941h; void *
0x18019553c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195541  nop
0x180195542  lea     rcx, [rsp+1C8h+pszPath]
0x18019554a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019554f  mov     eax, r14d
0x180195552  jmp     loc_180195B37
0x180195557  mov     rcx, rdi; this
0x18019555a  call    ?VerifyStoreConfiguration@EventTranscriptManager@Diagnostics@Microsoft@@AEBAJXZ; Microsoft::Diagnostics::EventTranscriptManager::VerifyStoreConfiguration(void)
0x18019555f  mov     r14d, eax
0x180195562  test    eax, eax
0x180195564  jns     short loc_180195598
0x180195566  mov     rcx, [rsp+1C8h]; this
0x18019556e  mov     r9d, eax; char *
0x180195571  lea     r8, aOnecoreBaseTel_213; "onecore\\base\\telemetry\\utc\\service"...
0x180195578  mov     edx, 942h; void *
0x18019557d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195582  nop
0x180195583  lea     rcx, [rsp+1C8h+pszPath]
0x18019558b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180195590  mov     eax, r14d
0x180195593  jmp     loc_180195B37
0x180195598  mov     r13b, 1
0x18019559b  mov     [rsp+1C8h+var_194], r13b
0x1801955a0  lea     rdx, [rsp+1C8h+var_158]
0x1801955a5  lea     r14, qword_1804634C0
0x1801955ac  mov     rcx, r14
0x1801955af  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801955b4  movups  xmm0, xmmword ptr [rax]
0x1801955b7  movdqu  [rsp+1C8h+var_168], xmm0
0x1801955bd  lea     rax, aPragmaPageSize; "PRAGMA page_size;"
0x1801955c4  mov     [rsp+1C8h+var_188], rax
0x1801955c9  mov     [rsp+1C8h+var_180], 11h
0x1801955d2  lea     r9, [rsp+1C8h+var_168]
0x1801955d7  lea     r8, [rsp+1C8h+var_188]
0x1801955dc  mov     rdx, [rsi]
0x1801955df  lea     rcx, [rsp+1C8h+var_C8]
0x1801955e7  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x1801955ec  nop
0x1801955ed  lea     rdx, [rsp+1C8h+var_188]
0x1801955f2  lea     rcx, [rsp+1C8h+var_C8]
0x1801955fa  call    ??$Bind@$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA?AVSqliteBoundStatement@12@XZ; Microsoft::Diagnostics::SqliteStatement::Bind<>(void)
0x1801955ff  nop
0x180195600  lea     rdx, [rsp+1C8h+var_138]
0x180195608  mov     rcx, rax
0x18019560b  call    ?Step@SqliteBoundStatement@Diagnostics@Microsoft@@QEAA?AV?$optional@VSqliteQueryResult@Diagnostics@Microsoft@@@std@@XZ; Microsoft::Diagnostics::SqliteBoundStatement::Step(void)
0x180195610  nop
0x180195611  lea     rcx, [rsp+1C8h+var_188]; void *
0x180195616  call    ??1?$shared_ptr@$$CBUProviderGroupInfo@Diagnostics@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(void)
0x18019561b  cmp     [rsp+1C8h+var_120], bl
0x180195622  jnz     short loc_180195675
0x180195624  mov     rcx, [rsp+1C8h]; this
0x18019562c  mov     ebx, 8000FFFFh
0x180195631  mov     r9d, ebx; char *
0x180195634  lea     r8, aOnecoreBaseTel_213; "onecore\\base\\telemetry\\utc\\service"...
0x18019563b  mov     edx, 94Eh; void *
0x180195640  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195645  lea     rcx, [rsp+1C8h+var_138]
0x18019564d  call    ??1?$optional@VSqliteQueryResult@Diagnostics@Microsoft@@@std@@QEAA@XZ; std::optional<Microsoft::Diagnostics::SqliteQueryResult>::~optional<Microsoft::Diagnostics::SqliteQueryResult>(void)
0x180195652  nop
0x180195653  lea     rcx, [rsp+1C8h+var_C8]; this
0x18019565b  call    ??1SqliteStatement@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::SqliteStatement::~SqliteStatement(void)
0x180195660  nop
0x180195661  lea     rcx, [rsp+1C8h+pszPath]
0x180195669  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019566e  mov     eax, ebx
0x180195670  jmp     loc_180195B37
0x180195675  lea     rcx, [rsp+1C8h+var_138]
0x18019567d  call    ??$Next@J@SqliteQueryResult@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::SqliteQueryResult::Next<long>(void)
0x180195682  mov     [rdi+600h], eax
0x180195688  lea     rcx, [rsp+1C8h+var_138]
0x180195690  call    ??1?$optional@VSqliteQueryResult@Diagnostics@Microsoft@@@std@@QEAA@XZ; std::optional<Microsoft::Diagnostics::SqliteQueryResult>::~optional<Microsoft::Diagnostics::SqliteQueryResult>(void)
0x180195695  nop
0x180195696  lea     rcx, [rsp+1C8h+var_C8]; this
0x18019569e  call    ??1SqliteStatement@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::SqliteStatement::~SqliteStatement(void)
0x1801956a3  test    r13b, r13b
0x1801956a6  jnz     loc_18019598B
0x1801956ac  lea     rdx, [rsp+1C8h+var_158]
0x1801956b1  mov     rcx, r14
0x1801956b4  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801956b9  movups  xmm0, xmmword ptr [rax]
0x1801956bc  movdqu  [rsp+1C8h+var_168], xmm0
0x1801956c2  lea     rax, aPragmaPageCoun; "PRAGMA page_count;"
0x1801956c9  mov     [rsp+1C8h+var_188], rax
0x1801956ce  mov     [rsp+1C8h+var_180], 12h
0x1801956d7  lea     r9, [rsp+1C8h+var_168]
0x1801956dc  lea     r8, [rsp+1C8h+var_188]
0x1801956e1  mov     rdx, [rsi]
0x1801956e4  lea     rcx, [rsp+1C8h+var_68]
0x1801956ec  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x1801956f1  nop
0x1801956f2  lea     rdx, [rsp+1C8h+var_138]
0x1801956fa  lea     rcx, [rsp+1C8h+var_68]
0x180195702  call    ??$Bind@$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA?AVSqliteBoundStatement@12@XZ; Microsoft::Diagnostics::SqliteStatement::Bind<>(void)
0x180195707  nop
0x180195708  lea     rdx, [rsp+1C8h+var_C8]
0x180195710  mov     rcx, rax
0x180195713  call    ?Step@SqliteBoundStatement@Diagnostics@Microsoft@@QEAA?AV?$optional@VSqliteQueryResult@Diagnostics@Microsoft@@@std@@XZ; Microsoft::Diagnostics::SqliteBoundStatement::Step(void)
0x180195718  nop
0x180195719  lea     rcx, [rsp+1C8h+var_138]; void *
0x180195721  call    ??1?$shared_ptr@$$CBUProviderGroupInfo@Diagnostics@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(void)
0x180195726  lea     rcx, [rsp+1C8h+var_C8]
  ... truncated ...
```
