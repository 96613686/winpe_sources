# Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl(tagDIAGTRACK_SCENARIO_INFORMATION,__MIDL_UtcApiStructures_0001,wchar_t const *,int,int,__MIDL_UtcApiStructures_0004,ulong,wchar_t const * *,wchar_t const * *,std::function<void (long,_GUID,_GUID)> const &,ulong *,_GUID *)

- ea: `0x1801f9dc4`
- end: `0x1801fbff2`
- name: `?EscalateScenarioImpl@UtcApiManager@Diagnostics@Microsoft@@AEAAJUtagDIAGTRACK_SCENARIO_INFORMATION@@W4__MIDL_UtcApiStructures_0001@@PEB_WHHW4__MIDL_UtcApiStructures_0004@@KPEAPEB_W4AEBV?$function@$$A6AXJU_GUID@@0@Z@std@@PEAKPEAU_GUID@@@Z`
- size: `8750`
- prototype: `__int64 __fastcall(__int64, struct _GUID *, unsigned int, const WCHAR *, int, int, unsigned int, unsigned int, __int64, __int64, __int64, _DWORD *, GUID *)`
- caller_count: `4`
- callee_count: `70`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801f3070`
- `0x1801f9cc0`
- `0x180288ff0`
- `0x18028ad30`

## callees

- `0x180002a28`
- `0x180006ed8`
- `0x1800074f4`
- `0x18001b3f8`
- `0x1800249a0`
- `0x18002afd8`
- `0x18002b770`
- `0x18002b9c0`
- `0x18002ba00`
- `0x18002cb04`
- `0x18002df00`
- `0x180030174`
- `0x180038034`
- `0x180049d00`
- `0x18004b6ac`
- `0x18004ffa4`
- `0x180052240`
- `0x18005ea74`
- `0x180064e8c`
- `0x18006a814`
- `0x18007b274`
- `0x180081278`
- `0x18008a4ec`
- `0x18008a580`
- `0x18008a5d8`
- `0x18008ab10`
- `0x18008abf4`
- `0x18008bce0`
- `0x180096888`
- `0x18009c8c0`
- `0x1800afab0`
- `0x1800b47f0`
- `0x1800b6204`
- `0x1800bc658`
- `0x1800bfdf8`
- `0x1800c2588`
- `0x1800cf7d8`
- `0x1800faa3c`
- `0x180105618`
- `0x18010af6c`
- `0x18010c974`
- `0x1801245e0`
- `0x180124720`
- `0x180135dac`
- `0x18013b624`
- `0x180142fcc`
- `0x1801639c8`
- `0x1801652d4`
- `0x180166420`
- `0x180166500`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1801fa27c`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1801fa27c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801fa9a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801fa9a7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801fa893`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801fa893`

## string_xrefs

- `0x1801f9f8a`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa03d`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa101`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa1c5`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa29a`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa37e`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa43c`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa4f2`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa6f1`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa7b6`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa8ae`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801faab2`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fade0`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fbbd5`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fbc0e`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fbdfa`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fbe8b`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fbf1e`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fbf59`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fbf94`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fac0a`: `ScenarioApiCompleted_0`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl(
        __int64 a1,
        struct _GUID *a2,
        unsigned int a3,
        const WCHAR *a4,
        int a5,
        int a6,
        unsigned int a7,
        unsigned int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        _DWORD *a12,
        GUID *a13)
{
  _DWORD *v15; // rdx
  GUID *v16; // rcx
  int v17; // ecx
  __int64 v18; // r9
  char v19; // r15
  int RpcImpersonationToken; // eax
  unsigned int v21; // ebx
  __int64 v23; // rcx
  unsigned int i; // ebx
  _QWORD *v25; // rcx
  WCHAR *v26; // rcx
  struct Microsoft::Diagnostics::ScenarioManager *ScenarioManager; // rax
  Microsoft::Diagnostics::ScenarioManager *v28; // rax
  int ScenarioById; // eax
  unsigned int v30; // ebx
  std::_Ref_count_base *v31; // r14
  int v32; // ebx
  __int64 v33; // rcx
  __int64 v34; // r8
  HRESULT v35; // eax
  __int64 v36; // rax
  std::_Ref_count_base *v37; // rdi
  __int64 *v38; // rbx
  __int64 v39; // rcx
  __int64 v40; // rcx
  char v41; // di
  __int64 v42; // rdx
  __int64 v43; // rax
  char v44; // bl
  int v45; // eax
  __int64 v46; // rax
  __int64 v47; // r8
  __int64 v48; // r8
  _QWORD *v49; // rax
  __int128 v50; // xmm6
  __int64 v51; // rax
  __int64 v52; // rax
  _QWORD *v53; // rax
  int v54; // eax
  const char *v55; // r9
  __int64 v56; // rdx
  struct Microsoft::Diagnostics::MetadataEngine *MetadataEngine; // rax
  _QWORD *v58; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v59; // rax
  _QWORD *v60; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v61; // rax
  _QWORD *v62; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v63; // rax
  _QWORD *v64; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v65; // rax
  _QWORD *v66; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v67; // rax
  _QWORD *v68; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v69; // rax
  _QWORD *v70; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v71; // rax
  _QWORD *v72; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v73; // rax
  _QWORD *v74; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v75; // rax
  _QWORD *v76; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v77; // rax
  _QWORD *v78; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v79; // rax
  _QWORD *v80; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v81; // rax
  _QWORD *v82; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v83; // rax
  _QWORD *v84; // rax
  _QWORD *v85; // rax
  _QWORD *v86; // rax
  __int64 v87; // rdx
  __int64 v88; // r8
  struct Microsoft::Diagnostics::ScenarioCounterStorage *v89; // rbx
  __int64 v90; // rdx
  __int64 v91; // r8
  __int64 v92; // rdx
  __int64 v93; // r8
  __int64 v94; // rdx
  __int64 v95; // r8
  __int64 v96; // rdx
  __int64 v97; // r8
  __int64 v98; // rbx
  _QWORD *v99; // rax
  __int64 v100; // rbx
  int v101; // ecx
  int v102; // r8d
  int v103; // r9d
  __int64 v104; // rdx
  __int64 v105; // rdx
  int v106; // eax
  struct Microsoft::Diagnostics::EscalationEngine *EscalationEngine; // rbx
  __int64 v108; // rax
  __int64 v109; // r12
  __int64 v110; // r9
  __int64 v111; // rax
  __int64 v112; // r8
  _QWORD *v113; // rax
  __int128 v114; // xmm6
  __int64 v115; // rax
  __int64 v116; // rax
  _QWORD *v117; // rax
  int v118; // eax
  unsigned int v119; // ebx
  unsigned int v120; // ebx
  unsigned int v121; // ebx
  unsigned int v122; // [rsp+20h] [rbp-C48h]
  int v123; // [rsp+20h] [rbp-C48h]
  int v124; // [rsp+20h] [rbp-C48h]
  bool v125; // [rsp+140h] [rbp-B28h] BYREF
  _BYTE v126[3]; // [rsp+141h] [rbp-B27h] BYREF
  _DWORD v127[3]; // [rsp+144h] [rbp-B24h] BYREF
  __int128 v128; // [rsp+150h] [rbp-B18h] BYREF
  struct _GUID *v129; // [rsp+160h] [rbp-B08h] BYREF
  char v130; // [rsp+168h] [rbp-B00h]
  _BYTE v131[4]; // [rsp+170h] [rbp-AF8h] BYREF
  _WORD v132[6]; // [rsp+174h] [rbp-AF4h] BYREF
  std::_Ref_count_base *v133[2]; // [rsp+180h] [rbp-AE8h] BYREF
  unsigned int v134; // [rsp+190h] [rbp-AD8h] BYREF
  __int64 v135; // [rsp+198h] [rbp-AD0h] BYREF
  __int64 v136; // [rsp+1A0h] [rbp-AC8h]
  _DWORD *v137; // [rsp+1A8h] [rbp-AC0h] BYREF
  int v138; // [rsp+1B0h] [rbp-AB8h]
  int CurrentScenarioEscalationsByType; // [rsp+1B4h] [rbp-AB4h] BYREF
  int v140; // [rsp+1B8h] [rbp-AB0h] BYREF
  _BYTE v141[16]; // [rsp+1C0h] [rbp-AA8h] BYREF
  std::_Ref_count_base *v142[2]; // [rsp+1D0h] [rbp-A98h] BYREF
  std::_Ref_count_base *v143[2]; // [rsp+1E0h] [rbp-A88h] BYREF
  unsigned int v144[2]; // [rsp+1F0h] [rbp-A78h] BYREF
  GUID *v145; // [rsp+1F8h] [rbp-A70h] BYREF
  __int64 v146; // [rsp+200h] [rbp-A68h]
  int v147; // [rsp+208h] [rbp-A60h] BYREF
  int v148; // [rsp+20Ch] [rbp-A5Ch] BYREF
  int CurrentScenarioReportsByType; // [rsp+210h] [rbp-A58h] BYREF
  __int64 v150; // [rsp+218h] [rbp-A50h] BYREF
  struct Microsoft::Diagnostics::ScenarioCounterStorage *ScenarioCounterStorage; // [rsp+220h] [rbp-A48h] BYREF
  char *v152; // [rsp+228h] [rbp-A40h] BYREF
  __int64 v153; // [rsp+230h] [rbp-A38h] BYREF
  int v154; // [rsp+238h] [rbp-A30h]
  __int64 v155; // [rsp+240h] [rbp-A28h]
  _QWORD *v156; // [rsp+248h] [rbp-A20h] BYREF
  _QWORD v157[3]; // [rsp+250h] [rbp-A18h] BYREF
  _QWORD *v158; // [rsp+268h] [rbp-A00h] BYREF
  _QWORD *v159; // [rsp+270h] [rbp-9F8h] BYREF
  _QWORD *v160; // [rsp+278h] [rbp-9F0h] BYREF
  _QWORD *v161; // [rsp+280h] [rbp-9E8h] BYREF
  const wchar_t *v162; // [rsp+288h] [rbp-9E0h] BYREF
  _QWORD *v163; // [rsp+290h] [rbp-9D8h] BYREF
  _QWORD *v164; // [rsp+298h] [rbp-9D0h] BYREF
  _QWORD *v165; // [rsp+2A0h] [rbp-9C8h] BYREF
  _QWORD *v166; // [rsp+2A8h] [rbp-9C0h] BYREF
  _QWORD *v167; // [rsp+2B0h] [rbp-9B8h] BYREF
  _QWORD *v168; // [rsp+2B8h] [rbp-9B0h] BYREF
  _BYTE v169[8]; // [rsp+2C0h] [rbp-9A8h] BYREF
  std::_Ref_count_base *v170; // [rsp+2C8h] [rbp-9A0h]
  unsigned int *v171; // [rsp+2D0h] [rbp-998h] BYREF
  int v172; // [rsp+2D8h] [rbp-990h]
  _QWORD *v173; // [rsp+2E0h] [rbp-988h] BYREF
  _QWORD *v174; // [rsp+2E8h] [rbp-980h] BYREF
  _BYTE v175[16]; // [rsp+2F0h] [rbp-978h] BYREF
  _QWORD *v176; // [rsp+300h] [rbp-968h] BYREF
  __int64 v177; // [rsp+308h] [rbp-960h] BYREF
  int v178; // [rsp+310h] [rbp-958h]
  _BYTE v179[16]; // [rsp+318h] [rbp-950h] BYREF
  _BYTE v180[16]; // [rsp+328h] [rbp-940h] BYREF
  _BYTE v181[16]; // [rsp+338h] [rbp-930h] BYREF
  _BYTE v182[16]; // [rsp+348h] [rbp-920h] BYREF
  _BYTE v183[16]; // [rsp+358h] [rbp-910h] BYREF
  _BYTE v184[16]; // [rsp+368h] [rbp-900h] BYREF
  _BYTE v185[16]; // [rsp+378h] [rbp-8F0h] BYREF
  _BYTE v186[16]; // [rsp+388h] [rbp-8E0h] BYREF
  _OWORD v187[2]; // [rsp+398h] [rbp-8D0h] BYREF
  __int128 v188; // [rsp+3B8h] [rbp-8B0h] BYREF
  __m128i si128; // [rsp+3C8h] [rbp-8A0h]
  _QWORD v190[2]; // [rsp+3D8h] [rbp-890h] BYREF
  __int64 v191; // [rsp+3E8h] [rbp-880h]
  unsigned __int64 v192; // [rsp+3F0h] [rbp-878h]
  PWSTR pszPathOut[4]; // [rsp+3F8h] [rbp-870h] BYREF
  __int128 v194; // [rsp+418h] [rbp-850h] BYREF
  __int64 v195; // [rsp+428h] [rbp-840h]
  _BYTE v196[4]; // [rsp+438h] [rbp-830h] BYREF
  int v197; // [rsp+43Ch] [rbp-82Ch]
  _BYTE v198[4]; // [rsp+440h] [rbp-828h] BYREF
  GUID Buf1; // [rsp+444h] [rbp-824h] BYREF
  _BYTE v200[32]; // [rsp+458h] [rbp-810h] BYREF
  _BYTE v201[32]; // [rsp+478h] [rbp-7F0h] BYREF
  _BYTE v202[72]; // [rsp+498h] [rbp-7D0h] BYREF
  _BYTE v203[8]; // [rsp+4E0h] [rbp-788h] BYREF
  _BYTE v204[64]; // [rsp+4E8h] [rbp-780h] BYREF
  _BYTE v205[16]; // [rsp+528h] [rbp-740h] BYREF
  _BYTE v206[40]; // [rsp+538h] [rbp-730h] BYREF
  _BYTE v207[40]; // [rsp+560h] [rbp-708h] BYREF
  _BYTE v208[40]; // [rsp+588h] [rbp-6E0h] BYREF
  _BYTE v209[40]; // [rsp+5B0h] [rbp-6B8h] BYREF
  _BYTE v210[40]; // [rsp+5D8h] [rbp-690h] BYREF
  _BYTE v211[40]; // [rsp+600h] [rbp-668h] BYREF
  _BYTE v212[40]; // [rsp+628h] [rbp-640h] BYREF
  _BYTE v213[40]; // [rsp+650h] [rbp-618h] BYREF
  _BYTE v214[40]; // [rsp+678h] [rbp-5F0h] BYREF
  _BYTE v215[40]; // [rsp+6A0h] [rbp-5C8h] BYREF
  _BYTE v216[40]; // [rsp+6C8h] [rbp-5A0h] BYREF
  _BYTE v217[40]; // [rsp+6F0h] [rbp-578h] BYREF
  _BYTE v218[40]; // [rsp+718h] [rbp-550h] BYREF
  _BYTE v219[48]; // [rsp+740h] [rbp-528h] BYREF
  int v220[176]; // [rsp+770h] [rbp-4F8h] BYREF
  _BYTE v221[344]; // [rsp+A30h] [rbp-238h] BYREF
  _BYTE v222[80]; // [rsp+B88h] [rbp-E0h] BYREF
  int v223[14]; // [rsp+BD8h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C68h] [rbp+0h]

  v134 = a3;
  v150 = a1;
  CurrentScenarioEscalationsByType = a5;
  v140 = a6;
  v155 = a11;
  v15 = a12;
  v137 = a12;
  v16 = a13;
  v145 = a13;
  if ( (unsigned int)dword_1804543B0 > 4 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x2000) )
    {
      v125 = *(_QWORD *)(v18 + 56) == 0;
      *(_QWORD *)v144 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(
        v17,
        (unsigned int)byte_1803ECD95,
        a3,
        v18,
        (__int64)v144,
        (__int64)&v125);
      a3 = v134;
    }
    v15 = v137;
    v16 = v145;
  }
  v129 = a2;
  v19 = 1;
  v130 = 1;
  if ( !a4 || !a9 || !a10 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v122);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2147942487LL;
  }
  if ( v15 )
    *v15 = 0;
  if ( v16 )
    *v16 = GUID_NULL;
  if ( a3 > 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v122);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2147942487LL;
  }
  if ( a7 > 2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C9,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v122);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2147942487LL;
  }
  *(_QWORD *)&v127[1] = 0;
  v187[0] = 0;
  v187[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v187[0]) = 0;
  RpcImpersonationToken = Microsoft::Diagnostics::ApiServer::GetRpcImpersonationToken(v16, &v127[1], v187);
  v21 = RpcImpersonationToken;
  if ( RpcImpersonationToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CF,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)RpcImpersonationToken,
      v122);
    std::wstring::_Tidy_deallocate(v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return v21;
  }
  std::map<std::wstring,std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::pair<std::wstring const,std::wstring>>>::map<std::wstring,std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::pair<std::wstring const,std::wstring>>>(&v135);
  for ( i = 0; i < a8; ++i )
  {
    if ( !*(_QWORD *)(a9 + 8LL * i) || !*(_QWORD *)(a10 + 8LL * i) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D8,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)0x80070057LL,
        v122);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v135);
      std::wstring::_Tidy_deallocate(v187);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
      v130 = 0;
      Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
      return 2147942487LL;
    }
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Emplace<wchar_t const * &,wchar_t const * &>(
      &v135,
      v133);
  }
  Microsoft::Diagnostics::UtcApiManager::ProcessApiMetaProperties(v23, v196, &v127[1], &v135);
  *(_QWORD *)v144 = v197;
  std::unique_lock<std::recursive_timed_mutex>::unique_lock<std::recursive_timed_mutex>(v141, v150 + 224, v144);
  if ( !v141[8] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x87C5102BLL,
      v122);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v135);
    std::wstring::_Tidy_deallocate(v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2277838891LL;
  }
  std::wstring::wstring(v190);
  v25 = v190;
  if ( v192 > 7 )
    v25 = (_QWORD *)v190[0];
  if ( std::_Traits_find_ch<std::char_traits<wchar_t>>(v25, v191, 0, 47) != -1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F0,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v122);
    std::wstring::_Tidy_deallocate(v190);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v135);
    std::wstring::_Tidy_deallocate(v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2147942487LL;
  }
  std::wstring::wstring(pszPathOut, v191, 0);
  v26 = (WCHAR *)pszPathOut;
  if ( pszPathOut[3] > (PWSTR)7 )
    v26 = pszPathOut[0];
  if ( PathCchCanonicalizeEx(v26, (size_t)pszPathOut[2] + 1, a4, 1u) < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F7,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v122);
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v190);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v135);
    std::wstring::_Tidy_deallocate(v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2147942487LL;
  }
  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_180463150, 0, 0) )
  {
    v121 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1FD,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
             (const char *)0x15,
             v122);
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v190);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v135);
    std::wstring::_Tidy_deallocate(v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return v121;
  }
  if ( !_InterlockedCompareExchange64((_QWORD *)&xmmword_180463190 + 1, 0, 0) )
  {
    v120 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x203,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
             (const char *)0x15,
             v122);
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v190);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v135);
    std::wstring::_Tidy_deallocate(v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return v120;
  }
  ScenarioManager = Microsoft::Diagnostics::LifetimeManager::GetScenarioManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  Microsoft::Diagnostics::ScenarioManager::GetScenarioState(ScenarioManager, v131, a2);
  if ( v131[0] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20A,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x87C51005LL,
      v122);
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v190);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v135);
    std::wstring::_Tidy_deallocate(v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2277838853LL;
  }
  *(_OWORD *)v143 = 0;
  v28 = Microsoft::Diagnostics::LifetimeManager::GetScenarioManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  ScenarioById = Microsoft::Diagnostics::ScenarioManager::TryGetScenarioById(v28, a2);
  v30 = ScenarioById;
  if ( ScenarioById < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x210,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)ScenarioById,
      v122);
    if ( v143[1] )
      std::_Ref_count_base::_Decref(v143[1]);
LABEL_39:
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v190);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v135);
    std::wstring::_Tidy_deallocate(v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return v30;
  }
  v31 = v143[0];
  if ( !v143[0] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x211,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x87C51005LL,
      v122);
    if ( v143[1] )
      std::_Ref_count_base::_Decref(v143[1]);
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v190);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v135);
    std::wstring::_Tidy_deallocate(v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2277838853LL;
  }
  v32 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v143[0] + 336LL))(v143[0]);
  v138 = v32;
  if ( *(_WORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, _WORD *))(*(_QWORD *)v31 + 80LL))(v31, v132) == 1 )
  {
    if ( !(unsigned __int8)Microsoft::Diagnostics::ApiServer::IsRpcCallerUif(v33, &v127[1]) )
    {
      v127[0] = v32;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_UtcFeedbackHubApiCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_UtcFeedbackHubApiCheck>::GetImpl'::`2'::impl) )
        goto LABEL_62;
    }
    LOBYTE(v34) = 1;
    Microsoft::Diagnostics::LifetimeManager::GetAuthorizationInfo(&gs_lifetimeManager, v127, v34);
    if ( a7 )
    {
      if ( (v127[0] & 0x200) == 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x227,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          (const char *)0x87C5101BLL,
          v122);
        if ( v143[1] )
          std::_Ref_count_base::_Decref(v143[1]);
        goto LABEL_55;
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_UtcFeedbackHubApiCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_UtcFeedbackHubApiCheck>::GetImpl'::`2'::impl) )
      {
        v188 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v188) = 0;
        Microsoft::Diagnostics::Utils::Os::GetDeviceClass(&v188);
        v142[0] = (std::_Ref_count_base *)L"Windows.Desktop";
        v142[1] = (std::_Ref_count_base *)15;
        *(_OWORD *)v133 = *(_OWORD *)std::wstring::operator std::wstring_view(&v188, &v153);
        if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v133, v142)
          && SLOBYTE(v127[0]) >= 0
          && !(unsigned __int8)Microsoft::Diagnostics::ApiServer::SoftIsAdminCheck(&v127[1]) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x240,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
            (const char *)0x87C5101BLL,
            v122);
          std::wstring::_Tidy_deallocate(&v188);
          if ( v143[1] )
            std::_Ref_count_base::_Decref(v143[1]);
LABEL_55:
          std::wstring::_Tidy_deallocate(pszPathOut);
          std::wstring::_Tidy_deallocate(v190);
          std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
          std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v135);
          std::wstring::_Tidy_deallocate(v187);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
          v130 = 0;
          Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
          return 2277838875LL;
        }
        std::wstring::_Tidy_deallocate(&v188);
      }
    }
    v32 &= ~0x80u;
  }
  v127[0] = v32;
  v138 = v32;
LABEL_62:
  *(_OWORD *)v142 = 0;
  if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
  {
    v35 = CoCreateGuid(&Buf1);
    v30 = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x251,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)v35,
        v122);
      if ( v143[1] )
        std::_Ref_count_base::_Decref(v143[1]);
      goto LABEL_39;
    }
  }
  if ( v145 )
    *v145 = Buf1;
  v36 = std::make_shared<Microsoft::Diagnostics::ScenarioInst,std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const> &,_GUID &>(
          v133,
          v143,
          &Buf1);
  std::shared_ptr<Concurrency::details::_Task_impl<std::shared_ptr<Microsoft::Diagnostics::HttpResponse>>>::operator=(
    v142,
    v36);
  if ( v133[1] )
    std::_Ref_count_base::_Decref(v133[1]);
  v37 = v142[0];
  GetSystemTimeAsFileTime((LPFILETIME)((char *)v142[0] + 36));
  *((_BYTE *)v37 + 72) = 1;
  v38 = (__int64 *)((char *)v37 + 80);
  if ( (__int64 *)((char *)v37 + 80) != &v135 )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear((char *)v37 + 80);
    v39 = *v38;
    *v38 = v135;
    v135 = v39;
    v40 = *((_QWORD *)v37 + 11);
    *((_QWORD *)v37 + 11) = v136;
    v136 = v40;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    (char *)v37 + 96,
    &v127[1]);
  std::wstring::operator=((char *)v37 + 104, v187);
  v41 = 0;
  v125 = 0;
  (*(void (__fastcall **)(std::_Ref_count_base *, _QWORD *))(*(_QWORD *)v31 + 264LL))(v31, v157);
  if ( v134 == 1 )
  {
    v41 = 1;
    v125 = 1;
    v43 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int128 *))(*(_QWORD *)v31 + 272LL))(v31, &v188);
    std::vector<std::shared_ptr<Microsoft::Diagnostics::IActionDef const>>::operator=(v157, v43);
    std::vector<std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>>::~vector<std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>>(&v188);
  }
  if ( v157[0] == v157[1] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x275,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x87C51057LL,
      v122);
    std::vector<std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>>::~vector<std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>>(v157);
    if ( v142[1] )
      std::_Ref_count_base::_Decref(v142[1]);
    if ( v143[1] )
      std::_Ref_count_base::_Decref(v143[1]);
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v190);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v135);
    std::wstring::_Tidy_deallocate(v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2277838935LL;
  }
  else
  {
    v44 = (v41 ^ 1) - 4;
    v126[0] = v44;
    if ( v137 )
    {
      LOBYTE(v42) = (v41 ^ 1) - 4;
      v45 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 224LL))(v31, v42);
      *v137 = v45 + 5000;
    }
    v46 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v31 + 72LL))(v31);
    LOBYTE(v47) = 1;
    Microsoft::Diagnostics::Utils::String::StringFromGuidW(v200, v46, v47);
    Microsoft::Diagnostics::Utils::String::NormalizeToBracelessUppercaseGuidString(v200);
    v152 = (char *)v142[0] + 12;
    LOBYTE(v48) = 1;
    Microsoft::Diagnostics::Utils::String::StringFromGuidW(v201, (char *)v142[0] + 12, v48);
    Microsoft::Diagnostics::Utils::String::NormalizeToBracelessUppercaseGuidString(v201);
    *(_QWORD *)&v128 = L"ScenarioApiCompleted_0";
    *((_QWORD *)&v128 + 1) = 22;
    Microsoft::Diagnostics::AsimovSyntheticEvent::MakeScenarioSyntheticEvent(
      (unsigned int)v220,
      (unsigned int)&v128,
      0x1000000,
      0,
      0);
    v49 = (_QWORD *)std::wstring::operator std::wstring_view(v201, v133);
    std::wstring::_Assign<wchar_t>(v221, *v49, v49[1]);
    (*(void (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v31 + 88LL))(v31, v133);
    *(_QWORD *)&v128 = L"ScenarioName";
    *((_QWORD *)&v128 + 1) = 12;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v220, (int)v223);
    *(_QWORD *)&v128 = L"ScenarioId";
    *((_QWORD *)&v128 + 1) = 10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v220, v223, &v128, v200);
    v50 = *(_OWORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64 *))(*(_QWORD *)v31 + 88LL))(v31, &v153);
    v51 = std::wstring::wstring(&v194);
    *(_OWORD *)v133 = v50;
    v52 = Microsoft::Diagnostics::operator+(&v188, v51, v133);
    v53 = (_QWORD *)std::wstring::operator std::wstring_view(v52, &v171);
    std::wstring::_Assign<wchar_t>(v222, *v53, v53[1]);
    std::wstring::_Tidy_deallocate(&v188);
    std::wstring::_Tidy_deallocate(&v194);
    *(_OWORD *)v133 = 0;
    Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(&v137, v133);
    v54 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v220);
    if ( v54 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x29D,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)v54,
        v123);
    if ( dword_1804543B0 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x400000002LL) )
    {
      ScenarioCounterStorage = Microsoft::Diagnostics::LifetimeManager::GetScenarioCounterStorage((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      v188 = 0;
      si128.m128i_i64[0] = 0;
      v132[0] = 0;
      v194 = 0;
      v195 = 0;
      LOWORD(v134) = 0;
      try
      {
        v132[0] = Microsoft::Diagnostics::ScenarioInst::PopulateTriggerInfoTlg();
        LOWORD(v134) = Microsoft::Diagnostics::ScenarioInst::PopulateSelectFieldsTlg(v142[0], &v194);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x2AD,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          v55);
        v19 = v130;
        v31 = v143[0];
        v138 = v127[0];
        v41 = v125;
        a5 = CurrentScenarioEscalationsByType;
        a6 = v140;
        v44 = v126[0];
      }
      v56 = 0x400000002LL;
      if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x400000002LL) )
      {
        v177 = v194;
        v178 = (unsigned __int16)(WORD4(v194) - v194);
        v171 = &v134;
        v172 = 2;
        v153 = v188;
        v154 = (unsigned __int16)(WORD4(v188) - v188);
        v133[0] = (std::_Ref_count_base *)v132;
        LODWORD(v133[1]) = 2;
        MetadataEngine = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_1803854C0;
        v58 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(MetadataEngine, v202, &v128);
        if ( v58[3] > 7u )
          v58 = (_QWORD *)*v58;
        v168 = v58;
        v59 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180385480;
        v60 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v59, v219, &v128);
        if ( v60[3] > 7u )
          v60 = (_QWORD *)*v60;
        v173 = v60;
        v61 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180385490;
        v62 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v61, v218, &v128);
        if ( v62[3] > 7u )
          v62 = (_QWORD *)*v62;
        v174 = v62;
        v63 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_1803854A0;
        v64 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v63, v217, &v128);
        if ( v64[3] > 7u )
          v64 = (_QWORD *)*v64;
        v176 = v64;
        v65 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_1803854B0;
        v66 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v65, v216, &v128);
        if ( v66[3] > 7u )
          v66 = (_QWORD *)*v66;
        v158 = v66;
        v67 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180385440;
        v68 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v67, v215, &v128);
        if ( v68[3] > 7u )
          v68 = (_QWORD *)*v68;
        v159 = v68;
        v69 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180385450;
        v70 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v69, v214, &v128);
        if ( v70[3] > 7u )
          v70 = (_QWORD *)*v70;
        v160 = v70;
        v71 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180385460;
        v72 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v71, v213, &v128);
        if ( v72[3] > 7u )
          v72 = (_QWORD *)*v72;
        v161 = v72;
        v162 = L"0";
        v73 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180385470;
        v74 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v73, v212, &v128);
        if ( v74[3] > 7u )
          v74 = (_QWORD *)*v74;
        v167 = v74;
        v75 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180385400;
        v76 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v75, v211, &v128);
        if ( v76[3] > 7u )
          v76 = (_QWORD *)*v76;
        v163 = v76;
        v77 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180385410;
        v78 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v77, v210, &v128);
        if ( v78[3] > 7u )
          v78 = (_QWORD *)*v78;
        v164 = v78;
        v79 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180385420;
        v80 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v79, v209, &v128);
        if ( v80[3] > 7u )
          v80 = (_QWORD *)*v80;
        v165 = v80;
        v81 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180385430;
        v82 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v81, v208, &v128);
        if ( v82[3] > 7u )
          v82 = (_QWORD *)*v82;
        v166 = v82;
        v83 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_1803853F0;
        v84 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v83, v207, &v128);
        if ( v84[3] > 7u )
          v84 = (_QWORD *)*v84;
        v156 = v84;
        v146 = *(_QWORD *)((*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 136LL))(
                             v31,
                             v186)
                         + 8);
        v85 = (_QWORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 136LL))(v31, v180);
        *(_QWORD *)&v128 = _tlgWrapBinary<wchar_t,2>(v181, *v85, (unsigned int)v146);
        v146 = *(_QWORD *)((*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 128LL))(
                             v31,
                             v182)
                         + 8);
        v86 = (_QWORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 128LL))(v31, v183);
        v146 = _tlgWrapBinary<wchar_t,2>(v184, *v86, (unsigned int)v146);
        v126[0] = v44;
        LOBYTE(v87) = -4;
        v140 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 192LL))(v31, v87);
        LOBYTE(v88) = -4;
        v89 = ScenarioCounterStorage;
        CurrentScenarioEscalationsByType = Microsoft::Diagnostics::ScenarioCounterStorage::GetCurrentScenarioEscalationsByType(
                                             ScenarioCounterStorage,
                                             v31,
                                             v88);
        LOBYTE(v90) = -3;
        v127[0] = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 192LL))(v31, v90);
        LOBYTE(v91) = -3;
        v147 = Microsoft::Diagnostics::ScenarioCounterStorage::GetCurrentScenarioEscalationsByType(v89, v31, v91);
        LOBYTE(v92) = -4;
        v148 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 184LL))(v31, v92);
        LOBYTE(v93) = -4;
        CurrentScenarioReportsByType = Microsoft::Diagnostics::ScenarioCounterStorage::GetCurrentScenarioReportsByType(
                                         v89,
                                         v31,
                                         v93);
        LOBYTE(v94) = -5;
        LODWORD(v150) = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 184LL))(v31, v94);
        LOBYTE(v95) = -5;
        v144[0] = Microsoft::Diagnostics::ScenarioCounterStorage::GetCurrentScenarioReportsByType(v89, v31, v95);
        LOBYTE(v96) = -3;
        LODWORD(v145) = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 184LL))(v31, v96);
        LOBYTE(v97) = -3;
        LODWORD(v137) = Microsoft::Diagnostics::ScenarioCounterStorage::GetCurrentScenarioReportsByType(v89, v31, v97);
        v98 = *(_QWORD *)((*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 88LL))(
                            v31,
                            v185)
                        + 8);
        v99 = (_QWORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 88LL))(v31, v179);
        v100 = _tlgWrapBinary<wchar_t,2>(v175, *v99, (unsigned int)v98);
        ScenarioCounterStorage = (struct Microsoft::Diagnostics::ScenarioCounterStorage *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v31 + 72LL))(v31);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
          v101,
          (unsigned int)word_1803EC9CA,
          v102,
          v103,
          (__int64)&ScenarioCounterStorage,
          (__int64)&v152,
          v100,
          (__int64)&v137,
          (__int64)&v145,
          (__int64)v144,
          (__int64)&v150,
          (__int64)&CurrentScenarioReportsByType,
          (__int64)&v148,
          (__int64)&v147,
          (__int64)v127,
          (__int64)&CurrentScenarioEscalationsByType,
          (__int64)&v140,
          (__int64)v126,
          v146,
          v128,
          (__int64)&v156,
          (__int64)&v166,
          (__int64)&v165,
          (__int64)&v164,
          (__int64)&v163,
          (__int64)&v167,
          (__int64)&v162,
          (__int64)&v161,
          (__int64)&v160,
          (__int64)&v159,
          (__int64)&v158,
          (__int64)&v176,
          (__int64)&v174,
          (__int64)&v173,
          (__int64)&v168,
          (__int64)v133,
          (__int64)&v153,
          (__int64)&v171,
          (__int64)&v177);
        std::wstring::_Tidy_deallocate(v207);
        std::wstring::_Tidy_deallocate(v208);
        std::wstring::_Tidy_deallocate(v209);
        std::wstring::_Tidy_deallocate(v210);
        std::wstring::_Tidy_deallocate(v211);
        std::wstring::_Tidy_deallocate(v212);
        std::wstring::_Tidy_deallocate(v213);
        std::wstring::_Tidy_deallocate(v214);
        std::wstring::_Tidy_deallocate(v215);
        std::wstring::_Tidy_deallocate(v216);
        std::wstring::_Tidy_deallocate(v217);
        std::wstring::_Tidy_deallocate(v218);
        std::wstring::_Tidy_deallocate(v219);
        std::wstring::_Tidy_deallocate(v202);
      }
      std::vector<enum gsl::byte>::_Tidy(&v194, v56);
      std::vector<enum gsl::byte>::_Tidy(&v188, v104);
    }
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v220);
    v126[0] = a6 != 0;
    v125 = a5 != 0;
    LOBYTE(v105) = a7;
    v106 = Microsoft::Diagnostics::EscalationUploadAction::_from_integral(&v134, v105);
    std::make_shared<Microsoft::Diagnostics::EscalationWorkItemOverrides,Microsoft::Diagnostics::EscalationUploadAction,std::wstring &,bool,bool,bool &>(
      (unsigned int)v169,
      v106,
      (unsigned int)pszPathOut,
      (unsigned int)&v125,
      (__int64)v126,
      (__int64)v198);
    v203[0] = v196[0];
    std::function<void (long,_GUID,_GUID)>::function<void (long,_GUID,_GUID)>(v204, v155);
    std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(
      v205,
      v142);
    std::wstring::wstring(v206, v200);
    EscalationEngine = Microsoft::Diagnostics::LifetimeManager::GetEscalationEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    *(_QWORD *)&v128 = v133;
    std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(
      v133,
      v169);
    v109 = v108;
    std::function_void___cdecl_long__::function_void___cdecl_long____Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_2____0_(
      v202,
      v203);
    std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(
      &v153,
      v142);
    LOBYTE(v110) = v41;
    v127[0] = Microsoft::Diagnostics::EscalationEngine::Execute(EscalationEngine, v31, v111, v110, v138, v112, v109);
    v133[0] = (std::_Ref_count_base *)L"EscalateApiFinished_0";
    v133[1] = (std::_Ref_count_base *)21;
    Microsoft::Diagnostics::AsimovSyntheticEvent::MakeScenarioSyntheticEvent(
      (unsigned int)v220,
      (unsigned int)v133,
      0x1000000,
      0,
      0);
    v113 = (_QWORD *)std::wstring::operator std::wstring_view(v201, v175);
    std::wstring::_Assign<wchar_t>(v221, *v113, v113[1]);
    (*(void (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 88LL))(v31, v175);
    v133[0] = (std::_Ref_count_base *)L"ScenarioName";
    v133[1] = (std::_Ref_count_base *)12;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v220, (int)v223);
    v133[0] = (std::_Ref_count_base *)L"ScenarioId";
    v133[1] = (std::_Ref_count_base *)10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v220, v223, v133, v200);
    v133[0] = (std::_Ref_count_base *)L"HRESULT";
    v133[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((int)v220, (int)v223);
    v114 = *(_OWORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 88LL))(v31, v175);
    v115 = std::wstring::wstring(&v194);
    *(_OWORD *)v133 = v114;
    v116 = Microsoft::Diagnostics::operator+(&v188, v115, v133);
    v117 = (_QWORD *)std::wstring::operator std::wstring_view(v116, v179);
    std::wstring::_Assign<wchar_t>(v222, *v117, v117[1]);
    std::wstring::_Tidy_deallocate(&v188);
    std::wstring::_Tidy_deallocate(&v194);
    *(_OWORD *)v133 = 0;
    Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(&v137, v133);
    v118 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v220);
    if ( v118 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x326,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)v118,
        v124);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v220);
    v119 = v127[0];
    if ( v127[0] >= 0 )
    {
      Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_2_::__lambda_2_(v203);
      if ( v170 )
        std::_Ref_count_base::_Decref(v170);
      std::wstring::_Tidy_deallocate(v201);
      std::wstring::_Tidy_deallocate(v200);
      std::vector<std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>>::~vector<std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>>(v157);
      if ( v142[1] )
        std::_Ref_count_base::_Decref(v142[1]);
      if ( v143[1] )
        std::_Ref_count_base::_Decref(v143[1]);
      std::wstring::_Tidy_deallocate(pszPathOut);
      std::wstring::_Tidy_deallocate(v190);
      std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v135);
      std::wstring::_Tidy_deallocate(v187);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
      if ( v19 )
      {
        v130 = 0;
        Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x329,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)v127[0],
        v124);
      Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_2_::__lambda_2_(v203);
      if ( v170 )
        std::_Ref_count_base::_Decref(v170);
      std::wstring::_Tidy_deallocate(v201);
      std::wstring::_Tidy_deallocate(v200);
      std::vector<std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>>::~vector<std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>>(v157);
      if ( v142[1] )
        std::_Ref_count_base::_Decref(v142[1]);
      if ( v143[1] )
        std::_Ref_count_base::_Decref(v143[1]);
      std::wstring::_Tidy_deallocate(pszPathOut);
      std::wstring::_Tidy_deallocate(v190);
      std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v135);
      std::wstring::_Tidy_deallocate(v187);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
      if ( v19 )
      {
        v130 = 0;
        Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
      }
      return v119;
    }
  }
}

```

## disassembly

```asm
0x1801f9dc4  mov     rax, rsp
0x1801f9dc7  push    rbx
0x1801f9dc8  push    rsi
0x1801f9dc9  push    rdi
0x1801f9dca  push    r12
0x1801f9dcc  push    r13
0x1801f9dce  push    r14
0x1801f9dd0  push    r15
0x1801f9dd2  sub     rsp, 0C30h
0x1801f9dd9  movaps  xmmword ptr [rax-48h], xmm6
0x1801f9ddd  mov     rax, cs:__security_cookie
0x1801f9de4  xor     rax, rsp
0x1801f9de7  mov     [rsp+0C68h+var_58], rax
0x1801f9def  mov     r14, r9
0x1801f9df2  mov     [rsp+0C68h+var_AD8], r8d
0x1801f9dfa  mov     rdi, rdx
0x1801f9dfd  mov     [rsp+0C68h+var_A50], rcx
0x1801f9e05  mov     eax, [rsp+0C68h+arg_20]
0x1801f9e0c  mov     [rsp+0C68h+var_AB4], eax
0x1801f9e13  mov     eax, [rsp+0C68h+arg_28]
0x1801f9e1a  mov     [rsp+0C68h+var_AB0], eax
0x1801f9e21  mov     r12, [rsp+0C68h+arg_40]
0x1801f9e29  mov     r13, [rsp+0C68h+arg_48]
0x1801f9e31  mov     r9, [rsp+0C68h+arg_50]
0x1801f9e39  mov     [rsp+0C68h+var_A28], r9
0x1801f9e41  mov     rdx, [rsp+0C68h+arg_58]
0x1801f9e49  mov     [rsp+0C68h+var_AC0], rdx
0x1801f9e51  mov     rcx, [rsp+0C68h+arg_60]
0x1801f9e59  mov     [rsp+0C68h+var_A70], rcx
0x1801f9e61  mov     eax, cs:dword_1804543B0
0x1801f9e67  cmp     eax, 4
0x1801f9e6a  jbe     loc_1801FA026
0x1801f9e70  mov     edx, 2000h
0x1801f9e75  lea     rcx, dword_1804543B0
0x1801f9e7c  call    _tlgKeywordOn
0x1801f9e81  xor     esi, esi
0x1801f9e83  test    al, al
0x1801f9e85  jz      short loc_1801F9EC9
0x1801f9e87  cmp     [r9+38h], rsi
0x1801f9e8b  setz    [rsp+0C68h+var_B28]
0x1801f9e93  mov     qword ptr [rsp+0C68h+var_A78], rdi
0x1801f9e9b  lea     rax, [rsp+0C68h+var_B28]
0x1801f9ea3  mov     [rsp+0C68h+var_C40], rax
0x1801f9ea8  lea     rax, [rsp+0C68h+var_A78]
0x1801f9eb0  mov     qword ptr [rsp+0C68h+var_C48], rax; int
0x1801f9eb5  lea     rdx, byte_1803ECD95
0x1801f9ebc  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &)
0x1801f9ec1  mov     r8d, [rsp+0C68h+var_AD8]
0x1801f9ec9  mov     rdx, [rsp+0C68h+var_AC0]
0x1801f9ed1  mov     rcx, [rsp+0C68h+var_A70]
0x1801f9ed9  mov     [rsp+0C68h+var_B08], rdi
0x1801f9ee1  mov     r15d, 1
0x1801f9ee7  mov     [rsp+0C68h+var_B00], r15b
0x1801f9eef  test    r14, r14
0x1801f9ef2  jz      loc_1801FBF84
0x1801f9ef8  test    r12, r12
0x1801f9efb  jz      loc_1801FBF84
0x1801f9f01  test    r13, r13
0x1801f9f04  jz      loc_1801FBF84
0x1801f9f0a  test    rdx, rdx
0x1801f9f0d  jz      short loc_1801F9F11
0x1801f9f0f  mov     [rdx], esi
0x1801f9f11  test    rcx, rcx
0x1801f9f14  jz      short loc_1801F9F21
0x1801f9f16  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801f9f1d  movdqu  xmmword ptr [rcx], xmm0
0x1801f9f21  cmp     r8d, r15d
0x1801f9f24  ja      loc_1801FBF49
0x1801f9f2a  cmp     [rsp+0C68h+arg_30], 2
0x1801f9f32  ja      loc_1801FBF0E
0x1801f9f38  mov     qword ptr [rsp+0C68h+var_B24+4], rsi
0x1801f9f40  xorps   xmm0, xmm0
0x1801f9f43  movups  [rsp+0C68h+var_8D0], xmm0
0x1801f9f4b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801f9f53  movdqu  [rsp+0C68h+var_8C0], xmm1
0x1801f9f5c  mov     word ptr [rsp+0C68h+var_8D0], si
0x1801f9f64  lea     r8, [rsp+0C68h+var_8D0]
0x1801f9f6c  lea     rdx, [rsp+0C68h+var_B24+4]
0x1801f9f74  call    ?GetRpcImpersonationToken@ApiServer@Diagnostics@Microsoft@@IEBAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::ApiServer::GetRpcImpersonationToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,std::wstring &)
0x1801f9f79  mov     ebx, eax
0x1801f9f7b  test    eax, eax
0x1801f9f7d  jns     short loc_1801F9FD4
0x1801f9f7f  mov     rcx, [rsp+0C68h]; this
0x1801f9f87  mov     r9d, eax; char *
0x1801f9f8a  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801f9f91  mov     edx, 1CFh; void *
0x1801f9f96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f9f9b  nop
0x1801f9f9c  lea     rcx, [rsp+0C68h+var_8D0]
0x1801f9fa4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801f9fa9  nop
0x1801f9faa  lea     rcx, [rsp+0C68h+var_B24+4]
0x1801f9fb2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801f9fb7  nop
0x1801f9fb8  mov     [rsp+0C68h+var_B00], sil
0x1801f9fc0  lea     rcx, [rsp+0C68h+var_B08]
0x1801f9fc8  call    _Microsoft__Diagnostics__UtcApiManager__EscalateScenarioImpl____3____lambda_1___operator__
0x1801f9fcd  mov     eax, ebx
0x1801f9fcf  jmp     loc_1801FBFC6
0x1801f9fd4  lea     rcx, [rsp+0C68h+var_AD0]
0x1801f9fdc  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UCaseInsensitiveLessThanPredicate@String@Utils@Diagnostics@Microsoft@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::pair<std::wstring const,std::wstring>>>::map<std::wstring,std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::pair<std::wstring const,std::wstring>>>(void)
0x1801f9fe1  nop
0x1801f9fe2  mov     ebx, esi
0x1801f9fe4  cmp     ebx, [rsp+0C68h+arg_38]
0x1801f9feb  jnb     loc_1801FA095
0x1801f9ff1  mov     eax, ebx
0x1801f9ff3  lea     r8, [r12+rax*8]
0x1801f9ff7  cmp     [r8], rsi
0x1801f9ffa  jz      short loc_1801FA02D
0x1801f9ffc  lea     r9, ds:0[rax*8]
0x1801fa004  add     r9, r13
0x1801fa007  cmp     [r9], rsi
0x1801fa00a  jz      short loc_1801FA02D
0x1801fa00c  lea     rdx, [rsp+0C68h+var_AE8]
0x1801fa014  lea     rcx, [rsp+0C68h+var_AD0]
0x1801fa01c  call    ??$_Emplace@AEAPEB_WAEAPEB_W@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@_N@1@AEAPEB_W0@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Emplace<wchar_t const * &,wchar_t const * &>(wchar_t const * &,wchar_t const * &)
0x1801fa021  add     ebx, r15d
0x1801fa024  jmp     short loc_1801F9FE4
0x1801fa026  xor     esi, esi
0x1801fa028  jmp     loc_1801F9ED9
0x1801fa02d  mov     rcx, [rsp+0C68h]; this
0x1801fa035  mov     ebx, 80070057h
0x1801fa03a  mov     r9d, ebx; char *
0x1801fa03d  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801fa044  mov     edx, 1D8h; void *
0x1801fa049  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa04e  nop
0x1801fa04f  lea     rcx, [rsp+0C68h+var_AD0]
0x1801fa057  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801fa05c  nop
0x1801fa05d  lea     rcx, [rsp+0C68h+var_8D0]
0x1801fa065  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa06a  nop
0x1801fa06b  lea     rcx, [rsp+0C68h+var_B24+4]
0x1801fa073  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801fa078  nop
0x1801fa079  mov     [rsp+0C68h+var_B00], sil
0x1801fa081  lea     rcx, [rsp+0C68h+var_B08]
0x1801fa089  call    _Microsoft__Diagnostics__UtcApiManager__EscalateScenarioImpl____3____lambda_1___operator__
0x1801fa08e  mov     eax, ebx
0x1801fa090  jmp     loc_1801FBFC6
0x1801fa095  lea     r9, [rsp+0C68h+var_AD0]
0x1801fa09d  lea     r8, [rsp+0C68h+var_B24+4]
0x1801fa0a5  lea     rdx, [rsp+0C68h+var_830]
0x1801fa0ad  call    ?ProcessApiMetaProperties@UtcApiManager@Diagnostics@Microsoft@@AEAA?AV?$tuple@U_GUID@@_NJ_N@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@5@@Z; Microsoft::Diagnostics::UtcApiManager::ProcessApiMetaProperties(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::map<std::wstring,std::wstring> &)
0x1801fa0b2  movsxd  rax, [rsp+0C68h+var_82C]
0x1801fa0ba  mov     qword ptr [rsp+0C68h+var_A78], rax
0x1801fa0c2  mov     rdx, [rsp+0C68h+var_A50]
0x1801fa0ca  add     rdx, 0E0h
0x1801fa0d1  lea     r8, [rsp+0C68h+var_A78]
0x1801fa0d9  lea     rcx, [rsp+0C68h+var_AA8]
0x1801fa0e1  call    ??$?0_JU?$ratio@$00$0DOI@@std@@@?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@AEAVrecursive_timed_mutex@1@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::unique_lock<std::recursive_timed_mutex>::unique_lock<std::recursive_timed_mutex>(std::recursive_timed_mutex &,std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x1801fa0e6  nop
0x1801fa0e7  cmp     [rsp+0C68h+var_AA0], sil
0x1801fa0ef  jnz     short loc_1801FA167
0x1801fa0f1  mov     rcx, [rsp+0C68h]; this
0x1801fa0f9  mov     ebx, 87C5102Bh
0x1801fa0fe  mov     r9d, ebx; char *
0x1801fa101  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801fa108  mov     edx, 1E7h; void *
0x1801fa10d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa112  nop
0x1801fa113  lea     rcx, [rsp+0C68h+var_AA8]
0x1801fa11b  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x1801fa120  nop
0x1801fa121  lea     rcx, [rsp+0C68h+var_AD0]
0x1801fa129  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801fa12e  nop
0x1801fa12f  lea     rcx, [rsp+0C68h+var_8D0]
0x1801fa137  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa13c  nop
0x1801fa13d  lea     rcx, [rsp+0C68h+var_B24+4]
0x1801fa145  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801fa14a  nop
0x1801fa14b  mov     [rsp+0C68h+var_B00], sil
0x1801fa153  lea     rcx, [rsp+0C68h+var_B08]
0x1801fa15b  call    _Microsoft__Diagnostics__UtcApiManager__EscalateScenarioImpl____3____lambda_1___operator__
0x1801fa160  mov     eax, ebx
0x1801fa162  jmp     loc_1801FBFC6
0x1801fa167  mov     rdx, r14
0x1801fa16a  lea     rcx, [rsp+0C68h+var_890]
0x1801fa172  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801fa177  nop
0x1801fa178  lea     rcx, [rsp+0C68h+var_890]
0x1801fa180  mov     r13d, 7
0x1801fa186  cmp     [rsp+0C68h+var_878], r13
0x1801fa18e  cmova   rcx, [rsp+0C68h+var_890]
0x1801fa197  lea     r9d, [r13+28h]
0x1801fa19b  xor     r8d, r8d
0x1801fa19e  mov     rdx, [rsp+0C68h+var_880]
0x1801fa1a6  call    ??$_Traits_find_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_find_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x1801fa1ab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801fa1af  jz      loc_1801FA239
0x1801fa1b5  mov     rcx, [rsp+0C68h]; this
0x1801fa1bd  mov     ebx, 80070057h
0x1801fa1c2  mov     r9d, ebx; char *
0x1801fa1c5  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801fa1cc  mov     edx, 1F0h; void *
0x1801fa1d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa1d6  nop
0x1801fa1d7  lea     rcx, [rsp+0C68h+var_890]
0x1801fa1df  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa1e4  nop
0x1801fa1e5  lea     rcx, [rsp+0C68h+var_AA8]
0x1801fa1ed  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x1801fa1f2  nop
0x1801fa1f3  lea     rcx, [rsp+0C68h+var_AD0]
0x1801fa1fb  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801fa200  nop
0x1801fa201  lea     rcx, [rsp+0C68h+var_8D0]
0x1801fa209  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa20e  nop
0x1801fa20f  lea     rcx, [rsp+0C68h+var_B24+4]
0x1801fa217  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801fa21c  nop
0x1801fa21d  mov     [rsp+0C68h+var_B00], sil
0x1801fa225  lea     rcx, [rsp+0C68h+var_B08]
0x1801fa22d  call    _Microsoft__Diagnostics__UtcApiManager__EscalateScenarioImpl____3____lambda_1___operator__
0x1801fa232  mov     eax, ebx
0x1801fa234  jmp     loc_1801FBFC6
0x1801fa239  xor     r8d, r8d
0x1801fa23c  mov     rdx, [rsp+0C68h+var_880]
0x1801fa244  lea     rcx, [rsp+0C68h+pszPathOut]
0x1801fa24c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x1801fa251  nop
0x1801fa252  mov     rdx, [rsp+0C68h+var_860]
0x1801fa25a  lea     rcx, [rsp+0C68h+pszPathOut]
0x1801fa262  cmp     [rsp+0C68h+var_858], r13
0x1801fa26a  cmova   rcx, [rsp+0C68h+pszPathOut]; pszPathOut
0x1801fa273  inc     rdx; cchPathOut
0x1801fa276  mov     r9d, r15d; dwFlags
0x1801fa279  mov     r8, r14; pszPathIn
0x1801fa27c  call    cs:__imp_PathCchCanonicalizeEx
0x1801fa282  test    eax, eax
0x1801fa284  jns     loc_1801FA31C
0x1801fa28a  mov     rcx, [rsp+0C68h]; this
0x1801fa292  mov     ebx, 80070057h
0x1801fa297  mov     r9d, ebx; char *
0x1801fa29a  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801fa2a1  mov     edx, 1F7h; void *
0x1801fa2a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa2ab  nop
0x1801fa2ac  lea     rcx, [rsp+0C68h+pszPathOut]
0x1801fa2b4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa2b9  nop
0x1801fa2ba  lea     rcx, [rsp+0C68h+var_890]
0x1801fa2c2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa2c7  nop
0x1801fa2c8  lea     rcx, [rsp+0C68h+var_AA8]
0x1801fa2d0  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x1801fa2d5  nop
0x1801fa2d6  lea     rcx, [rsp+0C68h+var_AD0]
0x1801fa2de  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801fa2e3  nop
0x1801fa2e4  lea     rcx, [rsp+0C68h+var_8D0]
0x1801fa2ec  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa2f1  nop
0x1801fa2f2  lea     rcx, [rsp+0C68h+var_B24+4]
0x1801fa2fa  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801fa2ff  nop
0x1801fa300  mov     [rsp+0C68h+var_B00], sil
0x1801fa308  lea     rcx, [rsp+0C68h+var_B08]
0x1801fa310  call    _Microsoft__Diagnostics__UtcApiManager__EscalateScenarioImpl____3____lambda_1___operator__
0x1801fa315  mov     eax, ebx
0x1801fa317  jmp     loc_1801FBFC6
0x1801fa31c  xor     eax, eax
0x1801fa31e  lock cmpxchg qword ptr cs:xmmword_180463150, rsi
0x1801fa327  jz      loc_1801FBE7D
0x1801fa32d  xor     eax, eax
0x1801fa32f  lock cmpxchg qword ptr cs:xmmword_180463190+8, rsi
0x1801fa338  jz      loc_1801FBDEC
0x1801fa33e  lea     r12, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; Microsoft::Diagnostics::LifetimeManager gs_lifetimeManager
0x1801fa345  mov     rcx, r12; this
0x1801fa348  call    ?GetScenarioManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioManager(void)
0x1801fa34d  mov     r8, rdi
0x1801fa350  lea     rdx, [rsp+0C68h+var_AF8]
0x1801fa358  mov     rcx, rax
0x1801fa35b  call    ?GetScenarioState@ScenarioManager@Diagnostics@Microsoft@@QEBA?AVScenarioActivityState@23@AEBU_GUID@@@Z; Microsoft::Diagnostics::ScenarioManager::GetScenarioState(_GUID const &)
0x1801fa360  cmp     [rsp+0C68h+var_AF8], sil
0x1801fa368  jz      loc_1801FA400
0x1801fa36e  mov     rcx, [rsp+0C68h]; this
0x1801fa376  mov     ebx, 87C51005h
0x1801fa37b  mov     r9d, ebx; char *
0x1801fa37e  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801fa385  mov     edx, 20Ah; void *
0x1801fa38a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa38f  nop
0x1801fa390  lea     rcx, [rsp+0C68h+pszPathOut]
0x1801fa398  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa39d  nop
0x1801fa39e  lea     rcx, [rsp+0C68h+var_890]
0x1801fa3a6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa3ab  nop
0x1801fa3ac  lea     rcx, [rsp+0C68h+var_AA8]
0x1801fa3b4  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x1801fa3b9  nop
0x1801fa3ba  lea     rcx, [rsp+0C68h+var_AD0]
0x1801fa3c2  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801fa3c7  nop
0x1801fa3c8  lea     rcx, [rsp+0C68h+var_8D0]
  ... truncated ...
```
