# Microsoft::Diagnostics::LifetimeManager::InitializeHost(void)

- ea: `0x1802549f8`
- end: `0x180257a25`
- name: `?InitializeHost@LifetimeManager@Diagnostics@Microsoft@@QEAAXXZ`
- size: `12333`
- prototype: `void __fastcall(Microsoft::Diagnostics::LifetimeManager *__hidden this)`
- caller_count: `1`
- callee_count: `158`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180254750`

## callees

- `0x1800137fc`
- `0x18001401c`
- `0x1800142e8`
- `0x180014fac`
- `0x1800154ac`
- `0x180016394`
- `0x18001c4e4`
- `0x18001cfe8`
- `0x18001d764`
- `0x18001fd84`
- `0x180020798`
- `0x180020a4c`
- `0x18002110c`
- `0x180021538`
- `0x18002b7c0`
- `0x18002b95c`
- `0x18002df00`
- `0x18002e06c`
- `0x180033de0`
- `0x180038524`
- `0x180039e6c`
- `0x18005ea74`
- `0x18005f35c`
- `0x1800624ac`
- `0x180064e34`
- `0x18006962c`
- `0x18006d2fc`
- `0x1800883d8`
- `0x18008a4ec`
- `0x180097bc8`
- `0x18009c6bc`
- `0x18009c8c0`
- `0x1800a34b0`
- `0x1800afab0`
- `0x1800bee8c`
- `0x1800c53b4`
- `0x1800d11c0`
- `0x1800d3790`
- `0x1800d39fc`
- `0x1800d77e4`
- `0x1800dce08`
- `0x1800e9a00`
- `0x1800f9c3c`
- `0x180100d24`
- `0x180102bbc`
- `0x180102e84`
- `0x180103130`
- `0x180108f10`
- `0x18010e7c0`
- `0x18010f8f4`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@K@Z` at `0x180255dca`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@K@Z` at `0x180255de9`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@K@Z` at `0x180255e08`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@K@Z` at `0x180255dca`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@K@Z` at `0x180255de9`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@K@Z` at `0x180255e08`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18025716b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180257243`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18025729c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18025716b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180257243`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18025729c`
- `ntdll!RtlGetVersion` at `0x180255db1`
- `ntdll!RtlGetVersion` at `0x180255db1`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180254d9b`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180254d9b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1802560a8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1802560a8`
- `UMPDC!Pdcv2ActivationClientRegister` at `0x180256119`
- `UMPDC!Pdcv2ActivationClientRegister` at `0x180256119`

## string_xrefs

- `0x180254c87`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x180254c9d`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x180256ada`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x180257083`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Microsoft::Diagnostics::LifetimeManager::InitializeHost(Microsoft::Diagnostics::LifetimeManager *this)
{
  Microsoft::Diagnostics::LifetimeManager *v1; // r15
  Microsoft::Diagnostics::LifetimeManager *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  Microsoft::Diagnostics::DevHealthMonTenant *v5; // rax
  Microsoft::Diagnostics::LifetimeManager *v6; // rcx
  Microsoft::Diagnostics::LifetimeManager *v7; // rcx
  Microsoft::Diagnostics::LifetimeManager *v8; // rcx
  __int64 v9; // r8
  int v10; // eax
  int Key; // eax
  unsigned int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 MutableDataCollectionRegistryKeyPath; // rax
  __int64 v28; // rax
  int v29; // eax
  int v30; // eax
  int v31; // ecx
  WCHAR *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rdx
  int Directory; // eax
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v39; // eax
  int v40; // eax
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  char IsEnabled; // al
  int v46; // eax
  __int64 v47; // rcx
  int v48; // eax
  int v49; // eax
  __int64 v50; // rcx
  int v51; // eax
  int v52; // eax
  int v53; // eax
  int v54; // eax
  int v55; // eax
  int v56; // eax
  int v57; // eax
  int v58; // eax
  int v59; // eax
  int v60; // eax
  int v61; // eax
  int v62; // eax
  int v63; // eax
  int v64; // eax
  int v65; // eax
  int v66; // eax
  int v67; // eax
  int v68; // eax
  int v69; // eax
  int v70; // eax
  int v71; // eax
  int v72; // eax
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rdx
  LPCWSTR *v78; // r8
  __int128 *v79; // rcx
  int v80; // ecx
  int v81; // r8d
  int v82; // r9d
  Microsoft::Diagnostics::DevHealthMonTenant *v83; // rax
  LPCWSTR *v84; // rax
  char v85; // bl
  _OWORD *v86; // rax
  int v87; // eax
  const WCHAR *v88; // rcx
  const char *v89; // r9
  int v90; // eax
  __int64 *v91; // rax
  __int64 v92; // rcx
  __int64 *v93; // rax
  __int64 v94; // rcx
  __int64 *v95; // rax
  __int64 v96; // rcx
  __int64 *v97; // rax
  __int64 v98; // rcx
  __int64 v99; // rax
  __int64 *v100; // rax
  __int64 v101; // rcx
  __int64 *v102; // rax
  __int64 v103; // rcx
  __int64 *v104; // rax
  __int64 v105; // rcx
  Microsoft::Diagnostics::EventMonitorManager *v106; // rbx
  __int64 *v107; // rax
  __int64 v108; // rcx
  __int64 v109; // rax
  __int64 v110; // r8
  Microsoft::Diagnostics::LifetimeManager *v111; // rcx
  __int64 v112; // rcx
  int v113; // eax
  __int64 v114; // rdi
  __int64 v115; // rbx
  struct Microsoft::Diagnostics::HeartbeatManager *HeartbeatManager; // rax
  __int64 *v117; // rax
  __int64 v118; // rcx
  Microsoft::Diagnostics::LifetimeManager *v119; // rcx
  __int64 v120; // rdi
  __int64 v121; // rbx
  struct Microsoft::Diagnostics::HeartbeatManager *v122; // rax
  __int64 v123; // r8
  __int64 *v124; // rax
  __int64 v125; // rcx
  __int64 *v126; // rax
  __int64 v127; // rcx
  __int64 *v128; // rax
  __int64 v129; // rcx
  bool v130; // dl
  __int64 v131; // rax
  __int64 v132; // rax
  __int64 v133; // rbx
  __int64 v134; // rax
  __int64 *v135; // rax
  __int64 v136; // rcx
  __int64 *v137; // rax
  __int64 v138; // rcx
  __int64 *v139; // rax
  __int64 v140; // rcx
  __int64 v141; // rax
  __int64 *v142; // rax
  __int64 v143; // rcx
  _QWORD *v144; // rax
  __int64 v145; // rax
  Microsoft::Diagnostics::ScenarioManager *v146; // rax
  Microsoft::Diagnostics::EnterpriseData *v147; // rcx
  const char *v148; // r9
  int v149; // ecx
  int v150; // r8d
  int v151; // r9d
  Microsoft::Diagnostics::DevHealthMonTenant *v152; // rax
  LPCWSTR *v153; // rax
  _QWORD *v154; // rdi
  __int64 v155; // rax
  __int64 v156; // rax
  __int64 matched; // rax
  __int64 v158; // rax
  __int64 *v159; // rax
  __int64 v160; // rcx
  __int64 v161; // rax
  __int64 *v162; // rax
  __int64 v163; // rcx
  __int64 v164; // rax
  __int64 *v165; // rax
  __int64 v166; // rcx
  __int64 v167; // rax
  __int64 v168; // rax
  Microsoft::Diagnostics::ScenariosSqliteTable *v169; // rdi
  __int64 v170; // rax
  __int64 v171; // rax
  __int64 RegistryConfig; // rax
  int v173; // ebx
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 *v176; // rax
  __int64 v177; // rcx
  Microsoft::Diagnostics::RemoteAggregatorManager *v178; // rcx
  const char *v179; // r9
  int v180; // eax
  HANDLE Thread; // rax
  const char *v182; // r9
  Microsoft::Diagnostics::ExporterManager *v183; // rcx
  _QWORD *started; // rbx
  HANDLE v185; // rax
  const char *v186; // r9
  HANDLE v187; // rax
  const char *v188; // r9
  Microsoft::Diagnostics::ApiServer *v189; // rcx
  int v190; // eax
  int v191; // eax
  int v192; // eax
  int v193; // eax
  int v194; // eax
  int v195; // eax
  int v196; // eax
  int v197; // eax
  int v198; // eax
  int v199; // eax
  Microsoft::Diagnostics::UtcWatchdog **v200; // rdi
  __int64 v201; // rbx
  __int64 v202; // r13
  int DwordAsBool; // eax
  int dwCreationFlags; // [rsp+20h] [rbp-768h]
  unsigned int dwCreationFlagsa; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsb; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsc; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsd; // [rsp+20h] [rbp-768h]
  int dwCreationFlagse; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsf; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsg; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsh; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsi; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsj; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsk; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsl; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsm; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsn; // [rsp+20h] [rbp-768h]
  int dwCreationFlagso; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsp; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsq; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsr; // [rsp+20h] [rbp-768h]
  int dwCreationFlagss; // [rsp+20h] [rbp-768h]
  int v224[4]; // [rsp+50h] [rbp-738h] BYREF
  __int64 v225; // [rsp+60h] [rbp-728h]
  bool v226[16]; // [rsp+70h] [rbp-718h] BYREF
  int v227[4]; // [rsp+80h] [rbp-708h] BYREF
  char v228; // [rsp+90h] [rbp-6F8h]
  int v229[4]; // [rsp+A0h] [rbp-6E8h] BYREF
  Microsoft::Diagnostics::DevHealthMonTenant *v230; // [rsp+C0h] [rbp-6C8h] BYREF
  HKEY hKeyDest; // [rsp+C8h] [rbp-6C0h] BYREF
  unsigned int v232[2]; // [rsp+D0h] [rbp-6B8h] BYREF
  unsigned int v233[2]; // [rsp+D8h] [rbp-6B0h] BYREF
  int v234[2]; // [rsp+E0h] [rbp-6A8h] BYREF
  Microsoft::Diagnostics::ScenariosSqliteTable *v235[2]; // [rsp+E8h] [rbp-6A0h] BYREF
  LPVOID *v236; // [rsp+F8h] [rbp-690h] BYREF
  LPVOID *v237; // [rsp+100h] [rbp-688h] BYREF
  __int16 v238; // [rsp+108h] [rbp-680h] BYREF
  char v239; // [rsp+10Ah] [rbp-67Eh]
  bool v240; // [rsp+10Bh] [rbp-67Dh]
  __int128 v241; // [rsp+110h] [rbp-678h] BYREF
  int v242; // [rsp+120h] [rbp-668h] BYREF
  __int64 v243; // [rsp+128h] [rbp-660h] BYREF
  Microsoft::Diagnostics::LifetimeManager *v244; // [rsp+130h] [rbp-658h]
  PSECURITY_DESCRIPTOR v245; // [rsp+138h] [rbp-650h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+140h] [rbp-648h] BYREF
  _QWORD v247[3]; // [rsp+148h] [rbp-640h] BYREF
  __int128 v248; // [rsp+160h] [rbp-628h]
  __int64 v249; // [rsp+170h] [rbp-618h]
  __int128 v250; // [rsp+178h] [rbp-610h]
  __int64 v251; // [rsp+188h] [rbp-600h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+190h] [rbp-5F8h] BYREF
  __int128 v253; // [rsp+2B0h] [rbp-4D8h] BYREF
  __int64 v254; // [rsp+2C0h] [rbp-4C8h]
  unsigned __int64 v255; // [rsp+2C8h] [rbp-4C0h]
  LPCWSTR lpFileName[3]; // [rsp+2D0h] [rbp-4B8h] BYREF
  unsigned __int64 v257; // [rsp+2E8h] [rbp-4A0h]
  WCHAR Src[16]; // [rsp+2F0h] [rbp-498h] BYREF
  WCHAR v259[8]; // [rsp+310h] [rbp-478h] BYREF
  __int64 v260; // [rsp+320h] [rbp-468h]
  unsigned __int64 v261; // [rsp+328h] [rbp-460h]
  _QWORD v262[4]; // [rsp+330h] [rbp-458h] BYREF
  WCHAR v263[16]; // [rsp+350h] [rbp-438h] BYREF
  WCHAR v264[16]; // [rsp+370h] [rbp-418h] BYREF
  WCHAR v265[16]; // [rsp+390h] [rbp-3F8h] BYREF
  _BYTE v266[16]; // [rsp+3B0h] [rbp-3D8h] BYREF
  _BYTE v267[8]; // [rsp+3C0h] [rbp-3C8h] BYREF
  _BYTE v268[232]; // [rsp+3C8h] [rbp-3C0h] BYREF
  _BYTE v269[224]; // [rsp+4B0h] [rbp-2D8h] BYREF
  _BYTE v270[224]; // [rsp+590h] [rbp-1F8h] BYREF
  _BYTE v271[224]; // [rsp+670h] [rbp-118h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+788h] [rbp+0h]

  v1 = this;
  v244 = this;
  v243 = 0;
  *(_OWORD *)v224 = *(_OWORD *)&off_1803843E0;
  *(_OWORD *)v227 = *(_OWORD *)&off_180370B28;
  if ( (int)Microsoft::Diagnostics::Utils::Registry::GetQword(-2147483646, v227, v224, &v243) >= 0 )
    _InterlockedExchange((volatile __int32 *)v1, v243);
  Microsoft::Diagnostics::InitialConsentManager::StartupConsentCheck((Microsoft::Diagnostics::LifetimeManager *)((char *)v1 + 8));
  *(_OWORD *)v224 = *(_OWORD *)&Microsoft::Diagnostics::LifetimeManager::k_csVer4_0String;
  std::wstring::wstring(v262, v224);
  *(_OWORD *)v224 = *(_OWORD *)&off_1803843D0;
  *(_OWORD *)v227 = *(_OWORD *)&off_180370B28;
  Microsoft::Diagnostics::Utils::Registry::GetString(-2147483646, v227, v224, v262);
  if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 16) )
  {
    v5 = (Microsoft::Diagnostics::DevHealthMonTenant *)v262;
    if ( v262[3] > 7u )
      v5 = (Microsoft::Diagnostics::DevHealthMonTenant *)v262[0];
    v230 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (unsigned int)&dword_1804543B0,
      (unsigned int)&unk_1803E5D38,
      v3,
      v4,
      (__int64)&v230);
  }
  v226[0] = 0;
  if ( !Microsoft::Diagnostics::LifetimeManager::WasCleanServiceShutdown(v2) )
  {
    v233[0] = 0;
    v232[0] = 0;
    Microsoft::Diagnostics::LifetimeManager::RecordDirtyShutdown(v6, v233, v232);
    v226[0] = Microsoft::Diagnostics::LifetimeManager::IsResetRequired(v7, v233[0], v232[0]);
    if ( v226[0] )
      Microsoft::Diagnostics::LifetimeManager::ResetState(v8);
  }
  Microsoft::Diagnostics::Utils::General::SetDiagTrackStatus(1);
  hKeyDest = 0;
  v242 = 0;
  *(_OWORD *)v227 = *(_OWORD *)&off_1803843C0;
  *(_QWORD *)v224 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack";
  *(_QWORD *)&v224[2] = 63;
  if ( (int)Microsoft::Diagnostics::Utils::Registry::GetDword(-2147483646, v224, v227, &v242) >= 0 )
  {
    v233[0] = 0;
    *(_OWORD *)v224 = *(_OWORD *)&off_1803843C0;
    *(_OWORD *)v227 = *(_OWORD *)&off_180370B28;
    if ( (int)Microsoft::Diagnostics::Utils::Registry::GetDword(-2147483646, v227, v224, v233) < 0 || v242 != v233[0] )
    {
      *(_OWORD *)v224 = *(_OWORD *)&off_180370B28;
      LOBYTE(v9) = 1;
      v10 = Microsoft::Diagnostics::Utils::Registry::DeleteTree(-2147483646, v224, v9);
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x188,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          (const char *)(unsigned int)v10,
          dwCreationFlags);
    }
  }
  *(_OWORD *)v224 = *(_OWORD *)&off_180370B28;
  if ( (int)Microsoft::Diagnostics::Utils::Registry::OpenKey(HKEY_LOCAL_MACHINE) < 0 )
  {
    *(_OWORD *)v224 = *(_OWORD *)&off_180370B28;
    Key = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
    if ( Key < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x18E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)Key,
        dwCreationFlagsa);
    std::wstring::wstring(Src, &off_180370B28);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src);
    *(_OWORD *)v227 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v229);
    *(_QWORD *)v224 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack";
    *(_QWORD *)&v224[2] = 63;
    if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v224, v227) )
    {
      v12 = RegCopyTreeW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack",
              hKeyDest);
      if ( v12 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x195,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          (const char *)v12,
          dwCreationFlagsa);
    }
    std::wstring::_Tidy_deallocate(Src);
  }
  *(_OWORD *)v224 = *(_OWORD *)&off_1803843A0;
  v13 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x199,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v13,
      dwCreationFlagsb);
  *(_OWORD *)v224 = *(_OWORD *)&off_1803843B0;
  v14 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19A,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v14,
      dwCreationFlagsc);
  *(_OWORD *)v224 = *(_OWORD *)&off_18036E9B0;
  v15 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v15,
      dwCreationFlagsd);
  *(_OWORD *)v224 = *(_OWORD *)&off_180384390;
  v16 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19C,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v16,
      dwCreationFlagse);
  *(_OWORD *)v224 = *(_OWORD *)&off_18036BA00;
  v17 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v17,
      dwCreationFlagsf);
  *(_OWORD *)v224 = *(_OWORD *)&off_18036BA10;
  v18 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v18,
      dwCreationFlagsg);
  *(_OWORD *)v224 = *(_OWORD *)&off_18036B9C0;
  v19 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v19,
      dwCreationFlagsh);
  *(_OWORD *)v224 = *(_OWORD *)&off_18036B9F0;
  v20 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A0,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v20,
      dwCreationFlagsi);
  *(_OWORD *)v224 = *(_OWORD *)&off_18036B9D0;
  v21 = Microsoft::Diagnostics::Utils::Registry::CreateGuaranteedVolatileKey(retaddr, v224, &hKeyDest);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A1,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v21,
      dwCreationFlagsi);
  *(_OWORD *)v224 = *(_OWORD *)&off_180384370;
  v22 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v22,
      dwCreationFlagsj);
  *(_OWORD *)v224 = *(_OWORD *)&off_180384380;
  v23 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v23,
      dwCreationFlagsk);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl'::`2'::impl) )
  {
    *(_OWORD *)v224 = *(_OWORD *)&off_180384360;
    v24 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A7,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v24,
        dwCreationFlagsl);
  }
  *(_OWORD *)v224 = *(_OWORD *)&off_18036B9B0;
  Microsoft::Diagnostics::Utils::Os::CreateSecurityDecriptorFromSddl(&SecurityDescriptor);
  *(_QWORD *)v224 = 24;
  *(_QWORD *)&v224[2] = SecurityDescriptor;
  v225 = 0;
  v248 = *(_OWORD *)v224;
  v249 = 0;
  *(_OWORD *)v224 = *(_OWORD *)&off_18036B9E0;
  v25 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v25 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1AD,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v25,
      dwCreationFlagsm);
  *(_OWORD *)v224 = *(_OWORD *)&off_180384350;
  Microsoft::Diagnostics::Utils::Os::CreateSecurityDecriptorFromSddl(&v245);
  *(_QWORD *)v224 = 24;
  *(_QWORD *)&v224[2] = v245;
  v225 = 0;
  v250 = *(_OWORD *)v224;
  v251 = 0;
  *(_OWORD *)v224 = *(_OWORD *)&off_180384340;
  v26 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v26,
      dwCreationFlagsn);
  MutableDataCollectionRegistryKeyPath = Microsoft::Diagnostics::Utils::Os::GetMutableDataCollectionRegistryKeyPath(lpFileName);
  v28 = std::operator+<wchar_t>(Src, MutableDataCollectionRegistryKeyPath, L"\\Users");
  *(_OWORD *)v224 = *(_OWORD *)std::wstring::operator std::wstring_view(v28, v227);
  v29 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B9,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v29,
      dwCreationFlagso);
  std::wstring::_Tidy_deallocate(Src);
  std::wstring::_Tidy_deallocate(lpFileName);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DmaUtcUpdate>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DmaUtcUpdate>::GetImpl'::`2'::impl) )
  {
    v30 = Microsoft::Diagnostics::LifetimeManager::PersistDmaApplicabilityToRegistry(v1);
    if ( v30 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1BE,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v30,
        dwCreationFlagso);
  }
  v230 = (Microsoft::Diagnostics::DevHealthMonTenant *)&qword_180460AD8;
  gsl::span<enum gsl::byte const,-1>::span<enum gsl::byte const,-1>(v224, &v230);
  *(_OWORD *)v227 = *(_OWORD *)&off_180371218;
  *(_OWORD *)v229 = *(_OWORD *)&off_180370B28;
  Microsoft::Diagnostics::Utils::Registry::SetBinary(v31, (int)v229, (int)v227, (int)v224, 0);
  std::wstring::wstring(v259, &off_18036BA40);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v259);
  v32 = v259;
  if ( v261 > 7 )
    v32 = *(WCHAR **)v259;
  v33 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(v32, v260, -1, 92);
  if ( v33 == -1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)0x80070057LL,
      dwCreationFlagsp);
  v34 = std::wstring::substr(v259, Src, 0, v33);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)std::wstring::operator std::wstring_view(v34, v229);
  LOBYTE(v35) = 1;
  Directory = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, v35, v224);
  if ( Directory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CB,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)Directory,
      dwCreationFlagsp);
  std::wstring::_Tidy_deallocate(Src);
  *(_OWORD *)v224 = *(_OWORD *)&off_18036BA50;
  *(_OWORD *)v227 = *(_OWORD *)std::wstring::operator std::wstring_view(v259, v229);
  Microsoft::Diagnostics::LifetimeManager::EnsureAclsOnFolder(v37, v227, (__int128 *)v224);
  std::wstring::wstring(v265, &off_180384330);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v265);
  *(_OWORD *)v224 = *(_OWORD *)&off_180384320;
  *(_OWORD *)v227 = *(_OWORD *)std::wstring::operator std::wstring_view(v265, v229);
  Microsoft::Diagnostics::LifetimeManager::EnsureAclsOnFolder(v38, v227, (__int128 *)v224);
  *(_OWORD *)v224 = *(_OWORD *)&off_18036BA50;
  *(_OWORD *)v227 = *(_OWORD *)&off_18036BA40;
  v39 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v39 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D7,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v39,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_18036BA20;
  v40 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v40 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D9,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v40,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_180371F90;
  v41 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v41 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DA,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v41,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_180371F80;
  v42 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v42 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DB,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v42,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_180371208;
  v43 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v43 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DC,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v43,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_180371FA0;
  v44 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v44 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v44,
      dwCreationFlagsp);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UsageAndQualityInsights>::GetImpl'::`2'::impl) )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl'::`2'::impl);
    *(_OWORD *)v224 = *(_OWORD *)&off_180384300;
    if ( IsEnabled )
    {
      *(_OWORD *)v227 = *(_OWORD *)&off_180384310;
      v49 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
      if ( v49 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1E3,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          (const char *)(unsigned int)v49,
          dwCreationFlagsp);
      std::wstring::wstring(Src, &off_180384310);
      Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src);
      *(_OWORD *)v224 = *(_OWORD *)&off_180384300;
      *(_OWORD *)v227 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v229);
      Microsoft::Diagnostics::LifetimeManager::EnsureAclsOnFolder(v50, v227, (__int128 *)v224);
    }
    else
    {
      *(_OWORD *)v227 = *(_OWORD *)&off_180371FA0;
      v46 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
      if ( v46 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1EA,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          (const char *)(unsigned int)v46,
          dwCreationFlagsp);
      std::wstring::wstring(Src, &off_180371FA0);
      Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src);
      *(_OWORD *)v224 = *(_OWORD *)&off_180384300;
      *(_OWORD *)v227 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v229);
      Microsoft::Diagnostics::LifetimeManager::EnsureAclsOnFolder(v47, v227, (__int128 *)v224);
    }
    std::wstring::_Tidy_deallocate(Src);
  }
  else
  {
    memset(v224, 0, sizeof(v224));
    *(_OWORD *)v227 = *(_OWORD *)&off_180371FA0;
    v51 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
    if ( v51 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F3,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v51,
        dwCreationFlagsp);
  }
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_1803842E0;
  v48 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v48 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F6,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v48,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_1803842F0;
  v52 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v52 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F7,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v52,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&Microsoft::Diagnostics::AlternativeSlot::k_traceProfileLocalStoreDirectory;
  v53 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v53 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F8,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v53,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&Microsoft::Diagnostics::ETWConsumer::k_etlFilesPath;
  v54 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v54 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F9,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v54,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&Microsoft::Diagnostics::ETWConsumer::k_autologgerFilesPath;
  v55 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v55 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FA,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v55,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&Microsoft::Diagnostics::ETWConsumer::k_dtShutdownLoggerStorePath;
  v56 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v56 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FB,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v56,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_1803842A0;
  v57 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v57 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v57,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_1803842B0;
  v58 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v58 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FD,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v58,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_180384280;
  v59 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v59 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FE,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v59,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_180384290;
  v60 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v60 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FF,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v60,
      dwCreationFlagsp);
  *(_OWORD *)v224 = *(_OWORD *)&off_180384320;
  *(_OWORD *)v227 = *(_OWORD *)&off_180384330;
  v61 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v61 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x200,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v61,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_180384440;
  v62 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v62 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x201,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v62,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_180384260;
  v63 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v63 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x202,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v63,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_180384270;
  v64 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v64 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x203,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v64,
      dwCreationFlagsp);
  std::wstring::wstring(v264, &off_180384250);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v264);
  *(_OWORD *)v224 = *(_OWORD *)std::wstring::operator std::wstring_view(v264, v227);
  v65 = Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)v224);
  if ( v65 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x209,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v65,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_180384250;
  v66 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v66 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v66,
      dwCreationFlagsp);
  *(_OWORD *)v224 = *(_OWORD *)&off_18036BA60;
  v67 = Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)v224);
  if ( v67 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v67,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_18036BA60;
  v68 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v68 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v68,
      dwCreationFlagsp);
  *(_OWORD *)v224 = *(_OWORD *)&off_180384240;
  v69 = Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)v224);
  if ( v69 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x212,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v69,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_180384240;
  v70 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v70 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x213,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v70,
      dwCreationFlagsp);
  *(_OWORD *)v224 = *(_OWORD *)&off_180384230;
  v71 = Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)v224);
  if ( v71 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x216,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v71,
      dwCreationFlagsp);
  memset(v224, 0, sizeof(v224));
  *(_OWORD *)v227 = *(_OWORD *)&off_180384230;
  v72 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
  if ( v72 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x217,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v72,
      dwCreationFlagsp);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v266);
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( RtlGetVersion(&VersionInformation) < 0 )
  {
    std::operator<<<std::char_traits<char>>(v267, "0.0.0");
  }
  else
  {
    v73 = std::ostream::operator<<(v267, VersionInformation.dwMajorVersion);
    v74 = std::operator<<<std::char_traits<char>>(v73, ".");
    v75 = std::ostream::operator<<(v74, VersionInformation.dwMinorVersion);
    v76 = std::operator<<<std::char_traits<char>>(v75, ".");
    std::ostream::operator<<(v76, VersionInformation.dwBuildNumber);
  }
  std::stringbuf::str(v268, lpFileName);
  std::wstring::wstring(Src, &off_180384460);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src);
  v253 = 0;
  v254 = 0;
  v255 = 15;
  LOBYTE(v253) = 0;
  *(_OWORD *)v224 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v227);
  if ( (int)Microsoft::Diagnostics::Utils::FileSystem::ReadStringFromFile(v224, v77, 0xFFFFFFFFLL, &v253) < 0 )
    goto LABEL_253;
  v78 = lpFileName;
  if ( v257 > 0xF )
    v78 = (LPCWSTR *)lpFileName[0];
  v79 = &v253;
  if ( v255 > 0xF )
    v79 = (__int128 *)v253;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<char>>(v79, v254, v78, lpFileName[2]) )
  {
    v228 = 0;
    if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 16) )
    {
      v83 = (Microsoft::Diagnostics::DevHealthMonTenant *)&v253;
      if ( v255 > 0xF )
        v83 = (Microsoft::Diagnostics::DevHealthMonTenant *)v253;
      v230 = v83;
      v84 = lpFileName;
      if ( v257 > 0xF )
        v84 = (LPCWSTR *)lpFileName[0];
      *(_QWORD *)v234 = v84;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v80,
        (unsigned int)byte_1803E5B2D,
        v81,
        v82,
        (__int64)v234,
        (__int64)&v230);
    }
    v85 = v228;
  }
  else
  {
LABEL_253:
    if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 16) )
    {
      v152 = (Microsoft::Diagnostics::DevHealthMonTenant *)&v253;
      if ( v255 > 0xF )
        v152 = (Microsoft::Diagnostics::DevHealthMonTenant *)v253;
      v230 = v152;
      v153 = lpFileName;
      if ( v257 > 0xF )
        v153 = (LPCWSTR *)lpFileName[0];
      *(_QWORD *)v234 = v153;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v149,
        (unsigned int)&unk_1803E5B80,
        v150,
        v151,
        (__int64)v234,
        (__int64)&v230);
    }
    v85 = 1;
    v228 = 1;
  }
  v86 = (_OWORD *)gslp::container_to_bytes<std::string>(v235, lpFileName);
  *(_QWORD *)v224 = &::Src;
  *(_QWORD *)&v224[2] = 0;
  *(_OWORD *)v227 = *v86;
  *(_OWORD *)v229 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, &v241);
  v87 = Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile(v229, v227, v224);
  if ( v87 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v87,
      dwCreationFlagsp);
  std::string::_Tidy_deallocate(&v253);
  std::wstring::_Tidy_deallocate(Src);
  std::string::_Tidy_deallocate(lpFileName);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(v266);
  if ( v85 )
  {
    std::wstring::wstring(lpFileName, &Microsoft::Diagnostics::ETWConsumer::k_dtAutoLoggerShutdownOutputLocation);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)lpFileName);
    v88 = (const WCHAR *)lpFileName;
    if ( v257 > 7 )
      v88 = lpFileName[0];
    if ( !DeleteFileW(v88) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x25D,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        v89);
    std::wstring::_Tidy_deallocate(lpFileName);
  }
  v247[0] = 1;
  v247[1] = &Microsoft::Diagnostics::PdcNetworkActivation::PdcActivatorCallback;
  v247[2] = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    (char *)v1 + 2264,
    0);
  v90 = Pdcv2ActivationClientRegister(77, v247, (char *)v1 + 2264);
  if ( v90 < 0 )
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0x266,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v90,
      dwCreationFlagsp);
  Microsoft::CommonDatapoints::UpdateStaticCommonDatapointsInRegistry();
  v91 = (__int64 *)std::make_unique<Microsoft::Diagnostics::UserManager,,0>(&v230);
  v92 = *v91;
  *v91 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 262, v92);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v230);
  v238 = 1;
  v239 = 0;
  v240 = v226[0];
  v93 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SettingsManager,Microsoft::Diagnostics::SettingsManagerConfig &,0>(
                     &v236,
                     &v238);
  v94 = *v93;
  *v93 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 235, v94);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v236);
  v95 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SevilleEventlogManager,,0>(&v237);
  v96 = *v95;
  *v95 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 271, v96);
  std::unique_ptr<Microsoft::Diagnostics::SevilleEventlogManager>::~unique_ptr<Microsoft::Diagnostics::SevilleEventlogManager>(&v237);
  v97 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SyntheticAggregationManager,,0>(v233);
  v98 = *v97;
  *v97 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 278, v98);
  std::unique_ptr<Microsoft::Diagnostics::SyntheticAggregationManager>::~unique_ptr<Microsoft::Diagnostics::SyntheticAggregationManager>(v233);
  v99 = std::make_unique<Microsoft::Diagnostics::ProxySourceRegistry,,0>(v232);
  v100 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SystemStateManager,std::unique_ptr<Microsoft::Diagnostics::ProxySourceMutable>,0>(
                      &v230,
                      v99);
  v101 = *v100;
  *v100 = 0;
  *(_QWORD *)v224 = (char *)v1 + 2064;
  _InterlockedExchange64((volatile __int64 *)v1 + 258, v101);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v230);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v232);
  LOBYTE(v232[0]) = 1;
  v102 = (__int64 *)std::make_unique<Microsoft::Diagnostics::HeartbeatManager,bool,wil::basic_zstring_view<wchar_t> const &,std::bitset<9> const &,0>(
                      &v253,
                      v232,
                      &Microsoft::Diagnostics::HeartBeat::k_defaultHeartBeatName,
                      &Microsoft::Diagnostics::HeartBeat::k_defaultHeartBeatSections);
  v103 = *v102;
  *v102 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 254, v103);
  std::unique_ptr<Microsoft::Diagnostics::HeartbeatManager>::~unique_ptr<Microsoft::Diagnostics::HeartbeatManager>(&v253);
  v104 = (__int64 *)std::make_unique<Microsoft::Diagnostics::PrivacyKeyManager,,0>(&v241);
  v105 = *v104;
  *v104 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 246, v105);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v241);
  v106 = (Microsoft::Diagnostics::EventMonitorManager *)operator new(0x550u);
  *(_QWORD *)v227 = v106;
  *(_OWORD *)v229 = *(_OWORD *)std::wstring::operator std::wstring_view(qword_1804634A0, &v241);
  Microsoft::Diagnostics::EventMonitorManager::EventMonitorManager(v106);
  *(_QWORD *)&v241 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 264, (__int64)v106);
  std::unique_ptr<Microsoft::Diagnostics::EventMonitorManager>::~unique_ptr<Microsoft::Diagnostics::EventMonitorManager>(&v241);
  v107 = (__int64 *)std::make_unique<Microsoft::Diagnostics::EnterpriseData,,0>(v235);
  v108 = *v107;
  *v107 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 251, v108);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v235);
  *(_QWORD *)v227 = operator new(0x108u);
  v109 = Microsoft::Diagnostics::RegionMetadata::RegionMetadata(*(Microsoft::Diagnostics::RegionMetadata **)v227);
  v235[0] = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 282, v109);
  std::unique_ptr<Microsoft::Diagnostics::RegionMetadata>::~unique_ptr<Microsoft::Diagnostics::RegionMetadata>(v235);
  v233[0] = 0;
  *(_OWORD *)v227 = *(_OWORD *)&off_180384450;
  *(_OWORD *)v229 = *(_OWORD *)&off_180370B28;
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateRegistryConfig(
    (unsigned int)v271,
    (unsigned int)v233,
    (unsigned int)v229,
    (unsigned int)v227,
    0);
  LODWORD(v230) = Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(v271);
  LOBYTE(v110) = 1;
  Microsoft::Diagnostics::LifetimeManager::GetAuthorizationInfo(v1, v234, v110);
  v111 = (Microsoft::Diagnostics::LifetimeManager *)*((unsigned int *)v1 + 568);
  if ( ((unsigned __int8)v111 & 4) == 0 )
  {
    v112 = (unsigned int)dword_1804543B0;
    if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 16) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1804543B0,
        word_1803E5AAA);
    *(_OWORD *)v227 = *(_OWORD *)&off_180371F50;
    *(_OWORD *)v229 = *(_OWORD *)&off_180370B28;
    v113 = Microsoft::Diagnostics::Utils::Registry::DeleteValue(v112, v229, v227);
    v111 = retaddr;
    if ( v113 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2A2,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v113,
        dwCreationFlagsq);
  }
  v234[0] = Microsoft::Diagnostics::LifetimeManager::GetUtcDefaultEventStoreSize(v111);
  std::wstring::wstring(v263, &off_18036BA20);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v263);
  v114 = std::make_unique<Microsoft::Diagnostics::XboxToastEventStoreUsageCallback,,0>(&v241);
  LOWORD(v232[0]) = 256;
  *(_QWORD *)v227 = v232;
  *(_QWORD *)&v227[2] = (char *)v232 + 2;
  v115 = std::vector<Microsoft::Diagnostics::StorageBufferType>::vector<Microsoft::Diagnostics::StorageBufferType>(
           v229,
           v227);
  v233[0] = Microsoft::Diagnostics::AsimovEventBuffer::GetEventBufferMaxBytes();
  LODWORD(v237) = Microsoft::Diagnostics::AsimovEventBuffer::GetCriticalEventBufferMaxEvents();
  LODWORD(v236) = Microsoft::Diagnostics::AsimovEventBuffer::GetNormalEventBufferMaxEvents();
  HeartbeatManager = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager(v1);
  v117 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SqliteEventStore,Microsoft::Diagnostics::HeartBeat &,std::wstring &,unsigned long &,unsigned long,unsigned long,unsigned long,std::vector<Microsoft::Diagnostics::StorageBufferType> &,std::unique_ptr<Microsoft::Diagnostics::SevilleEventStoreUsageCallback>,0>(
                      v235,
                      HeartbeatManager,
                      v263,
                      v234,
                      &v236,
                      &v237,
                      v233,
                      v115,
                      v114);
  v118 = *v117;
  *v117 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 244, v118);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v235);
  std::vector<Microsoft::Diagnostics::UploadLatency>::_Tidy(v229);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v241);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LocalEncryptCertRemoval>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LocalEncryptCertRemoval>::GetImpl'::`2'::impl) )
  {
    v233[0] = Microsoft::Diagnostics::LifetimeManager::GetUtcDefaultInMemoryEventStoreSize(v119);
    v120 = std::make_unique<Microsoft::Diagnostics::XboxToastEventStoreUsageCallback,,0>(&v241);
    LOWORD(v232[0]) = 256;
    *(_QWORD *)v227 = v232;
    *(_QWORD *)&v227[2] = (char *)v232 + 2;
    v121 = std::vector<Microsoft::Diagnostics::StorageBufferType>::vector<Microsoft::Diagnostics::StorageBufferType>(
             v229,
             v227);
    v234[0] = 102400;
    LODWORD(v236) = 50;
    LODWORD(v237) = 0;
    v122 = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager(v1);
    v124 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SqliteEventStore,Microsoft::Diagnostics::HeartBeat &,wchar_t const (&)[1],unsigned long const &,unsigned long,unsigned long,unsigned long,std::vector<Microsoft::Diagnostics::StorageBufferType>,std::unique_ptr<Microsoft::Diagnostics::XboxToastEventStoreUsageCallback>,0>(
                        v235,
                        v122,
                        v123,
                        v233,
                        &v237,
                        &v236,
                        v234,
                        v121,
                        v120);
    v125 = *v124;
    *v124 = 0;
    _InterlockedExchange64((volatile __int64 *)v1 + 245, v125);
    std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v235);
    std::vector<Microsoft::Diagnostics::UploadLatency>::_Tidy(v229);
    std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v241);
    if ( (unsigned int)dword_1804543B0 > 4 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 48) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_1804543B0,
          word_1803E5A72);
    }
  }
  v126 = (__int64 *)std::make_unique<Microsoft::Diagnostics::ScenarioCounterStorage,,0>(v235);
  v127 = *v126;
  *v126 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 249, v127);
  std::unique_ptr<Microsoft::Diagnostics::ScenarioCounterStorage>::~unique_ptr<Microsoft::Diagnostics::ScenarioCounterStorage>(v235);
  v128 = (__int64 *)std::make_unique<Microsoft::Diagnostics::LatencyData,,0>(&v241);
  v129 = *v128;
  *v128 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 255, v129);
  std::unique_ptr<Microsoft::Diagnostics::LatencyData>::~unique_ptr<Microsoft::Diagnostics::LatencyData>(&v241);
  *(_QWORD *)v227 = operator new(0x620u);
  v131 = Microsoft::Diagnostics::UsageAnalyzer::UsageAnalyzer(*(Microsoft::Diagnostics::UsageAnalyzer **)v227, v130);
  v235[0] = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 259, v131);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v235);
  *(_QWORD *)v227 = operator new(0xB70u);
  v132 = Microsoft::Diagnostics::EventTranscriptManager::EventTranscriptManager(*(Microsoft::Diagnostics::EventTranscriptManager **)v227);
  v235[0] = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 260, v132);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v235);
  *(_QWORD *)v227 = operator new(0x2A0u);
  v133 = Microsoft::Diagnostics::AsimovEndpointConfig::AsimovEndpointConfig(*(Microsoft::Diagnostics::AsimovEndpointConfig **)v227);
  v237 = (LPVOID *)v133;
  *(_QWORD *)v227 = operator new(0x330u);
  *(_QWORD *)v234 = 0;
  v237 = 0;
  v236 = (LPVOID *)v133;
  v134 = Microsoft::Diagnostics::AsimovUploadQueue::AsimovUploadQueue(*(_QWORD *)v227, &v236, v234, 180000);
  v235[0] = 0;
  *(_QWORD *)v227 = (char *)v1 + 2016;
  _InterlockedExchange64((volatile __int64 *)v1 + 252, v134);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v235);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v237);
  v135 = (__int64 *)std::make_unique<Microsoft::Diagnostics::AsimovEventSerializer,,0>(&v253);
  v136 = *v135;
  *v135 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 253, v136);
  std::unique_ptr<Microsoft::Diagnostics::AsimovEventSerializer>::~unique_ptr<Microsoft::Diagnostics::AsimovEventSerializer>(&v253);
  v137 = (__int64 *)std::make_unique<Microsoft::Diagnostics::KillSwitchManager,,0>(v233);
  v138 = *v137;
  *v137 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 270, v138);
  std::unique_ptr<Microsoft::Diagnostics::KillSwitchManager>::~unique_ptr<Microsoft::Diagnostics::KillSwitchManager>(v233);
  v139 = (__int64 *)std::make_unique<Microsoft::Diagnostics::EscalationEngine,,0>(v232);
  v140 = *v139;
  *v139 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 247, v140);
  std::unique_ptr<Microsoft::Diagnostics::EscalationEngine>::~unique_ptr<Microsoft::Diagnostics::EscalationEngine>(v232);
  v235[0] = (Microsoft::Diagnostics::ScenariosSqliteTable *)operator new(0x138u);
  v241 = *(_OWORD *)&off_180371208;
  v141 = Microsoft::Diagnostics::ScenariosSqliteTable::ScenariosSqliteTable(v235[0]);
  v235[0] = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 273, v141);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v235);
  v142 = (__int64 *)std::make_unique<Microsoft::Diagnostics::ScenarioObjectCache,,0>(v229);
  v143 = *v142;
  *v142 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 274, v143);
  std::unique_ptr<Microsoft::Diagnostics::ScenarioObjectCache>::~unique_ptr<Microsoft::Diagnostics::ScenarioObjectCache>(v229);
  v144 = operator new(8u);
  *v144 = &Microsoft::Diagnostics::ScenarioStorageSql::`vftable';
  *(_QWORD *)v229 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 257, (__int64)v144);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v229);
  *(_QWORD *)v229 = operator new(0x220u);
  v145 = Microsoft::Diagnostics::ScenarioCacheLRU::ScenarioCacheLRU(*(Microsoft::Diagnostics::ScenarioCacheLRU **)v229);
  *(_QWORD *)v229 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 256, v145);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v229);
  *(_QWORD *)v229 = operator new(0x528u);
  v146 = Microsoft::Diagnostics::ScenarioManager::ScenarioManager(*(Microsoft::Diagnostics::ScenarioManager **)v229);
  *(_QWORD *)v229 = 0;
  *(_QWORD *)v233 = (char *)v1 + 1904;
  _InterlockedExchange64((volatile __int64 *)v1 + 238, (__int64)v146);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v229);
  if ( *((_BYTE *)v1 + 2278) )
    *(_BYTE *)(*((_QWORD *)v1 + 238) + 618LL) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DpswOneSettingsControl>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_DpswOneSettingsControl>::GetImpl'::`2'::impl);
  v147 = (Microsoft::Diagnostics::EnterpriseData *)*((_QWORD *)v1 + 251);
  if ( v147 )
  {
    try
    {
      Microsoft::Diagnostics::EnterpriseData::Initialize(v147);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x2FA,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        v148);
      v1 = v244;
    }
  }
  v154 = operator new(0x60u);
  *(_QWORD *)v229 = v154;
  memset_0(v154, 0, 0x60u);
  *v154 = 258;
  *(_OWORD *)(v154 + 3) = 0;
  *(_OWORD *)(v154 + 5) = 0;
  *(_OWORD *)(v154 + 7) = 0;
  v154[1] = 0;
  v154[2] = 0;
  *((_DWORD *)v154 + 18) = -1;
  *((_DWORD *)v154 + 19) = 0;
  v154[10] = 0;
  v154[11] = 0;
  v155 = std::_Allocate<16,std::_Default_allocate_traits>(56);
  *(_QWORD *)v155 = v155;
  *(_QWORD *)(v155 + 8) = v155;
  *(_QWORD *)(v155 + 16) = v155;
  *(_WORD *)(v155 + 24) = 257;
  v154[10] = v155;
  *(_QWORD *)v229 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 266, (__int64)v154);
  std::unique_ptr<Microsoft::Diagnostics::TelemetryAssert>::~unique_ptr<Microsoft::Diagnostics::TelemetryAssert>(v229);
  *(_QWORD *)v229 = operator new(0x48u);
  v156 = Microsoft::Diagnostics::OsEvents::OsEvents(*(Microsoft::Diagnostics::OsEvents **)v229);
  *(_QWORD *)v229 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 242, v156);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v229);
  *(_QWORD *)v229 = operator new(0x188u);
  matched = Microsoft::Diagnostics::MatchEngine::MatchEngine(*(Microsoft::Diagnostics::MatchEngine **)v229);
  *(_QWORD *)v229 = 0;
  v237 = (LPVOID *)((char *)v1 + 1888);
  _InterlockedExchange64((volatile __int64 *)v1 + 236, matched);
  std::unique_ptr<Microsoft::Diagnostics::MatchEngine>::~unique_ptr<Microsoft::Diagnostics::MatchEngine>(v229);
  *(_QWORD *)v229 = operator new(0x440u);
  v158 = Microsoft::Diagnostics::TriggerListener::TriggerListener(*(Microsoft::Diagnostics::TriggerListener **)v229);
  *(_QWORD *)v229 = 0;
  v236 = (LPVOID *)((char *)v1 + 1920);
  _InterlockedExchange64((volatile __int64 *)v1 + 240, v158);
  std::unique_ptr<Microsoft::Diagnostics::TriggerListener>::~unique_ptr<Microsoft::Diagnostics::TriggerListener>(v229);
  v159 = (__int64 *)std::make_unique<Microsoft::Diagnostics::TraceManager,,0>(v235);
  v160 = *v159;
  *v159 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 248, v160);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v235);
  *(_QWORD *)v229 = operator new(0x158u);
  v161 = Microsoft::Diagnostics::MetadataEngine::MetadataEngine(*(Microsoft::Diagnostics::MetadataEngine **)v229, 0);
  *(_QWORD *)v229 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 250, v161);
  std::unique_ptr<Microsoft::Diagnostics::MetadataEngine>::~unique_ptr<Microsoft::Diagnostics::MetadataEngine>(v229);
  v162 = (__int64 *)std::make_unique<Microsoft::Diagnostics::DTraceManager,,0>(&v241);
  v163 = *v162;
  *v162 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 276, v163);
  std::unique_ptr<Microsoft::Diagnostics::DTraceManager>::~unique_ptr<Microsoft::Diagnostics::DTraceManager>(&v241);
  *(_QWORD *)v229 = operator new(0x80u);
  v164 = Microsoft::Diagnostics::PiiScrubberManager::PiiScrubberManager(*(Microsoft::Diagnostics::PiiScrubberManager **)v229);
  *(_QWORD *)v229 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 277, v164);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v229);
  v165 = (__int64 *)std::make_unique<Microsoft::Diagnostics::UtcWatchdog,,0>(&v253);
  v166 = *v165;
  *v165 = 0;
  *(_QWORD *)v232 = (char *)v1 + 2152;
  _InterlockedExchange64((volatile __int64 *)v1 + 269, v166);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v253);
  *(_QWORD *)v229 = operator new(0x10u);
  v167 = Microsoft::Diagnostics::TenantManager::TenantManager(*(Microsoft::Diagnostics::TenantManager **)v229);
  *(_QWORD *)v229 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 263, v167);
  std::unique_ptr<Microsoft::Diagnostics::TenantManager>::~unique_ptr<Microsoft::Diagnostics::TenantManager>(v229);
  *(_QWORD *)v229 = operator new(0x400u);
  v168 = Microsoft::Diagnostics::UtcApiManager::UtcApiManager(*(Microsoft::Diagnostics::UtcApiManager **)v229);
  *(_QWORD *)v229 = 0;
  v169 = (Microsoft::Diagnostics::LifetimeManager *)((char *)v1 + 2088);
  v235[0] = (Microsoft::Diagnostics::LifetimeManager *)((char *)v1 + 2088);
  _InterlockedExchange64((volatile __int64 *)v1 + 261, v168);
  std::unique_ptr<Microsoft::Diagnostics::AgentUtcApiManager>::~unique_ptr<Microsoft::Diagnostics::AgentUtcApiManager>(v229);
  *(_QWORD *)v229 = operator new(0x930u);
  v241 = *(_OWORD *)&Microsoft::Diagnostics::ETWConsumer::k_dtSessionName;
  v170 = Microsoft::Diagnostics::TriggerAggregator::TriggerAggregator(*(_QWORD *)v229, &v241);
  *(_QWORD *)v229 = 0;
  *(_QWORD *)&v241 = (char *)v1 + 2240;
  _InterlockedExchange64((volatile __int64 *)v1 + 280, v170);
  std::unique_ptr<Microsoft::Diagnostics::TriggerAggregator>::~unique_ptr<Microsoft::Diagnostics::TriggerAggregator>(v229);
  *(_QWORD *)v229 = operator new(0x90u);
  v171 = Microsoft::Diagnostics::AggregatedEventManager::AggregatedEventManager(*(Microsoft::Diagnostics::AggregatedEventManager **)v229);
  *(_QWORD *)v229 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 281, v171);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v229);
  v234[0] = 0;
  *(_OWORD *)v229 = *(_OWORD *)&off_180384210;
  v253 = *(_OWORD *)&off_180370B28;
  RegistryConfig = Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateRegistryConfig(
                     (unsigned int)v266,
                     (unsigned int)v234,
                     (unsigned int)&v253,
                     (unsigned int)v229,
                     0);
  v173 = Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(RegistryConfig);
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v266);
  if ( v173 == 1 )
  {
    *(_QWORD *)v229 = operator new(0xE8u);
    v174 = Microsoft::Diagnostics::ExporterManager::ExporterManager(*(Microsoft::Diagnostics::ExporterManager **)v229);
    *(_QWORD *)v229 = 0;
    _InterlockedExchange64((volatile __int64 *)v1 + 279, v174);
    std::unique_ptr<Microsoft::Diagnostics::ExporterManager>::~unique_ptr<Microsoft::Diagnostics::ExporterManager>(v229);
  }
  else if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 16) )
  {
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1804543B0,
      &byte_1803E5A3F);
  }
  *(_QWORD *)v229 = operator new(0x8D8u);
  v175 = Microsoft::Diagnostics::RemoteAggregatorManager::RemoteAggregatorManager(*(Microsoft::Diagnostics::RemoteAggregatorManager **)v229);
  *(_QWORD *)v229 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 275, v175);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v229);
  if ( *((_BYTE *)v1 + 2288)
    || (_DWORD)v230 != *((_DWORD *)v1 + 568)
    && (*((_DWORD *)v1 + 568) & 8) == 0
    && (*((_DWORD *)v1 + 568) & 0x400) == 0
    && ((unsigned __int8)v230 & 4) != 0 )
  {
    Microsoft::Diagnostics::LifetimeManager::ClearEventStoresOnOptInChange(v1);
  }
  LODWORD(v230) = 0;
  *(_OWORD *)v229 = *(_OWORD *)&off_180384200;
  v253 = *(_OWORD *)&off_180370B28;
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateRegistryConfig(
    (unsigned int)v270,
    (unsigned int)&v230,
    (unsigned int)&v253,
    (unsigned int)v229,
    0);
  if ( (unsigned int)Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(v270) != 1 )
  {
    v176 = (__int64 *)std::make_unique<Microsoft::Diagnostics::AgentManager,,0>(v229);
    v177 = *v176;
    *v176 = 0;
    _InterlockedExchange64((volatile __int64 *)v1 + 265, v177);
    std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v229);
  }
  Microsoft::Diagnostics::AsimovUploadQueue::StartTimers(**(Microsoft::Diagnostics::AsimovUploadQueue ***)v227);
  v230 = 0;
  *(_OWORD *)v227 = *(_OWORD *)&off_180372110;
  Microsoft::Diagnostics::TenantManager::GetTenant(*((_QWORD *)v1 + 263), v227, &v230);
  if ( v230 )
    Microsoft::Diagnostics::DevHealthMonTenant::StartMdmListener(v230);
  Microsoft::Diagnostics::SystemStateManager::BeginTrackingSystemState(**(Microsoft::Diagnostics::SystemStateManager ***)v224);
  v178 = (Microsoft::Diagnostics::RemoteAggregatorManager *)*((_QWORD *)v1 + 275);
  if ( v178 )
  {
    try
    {
      Microsoft::Diagnostics::RemoteAggregatorManager::Initialize(v178);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x34E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        v179);
      v1 = v244;
      v169 = v235[0];
    }
  }
  LODWORD(v230) = 0;
  *(_OWORD *)v224 = *(_OWORD *)&off_1803841E0;
  *(_OWORD *)v227 = *(_OWORD *)&off_180370B28;
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateRegistryConfig(
    (unsigned int)v269,
    (unsigned int)&v230,
    (unsigned int)v227,
    (unsigned int)v224,
    0);
  if ( (unsigned int)Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(v269) == 1 )
  {
    memset(v224, 0, sizeof(v224));
    *(_OWORD *)v227 = *(_OWORD *)&off_1803841F0;
    v180 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v227, 0, v224);
    if ( v180 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x357,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v180,
        dwCreationFlagsr);
  }
  Thread = CreateThread(0, 0xB000u, Microsoft::Diagnostics::MatchEngine::StartMatchEngine, *v237, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)v1 + 1896,
    Thread);
  if ( ((*((_QWORD *)v1 + 237) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x35C,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      v182);
  v183 = (Microsoft::Diagnostics::ExporterManager *)*((_QWORD *)v1 + 279);
  if ( v183 )
    Microsoft::Diagnostics::ExporterManager::Initialize(v183);
  started = (_QWORD *)Microsoft::Diagnostics::TriggerListener::StartConsumerThreads(*v236, v224);
  if ( (_QWORD *)((char *)v1 + 2328) != started )
  {
    std::vector<std::pair<std::string_view,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>::_Tidy((char *)v1 + 2328);
    *((_QWORD *)v1 + 291) = *started;
    *((_QWORD *)v1 + 292) = started[1];
    *((_QWORD *)v1 + 293) = started[2];
    *started = 0;
    started[1] = 0;
    started[2] = 0;
  }
  std::vector<std::pair<std::string_view,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>::_Tidy(v224);
  Microsoft::Diagnostics::TriggerAggregator::StartAggregation(*(Microsoft::Diagnostics::TriggerAggregator **)v241);
  v185 = CreateThread(0, 0x8000u, Microsoft::Diagnostics::TriggerListener::StartThread, *v236, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)v1 + 1928,
    v185);
  if ( ((*((_QWORD *)v1 + 241) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x369,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      v186);
  v187 = CreateThread(
           0,
           0xC000u,
           Microsoft::Diagnostics::ScenarioManager::StaticRuleUpdateThreadProc,
           **(LPVOID **)v233,
           0,
           0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)v1 + 1912,
    v187);
  if ( ((*((_QWORD *)v1 + 239) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x36C,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      v188);
  *(_OWORD *)v224 = *(_OWORD *)&off_1803841D0;
  if ( !Microsoft::Diagnostics::Utils::General::IsTestHookEnabled((__int128 *)v224) )
  {
    v190 = Microsoft::Diagnostics::ApiServer::StartRpcServer(v189);
    if ( v190 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x371,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v190,
        dwCreationFlagss);
    *(_OWORD *)v224 = *(_OWORD *)&off_18036BB70;
    v191 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v169, v224, qword_18036BA70);
    if ( v191 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x372,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v191,
        dwCreationFlagss);
    *(_OWORD *)v224 = *(_OWORD *)&off_1803841C0;
    v192 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v169, v224, qword_1803887A0);
    if ( v192 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x373,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v192,
        dwCreationFlagss);
    *(_OWORD *)v224 = *(_OWORD *)&off_18036BB80;
    v193 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v169, v224, qword_18036BB90);
    if ( v193 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x374,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v193,
        dwCreationFlagss);
    *(_OWORD *)v224 = *(_OWORD *)&off_1803841B0;
    v194 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v169, v224, qword_1803893B0);
    if ( v194 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x375,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v194,
        dwCreationFlagss);
    *(_OWORD *)v224 = *(_OWORD *)&off_18036BEC8;
    v195 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v169, v224, qword_18036BF80);
    if ( v195 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x376,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v195,
        dwCreationFlagss);
    *(_OWORD *)v224 = *(_OWORD *)&off_1803841A0;
    v196 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v169, v224, qword_180389CB0);
    if ( v196 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x377,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v196,
        dwCreationFlagss);
    *(_OWORD *)v224 = *(_OWORD *)&off_180384180;
    v197 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v169, v224, qword_18038AA80);
    if ( v197 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x378,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v197,
        dwCreationFlagss);
    *(_OWORD *)v224 = *(_OWORD *)&off_18036BB70;
    v198 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v169, v224, qword_18038AED0);
    if ( v198 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x379,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v198,
        dwCreationFlagss);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UsageAndQualityInsights>::GetImpl'::`2'::impl) )
    {
      *(_OWORD *)v224 = *(_OWORD *)&off_180384190;
      v199 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v169, v224, qword_18038B2D0);
      if ( v199 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x37C,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          (const char *)(unsigned int)v199,
          dwCreationFlagss);
    }
  }
  *(_OWORD *)v224 = *(_OWORD *)&off_180384150;
  v200 = *(Microsoft::Diagnostics::UtcWatchdog ***)v232;
  Microsoft::Diagnostics::UtcWatchdog::AddPermanentThread(**(_QWORD **)v232, v224, *((_QWORD *)v1 + 237));
  *(_OWORD *)v224 = *(_OWORD *)&off_180384170;
  Microsoft::Diagnostics::UtcWatchdog::AddPermanentThread(*v200, v224, *((_QWORD *)v1 + 241));
  *(_OWORD *)v224 = *(_OWORD *)&off_180384160;
  Microsoft::Diagnostics::UtcWatchdog::AddPermanentThread(*v200, v224, *((_QWORD *)v1 + 239));
  v201 = *((_QWORD *)v1 + 291);
  if ( v201 != *((_QWORD *)v1 + 292) )
  {
    v202 = *((_QWORD *)v1 + 292);
    do
    {
      *(_OWORD *)v224 = *(_OWORD *)v201;
      Microsoft::Diagnostics::UtcWatchdog::AddPermanentThread(*v200, v224, *(_QWORD *)(v201 + 16));
      v201 += 24;
    }
    while ( v201 != v202 );
  }
  Microsoft::Diagnostics::UtcWatchdog::StartTimer(*v200);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcJobObjectRestriction>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UtcJobObjectRestriction>::GetImpl'::`2'::impl) )
  {
    v226[0] = 1;
    *(_OWORD *)v224 = *(_OWORD *)&off_180384140;
    *(_OWORD *)v227 = *(_OWORD *)&off_180370B28;
    DwordAsBool = Microsoft::Diagnostics::Utils::Registry::GetDwordAsBool(-2147483646, v227, v224, v226);
    if ( DwordAsBool < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x392,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)DwordAsBool,
        dwCreationFlagss);
    if ( v226[0] )
      Microsoft::Diagnostics::LifetimeManager::UtcJobObjectImpl(v1);
  }
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v269);
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v270);
  std::wstring::_Tidy_deallocate(v263);
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v271);
  std::wstring::_Tidy_deallocate(v264);
  std::wstring::_Tidy_deallocate(v265);
  std::wstring::_Tidy_deallocate(v259);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&v245);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&SecurityDescriptor);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeyDest);
  std::wstring::_Tidy_deallocate(v262);
}

```

## disassembly

```asm
0x1802549f8  mov     r11, rsp
0x1802549fb  mov     [r11+10h], rbx
0x1802549ff  mov     [r11+18h], rsi
0x180254a03  push    rdi
0x180254a04  push    r12
0x180254a06  push    r13
0x180254a08  push    r14
0x180254a0a  push    r15
0x180254a0c  sub     rsp, 760h
0x180254a13  mov     rax, cs:__security_cookie
0x180254a1a  xor     rax, rsp
0x180254a1d  mov     [rsp+788h+var_38], rax
0x180254a25  mov     r15, rcx
0x180254a28  mov     [rsp+788h+var_658], rcx
0x180254a30  xor     esi, esi
0x180254a32  mov     [r11-660h], rsi
0x180254a39  movups  xmm0, xmmword ptr cs:off_1803843E0; "SubsystemShutdownTimeoutMillis"
0x180254a40  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180254a46  movups  xmm1, xmmword ptr cs:off_180370B28; "%DiagtrackRegistryRoot%"
0x180254a4d  movdqu  xmmword ptr [rsp+788h+var_708], xmm1
0x180254a56  lea     r9, [r11-660h]
0x180254a5d  lea     r8, [rsp+788h+var_738]
0x180254a62  lea     rdx, [r11-708h]
0x180254a69  mov     r13, 0FFFFFFFF80000002h
0x180254a70  mov     rcx, r13
0x180254a73  call    ?GetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEA_K@Z; Microsoft::Diagnostics::Utils::Registry::GetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64 &)
0x180254a78  test    eax, eax
0x180254a7a  js      short loc_180254A86
0x180254a7c  mov     eax, dword ptr [rsp+788h+var_660]
0x180254a83  xchg    eax, [r15]
0x180254a86  lea     rcx, [r15+8]; this
0x180254a8a  call    ?StartupConsentCheck@InitialConsentManager@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::InitialConsentManager::StartupConsentCheck(void)
0x180254a8f  movups  xmm0, xmmword ptr cs:?k_csVer4_0String@LifetimeManager@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::LifetimeManager::k_csVer4_0String
0x180254a96  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180254a9c  lea     rdx, [rsp+788h+var_738]
0x180254aa1  lea     rcx, [rsp+788h+var_458]
0x180254aa9  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x180254aae  nop
0x180254aaf  movups  xmm0, xmmword ptr cs:off_1803843D0; "LastCsVersion"
0x180254ab6  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180254abc  movups  xmm1, xmmword ptr cs:off_180370B28; "%DiagtrackRegistryRoot%"
0x180254ac3  movdqu  xmmword ptr [rsp+788h+var_708], xmm1
0x180254acc  lea     r9, [rsp+788h+var_458]
0x180254ad4  lea     r8, [rsp+788h+var_738]
0x180254ad9  lea     rdx, [rsp+788h+var_708]
0x180254ae1  mov     rcx, r13
0x180254ae4  call    ?GetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@7@@Z; Microsoft::Diagnostics::Utils::Registry::GetString(HKEY__ *,std::wstring_view,std::wstring_view,std::wstring &)
0x180254ae9  mov     eax, cs:dword_1804543B0
0x180254aef  mov     ebx, 10h
0x180254af4  lea     rdi, dword_1804543B0
0x180254afb  cmp     eax, 4
0x180254afe  jbe     short loc_180254B4C
0x180254b00  mov     edx, ebx
0x180254b02  mov     rcx, rdi
0x180254b05  call    _tlgKeywordOn
0x180254b0a  test    al, al
0x180254b0c  jz      short loc_180254B4C
0x180254b0e  lea     rax, [rsp+788h+var_458]
0x180254b16  cmp     [rsp+788h+var_440], 7
0x180254b1f  cmova   rax, [rsp+788h+var_458]
0x180254b28  mov     [rsp+788h+var_6C8], rax
0x180254b30  lea     rax, [rsp+788h+var_6C8]
0x180254b38  mov     qword ptr [rsp+788h+dwCreationFlags], rax; int
0x180254b3d  lea     rdx, unk_1803E5D38
0x180254b44  mov     rcx, rdi
0x180254b47  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180254b4c  mov     [rsp+788h+var_718], sil
0x180254b51  call    ?WasCleanServiceShutdown@LifetimeManager@Diagnostics@Microsoft@@AEAA_NXZ; Microsoft::Diagnostics::LifetimeManager::WasCleanServiceShutdown(void)
0x180254b56  test    al, al
0x180254b58  jnz     short loc_180254B9E
0x180254b5a  mov     [rsp+788h+var_6B0], esi
0x180254b61  mov     [rsp+788h+var_6B8], esi
0x180254b68  lea     r8, [rsp+788h+var_6B8]; unsigned int *
0x180254b70  lea     rdx, [rsp+788h+var_6B0]; unsigned int *
0x180254b78  call    ?RecordDirtyShutdown@LifetimeManager@Diagnostics@Microsoft@@AEAAXAEAK0@Z; Microsoft::Diagnostics::LifetimeManager::RecordDirtyShutdown(ulong &,ulong &)
0x180254b7d  mov     r8d, [rsp+788h+var_6B8]; unsigned int
0x180254b85  mov     edx, [rsp+788h+var_6B0]; unsigned int
0x180254b8c  call    ?IsResetRequired@LifetimeManager@Diagnostics@Microsoft@@AEAA_NKK@Z; Microsoft::Diagnostics::LifetimeManager::IsResetRequired(ulong,ulong)
0x180254b91  mov     [rsp+788h+var_718], al
0x180254b95  test    al, al
0x180254b97  jz      short loc_180254B9E
0x180254b99  call    ?ResetState@LifetimeManager@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::LifetimeManager::ResetState(void)
0x180254b9e  mov     r12d, 1
0x180254ba4  movzx   ecx, r12w
0x180254ba8  call    ?SetDiagTrackStatus@General@Utils@Diagnostics@Microsoft@@SAXVDiagTrackStatus@EnumDetails@234@@Z; Microsoft::Diagnostics::Utils::General::SetDiagTrackStatus(Microsoft::Diagnostics::Utils::EnumDetails::DiagTrackStatus)
0x180254bad  mov     [rsp+788h+hKeyDest], rsi
0x180254bb5  mov     [rsp+788h+var_668], esi
0x180254bbc  movups  xmm0, xmmword ptr cs:off_1803843C0; "ComponentManifestVersion"
0x180254bc3  movdqu  xmmword ptr [rsp+788h+var_708], xmm0
0x180254bcc  mov     rax, cs:off_180384430; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180254bd3  mov     qword ptr [rsp+788h+var_738], rax
0x180254bd8  mov     qword ptr [rsp+788h+var_738+8], 3Fh ; '?'
0x180254be1  lea     r9, [rsp+788h+var_668]
0x180254be9  lea     r8, [rsp+788h+var_708]
0x180254bf1  lea     rdx, [rsp+788h+var_738]
0x180254bf6  mov     rcx, r13
0x180254bf9  call    ?GetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEAK@Z; Microsoft::Diagnostics::Utils::Registry::GetDword(HKEY__ *,std::wstring_view,std::wstring_view,ulong &)
0x180254bfe  test    eax, eax
0x180254c00  js      loc_180254C9D
0x180254c06  mov     [rsp+788h+var_6B0], esi
0x180254c0d  movups  xmm0, xmmword ptr cs:off_1803843C0; "ComponentManifestVersion"
0x180254c14  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180254c1a  movups  xmm1, xmmword ptr cs:off_180370B28; "%DiagtrackRegistryRoot%"
0x180254c21  movdqu  xmmword ptr [rsp+788h+var_708], xmm1
0x180254c2a  lea     r9, [rsp+788h+var_6B0]
0x180254c32  lea     r8, [rsp+788h+var_738]
0x180254c37  lea     rdx, [rsp+788h+var_708]
0x180254c3f  mov     rcx, r13
0x180254c42  call    ?GetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEAK@Z; Microsoft::Diagnostics::Utils::Registry::GetDword(HKEY__ *,std::wstring_view,std::wstring_view,ulong &)
0x180254c47  test    eax, eax
0x180254c49  js      short loc_180254C5B
0x180254c4b  mov     eax, [rsp+788h+var_6B0]
0x180254c52  cmp     [rsp+788h+var_668], eax
0x180254c59  jz      short loc_180254C9D
0x180254c5b  movups  xmm0, xmmword ptr cs:off_180370B28; "%DiagtrackRegistryRoot%"
0x180254c62  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180254c68  mov     r8b, r12b
0x180254c6b  lea     rdx, [rsp+788h+var_738]
0x180254c70  mov     rcx, r13
0x180254c73  call    ?DeleteTree@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N@Z; Microsoft::Diagnostics::Utils::Registry::DeleteTree(HKEY__ *,std::wstring_view,bool)
0x180254c78  mov     rcx, [rsp+788h]; this
0x180254c80  test    eax, eax
0x180254c82  jns     short loc_180254C9D
0x180254c84  mov     r9d, eax; char *
0x180254c87  lea     r14, aOnecoreBaseTel_208; "onecore\\base\\telemetry\\utc\\service"...
0x180254c8e  mov     r8, r14; unsigned int
0x180254c91  mov     edx, 188h; void *
0x180254c96  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180254c9b  jmp     short loc_180254CA4
0x180254c9d  lea     r14, aOnecoreBaseTel_208; "onecore\\base\\telemetry\\utc\\service"...
0x180254ca4  movups  xmm0, xmmword ptr cs:off_180370B28; "%DiagtrackRegistryRoot%"
0x180254cab  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180254cb1  mov     r9d, 0F003Fh
0x180254cb7  lea     r8, [rsp+788h+hKeyDest]
0x180254cbf  lea     rdx, [rsp+788h+var_738]
0x180254cc4  mov     rcx, r13; hKey
0x180254cc7  call    ?OpenKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; Microsoft::Diagnostics::Utils::Registry::OpenKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ulong)
0x180254ccc  test    eax, eax
0x180254cce  jns     loc_180254DCB
0x180254cd4  movups  xmm0, xmmword ptr cs:off_180370B28; "%DiagtrackRegistryRoot%"
0x180254cdb  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180254ce1  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180254ce5  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180254ced  xor     r9d, r9d
0x180254cf0  lea     r8, [rsp+788h+hKeyDest]
0x180254cf8  lea     rdx, [rsp+788h+var_738]
0x180254cfd  mov     rcx, r13; hKey
0x180254d00  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180254d05  mov     rcx, [rsp+788h]; this
0x180254d0d  test    eax, eax
0x180254d0f  js      loc_18025772E
0x180254d15  lea     rdx, off_180370B28; "%DiagtrackRegistryRoot%"
0x180254d1c  lea     rcx, [rsp+788h+Src]
0x180254d24  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x180254d29  nop
0x180254d2a  xor     r8d, r8d
0x180254d2d  mov     dl, r12b
0x180254d30  lea     rcx, [rsp+788h+Src]; lpSrc
0x180254d38  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x180254d3d  lea     rdx, [rsp+788h+var_6E8]
0x180254d45  lea     rcx, [rsp+788h+Src]
0x180254d4d  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180254d52  movups  xmm0, xmmword ptr [rax]
0x180254d55  movdqu  xmmword ptr [rsp+788h+var_708], xmm0
0x180254d5e  mov     rax, cs:off_180384430; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180254d65  mov     qword ptr [rsp+788h+var_738], rax
0x180254d6a  mov     qword ptr [rsp+788h+var_738+8], 3Fh ; '?'
0x180254d73  lea     rdx, [rsp+788h+var_708]
0x180254d7b  lea     rcx, [rsp+788h+var_738]
0x180254d80  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x180254d85  test    eax, eax
0x180254d87  jz      short loc_180254DBE
0x180254d89  mov     r8, [rsp+788h+hKeyDest]; hKeyDest
0x180254d91  mov     rdx, cs:off_180384430; lpSubKey
0x180254d98  mov     rcx, r13; hKeySrc
0x180254d9b  call    cs:__imp_RegCopyTreeW
0x180254da1  mov     rcx, [rsp+788h]; this
0x180254da9  test    eax, eax
0x180254dab  jz      short loc_180254DBE
0x180254dad  mov     r9d, eax; char *
0x180254db0  mov     r8, r14; unsigned int
0x180254db3  mov     edx, 195h; void *
0x180254db8  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180254dbd  nop
0x180254dbe  lea     rcx, [rsp+788h+Src]
0x180254dc6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180254dcb  movups  xmm0, xmmword ptr cs:off_1803843A0; "%DiagtrackRegistryRoot%\\Scenarios"
0x180254dd2  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180254dd8  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180254ddc  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180254de4  xor     r9d, r9d
0x180254de7  lea     r8, [rsp+788h+hKeyDest]
0x180254def  lea     rdx, [rsp+788h+var_738]
0x180254df4  mov     rcx, r13; hKey
0x180254df7  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180254dfc  mov     rcx, [rsp+788h]; this
0x180254e04  test    eax, eax
0x180254e06  js      loc_18025773F
0x180254e0c  movups  xmm0, xmmword ptr cs:off_1803843B0; "%DiagtrackRegistryRoot%\\TraceManager"
0x180254e13  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180254e19  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180254e1d  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180254e25  xor     r9d, r9d
0x180254e28  lea     r8, [rsp+788h+hKeyDest]
0x180254e30  lea     rdx, [rsp+788h+var_738]
0x180254e35  mov     rcx, r13; hKey
0x180254e38  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180254e3d  mov     rcx, [rsp+788h]; this
0x180254e45  test    eax, eax
0x180254e47  js      loc_180257750
0x180254e4d  movups  xmm0, xmmword ptr cs:off_18036E9B0; "%DiagtrackRegistryRoot%\\SettingsReques"...
0x180254e54  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180254e5a  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180254e5e  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180254e66  xor     r9d, r9d
0x180254e69  lea     r8, [rsp+788h+hKeyDest]
0x180254e71  lea     rdx, [rsp+788h+var_738]
0x180254e76  mov     rcx, r13; hKey
0x180254e79  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180254e7e  mov     rcx, [rsp+788h]; this
0x180254e86  test    eax, eax
0x180254e88  js      loc_180257761
0x180254e8e  movups  xmm0, xmmword ptr cs:off_180384390; "%DiagtrackRegistryRoot%\\TelemetryNames"...
0x180254e95  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180254e9b  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180254e9f  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180254ea7  xor     r9d, r9d
0x180254eaa  lea     r8, [rsp+788h+hKeyDest]
0x180254eb2  lea     rdx, [rsp+788h+var_738]
0x180254eb7  mov     rcx, r13; hKey
0x180254eba  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180254ebf  mov     rcx, [rsp+788h]; this
0x180254ec7  test    eax, eax
0x180254ec9  js      loc_180257772
0x180254ecf  movups  xmm0, xmmword ptr cs:off_18036BA00; "%DiagtrackRegistryRoot%\\FailFastCounte"...
0x180254ed6  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180254edc  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180254ee0  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180254ee8  xor     r9d, r9d
0x180254eeb  lea     r8, [rsp+788h+hKeyDest]
0x180254ef3  lea     rdx, [rsp+788h+var_738]
0x180254ef8  mov     rcx, r13; hKey
0x180254efb  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180254f00  mov     rcx, [rsp+788h]; this
0x180254f08  test    eax, eax
0x180254f0a  js      loc_180257783
0x180254f10  movups  xmm0, xmmword ptr cs:off_18036BA10; "%DiagtrackRegistryRoot%\\HeartBeats"
0x180254f17  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180254f1d  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180254f21  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180254f29  xor     r9d, r9d
0x180254f2c  lea     r8, [rsp+788h+hKeyDest]
0x180254f34  lea     rdx, [rsp+788h+var_738]
0x180254f39  mov     rcx, r13; hKey
0x180254f3c  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180254f41  mov     rcx, [rsp+788h]; this
0x180254f49  test    eax, eax
0x180254f4b  js      loc_180257794
0x180254f51  movups  xmm0, xmmword ptr cs:off_18036B9C0; "%DiagtrackRegistryRoot%\\SevilleEventlo"...
0x180254f58  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180254f5e  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180254f62  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180254f6a  xor     r9d, r9d
0x180254f6d  lea     r8, [rsp+788h+hKeyDest]
0x180254f75  lea     rdx, [rsp+788h+var_738]
0x180254f7a  mov     rcx, r13; hKey
0x180254f7d  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180254f82  mov     rcx, [rsp+788h]; this
0x180254f8a  test    eax, eax
0x180254f8c  js      loc_1802577A5
0x180254f92  movups  xmm0, xmmword ptr cs:off_18036B9F0; "%DiagtrackRegistryRoot%\\TestHooks"
0x180254f99  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180254f9f  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180254fa3  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180254fab  xor     r9d, r9d
0x180254fae  lea     r8, [rsp+788h+hKeyDest]
0x180254fb6  lea     rdx, [rsp+788h+var_738]
0x180254fbb  mov     rcx, r13; hKey
0x180254fbe  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180254fc3  mov     rcx, [rsp+788h]; this
0x180254fcb  test    eax, eax
0x180254fcd  js      loc_1802577B6
0x180254fd3  movups  xmm0, xmmword ptr cs:off_18036B9D0; "%DiagtrackRegistryRoot%\\TestHooks\\Vol"...
0x180254fda  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180254fe0  lea     r8, [rsp+788h+hKeyDest]
0x180254fe8  lea     rdx, [rsp+788h+var_738]
0x180254fed  call    ?CreateGuaranteedVolatileKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateGuaranteedVolatileKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180254ff2  mov     rcx, [rsp+788h]; this
0x180254ffa  test    eax, eax
0x180254ffc  js      loc_1802577C7
0x180255002  movups  xmm0, xmmword ptr cs:off_180384370; "%DiagtrackRegistryRoot%\\exporters"
0x180255009  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x18025500f  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180255013  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x18025501b  xor     r9d, r9d
0x18025501e  lea     r8, [rsp+788h+hKeyDest]
0x180255026  lea     rdx, [rsp+788h+var_738]
0x18025502b  mov     rcx, r13; hKey
0x18025502e  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180255033  mov     rcx, [rsp+788h]; this
  ... truncated ...
```
