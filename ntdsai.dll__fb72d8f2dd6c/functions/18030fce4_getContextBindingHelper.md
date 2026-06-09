# getContextBindingHelper

- ea: `0x18030fce4`
- end: `0x180311acc`
- name: `getContextBindingHelper`
- size: `7656`
- prototype: ``
- caller_count: `1`
- callee_count: `41`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180305138`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000bb80`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180021a97`
- `0x180030af8`
- `0x180030bd4`
- `0x1800342d4`
- `0x1800f80e0`
- `0x1800f8280`
- `0x180172b98`
- `0x180172edc`
- `0x1801737f0`
- `0x180173e2c`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`
- `0x180181db0`
- `0x1801f2f9c`
- `0x180256abc`
- `0x18025b130`
- `0x18025b1d0`
- `0x1802903d8`
- `0x18030113c`
- `0x180301f24`
- `0x180302d10`
- `0x180303df0`
- `0x180304c04`
- `0x180305a98`
- `0x18030c148`
- `0x18030d02c`
- `0x18030d6c4`
- `0x18030e550`
- `0x18030fcc4`
- `0x18030fce4`
- `0x180311ad4`
- `0x180430790`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18031127c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18031127c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180310ba1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180310e0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180310ba1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180310e0f`
- `RPCRT4!RpcBindingSetOption` at `0x180310139`
- `RPCRT4!RpcBindingSetOption` at `0x18031037e`
- `RPCRT4!RpcBindingSetOption` at `0x180310139`
- `RPCRT4!RpcBindingSetOption` at `0x18031037e`
- `RPCRT4!RpcBindingFree` at `0x180310763`
- `RPCRT4!RpcBindingFree` at `0x180311983`
- `RPCRT4!RpcBindingFree` at `0x180310763`
- `RPCRT4!RpcBindingFree` at `0x180311983`
- `RPCRT4!NdrClientCall3` at `0x1803102fb`
- `RPCRT4!NdrClientCall3` at `0x1803102fb`
- `RPCRT4!RpcBindingCopy` at `0x1803112f5`
- `RPCRT4!RpcBindingCopy` at `0x1803112f5`
- `RPCRT4!I_RpcGetExtendedError` at `0x18031031a`
- `RPCRT4!I_RpcGetExtendedError` at `0x180310394`
- `RPCRT4!I_RpcGetExtendedError` at `0x18031031a`
- `RPCRT4!I_RpcGetExtendedError` at `0x180310394`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18031043b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1804718ea`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18031043b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1804718ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180311768`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180471918`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180311768`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180471918`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18031129d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18031129d`

## pseudocode

```c
__int64 __fastcall getContextBindingHelper(
        __int64 a1,
        unsigned int *a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        unsigned int *a7)
{
  char v7; // r15
  CLIENT_CALL_RETURN v9; // rbx
  int v10; // edi
  RPC_BINDING_HANDLE v11; // rdx
  __int64 *v12; // rax
  _WORD *v13; // rax
  __int64 v14; // rcx
  const wchar_t *v15; // r15
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rax
  int v25; // edx
  unsigned int v26; // eax
  unsigned int v27; // ebx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // r8
  __int64 v34; // r9
  BOOL v35; // ebx
  bool v36; // zf
  int v37; // eax
  RPC_STATUS ExtendedError; // eax
  unsigned int v39; // ecx
  int v40; // eax
  unsigned int v41; // r8d
  LPOVERLAPPED v42; // rax
  __int64 v43; // rdx
  const wchar_t *v44; // rax
  int v45; // r9d
  wchar_t *v46; // rdx
  __int64 v47; // rcx
  const wchar_t *v48; // rax
  wchar_t *v49; // rcx
  unsigned int *v50; // rbx
  __int64 v51; // rcx
  __int64 *v52; // rcx
  char *v53; // r15
  LPOVERLAPPED v54; // rbx
  __int64 v55; // rcx
  __int64 v56; // rdx
  LPOVERLAPPED v57; // rbx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // r15
  _DWORD *v61; // rax
  __int64 v62; // rcx
  _DWORD *v63; // r8
  const void *v64; // rdx
  const void *v65; // rcx
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 v70; // r8
  __int64 v71; // r9
  int v72; // eax
  int v73; // ebx
  unsigned int v74; // r15d
  __int64 BHCacheElement; // rax
  RPC_BINDING_HANDLE *v76; // rax
  RPC_BINDING_HANDLE *v77; // rbx
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // r8
  __int64 v81; // r9
  __int64 v82; // r8
  __int64 v83; // r9
  BOOL v84; // ebx
  int v85; // eax
  __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // r8
  __int64 v89; // r9
  __int64 v90; // r8
  __int64 v91; // r9
  BOOL v92; // r15d
  int v93; // eax
  __int64 v94; // rdx
  int v95; // edx
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 v98; // r8
  __int64 v99; // r9
  __int64 v100; // r8
  __int64 v101; // r9
  BOOL v102; // r15d
  int v103; // eax
  __int64 v104; // rdx
  int v105; // edx
  __int64 v106; // rdx
  __int64 v107; // rcx
  __int64 v108; // r8
  __int64 v109; // r9
  __int64 v110; // r8
  __int64 v111; // r9
  BOOL v112; // ebx
  int v113; // eax
  __int64 v114; // rdx
  unsigned int v115; // r15d
  __int64 v116; // rdx
  __int64 v117; // r8
  __int64 v118; // r9
  __int64 v119; // r8
  __int64 v120; // r9
  BOOL v121; // r15d
  int v122; // eax
  __int64 v123; // rdx
  __int64 v124; // rcx
  __int64 v125; // r8
  __int64 v126; // r9
  unsigned int v127; // r15d
  __int64 v128; // r8
  __int64 v129; // r9
  BOOL v130; // ebx
  __int64 v131; // rax
  __int64 v132; // rdx
  char v133; // r8
  int v135[2]; // [rsp+28h] [rbp-450h]
  __int64 *v136; // [rsp+30h] [rbp-448h]
  RPC_BINDING_HANDLE *p_DestinationBinding; // [rsp+38h] [rbp-440h]
  __int64 v138; // [rsp+40h] [rbp-438h]
  __int64 v139; // [rsp+40h] [rbp-438h]
  char v140; // [rsp+58h] [rbp-420h]
  char v141[4]; // [rsp+70h] [rbp-408h]
  int v142; // [rsp+70h] [rbp-408h]
  BOOL v144; // [rsp+78h] [rbp-400h]
  int v145; // [rsp+78h] [rbp-400h]
  BOOL v146; // [rsp+78h] [rbp-400h]
  unsigned int v147; // [rsp+90h] [rbp-3E8h]
  unsigned int BindingTimeoutMins; // [rsp+98h] [rbp-3E0h]
  __int64 v149; // [rsp+A0h] [rbp-3D8h] BYREF
  int v150; // [rsp+A8h] [rbp-3D0h]
  int Internal; // [rsp+ACh] [rbp-3CCh]
  __int64 v152; // [rsp+B0h] [rbp-3C8h]
  int v153; // [rsp+B8h] [rbp-3C0h]
  int v154; // [rsp+BCh] [rbp-3BCh]
  __int64 v155; // [rsp+C0h] [rbp-3B8h]
  __int64 v156; // [rsp+C8h] [rbp-3B0h]
  __int64 v157; // [rsp+D0h] [rbp-3A8h]
  __int64 v158; // [rsp+D8h] [rbp-3A0h]
  __int64 v159; // [rsp+E0h] [rbp-398h]
  int v160; // [rsp+E8h] [rbp-390h]
  __int64 v161; // [rsp+ECh] [rbp-38Ch]
  int v162; // [rsp+F4h] [rbp-384h]
  _DWORD *v163; // [rsp+F8h] [rbp-380h]
  wchar_t *Str; // [rsp+100h] [rbp-378h]
  RPC_BINDING_HANDLE hBinding; // [rsp+108h] [rbp-370h] BYREF
  __int64 v166; // [rsp+110h] [rbp-368h]
  RPC_BINDING_HANDLE DestinationBinding; // [rsp+118h] [rbp-360h] BYREF
  int v168; // [rsp+120h] [rbp-358h]
  int v169; // [rsp+124h] [rbp-354h]
  _DWORD *Simple; // [rsp+128h] [rbp-350h]
  __int64 v171; // [rsp+130h] [rbp-348h] BYREF
  __int64 v172; // [rsp+138h] [rbp-340h]
  wchar_t *v173; // [rsp+140h] [rbp-338h] BYREF
  unsigned int *v174; // [rsp+148h] [rbp-330h]
  _DWORD *v175; // [rsp+150h] [rbp-328h]
  _DWORD *v176; // [rsp+158h] [rbp-320h]
  __int64 v177; // [rsp+160h] [rbp-318h]
  __int64 v178; // [rsp+168h] [rbp-310h]
  _WORD *v179; // [rsp+170h] [rbp-308h]
  int v180; // [rsp+178h] [rbp-300h]
  __int64 v181; // [rsp+180h] [rbp-2F8h]
  __int64 *v182; // [rsp+188h] [rbp-2F0h]
  __int64 v183; // [rsp+190h] [rbp-2E8h] BYREF
  int v184; // [rsp+198h] [rbp-2E0h]
  DWORD Offset; // [rsp+19Ch] [rbp-2DCh]
  __int64 v186; // [rsp+1A0h] [rbp-2D8h]
  int v187; // [rsp+1A8h] [rbp-2D0h]
  int v188; // [rsp+1ACh] [rbp-2CCh]
  __int64 v189; // [rsp+1B0h] [rbp-2C8h]
  __int64 v190; // [rsp+1B8h] [rbp-2C0h]
  __int64 v191; // [rsp+1C0h] [rbp-2B8h]
  __int64 v192; // [rsp+1C8h] [rbp-2B0h]
  __int64 v193; // [rsp+1D0h] [rbp-2A8h]
  int v194; // [rsp+1D8h] [rbp-2A0h]
  __int64 v195; // [rsp+1DCh] [rbp-29Ch]
  int v196; // [rsp+1E4h] [rbp-294h]
  _DWORD *v197; // [rsp+1E8h] [rbp-290h]
  unsigned int *v198; // [rsp+1F8h] [rbp-280h]
  __int64 v199; // [rsp+200h] [rbp-278h]
  _DWORD v200[2]; // [rsp+210h] [rbp-268h] BYREF
  const wchar_t *v201; // [rsp+218h] [rbp-260h]
  int v202; // [rsp+230h] [rbp-248h]
  wchar_t *v203; // [rsp+238h] [rbp-240h]
  __int64 v204; // [rsp+248h] [rbp-230h] BYREF
  int v205; // [rsp+250h] [rbp-228h]
  __int64 *v206; // [rsp+258h] [rbp-220h]
  __int64 v207; // [rsp+268h] [rbp-210h] BYREF

  v7 = a4;
  v166 = a3;
  v177 = a1;
  v199 = a1;
  v198 = a2;
  v174 = a2;
  v181 = a3;
  v172 = a6;
  LODWORD(v9.Pointer) = 87;
  v147 = 8430;
  v10 = 0;
  hBinding = 0;
  DestinationBinding = 0;
  v171 = 0;
  Str = 0;
  v180 = 0;
  v168 = 0;
  v169 = 0;
  v176 = qword_18052B3B8;
  v173 = 0;
  if ( !(unsigned int)IsValidDSInstance(a2) )
  {
    DoLogUnhandledError2(83889918, &word_18049B11A, 8430, 1);
    DraExcept(8436, 8430, 83889919, 1);
  }
  if ( (v7 & 0x10) != 0 )
  {
    v12 = g_guidNtdsapi;
LABEL_8:
    v182 = v12;
    goto LABEL_9;
  }
  if ( qword_18052B2A8 )
  {
    v12 = (__int64 *)((char *)qword_18052B2A8 + 8);
    goto LABEL_8;
  }
  v182 = 0;
LABEL_9:
  if ( *(_DWORD *)gfADAM )
    *(_DWORD *)v141 = (unsigned int)GetReplAuthenticationMode() != 2 ? 2 : 0;
  else
    *(_DWORD *)v141 = 0;
  v175 = a2 + 1;
  if ( a2[1] )
    v13 = (_WORD *)((char *)a2 + a2[1]);
  else
    v13 = 0;
  v179 = v13;
  v178 = (__int64)v13;
  v14 = 92;
  if ( *v13 == 92 )
  {
    do
      v179 = ++v13;
    while ( *v13 == 92 );
    v178 = (__int64)v13;
  }
  v15 = L"[]";
  while ( 1 )
  {
    if ( (unsigned int)THStateCheckForTraceOverride(v14, v11)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 8)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v17, v16)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v17, v16, v18, v19)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 8)) )
    {
      v144 = gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v17, v16)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v17, v16, v20, v21)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 8));
      if ( (unsigned int)THStateCheckForTraceOverride(v17, v16)
        || (v22 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 8), v23 = 0, v22) )
      {
        v23 = 1;
      }
      v24 = DsaRpcInstanceDisplayName(a2, v23);
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        83889959,
        4,
        8,
        v25,
        v144,
        33,
        &WPP_9b5b8db6ac56383dc74d600fee488739_Traceguids,
        v24);
    }
    if ( !gfIsDrsClientLibInitialized || eServiceShutdown )
    {
      *a7 = 8463;
      return 0;
    }
    if ( *(_DWORD *)gfADAM )
    {
      Simple = (_DWORD *)v178;
    }
    else
    {
      if ( !v173 )
      {
        v147 = resolveDnsAddressWithFallback(v177, v178, &v173);
        if ( v147 || !v173 || !*(_QWORD *)v173 )
        {
          v147 = 8524;
          goto LABEL_84;
        }
      }
      Simple = *(_DWORD **)v173;
    }
    if ( (a4 & 8) == 0 )
      goto LABEL_48;
    LODWORD(v9.Pointer) = ImpersonateAnyClient();
    if ( !LODWORD(v9.Pointer) )
    {
      v169 = 1;
LABEL_48:
      LODWORD(p_DestinationBinding) = gfUseUniqueAssoc;
      LODWORD(v136) = *(_DWORD *)v141;
      v135[0] = a5;
      v147 = DRSGetRpcBinding(v177, a2, v178, Simple, v166, *(_QWORD *)v135);
      if ( !v147 )
      {
        v145 = dword_180528620;
        v26 = RpcBindingSetOption(hBinding, 0xCu, (unsigned int)(60000 * dword_180528620));
        v27 = v26;
        v147 = v26;
        if ( v26 )
        {
          LogRpcExtendedErrorInfo(v177, v26, a2, 83890032);
          DraExcept(v27, 0, 83890033, 1);
        }
        v28 = v172;
        *(_DWORD *)(*(_QWORD *)v172 + 476LL) = 2;
        *(_DWORD *)(*(_QWORD *)v28 + 460LL) = v145;
        if ( (a4 & 4) != 0 )
          InitRpcSessionEncryption(v177, 0, hBinding);
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
          || (unsigned int)THStateCheckForTraceOverride(v30, v29)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 8)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v30, v29)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v30, v29, v31, v32)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 8)) )
        {
          v35 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v30, v29)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v30, v29, v33, v34)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 8));
          if ( (unsigned int)THStateCheckForTraceOverride(v30, v29)
            || (v36 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 8) == 0, v37 = 0, !v36) )
          {
            v37 = 1;
          }
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            83890048,
            4,
            8,
            v37,
            v35,
            34,
            &WPP_9b5b8db6ac56383dc74d600fee488739_Traceguids);
        }
        Simple = 0;
        p_DestinationBinding = &DestinationBinding;
        v136 = &v171;
        v9.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18048AA10, 0, 0, hBinding, v182, v176).Pointer;
        Simple = (_DWORD *)v9.Simple;
        if ( LODWORD(v9.Pointer) == 1825 )
        {
          ExtendedError = I_RpcGetExtendedError();
          if ( ExtendedError )
          {
            if ( ExtendedError < 0 )
              ExtendedError = MapRpcExtendedHResultToWin32((unsigned int)ExtendedError);
            LODWORD(v9.Pointer) = ExtendedError;
          }
        }
        if ( !LODWORD(v9.Pointer) )
        {
          if ( (a4 & 4) != 0 && (!v171 || *(_DWORD *)v171 < 2u || (*(_BYTE *)(v171 + 5) & 0x20) == 0) )
            LODWORD(v9.Pointer) = 8454;
          if ( !LODWORD(v9.Pointer) && gfUseUniqueAssoc )
            RpcBindingSetOption(hBinding, 0xDu, 1u);
        }
      }
    }
LABEL_84:
    if ( v168 )
    {
      RevertToSelf();
    }
    else if ( v169 )
    {
      UnImpersonateAnyClient();
    }
    v39 = v147;
    if ( !v147 || *(_DWORD *)v141 )
      goto LABEL_133;
    v40 = 0;
    switch ( v147 )
    {
      case 5u:
        goto LABEL_94;
      case 0x574u:
        goto LABEL_95;
      case 0x774u:
      case 0x80090322:
LABEL_94:
        if ( !*(_DWORD *)gfADAM )
          break;
LABEL_95:
        v40 = dword_180527F68;
        break;
    }
    if ( !v40 )
      break;
    v41 = (*(_DWORD *)gfADAM != 0) + 1;
    *(_DWORD *)v141 = v41;
    v42 = gpDsEventConfig;
    if ( gpDsEventConfig )
    {
      if ( SHIDWORD(gpDsEventConfig[11].Internal) < 1 )
      {
        if ( (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(1280, 1))
          && !(unsigned int)DoLogMsgOverride(2147486160LL) )
        {
          goto LABEL_115;
        }
        v41 = *(_DWORD *)v141;
        v42 = gpDsEventConfig;
        v39 = v147;
      }
      v152 = 1;
      v158 = 0;
      v161 = 0;
      v162 = 0;
      Internal = v42[11].Internal;
      v150 = -2147481136;
      v153 = 0;
      v154 = 1;
      v163 = v200;
      v200[0] = 1;
      if ( a2 )
      {
        v43 = a2[3];
        if ( (-(__int64)(a2[3] != 0) & ((unsigned __int64)v174 + v43)) != 0 )
        {
          v44 = (const wchar_t *)(((unsigned __int64)v174 + v43) & -(__int64)((_DWORD)v43 != 0));
        }
        else if ( *v175 )
        {
          v44 = (const wchar_t *)((char *)a2 + (unsigned int)*v175);
        }
        else
        {
          v44 = 0;
        }
      }
      else
      {
        v44 = L"[]";
      }
      v201 = v44;
      v149 = 1;
      v202 = 10;
      v45 = 2;
      do
      {
        *(_QWORD *)&v163[8 * v149 + 6] = v39;
        *(_QWORD *)&v163[8 * v149 + 2] = &v163[8 * v149 + 6];
        ++v149;
        v163[8 * v149] = 5;
        --v45;
        v39 = v147;
      }
      while ( v45 );
      *(_QWORD *)&v163[8 * v149 + 6] = v41;
      *(_QWORD *)&v163[8 * v149 + 2] = &v163[8 * v149 + 6];
      ++v149;
      v163[8 * v149] = 1;
      v46 = L"<NULL>";
      if ( Str )
        v46 = Str;
      *(_QWORD *)&v163[8 * v149++ + 2] = v46;
      v163[8 * v149] = 0;
      *(_QWORD *)&v163[8 * v149++ + 2] = "Replicator Allow SPN Fallback";
      v157 = 0;
      v156 = 1280;
      v155 = 1;
      v159 = 0;
      v160 = 0;
      DoLogEventAndTrace(&v149);
    }
LABEL_115:
    if ( hBinding )
      RpcBindingFree(&hBinding);
    v14 = (__int64)Str;
    if ( Str )
    {
      DSFreeAux(Str, 83890156);
      Str = 0;
    }
  }
  if ( v147 == 1396
    && gpDsEventConfig
    && ((gpDsEventConfig[11].Internal & 0x8000000000000000uLL) == 0LL
     || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(1280, 0)
     || (unsigned int)DoLogMsgOverride(3221227117LL)) )
  {
    v152 = 0;
    v158 = 0;
    v161 = 0;
    v162 = 0;
    Internal = gpDsEventConfig[11].Internal;
    v150 = -1073740179;
    v153 = 0;
    v154 = 1;
    v163 = v200;
    v200[0] = 1;
    if ( a2 )
    {
      v47 = a2[3];
      if ( (-(__int64)(a2[3] != 0) & ((unsigned __int64)v174 + v47)) != 0 )
      {
        v48 = (const wchar_t *)(((unsigned __int64)v174 + v47) & -(__int64)((_DWORD)v47 != 0));
      }
      else if ( *v175 )
      {
        v48 = (const wchar_t *)((char *)a2 + (unsigned int)*v175);
      }
      else
      {
        v48 = 0;
      }
    }
    else
    {
      v48 = L"[]";
    }
    v201 = v48;
    v202 = 1;
    v203 = Str;
    v149 = 2;
    v157 = 0;
    v156 = 1280;
    v155 = 1;
    v159 = 0;
    v160 = 0;
    DoLogEventAndTrace(&v149);
  }
LABEL_133:
  v142 = 0;
  v49 = v173;
  if ( v173 )
  {
    GetIpFreeW();
    v173 = 0;
  }
  if ( !v147 )
  {
    if ( *(_DWORD *)gfADAM )
    {
      if ( LODWORD(v9.Pointer) )
        goto LABEL_316;
      if ( v176 && *v176 >= 0x30u )
      {
        v60 = (__int64)(v176 + 9);
        v61 = v176 + 9;
      }
      else
      {
        v61 = 0;
        v60 = (__int64)(v176 + 9);
      }
      if ( v61 )
      {
        if ( !v176 || (v62 = v60, *v176 < 0x30u) )
          v62 = 0;
        if ( !(unsigned int)fNullUuid(v62) )
        {
          if ( !v171 || (v64 = (const void *)(v171 + 36), *(_DWORD *)v171 < 0x30u) )
            v64 = 0;
          if ( !v63 || (v65 = (const void *)v60, *v63 < 0x30u) )
            v65 = 0;
          if ( memcmp_0(v65, v64, 0x10u) )
          {
            LODWORD(v9.Pointer) = 8593;
            if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
              || (unsigned int)THStateCheckForTraceOverride(v67, v66)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 8)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v67, v66)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v67, v66, v68, v69)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 8)) )
            {
              if ( v171 && *(_DWORD *)v171 >= 0x30u )
                v166 = v171 + 36;
              else
                v166 = 0;
              if ( !v176 || *v176 < 0x30u )
                v60 = 0;
              v146 = gfTraceToSecondProvider
                  && ((unsigned int)THStateCheckForTraceOverride(v67, v66)
                   || (unsigned int)ThStateCheckIfTraceToSecondProvier(v67, v66, v70, v71)
                   && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 8));
              if ( (unsigned int)THStateCheckForTraceOverride(v67, v66)
                || (v36 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 8) == 0, v72 = 0, !v36) )
              {
                v72 = 1;
              }
              WPP_SF__guid__guid_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                83890257,
                2,
                8,
                v72,
                v146,
                35,
                (__int64)&WPP_9b5b8db6ac56383dc74d600fee488739_Traceguids,
                v60,
                v166);
            }
          }
        }
      }
    }
    if ( !LODWORD(v9.Pointer) )
    {
      v73 = a4;
      if ( (a4 & 1) != 0 || !*(_DWORD *)gfADAM && (!Str || !wcschr(Str, 0x40u)) )
        goto LABEL_315;
      v74 = UlBHCacheHash(a2);
      EnterCriticalSection(&csBHCache);
      BHCacheElement = FindBHCacheElement(v74, a2);
      v181 = BHCacheElement;
      if ( BHCacheElement )
      {
        if ( *(_QWORD *)(BHCacheElement + 432) )
        {
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
            || (unsigned int)THStateCheckForTraceOverride(v97, v96)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 8)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v97, v96)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v97, v96, v98, v99)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 8)) )
          {
            v102 = gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v97, v96)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier(v97, v96, v100, v101)
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 8));
            if ( (unsigned int)THStateCheckForTraceOverride(v97, v96)
              || (v103 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 8), v104 = 0, v103) )
            {
              v104 = 1;
            }
            v139 = DsaRpcInstanceDisplayName(*(_QWORD *)(v181 + 432), v104);
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              83890378,
              3,
              8,
              v105,
              v102,
              38,
              &WPP_9b5b8db6ac56383dc74d600fee488739_Traceguids,
              v139);
          }
        }
        else
        {
          if ( !(unsigned int)IncrementWPPPerfCountersForLevel(2)
            && !(unsigned int)THStateCheckForTraceOverride(v107, v106)
            && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 8)
            && (!gfTraceToSecondProvider
             || !(unsigned int)THStateCheckForTraceOverride(v107, v106)
             && (!(unsigned int)ThStateCheckIfTraceToSecondProvier(v107, v106, v108, v109)
              || !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 8))) )
          {
            goto LABEL_314;
          }
          v112 = gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v107, v106)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v107, v106, v110, v111)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 8));
          if ( (unsigned int)THStateCheckForTraceOverride(v107, v106)
            || (v36 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 8) == 0, v113 = 0, !v36) )
          {
            v113 = 1;
          }
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            83890383,
            2,
            8,
            v113,
            v112,
            39,
            &WPP_9b5b8db6ac56383dc74d600fee488739_Traceguids);
        }
      }
      else
      {
        v76 = (RPC_BINDING_HANDLE *)AllocBHCacheElement(v74, a2);
        v77 = v76;
        if ( v76 )
        {
          *v76 = DestinationBinding;
          DestinationBinding = 0;
          if ( RpcBindingCopy(*v76, &DestinationBinding) )
          {
            DestinationBinding = *v77;
            DeallocBHCacheElement(v74, v77);
            if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
              || (unsigned int)THStateCheckForTraceOverride(v79, v78)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 8)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v79, v78)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v79, v78, v80, v81)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 8)) )
            {
              v84 = gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v79, v78)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier(v79, v78, v82, v83)
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 8));
              if ( (unsigned int)THStateCheckForTraceOverride(v79, v78)
                || (v36 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 8) == 0, v85 = 0, !v36) )
              {
                v85 = 1;
              }
              WPP_SF__ATTRTYP_LOG_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                83890345,
                2,
                8,
                v85,
                v84,
                36,
                (__int64)&WPP_9b5b8db6ac56383dc74d600fee488739_Traceguids);
            }
          }
          else
          {
            CopyExtensions(v171, v77 + 1);
            CopyExtensions(v176, (char *)v77 + 460);
            v77[55] = Str;
            v77[56] = (RPC_BINDING_HANDLE)2;
            *(_DWORD *)(*(_QWORD *)v172 + 16LL) |= 2u;
            if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
              || (unsigned int)THStateCheckForTraceOverride(v87, v86)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 8)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v87, v86)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v87, v86, v88, v89)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 8)) )
            {
              v92 = gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v87, v86)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier(v87, v86, v90, v91)
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 8));
              if ( (unsigned int)THStateCheckForTraceOverride(v87, v86)
                || (v93 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 8), v94 = 0, v93) )
              {
                v94 = 1;
              }
              v138 = DsaRpcInstanceDisplayName(v77[54], v94);
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                83890365,
                4,
                8,
                v95,
                v92,
                37,
                &WPP_9b5b8db6ac56383dc74d600fee488739_Traceguids,
                v138);
            }
          }
        }
      }
      v73 = a4;
LABEL_314:
      LeaveCriticalSection(&csBHCache);
LABEL_315:
      v114 = v172;
      *(_QWORD *)(*(_QWORD *)v172 + 8LL) = DestinationBinding;
      *(_DWORD *)(*(_QWORD *)v114 + 440LL) = v73;
      CopyExtensions(v171, *(_QWORD *)v114 + 20LL);
      v115 = 1;
      v142 = 1;
      v50 = a7;
      *a7 = 0;
      goto LABEL_345;
    }
LABEL_316:
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v49, v116)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 8)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v49, v116)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v49, v116, v117, v118)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 8)) )
    {
      if ( v171 && *(_DWORD *)v171 >= 0x30u )
        v166 = v171 + 36;
      else
        v166 = 0;
      if ( v176 && *v176 >= 0x30u )
      {
        v49 = (wchar_t *)(v176 + 9);
        Simple = v176 + 9;
      }
      else
      {
        Simple = 0;
      }
      v121 = gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v49, v116)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v49, v116, v119, v120)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 8));
      if ( (unsigned int)THStateCheckForTraceOverride(v49, v116)
        || (v36 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 8) == 0, v122 = 0, !v36) )
      {
        v122 = 1;
      }
      WPP_SF__guid__guid_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        83890413,
        2,
        8,
        v122,
        v121,
        40,
        (__int64)&WPP_9b5b8db6ac56383dc74d600fee488739_Traceguids,
        (__int64)Simple,
        v166);
    }
    *a7 = (unsigned int)v9.Pointer;
    v11 = DestinationBinding;
    if ( !DestinationBinding )
    {
      v50 = a7;
      goto LABEL_344;
    }
    DRSInsertFreeHandleQueue(a2);
    DestinationBinding = 0;
    goto LABEL_150;
  }
  v50 = a7;
  *a7 = v147;
  if ( dsaInitPhase == 1 )
  {
    if ( v147 == 1818 )
    {
      BindingTimeoutMins = getBindingTimeoutMins(v172);
      v49 = (wchar_t *)(unsigned int)eServiceShutdown;
      if ( !eServiceShutdown )
      {
        if ( a2[4] )
          v53 = (char *)a2 + a2[4];
        else
          v53 = 0;
        v54 = gpDsEventConfig;
        if ( !gpDsEventConfig )
          goto LABEL_168;
        if ( (gpDsEventConfig[11].Internal & 0x8000000000000000uLL) != 0LL
          && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(1280, 0)) )
        {
          if ( !(unsigned int)DoLogMsgOverride(2147484880LL) )
          {
LABEL_168:
            draUpdateTimeoutReplica(v53);
            goto LABEL_150;
          }
          v54 = gpDsEventConfig;
        }
        memset_0(&v149, 0, 0x60u);
        Internal = v54[11].Internal;
        LODWORD(v152) = 0;
        v150 = -2147482416;
        v153 = 0;
        v154 = 1;
        v163 = v200;
        v200[0] = 4;
        *(_QWORD *)&v200[8 * v149 + 6] = GetCurrentThreadId();
        *(_QWORD *)&v163[8 * v149 + 2] = &v163[8 * v149 + 6];
        ++v149;
        v163[8 * v149] = 1;
        v55 = a2[3];
        if ( (-(__int64)(a2[3] != 0) & ((unsigned __int64)v174 + v55)) != 0 )
        {
          v56 = ((unsigned __int64)v174 + v55) & -(__int64)((_DWORD)v55 != 0);
        }
        else if ( *v175 )
        {
          v56 = (__int64)a2 + (unsigned int)*v175;
        }
        else
        {
          v56 = 0;
        }
        *(_QWORD *)&v163[8 * v149++ + 2] = v56;
        v163[8 * v149] = 5;
        *(_QWORD *)&v163[8 * v149 + 6] = BindingTimeoutMins;
        *(_QWORD *)&v163[8 * v149 + 2] = &v163[8 * v149 + 6];
        ++v149;
        v163[8 * v149] = 4;
        *(_QWORD *)&v163[8 * v149 + 6] = 83890215;
        *(_QWORD *)&v163[8 * v149 + 2] = &v163[8 * v149 + 6];
        ++v149;
        v157 = 0;
        v156 = 1280;
        v155 = 1;
        v159 = 0;
        v160 = 0;
        DoLogEventAndTrace(&v149);
        goto LABEL_168;
      }
      v57 = gpDsEventConfig;
      if ( !gpDsEventConfig )
        goto LABEL_150;
      if ( SHIDWORD(gpDsEventConfig[11].Internal) < 1
        && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(1280, 1)) )
      {
        if ( !(unsigned int)DoLogMsgOverride(2147485641LL) )
          goto LABEL_150;
        v57 = gpDsEventConfig;
      }
      memset_0(&v149, 0, 0x60u);
      Internal = v57[11].Internal;
      LODWORD(v152) = 1;
      v150 = -2147481655;
      v153 = 0;
      v154 = 1;
      v163 = v200;
      v200[0] = 4;
      *(_QWORD *)&v200[8 * v149 + 6] = GetCurrentThreadId();
      *(_QWORD *)&v163[8 * v149 + 2] = &v163[8 * v149 + 6];
      ++v149;
      v163[8 * v149] = 1;
      if ( a2 )
      {
        v58 = a2[3];
        if ( (-(__int64)(a2[3] != 0) & ((unsigned __int64)v174 + v58)) != 0 )
        {
          v15 = (const wchar_t *)(((unsigned __int64)v174 + v58) & -(__int64)((_DWORD)v58 != 0));
        }
        else if ( *v175 )
        {
          v15 = (const wchar_t *)((char *)a2 + (unsigned int)*v175);
        }
        else
        {
          v15 = 0;
        }
      }
      *(_QWORD *)&v163[8 * v149++ + 2] = v15;
      v163[8 * v149] = 4;
      *(_QWORD *)&v163[8 * v149 + 6] = 83890227;
      *(_QWORD *)&v163[8 * v149 + 2] = &v163[8 * v149 + 6];
      ++v149;
      v157 = 0;
      v156 = 1280;
      v155 = 1;
      v159 = 0;
      v160 = 0;
      v52 = &v149;
      goto LABEL_149;
    }
    if ( !gpDsEventConfig )
      goto LABEL_344;
    if ( SHIDWORD(gpDsEventConfig[11].Internal) >= 3
      || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(1280, 3)
      || (unsigned int)DoLogMsgOverride(1073742948) )
    {
      v186 = 3;
      v192 = 0;
      v195 = 0;
      v196 = 0;
      Offset = gpDsEventConfig[11].Internal;
      v184 = 1073742948;
      v187 = 0;
      v188 = 1;
      v197 = v200;
      v200[0] = 1;
      if ( a2 )
      {
        v59 = a2[3];
        if ( (-(__int64)(a2[3] != 0) & ((unsigned __int64)v174 + v59)) != 0 )
        {
          v15 = (const wchar_t *)(((unsigned __int64)v174 + v59) & -(__int64)((_DWORD)v59 != 0));
        }
        else if ( *v175 )
        {
          v15 = (const wchar_t *)((char *)a2 + (unsigned int)*v175);
        }
        else
        {
          v15 = 0;
        }
      }
LABEL_148:
      v204 = v147;
      v207 = v147;
      v206 = &v207;
      v205 = 10;
      v203 = (wchar_t *)&v204;
      v202 = 5;
      v201 = v15;
      v183 = 3;
      v191 = 0;
      v190 = 1280;
      v189 = 1;
      v193 = 0;
      v194 = 0;
      v52 = &v183;
LABEL_149:
      DoLogEventAndTrace(v52);
    }
LABEL_150:
    v50 = a7;
    goto LABEL_344;
  }
  if ( gpDsEventConfig
    && ((gpDsEventConfig[8].OffsetHigh & 0x80000000) == 0
     || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(1280, 0)
     || (unsigned int)DoLogMsgOverride(3221226597LL)) )
  {
    v186 = 0;
    v192 = 0;
    v195 = 0;
    v196 = 0;
    Offset = gpDsEventConfig[8].Offset;
    v184 = -1073740699;
    v187 = 0;
    v188 = 1;
    v197 = v200;
    v200[0] = 1;
    if ( a2 )
    {
      v51 = a2[3];
      if ( (-(__int64)(a2[3] != 0) & ((unsigned __int64)v174 + v51)) != 0 )
      {
        v15 = (const wchar_t *)(((unsigned __int64)v174 + v51) & -(__int64)((_DWORD)v51 != 0));
      }
      else if ( *v175 )
      {
        v15 = (const wchar_t *)((char *)a2 + (unsigned int)*v175);
      }
      else
      {
        v15 = 0;
      }
    }
    goto LABEL_148;
  }
LABEL_344:
  v115 = 0;
LABEL_345:
  if ( (*(_BYTE *)(*(_QWORD *)v172 + 16LL) & 2) == 0 )
  {
    v49 = Str;
    if ( Str )
    {
      DSFreeAux(Str, 83890429);
      Str = 0;
    }
  }
  if ( hBinding )
    RpcBindingFree(&hBinding);
  if ( (unsigned int)THStateCheckForTraceOverride(v49, v11)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 8)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v124, v123)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v124, v123, v125, v126)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 8)) )
  {
    v127 = *v50;
    v130 = gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v124, v123)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v124, v123, v128, v129)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 8));
    if ( (unsigned int)THStateCheckForTraceOverride(v124, v123)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 8) )
    {
      v10 = 1;
    }
    v131 = DsaRpcInstanceDisplayName(a2, v177 + 6072);
    v140 = v127;
    v115 = v142;
    WPP_SF_Sddd_guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      v130,
      (int)v136,
      (int)p_DestinationBinding,
      v131,
      v133,
      v142,
      v140,
      v132);
  }
  return v115;
}

```

## disassembly

```asm
0x18030fce4  mov     r11, rsp
0x18030fce7  push    rbx
0x18030fce8  push    rsi
0x18030fce9  push    rdi
0x18030fcea  push    r12
0x18030fcec  push    r13
0x18030fcee  push    r14
0x18030fcf0  push    r15
0x18030fcf2  sub     rsp, 440h
0x18030fcf9  mov     rax, cs:__security_cookie
0x18030fd00  xor     rax, rsp
0x18030fd03  mov     [rsp+478h+var_48], rax
0x18030fd0b  mov     r15d, r9d
0x18030fd0e  mov     [rsp+478h+var_404], r9d
0x18030fd13  mov     rax, r8
0x18030fd16  mov     [rsp+478h+var_368], rax
0x18030fd1e  mov     r13, rdx
0x18030fd21  mov     [rsp+478h+var_318], rcx
0x18030fd29  mov     [rsp+478h+var_278], rcx
0x18030fd31  mov     [rsp+478h+var_280], rdx
0x18030fd39  mov     [rsp+478h+var_330], rdx
0x18030fd41  mov     [rsp+478h+var_2F8], rax
0x18030fd49  mov     [rsp+478h+var_3E0], r9d
0x18030fd51  mov     rax, [rsp+478h+arg_28]
0x18030fd59  mov     [rsp+478h+var_340], rax
0x18030fd61  mov     rax, [rsp+478h+arg_30]
0x18030fd69  mov     [rsp+478h+var_3F8], rax
0x18030fd71  mov     ebx, 57h ; 'W'
0x18030fd76  mov     [rsp+478h+var_3F0], ebx
0x18030fd7d  mov     r14d, 20EEh
0x18030fd83  mov     [rsp+478h+var_3E8], r14
0x18030fd8b  xor     edi, edi
0x18030fd8d  mov     [r11-370h], rdi
0x18030fd94  mov     [r11-360h], rdi
0x18030fd9b  mov     [r11-348h], rdi
0x18030fda2  mov     [r11-378h], rdi
0x18030fda9  mov     [rsp+478h+var_300], edi
0x18030fdb0  mov     [rsp+478h+var_358], edi
0x18030fdb7  mov     [rsp+478h+var_354], edi
0x18030fdbe  mov     rax, cs:qword_18052B3B8
0x18030fdc5  mov     [rsp+478h+var_320], rax
0x18030fdcd  mov     [r11-338h], rdi
0x18030fdd4  mov     rcx, rdx
0x18030fdd7  call    IsValidDSInstance
0x18030fddc  lea     esi, [rbx-56h]
0x18030fddf  test    eax, eax
0x18030fde1  jnz     short loc_18030FE0F
0x18030fde3  mov     r9d, esi
0x18030fde6  mov     r8d, r14d
0x18030fde9  lea     rdx, word_18049B11A
0x18030fdf0  mov     ecx, 5000EFEh
0x18030fdf5  call    DoLogUnhandledError2
0x18030fdfa  mov     r9d, esi
0x18030fdfd  mov     r8d, 5000EFFh
0x18030fe03  mov     edx, r14d
0x18030fe06  lea     ecx, [r14+6]
0x18030fe0a  call    DraExcept
0x18030fe0f  test    r15b, 10h
0x18030fe13  jz      short loc_18030FE1E
0x18030fe15  lea     rax, g_guidNtdsapi
0x18030fe1c  jmp     short loc_18030FE38
0x18030fe1e  mov     rax, cs:qword_18052B2A8
0x18030fe25  test    rax, rax
0x18030fe28  jnz     short loc_18030FE34
0x18030fe2a  mov     [rsp+478h+var_2F0], rdi
0x18030fe32  jmp     short loc_18030FE40
0x18030fe34  add     rax, 8
0x18030fe38  mov     [rsp+478h+var_2F0], rax
0x18030fe40  cmp     cs:gfADAM, edi
0x18030fe46  jz      short loc_18030FE63
0x18030fe48  call    GetReplAuthenticationMode
0x18030fe4d  mov     r12d, 2
0x18030fe53  sub     eax, r12d
0x18030fe56  neg     eax
0x18030fe58  sbb     eax, eax
0x18030fe5a  and     eax, r12d
0x18030fe5d  mov     dword ptr [rsp+478h+var_408], eax
0x18030fe61  jmp     short loc_18030FE6D
0x18030fe63  mov     dword ptr [rsp+478h+var_408], edi
0x18030fe67  mov     r12d, 2
0x18030fe6d  lea     rax, [r13+4]
0x18030fe71  mov     [rsp+478h+var_328], rax
0x18030fe79  cmp     [rax], edi
0x18030fe7b  jz      short loc_18030FE84
0x18030fe7d  mov     eax, [rax]
0x18030fe7f  add     rax, r13
0x18030fe82  jmp     short loc_18030FE87
0x18030fe84  mov     rax, rdi
0x18030fe87  mov     [rsp+478h+var_308], rax
0x18030fe8f  mov     [rsp+478h+var_310], rax
0x18030fe97  mov     ecx, 5Ch ; '\'
0x18030fe9c  cmp     cx, [rax]
0x18030fe9f  jnz     short loc_18030FEB9
0x18030fea1  add     rax, r12
0x18030fea4  mov     [rsp+478h+var_308], rax
0x18030feac  cmp     cx, [rax]
0x18030feaf  jz      short loc_18030FEA1
0x18030feb1  mov     [rsp+478h+var_310], rax
0x18030feb9  mov     r14d, 8
0x18030febf  lea     r15, asc_18049FBBC; "[]"
0x18030fec6  call    THStateCheckForTraceOverride
0x18030fecb  test    eax, eax
0x18030fecd  jnz     short loc_18030FF1B
0x18030fecf  mov     r8d, r14d
0x18030fed2  lea     edx, [rax+4]
0x18030fed5  xor     ecx, ecx
0x18030fed7  call    CheckWPPLevelFlagsEnabledForProvider
0x18030fedc  test    eax, eax
0x18030fede  jnz     short loc_18030FF1B
0x18030fee0  mov     eax, cs:gfTraceToSecondProvider
0x18030fee6  test    eax, eax
0x18030fee8  jz      loc_18030FFBC
0x18030feee  call    THStateCheckForTraceOverride
0x18030fef3  test    eax, eax
0x18030fef5  jnz     short loc_18030FF1B
0x18030fef7  call    ThStateCheckIfTraceToSecondProvier
0x18030fefc  test    eax, eax
0x18030fefe  jz      loc_18030FFBC
0x18030ff04  mov     r8d, r14d
0x18030ff07  mov     edx, 4
0x18030ff0c  mov     ecx, esi
0x18030ff0e  call    CheckWPPLevelFlagsEnabledForProvider
0x18030ff13  test    eax, eax
0x18030ff15  jz      loc_18030FFBC
0x18030ff1b  mov     eax, cs:gfTraceToSecondProvider
0x18030ff21  test    eax, eax
0x18030ff23  jz      short loc_18030FF50
0x18030ff25  call    THStateCheckForTraceOverride
0x18030ff2a  test    eax, eax
0x18030ff2c  jnz     short loc_18030FF4A
0x18030ff2e  call    ThStateCheckIfTraceToSecondProvier
0x18030ff33  test    eax, eax
0x18030ff35  jz      short loc_18030FF50
0x18030ff37  mov     r8d, r14d
0x18030ff3a  mov     edx, 4
0x18030ff3f  mov     ecx, esi
0x18030ff41  call    CheckWPPLevelFlagsEnabledForProvider
0x18030ff46  test    eax, eax
0x18030ff48  jz      short loc_18030FF50
0x18030ff4a  mov     [rsp+478h+var_400], esi
0x18030ff4e  jmp     short loc_18030FF54
0x18030ff50  mov     [rsp+478h+var_400], edi
0x18030ff54  call    THStateCheckForTraceOverride
0x18030ff59  test    eax, eax
0x18030ff5b  jnz     short loc_18030FF70
0x18030ff5d  mov     r8d, r14d
0x18030ff60  lea     edx, [rax+4]
0x18030ff63  xor     ecx, ecx
0x18030ff65  call    CheckWPPLevelFlagsEnabledForProvider
0x18030ff6a  test    eax, eax
0x18030ff6c  mov     edx, edi
0x18030ff6e  jz      short loc_18030FF72
0x18030ff70  mov     edx, esi
0x18030ff72  mov     rcx, r13
0x18030ff75  call    DsaRpcInstanceDisplayName
0x18030ff7a  mov     [rsp+478h+var_438], rax; __int64
0x18030ff7f  lea     rax, WPP_9b5b8db6ac56383dc74d600fee488739_Traceguids
0x18030ff86  mov     [rsp+478h+var_440], rax; LPCGUID
0x18030ff8b  mov     [rsp+478h+var_448], 21h ; '!'; __int16
0x18030ff92  mov     eax, [rsp+478h+var_400]
0x18030ff96  mov     [rsp+478h+var_450], eax; int
0x18030ff9a  mov     [rsp+478h+var_458], edx; int
0x18030ff9e  mov     r9d, r14d; int
0x18030ffa1  mov     edx, 5000F27h; int
0x18030ffa6  mov     r8d, 4; int
0x18030ffac  mov     rcx, cs:WPP_GLOBAL_Control
0x18030ffb3  mov     rcx, [rcx+10h]; int
0x18030ffb7  call    WPP_SF_S
0x18030ffbc  cmp     cs:gfIsDrsClientLibInitialized, edi
0x18030ffc2  jz      loc_180311A99
0x18030ffc8  mov     eax, cs:eServiceShutdown
0x18030ffce  test    eax, eax
0x18030ffd0  jnz     loc_180311A99
0x18030ffd6  cmp     cs:gfADAM, edi
0x18030ffdc  jz      short loc_18030FFF0
0x18030ffde  mov     rcx, [rsp+478h+var_310]
0x18030ffe6  mov     [rsp+478h+var_350], rcx
0x18030ffee  jmp     short loc_180310064
0x18030fff0  cmp     [rsp+478h+var_338], rdi
0x18030fff8  jnz     short loc_180310051
0x18030fffa  lea     r8, [rsp+478h+var_338]
0x180310002  mov     rdx, [rsp+478h+var_310]
0x18031000a  mov     rcx, [rsp+478h+var_318]
0x180310012  call    resolveDnsAddressWithFallback
0x180310017  mov     ecx, eax
0x180310019  mov     [rsp+478h+var_3E8], rcx
0x180310021  mov     [rsp+478h+var_3FC], eax
0x180310025  test    eax, eax
0x180310027  jnz     short loc_18031003B
0x180310029  mov     rcx, [rsp+478h+var_338]
0x180310031  test    rcx, rcx
0x180310034  jz      short loc_18031003B
0x180310036  cmp     [rcx], rdi
0x180310039  jnz     short loc_180310051
0x18031003b  mov     ecx, 214Ch
0x180310040  mov     [rsp+478h+var_3E8], rcx
0x180310048  mov     [rsp+478h+var_3FC], ecx
0x18031004c  jmp     loc_180310432
0x180310051  mov     rax, [rsp+478h+var_338]
0x180310059  mov     rax, [rax]
0x18031005c  mov     [rsp+478h+var_350], rax
0x180310064  mov     eax, [rsp+478h+var_404]
0x180310068  and     eax, r14d
0x18031006b  mov     [rsp+478h+var_400], eax
0x18031006f  jz      short loc_180310092
0x180310071  call    ImpersonateAnyClient
0x180310076  mov     ebx, eax
0x180310078  mov     [rsp+478h+var_3F0], eax
0x18031007f  test    eax, eax
0x180310081  jnz     loc_180310432
0x180310087  mov     [rsp+478h+var_354], esi
0x18031008e  mov     eax, [rsp+478h+var_400]
0x180310092  lea     rcx, [rsp+478h+var_358]
0x18031009a  mov     qword ptr [rsp+478h+var_420], rcx
0x18031009f  lea     rcx, [rsp+478h+Str]
0x1803100a7  mov     qword ptr [rsp+478h+var_428], rcx
0x1803100ac  lea     rcx, [rsp+478h+hBinding]
0x1803100b4  mov     qword ptr [rsp+478h+var_430], rcx
0x1803100b9  mov     dword ptr [rsp+478h+var_438], eax
0x1803100bd  mov     eax, cs:gfUseUniqueAssoc
0x1803100c3  mov     dword ptr [rsp+478h+var_440], eax
0x1803100c7  mov     eax, dword ptr [rsp+478h+var_408]
0x1803100cb  mov     dword ptr [rsp+478h+var_448], eax
0x1803100cf  mov     eax, [rsp+478h+arg_20]
0x1803100d6  mov     [rsp+478h+var_450], eax
0x1803100da  mov     rax, [rsp+478h+var_368]
0x1803100e2  mov     qword ptr [rsp+478h+var_458], rax
0x1803100e7  mov     r9, [rsp+478h+var_350]
0x1803100ef  mov     r8, [rsp+478h+var_310]
0x1803100f7  mov     rdx, r13
0x1803100fa  mov     rcx, [rsp+478h+var_318]
0x180310102  call    DRSGetRpcBinding
0x180310107  mov     ecx, eax
0x180310109  mov     [rsp+478h+var_3E8], rcx
0x180310111  mov     [rsp+478h+var_3FC], eax
0x180310115  test    eax, eax
0x180310117  jnz     loc_180310432
0x18031011d  mov     eax, cs:dword_180528620
0x180310123  mov     [rsp+478h+var_400], eax
0x180310127  imul    r8d, eax, 0EA60h; optionValue
0x18031012e  lea     edx, [rcx+0Ch]; option
0x180310131  mov     rcx, [rsp+478h+hBinding]; hBinding
0x180310139  call    cs:__imp_RpcBindingSetOption
0x18031013f  mov     ebx, eax
0x180310141  mov     [rsp+478h+var_3E8], rbx
0x180310149  mov     [rsp+478h+var_3FC], eax
0x18031014d  test    eax, eax
0x18031014f  jz      short loc_18031017B
0x180310151  mov     r9d, 5000F70h
0x180310157  mov     r8, r13
0x18031015a  mov     edx, eax
0x18031015c  mov     rcx, [rsp+478h+var_318]
0x180310164  call    LogRpcExtendedErrorInfo
0x180310169  mov     r9d, esi
0x18031016c  xor     edx, edx
0x18031016e  mov     r8d, 5000F71h
0x180310174  mov     ecx, ebx
0x180310176  call    DraExcept
0x18031017b  mov     rcx, [rsp+478h+var_340]
0x180310183  mov     rax, [rcx]
0x180310186  mov     [rax+1DCh], r12d
0x18031018d  mov     rax, [rcx]
0x180310190  mov     ecx, [rsp+478h+var_400]
0x180310194  mov     [rax+1CCh], ecx
0x18031019a  mov     eax, [rsp+478h+var_404]
0x18031019e  mov     ebx, 4
0x1803101a3  and     eax, ebx
0x1803101a5  mov     [rsp+478h+var_400], eax
0x1803101a9  jz      short loc_1803101C3
0x1803101ab  mov     r8, [rsp+478h+hBinding]
0x1803101b3  xor     edx, edx
0x1803101b5  mov     rcx, [rsp+478h+var_318]
0x1803101bd  call    InitRpcSessionEncryption
0x1803101c2  nop
0x1803101c3  mov     ecx, ebx
0x1803101c5  call    IncrementWPPPerfCountersForLevel
0x1803101ca  test    eax, eax
0x1803101cc  jnz     short loc_18031021F
0x1803101ce  call    THStateCheckForTraceOverride
0x1803101d3  test    eax, eax
0x1803101d5  jnz     short loc_18031021F
0x1803101d7  mov     r8d, r14d
0x1803101da  mov     edx, ebx
0x1803101dc  xor     ecx, ecx
0x1803101de  call    CheckWPPLevelFlagsEnabledForProvider
0x1803101e3  test    eax, eax
0x1803101e5  jnz     short loc_18031021F
0x1803101e7  mov     eax, cs:gfTraceToSecondProvider
0x1803101ed  test    eax, eax
0x1803101ef  jz      loc_1803102AB
0x1803101f5  call    THStateCheckForTraceOverride
0x1803101fa  test    eax, eax
0x1803101fc  jnz     short loc_18031021F
0x1803101fe  call    ThStateCheckIfTraceToSecondProvier
0x180310203  test    eax, eax
0x180310205  jz      loc_1803102AB
0x18031020b  mov     r8d, r14d
0x18031020e  mov     edx, ebx
0x180310210  mov     ecx, esi
0x180310212  call    CheckWPPLevelFlagsEnabledForProvider
  ... truncated ...
```
