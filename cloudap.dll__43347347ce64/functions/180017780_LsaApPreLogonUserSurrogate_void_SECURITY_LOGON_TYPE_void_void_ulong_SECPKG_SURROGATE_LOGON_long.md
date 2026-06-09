# LsaApPreLogonUserSurrogate(void * *,_SECURITY_LOGON_TYPE,void *,void *,ulong,_SECPKG_SURROGATE_LOGON *,long *)

- ea: `0x180017780`
- end: `0x180018a10`
- name: `?LsaApPreLogonUserSurrogate@@YAJPEAPEAXW4_SECURITY_LOGON_TYPE@@PEAX2KPEAU_SECPKG_SURROGATE_LOGON@@PEAJ@Z`
- size: `4752`
- prototype: `int(void **, enum _SECURITY_LOGON_TYPE, void *, void *, unsigned int, struct _SECPKG_SURROGATE_LOGON *, int *)`
- caller_count: `0`
- callee_count: `33`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180004460`
- `0x180007ef0`
- `0x180007fc0`
- `0x18000a600`
- `0x18000ce50`
- `0x18000e7e0`
- `0x18000fb70`
- `0x18000fd50`
- `0x180017780`
- `0x180018a20`
- `0x18001cd80`
- `0x180022f80`
- `0x180023700`
- `0x180029650`
- `0x18002b260`
- `0x18002f080`
- `0x180032884`
- `0x180032998`
- `0x180034e20`
- `0x180039090`
- `0x18003de28`
- `0x18003df0c`
- `0x18003f5ec`
- `0x180042410`
- `0x18004d514`
- `0x180051464`
- `0x180051fe4`
- `0x180054e30`
- `0x180058990`
- `0x180058a7c`
- `0x18005fc44`
- `0x18007f9f0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017ed7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800186e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017ed7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800186e6`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001860e`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001860e`
- `ntdll!RtlReleaseResource` at `0x180018662`
- `ntdll!RtlReleaseResource` at `0x18001867c`
- `ntdll!RtlReleaseResource` at `0x180018662`
- `ntdll!RtlReleaseResource` at `0x18001867c`
- `LSASRV!LsapDbLookupGetDomainInfo` at `0x1800179b5`
- `LSASRV!LsapDbLookupGetDomainInfo` at `0x1800179b5`

## string_xrefs

- `0x18001797b`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180017a2a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180017a8d`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180017b2d`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180017b85`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180017c44`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180017ca5`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180017ce0`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180017d3a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001854f`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800185a7`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180018902`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800179d0`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001811b`: `PublicCacheData`
- `0x180017f84`: `CreateOrAcquireUserCacheEntry`
- `0x180018329`: `SaveCaches`
- `0x180017ebe`: `GetUnlockBufferForDPAPICache`
- `0x1800182aa`: `EnableCacheNodeFlags`
- `0x180018158`: `GetLogonPublicCacheForUser`
- `0x180017cc0`: `CloudTrust NGC not supported during cached logon.`
- `0x180017e08`: `The plugin doesn't have surrogate logon capability`
- `0x180018206`: `GetFidoDecryptedPrimaryApCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LsaApPreLogonUserSurrogate(
        void **a1,
        enum _SECURITY_LOGON_TYPE a2,
        struct _KERB_CERTIFICATE_LOGON *a3,
        void *a4,
        unsigned int a5,
        struct _SECPKG_SURROGATE_LOGON *a6,
        int *a7)
{
  struct _SECPKG_SURROGATE_LOGON *v9; // rdi
  struct _ApPluginPkg *v10; // r15
  const char *v11; // r13
  unsigned int DomainInfo; // r12d
  const char *v13; // r9
  __int64 v14; // r8
  const char *v15; // r9
  const char *v16; // rcx
  bool v17; // zf
  const char *v18; // rax
  bool v19; // al
  const char *v20; // r9
  const char *v21; // rcx
  bool v22; // zf
  bool v23; // al
  const char *v24; // r9
  const char *v25; // rax
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v26; // rsi
  const char *v27; // r9
  const char *v28; // r9
  const char *v29; // rax
  unsigned __int16 *v30; // r15
  const char *v31; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  struct _ApPluginPkg *v35; // r14
  const char *v36; // rax
  const char *v37; // r9
  const char *v38; // r9
  DWORD CurrentThreadId; // eax
  __int64 v40; // r8
  unsigned int v41; // r9d
  BOOL v42; // esi
  const char *v43; // r9
  int v44; // eax
  const char *v45; // rax
  __int64 v46; // r8
  const char *v47; // r9
  const char *v48; // rax
  const char *v49; // r9
  const char *v50; // rax
  __int64 v51; // r8
  unsigned int v52; // r9d
  const char *v53; // rax
  __int64 v54; // r8
  const char *v55; // r9
  __int64 v56; // rax
  __int64 v57; // r15
  const char *v58; // r9
  __int64 v59; // rsi
  const char *v60; // r9
  __int64 v61; // r14
  const char *v62; // r9
  __int64 v63; // rdx
  __int64 v64; // rax
  __int64 v65; // rcx
  __int64 v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rax
  const char *v70; // r9
  const char *v71; // rcx
  bool v72; // zf
  struct _USER_CACHE_ENTRY *v73; // rbx
  __int64 v74; // rcx
  struct _USER_CACHE_ENTRY **v75; // rax
  int v76; // eax
  BOOL v77; // r12d
  BOOL v78; // ebx
  BOOL v79; // edi
  BOOL v80; // esi
  BOOL v81; // r14d
  BOOL v82; // r15d
  DWORD v83; // eax
  unsigned __int16 *v84; // rbx
  _BYTE *v85; // rcx
  __int64 v86; // rax
  __int64 v87; // rsi
  __int64 i; // rbx
  unsigned __int8 *v89; // rcx
  __int64 v90; // rax
  const char *v91; // r9
  bool v92; // zf
  const char *v93; // rdx
  bool v94; // zf
  struct _USER_CACHE_ENTRY **v96; // [rsp+20h] [rbp-110h]
  struct _USER_CACHE_ENTRY **v97; // [rsp+20h] [rbp-110h]
  int v98; // [rsp+20h] [rbp-110h]
  struct _USER_CACHE_ENTRY **v99; // [rsp+20h] [rbp-110h]
  struct _USER_CACHE_ENTRY **v100; // [rsp+20h] [rbp-110h]
  struct _USER_CACHE_ENTRY **v101; // [rsp+20h] [rbp-110h]
  struct _USER_CACHE_ENTRY **v102; // [rsp+20h] [rbp-110h]
  const char *SourceSid; // [rsp+28h] [rbp-108h]
  int v104; // [rsp+48h] [rbp-E8h]
  int v105; // [rsp+60h] [rbp-D0h]
  int v106; // [rsp+B0h] [rbp-80h]
  bool v107; // [rsp+B4h] [rbp-7Ch] BYREF
  bool v108; // [rsp+B5h] [rbp-7Bh] BYREF
  bool v109; // [rsp+B6h] [rbp-7Ah] BYREF
  bool v110; // [rsp+B7h] [rbp-79h] BYREF
  bool v111; // [rsp+B8h] [rbp-78h] BYREF
  char v112; // [rsp+B9h] [rbp-77h]
  bool v113; // [rsp+BAh] [rbp-76h] BYREF
  unsigned __int16 *v114; // [rsp+C0h] [rbp-70h] BYREF
  int v115; // [rsp+C8h] [rbp-68h]
  struct _USER_CACHE_ENTRY *v116; // [rsp+D0h] [rbp-60h] BYREF
  struct _ApPluginPkg *v117; // [rsp+D8h] [rbp-58h] BYREF
  enum _SECURITY_LOGON_TYPE v118; // [rsp+E0h] [rbp-50h]
  unsigned __int16 *v119; // [rsp+E8h] [rbp-48h]
  unsigned __int8 *v120; // [rsp+F0h] [rbp-40h] BYREF
  unsigned int v121; // [rsp+F8h] [rbp-38h] BYREF
  unsigned int v122[4]; // [rsp+100h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+110h] [rbp-20h] BYREF
  struct _APPLUGIN_USER_INFO *v124; // [rsp+118h] [rbp-18h] BYREF
  unsigned __int16 *v125; // [rsp+120h] [rbp-10h] BYREF
  struct _SCARD_PIN *v126; // [rsp+128h] [rbp-8h] BYREF
  __int64 v127; // [rsp+130h] [rbp+0h]
  __int64 v128; // [rsp+138h] [rbp+8h]
  HLOCAL v129; // [rsp+140h] [rbp+10h] BYREF
  __int128 v130; // [rsp+148h] [rbp+18h] BYREF
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v131; // [rsp+158h] [rbp+28h]
  __int128 v132; // [rsp+160h] [rbp+30h] BYREF
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v133; // [rsp+170h] [rbp+40h]
  __int128 v134; // [rsp+180h] [rbp+50h] BYREF
  int *v135; // [rsp+190h] [rbp+60h]
  struct _SECPKG_SURROGATE_LOGON *v136; // [rsp+198h] [rbp+68h]
  __int128 v137; // [rsp+1A0h] [rbp+70h] BYREF
  __int64 v138; // [rsp+1B0h] [rbp+80h]
  void **v139; // [rsp+1C0h] [rbp+90h] BYREF
  int v140; // [rsp+1C8h] [rbp+98h] BYREF
  char v141; // [rsp+1CCh] [rbp+9Ch]
  int v142; // [rsp+1F0h] [rbp+C0h] BYREF
  const char *v143; // [rsp+1F8h] [rbp+C8h]
  __int64 v144; // [rsp+200h] [rbp+D0h]
  char v145; // [rsp+208h] [rbp+D8h]
  int v146; // [rsp+210h] [rbp+E0h]
  __int128 v147; // [rsp+218h] [rbp+E8h]
  __int128 v148; // [rsp+228h] [rbp+F8h]
  __int128 v149; // [rsp+238h] [rbp+108h]
  __int128 v150; // [rsp+248h] [rbp+118h]
  __int128 v151; // [rsp+258h] [rbp+128h]
  __int128 v152; // [rsp+268h] [rbp+138h]
  __int128 v153; // [rsp+278h] [rbp+148h]
  __int128 v154; // [rsp+288h] [rbp+158h]
  __int128 v155; // [rsp+298h] [rbp+168h]
  __int64 v156; // [rsp+2A8h] [rbp+178h]
  __int128 v157; // [rsp+2B0h] [rbp+180h]
  int v158; // [rsp+2C0h] [rbp+190h]
  __int64 v159; // [rsp+2C8h] [rbp+198h]
  int *v160; // [rsp+2D0h] [rbp+1A0h]
  __int64 v161; // [rsp+2D8h] [rbp+1A8h]
  __int64 v162; // [rsp+2E0h] [rbp+1B0h]
  void ***v163; // [rsp+2E8h] [rbp+1B8h]
  __int64 v164; // [rsp+2F0h] [rbp+1C0h]
  int v165; // [rsp+2F8h] [rbp+1C8h]
  int *v166; // [rsp+300h] [rbp+1D0h]
  char v167; // [rsp+308h] [rbp+1D8h]
  _QWORD v168[42]; // [rsp+310h] [rbp+1E0h] BYREF

  v118 = a2;
  v9 = a6;
  v136 = a6;
  v135 = a7;
  v115 = 0;
  v107 = 0;
  v111 = 0;
  v110 = 0;
  v109 = 0;
  v113 = 0;
  v112 = 0;
  v108 = 0;
  v132 = 0;
  v133 = 0;
  v130 = 0;
  v131 = 0;
  *(_OWORD *)v122 = 0;
  v137 = 0;
  v138 = 0;
  v119 = 0;
  v114 = 0;
  v10 = 0;
  v117 = 0;
  v116 = 0;
  v124 = 0;
  hMem = 0;
  v125 = 0;
  v126 = 0;
  v127 = 0;
  v128 = 0;
  v129 = 0;
  v120 = 0;
  v121 = 0;
  v140 = 0;
  v141 = 0;
  v145 = 0;
  v142 = 0;
  v143 = "CloudAPPreLogonUserSurrogate";
  v144 = 0;
  v146 = 0;
  v157 = 0;
  v147 = 0;
  v148 = 0;
  v149 = 0;
  v150 = 0;
  v151 = 0;
  v152 = 0;
  v153 = 0;
  v154 = 0;
  v155 = 0;
  v156 = 0;
  v158 = 1;
  v159 = 0;
  v160 = &v140;
  v161 = 0;
  v162 = 0;
  v163 = &v139;
  v164 = 0;
  v165 = 0;
  v166 = &v142;
  v167 = 0;
  v139 = &CloudAPProvider::CloudAPPreLogonUserSurrogate::`vftable';
  v11 = "";
  if ( !a3 || !a5 || !a7 || !a6 )
  {
    DomainInfo = -1073741811;
    v106 = -1073741811;
    v20 = "";
    while ( 1 )
    {
      v21 = v20--;
      v22 = *v20 == 92;
      if ( *v20 == 92 )
        break;
      if ( v20 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v22 = *v20 == 92;
        break;
      }
    }
    SourceSid = "Invalid Arg(s)";
    v98 = 7837;
    goto LABEL_98;
  }
  *a7 = 0;
  if ( *(_DWORD *)a6 == 1 )
  {
    *(_QWORD *)&v134 = 0;
    DomainInfo = LsapDbLookupGetDomainInfo(0, &v134, 0);
    v106 = DomainInfo;
    if ( DomainInfo )
    {
      v15 = "";
      while ( 1 )
      {
        v16 = v15--;
        v17 = *v15 == 92;
        if ( *v15 == 92 )
          break;
        if ( v15 <= "onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp" )
        {
          v17 = *v15 == 92;
          break;
        }
      }
      if ( v17 )
        v15 = v16;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", DomainInfo, v15, 722, "IsDomainJoined", &Class);
      v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v97) = 7850;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", DomainInfo, v18, v97, "IsDomainJoined", &Class);
LABEL_84:
      if ( (DomainInfo & 0x80000000) == 0 )
        goto LABEL_111;
      goto LABEL_101;
    }
    v19 = 0;
    if ( (_QWORD)v134 )
      v19 = *(_QWORD *)(v134 + 64) != 0;
    if ( !v19 )
    {
      DomainInfo = -2146893042;
      v106 = -2146893042;
      v20 = "";
      while ( 1 )
      {
        v21 = v20--;
        v22 = *v20 == 92;
        if ( *v20 == 92 )
          break;
        if ( v20 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v22 = *v20 == 92;
          break;
        }
      }
      SourceSid = "The machine is not hybrid joined";
      v98 = 7855;
LABEL_98:
      if ( v22 )
        v20 = v21;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", DomainInfo, v20, v98, SourceSid, &Class);
      goto LABEL_101;
    }
    switch ( v118 )
    {
      case Interactive:
      case Network:
      case Batch:
      case Service:
      case NetworkCleartext:
      case RemoteInteractive:
        v23 = 0;
        goto LABEL_26;
      case CachedInteractive:
      case CachedRemoteInteractive:
      case CachedUnlock:
        v23 = 1;
LABEL_26:
        v107 = v23;
        if ( !((unsigned __int8 (__fastcall *)(__int128 *))g_pLsaFunctionTable->GetCallInfo)(&v137) )
        {
          DomainInfo = -1073741595;
          v106 = -1073741595;
          v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v24, 7885, "GetCallInfo", &Class);
          goto LABEL_101;
        }
        DomainInfo = GetLogonCredsFromAuthBuffer(a3, a5, a4, (struct _DECRYPTED_AUTH_DATA *)&v132, &v114);
        v106 = DomainInfo;
        if ( DomainInfo )
        {
          v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v99) = 7896;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", DomainInfo, v25, v99, "GetLogonCredsFromAuthBuffer", &Class);
          v119 = v114;
          goto LABEL_84;
        }
        v26 = v133;
        if ( !memcmp_0(&SEC_WINNT_AUTH_DATA_TYPE_FIDO, (char *)v133 + 4, 0x10u)
          || !memcmp_0(SEC_WINNT_AUTH_DATA_TYPE_DELEGATION_TOKEN, (char *)v26 + 4, 0x10u) )
        {
          goto LABEL_39;
        }
        if ( memcmp_0(&SEC_WINNT_AUTH_DATA_TYPE_NGC, (char *)v26 + 4, 0x10u) )
        {
          DomainInfo = -2146893042;
          v106 = -2146893042;
          v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          v134 = *(_OWORD *)((char *)v26 + 4);
          LODWORD(v99) = 7926;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%u", 2148074254LL, v29, v99, "Unsupported credential type", &v134);
          goto LABEL_35;
        }
        if ( (*((_BYTE *)v26 + *((unsigned int *)v26 + 5) + 8) & 8) == 0 )
        {
          DomainInfo = -2146893042;
          v106 = -2146893042;
          LODWORD(v99) = 7914;
          v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            2148074254LL,
            v27,
            v99,
            "Non-CloudTrust NGC credential not supported.",
            &Class);
LABEL_35:
          v119 = v114;
          goto LABEL_101;
        }
        if ( v107 )
        {
          DomainInfo = -2146893042;
          v106 = -2146893042;
          v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v99) = 7920;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            2148074254LL,
            v28,
            v99,
            "CloudTrust NGC not supported during cached logon.",
            &Class);
          goto LABEL_35;
        }
LABEL_39:
        v30 = v114;
        v119 = v114;
        DomainInfo = RefPackageByProvName(v114, &v117);
        v106 = DomainInfo;
        if ( (DomainInfo & 0x80000000) != 0 )
        {
          v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v99) = 7933;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", DomainInfo, v31, v99, "RefPackageByProvName", v32);
          DomainInfo = RefDefaultPackage(&v117);
          v106 = DomainInfo;
        }
        if ( DomainInfo )
        {
          v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v99) = 7937;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", DomainInfo, v33, v99, "RefPackageByProvName", v34);
LABEL_83:
          v10 = v117;
          goto LABEL_84;
        }
        v35 = v117;
        if ( (*((_BYTE *)v117 + 160) & 4) == 0 )
        {
          DomainInfo = -2146893042;
          v106 = -2146893042;
          v36 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v99) = 7942;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            2148074254LL,
            v36,
            v99,
            "The plugin doesn't have surrogate logon capability",
            &Class);
          v10 = v35;
          goto LABEL_101;
        }
        DomainInfo = ConvertAuthDataToAuthDataInt(
                       1u,
                       v117,
                       v30,
                       (struct _DECRYPTED_AUTH_DATA *)&v132,
                       (unsigned __int16 **)&v130,
                       &v125,
                       &v126);
        v106 = DomainInfo;
        if ( DomainInfo )
        {
          v37 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v100) = 7956;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", DomainInfo, v37, v100, "ConvertAuthDataToAuthDataInt", &Class);
          goto LABEL_83;
        }
        DomainInfo = GetUnlockBufferForDPAPICache(
                       v35,
                       (struct _DECRYPTED_AUTH_DATA *)&v130,
                       (struct _DPAPI_DECODED_AUTH_DATA *)v122);
        v106 = DomainInfo;
        if ( DomainInfo )
        {
          v38 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v100) = 7962;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", DomainInfo, v38, v100, "GetUnlockBufferForDPAPICache", &Class);
          goto LABEL_83;
        }
        CurrentThreadId = GetCurrentThreadId();
        wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
          v168,
          "CloudAPPreLogonUserSurrogate",
          v40,
          CurrentThreadId);
        v168[0] = &CloudAPProvider::CloudAPPreLogonUserSurrogate::`vftable';
        CloudAPProvider::CloudAPPreLogonUserSurrogate::StartActivity(
          (CloudAPProvider::CloudAPPreLogonUserSurrogate *)v168,
          v41);
        CloudAPProvider::CloudAPPreLogonUserSurrogate::operator=(&v139, v168);
        CloudAPProvider::CloudAPPreLogonUserSurrogate::~CloudAPPreLogonUserSurrogate((CloudAPProvider::CloudAPPreLogonUserSurrogate *)v168);
        v112 = 1;
        v42 = (DWORD2(v137) & 0x41800) != 0;
        DomainInfo = _CreateOrAcquireUserCacheEntry(v42, (struct _GUID *)((char *)v35 + 68), v125, 0, &v116);
        v106 = DomainInfo;
        if ( DomainInfo )
        {
          v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v101) = 7977;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", DomainInfo, v43, v101, "CreateOrAcquireUserCacheEntry", &Class);
          goto LABEL_83;
        }
        LockAndUnProtectUserCacheEntry(v116, 1);
        v44 = LogonCloudUser(
                v118,
                v35,
                v42,
                &v116,
                (struct _DECRYPTED_AUTH_DATA *)&v130,
                v122,
                0,
                v126,
                0,
                &v107,
                (struct _CloudAPCache **)&hMem,
                &v111,
                &v110,
                &v109,
                &v113,
                &v108,
                0,
                &v124,
                0,
                0,
                0,
                0);
        if ( v44 >= 0 )
        {
          *((_DWORD *)v116 + 86) = *((_DWORD *)v116 + 74);
          if ( v108 )
          {
            if ( v122[0] == 7 )
            {
              DomainInfo = _GetLogonCacheForUser(
                             *((const unsigned __int16 **)v35 + 43),
                             (const unsigned __int16 *)v116 + 52,
                             L"PublicCacheData",
                             (struct _CloudAPCache **)&v129);
              v106 = DomainInfo;
              LODWORD(v114) = DomainInfo;
              if ( (DomainInfo & 0x80000000) == 0 )
              {
                LODWORD(v114) = GetFidoDecryptedPrimaryApCache(
                                  (struct _CloudAPCache *)v129,
                                  (struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *)((char *)v131
                                                                              + *((unsigned int *)v131 + 5)),
                                  (unsigned __int8 *)(*(_QWORD *)&v122[2] + *(unsigned int *)(*(_QWORD *)&v122[2] + 16LL)),
                                  *(_DWORD *)(*(_QWORD *)&v122[2] + 20LL),
                                  &v120,
                                  &v121);
                v50 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(v96) = 8051;
                WPPTraceLogA(2, "0x%08x %s:%u : %s:%ws", v51, v50);
                CloudAPProvider::FidoPrimaryApCacheRetrievalStatus<long &>((int *)&v114);
              }
              else
              {
                CloudAPProvider::FidoPrimaryApCacheRetrievalStatus<long &>((int *)&v114);
                v48 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(v96) = 8030;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", DomainInfo, v48);
                if ( DomainInfo == -1073741801 || DomainInfo == -1073741670 )
                {
                  v49 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                  LODWORD(v96) = 8035;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", DomainInfo, v49, v96, "GetLogonPublicCacheForUser", &Class);
                  goto LABEL_82;
                }
              }
            }
            if ( v122[0] - 5 > 2 )
              goto LABEL_71;
            v52 = 0;
            if ( v110 )
              v52 = 2;
            if ( v109 )
              v52 |= 4u;
            if ( v52
              && UpdateCacheNodeFlags(
                   (struct _CloudAPCache *)hMem,
                   (struct _USER_CACHE_ENTRY *)((char *)v116 + 296),
                   *((struct _CREDENTIAL_KEY **)v116 + 33),
                   v52,
                   (unsigned int)v96) )
            {
              v53 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
              LODWORD(v102) = 8083;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v54, v53, v102, "EnableCacheNodeFlags", &Class);
            }
            DomainInfo = SaveCaches(
                           (const unsigned __int16 **)v35,
                           v111,
                           !v107,
                           (struct _CloudAPCache *)hMem,
                           v116,
                           v124,
                           (struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *)((char *)v131 + *((unsigned int *)v131 + 5)),
                           0,
                           0);
            v106 = DomainInfo;
            if ( DomainInfo )
            {
              v55 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
              LODWORD(v96) = 8098;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", DomainInfo, v55, v96, "SaveCaches", &Class);
            }
            else
            {
LABEL_71:
              v56 = ((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(96);
              v57 = v56;
              v127 = v56;
              if ( v56 )
              {
                *(_DWORD *)v56 = 0;
                *(_QWORD *)(v56 + 80) = RetrieveKerbSupplementalCredential;
                *(_QWORD *)(v56 + 88) = v116;
                v59 = (unsigned int)(v120 != 0) + 1 + *((_DWORD *)a6 + 3);
                LODWORD(v114) = 0;
                DomainInfo = RtlULongLongToULong(24 * v59, (unsigned int *)&v114);
                v106 = DomainInfo;
                if ( DomainInfo )
                {
                  v60 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                  LODWORD(v96) = 8116;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", DomainInfo, v60, v96, "RtlDWordMult", &Class);
                }
                else
                {
                  v61 = ((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)((unsigned int)v114);
                  v128 = v61;
                  if ( v61 )
                  {
                    v63 = 0;
                    v64 = *((unsigned int *)a6 + 3);
                    if ( (_DWORD)v64 )
                    {
                      do
                      {
                        v65 = 3 * v63;
                        v66 = *((_QWORD *)a6 + 2);
                        *(_OWORD *)(v61 + 8 * v65) = *(_OWORD *)(v66 + 24 * v63);
                        *(_QWORD *)(v61 + 8 * v65 + 16) = *(_QWORD *)(v66 + 24 * v63 + 16);
                        v63 = (unsigned int)(v63 + 1);
                        v64 = *((unsigned int *)a6 + 3);
                      }
                      while ( (unsigned int)v63 < (unsigned int)v64 );
                    }
                    v67 = 3 * v64;
                    *(_DWORD *)(v61 + 8 * v67) = 73383531;
                    *(_DWORD *)(v61 + 8 * v67 + 4) = 1107655061;
                    *(_DWORD *)(v61 + 8 * v67 + 8) = -93056623;
                    *(_DWORD *)(v61 + 8 * v67 + 12) = 658300316;
                    *(_QWORD *)(v61 + 24LL * *((unsigned int *)a6 + 3) + 16) = v57;
                    v127 = 0;
                    if ( v120 )
                    {
                      v68 = 3LL * (unsigned int)++*((_DWORD *)a6 + 3);
                      *(_DWORD *)(v61 + 8 * v68) = -1899063973;
                      *(_DWORD *)(v61 + 8 * v68 + 4) = 1106830124;
                      *(_DWORD *)(v61 + 8 * v68 + 8) = 2090153604;
                      *(_DWORD *)(v61 + 8 * v68 + 12) = 909273123;
                      *(_QWORD *)(v61 + 24LL * *((unsigned int *)a6 + 3) + 16) = v120;
                      v120 = 0;
                    }
                    v69 = *((_QWORD *)a6 + 2);
                    *((_QWORD *)a6 + 2) = v61;
                    v128 = v69;
                    *((_DWORD *)a6 + 3) = v59;
                  }
                  else
                  {
                    DomainInfo = -1073741801;
                    v106 = -1073741801;
                    v62 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                    LODWORD(v96) = 8122;
                    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v62, v96, "AllocateLsaHeap", &Class);
                  }
                }
              }
              else
              {
                DomainInfo = -1073741801;
                v106 = -1073741801;
                v58 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(v96) = 8106;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v58, v96, "AllocateLsaHeap", &Class);
              }
            }
            goto LABEL_82;
          }
          DomainInfo = -2146893042;
          v106 = -2146893042;
          v47 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v96) = 8017;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 2148074254LL, v47, v96, "No kerberos ticket", &Class);
        }
        else
        {
          v115 = v44;
          DomainInfo = -1073741715;
          v106 = -1073741715;
          v45 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v96) = 8009;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v46, v45, v96, "LogonCloudUser", &Class);
        }
LABEL_82:
        UnlockAndProtectUserCacheEntry(v116);
        goto LABEL_83;
      default:
        DomainInfo = -1073741557;
        v106 = -1073741557;
        v70 = "";
        while ( 1 )
        {
          v71 = v70--;
          v72 = *v70 == 92;
          if ( *v70 == 92 )
            break;
          if ( v70 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
          {
            v72 = *v70 == 92;
            break;
          }
        }
        if ( v72 )
          v70 = v71;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%u", 3221225739LL, v70, 7878, "Unsupported Logon Type", v118);
        goto LABEL_101;
    }
  }
  DomainInfo = -1073741736;
  v106 = -1073741736;
  v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225560LL, v13, 7845, "SurrogateLogonVersion", v14);
LABEL_101:
  v73 = v116;
  if ( v116 && (*((_BYTE *)v116 + 348) & 2) == 0 )
  {
    RtlAcquireResourceExclusive(&g_UserCacheListLock, 1u);
    _InterlockedDecrement((volatile signed __int32 *)v73 + 4);
    if ( !*((_DWORD *)v73 + 4) )
    {
      v74 = *(_QWORD *)v73;
      if ( *(struct _USER_CACHE_ENTRY **)(*(_QWORD *)v73 + 8LL) != v73
        || (v75 = (struct _USER_CACHE_ENTRY **)*((_QWORD *)v73 + 1), *v75 != v73) )
      {
        __fastfail(3u);
      }
      *v75 = (struct _USER_CACHE_ENTRY *)v74;
      *(_QWORD *)(v74 + 8) = v75;
      if ( (*((_BYTE *)v73 + 348) & 1) != 0 )
      {
        _AddStaleUserCacheEntry(v73);
        CloudAPProvider::AddStaleUserCacheEntry();
      }
      else
      {
        _FreeUserCacheEntryBuffer(v73);
      }
    }
    RtlReleaseResource(&g_UserCacheListLock);
  }
LABEL_111:
  v116 = 0;
  if ( v10 )
    RtlReleaseResource(&g_PackageListLock);
  v76 = v115;
  if ( (DomainInfo & 0x80000000) != 0
    && v115 >= 0
    && DomainInfo != -1073741801
    && DomainInfo != -1073741670
    && DomainInfo != -2146893042 )
  {
    v76 = DomainInfo;
    v115 = DomainInfo;
    DomainInfo = -2146893042;
    v106 = -2146893042;
  }
  *v135 = v76;
  if ( v112 )
  {
    v77 = v122[0] == 5;
    v78 = v108;
    v79 = v113;
    v80 = v109;
    v81 = v110;
    v82 = v107;
    v83 = GetCurrentThreadId();
    v105 = v77;
    DomainInfo = v106;
    v104 = v78;
    v84 = v119;
    CloudAPProvider::CloudAPPreLogonUserSurrogate::Stop(
      (CloudAPProvider::CloudAPPreLogonUserSurrogate *)&v139,
      v83,
      v119,
      v118,
      v122[0],
      v82,
      v81,
      v80,
      v79,
      v104,
      v106,
      v115,
      v105);
    v9 = v136;
  }
  else
  {
    v84 = v119;
  }
  v85 = *(_BYTE **)&v122[2];
  if ( *(_QWORD *)&v122[2] )
  {
    v86 = v122[1];
    if ( v122[1] )
    {
      do
      {
        *v85++ = 0;
        --v86;
      }
      while ( v86 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  FreePackedCreds(v133);
  if ( (_QWORD)v132 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( *((_QWORD *)&v132 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v132 = 0;
  v133 = 0;
  FreePackedCreds(v131);
  if ( (_QWORD)v130 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( *((_QWORD *)&v130 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v130 = 0;
  v131 = 0;
  if ( v84 )
    ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v84);
  FreeUserInfo(v124);
  FreeCloudAPCache(hMem);
  if ( v125 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v126 )
    FreeScardPin(v126);
  if ( v127 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v87 = v128;
  if ( v128 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)v9 + 3); i = (unsigned int)(i + 1) )
      ((void (__fastcall *)(_QWORD))g_pLsaFunctionTable->FreeLsaHeap)(*(_QWORD *)(*((_QWORD *)v9 + 2) + 24 * i + 16));
    ((void (__fastcall *)(__int64))g_pLsaFunctionTable->FreeLsaHeap)(v87);
  }
  FreeCloudAPCache(v129);
  v89 = v120;
  if ( v120 )
  {
    v90 = v121;
    if ( v121 )
    {
      do
      {
        *v89++ = 0;
        --v90;
      }
      while ( v90 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  if ( (DomainInfo & 0x80000000) == 0 )
  {
    while ( 1 )
    {
      v93 = v11--;
      v94 = *v11 == 92;
      if ( *v11 == 92 )
        break;
      if ( v11 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v94 = *v11 == 92;
        break;
      }
    }
    if ( v94 )
      v11 = v93;
    LODWORD(v96) = 8247;
    WPPTraceLogA(2, "0x%08x %s:%u : %s:%ws", DomainInfo, v11, v96, "CloudAPPreLogonUserSurrogate succeeded", &Class);
  }
  else
  {
    while ( 1 )
    {
      v91 = v11--;
      v92 = *v11 == 92;
      if ( *v11 == 92 )
        break;
      if ( v11 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v92 = *v11 == 92;
        break;
      }
    }
    if ( v92 )
      v11 = v91;
    LODWORD(v96) = 8243;
    WPPTraceLogA(2, "0x%08x %s:%u : %s:%ws", DomainInfo, v11, v96, "CloudAPPreLogonUserSurrogate", &Class);
  }
  CloudAPProvider::CloudAPPreLogonUserSurrogate::~CloudAPPreLogonUserSurrogate((CloudAPProvider::CloudAPPreLogonUserSurrogate *)&v139);
  return DomainInfo;
}

```

## disassembly

```asm
0x180017780  mov     [rsp-8+arg_0], rbx
0x180017785  push    rbp
0x180017786  push    rsi
0x180017787  push    rdi
0x180017788  push    r12
0x18001778a  push    r13
0x18001778c  push    r14
0x18001778e  push    r15
0x180017790  lea     rbp, [rsp-340h]
0x180017798  sub     rsp, 470h
0x18001779f  mov     rax, cs:__security_cookie
0x1800177a6  xor     rax, rsp
0x1800177a9  mov     [rbp+370h+var_40], rax
0x1800177b0  mov     r14, r9
0x1800177b3  mov     rsi, r8
0x1800177b6  mov     [rbp+370h+var_3C0], edx
0x1800177b9  mov     rdi, [rbp+370h+arg_28]
0x1800177c0  mov     [rbp+370h+var_308], rdi
0x1800177c4  mov     rax, [rbp+370h+arg_30]
0x1800177cb  mov     [rbp+370h+var_310], rax
0x1800177cf  xor     edx, edx
0x1800177d1  mov     [rbp+370h+var_3D8], edx
0x1800177d4  mov     [rbp+370h+var_3EC], dl
0x1800177d7  mov     [rbp+370h+var_3E8], dl
0x1800177da  mov     [rbp+370h+var_3E9], dl
0x1800177dd  mov     [rbp+370h+var_3EA], dl
0x1800177e0  mov     [rbp+370h+var_3E6], dl
0x1800177e3  mov     [rbp+370h+var_3E7], dl
0x1800177e6  mov     [rbp+370h+var_3EB], dl
0x1800177e9  xorps   xmm0, xmm0
0x1800177ec  xor     ecx, ecx
0x1800177ee  movups  [rbp+370h+var_340], xmm0
0x1800177f2  mov     [rbp+370h+var_330], rcx
0x1800177f6  xorps   xmm1, xmm1
0x1800177f9  movups  [rbp+370h+var_358], xmm1
0x1800177fd  mov     [rbp+370h+var_348], rcx
0x180017801  movups  xmmword ptr [rbp+370h+var_3A0], xmm0
0x180017805  movups  [rbp+370h+var_300], xmm1
0x180017809  mov     [rbp+370h+var_2F0], rcx
0x180017810  mov     [rbp+370h+var_3B8], rdx
0x180017814  mov     [rbp+370h+var_3E0], rdx
0x180017818  mov     r15d, edx
0x18001781b  mov     [rbp+370h+var_3C8], rdx
0x18001781f  mov     [rbp+370h+var_3D0], rdx
0x180017823  mov     [rbp+370h+var_388], rdx
0x180017827  mov     [rbp+370h+hMem], rdx
0x18001782b  mov     [rbp+370h+var_380], rdx
0x18001782f  mov     [rbp+370h+var_378], rdx
0x180017833  mov     [rbp+370h+var_370], rdx
0x180017837  mov     [rbp+370h+var_368], rdx
0x18001783b  mov     [rbp+370h+var_360], rdx
0x18001783f  mov     [rbp+370h+var_3B0], rdx
0x180017843  mov     [rbp+370h+var_3A8], edx
0x180017846  mov     [rbp+370h+var_2D8], edx
0x18001784c  mov     [rbp+370h+var_2D4], cl
0x180017852  mov     [rbp+370h+var_298], cl
0x180017858  mov     [rbp+370h+var_2B0], edx
0x18001785e  lea     rcx, aCloudapprelogo_0; "CloudAPPreLogonUserSurrogate"
0x180017865  mov     [rbp+370h+var_2A8], rcx
0x18001786c  mov     [rbp+370h+var_2A0], rdx
0x180017873  mov     [rbp+370h+var_290], edx
0x180017879  movdqa  [rbp+370h+var_1F0], xmm0
0x180017881  xor     ecx, ecx
0x180017883  movups  [rbp+370h+var_288], xmm1
0x18001788a  movups  [rbp+370h+var_278], xmm1
0x180017891  movups  [rbp+370h+var_268], xmm1
0x180017898  movups  [rbp+370h+var_258], xmm1
0x18001789f  movups  [rbp+370h+var_248], xmm1
0x1800178a6  movups  [rbp+370h+var_238], xmm1
0x1800178ad  movups  [rbp+370h+var_228], xmm1
0x1800178b4  movups  [rbp+370h+var_218], xmm1
0x1800178bb  movups  [rbp+370h+var_208], xmm1
0x1800178c2  mov     [rbp+370h+var_1F8], rcx
0x1800178c9  mov     [rbp+370h+var_1E0], 1
0x1800178d3  mov     [rbp+370h+var_1D8], rcx
0x1800178da  lea     rcx, [rbp+370h+var_2D8]
0x1800178e1  mov     [rbp+370h+var_1D0], rcx
0x1800178e8  mov     [rbp+370h+var_1C8], rdx
0x1800178ef  mov     [rbp+370h+var_1C0], rdx
0x1800178f6  lea     rcx, [rbp+370h+var_2E0]
0x1800178fd  mov     [rbp+370h+var_1B8], rcx
0x180017904  mov     [rbp+370h+var_1B0], rdx
0x18001790b  mov     [rbp+370h+var_1A8], edx
0x180017911  lea     rcx, [rbp+370h+var_2B0]
0x180017918  mov     [rbp+370h+var_1A0], rcx
0x18001791f  mov     [rbp+370h+var_198], dl
0x180017925  lea     rcx, ??_7CloudAPPreLogonUserSurrogate@CloudAPProvider@@6B@; const CloudAPProvider::CloudAPPreLogonUserSurrogate::`vftable'
0x18001792c  mov     [rbp+370h+var_2E0], rcx
0x180017933  lea     r13, aOnecoreDsExtCl_6+27h; ""
0x18001793a  lea     r8, Class
0x180017941  test    rsi, rsi
0x180017944  jz      loc_18001859A
0x18001794a  mov     ebx, [rbp+370h+arg_20]
0x180017950  test    ebx, ebx
0x180017952  jz      loc_18001859A
0x180017958  test    rax, rax
0x18001795b  jz      loc_18001859A
0x180017961  test    rdi, rdi
0x180017964  jz      loc_18001859A
0x18001796a  mov     [rax], edx
0x18001796c  cmp     dword ptr [rdi], 1
0x18001796f  jz      short loc_1800179A8
0x180017971  mov     r12d, 0C0000058h
0x180017977  mov     [rbp+370h+var_3F0], r12d
0x18001797b  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180017982  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017987  mov     r9, rax
0x18001798a  mov     [rsp+4A0h+var_470], r8
0x18001798f  lea     rax, aSurrogatelogon_0; "SurrogateLogonVersion"
0x180017996  mov     [rsp+4A0h+SourceSid], rax
0x18001799b  mov     dword ptr [rsp+4A0h+var_480], 1EA5h
0x1800179a3  jmp     loc_1800185E2
0x1800179a8  mov     qword ptr [rbp+370h+var_320], rdx
0x1800179ac  xor     r8d, r8d
0x1800179af  lea     rdx, [rbp+370h+var_320]
0x1800179b3  xor     ecx, ecx
0x1800179b5  call    cs:__imp_LsapDbLookupGetDomainInfo
0x1800179bb  mov     r12d, eax
0x1800179be  mov     [rbp+370h+var_3F0], eax
0x1800179c1  test    eax, eax
0x1800179c3  jz      loc_180017A61
0x1800179c9  lea     r9, aOnecoreDsExtCl+2Eh; ""
0x1800179d0  lea     rdx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x1800179d7  nop     word ptr [rax+rax+00000000h]
0x1800179e0  mov     rcx, r9
0x1800179e3  dec     r9
0x1800179e6  movzx   eax, byte ptr [r9]
0x1800179ea  cmp     al, 5Ch ; '\'
0x1800179ec  jz      short loc_1800179F5
0x1800179ee  cmp     r9, rdx
0x1800179f1  ja      short loc_1800179E0
0x1800179f3  cmp     al, 5Ch ; '\'
0x1800179f5  cmovz   r9, rcx
0x1800179f9  lea     rsi, Class
0x180017a00  mov     [rsp+4A0h+var_470], rsi
0x180017a05  lea     rbx, aIsdomainjoined; "IsDomainJoined"
0x180017a0c  mov     [rsp+4A0h+SourceSid], rbx
0x180017a11  mov     dword ptr [rsp+4A0h+var_480], 2D2h
0x180017a19  mov     r8d, r12d
0x180017a1c  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180017a23  xor     ecx, ecx
0x180017a25  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180017a2a  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180017a31  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017a36  mov     r9, rax
0x180017a39  mov     [rsp+4A0h+var_470], rsi
0x180017a3e  mov     [rsp+4A0h+SourceSid], rbx
0x180017a43  mov     dword ptr [rsp+4A0h+var_480], 1EAAh
0x180017a4b  mov     r8d, r12d
0x180017a4e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180017a55  xor     ecx, ecx
0x180017a57  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180017a5c  jmp     loc_180018534
0x180017a61  xor     al, al
0x180017a63  mov     rcx, qword ptr [rbp+370h+var_320]
0x180017a67  test    rcx, rcx
0x180017a6a  jz      short loc_180017A7C
0x180017a6c  movzx   eax, al
0x180017a6f  cmp     qword ptr [rcx+40h], 0
0x180017a74  mov     ecx, 1
0x180017a79  cmovnz  eax, ecx
0x180017a7c  test    al, al
0x180017a7e  jnz     short loc_180017ADA
0x180017a80  mov     r12d, 8009030Eh
0x180017a86  mov     [rbp+370h+var_3F0], r12d
0x180017a8a  mov     r9, r13
0x180017a8d  lea     rbx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180017a94  nop     dword ptr [rax+00h]
0x180017a98  nop     dword ptr [rax+rax+00000000h]
0x180017aa0  mov     rcx, r9
0x180017aa3  dec     r9
0x180017aa6  movzx   eax, byte ptr [r9]
0x180017aaa  cmp     al, 5Ch ; '\'
0x180017aac  jz      short loc_180017AB5
0x180017aae  cmp     r9, rbx
0x180017ab1  ja      short loc_180017AA0
0x180017ab3  cmp     al, 5Ch ; '\'
0x180017ab5  lea     rax, Class
0x180017abc  mov     [rsp+4A0h+var_470], rax
0x180017ac1  lea     rax, aTheMachineIsNo; "The machine is not hybrid joined"
0x180017ac8  mov     [rsp+4A0h+SourceSid], rax
0x180017acd  mov     dword ptr [rsp+4A0h+var_480], 1EAFh
0x180017ad5  jmp     loc_1800185DE
0x180017ada  mov     edx, [rbp+370h+var_3C0]
0x180017add  lea     eax, [rdx-2]; switch 12 cases
0x180017ae0  cmp     eax, 0Bh
0x180017ae3  ja      def_180017AFD; jumptable 0000000180017AFD default case, cases 6,7,9
0x180017ae9  cdqe
0x180017aeb  lea     r8, __ImageBase
0x180017af2  mov     ecx, ds:(jpt_180017AFD - 180000000h)[r8+rax*4]
0x180017afa  add     rcx, r8
0x180017afd  jmp     rcx; switch jump
0x180017aff  xor     al, al; jumptable 0000000180017AFD cases 2-5,8,10
0x180017b01  jmp     short loc_180017B05
0x180017b03  mov     al, 1; jumptable 0000000180017AFD cases 11-13
0x180017b05  mov     [rbp+370h+var_3EC], al
0x180017b08  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180017b0f  lea     rcx, [rbp+370h+var_300]
0x180017b13  mov     rax, [rax+0C0h]
0x180017b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b1f  test    al, al
0x180017b21  jnz     short loc_180017B61
0x180017b23  mov     r12d, 0C00000E5h
0x180017b29  mov     [rbp+370h+var_3F0], r12d
0x180017b2d  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180017b34  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017b39  mov     r9, rax
0x180017b3c  lea     rax, Class
0x180017b43  mov     [rsp+4A0h+var_470], rax
0x180017b48  lea     rax, aGetcallinfo; "GetCallInfo"
0x180017b4f  mov     [rsp+4A0h+SourceSid], rax
0x180017b54  mov     dword ptr [rsp+4A0h+var_480], 1ECDh
0x180017b5c  jmp     loc_1800185E2
0x180017b61  lea     rax, [rbp+370h+var_3E0]
0x180017b65  mov     [rsp+4A0h+var_480], rax; unsigned __int16 **
0x180017b6a  lea     r9, [rbp+370h+var_340]; struct _DECRYPTED_AUTH_DATA *
0x180017b6e  mov     r8, r14; void *
0x180017b71  mov     edx, ebx; unsigned int
0x180017b73  mov     rcx, rsi; struct _KERB_CERTIFICATE_LOGON *
0x180017b76  call    ?GetLogonCredsFromAuthBuffer@@YAJPEAXK0PEAU_DECRYPTED_AUTH_DATA@@PEAPEAG@Z; GetLogonCredsFromAuthBuffer(void *,ulong,void *,_DECRYPTED_AUTH_DATA *,ushort * *)
0x180017b7b  mov     r12d, eax
0x180017b7e  mov     [rbp+370h+var_3F0], eax
0x180017b81  test    eax, eax
0x180017b83  jz      short loc_180017BD2
0x180017b85  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180017b8c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017b91  mov     r9, rax
0x180017b94  lea     rax, Class
0x180017b9b  mov     [rsp+4A0h+var_470], rax
0x180017ba0  lea     rax, aGetlogoncredsf; "GetLogonCredsFromAuthBuffer"
0x180017ba7  mov     [rsp+4A0h+SourceSid], rax
0x180017bac  mov     dword ptr [rsp+4A0h+var_480], 1ED8h
0x180017bb4  mov     r8d, r12d
0x180017bb7  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180017bbe  xor     ecx, ecx
0x180017bc0  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180017bc5  mov     rax, [rbp+370h+var_3E0]
0x180017bc9  mov     [rbp+370h+var_3B8], rax
0x180017bcd  jmp     loc_180018534
0x180017bd2  mov     rsi, [rbp+370h+var_330]
0x180017bd6  mov     r8d, 10h; Size
0x180017bdc  lea     rdx, [rsi+4]; Buf2
0x180017be0  lea     rcx, SEC_WINNT_AUTH_DATA_TYPE_FIDO; Buf1
0x180017be7  call    memcmp_0
0x180017bec  test    eax, eax
0x180017bee  jz      loc_180017D20
0x180017bf4  mov     r8d, 10h; Size
0x180017bfa  lea     rdx, [rsi+4]; Buf2
0x180017bfe  lea     rcx, SEC_WINNT_AUTH_DATA_TYPE_DELEGATION_TOKEN; Buf1
0x180017c05  call    memcmp_0
0x180017c0a  test    eax, eax
0x180017c0c  jz      loc_180017D20
0x180017c12  mov     r8d, 10h; Size
0x180017c18  lea     rdx, [rsi+4]; Buf2
0x180017c1c  lea     rcx, SEC_WINNT_AUTH_DATA_TYPE_NGC; Buf1
0x180017c23  call    memcmp_0
0x180017c28  test    eax, eax
0x180017c2a  jnz     loc_180017CD6
0x180017c30  mov     eax, [rsi+14h]
0x180017c33  test    byte ptr [rax+rsi+8], 8
0x180017c38  jnz     short loc_180017C91
0x180017c3a  mov     r12d, 8009030Eh
0x180017c40  mov     [rbp+370h+var_3F0], r12d
0x180017c44  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180017c4b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017c50  mov     r9, rax
0x180017c53  lea     rax, Class
0x180017c5a  mov     [rsp+4A0h+var_470], rax
0x180017c5f  lea     rax, aNonCloudtrustN; "Non-CloudTrust NGC credential not suppo"...
0x180017c66  mov     [rsp+4A0h+SourceSid], rax
0x180017c6b  mov     dword ptr [rsp+4A0h+var_480], 1EEAh
0x180017c73  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180017c7a  mov     r8d, r12d
0x180017c7d  xor     ecx, ecx
0x180017c7f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180017c84  mov     rax, [rbp+370h+var_3E0]
0x180017c88  mov     [rbp+370h+var_3B8], rax
0x180017c8c  jmp     loc_1800185F3
0x180017c91  cmp     [rbp+370h+var_3EC], 0
0x180017c95  jz      loc_180017D20
0x180017c9b  mov     r12d, 8009030Eh
0x180017ca1  mov     [rbp+370h+var_3F0], r12d
0x180017ca5  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180017cac  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017cb1  mov     r9, rax
0x180017cb4  lea     rax, Class
0x180017cbb  mov     [rsp+4A0h+var_470], rax
0x180017cc0  lea     rax, aCloudtrustNgcN; "CloudTrust NGC not supported during cac"...
0x180017cc7  mov     [rsp+4A0h+SourceSid], rax
0x180017ccc  mov     dword ptr [rsp+4A0h+var_480], 1EF0h
0x180017cd4  jmp     short loc_180017C73
0x180017cd6  mov     r12d, 8009030Eh
0x180017cdc  mov     [rbp+370h+var_3F0], r12d
0x180017ce0  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180017ce7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017cec  movups  xmm0, xmmword ptr [rsi+4]
0x180017cf0  movaps  [rbp+370h+var_320], xmm0
0x180017cf4  lea     rcx, [rbp+370h+var_320]
0x180017cf8  mov     [rsp+4A0h+var_470], rcx
0x180017cfd  lea     rcx, aUnsupportedCre; "Unsupported credential type"
  ... truncated ...
```
