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
// Hidden C++ exception states: #wind=49
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
  int v50; // eax
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
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rdx
  LPCWSTR *v77; // r8
  __int128 *v78; // rcx
  int v79; // ecx
  int v80; // r8d
  int v81; // r9d
  Microsoft::Diagnostics::DevHealthMonTenant *v82; // rax
  LPCWSTR *v83; // rax
  char v84; // bl
  _OWORD *v85; // rax
  int v86; // eax
  const WCHAR *v87; // rcx
  const char *v88; // r9
  int v89; // eax
  __int64 *v90; // rax
  __int64 v91; // rcx
  __int64 *v92; // rax
  __int64 v93; // rcx
  __int64 *v94; // rax
  __int64 v95; // rcx
  __int64 *v96; // rax
  __int64 v97; // rcx
  __int64 v98; // rax
  __int64 *v99; // rax
  __int64 v100; // rcx
  __int64 *v101; // rax
  __int64 v102; // rcx
  __int64 *v103; // rax
  __int64 v104; // rcx
  Microsoft::Diagnostics::EventMonitorManager *v105; // rbx
  __int64 *v106; // rax
  __int64 v107; // rcx
  __int64 v108; // rax
  __int64 v109; // r8
  Microsoft::Diagnostics::LifetimeManager *v110; // rcx
  __int64 v111; // rcx
  int v112; // eax
  __int64 v113; // rdi
  __int64 v114; // rbx
  struct Microsoft::Diagnostics::HeartbeatManager *HeartbeatManager; // rax
  __int64 *v116; // rax
  __int64 v117; // rcx
  Microsoft::Diagnostics::LifetimeManager *v118; // rcx
  __int64 v119; // rdi
  __int64 v120; // rbx
  struct Microsoft::Diagnostics::HeartbeatManager *v121; // rax
  __int64 v122; // r8
  __int64 *v123; // rax
  __int64 v124; // rcx
  __int64 *v125; // rax
  __int64 v126; // rcx
  __int64 *v127; // rax
  __int64 v128; // rcx
  bool v129; // dl
  __int64 v130; // rax
  __int64 v131; // rax
  __int64 v132; // rbx
  __int64 v133; // rax
  __int64 *v134; // rax
  __int64 v135; // rcx
  __int64 *v136; // rax
  __int64 v137; // rcx
  __int64 *v138; // rax
  __int64 v139; // rcx
  __int64 v140; // rax
  __int64 *v141; // rax
  __int64 v142; // rcx
  _QWORD *v143; // rax
  __int64 v144; // rax
  __int64 v145; // rax
  Microsoft::Diagnostics::EnterpriseData *v146; // rcx
  const char *v147; // r9
  int v148; // ecx
  int v149; // r8d
  int v150; // r9d
  Microsoft::Diagnostics::DevHealthMonTenant *v151; // rax
  LPCWSTR *v152; // rax
  _QWORD *v153; // rdi
  __int64 v154; // rax
  __int64 v155; // rax
  __int64 matched; // rax
  __int64 v157; // rax
  __int64 *v158; // rax
  __int64 v159; // rcx
  __int64 v160; // rax
  __int64 *v161; // rax
  __int64 v162; // rcx
  __int64 v163; // rax
  __int64 *v164; // rax
  __int64 v165; // rcx
  __int64 v166; // rax
  __int64 v167; // rax
  Microsoft::Diagnostics::ScenariosSqliteTable *v168; // rdi
  __int64 v169; // rax
  __int64 v170; // rax
  __int64 RegistryConfig; // rax
  int v172; // ebx
  __int64 v173; // rax
  __int64 v174; // rax
  __int64 *v175; // rax
  __int64 v176; // rcx
  Microsoft::Diagnostics::RemoteAggregatorManager *v177; // rcx
  const char *v178; // r9
  int v179; // eax
  HANDLE Thread; // rax
  const char *v181; // r9
  Microsoft::Diagnostics::ExporterManager *v182; // rcx
  _QWORD *started; // rbx
  HANDLE v184; // rax
  const char *v185; // r9
  HANDLE v186; // rax
  const char *v187; // r9
  Microsoft::Diagnostics::ApiServer *v188; // rcx
  int v189; // eax
  int v190; // eax
  int v191; // eax
  int v192; // eax
  int v193; // eax
  int v194; // eax
  int v195; // eax
  int v196; // eax
  int v197; // eax
  int v198; // eax
  Microsoft::Diagnostics::UtcWatchdog **v199; // rdi
  __int64 v200; // rbx
  __int64 v201; // r13
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
  int v223[4]; // [rsp+50h] [rbp-738h] BYREF
  __int64 v224; // [rsp+60h] [rbp-728h]
  bool v225[16]; // [rsp+70h] [rbp-718h] BYREF
  int v226[4]; // [rsp+80h] [rbp-708h] BYREF
  char v227; // [rsp+90h] [rbp-6F8h]
  int v228[4]; // [rsp+A0h] [rbp-6E8h] BYREF
  Microsoft::Diagnostics::DevHealthMonTenant *v229; // [rsp+C0h] [rbp-6C8h] BYREF
  HKEY hKeyDest; // [rsp+C8h] [rbp-6C0h] BYREF
  unsigned int v231[2]; // [rsp+D0h] [rbp-6B8h] BYREF
  unsigned int v232[2]; // [rsp+D8h] [rbp-6B0h] BYREF
  int v233[2]; // [rsp+E0h] [rbp-6A8h] BYREF
  Microsoft::Diagnostics::ScenariosSqliteTable *v234[2]; // [rsp+E8h] [rbp-6A0h] BYREF
  LPVOID *v235; // [rsp+F8h] [rbp-690h] BYREF
  LPVOID *v236; // [rsp+100h] [rbp-688h] BYREF
  __int16 v237; // [rsp+108h] [rbp-680h] BYREF
  char v238; // [rsp+10Ah] [rbp-67Eh]
  bool v239; // [rsp+10Bh] [rbp-67Dh]
  __int128 v240; // [rsp+110h] [rbp-678h] BYREF
  int v241; // [rsp+120h] [rbp-668h] BYREF
  __int64 v242; // [rsp+128h] [rbp-660h] BYREF
  Microsoft::Diagnostics::LifetimeManager *v243; // [rsp+130h] [rbp-658h]
  PSECURITY_DESCRIPTOR v244; // [rsp+138h] [rbp-650h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+140h] [rbp-648h] BYREF
  _QWORD v246[3]; // [rsp+148h] [rbp-640h] BYREF
  __int128 v247; // [rsp+160h] [rbp-628h]
  __int64 v248; // [rsp+170h] [rbp-618h]
  __int128 v249; // [rsp+178h] [rbp-610h]
  __int64 v250; // [rsp+188h] [rbp-600h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+190h] [rbp-5F8h] BYREF
  __int128 v252; // [rsp+2B0h] [rbp-4D8h] BYREF
  __int64 v253; // [rsp+2C0h] [rbp-4C8h]
  unsigned __int64 v254; // [rsp+2C8h] [rbp-4C0h]
  LPCWSTR lpFileName[3]; // [rsp+2D0h] [rbp-4B8h] BYREF
  unsigned __int64 v256; // [rsp+2E8h] [rbp-4A0h]
  WCHAR Src[16]; // [rsp+2F0h] [rbp-498h] BYREF
  WCHAR v258[8]; // [rsp+310h] [rbp-478h] BYREF
  __int64 v259; // [rsp+320h] [rbp-468h]
  unsigned __int64 v260; // [rsp+328h] [rbp-460h]
  _QWORD v261[4]; // [rsp+330h] [rbp-458h] BYREF
  WCHAR v262[16]; // [rsp+350h] [rbp-438h] BYREF
  WCHAR v263[16]; // [rsp+370h] [rbp-418h] BYREF
  WCHAR v264[16]; // [rsp+390h] [rbp-3F8h] BYREF
  _BYTE v265[16]; // [rsp+3B0h] [rbp-3D8h] BYREF
  _BYTE v266[8]; // [rsp+3C0h] [rbp-3C8h] BYREF
  _BYTE v267[232]; // [rsp+3C8h] [rbp-3C0h] BYREF
  _BYTE v268[224]; // [rsp+4B0h] [rbp-2D8h] BYREF
  _BYTE v269[224]; // [rsp+590h] [rbp-1F8h] BYREF
  _BYTE v270[224]; // [rsp+670h] [rbp-118h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+788h] [rbp+0h]

  v1 = this;
  v243 = this;
  v242 = 0;
  *(_OWORD *)v223 = *(_OWORD *)&off_1803843E0;
  *(_OWORD *)v226 = *(_OWORD *)&off_180370B28;
  if ( (int)Microsoft::Diagnostics::Utils::Registry::GetQword(-2147483646, v226, v223, &v242) >= 0 )
    _InterlockedExchange((volatile __int32 *)v1, v242);
  Microsoft::Diagnostics::InitialConsentManager::StartupConsentCheck((Microsoft::Diagnostics::LifetimeManager *)((char *)v1 + 8));
  *(_OWORD *)v223 = *(_OWORD *)&Microsoft::Diagnostics::LifetimeManager::k_csVer4_0String;
  std::wstring::wstring(v261);
  *(_OWORD *)v223 = *(_OWORD *)&off_1803843D0;
  *(_OWORD *)v226 = *(_OWORD *)&off_180370B28;
  Microsoft::Diagnostics::Utils::Registry::GetString(-2147483646, v226, v223, v261);
  if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 16) )
  {
    v5 = (Microsoft::Diagnostics::DevHealthMonTenant *)v261;
    if ( v261[3] > 7u )
      v5 = (Microsoft::Diagnostics::DevHealthMonTenant *)v261[0];
    v229 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (unsigned int)&dword_1804543B0,
      (unsigned int)&unk_1803E5DB8,
      v3,
      v4,
      (__int64)&v229);
  }
  v225[0] = 0;
  if ( !Microsoft::Diagnostics::LifetimeManager::WasCleanServiceShutdown(v2) )
  {
    v232[0] = 0;
    v231[0] = 0;
    Microsoft::Diagnostics::LifetimeManager::RecordDirtyShutdown(v6, v232, v231);
    v225[0] = Microsoft::Diagnostics::LifetimeManager::IsResetRequired(v7, v232[0], v231[0]);
    if ( v225[0] )
      Microsoft::Diagnostics::LifetimeManager::ResetState(v8);
  }
  Microsoft::Diagnostics::Utils::General::SetDiagTrackStatus(1);
  hKeyDest = 0;
  v241 = 0;
  *(_OWORD *)v226 = *(_OWORD *)&off_1803843C0;
  *(_QWORD *)v223 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack";
  *(_QWORD *)&v223[2] = 63;
  if ( (int)Microsoft::Diagnostics::Utils::Registry::GetDword(-2147483646, v223, v226, &v241) >= 0 )
  {
    v232[0] = 0;
    *(_OWORD *)v223 = *(_OWORD *)&off_1803843C0;
    *(_OWORD *)v226 = *(_OWORD *)&off_180370B28;
    if ( (int)Microsoft::Diagnostics::Utils::Registry::GetDword(-2147483646, v226, v223, v232) < 0 || v241 != v232[0] )
    {
      *(_OWORD *)v223 = *(_OWORD *)&off_180370B28;
      LOBYTE(v9) = 1;
      v10 = Microsoft::Diagnostics::Utils::Registry::DeleteTree(-2147483646, v223, v9);
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x188,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          (const char *)(unsigned int)v10,
          dwCreationFlags);
    }
  }
  *(_OWORD *)v223 = *(_OWORD *)&off_180370B28;
  if ( (int)Microsoft::Diagnostics::Utils::Registry::OpenKey(HKEY_LOCAL_MACHINE) < 0 )
  {
    *(_OWORD *)v223 = *(_OWORD *)&off_180370B28;
    Key = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
    if ( Key < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x18E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)Key,
        dwCreationFlagsa);
    std::wstring::wstring(Src);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src);
    *(_OWORD *)v226 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v228);
    *(_QWORD *)v223 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack";
    *(_QWORD *)&v223[2] = 63;
    if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v223, v226) )
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
  *(_OWORD *)v223 = *(_OWORD *)&off_1803843B0;
  v13 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x199,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v13,
      dwCreationFlagsb);
  *(_OWORD *)v223 = *(_OWORD *)&off_180384390;
  v14 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19A,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v14,
      dwCreationFlagsc);
  *(_OWORD *)v223 = *(_OWORD *)&off_18036E9B0;
  v15 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v15,
      dwCreationFlagsd);
  *(_OWORD *)v223 = *(_OWORD *)&off_1803843A0;
  v16 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19C,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v16,
      dwCreationFlagse);
  *(_OWORD *)v223 = *(_OWORD *)&off_18036BA00;
  v17 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v17,
      dwCreationFlagsf);
  *(_OWORD *)v223 = *(_OWORD *)&off_18036BA10;
  v18 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v18,
      dwCreationFlagsg);
  *(_OWORD *)v223 = *(_OWORD *)&off_18036B9C0;
  v19 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v19,
      dwCreationFlagsh);
  *(_OWORD *)v223 = *(_OWORD *)&off_18036B9F0;
  v20 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A0,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v20,
      dwCreationFlagsi);
  *(_OWORD *)v223 = *(_OWORD *)&off_18036B9D0;
  v21 = Microsoft::Diagnostics::Utils::Registry::CreateGuaranteedVolatileKey(retaddr, v223, &hKeyDest);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A1,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v21,
      dwCreationFlagsi);
  *(_OWORD *)v223 = *(_OWORD *)&off_180384380;
  v22 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v22,
      dwCreationFlagsj);
  *(_OWORD *)v223 = *(_OWORD *)&off_180384370;
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
    *(_OWORD *)v223 = *(_OWORD *)&off_180384360;
    v24 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A7,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v24,
        dwCreationFlagsl);
  }
  *(_OWORD *)v223 = *(_OWORD *)&off_18036B9B0;
  Microsoft::Diagnostics::Utils::Os::CreateSecurityDecriptorFromSddl(&SecurityDescriptor);
  *(_QWORD *)v223 = 24;
  *(_QWORD *)&v223[2] = SecurityDescriptor;
  v224 = 0;
  v247 = *(_OWORD *)v223;
  v248 = 0;
  *(_OWORD *)v223 = *(_OWORD *)&off_18036B9E0;
  v25 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v25 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1AD,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v25,
      dwCreationFlagsm);
  *(_OWORD *)v223 = *(_OWORD *)&off_180384350;
  Microsoft::Diagnostics::Utils::Os::CreateSecurityDecriptorFromSddl(&v244);
  *(_QWORD *)v223 = 24;
  *(_QWORD *)&v223[2] = v244;
  v224 = 0;
  v249 = *(_OWORD *)v223;
  v250 = 0;
  *(_OWORD *)v223 = *(_OWORD *)&off_180384340;
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
  *(_OWORD *)v223 = *(_OWORD *)std::wstring::operator std::wstring_view(v28, v226);
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
  v229 = (Microsoft::Diagnostics::DevHealthMonTenant *)&qword_180460AD8;
  gsl::span<enum gsl::byte const,-1>::span<enum gsl::byte const,-1>(v223, &v229);
  *(_OWORD *)v226 = *(_OWORD *)&off_180371218;
  *(_OWORD *)v228 = *(_OWORD *)&off_180370B28;
  Microsoft::Diagnostics::Utils::Registry::SetBinary(v31, (int)v228, (int)v226, (int)v223, 0);
  std::wstring::wstring(v258);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v258);
  v32 = v258;
  if ( v260 > 7 )
    v32 = *(WCHAR **)v258;
  v33 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(v32, v259, -1, 92);
  if ( v33 == -1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)0x80070057LL,
      dwCreationFlagsp);
  v34 = std::wstring::substr(v258, Src, 0, v33);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)std::wstring::operator std::wstring_view(v34, v228);
  LOBYTE(v35) = 1;
  Directory = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, v35, v223);
  if ( Directory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CB,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)Directory,
      dwCreationFlagsp);
  std::wstring::_Tidy_deallocate(Src);
  *(_OWORD *)v223 = *(_OWORD *)&off_18036BA50;
  *(_OWORD *)v226 = *(_OWORD *)std::wstring::operator std::wstring_view(v258, v228);
  Microsoft::Diagnostics::LifetimeManager::EnsureAclsOnFolder(v37, v226, (__int128 *)v223);
  std::wstring::wstring(v264);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v264);
  *(_OWORD *)v223 = *(_OWORD *)&off_180384330;
  *(_OWORD *)v226 = *(_OWORD *)std::wstring::operator std::wstring_view(v264, v228);
  Microsoft::Diagnostics::LifetimeManager::EnsureAclsOnFolder(v38, v226, (__int128 *)v223);
  *(_OWORD *)v223 = *(_OWORD *)&off_18036BA50;
  *(_OWORD *)v226 = *(_OWORD *)&off_18036BA40;
  v39 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v39 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D7,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v39,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_18036BA20;
  v40 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v40 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D9,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v40,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_180371F90;
  v41 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v41 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DA,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v41,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_180371F80;
  v42 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v42 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DB,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v42,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_180371208;
  v43 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v43 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DC,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v43,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_180371FA0;
  v44 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
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
    *(_OWORD *)v223 = *(_OWORD *)&off_180384310;
    if ( IsEnabled )
    {
      *(_OWORD *)v226 = *(_OWORD *)&off_1803842F0;
      v49 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
      if ( v49 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1E3,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          (const char *)(unsigned int)v49,
          dwCreationFlagsp);
    }
    else
    {
      *(_OWORD *)v226 = *(_OWORD *)&off_180371FA0;
      v46 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
      if ( v46 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1EA,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          (const char *)(unsigned int)v46,
          dwCreationFlagsp);
    }
    std::wstring::wstring(Src);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src);
    *(_OWORD *)v223 = *(_OWORD *)&off_180384310;
    *(_OWORD *)v226 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v228);
    Microsoft::Diagnostics::LifetimeManager::EnsureAclsOnFolder(v47, v226, (__int128 *)v223);
    std::wstring::_Tidy_deallocate(Src);
  }
  else
  {
    memset(v223, 0, sizeof(v223));
    *(_OWORD *)v226 = *(_OWORD *)&off_180371FA0;
    v50 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
    if ( v50 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F3,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v50,
        dwCreationFlagsp);
  }
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_180384300;
  v48 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v48 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F6,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v48,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_1803842E0;
  v51 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v51 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F7,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v51,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&Microsoft::Diagnostics::AlternativeSlot::k_traceProfileLocalStoreDirectory;
  v52 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v52 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F8,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v52,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&Microsoft::Diagnostics::ETWConsumer::k_etlFilesPath;
  v53 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v53 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F9,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v53,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&Microsoft::Diagnostics::ETWConsumer::k_autologgerFilesPath;
  v54 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v54 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FA,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v54,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&Microsoft::Diagnostics::ETWConsumer::k_dtShutdownLoggerStorePath;
  v55 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v55 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FB,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v55,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_1803842C0;
  v56 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v56 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v56,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_180384290;
  v57 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v57 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FD,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v57,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_1803842A0;
  v58 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v58 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FE,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v58,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_180384270;
  v59 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v59 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FF,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v59,
      dwCreationFlagsp);
  *(_OWORD *)v223 = *(_OWORD *)&off_180384330;
  *(_OWORD *)v226 = *(_OWORD *)&off_180384320;
  v60 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v60 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x200,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v60,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_180384430;
  v61 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v61 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x201,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v61,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_180384280;
  v62 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v62 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x202,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v62,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_180384250;
  v63 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v63 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x203,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v63,
      dwCreationFlagsp);
  std::wstring::wstring(v263);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v263);
  *(_OWORD *)v223 = *(_OWORD *)std::wstring::operator std::wstring_view(v263, v226);
  v64 = Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory(v223);
  if ( v64 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x209,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v64,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_180384260;
  v65 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v65 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v65,
      dwCreationFlagsp);
  *(_OWORD *)v223 = *(_OWORD *)&off_18036BA60;
  v66 = Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory(v223);
  if ( v66 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v66,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_18036BA60;
  v67 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v67 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v67,
      dwCreationFlagsp);
  *(_OWORD *)v223 = *(_OWORD *)&off_180384230;
  v68 = Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory(v223);
  if ( v68 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x212,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v68,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_180384230;
  v69 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v69 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x213,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v69,
      dwCreationFlagsp);
  *(_OWORD *)v223 = *(_OWORD *)&off_180384240;
  v70 = Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory(v223);
  if ( v70 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x216,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v70,
      dwCreationFlagsp);
  memset(v223, 0, sizeof(v223));
  *(_OWORD *)v226 = *(_OWORD *)&off_180384240;
  v71 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
  if ( v71 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x217,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v71,
      dwCreationFlagsp);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v265);
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( RtlGetVersion(&VersionInformation) < 0 )
  {
    std::operator<<<std::char_traits<char>>(v266, "0.0.0");
  }
  else
  {
    v72 = std::ostream::operator<<(v266, VersionInformation.dwMajorVersion);
    v73 = std::operator<<<std::char_traits<char>>(v72, ".");
    v74 = std::ostream::operator<<(v73, VersionInformation.dwMinorVersion);
    v75 = std::operator<<<std::char_traits<char>>(v74, ".");
    std::ostream::operator<<(v75, VersionInformation.dwBuildNumber);
  }
  std::stringbuf::str(v267, lpFileName);
  std::wstring::wstring(Src);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src);
  v252 = 0;
  v253 = 0;
  v254 = 15;
  LOBYTE(v252) = 0;
  *(_OWORD *)v223 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v226);
  if ( (int)Microsoft::Diagnostics::Utils::FileSystem::ReadStringFromFile(v223, v76, 0xFFFFFFFFLL, &v252) < 0 )
    goto LABEL_252;
  v77 = lpFileName;
  if ( v256 > 0xF )
    v77 = (LPCWSTR *)lpFileName[0];
  v78 = &v252;
  if ( v254 > 0xF )
    v78 = (__int128 *)v252;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<char>>(v78, v253, v77, lpFileName[2]) )
  {
    v227 = 0;
    if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 16) )
    {
      v82 = (Microsoft::Diagnostics::DevHealthMonTenant *)&v252;
      if ( v254 > 0xF )
        v82 = (Microsoft::Diagnostics::DevHealthMonTenant *)v252;
      v229 = v82;
      v83 = lpFileName;
      if ( v256 > 0xF )
        v83 = (LPCWSTR *)lpFileName[0];
      *(_QWORD *)v233 = v83;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v79,
        (unsigned int)&byte_1803E5BFF,
        v80,
        v81,
        (__int64)v233,
        (__int64)&v229);
    }
    v84 = v227;
  }
  else
  {
LABEL_252:
    if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 16) )
    {
      v151 = (Microsoft::Diagnostics::DevHealthMonTenant *)&v252;
      if ( v254 > 0xF )
        v151 = (Microsoft::Diagnostics::DevHealthMonTenant *)v252;
      v229 = v151;
      v152 = lpFileName;
      if ( v256 > 0xF )
        v152 = (LPCWSTR *)lpFileName[0];
      *(_QWORD *)v233 = v152;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v148,
        (unsigned int)byte_1803E5BAD,
        v149,
        v150,
        (__int64)v233,
        (__int64)&v229);
    }
    v84 = 1;
    v227 = 1;
  }
  v85 = (_OWORD *)gslp::container_to_bytes<std::string>(v234, lpFileName);
  *(_QWORD *)v223 = &::Src;
  *(_QWORD *)&v223[2] = 0;
  *(_OWORD *)v226 = *v85;
  *(_OWORD *)v228 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, &v240);
  v86 = Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile(v228, v226, v223);
  if ( v86 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v86,
      dwCreationFlagsp);
  std::string::_Tidy_deallocate(&v252);
  std::wstring::_Tidy_deallocate(Src);
  std::string::_Tidy_deallocate(lpFileName);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(v265);
  if ( v84 )
  {
    std::wstring::wstring(lpFileName);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)lpFileName);
    v87 = (const WCHAR *)lpFileName;
    if ( v256 > 7 )
      v87 = lpFileName[0];
    if ( !DeleteFileW(v87) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x25D,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        v88);
    std::wstring::_Tidy_deallocate(lpFileName);
  }
  v246[0] = 1;
  v246[1] = &Microsoft::Diagnostics::PdcNetworkActivation::PdcActivatorCallback;
  v246[2] = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    (char *)v1 + 2264,
    0);
  v89 = Pdcv2ActivationClientRegister(77, v246, (char *)v1 + 2264);
  if ( v89 < 0 )
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0x266,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v89,
      dwCreationFlagsp);
  Microsoft::CommonDatapoints::UpdateStaticCommonDatapointsInRegistry();
  v90 = (__int64 *)std::make_unique<Microsoft::Diagnostics::UserManager,,0>(&v229);
  v91 = *v90;
  *v90 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 262, v91);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v229);
  v237 = 1;
  v238 = 0;
  v239 = v225[0];
  v92 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SettingsManager,Microsoft::Diagnostics::SettingsManagerConfig &,0>(
                     &v235,
                     &v237);
  v93 = *v92;
  *v92 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 235, v93);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v235);
  v94 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SevilleEventlogManager,,0>(&v236);
  v95 = *v94;
  *v94 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 271, v95);
  std::unique_ptr<Microsoft::Diagnostics::SevilleEventlogManager>::~unique_ptr<Microsoft::Diagnostics::SevilleEventlogManager>(&v236);
  v96 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SyntheticAggregationManager,,0>(v232);
  v97 = *v96;
  *v96 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 278, v97);
  std::unique_ptr<Microsoft::Diagnostics::SyntheticAggregationManager>::~unique_ptr<Microsoft::Diagnostics::SyntheticAggregationManager>(v232);
  v98 = std::make_unique<Microsoft::Diagnostics::ProxySourceRegistry,,0>(v231);
  v99 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SystemStateManager,std::unique_ptr<Microsoft::Diagnostics::ProxySourceMutable>,0>(
                     &v229,
                     v98);
  v100 = *v99;
  *v99 = 0;
  *(_QWORD *)v223 = (char *)v1 + 2064;
  _InterlockedExchange64((volatile __int64 *)v1 + 258, v100);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v229);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v231);
  LOBYTE(v231[0]) = 1;
  v101 = (__int64 *)std::make_unique<Microsoft::Diagnostics::HeartbeatManager,bool,wil::basic_zstring_view<wchar_t> const &,std::bitset<9> const &,0>(
                      &v252,
                      v231,
                      &Microsoft::Diagnostics::HeartBeat::k_defaultHeartBeatName,
                      &Microsoft::Diagnostics::HeartBeat::k_defaultHeartBeatSections);
  v102 = *v101;
  *v101 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 254, v102);
  std::unique_ptr<Microsoft::Diagnostics::HeartbeatManager>::~unique_ptr<Microsoft::Diagnostics::HeartbeatManager>(&v252);
  v103 = (__int64 *)std::make_unique<Microsoft::Diagnostics::PrivacyKeyManager,,0>(&v240);
  v104 = *v103;
  *v103 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 246, v104);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v240);
  v105 = (Microsoft::Diagnostics::EventMonitorManager *)operator new(0x550u);
  *(_QWORD *)v226 = v105;
  *(_OWORD *)v228 = *(_OWORD *)std::wstring::operator std::wstring_view(qword_1804634E0, &v240);
  Microsoft::Diagnostics::EventMonitorManager::EventMonitorManager(v105);
  *(_QWORD *)&v240 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 264, (__int64)v105);
  std::unique_ptr<Microsoft::Diagnostics::EventMonitorManager>::~unique_ptr<Microsoft::Diagnostics::EventMonitorManager>(&v240);
  v106 = (__int64 *)std::make_unique<Microsoft::Diagnostics::EnterpriseData,,0>(v234);
  v107 = *v106;
  *v106 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 251, v107);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v234);
  *(_QWORD *)v226 = operator new(0x108u);
  v108 = Microsoft::Diagnostics::RegionMetadata::RegionMetadata(*(Microsoft::Diagnostics::RegionMetadata **)v226);
  v234[0] = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 282, v108);
  std::unique_ptr<Microsoft::Diagnostics::RegionMetadata>::~unique_ptr<Microsoft::Diagnostics::RegionMetadata>(v234);
  v232[0] = 0;
  *(_OWORD *)v226 = *(_OWORD *)&off_180384450;
  *(_OWORD *)v228 = *(_OWORD *)&off_180370B28;
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateRegistryConfig(
    (unsigned int)v270,
    (unsigned int)v232,
    (unsigned int)v228,
    (unsigned int)v226,
    0);
  LODWORD(v229) = Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(v270);
  LOBYTE(v109) = 1;
  Microsoft::Diagnostics::LifetimeManager::GetAuthorizationInfo(v1, v233, v109);
  v110 = (Microsoft::Diagnostics::LifetimeManager *)*((unsigned int *)v1 + 568);
  if ( ((unsigned __int8)v110 & 4) == 0 )
  {
    v111 = (unsigned int)dword_1804543B0;
    if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 16) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1804543B0,
        word_1803E5B2A);
    *(_OWORD *)v226 = *(_OWORD *)&off_180371F50;
    *(_OWORD *)v228 = *(_OWORD *)&off_180370B28;
    v112 = Microsoft::Diagnostics::Utils::Registry::DeleteValue(v111, v228, v226);
    v110 = retaddr;
    if ( v112 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2A2,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v112,
        dwCreationFlagsq);
  }
  v233[0] = Microsoft::Diagnostics::LifetimeManager::GetUtcDefaultEventStoreSize(v110);
  std::wstring::wstring(v262);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v262);
  v113 = std::make_unique<Microsoft::Diagnostics::XboxToastEventStoreUsageCallback,,0>(&v240);
  LOWORD(v231[0]) = 256;
  *(_QWORD *)v226 = v231;
  *(_QWORD *)&v226[2] = (char *)v231 + 2;
  v114 = std::vector<Microsoft::Diagnostics::StorageBufferType>::vector<Microsoft::Diagnostics::StorageBufferType>(
           v228,
           v226);
  v232[0] = Microsoft::Diagnostics::AsimovEventBuffer::GetEventBufferMaxBytes();
  LODWORD(v236) = Microsoft::Diagnostics::AsimovEventBuffer::GetCriticalEventBufferMaxEvents();
  LODWORD(v235) = Microsoft::Diagnostics::AsimovEventBuffer::GetNormalEventBufferMaxEvents();
  HeartbeatManager = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager(v1);
  v116 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SqliteEventStore,Microsoft::Diagnostics::HeartBeat &,std::wstring &,unsigned long &,unsigned long,unsigned long,unsigned long,std::vector<Microsoft::Diagnostics::StorageBufferType> &,std::unique_ptr<Microsoft::Diagnostics::SevilleEventStoreUsageCallback>,0>(
                      v234,
                      HeartbeatManager,
                      v262,
                      v233,
                      &v235,
                      &v236,
                      v232,
                      v114,
                      v113);
  v117 = *v116;
  *v116 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 244, v117);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v234);
  std::vector<Microsoft::Diagnostics::UploadLatency>::_Tidy(v228);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v240);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LocalEncryptCertRemoval>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LocalEncryptCertRemoval>::GetImpl'::`2'::impl) )
  {
    v232[0] = Microsoft::Diagnostics::LifetimeManager::GetUtcDefaultInMemoryEventStoreSize(v118);
    v119 = std::make_unique<Microsoft::Diagnostics::XboxToastEventStoreUsageCallback,,0>(&v240);
    LOWORD(v231[0]) = 256;
    *(_QWORD *)v226 = v231;
    *(_QWORD *)&v226[2] = (char *)v231 + 2;
    v120 = std::vector<Microsoft::Diagnostics::StorageBufferType>::vector<Microsoft::Diagnostics::StorageBufferType>(
             v228,
             v226);
    v233[0] = 102400;
    LODWORD(v235) = 50;
    LODWORD(v236) = 0;
    v121 = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager(v1);
    v123 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SqliteEventStore,Microsoft::Diagnostics::HeartBeat &,wchar_t const (&)[1],unsigned long const &,unsigned long,unsigned long,unsigned long,std::vector<Microsoft::Diagnostics::StorageBufferType>,std::unique_ptr<Microsoft::Diagnostics::XboxToastEventStoreUsageCallback>,0>(
                        v234,
                        v121,
                        v122,
                        v232,
                        &v236,
                        &v235,
                        v233,
                        v120,
                        v119);
    v124 = *v123;
    *v123 = 0;
    _InterlockedExchange64((volatile __int64 *)v1 + 245, v124);
    std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v234);
    std::vector<Microsoft::Diagnostics::UploadLatency>::_Tidy(v228);
    std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v240);
    if ( (unsigned int)dword_1804543B0 > 4 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 48) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_1804543B0,
          word_1803E5AF2);
    }
  }
  v125 = (__int64 *)std::make_unique<Microsoft::Diagnostics::ScenarioCounterStorage,,0>(v234);
  v126 = *v125;
  *v125 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 249, v126);
  std::unique_ptr<Microsoft::Diagnostics::ScenarioCounterStorage>::~unique_ptr<Microsoft::Diagnostics::ScenarioCounterStorage>(v234);
  v127 = (__int64 *)std::make_unique<Microsoft::Diagnostics::LatencyData,,0>(&v240);
  v128 = *v127;
  *v127 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 255, v128);
  std::unique_ptr<Microsoft::Diagnostics::LatencyData>::~unique_ptr<Microsoft::Diagnostics::LatencyData>(&v240);
  *(_QWORD *)v226 = operator new(0x620u);
  v130 = Microsoft::Diagnostics::UsageAnalyzer::UsageAnalyzer(*(Microsoft::Diagnostics::UsageAnalyzer **)v226, v129);
  v234[0] = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 259, v130);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v234);
  *(_QWORD *)v226 = operator new(0xB70u);
  v131 = Microsoft::Diagnostics::EventTranscriptManager::EventTranscriptManager(*(Microsoft::Diagnostics::EventTranscriptManager **)v226);
  v234[0] = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 260, v131);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v234);
  *(_QWORD *)v226 = operator new(0x2A0u);
  v132 = Microsoft::Diagnostics::AsimovEndpointConfig::AsimovEndpointConfig(*(Microsoft::Diagnostics::AsimovEndpointConfig **)v226);
  v236 = (LPVOID *)v132;
  *(_QWORD *)v226 = operator new(0x330u);
  *(_QWORD *)v233 = 0;
  v236 = 0;
  v235 = (LPVOID *)v132;
  v133 = Microsoft::Diagnostics::AsimovUploadQueue::AsimovUploadQueue(*(_QWORD *)v226, &v235, v233, 180000);
  v234[0] = 0;
  *(_QWORD *)v226 = (char *)v1 + 2016;
  _InterlockedExchange64((volatile __int64 *)v1 + 252, v133);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v234);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v236);
  v134 = (__int64 *)std::make_unique<Microsoft::Diagnostics::AsimovEventSerializer,,0>(&v252);
  v135 = *v134;
  *v134 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 253, v135);
  std::unique_ptr<Microsoft::Diagnostics::AsimovEventSerializer>::~unique_ptr<Microsoft::Diagnostics::AsimovEventSerializer>(&v252);
  v136 = (__int64 *)std::make_unique<Microsoft::Diagnostics::KillSwitchManager,,0>(v232);
  v137 = *v136;
  *v136 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 270, v137);
  std::unique_ptr<Microsoft::Diagnostics::KillSwitchManager>::~unique_ptr<Microsoft::Diagnostics::KillSwitchManager>(v232);
  v138 = (__int64 *)std::make_unique<Microsoft::Diagnostics::EscalationEngine,,0>(v231);
  v139 = *v138;
  *v138 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 247, v139);
  std::unique_ptr<Microsoft::Diagnostics::EscalationEngine>::~unique_ptr<Microsoft::Diagnostics::EscalationEngine>(v231);
  v234[0] = (Microsoft::Diagnostics::ScenariosSqliteTable *)operator new(0x138u);
  v240 = *(_OWORD *)&off_180371208;
  v140 = Microsoft::Diagnostics::ScenariosSqliteTable::ScenariosSqliteTable(v234[0]);
  v234[0] = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 273, v140);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v234);
  v141 = (__int64 *)std::make_unique<Microsoft::Diagnostics::ScenarioObjectCache,,0>(v228);
  v142 = *v141;
  *v141 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 274, v142);
  std::unique_ptr<Microsoft::Diagnostics::ScenarioObjectCache>::~unique_ptr<Microsoft::Diagnostics::ScenarioObjectCache>(v228);
  v143 = operator new(8u);
  *v143 = &Microsoft::Diagnostics::ScenarioStorageSql::`vftable';
  *(_QWORD *)v228 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 257, (__int64)v143);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v228);
  *(_QWORD *)v228 = operator new(0x220u);
  v144 = Microsoft::Diagnostics::ScenarioCacheLRU::ScenarioCacheLRU(*(Microsoft::Diagnostics::ScenarioCacheLRU **)v228);
  *(_QWORD *)v228 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 256, v144);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v228);
  *(_QWORD *)v228 = operator new(0x528u);
  v145 = Microsoft::Diagnostics::ScenarioManager::ScenarioManager(*(Microsoft::Diagnostics::ScenarioManager **)v228);
  *(_QWORD *)v228 = 0;
  *(_QWORD *)v232 = (char *)v1 + 1904;
  _InterlockedExchange64((volatile __int64 *)v1 + 238, v145);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v228);
  if ( *((_BYTE *)v1 + 2278) )
    *(_BYTE *)(*((_QWORD *)v1 + 238) + 618LL) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DpswOneSettingsControl>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_DpswOneSettingsControl>::GetImpl'::`2'::impl);
  v146 = (Microsoft::Diagnostics::EnterpriseData *)*((_QWORD *)v1 + 251);
  if ( v146 )
  {
    try
    {
      Microsoft::Diagnostics::EnterpriseData::Initialize(v146);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x2FA,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        v147);
      v1 = v243;
    }
  }
  v153 = operator new(0x60u);
  *(_QWORD *)v228 = v153;
  memset_0(v153, 0, 0x60u);
  *v153 = 258;
  *(_OWORD *)(v153 + 3) = 0;
  *(_OWORD *)(v153 + 5) = 0;
  *(_OWORD *)(v153 + 7) = 0;
  v153[1] = 0;
  v153[2] = 0;
  *((_DWORD *)v153 + 18) = -1;
  *((_DWORD *)v153 + 19) = 0;
  v153[10] = 0;
  v153[11] = 0;
  v154 = std::_Allocate<16,std::_Default_allocate_traits>(56);
  *(_QWORD *)v154 = v154;
  *(_QWORD *)(v154 + 8) = v154;
  *(_QWORD *)(v154 + 16) = v154;
  *(_WORD *)(v154 + 24) = 257;
  v153[10] = v154;
  *(_QWORD *)v228 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 266, (__int64)v153);
  std::unique_ptr<Microsoft::Diagnostics::TelemetryAssert>::~unique_ptr<Microsoft::Diagnostics::TelemetryAssert>(v228);
  *(_QWORD *)v228 = operator new(0x48u);
  v155 = Microsoft::Diagnostics::OsEvents::OsEvents(*(Microsoft::Diagnostics::OsEvents **)v228);
  *(_QWORD *)v228 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 242, v155);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v228);
  *(_QWORD *)v228 = operator new(0x188u);
  matched = Microsoft::Diagnostics::MatchEngine::MatchEngine(*(Microsoft::Diagnostics::MatchEngine **)v228);
  *(_QWORD *)v228 = 0;
  v236 = (LPVOID *)((char *)v1 + 1888);
  _InterlockedExchange64((volatile __int64 *)v1 + 236, matched);
  std::unique_ptr<Microsoft::Diagnostics::MatchEngine>::~unique_ptr<Microsoft::Diagnostics::MatchEngine>(v228);
  *(_QWORD *)v228 = operator new(0x440u);
  v157 = Microsoft::Diagnostics::TriggerListener::TriggerListener(*(Microsoft::Diagnostics::TriggerListener **)v228);
  *(_QWORD *)v228 = 0;
  v235 = (LPVOID *)((char *)v1 + 1920);
  _InterlockedExchange64((volatile __int64 *)v1 + 240, v157);
  std::unique_ptr<Microsoft::Diagnostics::TriggerListener>::~unique_ptr<Microsoft::Diagnostics::TriggerListener>(v228);
  v158 = (__int64 *)std::make_unique<Microsoft::Diagnostics::TraceManager,,0>(v234);
  v159 = *v158;
  *v158 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 248, v159);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v234);
  *(_QWORD *)v228 = operator new(0x158u);
  v160 = Microsoft::Diagnostics::MetadataEngine::MetadataEngine(*(Microsoft::Diagnostics::MetadataEngine **)v228, 0);
  *(_QWORD *)v228 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 250, v160);
  std::unique_ptr<Microsoft::Diagnostics::MetadataEngine>::~unique_ptr<Microsoft::Diagnostics::MetadataEngine>(v228);
  v161 = (__int64 *)std::make_unique<Microsoft::Diagnostics::DTraceManager,,0>(&v240);
  v162 = *v161;
  *v161 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 276, v162);
  std::unique_ptr<Microsoft::Diagnostics::DTraceManager>::~unique_ptr<Microsoft::Diagnostics::DTraceManager>(&v240);
  *(_QWORD *)v228 = operator new(0x80u);
  v163 = Microsoft::Diagnostics::PiiScrubberManager::PiiScrubberManager(*(Microsoft::Diagnostics::PiiScrubberManager **)v228);
  *(_QWORD *)v228 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 277, v163);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v228);
  v164 = (__int64 *)std::make_unique<Microsoft::Diagnostics::UtcWatchdog,,0>(&v252);
  v165 = *v164;
  *v164 = 0;
  *(_QWORD *)v231 = (char *)v1 + 2152;
  _InterlockedExchange64((volatile __int64 *)v1 + 269, v165);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v252);
  *(_QWORD *)v228 = operator new(0x10u);
  v166 = Microsoft::Diagnostics::TenantManager::TenantManager(*(Microsoft::Diagnostics::TenantManager **)v228);
  *(_QWORD *)v228 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 263, v166);
  std::unique_ptr<Microsoft::Diagnostics::TenantManager>::~unique_ptr<Microsoft::Diagnostics::TenantManager>(v228);
  *(_QWORD *)v228 = operator new(0x400u);
  v167 = Microsoft::Diagnostics::UtcApiManager::UtcApiManager(*(Microsoft::Diagnostics::UtcApiManager **)v228);
  *(_QWORD *)v228 = 0;
  v168 = (Microsoft::Diagnostics::LifetimeManager *)((char *)v1 + 2088);
  v234[0] = (Microsoft::Diagnostics::LifetimeManager *)((char *)v1 + 2088);
  _InterlockedExchange64((volatile __int64 *)v1 + 261, v167);
  std::unique_ptr<Microsoft::Diagnostics::AgentUtcApiManager>::~unique_ptr<Microsoft::Diagnostics::AgentUtcApiManager>(v228);
  *(_QWORD *)v228 = operator new(0x930u);
  v240 = *(_OWORD *)&Microsoft::Diagnostics::ETWConsumer::k_dtSessionName;
  v169 = Microsoft::Diagnostics::TriggerAggregator::TriggerAggregator(*(_QWORD *)v228, &v240);
  *(_QWORD *)v228 = 0;
  *(_QWORD *)&v240 = (char *)v1 + 2240;
  _InterlockedExchange64((volatile __int64 *)v1 + 280, v169);
  std::unique_ptr<Microsoft::Diagnostics::TriggerAggregator>::~unique_ptr<Microsoft::Diagnostics::TriggerAggregator>(v228);
  *(_QWORD *)v228 = operator new(0x90u);
  v170 = Microsoft::Diagnostics::AggregatedEventManager::AggregatedEventManager(*(Microsoft::Diagnostics::AggregatedEventManager **)v228);
  *(_QWORD *)v228 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 281, v170);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v228);
  v233[0] = 0;
  *(_OWORD *)v228 = *(_OWORD *)&off_180384210;
  v252 = *(_OWORD *)&off_180370B28;
  RegistryConfig = Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateRegistryConfig(
                     (unsigned int)v265,
                     (unsigned int)v233,
                     (unsigned int)&v252,
                     (unsigned int)v228,
                     0);
  v172 = Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(RegistryConfig);
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v265);
  if ( v172 == 1 )
  {
    *(_QWORD *)v228 = operator new(0xE8u);
    v173 = Microsoft::Diagnostics::ExporterManager::ExporterManager(*(Microsoft::Diagnostics::ExporterManager **)v228);
    *(_QWORD *)v228 = 0;
    _InterlockedExchange64((volatile __int64 *)v1 + 279, v173);
    std::unique_ptr<Microsoft::Diagnostics::ExporterManager>::~unique_ptr<Microsoft::Diagnostics::ExporterManager>(v228);
  }
  else if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 16) )
  {
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1804543B0,
      &byte_1803E5ABF);
  }
  *(_QWORD *)v228 = operator new(0x8D8u);
  v174 = Microsoft::Diagnostics::RemoteAggregatorManager::RemoteAggregatorManager(*(Microsoft::Diagnostics::RemoteAggregatorManager **)v228);
  *(_QWORD *)v228 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 275, v174);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v228);
  if ( *((_BYTE *)v1 + 2288)
    || (_DWORD)v229 != *((_DWORD *)v1 + 568)
    && (*((_DWORD *)v1 + 568) & 8) == 0
    && (*((_DWORD *)v1 + 568) & 0x400) == 0
    && ((unsigned __int8)v229 & 4) != 0 )
  {
    Microsoft::Diagnostics::LifetimeManager::ClearEventStoresOnOptInChange(v1);
  }
  LODWORD(v229) = 0;
  *(_OWORD *)v228 = *(_OWORD *)&off_180384200;
  v252 = *(_OWORD *)&off_180370B28;
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateRegistryConfig(
    (unsigned int)v269,
    (unsigned int)&v229,
    (unsigned int)&v252,
    (unsigned int)v228,
    0);
  if ( (unsigned int)Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(v269) != 1 )
  {
    v175 = (__int64 *)std::make_unique<Microsoft::Diagnostics::AgentManager,,0>(v228);
    v176 = *v175;
    *v175 = 0;
    _InterlockedExchange64((volatile __int64 *)v1 + 265, v176);
    std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v228);
  }
  Microsoft::Diagnostics::AsimovUploadQueue::StartTimers(**(Microsoft::Diagnostics::AsimovUploadQueue ***)v226);
  v229 = 0;
  *(_OWORD *)v226 = *(_OWORD *)&off_180372110;
  Microsoft::Diagnostics::TenantManager::GetTenant(*((_QWORD *)v1 + 263), v226, &v229);
  if ( v229 )
    Microsoft::Diagnostics::DevHealthMonTenant::StartMdmListener(v229);
  Microsoft::Diagnostics::SystemStateManager::BeginTrackingSystemState(**(Microsoft::Diagnostics::SystemStateManager ***)v223);
  v177 = (Microsoft::Diagnostics::RemoteAggregatorManager *)*((_QWORD *)v1 + 275);
  if ( v177 )
  {
    try
    {
      Microsoft::Diagnostics::RemoteAggregatorManager::Initialize(v177);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x34E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        v178);
      v1 = v243;
      v168 = v234[0];
    }
  }
  LODWORD(v229) = 0;
  *(_OWORD *)v223 = *(_OWORD *)&off_1803841F0;
  *(_OWORD *)v226 = *(_OWORD *)&off_180370B28;
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateRegistryConfig(
    (unsigned int)v268,
    (unsigned int)&v229,
    (unsigned int)v226,
    (unsigned int)v223,
    0);
  if ( (unsigned int)Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(v268) == 1 )
  {
    memset(v223, 0, sizeof(v223));
    *(_OWORD *)v226 = *(_OWORD *)&off_1803841E0;
    v179 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v226, 0, v223);
    if ( v179 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x357,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v179,
        dwCreationFlagsr);
  }
  Thread = CreateThread(0, 0xB000u, Microsoft::Diagnostics::MatchEngine::StartMatchEngine, *v236, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)v1 + 1896,
    Thread);
  if ( ((*((_QWORD *)v1 + 237) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x35C,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      v181);
  v182 = (Microsoft::Diagnostics::ExporterManager *)*((_QWORD *)v1 + 279);
  if ( v182 )
    Microsoft::Diagnostics::ExporterManager::Initialize(v182);
  started = (_QWORD *)Microsoft::Diagnostics::TriggerListener::StartConsumerThreads(*v235, v223);
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
  std::vector<std::pair<std::string_view,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>::_Tidy(v223);
  Microsoft::Diagnostics::TriggerAggregator::StartAggregation(*(Microsoft::Diagnostics::TriggerAggregator **)v240);
  v184 = CreateThread(0, 0x8000u, Microsoft::Diagnostics::TriggerListener::StartThread, *v235, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)v1 + 1928,
    v184);
  if ( ((*((_QWORD *)v1 + 241) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x369,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      v185);
  v186 = CreateThread(
           0,
           0xC000u,
           Microsoft::Diagnostics::ScenarioManager::StaticRuleUpdateThreadProc,
           **(LPVOID **)v232,
           0,
           0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)v1 + 1912,
    v186);
  if ( ((*((_QWORD *)v1 + 239) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x36C,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      v187);
  *(_OWORD *)v223 = *(_OWORD *)&off_1803841D0;
  if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(v223) )
  {
    v189 = Microsoft::Diagnostics::ApiServer::StartRpcServer(v188);
    if ( v189 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x371,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v189,
        dwCreationFlagss);
    *(_OWORD *)v223 = *(_OWORD *)&off_18036BB70;
    v190 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v168, v223, qword_18036BA70);
    if ( v190 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x372,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v190,
        dwCreationFlagss);
    *(_OWORD *)v223 = *(_OWORD *)&off_1803841C0;
    v191 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v168, v223, qword_180388750);
    if ( v191 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x373,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v191,
        dwCreationFlagss);
    *(_OWORD *)v223 = *(_OWORD *)&off_18036BB80;
    v192 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v168, v223, qword_18036BB90);
    if ( v192 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x374,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v192,
        dwCreationFlagss);
    *(_OWORD *)v223 = *(_OWORD *)&off_1803841B0;
    v193 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v168, v223, qword_180389390);
    if ( v193 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x375,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v193,
        dwCreationFlagss);
    *(_OWORD *)v223 = *(_OWORD *)&off_18036BEC8;
    v194 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v168, v223, qword_18036BF80);
    if ( v194 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x376,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v194,
        dwCreationFlagss);
    *(_OWORD *)v223 = *(_OWORD *)&off_180384190;
    v195 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v168, v223, qword_180389C30);
    if ( v195 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x377,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v195,
        dwCreationFlagss);
    *(_OWORD *)v223 = *(_OWORD *)&off_1803841A0;
    v196 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v168, v223, qword_18038AA90);
    if ( v196 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x378,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v196,
        dwCreationFlagss);
    *(_OWORD *)v223 = *(_OWORD *)&off_18036BB70;
    v197 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v168, v223, qword_18038AE90);
    if ( v197 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x379,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v197,
        dwCreationFlagss);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UsageAndQualityInsights>::GetImpl'::`2'::impl) )
    {
      *(_OWORD *)v223 = *(_OWORD *)&off_180384170;
      v198 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v168, v223, qword_18038B370);
      if ( v198 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x37C,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          (const char *)(unsigned int)v198,
          dwCreationFlagss);
    }
  }
  *(_OWORD *)v223 = *(_OWORD *)&off_180384180;
  v199 = *(Microsoft::Diagnostics::UtcWatchdog ***)v231;
  Microsoft::Diagnostics::UtcWatchdog::AddPermanentThread(**(_QWORD **)v231, v223, *((_QWORD *)v1 + 237));
  *(_OWORD *)v223 = *(_OWORD *)&off_180384150;
  Microsoft::Diagnostics::UtcWatchdog::AddPermanentThread(*v199, v223, *((_QWORD *)v1 + 241));
  *(_OWORD *)v223 = *(_OWORD *)&off_180384140;
  Microsoft::Diagnostics::UtcWatchdog::AddPermanentThread(*v199, v223, *((_QWORD *)v1 + 239));
  v200 = *((_QWORD *)v1 + 291);
  if ( v200 != *((_QWORD *)v1 + 292) )
  {
    v201 = *((_QWORD *)v1 + 292);
    do
    {
      *(_OWORD *)v223 = *(_OWORD *)v200;
      Microsoft::Diagnostics::UtcWatchdog::AddPermanentThread(*v199, v223, *(_QWORD *)(v200 + 16));
      v200 += 24;
    }
    while ( v200 != v201 );
  }
  Microsoft::Diagnostics::UtcWatchdog::StartTimer(*v199);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcJobObjectRestriction>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UtcJobObjectRestriction>::GetImpl'::`2'::impl) )
  {
    v225[0] = 1;
    *(_OWORD *)v223 = *(_OWORD *)&off_180384160;
    *(_OWORD *)v226 = *(_OWORD *)&off_180370B28;
    DwordAsBool = Microsoft::Diagnostics::Utils::Registry::GetDwordAsBool(-2147483646, v226, v223, v225);
    if ( DwordAsBool < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x392,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)DwordAsBool,
        dwCreationFlagss);
    if ( v225[0] )
      Microsoft::Diagnostics::LifetimeManager::UtcJobObjectImpl(v1);
  }
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v268);
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v269);
  std::wstring::_Tidy_deallocate(v262);
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v270);
  std::wstring::_Tidy_deallocate(v263);
  std::wstring::_Tidy_deallocate(v264);
  std::wstring::_Tidy_deallocate(v258);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&v244);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&SecurityDescriptor);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeyDest);
  std::wstring::_Tidy_deallocate(v261);
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
0x180254b3d  lea     rdx, unk_1803E5DB8
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
0x180254bcc  mov     rax, cs:off_180384420; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
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
0x180254d5e  mov     rax, cs:off_180384420; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180254d65  mov     qword ptr [rsp+788h+var_738], rax
0x180254d6a  mov     qword ptr [rsp+788h+var_738+8], 3Fh ; '?'
0x180254d73  lea     rdx, [rsp+788h+var_708]
0x180254d7b  lea     rcx, [rsp+788h+var_738]
0x180254d80  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x180254d85  test    eax, eax
0x180254d87  jz      short loc_180254DBE
0x180254d89  mov     r8, [rsp+788h+hKeyDest]; hKeyDest
0x180254d91  mov     rdx, cs:off_180384420; lpSubKey
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
0x180254dcb  movups  xmm0, xmmword ptr cs:off_1803843B0; "%DiagtrackRegistryRoot%\\Scenarios"
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
0x180254e0c  movups  xmm0, xmmword ptr cs:off_180384390; "%DiagtrackRegistryRoot%\\TraceManager"
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
0x180254e8e  movups  xmm0, xmmword ptr cs:off_1803843A0; "%DiagtrackRegistryRoot%\\TelemetryNames"...
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
0x180255002  movups  xmm0, xmmword ptr cs:off_180384380; "%DiagtrackRegistryRoot%\\exporters"
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
