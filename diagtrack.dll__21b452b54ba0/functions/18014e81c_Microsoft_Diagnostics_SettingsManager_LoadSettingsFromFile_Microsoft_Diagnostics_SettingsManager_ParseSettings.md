# Microsoft::Diagnostics::SettingsManager::LoadSettingsFromFile(Microsoft::Diagnostics::SettingsManager::ParseSettingsState &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,Microsoft::Diagnostics::SettingsPayloadType,Microsoft::Diagnostics::SettingsManager::SettingsFileExistenceCheck,Microsoft::Diagnostics::SettingsManager::SettingsFileBackupOptions)

- ea: `0x18014e81c`
- end: `0x18014fd67`
- name: `?LoadSettingsFromFile@SettingsManager@Diagnostics@Microsoft@@AEAAJAEAUParseSettingsState@123@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSettingsPayloadType@23@W4SettingsFileExistenceCheck@123@W4SettingsFileBackupOptions@123@@Z`
- size: `5451`
- prototype: ``
- caller_count: `4`
- callee_count: `48`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18013a850`
- `0x18014e0b4`
- `0x1801effcc`
- `0x1802651e0`

## callees

- `0x18002110c`
- `0x180024558`
- `0x18002abec`
- `0x18002afd8`
- `0x18002b7c0`
- `0x18002df00`
- `0x18002fa34`
- `0x180031168`
- `0x18003461c`
- `0x180038524`
- `0x18003c66c`
- `0x180049bec`
- `0x180049d00`
- `0x18004b6ac`
- `0x1800624ac`
- `0x180064e8c`
- `0x18006962c`
- `0x18006a7a0`
- `0x180081278`
- `0x18008a4ec`
- `0x18008a51c`
- `0x18008a580`
- `0x18008a5d8`
- `0x18008ab10`
- `0x18009c8c0`
- `0x1800afab0`
- `0x1800b47f0`
- `0x1800bc658`
- `0x1800c5dcc`
- `0x1800c96d4`
- `0x1800cf7d8`
- `0x1800d3790`
- `0x1800dce08`
- `0x1800ecc5c`
- `0x1800ef550`
- `0x1800f7eb8`
- `0x18013f76c`
- `0x18013fa24`
- `0x180142fcc`
- `0x18014e81c`
- `0x1801a9494`
- `0x1801b7bd0`
- `0x1801c32a0`
- `0x1801cd84c`
- `0x1801deef8`
- `0x18020aac0`
- `0x1802653b0`
- `0x180369010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014ed61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014f140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014f44c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014ed61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014f140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014f44c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18014ecec`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18014ecec`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18014fab9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18014fab9`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18014f3c3`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18014faf6`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18014f3c3`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18014faf6`

## string_xrefs

- `0x18014eddd`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18014f1b2`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18014f282`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18014f4be`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18014f635`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18014f7e6`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18014fb08`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18014fb7c`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18014fc60`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18014fd26`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18014fd3d`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18014fd54`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall Microsoft::Diagnostics::SettingsManager::LoadSettingsFromFile(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int16 a4,
        int a5,
        int a6)
{
  __int64 v8; // r8
  int v9; // r9d
  void *v10; // rax
  _QWORD *v11; // rcx
  void *v12; // r12
  _QWORD *v13; // rcx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // r13
  _QWORD *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rsi
  __int128 v19; // xmm6
  __int64 v20; // rsi
  __int64 v21; // rbx
  unsigned __int64 FileTimeAsULL; // rax
  unsigned __int64 v23; // r8
  const char *v24; // r9
  __int64 result; // rax
  int v26; // eax
  int v27; // eax
  int v28; // esi
  __int128 v29; // xmm7
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  wil::details *v34; // rcx
  int v35; // eax
  char IsEnabled; // al
  _QWORD *v37; // rcx
  _QWORD *v38; // rdx
  int v39; // eax
  unsigned int LastErrorFailHr; // ebx
  int CompressedFile; // eax
  unsigned int v42; // esi
  __int128 v43; // xmm0
  __int128 *v44; // rax
  const WCHAR *v45; // rdx
  int v46; // eax
  LPCWSTR *v47; // rcx
  __int64 v48; // rdx
  int v49; // eax
  unsigned int v50; // ebx
  __int128 v51; // xmm0
  __int128 *v52; // rax
  char v53; // di
  int v54; // r13d
  int v55; // eax
  unsigned int v56; // ebx
  __int128 v57; // xmm0
  __int128 *v58; // rax
  int v59; // ebx
  __int128 v60; // xmm0
  __int128 *v61; // rax
  __int64 v62; // rax
  __int128 v63; // xmm6
  __int64 v64; // rax
  const WCHAR *v65; // rcx
  const WCHAR *v66; // rdx
  const WCHAR *v67; // rcx
  const char *v68; // r9
  __int64 v69; // rdx
  int v70; // eax
  unsigned int v71; // ebx
  __int128 v72; // xmm0
  __int128 *v73; // rax
  int v74; // eax
  unsigned int v75; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-BF8h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-BF8h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-BF8h]
  int dwCreationDispositionc; // [rsp+20h] [rbp-BF8h]
  int dwCreationDispositiond; // [rsp+20h] [rbp-BF8h]
  int dwCreationDispositione; // [rsp+20h] [rbp-BF8h]
  __int128 v82; // [rsp+40h] [rbp-BD8h] BYREF
  __int128 v83; // [rsp+50h] [rbp-BC8h] BYREF
  __int128 v84; // [rsp+60h] [rbp-BB8h] BYREF
  HANDLE hFile; // [rsp+70h] [rbp-BA8h] BYREF
  int v86; // [rsp+78h] [rbp-BA0h]
  __int64 v87; // [rsp+80h] [rbp-B98h]
  __int64 v88; // [rsp+88h] [rbp-B90h]
  _BYTE v89[16]; // [rsp+90h] [rbp-B88h] BYREF
  _BYTE v90[80]; // [rsp+A0h] [rbp-B78h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+F0h] [rbp-B28h] BYREF
  unsigned __int64 v92; // [rsp+108h] [rbp-B10h]
  LPCWSTR lpNewFileName[2]; // [rsp+110h] [rbp-B08h] BYREF
  __m128i v94; // [rsp+120h] [rbp-AF8h]
  __int128 v95; // [rsp+130h] [rbp-AE8h] BYREF
  __m128i si128; // [rsp+140h] [rbp-AD8h]
  _OWORD v97[2]; // [rsp+150h] [rbp-AC8h] BYREF
  WCHAR v98[16]; // [rsp+170h] [rbp-AA8h] BYREF
  _BYTE v99[32]; // [rsp+190h] [rbp-A88h] BYREF
  WCHAR v100[16]; // [rsp+1B0h] [rbp-A68h] BYREF
  _QWORD v101[7]; // [rsp+1D0h] [rbp-A48h] BYREF
  _QWORD *v102; // [rsp+208h] [rbp-A10h]
  _QWORD v103[7]; // [rsp+210h] [rbp-A08h] BYREF
  _QWORD *v104; // [rsp+248h] [rbp-9D0h]
  _BYTE Src[32]; // [rsp+250h] [rbp-9C8h] BYREF
  int v106[282]; // [rsp+270h] [rbp-9A8h] BYREF
  int v107[14]; // [rsp+6D8h] [rbp-540h] BYREF
  _BYTE v108[1128]; // [rsp+710h] [rbp-508h] BYREF
  char v109[56]; // [rsp+B78h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C18h] [rbp+0h]

  v88 = a2;
  v87 = a1;
  if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 512) )
  {
    if ( *(_QWORD *)(v8 + 24) <= 7u )
      v10 = a3;
    else
      v10 = *(void **)v8;
    hFile = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (unsigned int)&dword_1804543B0,
      (unsigned int)&byte_1803E7CC7,
      v8,
      v9,
      (__int64)&hFile);
  }
  if ( a3[3] <= 7u )
    v11 = a3;
  else
    v11 = (_QWORD *)*a3;
  v12 = (void *)std::_Traits_rfind_ch<std::char_traits<wchar_t>>(v11, a3[2], -1, 92);
  hFile = v12;
  if ( a3[3] <= 7u )
    v13 = a3;
  else
    v13 = (_QWORD *)*a3;
  v14 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(v13, a3[2], -1, 46);
  try
  {
    v15 = v14;
    if ( v12 == (void *)-1LL )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x79A,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
        (const char *)0x80070057LL,
        dwCreationDisposition);
    if ( v14 == -1 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x79B,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
        (const char *)0x80070057LL,
        dwCreationDisposition);
    if ( (unsigned __int64)v12 > v14 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x79C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
        (const char *)0x80070057LL,
        dwCreationDisposition);
    LOBYTE(v86) = 0;
    std::wstring::operator std::wstring_view(a3, lpFileName);
    v97[0] = 0;
    v97[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v97[0]) = 0;
    if ( a3[3] <= 7u )
      v16 = a3;
    else
      v16 = (_QWORD *)*a3;
    v17 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(v16, a3[2], v15 - 1, 46);
    v18 = v17;
    if ( v17 == -1 || v15 - v17 < 2 )
    {
      v28 = v87;
    }
    else
    {
      std::wstring_view::substr(lpFileName, &v82, (char *)hFile + 1);
      std::wstring_view::substr(lpFileName, &v84, v18 + 1);
      v83 = *(_OWORD *)&off_18036A6A0;
      v19 = v82;
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v82, &v83) )
      {
        v20 = v87;
        std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(&v82, v87 + 232);
        v21 = std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Find<std::wstring_view>(
                v20 + 56,
                &v84);
        if ( v21 != *(_QWORD *)(v20 + 56) )
        {
          FileTimeAsULL = Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL();
          if ( *(_QWORD *)(v21 + 64) )
          {
            v23 = FileTimeAsULL - *(_QWORD *)(v21 + 64);
            if ( v23 > 600000000 * (unsigned __int64)*(unsigned int *)(v20 + 544) )
            {
              v83 = v84;
              v84 = *(_OWORD *)&off_18036A6A0;
              Microsoft::Diagnostics::SettingsManager::UnregisterSettingsEndpoint(
                v20,
                (unsigned int)&v84,
                (unsigned int)&v83,
                0,
                3);
              std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v82);
              std::wstring::_Tidy_deallocate(v97);
              return 0;
            }
            v26 = (unsigned __int8)v86;
            if ( v23 > 600000000 * (unsigned __int64)*(unsigned int *)(v20 + 548) )
              v26 = 1;
            v86 = v26;
          }
        }
        std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v82);
      }
      v83 = *(_OWORD *)&off_180384950;
      v82 = v19;
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v82, &v83) )
        std::wstring::_Assign<wchar_t>((char **)v97, (const void *)v84, *((char **)&v84 + 1));
      v83 = *(_OWORD *)&off_180384960;
      v82 = v84;
      v27 = Microsoft::Diagnostics::Utils::String::ICompare(&v82, &v83);
      v28 = v87;
      if ( !v27 )
        std::_Tree<std::_Tset_traits<std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::wstring>,0>>::insert<0,0>(
          v87 + 1152,
          &v83,
          a3);
    }
    if ( a4 )
    {
      if ( (unsigned __int16)(a4 - 1) > 1u )
      {
LABEL_112:
        std::wstring::_Tidy_deallocate(v97);
        return 0;
      }
      std::wstring_view::substr(lpFileName, &v84, (char *)hFile + 1);
      v95 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(v95) = 0;
      v29 = v84;
      v30 = std::wstring::wstring((__int64)v99, &off_180384700);
      v31 = std::operator+<wchar_t>(v98, v30, L"\\");
      v83 = v29;
      v32 = Microsoft::Diagnostics::operator+(lpNewFileName, v31, &v83);
      v83 = *(_OWORD *)&Microsoft::Diagnostics::SettingsDownloader::k_diffBaseFileExtension;
      Microsoft::Diagnostics::operator+(v100, v32, &v83);
      std::wstring::_Tidy_deallocate(lpNewFileName);
      std::wstring::_Tidy_deallocate(v98);
      std::wstring::_Tidy_deallocate(v99);
      Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v100);
      v33 = std::wstring::wstring(Src, v100);
      if ( *(_QWORD *)(v33 + 24) > 7u )
        v33 = *(_QWORD *)v33;
      hFile = CreateFileW((LPCWSTR)v33, 0x80000000, 5u, 0, 3u, 0x80u, 0);
      std::wstring::_Tidy_deallocate(Src);
      v34 = (wil::details *)hFile;
      if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        goto LABEL_60;
      *(_QWORD *)&v82 = L"SettingsManager_UseWinSxSStorageFileAsLoadingInboxDiffFileFailed";
      *((_QWORD *)&v82 + 1) = 64;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
        (unsigned int)v108,
        (unsigned int)&v82,
        0x1000000,
        0,
        0,
        0,
        0);
      LODWORD(lpFileName[0]) = GetLastError();
      *(_QWORD *)&v82 = L"LastError";
      *((_QWORD *)&v82 + 1) = 9;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(v108, v109, &v82, lpFileName);
      v83 = 0;
      Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(
        lpFileName,
        &v83);
      v35 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v108);
      if ( v35 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x834,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
          (const char *)(unsigned int)v35,
          dwCreationDispositiona);
      *(_OWORD *)lpNewFileName = 0;
      v94.m128i_i64[0] = 0;
      v94.m128i_i64[1] = 7;
      LOWORD(lpNewFileName[0]) = 0;
      *(_QWORD *)&v82 = L"utc.allow";
      *((_QWORD *)&v82 + 1) = 9;
      v83 = v84;
      if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v83, &v82) )
      {
        *(_QWORD *)&v82 = L"utc.privacy";
        *((_QWORD *)&v82 + 1) = 11;
        v83 = v84;
        if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v83, &v82)
          || (*(_QWORD *)&v82 = L"utc.aggregators",
              *((_QWORD *)&v82 + 1) = 15,
              v83 = v84,
              !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v83, &v82)) )
        {
          std::wstring::assign(lpNewFileName, L"*windowsclient*");
        }
      }
      else
      {
        std::wstring::assign(lpNewFileName, L"*telemetry-client*");
      }
      if ( !v94.m128i_i64[0] )
      {
        *(_QWORD *)&v82 = L"SettingsManager_NonUtcAllowOrPrivacyHardcodedEndpointEncountered";
        *((_QWORD *)&v82 + 1) = 64;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
          (unsigned int)v106,
          (unsigned int)&v82,
          0x1000000,
          0,
          0,
          0,
          0);
        *(_QWORD *)&v82 = L"endpoint";
        *((_QWORD *)&v82 + 1) = 8;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v106, (int)v107);
        LODWORD(lpFileName[0]) = GetLastError();
        *(_QWORD *)&v82 = L"LastError";
        *((_QWORD *)&v82 + 1) = 9;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(v106, v107, &v82, lpFileName);
        v83 = 0;
        Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(
          lpFileName,
          &v83);
        v39 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v106);
        if ( v39 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x87C,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
            (const char *)(unsigned int)v39,
            dwCreationDispositiona);
        Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v106);
        goto LABEL_59;
      }
      std::wstring::wstring((__int64)v98, &off_180384710);
      Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v98);
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TvsWarningFixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TvsWarningFixes>::GetImpl'::`2'::impl);
      v90[64] = 0;
      if ( IsEnabled )
      {
        v103[0] = off_18037DAF0;
        v103[1] = v100;
        v103[2] = &v84;
        v103[3] = &hFile;
        v104 = v103;
        v83 = *(_OWORD *)std::wstring::operator std::wstring_view(lpNewFileName, v89);
        v82 = *(_OWORD *)std::wstring::operator std::wstring_view(v98, v99);
        Microsoft::Diagnostics::Utils::FileSystem::DoForEachDirectoryInPattern(&v82, &v83, v103, v90);
        v37 = v104;
        if ( v104 )
        {
          v38 = v103;
          goto LABEL_54;
        }
      }
      else
      {
        v101[0] = off_18037DAC0;
        v101[1] = v100;
        v101[2] = &v84;
        v101[3] = &hFile;
        v102 = v101;
        v83 = *(_OWORD *)std::wstring::operator std::wstring_view(lpNewFileName, lpFileName);
        v82 = *(_OWORD *)std::wstring::operator std::wstring_view(v98, v89);
        Microsoft::Diagnostics::Utils::FileSystem::DoForEachDirectoryInPattern(&v82, &v83, v101, v90);
        v37 = v102;
        if ( v102 )
        {
          v38 = v101;
LABEL_54:
          LOBYTE(v38) = v37 != v38;
          (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v37 + 32LL))(v37, v38);
        }
      }
      std::wstring::_Tidy_deallocate(v98);
LABEL_59:
      std::wstring::_Tidy_deallocate(lpNewFileName);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v108);
      v34 = (wil::details *)hFile;
LABEL_60:
      if ( a4 == 1 && (((unsigned __int64)v34 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LastErrorFailHr = wil::details::GetLastErrorFailHr(v34);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        std::wstring::_Tidy_deallocate(v100);
        std::string::_Tidy_deallocate(&v95);
        std::wstring::_Tidy_deallocate(v97);
        return LastErrorFailHr;
      }
      if ( (unsigned __int64)v34 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CompressedFile = Microsoft::Diagnostics::Utils::FileSystem::ReadCompressedFile(v34);
        v42 = CompressedFile;
        if ( CompressedFile < 0 && a4 == 1 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x88C,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
            (const char *)(unsigned int)CompressedFile,
            dwCreationDispositiona);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          std::wstring::_Tidy_deallocate(v100);
          std::string::_Tidy_deallocate(&v95);
          std::wstring::_Tidy_deallocate(v97);
          return v42;
        }
      }
      v43 = *(_OWORD *)std::wstring::operator std::wstring_view(v97, v99);
      v44 = (__int128 *)std::wstring::operator std::wstring_view(a3, v89);
      v83 = v43;
      v82 = *v44;
      *(_OWORD *)lpFileName = *(_OWORD *)std::string::operator std::string_view(&v95, v98);
      LOBYTE(dwCreationDispositiona) = v86;
      if ( (int)Microsoft::Diagnostics::SettingsManager::ParseSettings(
                  v87,
                  v88,
                  (unsigned int)lpFileName,
                  (unsigned int)&v82,
                  dwCreationDispositiona,
                  (__int64)&v83,
                  a4) >= 0
        && !a6 )
      {
        v83 = *(_OWORD *)&Microsoft::Diagnostics::SettingsDownloader::k_backupFileExtension;
        Microsoft::Diagnostics::operator+(lpNewFileName);
        v45 = (const WCHAR *)lpNewFileName;
        if ( v94.m128i_i64[1] > 7uLL )
          v45 = lpNewFileName[0];
        if ( a3[3] > 7u )
          a3 = (_QWORD *)*a3;
        if ( !CopyFileW((LPCWSTR)a3, v45, 0) )
        {
          *(_QWORD *)&v82 = L"SettingsManager_SavePatchSettingsBackupFailed";
          *((_QWORD *)&v82 + 1) = 45;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
            (unsigned int)v106,
            (unsigned int)&v82,
            0x1000000,
            0,
            0,
            0,
            0);
          *(_QWORD *)&v82 = L"fileName";
          *((_QWORD *)&v82 + 1) = 8;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v106, (int)v107);
          LODWORD(lpFileName[0]) = GetLastError();
          *(_QWORD *)&v82 = L"LastError";
          *((_QWORD *)&v82 + 1) = 9;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(v106, v107, &v82, lpFileName);
          v83 = 0;
          Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(
            lpFileName,
            &v83);
          v46 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v106);
          if ( v46 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x89D,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
              (const char *)(unsigned int)v46,
              dwCreationDispositionb);
          Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v106);
        }
        std::wstring::_Tidy_deallocate(lpNewFileName);
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      std::wstring::_Tidy_deallocate(v100);
      v47 = (LPCWSTR *)&v95;
      goto LABEL_111;
    }
    *(_OWORD *)lpNewFileName = 0;
    v94 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(lpNewFileName[0]) = 0;
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)a3);
    v83 = *(_OWORD *)std::wstring::operator std::wstring_view(a3, v98);
    v49 = Microsoft::Diagnostics::Utils::FileSystem::ReadStringFromFile(&v83, v48, 0xFFFFFFFFLL, lpNewFileName);
    v50 = v49;
    LODWORD(lpFileName[0]) = v49;
    if ( v49 < 0 )
    {
      if ( a6 == 1 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7F0,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
          (const char *)(unsigned int)v49,
          dwCreationDisposition);
        std::string::_Tidy_deallocate(lpNewFileName);
        std::wstring::_Tidy_deallocate(v97);
        return v50;
      }
      if ( a5 == 1 && v49 == -2147024894 )
      {
        std::string::_Tidy_deallocate(lpNewFileName);
        std::wstring::_Tidy_deallocate(v97);
        return 0;
      }
      *(_QWORD *)&v82 = L"SettingsManager_RevertToPreviousSettingsBecauseFailedParse";
      *((_QWORD *)&v82 + 1) = 58;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
        (unsigned int)v106,
        (unsigned int)&v82,
        0x1000000,
        0,
        0,
        0,
        0);
      *(_QWORD *)&v82 = L"ErrorCode";
      *((_QWORD *)&v82 + 1) = 9;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((int)v106, (int)v107);
      *(_QWORD *)&v82 = L"FileName";
      *((_QWORD *)&v82 + 1) = 8;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v106, v107, &v82, a3);
      v83 = 0;
      Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(
        lpFileName,
        &v83);
      Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v106);
      v60 = *(_OWORD *)std::wstring::operator std::wstring_view(v97, v98);
      v61 = (__int128 *)std::wstring::operator std::wstring_view(a3, v99);
      v83 = v60;
      v82 = *v61;
      v84 = *(_OWORD *)std::string::operator std::string_view(qword_180462710, v89);
      v53 = v86;
      v54 = v88;
      v59 = Microsoft::Diagnostics::SettingsManager::RetryParseWithBackupSettings(
              v28,
              v88,
              (unsigned int)&v84,
              (unsigned int)&v82,
              v86,
              (__int64)&v83,
              0);
    }
    else
    {
      v51 = *(_OWORD *)std::wstring::operator std::wstring_view(v97, v98);
      v52 = (__int128 *)std::wstring::operator std::wstring_view(&qword_1804626F0, v99);
      v83 = v51;
      v82 = *v52;
      v84 = *(_OWORD *)std::string::operator std::string_view(lpNewFileName, v89);
      v53 = v86;
      LOBYTE(dwCreationDisposition) = v86;
      v54 = v88;
      v55 = Microsoft::Diagnostics::SettingsManager::ParseSettings(
              v28,
              v88,
              (unsigned int)&v84,
              (unsigned int)&v82,
              dwCreationDisposition,
              (__int64)&v83,
              0);
      v56 = v55;
      LODWORD(lpFileName[0]) = v55;
      if ( a6 == 1 )
      {
        if ( v55 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7DC,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
            (const char *)(unsigned int)v55,
            dwCreationDispositionc);
        std::string::_Tidy_deallocate(lpNewFileName);
        std::wstring::_Tidy_deallocate(v97);
        return v56;
      }
      if ( v55 >= 0 )
      {
LABEL_110:
        v47 = lpNewFileName;
LABEL_111:
        std::string::_Tidy_deallocate(v47);
        goto LABEL_112;
      }
      *(_QWORD *)&v82 = L"SettingsManager_RevertToPreviousSettingsBecauseFailedParse";
      *((_QWORD *)&v82 + 1) = 58;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
        (unsigned int)v106,
        (unsigned int)&v82,
        0x1000000,
        0,
        0,
        0,
        0);
      *(_QWORD *)&v82 = L"ErrorCode";
      *((_QWORD *)&v82 + 1) = 9;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((int)v106, (int)v107);
      *(_QWORD *)&v82 = L"FileName";
      *((_QWORD *)&v82 + 1) = 8;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v106, v107, &v82, a3);
      v83 = 0;
      Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(
        lpFileName,
        &v83);
      Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v106);
      v57 = *(_OWORD *)std::wstring::operator std::wstring_view(v97, v98);
      v58 = (__int128 *)std::wstring::operator std::wstring_view(a3, v99);
      v83 = v57;
      v82 = *v58;
      v84 = *(_OWORD *)std::string::operator std::string_view(qword_180462710, v89);
      v59 = Microsoft::Diagnostics::SettingsManager::RetryParseWithBackupSettings(
              v28,
              v54,
              (unsigned int)&v84,
              (unsigned int)&v82,
              v53,
              (__int64)&v83,
              0);
    }
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v106);
    if ( v59 < 0 )
    {
      std::wstring::operator std::wstring_view(a3, &v84);
      v62 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(v84, *((_QWORD *)&v84 + 1), -1, 92);
      if ( v62 != -1 )
      {
        v63 = *(_OWORD *)std::wstring_view::substr(&v84, v98, v62 + 1);
        std::wstring::wstring(&v95);
        v83 = *(_OWORD *)&off_180384830;
        v64 = Microsoft::Diagnostics::operator+(Src);
        v83 = v63;
        Microsoft::Diagnostics::operator+(lpFileName, v64, &v83);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(&v95);
        Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)lpFileName);
        v65 = (const WCHAR *)lpFileName;
        if ( v92 > 7 )
          v65 = lpFileName[0];
        if ( GetFileAttributesW(v65) != -1 )
        {
          if ( a3[3] <= 7u )
            v66 = (const WCHAR *)a3;
          else
            v66 = (const WCHAR *)*a3;
          v67 = (const WCHAR *)lpFileName;
          if ( v92 > 7 )
            v67 = lpFileName[0];
          if ( !CopyFileW(v67, v66, 0) )
            wil::details::in1diag3::_Log_GetLastError(
              retaddr,
              (void *)0x812,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
              v68);
          v95 = 0;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOBYTE(v95) = 0;
          v83 = *(_OWORD *)std::wstring::operator std::wstring_view(a3, v98);
          v70 = Microsoft::Diagnostics::Utils::FileSystem::ReadStringFromFile(&v83, v69, 0xFFFFFFFFLL, &v95);
          v71 = v70;
          if ( v70 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x816,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
              (const char *)(unsigned int)v70,
              dwCreationDispositiond);
            std::string::_Tidy_deallocate(&v95);
            std::wstring::_Tidy_deallocate(lpFileName);
            std::string::_Tidy_deallocate(lpNewFileName);
            std::wstring::_Tidy_deallocate(v97);
            return v71;
          }
          v72 = *(_OWORD *)std::wstring::operator std::wstring_view(v97, v98);
          v73 = (__int128 *)std::wstring::operator std::wstring_view(&qword_1804626F0, v99);
          v83 = v72;
          v82 = *v73;
          v84 = *(_OWORD *)std::string::operator std::string_view(&v95, v89);
          LOBYTE(dwCreationDispositiond) = v53;
          v74 = Microsoft::Diagnostics::SettingsManager::ParseSettings(
                  v28,
                  v54,
                  (unsigned int)&v84,
                  (unsigned int)&v82,
                  dwCreationDispositiond,
                  (__int64)&v83,
                  0);
          v75 = v74;
          if ( v74 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x817,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
              (const char *)(unsigned int)v74,
              dwCreationDispositione);
            std::string::_Tidy_deallocate(&v95);
            std::wstring::_Tidy_deallocate(lpFileName);
            std::string::_Tidy_deallocate(lpNewFileName);
            std::wstring::_Tidy_deallocate(v97);
            return v75;
          }
          std::string::_Tidy_deallocate(&v95);
        }
        std::wstring::_Tidy_deallocate(lpFileName);
      }
    }
    goto LABEL_110;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x8A4,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
                           v24);
  }
  return result;
}

```

## disassembly

```asm
0x18014e81c  mov     rax, rsp
0x18014e81f  push    rbx
0x18014e820  push    rsi
0x18014e821  push    rdi
0x18014e822  push    r12
0x18014e824  push    r13
0x18014e826  push    r14
0x18014e828  push    r15
0x18014e82a  sub     rsp, 0BE0h
0x18014e831  movaps  xmmword ptr [rax-48h], xmm6
0x18014e835  movaps  xmmword ptr [rax-58h], xmm7
0x18014e839  mov     rax, cs:__security_cookie
0x18014e840  xor     rax, rsp
0x18014e843  mov     [rsp+0C18h+var_68], rax
0x18014e84b  movzx   edi, r9w
0x18014e84f  mov     r15, r8
0x18014e852  mov     [rsp+0C18h+var_B90], rdx
0x18014e85a  mov     [rsp+0C18h+var_B98], rcx
0x18014e862  mov     eax, cs:dword_1804543B0
0x18014e868  cmp     eax, 5
0x18014e86b  jbe     short loc_18014E8B8
0x18014e86d  mov     edx, 200h
0x18014e872  lea     rcx, dword_1804543B0
0x18014e879  call    _tlgKeywordOn
0x18014e87e  xor     r14d, r14d
0x18014e881  test    al, al
0x18014e883  jz      short loc_18014E8BB
0x18014e885  cmp     qword ptr [r8+18h], 7
0x18014e88a  jbe     short loc_18014E891
0x18014e88c  mov     rax, [r8]
0x18014e88f  jmp     short loc_18014E894
0x18014e891  mov     rax, r15
0x18014e894  mov     [rsp+0C18h+hFile], rax
0x18014e899  lea     rax, [rsp+0C18h+hFile]
0x18014e89e  mov     qword ptr [rsp+0C18h+dwCreationDisposition], rax
0x18014e8a3  lea     rdx, byte_1803E7CC7
0x18014e8aa  lea     rcx, dword_1804543B0
0x18014e8b1  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18014e8b6  jmp     short loc_18014E8BB
0x18014e8b8  xor     r14d, r14d
0x18014e8bb  cmp     qword ptr [r15+18h], 7
0x18014e8c0  jbe     short loc_18014E8C7
0x18014e8c2  mov     rcx, [r15]
0x18014e8c5  jmp     short loc_18014E8CA
0x18014e8c7  mov     rcx, r15
0x18014e8ca  mov     r9d, 5Ch ; '\'
0x18014e8d0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18014e8d4  mov     r8, rbx
0x18014e8d7  mov     rdx, [r15+10h]
0x18014e8db  call    ??$_Traits_rfind_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_rfind_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x18014e8e0  mov     r12, rax
0x18014e8e3  mov     [rsp+0C18h+hFile], rax
0x18014e8e8  cmp     qword ptr [r15+18h], 7
0x18014e8ed  jbe     short loc_18014E8F4
0x18014e8ef  mov     rcx, [r15]
0x18014e8f2  jmp     short loc_18014E8F7
0x18014e8f4  mov     rcx, r15
0x18014e8f7  mov     esi, 2Eh ; '.'
0x18014e8fc  mov     r9d, esi
0x18014e8ff  mov     r8, rbx
0x18014e902  mov     rdx, [r15+10h]
0x18014e906  call    ??$_Traits_rfind_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_rfind_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x18014e90b  mov     r13, rax
0x18014e90e  mov     rcx, [rsp+0C18h]; this
0x18014e916  cmp     r12, rbx
0x18014e919  jz      loc_18014FD20
0x18014e91f  mov     rcx, [rsp+0C18h]; this
0x18014e927  cmp     r13, rbx
0x18014e92a  jz      loc_18014FD37
0x18014e930  mov     rcx, [rsp+0C18h]; this
0x18014e938  cmp     r12, r13
0x18014e93b  ja      loc_18014FD4E
0x18014e941  mov     byte ptr [rsp+0C18h+var_BA0], r14b
0x18014e946  lea     rdx, [rsp+0C18h+lpFileName]
0x18014e94e  mov     rcx, r15
0x18014e951  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18014e956  xorps   xmm0, xmm0
0x18014e959  movups  [rsp+0C18h+var_AC8], xmm0
0x18014e961  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18014e969  movdqu  [rsp+0C18h+var_AB8], xmm1
0x18014e972  mov     word ptr [rsp+0C18h+var_AC8], r14w
0x18014e97b  cmp     qword ptr [r15+18h], 7
0x18014e980  jbe     short loc_18014E987
0x18014e982  mov     rcx, [r15]
0x18014e985  jmp     short loc_18014E98A
0x18014e987  mov     rcx, r15
0x18014e98a  mov     r9d, esi
0x18014e98d  lea     r8, [r13-1]
0x18014e991  mov     rdx, [r15+10h]
0x18014e995  call    ??$_Traits_rfind_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_rfind_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x18014e99a  mov     rsi, rax
0x18014e99d  cmp     rax, rbx
0x18014e9a0  jz      loc_18014EB8C
0x18014e9a6  mov     rbx, r13
0x18014e9a9  sub     rbx, rax
0x18014e9ac  cmp     rbx, 2
0x18014e9b0  jb      loc_18014EB8C
0x18014e9b6  mov     r9, rax
0x18014e9b9  sub     r9, r12
0x18014e9bc  mov     r12d, 1
0x18014e9c2  sub     r9, r12
0x18014e9c5  mov     r8, [rsp+0C18h+hFile]
0x18014e9ca  inc     r8
0x18014e9cd  lea     rdx, [rsp+0C18h+var_BD8]
0x18014e9d2  lea     rcx, [rsp+0C18h+lpFileName]
0x18014e9da  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x18014e9df  lea     r9, [rbx-1]
0x18014e9e3  lea     r8, [rsi+1]
0x18014e9e7  lea     rdx, [rsp+0C18h+var_BB8]
0x18014e9ec  lea     rcx, [rsp+0C18h+lpFileName]
0x18014e9f4  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x18014e9f9  movups  xmm0, xmmword ptr cs:off_18036A6A0; "telemetry"
0x18014ea00  movdqu  [rsp+0C18h+var_BC8], xmm0
0x18014ea06  movaps  xmm6, [rsp+0C18h+var_BD8]
0x18014ea0b  movdqa  [rsp+0C18h+var_BD8], xmm6
0x18014ea11  lea     rdx, [rsp+0C18h+var_BC8]
0x18014ea16  lea     rcx, [rsp+0C18h+var_BD8]
0x18014ea1b  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18014ea20  test    eax, eax
0x18014ea22  jnz     loc_18014EB06
0x18014ea28  mov     rsi, [rsp+0C18h+var_B98]
0x18014ea30  lea     rdx, [rsi+0E8h]
0x18014ea37  lea     rcx, [rsp+0C18h+var_BD8]
0x18014ea3c  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x18014ea41  nop
0x18014ea42  lea     rdx, [rsp+0C18h+var_BB8]
0x18014ea47  lea     rcx, [rsi+38h]
0x18014ea4b  call    ??$_Find@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@PEAX@1@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Find<std::wstring_view>(std::wstring_view const &)
0x18014ea50  mov     rbx, rax
0x18014ea53  cmp     rax, [rsi+38h]
0x18014ea57  jz      loc_18014EAFC
0x18014ea5d  call    ?GetFileTimeAsULL@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL(void)
0x18014ea62  mov     r8, rax
0x18014ea65  cmp     [rbx+40h], r14
0x18014ea69  jz      loc_18014EAFC
0x18014ea6f  sub     r8, [rbx+40h]
0x18014ea73  mov     rax, rsi
0x18014ea76  mov     ecx, [rax+220h]
0x18014ea7c  imul    rdx, rcx, 23C34600h
0x18014ea83  cmp     r8, rdx
0x18014ea86  jbe     short loc_18014EADD
0x18014ea88  movaps  xmm0, [rsp+0C18h+var_BB8]
0x18014ea8d  movdqa  [rsp+0C18h+var_BC8], xmm0
0x18014ea93  movups  xmm1, xmmword ptr cs:off_18036A6A0; "telemetry"
0x18014ea9a  movdqu  [rsp+0C18h+var_BB8], xmm1
0x18014eaa0  mov     [rsp+0C18h+dwCreationDisposition], 3
0x18014eaa8  xor     r9d, r9d
0x18014eaab  lea     r8, [rsp+0C18h+var_BC8]
0x18014eab0  lea     rdx, [rsp+0C18h+var_BB8]
0x18014eab5  mov     rcx, rax
0x18014eab8  call    ?UnregisterSettingsEndpoint@SettingsManager@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_NVEndpointUnregistrationReason@23@@Z; Microsoft::Diagnostics::SettingsManager::UnregisterSettingsEndpoint(std::wstring_view,std::wstring_view,bool,Microsoft::Diagnostics::EndpointUnregistrationReason)
0x18014eabd  nop
0x18014eabe  lea     rcx, [rsp+0C18h+var_BD8]
0x18014eac3  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18014eac8  nop
0x18014eac9  lea     rcx, [rsp+0C18h+var_AC8]
0x18014ead1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18014ead6  xor     eax, eax
0x18014ead8  jmp     loc_18014FCEF
0x18014eadd  mov     eax, [rax+224h]
0x18014eae3  imul    rcx, rax, 23C34600h
0x18014eaea  mov     eax, [rsp+0C18h+var_BA0]
0x18014eaee  movzx   eax, al
0x18014eaf1  cmp     r8, rcx
0x18014eaf4  cmova   eax, r12d
0x18014eaf8  mov     [rsp+0C18h+var_BA0], eax
0x18014eafc  lea     rcx, [rsp+0C18h+var_BD8]
0x18014eb01  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18014eb06  movups  xmm0, xmmword ptr cs:off_180384950; "telemetry"
0x18014eb0d  movdqu  [rsp+0C18h+var_BC8], xmm0
0x18014eb13  movdqa  [rsp+0C18h+var_BD8], xmm6
0x18014eb19  lea     rdx, [rsp+0C18h+var_BC8]
0x18014eb1e  lea     rcx, [rsp+0C18h+var_BD8]
0x18014eb23  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18014eb28  test    eax, eax
0x18014eb2a  jnz     short loc_18014EB43
0x18014eb2c  mov     r8, qword ptr [rsp+0C18h+var_BB8+8]
0x18014eb31  mov     rdx, qword ptr [rsp+0C18h+var_BB8]
0x18014eb36  lea     rcx, [rsp+0C18h+var_AC8]
0x18014eb3e  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18014eb43  movups  xmm0, xmmword ptr cs:off_180384960; "aggregators"
0x18014eb4a  movdqu  [rsp+0C18h+var_BC8], xmm0
0x18014eb50  movaps  xmm0, [rsp+0C18h+var_BB8]
0x18014eb55  movdqa  [rsp+0C18h+var_BD8], xmm0
0x18014eb5b  lea     rdx, [rsp+0C18h+var_BC8]
0x18014eb60  lea     rcx, [rsp+0C18h+var_BD8]
0x18014eb65  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18014eb6a  mov     rsi, [rsp+0C18h+var_B98]
0x18014eb72  test    eax, eax
0x18014eb74  jnz     short loc_18014EB9A
0x18014eb76  lea     rcx, [rsi+480h]
0x18014eb7d  mov     r8, r15
0x18014eb80  lea     rdx, [rsp+0C18h+var_BC8]
0x18014eb85  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveLessThanPredicate@String@Utils@Diagnostics@Microsoft@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring const &)
0x18014eb8a  jmp     short loc_18014EB9A
0x18014eb8c  mov     r12d, 1
0x18014eb92  mov     rsi, [rsp+0C18h+var_B98]
0x18014eb9a  test    di, di
0x18014eb9d  jz      loc_18014F512
0x18014eba3  movzx   eax, di
0x18014eba6  sub     ax, r12w
0x18014ebaa  cmp     ax, r12w
0x18014ebae  ja      loc_18014FCD7
0x18014ebb4  mov     rax, [rsp+0C18h+hFile]
0x18014ebb9  sub     r13, rax
0x18014ebbc  sub     r13, r12
0x18014ebbf  lea     r8, [rax+1]
0x18014ebc3  mov     r9, r13
0x18014ebc6  lea     rdx, [rsp+0C18h+var_BB8]
0x18014ebcb  lea     rcx, [rsp+0C18h+lpFileName]
0x18014ebd3  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x18014ebd8  xorps   xmm0, xmm0
0x18014ebdb  movups  [rsp+0C18h+var_AE8], xmm0
0x18014ebe3  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18014ebeb  movdqu  [rsp+0C18h+var_AD8], xmm1
0x18014ebf4  mov     byte ptr [rsp+0C18h+var_AE8], r14b
0x18014ebfc  movups  xmm6, xmmword ptr cs:?k_diffBaseFileExtension@SettingsDownloader@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::SettingsDownloader::k_diffBaseFileExtension
0x18014ec03  movaps  xmm7, [rsp+0C18h+var_BB8]
0x18014ec08  lea     rdx, off_180384700; "%WinDir%\\DiagTrack"
0x18014ec0f  lea     rcx, [rsp+0C18h+var_A88]
0x18014ec17  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18014ec1c  nop
0x18014ec1d  lea     r8, asc_18039BCF0; "\\"
0x18014ec24  mov     rdx, rax
0x18014ec27  lea     rcx, [rsp+0C18h+var_AA8]
0x18014ec2f  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18014ec34  nop
0x18014ec35  movdqu  [rsp+0C18h+var_BC8], xmm7
0x18014ec3b  lea     r8, [rsp+0C18h+var_BC8]
0x18014ec40  mov     rdx, rax
0x18014ec43  lea     rcx, [rsp+0C18h+lpNewFileName]
0x18014ec4b  call    ??HDiagnostics@Microsoft@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$QEAV23@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; Microsoft::Diagnostics::operator+(std::wstring &&,std::wstring_view)
0x18014ec50  nop
0x18014ec51  movdqu  [rsp+0C18h+var_BC8], xmm6
0x18014ec57  lea     r8, [rsp+0C18h+var_BC8]
0x18014ec5c  mov     rdx, rax
0x18014ec5f  lea     rcx, [rsp+0C18h+var_A68]
0x18014ec67  call    ??HDiagnostics@Microsoft@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$QEAV23@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; Microsoft::Diagnostics::operator+(std::wstring &&,std::wstring_view)
0x18014ec6c  nop
0x18014ec6d  lea     rcx, [rsp+0C18h+lpNewFileName]
0x18014ec75  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18014ec7a  nop
0x18014ec7b  lea     rcx, [rsp+0C18h+var_AA8]
0x18014ec83  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18014ec88  nop
0x18014ec89  lea     rcx, [rsp+0C18h+var_A88]
0x18014ec91  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18014ec96  xor     r8d, r8d
0x18014ec99  mov     dl, r12b
0x18014ec9c  lea     rcx, [rsp+0C18h+var_A68]; lpSrc
0x18014eca4  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18014eca9  lea     rdx, [rsp+0C18h+var_A68]
0x18014ecb1  lea     rcx, [rsp+0C18h+Src]
0x18014ecb9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18014ecbe  cmp     qword ptr [rax+18h], 7
0x18014ecc3  jbe     short loc_18014ECC8
0x18014ecc5  mov     rax, [rax]
0x18014ecc8  mov     [rsp+0C18h+hTemplateFile], r14; hTemplateFile
0x18014eccd  mov     [rsp+0C18h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18014ecd5  mov     [rsp+0C18h+dwCreationDisposition], 3; int
0x18014ecdd  xor     r9d, r9d; lpSecurityAttributes
0x18014ece0  mov     edx, 80000000h; dwDesiredAccess
0x18014ece5  lea     r8d, [r9+5]; dwShareMode
0x18014ece9  mov     rcx, rax; lpFileName
0x18014ecec  call    cs:__imp_CreateFileW
0x18014ecf2  mov     [rsp+0C18h+hFile], rax
0x18014ecf7  lea     rcx, [rsp+0C18h+Src]
0x18014ecff  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18014ed04  mov     rcx, [rsp+0C18h+hFile]; hFile
0x18014ed09  lea     rax, [rcx+1]
0x18014ed0d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18014ed13  jnz     loc_18014F1F4
0x18014ed19  lea     rax, aSettingsmanage_9; "SettingsManager_UseWinSxSStorageFileAsL"...
0x18014ed20  mov     qword ptr [rsp+0C18h+var_BD8], rax
0x18014ed25  mov     esi, 40h ; '@'
0x18014ed2a  mov     qword ptr [rsp+0C18h+var_BD8+8], rsi
0x18014ed2f  mov     r8d, 1000000h
0x18014ed35  mov     byte ptr [rsp+0C18h+hTemplateFile], r14b
0x18014ed3a  mov     byte ptr [rsp+0C18h+dwFlagsAndAttributes], r14b
0x18014ed3f  mov     byte ptr [rsp+0C18h+dwCreationDisposition], r14b; int
0x18014ed44  mov     r9, 400000000000h
0x18014ed4e  lea     rdx, [rsp+0C18h+var_BD8]
0x18014ed53  lea     rcx, [rsp+0C18h+var_508]
0x18014ed5b  call    ??0AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@12@VTriggerLatency@12@_N@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency,bool)
0x18014ed60  nop
0x18014ed61  call    cs:__imp_GetLastError
0x18014ed67  mov     dword ptr [rsp+0C18h+lpFileName], eax
0x18014ed6e  lea     r13, aLasterror; "LastError"
0x18014ed75  mov     qword ptr [rsp+0C18h+var_BD8], r13
0x18014ed7a  lea     ebx, [rsi-37h]
0x18014ed7d  mov     qword ptr [rsp+0C18h+var_BD8+8], rbx
0x18014ed82  lea     r9, [rsp+0C18h+lpFileName]
0x18014ed8a  lea     r8, [rsp+0C18h+var_BD8]
0x18014ed8f  lea     rdx, [rsp+0C18h+var_A0]
0x18014ed97  lea     rcx, [rsp+0C18h+var_508]
0x18014ed9f  call    ??$AddField@K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBK@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<ulong>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,ulong const &)
0x18014eda4  xorps   xmm0, xmm0
0x18014eda7  movdqa  [rsp+0C18h+var_BC8], xmm0
0x18014edad  lea     rdx, [rsp+0C18h+var_BC8]
0x18014edb2  lea     rcx, [rsp+0C18h+lpFileName]
  ... truncated ...
```
