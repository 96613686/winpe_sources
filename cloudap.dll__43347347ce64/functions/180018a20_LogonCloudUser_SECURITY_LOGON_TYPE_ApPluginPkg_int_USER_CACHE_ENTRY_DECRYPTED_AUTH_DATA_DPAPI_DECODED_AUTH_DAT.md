# LogonCloudUser(_SECURITY_LOGON_TYPE,_ApPluginPkg *,int,_USER_CACHE_ENTRY * *,_DECRYPTED_AUTH_DATA *,_DPAPI_DECODED_AUTH_DATA *,bool,_SCARD_PIN *,bool,bool *,_CloudAPCache * *,bool *,bool *,bool *,bool *,bool *,bool *,_APPLUGIN_USER_INFO * *,_ApPluginSubPkg * *,_AP_BLOB *,_tagCacheNodeIdentifier *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x180018a20`
- end: `0x180019e3f`
- name: `?LogonCloudUser@@YAJW4_SECURITY_LOGON_TYPE@@PEAU_ApPluginPkg@@HPEAPEAU_USER_CACHE_ENTRY@@PEAU_DECRYPTED_AUTH_DATA@@PEAU_DPAPI_DECODED_AUTH_DATA@@_NPEAU_SCARD_PIN@@5PEA_NPEAPEAU_CloudAPCache@@777777PEAPEAU_APPLUGIN_USER_INFO@@PEAPEAU_ApPluginSubPkg@@PEAU_AP_BLOB@@PEAU_tagCacheNodeIdentifier@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `5151`
- prototype: `__int64 __fastcall(enum _SECURITY_LOGON_TYPE, struct _ApPluginPkg *, int, struct _USER_CACHE_ENTRY **, struct _DECRYPTED_AUTH_DATA *, PSID SourceSid, bool, struct _SCARD_PIN *, bool, bool *, struct _CloudAPCache **, bool *, bool *, bool *, bool *, bool *, bool *, struct _APPLUGIN_USER_INFO **, struct _ApPluginSubPkg **, struct _AP_BLOB *, struct _tagCacheNodeIdentifier *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `3`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800035b4`
- `0x180011960`
- `0x180017780`

## callees

- `0x180003ef4`
- `0x1800046f4`
- `0x180004e80`
- `0x180007fc0`
- `0x18000a600`
- `0x18000b9b0`
- `0x18000ce50`
- `0x18000f700`
- `0x18000fd50`
- `0x180014d90`
- `0x180018a20`
- `0x18001f8f0`
- `0x1800293c0`
- `0x18002f59c`
- `0x180037240`
- `0x18004cf50`
- `0x18004e1b8`
- `0x180052288`
- `0x180056d00`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018f3c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019252`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018f3c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019252`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180018f29`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001923f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180018f29`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001923f`
- `ntdll!RtlReleaseResource` at `0x180019918`
- `ntdll!RtlReleaseResource` at `0x180019af9`
- `ntdll!RtlReleaseResource` at `0x180019b08`
- `ntdll!RtlReleaseResource` at `0x180019bd4`
- `ntdll!RtlReleaseResource` at `0x180019cf4`
- `ntdll!RtlReleaseResource` at `0x180019918`
- `ntdll!RtlReleaseResource` at `0x180019af9`
- `ntdll!RtlReleaseResource` at `0x180019b08`
- `ntdll!RtlReleaseResource` at `0x180019bd4`
- `ntdll!RtlReleaseResource` at `0x180019cf4`
- `ntdll!RtlAcquireResourceShared` at `0x1800198a1`
- `ntdll!RtlAcquireResourceShared` at `0x1800199ab`
- `ntdll!RtlAcquireResourceShared` at `0x1800198a1`
- `ntdll!RtlAcquireResourceShared` at `0x1800199ab`
- `LSASRV!LsaICheckRestrictedMode` at `0x180018e46`
- `LSASRV!LsaICheckRestrictedMode` at `0x180018e46`

## string_xrefs

- `0x180019a04`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180019a96`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180019b34`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180018b50`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180018bbd`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180019b96`: `AddEntryInLookupCacheForSubPkgs`
- `0x180019a31`: `_AddEntryInLookupCache`
- `0x180019ab6`: `_AddEntryInLookupCache(SubPkg)`
- `0x18001938c`: `CleanupUserCache`
- `0x180019bfa`: `UpdateSidNameCaches`
- `0x180019b4a`: `FlushIdentityCache`
- `0x180018dbf`: `GetLogonCache`
- `0x180018d52`: `User is not connected for service/ARSO logon`
- `0x180018f6f`: `not checking cache in restricted mode`
- `0x180018fbf`: `CachedLogon`
- `0x180019451`: `Smart Card has been revoked. Disabled cached logon for subsequent logons.`
- `0x18001956e`: `Cached logon is disabled by plugin`
- `0x1800195b0`: `Cached logon is allowed by plugin`
- `0x18001976a`: `UpdatePwdExpiryInfo`

## pseudocode

```c
__int64 __fastcall LogonCloudUser(
        unsigned int a1,
        struct _ApPluginPkg *a2,
        int a3,
        struct _USER_CACHE_ENTRY **a4,
        const unsigned __int16 **a5,
        struct _DPAPI_DECODED_AUTH_DATA *SourceSid,
        bool a7,
        struct _SCARD_PIN *a8,
        bool a9,
        bool *a10,
        struct _CloudAPCache **a11,
        bool *a12,
        bool *a13,
        bool *a14,
        bool *a15,
        bool *a16,
        bool *a17,
        struct _APPLUGIN_USER_INFO **a18,
        struct _ApPluginSubPkg **a19,
        struct _AP_BLOB *a20,
        struct _tagCacheNodeIdentifier *a21,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a22)
{
  struct _USER_CACHE_ENTRY *v23; // rdx
  struct _tagCacheNodeIdentifier *v24; // r15
  unsigned int LogonCache; // edi
  const char *v26; // rax
  int *v27; // rcx
  const char *v28; // rbx
  int v29; // r14d
  const char *v30; // r9
  char v31; // al
  const char *v32; // rcx
  bool v33; // zf
  const char *v34; // r9
  const char *v35; // r9
  const char *v36; // r9
  const char *v37; // r9
  const char *v38; // r9
  char v39; // al
  const char *v40; // rcx
  bool v41; // zf
  int v42; // r14d
  bool v43; // r13
  char v44; // al
  const char *v45; // rcx
  bool v46; // zf
  __int64 v47; // r8
  const char *v48; // rax
  __int64 v49; // r8
  struct _DPAPI_DECODED_AUTH_DATA *v50; // rdi
  const char *v51; // rax
  const char *v52; // r9
  char v53; // al
  const char *v54; // rcx
  bool v55; // zf
  bool *v56; // rax
  bool *v57; // rdx
  bool *v58; // rax
  const char *v59; // r9
  char v60; // al
  const char *v61; // r9
  char v62; // al
  const char *v63; // rcx
  bool v64; // zf
  struct _APPLUGIN_USER_INFO *v65; // rcx
  _WORD *v66; // rdx
  struct _APPLUGIN_USER_INFO *v67; // r8
  const char *v68; // r9
  const char *v69; // rax
  __int64 v70; // r8
  const char *v71; // r9
  const char *v72; // rax
  const char *v73; // rax
  struct _USER_CACHE_ENTRY *v74; // r13
  struct _APPLUGIN_USER_INFO *v75; // r14
  bool v76; // r15
  char v77; // al
  char v78; // al
  const char *v79; // rax
  const char *v80; // rdx
  int v81; // ecx
  char v82; // cl
  const char *v83; // rdx
  bool v84; // zf
  const char *v85; // r9
  char v86; // al
  const char *v87; // rcx
  bool v88; // zf
  const char *v89; // r9
  BOOL v90; // edx
  char v91; // al
  const char *v92; // rcx
  bool v93; // zf
  const unsigned __int16 *v94; // rcx
  const char *v95; // r9
  char v96; // al
  const char *v97; // rcx
  bool v98; // zf
  char v99; // al
  LONG HighPart; // eax
  struct _APPLUGIN_USER_INFO *v101; // r15
  _WORD *v102; // rcx
  _WORD *v103; // rcx
  _WORD *v104; // rcx
  const char *v105; // r9
  WCHAR *v106; // rdi
  struct _RTL_BALANCED_NODE *v107; // r14
  int v108; // eax
  struct _RTL_BALANCED_NODE *v109; // r14
  int v110; // eax
  const char *v111; // r9
  HKEY ParentValue; // r12
  const unsigned __int16 *v113; // r13
  HKEY v114; // rdi
  const char *v115; // r9
  char v116; // al
  const char *v117; // rdx
  int v118; // eax
  const char *v119; // rdx
  char v120; // al
  const char *v121; // r8
  const char *v122; // rax
  const char *v123; // r9
  char v124; // al
  const char *v125; // rcx
  bool v126; // zf
  char v127; // al
  HKEY v128; // rdx
  const char *v129; // rax
  __int64 v130; // r8
  struct _APPLUGIN_USER_INFO **v131; // rcx
  struct _CloudAPCache *v132; // rax
  struct _CloudAPCache *v133; // rax
  char v134; // al
  HLOCAL v135; // rsi
  unsigned int v136; // ebx
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v137; // r9
  ULONG v138; // r8d
  __int64 v139; // rax
  __int64 CredentialSize; // rdx
  PUCHAR Credentials; // rcx
  struct _SCARD_PIN *v143; // [rsp+28h] [rbp-D9h]
  struct _SCARD_PIN *v144; // [rsp+28h] [rbp-D9h]
  struct _SCARD_PIN *v145; // [rsp+28h] [rbp-D9h]
  struct _SCARD_PIN *v146; // [rsp+28h] [rbp-D9h]
  struct _SCARD_PIN *v147; // [rsp+28h] [rbp-D9h]
  struct _SCARD_PIN *v148; // [rsp+28h] [rbp-D9h]
  struct _SCARD_PIN *v149; // [rsp+28h] [rbp-D9h]
  const char *v150; // [rsp+30h] [rbp-D1h]
  struct _APPLUGIN_USER_INFO *v151; // [rsp+78h] [rbp-89h] BYREF
  struct _USER_CACHE_ENTRY *v152; // [rsp+80h] [rbp-81h]
  HLOCAL hMem; // [rsp+88h] [rbp-79h] BYREF
  struct _APPLUGIN_USER_INFO *v154; // [rsp+90h] [rbp-71h] BYREF
  int v155; // [rsp+98h] [rbp-69h] BYREF
  int v156; // [rsp+9Ch] [rbp-65h] BYREF
  int v157; // [rsp+A0h] [rbp-61h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A8h] [rbp-59h] BYREF
  int *v159; // [rsp+B0h] [rbp-51h] BYREF
  unsigned __int16 *v160; // [rsp+B8h] [rbp-49h] BYREF
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v161; // [rsp+C0h] [rbp-41h] BYREF
  struct _USER_CACHE_ENTRY **v166; // [rsp+130h] [rbp+2Fh]
  PSID SourceSida; // [rsp+140h] [rbp+3Fh]
  bool *v168; // [rsp+170h] [rbp+6Fh]

  v23 = *a4;
  v156 = 1;
  v157 = 0;
  SystemTimeAsFileTime = 0;
  *a11 = 0;
  v155 = 0;
  v152 = v23;
  v161 = 0;
  *a12 = 0;
  v151 = 0;
  hMem = 0;
  v154 = 0;
  *a13 = 0;
  v160 = 0;
  *a14 = 0;
  *a16 = 0;
  *a15 = 0;
  *a18 = 0;
  if ( a17 )
    *a17 = 0;
  if ( a19 )
    *a19 = 0;
  if ( a20 )
    *(_OWORD *)a20 = 0;
  v24 = a21;
  if ( a21 )
    *(_OWORD *)a21 = 0;
  if ( *(_DWORD *)SourceSid == 3 && !*a10 )
  {
    LogonCache = -1073741477;
    v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225819LL, v26, 5939, "Interactive logon doesn't work for TBAL", &Class);
    goto LABEL_268;
  }
  v27 = 0;
  v33 = (*((_BYTE *)a2 + 160) & 1) == 0;
  v28 = "";
  LODWORD(a22) = 0;
  v159 = 0;
  if ( v33 )
  {
    v29 = 2;
  }
  else
  {
    v29 = 0;
    LogonCache = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int **, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY ***))g_pLsaIdProvHostFunctionTable
                  + 4))(
                   *((_QWORD *)a2 + 2),
                   *((_QWORD *)v23 + 12),
                   0,
                   6,
                   &v159,
                   &a22);
    if ( LogonCache )
    {
      v30 = "";
      while ( 1 )
      {
        v31 = *(v30 - 1);
        v32 = v30--;
        v33 = v31 == 92;
        if ( v31 == 92 )
          break;
        if ( v30 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v33 = v31 == 92;
          break;
        }
      }
      if ( v33 )
        v30 = v32;
      LODWORD(v143) = 2093;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCache, v30, v143, "LookUpUserInfo", &Class);
      goto LABEL_21;
    }
    if ( (_DWORD)a22 != 4 )
    {
      LogonCache = -1073741595;
      v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v143) = 2098;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v34, v143, "No shadow account", &Class);
LABEL_21:
      v27 = v159;
      goto LABEL_27;
    }
    v27 = v159;
    v29 = *v159;
  }
  LogonCache = 0;
LABEL_27:
  if ( v27 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( LogonCache )
  {
    v35 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(v143) = 5948;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCache, v35, v143, "GetUserType", &Class);
    goto LABEL_268;
  }
  if ( !v29 )
  {
    LogonCache = -1073741724;
    v36 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(v143) = 5953;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225572LL, v36, v143, "Unknown User", &Class);
    goto LABEL_268;
  }
  if ( v29 == 1 && (a7 || *(_DWORD *)SourceSid == 3) )
  {
    LogonCache = -1073741724;
    v37 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(v143) = 5964;
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%ws",
      3221225572LL,
      v37,
      v143,
      "User is not connected for service/ARSO logon",
      &Class);
    goto LABEL_268;
  }
  LogonCache = GetLogonCache((const unsigned __int16 **)a2, v152, SourceSid, &hMem, a12);
  if ( (LogonCache & 0x80000000) != 0 )
  {
    v38 = "";
    while ( 1 )
    {
      v39 = *(v38 - 1);
      v40 = v38--;
      v41 = v39 == 92;
      if ( v39 == 92 )
        break;
      if ( v38 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v41 = v39 == 92;
        break;
      }
    }
    if ( v41 )
      v38 = v40;
    LODWORD(v144) = 5976;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCache, v38, v144, "GetLogonCache", &Class);
    if ( LogonCache == -1073741801 || LogonCache == -1073741670 || *a10 )
    {
      while ( 1 )
      {
        v44 = *(v28 - 1);
        v45 = v28--;
        v46 = v44 == 92;
        if ( v44 == 92 )
          break;
        if ( v28 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v46 = v44 == 92;
          break;
        }
      }
      v47 = LogonCache;
      v150 = "GetLogonCache";
      LODWORD(v145) = 5981;
      goto LABEL_265;
    }
    v42 = -1073741718;
    v43 = LogonCache == -1073741718;
    goto LABEL_78;
  }
  v43 = 0;
  if ( (unsigned int)LsaICheckRestrictedMode(&v155) )
  {
    v48 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(v144) = 5993;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v49, v48, v144, "LsaICheckRestrictedMode", &Class);
  }
  if ( v155 )
  {
    v42 = -1073741043;
    v51 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(v144) = 6014;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221226253LL, v51, v144, "not checking cache in restricted mode", &Class);
    v50 = SourceSid;
  }
  else
  {
    v50 = SourceSid;
    v42 = CachedLogon(a2, v152, SourceSid, (struct _CloudAPCache *)hMem, a8, &v151, &v156, &v157, a13, a16, a20, v24);
    if ( v42 >= 0 )
    {
      if ( g_ulPlatformId == 3 && (*((_BYTE *)a2 + 160) & 0x40) != 0 && *(_DWORD *)SourceSid != 3 )
      {
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        if ( CompareFileTime((const FILETIME *)v151 + 13, &SystemTimeAsFileTime) < 0 )
          *a15 = 1;
      }
      goto LABEL_78;
    }
  }
  v52 = "";
  while ( 1 )
  {
    v53 = *(v52 - 1);
    v54 = v52--;
    v55 = v53 == 92;
    if ( v53 == 92 )
      break;
    if ( v52 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
    {
      v55 = v53 == 92;
      break;
    }
  }
  if ( v55 )
    v52 = v54;
  LODWORD(v145) = 6018;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v42, v52, v145, "CachedLogon", &Class);
  if ( v42 == -1073741801
    || v42 == -1073741670
    || *a10
    || (unsigned int)(*(_DWORD *)v50 - 4) <= 1 && (unsigned int)(v42 + 1073740928) <= 1 )
  {
    LogonCache = v42;
    while ( 1 )
    {
      v134 = *(v28 - 1);
      v45 = v28--;
      v46 = v134 == 92;
      if ( v134 == 92 )
        break;
      if ( v28 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v46 = v134 == 92;
        break;
      }
    }
    v47 = (unsigned int)v42;
    v150 = "CachedLogon";
    LODWORD(v145) = 6033;
    goto LABEL_265;
  }
  if ( v42 == -1073741557 )
  {
    v56 = a14;
    *a14 = 1;
    goto LABEL_79;
  }
  if ( v42 == -1073741718 )
  {
    v43 = 1;
  }
  else
  {
    FreeCloudAPCache(hMem);
    hMem = 0;
  }
LABEL_78:
  v56 = a14;
LABEL_79:
  v57 = a10;
  if ( *a10 )
  {
LABEL_134:
    v58 = a15;
    goto LABEL_135;
  }
  if ( v156 || v157 || v42 < 0 || *a13 || *v56 || (v58 = a15, *a15) )
  {
    if ( a9 )
    {
      LogonCache = -1073741608;
      v59 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v145) = 6094;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225688LL, v59, v145, "DelayInteractiveLogon", &Class);
      goto LABEL_268;
    }
    LogonCache = DuplicateString(a5[1], 0, &v160);
    if ( LogonCache )
    {
      while ( 1 )
      {
        v60 = *(v28 - 1);
        v45 = v28--;
        v46 = v60 == 92;
        if ( v60 == 92 )
          break;
        if ( v28 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v46 = v60 == 92;
          break;
        }
      }
      v150 = "DuplicateString";
      v47 = LogonCache;
      LODWORD(v145) = 6098;
      goto LABEL_265;
    }
    LogonCache = InteractiveLogon(
                   a1,
                   a2,
                   a3,
                   a4,
                   (struct _DECRYPTED_AUTH_DATA *)a5,
                   SourceSid,
                   v43,
                   (struct _CloudAPCache **)&hMem,
                   &v154,
                   a12,
                   a8,
                   a20,
                   a21,
                   &v161);
    if ( (LogonCache & 0x80000000) == 0 )
    {
      if ( a17 )
        *a17 = 1;
      if ( (*((_DWORD *)v154 + 32) & 1) == 0 || (*((_DWORD *)a2 + 40) & 1) != 0 )
      {
        *a14 = 0;
        v79 = "";
        while ( 1 )
        {
          v82 = *(v79 - 1);
          v83 = v79--;
          v84 = v82 == 92;
          if ( v82 == 92 )
            break;
          if ( v79 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
          {
            v84 = v82 == 92;
            break;
          }
        }
        if ( v84 )
          v79 = v83;
        v81 = 6245;
        v80 = "Cached logon is allowed by plugin";
      }
      else
      {
        *a14 = 1;
        v79 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        v80 = "Cached logon is disabled by plugin";
        v81 = 6240;
      }
      LODWORD(v146) = v81;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCache, v79, v146, v80, &Class);
      v85 = "";
      *a13 = 0;
      while ( 1 )
      {
        v86 = *(v85 - 1);
        v87 = v85--;
        v88 = v86 == 92;
        if ( v86 == 92 )
          break;
        if ( v85 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v88 = v86 == 92;
          break;
        }
      }
      if ( v88 )
        v85 = v87;
      LODWORD(v147) = 6250;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCache, v85, v147, "Will re-enable optimized logon", &Class);
      v89 = "";
      v90 = v161 != 0;
      *a16 = v161 != 0;
      while ( 1 )
      {
        v91 = *(v89 - 1);
        v92 = v89--;
        v93 = v91 == 92;
        if ( v91 == 92 )
          break;
        if ( v89 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v93 = v91 == 92;
          break;
        }
      }
      if ( v93 )
        v89 = v92;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%u", LogonCache, v89, 6253, "Setting Kerberos callback creds", v90);
      FreeUserInfo(v151);
      v57 = a10;
      v151 = v154;
      v154 = 0;
      v74 = *a4;
      v58 = a15;
      v152 = *a4;
      goto LABEL_136;
    }
    v61 = "";
    while ( 1 )
    {
      v62 = *(v61 - 1);
      v63 = v61--;
      v64 = v62 == 92;
      if ( v62 == 92 )
        break;
      if ( v61 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v64 = v62 == 92;
        break;
      }
    }
    if ( v64 )
      v61 = v63;
    LODWORD(v146) = 6117;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCache, v61, v146, "InteractiveLogon", &Class);
    if ( LogonCache == -1073741801 || LogonCache == -1073741670 || LogonCache == -1073741564 || v42 < 0 )
    {
      while ( 1 )
      {
        v78 = *(v28 - 1);
        v45 = v28--;
        v46 = v78 == 92;
        if ( v78 == 92 )
          break;
        if ( v28 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v46 = v78 == 92;
          break;
        }
      }
      v150 = "InteractiveLogon";
      v47 = LogonCache;
      LODWORD(v145) = 6123;
      goto LABEL_265;
    }
    if ( LogonCache == -1073741711 && (*((_BYTE *)a2 + 160) & 0x40) != 0 )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( CompareFileTime((const FILETIME *)v151 + 13, &SystemTimeAsFileTime) >= 0 )
        *((_QWORD *)v151 + 13) = *(_QWORD *)&SystemTimeAsFileTime - 864000000000LL;
      v65 = v154;
      if ( v154 )
      {
        v66 = (_WORD *)*((_QWORD *)v154 + 12);
        if ( v66 )
        {
          if ( *v66 )
          {
            v67 = v151;
            if ( *((_QWORD *)v151 + 12) )
            {
              ((void (__fastcall *)(_QWORD))g_pLsaFunctionTable->FreeLsaHeap)(*((_QWORD *)v151 + 12));
              *((_QWORD *)v151 + 12) = 0;
              v67 = v151;
              v65 = v154;
            }
            LogonCache = DuplicateString(*((const unsigned __int16 **)v65 + 12), 0, (unsigned __int16 **)v67 + 12);
            if ( LogonCache )
            {
              v68 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
              LODWORD(v145) = 6152;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCache, v68, v145, "DuplicateString", &Class);
              goto LABEL_268;
            }
          }
        }
      }
      if ( g_ulPlatformId != 3 )
      {
LABEL_131:
        if ( !*a4 )
          *a4 = v152;
        v57 = a10;
        *a10 = 1;
        goto LABEL_134;
      }
      *a15 = 1;
    }
    if ( g_ulPlatformId == 3 && (*((_DWORD *)a2 + 40) & 1) == 0 )
    {
      if ( ((LogonCache + 1073741718) & 0xFFFFFFFB) != 0 )
      {
        if ( LogonCache == -1073741710 && v151 )
        {
          if ( (unsigned int)CleanupUserCache(a2, *((void **)v151 + 2), 0) )
          {
            v69 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(v145) = 6202;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v70, v69, v145, "CleanupUserCache", &Class);
          }
          v71 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v145) = 6205;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225586LL, v71, v145, "InteractiveLogon", &Class);
          goto LABEL_268;
        }
      }
      else
      {
        if ( *a13 )
        {
          while ( 1 )
          {
            v77 = *(v28 - 1);
            v45 = v28--;
            v46 = v77 == 92;
            if ( v77 == 92 )
              break;
            if ( v28 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
            {
              v46 = v77 == 92;
              break;
            }
          }
          v150 = "InteractiveLogon:Optimized logon is disabled";
          v47 = LogonCache;
          LODWORD(v145) = 6190;
          goto LABEL_265;
        }
        *a13 = 1;
        *a12 = 1;
        v72 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v145) = 6184;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCache, v72, v145, "Will disable optimized logon", &Class);
        LogonCache = 0;
      }
      if ( *(_DWORD *)SourceSid == 4 && LogonCache == -1073740919 )
      {
        *a14 = 1;
        v73 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v145) = 6213;
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          3221226377LL,
          v73,
          v145,
          "Smart Card has been revoked. Disabled cached logon for subsequent logons.",
          &Class);
        CloudAPProvider::SmartCardCacheDisabled();
      }
    }
    goto LABEL_131;
  }
  *a10 = 1;
LABEL_135:
  v74 = v152;
LABEL_136:
  v75 = v151;
  v76 = !*v57 || *v58;
  v94 = (const unsigned __int16 *)*((_QWORD *)v151 + 12);
  a14 = 0;
  LogonCache = DuplicateString(v94, 0, (unsigned __int16 **)&a14);
  if ( LogonCache )
  {
    v95 = "";
    while ( 1 )
    {
      v96 = *(v95 - 1);
      v97 = v95--;
      v98 = v96 == 92;
      if ( v96 == 92 )
        break;
      if ( v95 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v98 = v96 == 92;
        break;
      }
    }
    if ( v98 )
      v95 = v97;
    LODWORD(v145) = 5824;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCache, v95, v145, "DuplicateString", &Class);
    if ( a14 )
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    while ( 1 )
    {
      v99 = *(v28 - 1);
      v45 = v28--;
      v46 = v99 == 92;
      if ( v99 == 92 )
        break;
      if ( v28 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v46 = v99 == 92;
        break;
      }
    }
    v150 = "UpdatePwdExpiryInfo";
    v47 = LogonCache;
    LODWORD(v145) = 6288;
LABEL_265:
    if ( v46 )
      v28 = v45;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v47, v28, v145, v150, &Class);
    goto LABEL_268;
  }
  if ( *((_QWORD *)v74 + 39) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  *((_QWORD *)v74 + 39) = a14;
  if ( v76 )
  {
    *((_DWORD *)v74 + 80) = *((_DWORD *)v75 + 26);
    HighPart = *((_DWORD *)v75 + 27);
  }
  else
  {
    *((_DWORD *)v74 + 80) = g_TimeForever.LowPart;
    HighPart = g_TimeForever.HighPart;
  }
  *((_DWORD *)v74 + 81) = HighPart;
  v101 = v151;
  v166 = (struct _USER_CACHE_ENTRY **)*((_QWORD *)v74 + 12);
  if ( (*((_DWORD *)a2 + 40) & 0xD) == 8 )
  {
    v102 = (_WORD *)*((_QWORD *)v151 + 9);
    if ( v102 )
    {
      if ( *v102 )
      {
        v103 = (_WORD *)*((_QWORD *)v151 + 10);
        if ( v103 )
        {
          if ( *v103 )
          {
            v104 = (_WORD *)*((_QWORD *)v151 + 11);
            if ( v104 )
            {
              if ( *v104 )
              {
                LogonCache = RegisterSubPackage(
                               0,
                               a2,
                               *((const unsigned __int16 **)v151 + 10),
                               *((const unsigned __int16 **)v151 + 11));
                if ( LogonCache )
                {
                  v105 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                  LODWORD(v145) = 5766;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCache, v105, v145, "RegisterSubPackage", &Class);
                  goto LABEL_246;
                }
                v106 = (WCHAR *)*((_QWORD *)v101 + 10);
                RtlAcquireResourceShared(*((PRTL_RESOURCE *)a2 + 45), 1u);
                if ( v106 )
                {
                  v107 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)a2 + 47);
                  while ( v107 )
                  {
                    v108 = SubPkgTable_CompareNames(v106, v107);
                    if ( v108 >= 0 )
                    {
                      if ( v108 <= 0 )
                      {
LABEL_217:
                        ParentValue = (HKEY)v107[24].ParentValue;
                        v113 = (const unsigned __int16 *)&v107[2];
                        goto LABEL_219;
                      }
                      v107 = v107->Children[1];
                    }
                    else
                    {
                      v107 = v107->Children[0];
                    }
                  }
                  v109 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)a2 + 48);
                  while ( v109 )
                  {
                    v110 = SubPkgTable_CompareDnsNames(v106, v109);
                    if ( v110 >= 0 )
                    {
                      if ( v110 <= 0 )
                      {
                        v107 = v109 - 1;
                        goto LABEL_217;
                      }
                      v109 = v109->Children[1];
                    }
                    else
                    {
                      v109 = v109->Children[0];
                    }
                  }
                }
                RtlReleaseResource(*((PRTL_RESOURCE *)a2 + 45));
                LogonCache = -2146893039;
                v111 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(v145) = 5769;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 2148074257LL, v111, v145, "RefSubPackage", &Class);
                goto LABEL_246;
              }
            }
          }
        }
      }
    }
  }
  v107 = 0;
  ParentValue = 0;
  v113 = (const unsigned __int16 *)((char *)a2 + 24);
LABEL_219:
  v168 = (bool *)*((_QWORD *)v101 + 5);
  LODWORD(a14) = *((_DWORD *)v101 + 32);
  SourceSida = (PSID)*((_QWORD *)v101 + 2);
  LODWORD(a15) = 0;
  LODWORD(a13) = 0;
  v114 = (HKEY)*((_QWORD *)a2 + 44);
  RtlAcquireResourceShared(&g_LookupsCacheLock, 1u);
  LogonCache = _AddEntryInLookupCache(
                 v114,
                 v113,
                 (const unsigned __int16 *)v152 + 52,
                 (const unsigned __int16 *)v166,
                 SourceSida,
                 (unsigned int)a14,
                 v160,
                 (const unsigned __int16 *)v168,
                 (int *)&a15);
  if ( LogonCache )
  {
    v115 = "";
    do
    {
      v116 = *(v115 - 1);
      v117 = v115--;
    }
    while ( v116 != 92 && v115 > "onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp" );
    v33 = v116 == 92;
    v118 = 2289;
    if ( v33 )
      v115 = v117;
    v119 = "_AddEntryInLookupCache";
LABEL_233:
    LODWORD(v148) = v118;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCache, v115, v148, v119, &Class);
    RtlReleaseResource(&g_LookupsCacheLock);
    goto LABEL_238;
  }
  if ( ParentValue )
  {
    LogonCache = _AddEntryInLookupCache(
                   ParentValue,
                   v113,
                   (const unsigned __int16 *)v152 + 52,
                   (const unsigned __int16 *)v166,
                   SourceSida,
                   (unsigned int)a14,
                   v160,
                   (const unsigned __int16 *)v168,
                   (int *)&a13);
    if ( LogonCache )
    {
      v115 = "";
      do
      {
        v120 = *(v115 - 1);
        v121 = v115--;
      }
      while ( v120 != 92 && v115 > "onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp" );
      v119 = "_AddEntryInLookupCache(SubPkg)";
      v33 = v120 == 92;
      v118 = 2304;
      if ( v33 )
        v115 = v121;
      goto LABEL_233;
    }
  }
  RtlReleaseResource(&g_LookupsCacheLock);
  if ( (_DWORD)a15 || (_DWORD)a13 )
  {
    LogonCache = FlushIdentityCache(SourceSida);
    if ( LogonCache )
    {
      v122 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
      LODWORD(v148) = 2313;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCache, v122, v148, "FlushIdentityCache", &Class);
LABEL_238:
      v123 = "";
      while ( 1 )
      {
        v124 = *(v123 - 1);
        v125 = v123--;
        v126 = v124 == 92;
        if ( v124 == 92 )
          break;
        if ( v123 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v126 = v124 == 92;
          break;
        }
      }
      if ( v126 )
        v123 = v125;
      LODWORD(v149) = 5792;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCache, v123, v149, "AddEntryInLookupCacheForSubPkgs", &Class);
      if ( v107 )
        RtlReleaseResource(*((PRTL_RESOURCE *)a2 + 45));
LABEL_246:
      while ( 1 )
      {
        v127 = *(v28 - 1);
        v45 = v28--;
        v46 = v127 == 92;
        if ( v127 == 92 )
          break;
        if ( v28 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v46 = v127 == 92;
          break;
        }
      }
      v150 = "UpdateSidNameCaches";
      v47 = LogonCache;
      LODWORD(v145) = 6307;
      goto LABEL_265;
    }
  }
  if ( (g_ulTestFlags & 2) == 0 )
  {
    v128 = v107 ? (HKEY)v107[24].ParentValue : 0LL;
    if ( (unsigned int)CleanupPreRS2Names(*((HKEY *)a2 + 44), v128, *((const unsigned __int16 **)v152 + 11)) )
    {
      v129 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v148) = 6317;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v130, v129, v148, "CleanupPreRS2Names", &Class);
    }
  }
  LogonCache = 0;
  v131 = a18;
  if ( a19 )
  {
    *a19 = (struct _ApPluginSubPkg *)v107;
    *v131 = v151;
    v132 = (struct _CloudAPCache *)hMem;
    v151 = 0;
    hMem = 0;
    *a11 = v132;
  }
  else
  {
    *a18 = v151;
    v133 = (struct _CloudAPCache *)hMem;
    v151 = 0;
    hMem = 0;
    *a11 = v133;
    if ( v107 )
      RtlReleaseResource(*((PRTL_RESOURCE *)a2 + 45));
  }
LABEL_268:
  FreeUserInfo(v151);
  v135 = hMem;
  if ( hMem )
  {
    v136 = 0;
    if ( *((_DWORD *)hMem + 5) )
    {
      do
        FreeCloudAPCacheNodeContents(*((_QWORD *)v135 + 3) + 32LL * v136++);
      while ( v136 < *((_DWORD *)v135 + 5) );
    }
    FreeMemory(*((void **)v135 + 3));
    FreeMemory(v135);
  }
  FreeUserInfo(v154);
  if ( v160 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v137 = v161;
  if ( v161 )
  {
    v138 = 0;
    if ( v161->CredentialCount )
    {
      do
      {
        v139 = v138;
        CredentialSize = v137->Credentials[v139].CredentialSize;
        Credentials = v137->Credentials[v139].Credentials;
        if ( v137->Credentials[v139].CredentialSize )
        {
          do
          {
            *Credentials++ = 0;
            --CredentialSize;
          }
          while ( CredentialSize );
          v137 = v161;
        }
        ++v138;
      }
      while ( v138 < v137->CredentialCount );
    }
    ((void (__fastcall *)(struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *))g_pLsaFunctionTable->FreeLsaHeap)(v137);
  }
  return LogonCache;
}

```

## disassembly

```asm
0x180018a20  mov     rax, rsp
0x180018a23  mov     [rax+20h], r9
0x180018a27  mov     [rax+18h], r8d
0x180018a2b  mov     [rax+10h], rdx
0x180018a2f  mov     [rax+8], ecx
0x180018a32  push    rbp
0x180018a33  lea     rbp, [rax-0Fh]
0x180018a37  sub     rsp, 100h
0x180018a3e  mov     [rax-18h], rsi
0x180018a42  mov     r10, rdx
0x180018a45  mov     rdx, [r9]
0x180018a48  mov     [rax-30h], r13
0x180018a4c  mov     [rax-40h], r15
0x180018a50  mov     rax, [rbp+7+arg_50]
0x180018a54  mov     [rbp+7+var_6C], 1
0x180018a5b  mov     [rbp+7+var_68], 0
0x180018a62  mov     qword ptr [rbp+7+SystemTimeAsFileTime.dwLowDateTime], 0
0x180018a6a  mov     qword ptr [rax], 0
0x180018a71  mov     rax, [rbp+7+arg_58]
0x180018a75  mov     [rbp+7+var_70], 0
0x180018a7c  mov     [rsp+100h+var_88], rdx
0x180018a81  mov     [rbp+7+var_48], 0
0x180018a89  mov     byte ptr [rax], 0
0x180018a8c  mov     rax, [rbp+7+arg_60]
0x180018a90  mov     [rsp+100h+var_90], 0
0x180018a99  mov     [rbp+7+hMem], 0
0x180018aa1  mov     [rbp+7+var_78], 0
0x180018aa9  mov     byte ptr [rax], 0
0x180018aac  mov     rax, [rbp+7+arg_68]
0x180018ab0  mov     [rbp+7+var_50], 0
0x180018ab8  mov     byte ptr [rax], 0
0x180018abb  mov     rax, [rbp+7+arg_78]
0x180018ac2  mov     byte ptr [rax], 0
0x180018ac5  mov     rax, [rbp+7+arg_70]
0x180018acc  mov     byte ptr [rax], 0
0x180018acf  mov     rax, [rbp+7+arg_88]
0x180018ad6  mov     qword ptr [rax], 0
0x180018add  mov     rax, [rbp+7+arg_80]
0x180018ae4  test    rax, rax
0x180018ae7  jz      short loc_180018AEC
0x180018ae9  mov     byte ptr [rax], 0
0x180018aec  mov     rax, [rbp+7+arg_90]
0x180018af3  test    rax, rax
0x180018af6  jz      short loc_180018AFF
0x180018af8  mov     qword ptr [rax], 0
0x180018aff  mov     rax, [rbp+7+arg_98]
0x180018b06  test    rax, rax
0x180018b09  jz      short loc_180018B11
0x180018b0b  xorps   xmm0, xmm0
0x180018b0e  movups  xmmword ptr [rax], xmm0
0x180018b11  mov     r15, [rbp+7+arg_A0]
0x180018b18  test    r15, r15
0x180018b1b  jz      short loc_180018B24
0x180018b1d  xorps   xmm0, xmm0
0x180018b20  movups  xmmword ptr [r15], xmm0
0x180018b24  mov     r13, [rbp+7+SourceSid]
0x180018b28  mov     [rsp+0F8h], rbx
0x180018b30  mov     [rsp+100h+var_18], rdi
0x180018b38  mov     [rsp+100h+var_30], r14
0x180018b40  cmp     dword ptr [r13+0], 3
0x180018b45  jnz     short loc_180018B9A
0x180018b47  mov     rax, [rbp+7+arg_48]
0x180018b4b  cmp     byte ptr [rax], 0
0x180018b4e  jnz     short loc_180018B9A
0x180018b50  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180018b57  mov     edi, 0C000015Bh
0x180018b5c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180018b61  mov     r9, rax
0x180018b64  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180018b6b  lea     rax, Class
0x180018b72  mov     r8d, edi
0x180018b75  mov     [rsp+100h+var_D0], rax
0x180018b7a  xor     ecx, ecx
0x180018b7c  lea     rax, aInteractiveLog; "Interactive logon doesn't work for TBAL"
0x180018b83  mov     [rsp+100h+var_D8], rax
0x180018b88  mov     dword ptr [rsp+100h+var_E0], 1733h
0x180018b90  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180018b95  jmp     loc_180019D47
0x180018b9a  xor     ecx, ecx
0x180018b9c  mov     [rsp+100h+var_20], r12
0x180018ba4  test    byte ptr [r10+0A0h], 1
0x180018bac  lea     rbx, aOnecoreDsExtCl_6+27h; ""
0x180018bb3  mov     dword ptr [rbp+7+arg_A8], 0
0x180018bbd  lea     rsi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180018bc4  mov     [rbp+7+var_58], rcx
0x180018bc8  lea     r12, Class
0x180018bcf  jz      loc_180018CA7
0x180018bd5  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x180018bdc  lea     rcx, [rbp+7+arg_A8]
0x180018be3  mov     rdx, [rdx+60h]
0x180018be7  mov     r9d, 6
0x180018bed  mov     [rsp+100h+var_D8], rcx
0x180018bf2  xor     r8d, r8d
0x180018bf5  lea     rcx, [rbp+7+var_58]
0x180018bf9  xor     r14d, r14d
0x180018bfc  mov     rax, [rax+20h]
0x180018c00  mov     [rsp+100h+var_E0], rcx
0x180018c05  mov     rcx, [r10+10h]
0x180018c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c0e  mov     edi, eax
0x180018c10  test    eax, eax
0x180018c12  jz      short loc_180018C6A
0x180018c14  mov     r9, rbx
0x180018c17  nop     word ptr [rax+rax+00000000h]
0x180018c20  movzx   eax, byte ptr [r9-1]
0x180018c25  mov     rcx, r9
0x180018c28  dec     r9
0x180018c2b  cmp     al, 5Ch ; '\'
0x180018c2d  jz      short loc_180018C36
0x180018c2f  cmp     r9, rsi
0x180018c32  ja      short loc_180018C20
0x180018c34  cmp     al, 5Ch ; '\'
0x180018c36  mov     [rsp+100h+var_D0], r12
0x180018c3b  lea     rax, aLookupuserinfo; "LookUpUserInfo"
0x180018c42  mov     [rsp+100h+var_D8], rax
0x180018c47  cmovz   r9, rcx
0x180018c4b  mov     dword ptr [rsp+100h+var_E0], 82Dh
0x180018c53  mov     r8d, edi
0x180018c56  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180018c5d  xor     ecx, ecx
0x180018c5f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180018c64  mov     rcx, [rbp+7+var_58]
0x180018c68  jmp     short loc_180018CAF
0x180018c6a  cmp     dword ptr [rbp+7+arg_A8], 4
0x180018c71  jz      short loc_180018C9E
0x180018c73  mov     rcx, rsi; char *
0x180018c76  mov     edi, 0C00000E5h
0x180018c7b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180018c80  mov     [rsp+100h+var_D0], r12
0x180018c85  mov     r9, rax
0x180018c88  lea     rax, aNoShadowAccoun; "No shadow account"
0x180018c8f  mov     [rsp+100h+var_D8], rax
0x180018c94  mov     dword ptr [rsp+100h+var_E0], 832h
0x180018c9c  jmp     short loc_180018C53
0x180018c9e  mov     rcx, [rbp+7+var_58]
0x180018ca2  mov     r14d, [rcx]
0x180018ca5  jmp     short loc_180018CAD
0x180018ca7  mov     r14d, 2
0x180018cad  xor     edi, edi
0x180018caf  test    rcx, rcx
0x180018cb2  jz      short loc_180018CC4
0x180018cb4  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180018cbb  mov     rax, [rax+30h]
0x180018cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cc4  test    edi, edi
0x180018cc6  jz      short loc_180018CF4
0x180018cc8  mov     rcx, rsi; char *
0x180018ccb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180018cd0  mov     [rsp+100h+var_D0], r12
0x180018cd5  mov     r9, rax
0x180018cd8  lea     rax, aGetusertype; "GetUserType"
0x180018cdf  mov     r8d, edi
0x180018ce2  mov     [rsp+100h+var_D8], rax
0x180018ce7  mov     dword ptr [rsp+100h+var_E0], 173Ch
0x180018cef  jmp     loc_180019D31
0x180018cf4  test    r14d, r14d
0x180018cf7  jnz     short loc_180018D2A
0x180018cf9  mov     rcx, rsi; char *
0x180018cfc  mov     edi, 0C0000064h
0x180018d01  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180018d06  mov     [rsp+100h+var_D0], r12
0x180018d0b  mov     r9, rax
0x180018d0e  lea     rax, aUnknownUser; "Unknown User"
0x180018d15  mov     r8d, edi
0x180018d18  mov     [rsp+100h+var_D8], rax
0x180018d1d  mov     dword ptr [rsp+100h+var_E0], 1741h
0x180018d25  jmp     loc_180019D31
0x180018d2a  cmp     r14d, 1
0x180018d2e  jnz     short loc_180018D6E
0x180018d30  cmp     [rbp+7+arg_30], 0
0x180018d34  jnz     short loc_180018D3D
0x180018d36  cmp     dword ptr [r13+0], 3
0x180018d3b  jnz     short loc_180018D6E
0x180018d3d  mov     rcx, rsi; char *
0x180018d40  mov     edi, 0C0000064h
0x180018d45  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180018d4a  mov     [rsp+100h+var_D0], r12
0x180018d4f  mov     r9, rax
0x180018d52  lea     rax, aUserIsNotConne; "User is not connected for service/ARSO "...
0x180018d59  mov     r8d, edi
0x180018d5c  mov     [rsp+100h+var_D8], rax
0x180018d61  mov     dword ptr [rsp+100h+var_E0], 174Ch
0x180018d69  jmp     loc_180019D31
0x180018d6e  mov     rax, [rbp+7+arg_58]
0x180018d72  lea     r9, [rbp+7+hMem]; struct _CloudAPCache **
0x180018d76  mov     r14, [rbp+7+arg_8]
0x180018d7a  mov     r8, r13; struct _DPAPI_DECODED_AUTH_DATA *
0x180018d7d  mov     rdx, [rsp+100h+var_88]; struct _USER_CACHE_ENTRY *
0x180018d82  mov     rcx, r14; struct _ApPluginPkg *
0x180018d85  mov     [rsp+100h+var_E0], rax; bool *
0x180018d8a  call    ?GetLogonCache@@YAJPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@PEAU_DPAPI_DECODED_AUTH_DATA@@PEAPEAU_CloudAPCache@@PEA_N@Z; GetLogonCache(_ApPluginPkg *,_USER_CACHE_ENTRY *,_DPAPI_DECODED_AUTH_DATA *,_CloudAPCache * *,bool *)
0x180018d8f  mov     edi, eax
0x180018d91  test    eax, eax
0x180018d93  jns     loc_180018E3F
0x180018d99  mov     r9, rbx
0x180018d9c  nop     dword ptr [rax+00h]
0x180018da0  movzx   eax, byte ptr [r9-1]
0x180018da5  mov     rcx, r9
0x180018da8  dec     r9
0x180018dab  cmp     al, 5Ch ; '\'
0x180018dad  jz      short loc_180018DB6
0x180018daf  cmp     r9, rsi
0x180018db2  ja      short loc_180018DA0
0x180018db4  cmp     al, 5Ch ; '\'
0x180018db6  cmovz   r9, rcx
0x180018dba  mov     [rsp+100h+var_D0], r12
0x180018dbf  lea     r14, aGetlogoncache; "GetLogonCache"
0x180018dc6  mov     r8d, edi
0x180018dc9  mov     [rsp+100h+var_D8], r14
0x180018dce  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180018dd5  xor     ecx, ecx
0x180018dd7  mov     dword ptr [rsp+100h+var_E0], 1758h
0x180018ddf  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180018de4  cmp     edi, 0C0000017h
0x180018dea  jz      short loc_180018E10
0x180018dec  cmp     edi, 0C000009Ah
0x180018df2  jz      short loc_180018E10
0x180018df4  mov     rax, [rbp+7+arg_48]
0x180018df8  cmp     byte ptr [rax], 0
0x180018dfb  jnz     short loc_180018E10
0x180018dfd  mov     r14d, 0C000006Ah
0x180018e03  cmp     edi, r14d
0x180018e06  setz    r13b
0x180018e0a  jmp     loc_180019056
0x180018e10  movzx   eax, byte ptr [rbx-1]
0x180018e14  mov     rcx, rbx
0x180018e17  dec     rbx
0x180018e1a  cmp     al, 5Ch ; '\'
0x180018e1c  jz      short loc_180018E25
0x180018e1e  cmp     rbx, rsi
0x180018e21  ja      short loc_180018E10
0x180018e23  cmp     al, 5Ch ; '\'
0x180018e25  mov     [rsp+100h+var_D0], r12
0x180018e2a  mov     r8d, edi
0x180018e2d  mov     [rsp+100h+var_D8], r14
0x180018e32  mov     dword ptr [rsp+100h+var_E0], 175Dh
0x180018e3a  jmp     loc_180019D2A
0x180018e3f  lea     rcx, [rbp+7+var_70]
0x180018e43  xor     r13b, r13b
0x180018e46  call    cs:__imp_LsaICheckRestrictedMode
0x180018e4c  mov     r8d, eax
0x180018e4f  test    eax, eax
0x180018e51  jz      short loc_180018E85
0x180018e53  mov     rcx, rsi; char *
0x180018e56  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180018e5b  mov     r9, rax
0x180018e5e  mov     [rsp+100h+var_D0], r12
0x180018e63  lea     rax, aLsaicheckrestr; "LsaICheckRestrictedMode"
0x180018e6a  xor     ecx, ecx
0x180018e6c  mov     [rsp+100h+var_D8], rax
0x180018e71  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180018e78  mov     dword ptr [rsp+100h+var_E0], 1769h
0x180018e80  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180018e85  cmp     [rbp+7+var_70], 0
0x180018e89  jnz     loc_180018F59
0x180018e8f  mov     rax, [rbp+7+arg_98]
0x180018e96  mov     rcx, r14; struct _ApPluginPkg *
0x180018e99  mov     rdi, [rbp+7+SourceSid]
0x180018e9d  mov     r9, [rbp+7+hMem]; struct _CloudAPCache *
0x180018ea1  mov     r8, rdi; struct _DPAPI_DECODED_AUTH_DATA *
0x180018ea4  mov     rdx, [rsp+100h+var_88]; struct _USER_CACHE_ENTRY *
0x180018ea9  mov     [rsp+100h+var_A8], r15; struct _tagCacheNodeIdentifier *
0x180018eae  mov     [rsp+100h+var_B0], rax; struct _AP_BLOB *
0x180018eb3  mov     rax, [rbp+7+arg_78]
0x180018eba  mov     [rsp+100h+var_B8], rax; bool *
0x180018ebf  mov     rax, [rbp+7+arg_60]
0x180018ec3  mov     [rsp+100h+var_C0], rax; bool *
0x180018ec8  lea     rax, [rbp+7+var_68]
0x180018ecc  mov     [rsp+100h+var_C8], rax; int *
0x180018ed1  lea     rax, [rbp+7+var_6C]
0x180018ed5  mov     [rsp+100h+var_D0], rax; int *
0x180018eda  lea     rax, [rsp+100h+var_90]
0x180018edf  mov     [rsp+100h+var_D8], rax; struct _APPLUGIN_USER_INFO **
0x180018ee4  mov     rax, [rbp+7+arg_38]
0x180018ee8  mov     [rsp+100h+var_E0], rax; struct _SCARD_PIN *
0x180018eed  call    ?CachedLogon@@YAJPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@PEAU_DPAPI_DECODED_AUTH_DATA@@PEAU_CloudAPCache@@PEAU_SCARD_PIN@@PEAPEAU_APPLUGIN_USER_INFO@@PEAH6PEA_N7PEAU_AP_BLOB@@PEAU_tagCacheNodeIdentifier@@@Z; CachedLogon(_ApPluginPkg *,_USER_CACHE_ENTRY *,_DPAPI_DECODED_AUTH_DATA *,_CloudAPCache *,_SCARD_PIN *,_APPLUGIN_USER_INFO * *,int *,int *,bool *,bool *,_AP_BLOB *,_tagCacheNodeIdentifier *)
0x180018ef2  mov     r14d, eax
0x180018ef5  test    eax, eax
0x180018ef7  js      loc_180018F98
0x180018efd  cmp     cs:?g_ulPlatformId@@3KA, 3; ulong g_ulPlatformId
0x180018f04  jnz     loc_180019056
0x180018f0a  mov     r15, [rbp+7+arg_8]
0x180018f0e  test    byte ptr [r15+0A0h], 40h
0x180018f16  jz      loc_180019056
0x180018f1c  cmp     dword ptr [rdi], 3
0x180018f1f  jz      loc_180019056
0x180018f25  lea     rcx, [rbp+7+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180018f29  call    cs:__imp_GetSystemTimeAsFileTime
0x180018f2f  mov     rcx, [rsp+100h+var_90]
0x180018f34  lea     rdx, [rbp+7+SystemTimeAsFileTime]; lpFileTime2
0x180018f38  add     rcx, 68h ; 'h'; lpFileTime1
0x180018f3c  call    cs:__imp_CompareFileTime
0x180018f42  test    eax, eax
0x180018f44  jns     loc_180019056
0x180018f4a  mov     rax, [rbp+7+arg_70]
0x180018f51  mov     byte ptr [rax], 1
0x180018f54  jmp     loc_180019056
0x180018f59  mov     rcx, rsi; char *
0x180018f5c  mov     r14d, 0C000030Dh
0x180018f62  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
  ... truncated ...
```
