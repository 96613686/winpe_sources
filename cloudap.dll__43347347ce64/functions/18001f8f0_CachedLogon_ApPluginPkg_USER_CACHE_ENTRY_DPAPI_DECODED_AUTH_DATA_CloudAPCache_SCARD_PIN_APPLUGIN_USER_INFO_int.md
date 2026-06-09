# CachedLogon(_ApPluginPkg *,_USER_CACHE_ENTRY *,_DPAPI_DECODED_AUTH_DATA *,_CloudAPCache *,_SCARD_PIN *,_APPLUGIN_USER_INFO * *,int *,int *,bool *,bool *,_AP_BLOB *,_tagCacheNodeIdentifier *)

- ea: `0x18001f8f0`
- end: `0x1800209bc`
- name: `?CachedLogon@@YAJPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@PEAU_DPAPI_DECODED_AUTH_DATA@@PEAU_CloudAPCache@@PEAU_SCARD_PIN@@PEAPEAU_APPLUGIN_USER_INFO@@PEAH6PEA_N7PEAU_AP_BLOB@@PEAU_tagCacheNodeIdentifier@@@Z`
- size: `4300`
- prototype: `__int64 __fastcall(struct _ApPluginPkg *, struct _USER_CACHE_ENTRY *, struct _DPAPI_DECODED_AUTH_DATA *, struct _CloudAPCache *, struct _SCARD_PIN *, struct _APPLUGIN_USER_INFO **, int *, int *, bool *, bool *, struct _AP_BLOB *, struct _tagCacheNodeIdentifier *)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180018a20`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000ce50`
- `0x18000fb70`
- `0x18000fd50`
- `0x18001e130`
- `0x18001f8f0`
- `0x1800239f0`
- `0x1800293f0`
- `0x18002b28c`
- `0x18002b6dc`
- `0x18002ce50`
- `0x18003f220`
- `0x18003faf4`
- `0x180042410`
- `0x18004d570`
- `0x180051130`
- `0x1800513f4`
- `0x18005291c`
- `0x18005f6b0`
- `0x1800641e4`
- `0x18007f9f0`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fde9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800206a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fde9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800206a1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001fddf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180020697`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001fddf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180020697`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020852`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020852`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002082b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002082b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002040d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002040d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020895`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020895`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800203ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800203ff`
- `ntdll!RtlLengthSid` at `0x18002019b`
- `ntdll!RtlLengthSid` at `0x18002019b`
- `ntdll!RtlEqualSid` at `0x18002013c`
- `ntdll!RtlEqualSid` at `0x18002013c`

## string_xrefs

- `0x18001fa10`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001fa8b`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001faa7`: `PublicCacheData`
- `0x18001fab3`: `GetLogonPublicCacheForUser`
- `0x18001fc7f`: `GetLogonPublicCacheForUser`
- `0x18001fbb1`: `GetRawCacheNode`
- `0x18001fb87`: `FIDOValidatePublicCacheData`
- `0x18001fa4c`: `ImpersonateClient`
- `0x18001fef2`: `Plugin doesn't support cached logon`
- `0x18001fd5b`: `UnlockCloudAPCacheNodeData`
- `0x18001fe15`: `SetThreadToken`
- `0x180020686`: `SetThreadToken`
- `0x18001fe6b`: `Cached logon is disabled`
- `0x180020182`: `Inconsistent SID`
- `0x180020612`: `CredKey mismatch between cache and current cred key`
- `0x1800205d2`: `CredKey mismatch between cache node and current cred key`
- `0x180020352`: `Cached Blobs do not match`

## pseudocode

```c
__int64 __fastcall CachedLogon(
        struct _ApPluginPkg *a1,
        struct _USER_CACHE_ENTRY *a2,
        struct _DPAPI_DECODED_AUTH_DATA *a3,
        struct _CloudAPCache *a4,
        struct _SCARD_PIN *a5,
        struct _APPLUGIN_USER_INFO **a6,
        int *a7,
        int *a8,
        bool *a9,
        bool *a10,
        struct _AP_BLOB *a11,
        struct _tagCacheNodeIdentifier *a12)
{
  struct _APPLUGIN_USER_INFO *v13; // r14
  struct _DPAPI_DECODED_AUTH_DATA *v14; // r11
  struct _SCARD_PIN *v15; // r15
  int LogonCacheForUser; // esi
  const char *v17; // rbx
  char v18; // al
  const char *v19; // rcx
  bool v20; // zf
  const char *v21; // rbx
  __int64 v22; // r14
  const char *v23; // rax
  const char *v24; // rax
  const char *v25; // rax
  int v26; // r14d
  const char *v27; // rax
  __int64 v28; // r8
  const char *v29; // rax
  const char *v30; // r9
  int ScardPinFromCurrentUserLogonSession; // esi
  const char *v32; // rax
  struct _CloudAPCache *v33; // r15
  const char *v34; // rax
  const char *v35; // r9
  signed int LastError; // eax
  const char *v37; // rax
  const char *v38; // r9
  int v39; // ecx
  __int64 v40; // rdx
  int *v41; // r8
  struct _ApPluginPkg *v42; // r10
  __int64 (__fastcall *v43)(_QWORD, char *, __int128 *, struct _APPLUGIN_USER_INFO **, unsigned int *, int *, struct _CloudAPCache **); // rax
  const char *v44; // r9
  char v45; // al
  const char *v46; // rcx
  bool v47; // zf
  const char *v48; // r9
  struct _APPLUGIN_USER_INFO *v49; // rcx
  struct _CloudAPCache *v50; // r8
  char v51; // al
  unsigned int i; // r9d
  __int64 v53; // rax
  __int64 v54; // rdx
  _BYTE *v55; // rcx
  const char *v56; // r9
  char v57; // al
  const char *v58; // rcx
  bool v59; // zf
  _BYTE *v60; // rax
  struct _APPLUGIN_USER_INFO *v61; // r12
  void *v62; // rdx
  void *v63; // rcx
  char v64; // al
  size_t v65; // rsi
  void *v66; // rax
  const char *v67; // r9
  char v68; // cl
  const char *v69; // rdx
  bool v70; // zf
  unsigned int *v71; // r14
  unsigned int v72; // ecx
  unsigned int v73; // edx
  unsigned int v74; // r8d
  struct _APPLUGIN_USER_INFO *v75; // r8
  struct _ApPluginPkg *v76; // r12
  char v77; // al
  _DWORD *v78; // rdx
  char v79; // r15
  char v80; // al
  char v81; // al
  char v82; // al
  _BYTE *v83; // rax
  __int64 v84; // rcx
  _DWORD *v85; // rcx
  _QWORD *v86; // rcx
  __int128 v87; // xmm0
  void *v88; // rax
  _QWORD *v89; // rax
  struct _APPLUGIN_USER_INFO *v90; // rcx
  char v91; // al
  char v92; // al
  char v93; // al
  HANDLE v94; // r14
  signed int v95; // eax
  unsigned int v96; // r14d
  char v97; // al
  const char *v98; // rcx
  bool v99; // zf
  __int64 v100; // rdx
  __int64 v101; // rcx
  struct _DPAPI_DECODED_AUTH_DATA *v102; // rax
  HLOCAL v103; // rbx
  struct _SCARD_PIN *v104; // rbx
  _BYTE *v105; // rax
  __int64 v106; // rcx
  struct _CloudAPCache *v107; // rcx
  unsigned int v108; // r9d
  __int64 v109; // rax
  __int64 v110; // r8
  _BYTE *v111; // rdx
  ULONG UserDataCount[2]; // [rsp+28h] [rbp-E0h]
  ULONG UserDataCounta[2]; // [rsp+28h] [rbp-E0h]
  ULONG UserDataCountb[2]; // [rsp+28h] [rbp-E0h]
  struct _SCARD_PIN *UserDataCountd; // [rsp+28h] [rbp-E0h]
  ULONG UserDataCountc[2]; // [rsp+28h] [rbp-E0h]
  const char *UserData; // [rsp+30h] [rbp-D8h]
  const char *UserDataa; // [rsp+30h] [rbp-D8h]
  unsigned int v120[2]; // [rsp+48h] [rbp-C0h] BYREF
  struct _CloudAPCache *v121; // [rsp+50h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-B0h] BYREF
  struct _DPAPI_DECODED_AUTH_DATA *v123; // [rsp+60h] [rbp-A8h] BYREF
  HANDLE Token; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v125; // [rsp+70h] [rbp-98h] BYREF
  struct _APPLUGIN_USER_INFO *v126; // [rsp+78h] [rbp-90h] BYREF
  struct _APPLUGIN_USER_INFO *v127; // [rsp+80h] [rbp-88h]
  void *v128; // [rsp+88h] [rbp-80h]
  unsigned __int8 *v129; // [rsp+90h] [rbp-78h] BYREF
  struct _ApPluginPkg *v130; // [rsp+98h] [rbp-70h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A0h] [rbp-68h] BYREF
  FILETIME FileTime2; // [rsp+A8h] [rbp-60h] BYREF
  HLOCAL v133; // [rsp+B0h] [rbp-58h] BYREF
  struct _SCARD_PIN *v134; // [rsp+B8h] [rbp-50h] BYREF
  struct _CloudAPCache *v135; // [rsp+C0h] [rbp-48h]
  __int64 v136; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v137; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v138; // [rsp+E0h] [rbp-28h] BYREF
  int *v139; // [rsp+F0h] [rbp-18h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+F8h] [rbp-10h] BYREF
  bool *v141; // [rsp+108h] [rbp+0h]
  struct _AP_BLOB *v142; // [rsp+110h] [rbp+8h]
  __int128 v143; // [rsp+118h] [rbp+10h] BYREF
  UUID Uuid; // [rsp+128h] [rbp+20h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v145; // [rsp+138h] [rbp+30h] BYREF
  char *v146; // [rsp+148h] [rbp+40h]
  int v147; // [rsp+150h] [rbp+48h]
  int v148; // [rsp+154h] [rbp+4Ch]
  struct _DPAPI_DECODED_AUTH_DATA **v149; // [rsp+158h] [rbp+50h]
  __int64 v150; // [rsp+160h] [rbp+58h]
  __int64 *v151; // [rsp+168h] [rbp+60h]
  __int64 v152; // [rsp+170h] [rbp+68h]
  __int64 *v153; // [rsp+178h] [rbp+70h]
  __int64 v154; // [rsp+180h] [rbp+78h]

  v13 = (struct _APPLUGIN_USER_INFO *)a10;
  v121 = a4;
  v14 = a3;
  v15 = a5;
  *(_QWORD *)&EventDescriptor.Id = a12;
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  *a9 = 0;
  v123 = a3;
  Uuid = stru_180085DB8;
  *a10 = 0;
  v20 = *(_DWORD *)a3 == 4;
  v130 = a1;
  v136 = (__int64)a6;
  v139 = a8;
  v141 = a9;
  v126 = (struct _APPLUGIN_USER_INFO *)a10;
  v142 = a11;
  LOBYTE(v120[0]) = 0;
  FileTime2 = 0;
  SystemTimeAsFileTime = 0;
  v120[1] = 0;
  v138 = 0;
  v128 = 0;
  hMem = 0;
  v127 = 0;
  Token = 0;
  v143 = 0;
  v133 = 0;
  v129 = 0;
  v134 = 0;
  v135 = 0;
  if ( v20 )
  {
    LogonCacheForUser = ImpersonateClient(&Token);
    if ( LogonCacheForUser )
    {
      v17 = "";
      while ( 1 )
      {
        v18 = *(v17 - 1);
        v19 = v17--;
        v20 = v18 == 92;
        if ( v18 == 92 )
          break;
        if ( v17 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v20 = v18 == 92;
          break;
        }
      }
      if ( v20 )
        v17 = v19;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)LogonCacheForUser, v17, 2828, "ImpersonateClient", &Class);
      goto LABEL_183;
    }
    a1 = v130;
    v14 = v123;
    LOBYTE(v120[0]) = 1;
  }
  v21 = "";
  if ( *(_DWORD *)v14 == 7 )
  {
    LogonCacheForUser = _GetLogonCacheForUser(
                          *((const unsigned __int16 **)a1 + 43),
                          (const unsigned __int16 *)a2 + 52,
                          L"PublicCacheData",
                          (struct _CloudAPCache **)&v133);
    if ( LogonCacheForUser < 0 )
    {
      v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)LogonCacheForUser, v27, 2880, v28, &Class);
      v26 = LogonCacheForUser;
LABEL_22:
      v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      UserDataCount[0] = 2885;
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        (unsigned int)LogonCacheForUser,
        v29,
        *(_QWORD *)UserDataCount,
        "Failed Signature count validation",
        &Class);
      if ( v26 != -1073741801 && v26 != -1073741670 )
        LogonCacheForUser = -1073741718;
      v30 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      UserDataCounta[0] = 2892;
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        (unsigned int)LogonCacheForUser,
        v30,
        *(_QWORD *)UserDataCounta,
        "GetLogonPublicCacheForUser",
        &Class);
      goto LABEL_172;
    }
    LODWORD(v137) = 7;
    v22 = *((_QWORD *)v123 + 1);
    DWORD1(v137) = *(_DWORD *)(v22 + 20);
    *((_QWORD *)&v137 + 1) = v22 + *(unsigned int *)(v22 + 16);
    LogonCacheForUser = GetRawCacheNode(
                          (struct _CloudAPCache *)v133,
                          (struct _tagCacheNodeIdentifier *)&v137,
                          &v129,
                          &v120[1]);
    if ( LogonCacheForUser < 0 )
    {
      v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)LogonCacheForUser, v25, 2875, "GetRawCacheNode", &Class);
    }
    else
    {
      LogonCacheForUser = FIDOValidatePublicCacheData(v129, v120[1]);
      if ( LogonCacheForUser < 0 )
      {
        v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          (unsigned int)LogonCacheForUser,
          v24,
          2870,
          "FIDOValidatePublicCacheData",
          &Class);
      }
      else if ( *((_QWORD *)v129 + 2) >= *(_QWORD *)(v22 + 8) )
      {
        LogonCacheForUser = -1073741790;
        v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225506LL, v23, 2864, "Potential replay of creds", &Class);
        CloudAPProvider::CloudApFIDOCredReplay();
      }
    }
    v26 = LogonCacheForUser;
    if ( LogonCacheForUser < 0 )
      goto LABEL_22;
    v13 = v126;
    v14 = v123;
  }
  if ( *(_DWORD *)v14 == 4 && !a5 )
  {
    ScardPinFromCurrentUserLogonSession = GetScardPinFromCurrentUserLogonSession(a2, &v134);
    if ( !ScardPinFromCurrentUserLogonSession
      || (v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp"),
          UserDataCount[0] = 2901,
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            (unsigned int)ScardPinFromCurrentUserLogonSession,
            v32,
            *(_QWORD *)UserDataCount,
            "GetScardPinFromCurrentUserLogonSession before Unlock",
            &Class),
          ScardPinFromCurrentUserLogonSession >= 0) )
    {
      v15 = v134;
    }
  }
  UserDataCountd = v15;
  v33 = v121;
  LogonCacheForUser = UnlockCloudAPCacheNodeData(
                        v121,
                        *(_DWORD *)v123,
                        *((unsigned __int8 **)v123 + 1),
                        *((_DWORD *)v123 + 1),
                        UserDataCountd,
                        (struct _tagCacheNodeIdentifier *)&v138,
                        (struct _CloudAPCacheNodeData2 **)&hMem);
  if ( LogonCacheForUser < 0 )
  {
    v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    UserDataCountb[0] = 2917;
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%ws",
      (unsigned int)LogonCacheForUser,
      v34,
      *(_QWORD *)UserDataCountb,
      "UnlockCloudAPCacheNodeData",
      &Class);
    if ( LogonCacheForUser != -1073741801
      && LogonCacheForUser != -1073741670
      && ((unsigned int)(*(_DWORD *)v123 - 4) > 1 || (unsigned int)(LogonCacheForUser + 1073740928) > 1) )
    {
      LogonCacheForUser = -1073741718;
    }
    v35 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    UserDataCountc[0] = 2927;
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%ws",
      (unsigned int)LogonCacheForUser,
      v35,
      *(_QWORD *)UserDataCountc,
      "UnlockCloudAPCacheNodeData",
      &Class);
    goto LABEL_172;
  }
  if ( LOBYTE(v120[0]) )
  {
    if ( !SetThreadToken(0, Token) )
    {
      LastError = GetLastError();
      LogonCacheForUser = LastError;
      if ( LastError > 0 )
        LogonCacheForUser = (unsigned __int16)LastError | 0xC0070000;
      v37 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      UserDataCountb[0] = 2936;
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        (unsigned int)LogonCacheForUser,
        v37,
        *(_QWORD *)UserDataCountb,
        "SetThreadToken",
        &Class);
      goto LABEL_173;
    }
    LOBYTE(v120[0]) = 0;
  }
  if ( (*((_BYTE *)hMem + 8) & 4) != 0 )
  {
    LogonCacheForUser = -1073741557;
    v38 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    UserDataCountb[0] = 2944;
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%ws",
      3221225739LL,
      v38,
      *(_QWORD *)UserDataCountb,
      "Cached logon is disabled",
      &Class);
    goto LABEL_172;
  }
  v39 = *((_DWORD *)hMem + 6);
  v40 = *((_QWORD *)hMem + 4);
  v41 = v139;
  v42 = v130;
  *a7 = 0;
  v120[1] = 0;
  *v41 = 0;
  v121 = 0;
  v126 = 0;
  v43 = (__int64 (__fastcall *)(_QWORD, char *, __int128 *, struct _APPLUGIN_USER_INFO **, unsigned int *, int *, struct _CloudAPCache **))*((_QWORD *)v42 + 23);
  v137 = 0;
  if ( !v43 )
  {
    LogonCacheForUser = -2146893039;
    v44 = "";
    while ( 1 )
    {
      v45 = *(v44 - 1);
      v46 = v44--;
      v47 = v45 == 92;
      if ( v45 == 92 )
        break;
      if ( v44 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v47 = v45 == 92;
        break;
      }
    }
    UserData = "Plugin doesn't support cached logon";
    UserDataCountb[0] = 2007;
LABEL_63:
    if ( v47 )
      v44 = v46;
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%ws",
      (unsigned int)LogonCacheForUser,
      v44,
      *(_QWORD *)UserDataCountb,
      UserData,
      &Class);
    goto LABEL_66;
  }
  LODWORD(v137) = v39;
  *((_QWORD *)&v137 + 1) = v40;
  LogonCacheForUser = v43(*((_QWORD *)v42 + 1), (char *)v33 + 4, &v137, &v126, &v120[1], v41, &v121);
  if ( LogonCacheForUser >= 0 )
  {
    v49 = v126;
    if ( v126 && *((_QWORD *)v126 + 2) )
    {
      v50 = 0;
      *a7 = v120[1];
      LogonCacheForUser = 0;
      v135 = v121;
      v121 = 0;
      v127 = v49;
      v126 = 0;
      goto LABEL_67;
    }
    LogonCacheForUser = -1073741715;
    v44 = "";
    while ( 1 )
    {
      v51 = *(v44 - 1);
      v46 = v44--;
      v47 = v51 == 92;
      if ( v51 == 92 )
        break;
      if ( v44 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v47 = v51 == 92;
        break;
      }
    }
    UserData = "UserInfo is invalid";
    UserDataCountb[0] = 2031;
    goto LABEL_63;
  }
  v126 = 0;
  v48 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
  UserDataCountb[0] = 2024;
  WPPTraceLogA(
    0,
    "0x%08x %s:%u : %s:%ws",
    (unsigned int)LogonCacheForUser,
    v48,
    *(_QWORD *)UserDataCountb,
    "ValidateUserInfo",
    &Class);
LABEL_66:
  v50 = v121;
LABEL_67:
  if ( v50 )
  {
    for ( i = 0; i < *(_DWORD *)v50; ++i )
    {
      v53 = 32LL * i;
      v54 = *(unsigned int *)((char *)v50 + v53 + 24);
      v55 = *(_BYTE **)((char *)v50 + v53 + 32);
      if ( *(_DWORD *)((char *)v50 + v53 + 24) )
      {
        do
        {
          *v55++ = 0;
          --v54;
        }
        while ( v54 );
        v50 = v121;
      }
    }
    ((void (__fastcall *)(struct _CloudAPCache *))g_pLsaFunctionTable->FreeLsaHeap)(v50);
    v121 = 0;
  }
  FreeUserInfo(v126);
  if ( LogonCacheForUser )
  {
    v56 = "";
    while ( 1 )
    {
      v57 = *(v56 - 1);
      v58 = v56--;
      v59 = v57 == 92;
      if ( v57 == 92 )
        break;
      if ( v56 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v59 = v57 == 92;
        break;
      }
    }
    UserDataa = "ValidateUserInfo";
    UserDataCountb[0] = 2956;
LABEL_169:
    if ( v59 )
      v56 = v58;
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%ws",
      (unsigned int)LogonCacheForUser,
      v56,
      *(_QWORD *)UserDataCountb,
      UserDataa,
      &Class);
    goto LABEL_172;
  }
  if ( (*((_DWORD *)v127 + 32) & 2) != 0 )
  {
    LODWORD(v125) = RemoveCloudAPCacheNode(v33, 1u, 0, 0);
    CloudAPProvider::CloudApCachePasswordRemoved<long &>((int *)&v125);
  }
  *(_BYTE *)v13 = v135 != 0;
  v60 = hMem;
  if ( (*((_BYTE *)hMem + 8) & 1) != 0 )
    *a7 = 1;
  if ( (v60[8] & 2) != 0 )
    *v141 = 1;
  v61 = v127;
  v62 = (void *)*((_QWORD *)a2 + 30);
  v63 = (void *)*((_QWORD *)v127 + 2);
  if ( v62 )
  {
    if ( !RtlEqualSid(v63, v62) )
    {
      LogonCacheForUser = -1073741152;
      v56 = "";
      while ( 1 )
      {
        v64 = *(v56 - 1);
        v58 = v56--;
        v59 = v64 == 92;
        if ( v64 == 92 )
          break;
        if ( v56 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v59 = v64 == 92;
          break;
        }
      }
      UserDataa = "Inconsistent SID";
      UserDataCountb[0] = 2983;
      goto LABEL_169;
    }
  }
  else
  {
    v65 = RtlLengthSid(v63);
    v66 = (void *)((__int64 (__fastcall *)(size_t))g_pLsaFunctionTable->AllocateLsaHeap)(v65);
    v128 = v66;
    if ( !v66 )
    {
      LogonCacheForUser = -1073741801;
      v67 = "";
      while ( 1 )
      {
        v68 = *(v67 - 1);
        v69 = v67--;
        v70 = v68 == 92;
        if ( v68 == 92 )
          break;
        if ( v67 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v70 = v68 == 92;
          break;
        }
      }
      if ( v70 )
        v67 = v69;
      UserDataCountb[0] = 2993;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v67, *(_QWORD *)UserDataCountb, "AllocateLsaHeap", &Class);
      goto LABEL_172;
    }
    memcpy_0(v66, *((const void **)v61 + 2), v65);
  }
  v71 = (unsigned int *)*((_QWORD *)hMem + 2);
  v72 = *v71;
  if ( *v71 > *((_DWORD *)hMem + 3) || (v73 = v71[2], v73 > v72) || (v74 = v73 + v71[3], v74 < v73) || v74 > v72 )
  {
    LogonCacheForUser = -1073281680;
    v56 = "";
    while ( 1 )
    {
      v93 = *(v56 - 1);
      v58 = v56--;
      v59 = v93 == 92;
      if ( v93 == 92 )
        break;
      if ( v56 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v59 = v93 == 92;
        break;
      }
    }
    UserDataa = "DPAPI Cred key is corrupted";
    UserDataCountb[0] = 3006;
    goto LABEL_169;
  }
  v75 = v61;
  v76 = v130;
  LogonCacheForUser = GetCurrentCredKeyIdForUser(v130, a2, v75, v33, &Uuid);
  if ( LogonCacheForUser )
  {
    v56 = "";
    while ( 1 )
    {
      v77 = *(v56 - 1);
      v58 = v56--;
      v59 = v77 == 92;
      if ( v77 == 92 )
        break;
      if ( v56 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v59 = v77 == 92;
        break;
      }
    }
    UserDataa = "GetCurrentCredKeyIdForUser";
    UserDataCountb[0] = 3016;
    goto LABEL_169;
  }
  if ( *(_QWORD *)&Uuid.Data1 != *(_QWORD *)((char *)v33 + 4) || *(_QWORD *)Uuid.Data4 != *(_QWORD *)((char *)v33 + 12) )
  {
    LogonCacheForUser = -1073741788;
    v56 = "";
    while ( 1 )
    {
      v92 = *(v56 - 1);
      v58 = v56--;
      v59 = v92 == 92;
      if ( v92 == 92 )
        break;
      if ( v56 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v59 = v92 == 92;
        break;
      }
    }
    UserDataa = "CredKey mismatch between cache and current cred key";
    UserDataCountb[0] = 3021;
    goto LABEL_169;
  }
  if ( *(_QWORD *)&Uuid.Data1 != *((_QWORD *)v71 + 2) || *(_QWORD *)Uuid.Data4 != *((_QWORD *)v71 + 3) )
  {
    LogonCacheForUser = -1073741788;
    v56 = "";
    while ( 1 )
    {
      v91 = *(v56 - 1);
      v58 = v56--;
      v59 = v91 == 92;
      if ( v91 == 92 )
        break;
      if ( v56 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v59 = v91 == 92;
        break;
      }
    }
    UserDataa = "CredKey mismatch between cache node and current cred key";
    UserDataCountb[0] = 3027;
    goto LABEL_169;
  }
  v78 = (_DWORD *)*((_QWORD *)a2 + 33);
  if ( v78 )
  {
    if ( *v71 != *v78 || (v79 = 0, memcmp_0(v71, v78, *v71)) )
    {
      LogonCacheForUser = -1073741788;
      v56 = "";
      while ( 1 )
      {
        v80 = *(v56 - 1);
        v58 = v56--;
        v59 = v80 == 92;
        if ( v80 == 92 )
          break;
        if ( v56 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v59 = v80 == 92;
          break;
        }
      }
      UserDataa = "Cached Blobs do not match";
      UserDataCountb[0] = 3040;
      goto LABEL_169;
    }
  }
  else
  {
    v79 = 1;
  }
  if ( (*((_DWORD *)v76 + 40) & 0x22) == 0 )
  {
    LogonCacheForUser = GetKeyBlobForUser(
                          *((const unsigned __int16 **)v76 + 43),
                          (const unsigned __int16 *)a2 + 52,
                          *((const unsigned __int16 **)a2 + 11),
                          &Uuid,
                          (struct _AP_BLOB *)&v143,
                          &FileTime2);
    if ( LogonCacheForUser )
    {
      v56 = "";
      while ( 1 )
      {
        v81 = *(v56 - 1);
        v58 = v56--;
        v59 = v81 == 92;
        if ( v81 == 92 )
          break;
        if ( v56 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v59 = v81 == 92;
          break;
        }
      }
      UserDataa = "GetKeyBlobForUser";
      UserDataCountb[0] = 3068;
      goto LABEL_169;
    }
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( CompareFileTime(&SystemTimeAsFileTime, &FileTime2) > 0
      && (unsigned int)((*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&FileTime2) / 0x989680uLL) >= 0x76A700 )
    {
      CloudAPProvider::CloudAPLogonCacheUserKeyExpired<_GUID &>((__int128 *)&Uuid);
      *v139 = 1;
    }
  }
  if ( v142 )
  {
    if ( *(_QWORD *)&EventDescriptor.Id )
    {
      LogonCacheForUser = DuplicateCredentialData(a2, v142, *(struct _tagCacheNodeIdentifier **)&EventDescriptor.Id);
      if ( LogonCacheForUser )
      {
        v56 = "";
        while ( 1 )
        {
          v82 = *(v56 - 1);
          v58 = v56--;
          v59 = v82 == 92;
          if ( v82 == 92 )
            break;
          if ( v56 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
          {
            v59 = v82 == 92;
            break;
          }
        }
        UserDataa = "DuplicateCredentialData";
        UserDataCountb[0] = 3089;
        goto LABEL_169;
      }
    }
  }
  v83 = (_BYTE *)*((_QWORD *)a2 + 36);
  if ( v83 )
  {
    v84 = *((unsigned int *)a2 + 70);
    if ( *((_DWORD *)a2 + 70) )
    {
      do
      {
        *v83++ = 0;
        --v84;
      }
      while ( v84 );
    }
    ((void (__fastcall *)(_QWORD))g_pLsaFunctionTable->FreeLsaHeap)(*((_QWORD *)a2 + 36));
  }
  v85 = hMem;
  LogonCacheForUser = 0;
  *((_DWORD *)a2 + 70) = *((_DWORD *)hMem + 6);
  v85[6] = 0;
  v86 = hMem;
  *((_QWORD *)a2 + 36) = *((_QWORD *)hMem + 4);
  v86[4] = 0;
  if ( *((_QWORD *)a2 + 38) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v87 = v138;
  v88 = v128;
  v138 = 0u;
  *(_OWORD *)((char *)a2 + 296) = v87;
  if ( v88 )
  {
    *((_QWORD *)a2 + 30) = v88;
    v128 = 0;
  }
  if ( v79 )
  {
    v89 = hMem;
    *((_QWORD *)a2 + 33) = v71;
    v89[2] = 0;
    *((_DWORD *)hMem + 3) = 0;
  }
  v90 = v127;
  v127 = 0;
  *(_QWORD *)v136 = v90;
LABEL_172:
  if ( !LOBYTE(v120[0]) )
  {
LABEL_183:
    v94 = Token;
    goto LABEL_184;
  }
LABEL_173:
  v94 = Token;
  if ( !SetThreadToken(0, Token) )
  {
    v95 = GetLastError();
    v96 = v95;
    if ( v95 > 0 )
      v96 = (unsigned __int16)v95 | 0xC0070000;
    while ( 1 )
    {
      v97 = *(v21 - 1);
      v98 = v21--;
      v99 = v97 == 92;
      if ( v97 == 92 )
        break;
      if ( v21 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v99 = v97 == 92;
        break;
      }
    }
    if ( v99 )
      v21 = v98;
    UserDataCountb[0] = 3143;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v96, v21, *(_QWORD *)UserDataCountb, "SetThreadToken", &Class);
    if ( LogonCacheForUser >= 0 )
      LogonCacheForUser = v96;
    goto LABEL_183;
  }
LABEL_184:
  v101 = *((_QWORD *)CloudAPProvider::Instance() + 1);
  if ( *(_DWORD *)v101 > 5u )
  {
    v100 = *(_QWORD *)(v101 + 24);
    if ( (*(_QWORD *)(v101 + 16) & 0x400000000000LL) != 0 && (v100 & 0x400000000000LL) == v100 )
    {
      v102 = v123;
      EventDescriptor.Keyword = 0x400000000000LL;
      v136 = 0x2000000;
      LODWORD(v123) = LogonCacheForUser;
      LODWORD(v125) = *(_DWORD *)v102;
      v153 = &v136;
      v151 = &v125;
      v149 = &v123;
      *(_DWORD *)&EventDescriptor.Level = 5;
      v145.Ptr = *(_QWORD *)(v101 + 8);
      v154 = 8;
      v152 = 4;
      v150 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      v145.Size = *(unsigned __int16 *)v145.Ptr;
      v146 = byte_18008F013;
      v145.Reserved = 2;
      v147 = 49;
      v148 = 1;
      LODWORD(Token) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v101 + 32), &EventDescriptor, 0, 0, 5u, &v145);
    }
  }
  if ( *((_QWORD *)&v143 + 1) )
    ((void (__fastcall *)(_QWORD, __int64))g_pLsaFunctionTable->FreeLsaHeap)(*((_QWORD *)&v143 + 1), v100);
  if ( v94 )
    CloseHandle(v94);
  FreeCloudAPCache(v133);
  v103 = hMem;
  if ( hMem )
  {
    FreeCloudAPCacheNodeDataContents((struct _CloudAPCacheNodeData2 *)hMem);
    if ( g_pLsaFunctionTable )
      ((void (__fastcall *)(HLOCAL))g_pLsaFunctionTable->FreeLsaHeap)(v103);
    else
      LocalFree(v103);
  }
  FreeUserInfo(v127);
  v104 = v134;
  if ( v134 )
  {
    v105 = *(_BYTE **)v134;
    if ( *(_QWORD *)v134 )
    {
      v106 = *((unsigned int *)v134 + 2);
      if ( *((_DWORD *)v134 + 2) )
      {
        do
        {
          *v105++ = 0;
          --v106;
        }
        while ( v106 );
      }
      ((void (__fastcall *)(_QWORD))g_pLsaFunctionTable->FreeLsaHeap)(*(_QWORD *)v104);
    }
    ((void (__fastcall *)(struct _SCARD_PIN *))g_pLsaFunctionTable->FreeLsaHeap)(v104);
  }
  if ( v128 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( *((_QWORD *)&v138 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v107 = v135;
  if ( v135 )
  {
    v108 = 0;
    if ( *(_DWORD *)v135 )
    {
      do
      {
        v109 = 32LL * v108;
        v110 = *(unsigned int *)((char *)v107 + v109 + 24);
        v111 = *(_BYTE **)((char *)v107 + v109 + 32);
        if ( *(_DWORD *)((char *)v107 + v109 + 24) )
        {
          do
          {
            *v111++ = 0;
            --v110;
          }
          while ( v110 );
        }
        ++v108;
      }
      while ( v108 < *(_DWORD *)v107 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  if ( v129 )
    ((void (__fastcall *)(unsigned __int8 *))g_pLsaFunctionTable->FreeLsaHeap)(v129);
  return (unsigned int)LogonCacheForUser;
}

```

## disassembly

```asm
0x18001f8f0  mov     r11, rsp
0x18001f8f3  push    rbp
0x18001f8f4  push    rsi
0x18001f8f5  lea     rbp, [r11-0D8h]
0x18001f8fc  sub     rsp, 1C8h
0x18001f903  mov     rax, cs:__security_cookie
0x18001f90a  xor     rax, rsp
0x18001f90d  mov     [rbp+0D0h+var_50], rax
0x18001f914  movups  xmm0, xmmword ptr cs:stru_180085DB8.Data1
0x18001f91b  mov     r10, [rbp+0D0h+arg_28]
0x18001f922  mov     rax, [rbp+0D0h+arg_40]
0x18001f929  mov     [r11-18h], rbx
0x18001f92d  mov     [r11-20h], rdi
0x18001f931  mov     [r11-28h], r12
0x18001f935  mov     r12, [rbp+0D0h+arg_30]
0x18001f93c  mov     [r11-30h], r13
0x18001f940  mov     r13, rdx
0x18001f943  mov     rdx, [rbp+0D0h+arg_38]
0x18001f94a  mov     [r11-38h], r14
0x18001f94e  mov     r14, [rbp+0D0h+arg_48]
0x18001f955  mov     [rsp+1D0h+var_188], r9
0x18001f95a  mov     r9, [rbp+0D0h+arg_58]
0x18001f961  mov     [r11-40h], r15
0x18001f965  mov     r11, r8
0x18001f968  mov     r15, [rbp+0D0h+arg_20]
0x18001f96f  mov     qword ptr [rbp+0D0h+EventDescriptor.Id], r9
0x18001f973  xor     r9d, r9d
0x18001f976  mov     [r10], r9
0x18001f979  mov     [r12], r9d
0x18001f97d  mov     [rdx], r9d
0x18001f980  mov     [rax], r9b
0x18001f983  mov     [rsp+1D0h+var_178], r8
0x18001f988  mov     r8, [rbp+0D0h+arg_50]
0x18001f98f  movups  xmmword ptr [rbp+0D0h+Uuid.Data1], xmm0
0x18001f993  mov     [r14], r9b
0x18001f996  cmp     dword ptr [r11], 4
0x18001f99a  xorps   xmm0, xmm0
0x18001f99d  mov     [rbp+0D0h+var_140], rcx
0x18001f9a1  mov     [rbp+0D0h+var_110], r10
0x18001f9a5  mov     [rbp+0D0h+var_E8], rdx
0x18001f9a9  mov     [rbp+0D0h+var_D0], rax
0x18001f9ad  mov     [rsp+1D0h+var_160], r14
0x18001f9b2  mov     [rbp+0D0h+var_C8], r8
0x18001f9b6  mov     byte ptr [rsp+1D0h+var_190], 0
0x18001f9bb  mov     qword ptr [rbp+0D0h+FileTime2.dwLowDateTime], r9
0x18001f9bf  mov     qword ptr [rbp+0D0h+SystemTimeAsFileTime.dwLowDateTime], r9
0x18001f9c3  mov     [rsp+1D0h+var_190+4], r9d
0x18001f9c8  movups  [rbp+0D0h+var_F8], xmm0
0x18001f9cc  mov     [rbp+0D0h+var_150], r9
0x18001f9d0  mov     [rsp+1D0h+hMem], r9
0x18001f9d5  mov     [rsp+1D0h+var_158], r9
0x18001f9da  mov     [rsp+1D0h+Token], r9
0x18001f9df  movups  [rbp+0D0h+var_C0], xmm0
0x18001f9e3  mov     [rbp+0D0h+var_128], r9
0x18001f9e7  mov     [rbp+0D0h+var_148], r9
0x18001f9eb  mov     [rbp+0D0h+var_120], r9
0x18001f9ef  mov     [rbp+0D0h+var_118], r9
0x18001f9f3  jnz     loc_18001FA80
0x18001f9f9  lea     rcx, [rsp+1D0h+Token]; void **
0x18001f9fe  call    ?ImpersonateClient@@YAJPEAPEAX@Z; ImpersonateClient(void * *)
0x18001fa03  mov     esi, eax
0x18001fa05  test    eax, eax
0x18001fa07  jz      short loc_18001FA72
0x18001fa09  lea     rbx, aOnecoreDsExtCl_6+27h; ""
0x18001fa10  lea     rdi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001fa17  nop     word ptr [rax+rax+00000000h]
0x18001fa20  movzx   eax, byte ptr [rbx-1]
0x18001fa24  mov     rcx, rbx
0x18001fa27  dec     rbx
0x18001fa2a  cmp     al, 5Ch ; '\'
0x18001fa2c  jz      short loc_18001FA35
0x18001fa2e  cmp     rbx, rdi
0x18001fa31  ja      short loc_18001FA20
0x18001fa33  cmp     al, 5Ch ; '\'
0x18001fa35  cmovz   rbx, rcx
0x18001fa39  lea     rax, Class
0x18001fa40  mov     [rsp+30h], rax
0x18001fa45  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001fa4c  lea     rax, aImpersonatecli; "ImpersonateClient"
0x18001fa53  mov     r9, rbx
0x18001fa56  mov     [rsp+1D0h+UserData], rax
0x18001fa5b  mov     r8d, esi
0x18001fa5e  xor     ecx, ecx
0x18001fa60  mov     [rsp+1D0h+UserDataCount], 0B0Ch
0x18001fa68  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001fa6d  jmp     loc_180020705
0x18001fa72  mov     rcx, [rbp+0D0h+var_140]
0x18001fa76  mov     r11, [rsp+1D0h+var_178]
0x18001fa7b  mov     byte ptr [rsp+1D0h+var_190], 1
0x18001fa80  cmp     dword ptr [r11], 7
0x18001fa84  lea     rbx, aOnecoreDsExtCl_6+27h; ""
0x18001fa8b  lea     rdi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001fa92  jnz     loc_18001FCA5
0x18001fa98  mov     rcx, [rcx+158h]; unsigned __int16 *
0x18001fa9f  lea     rdx, [r13+68h]; unsigned __int16 *
0x18001faa3  lea     r9, [rbp+0D0h+var_128]; struct _CloudAPCache **
0x18001faa7  lea     r8, aPubliccachedat; "PublicCacheData"
0x18001faae  call    ?_GetLogonCacheForUser@@YAJPEBG00PEAPEAU_CloudAPCache@@@Z; _GetLogonCacheForUser(ushort const *,ushort const *,ushort const *,_CloudAPCache * *)
0x18001fab3  lea     r8, aGetlogonpublic; "GetLogonPublicCacheForUser"
0x18001faba  mov     esi, eax
0x18001fabc  test    eax, eax
0x18001fabe  js      loc_18001FBED
0x18001fac4  mov     rax, [rsp+1D0h+var_178]
0x18001fac9  lea     r9, [rsp+1D0h+var_190+4]; unsigned int *
0x18001face  mov     rcx, [rbp+0D0h+var_128]; struct _CloudAPCache *
0x18001fad2  lea     r8, [rbp+0D0h+var_148]; unsigned __int8 **
0x18001fad6  lea     rdx, [rbp+0D0h+var_108]; struct _tagCacheNodeIdentifier *
0x18001fada  mov     dword ptr [rbp+0D0h+var_108], 7
0x18001fae1  mov     r14, [rax+8]
0x18001fae5  mov     eax, [r14+14h]
0x18001fae9  mov     dword ptr [rbp+0D0h+var_108+4], eax
0x18001faec  mov     eax, [r14+10h]
0x18001faf0  add     rax, r14
0x18001faf3  mov     qword ptr [rbp+0D0h+var_108+8], rax
0x18001faf7  call    ?GetRawCacheNode@@YAJPEAU_CloudAPCache@@PEAU_tagCacheNodeIdentifier@@PEAPEAEPEAK@Z; GetRawCacheNode(_CloudAPCache *,_tagCacheNodeIdentifier *,uchar * *,ulong *)
0x18001fafc  mov     esi, eax
0x18001fafe  test    eax, eax
0x18001fb00  js      loc_18001FB9D
0x18001fb06  mov     edx, [rsp+1D0h+var_190+4]; unsigned int
0x18001fb0a  mov     rcx, [rbp+0D0h+var_148]; unsigned __int8 *
0x18001fb0e  call    ?FIDOValidatePublicCacheData@@YAJPEAEK@Z; FIDOValidatePublicCacheData(uchar *,ulong)
0x18001fb13  mov     esi, eax
0x18001fb15  test    eax, eax
0x18001fb17  js      short loc_18001FB73
0x18001fb19  mov     rcx, [rbp+0D0h+var_148]
0x18001fb1d  mov     rax, [r14+8]
0x18001fb21  cmp     [rcx+10h], rax
0x18001fb25  jb      loc_18001FBD9
0x18001fb2b  mov     rcx, rdi; char *
0x18001fb2e  mov     esi, 0C0000022h
0x18001fb33  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001fb38  lea     rcx, Class
0x18001fb3f  mov     r9, rax
0x18001fb42  mov     [rsp+30h], rcx
0x18001fb47  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001fb4e  lea     rcx, aPotentialRepla; "Potential replay of creds"
0x18001fb55  mov     r8d, esi
0x18001fb58  mov     [rsp+1D0h+UserData], rcx
0x18001fb5d  xor     ecx, ecx
0x18001fb5f  mov     [rsp+1D0h+UserDataCount], 0B30h
0x18001fb67  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001fb6c  call    ?CloudApFIDOCredReplay@CloudAPProvider@@SAXXZ; CloudAPProvider::CloudApFIDOCredReplay(void)
0x18001fb71  jmp     short loc_18001FBD9
0x18001fb73  mov     rcx, rdi; char *
0x18001fb76  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001fb7b  lea     rcx, Class
0x18001fb82  mov     [rsp+30h], rcx
0x18001fb87  lea     rcx, aFidovalidatepu; "FIDOValidatePublicCacheData"
0x18001fb8e  mov     [rsp+1D0h+UserData], rcx
0x18001fb93  mov     [rsp+1D0h+UserDataCount], 0B36h
0x18001fb9b  jmp     short loc_18001FBC5
0x18001fb9d  mov     rcx, rdi; char *
0x18001fba0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001fba5  lea     rcx, Class
0x18001fbac  mov     [rsp+30h], rcx
0x18001fbb1  lea     rcx, aGetrawcachenod; "GetRawCacheNode"
0x18001fbb8  mov     [rsp+1D0h+UserData], rcx
0x18001fbbd  mov     [rsp+1D0h+UserDataCount], 0B3Bh
0x18001fbc5  mov     r9, rax
0x18001fbc8  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001fbcf  mov     r8d, esi
0x18001fbd2  xor     ecx, ecx
0x18001fbd4  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001fbd9  mov     r14d, esi
0x18001fbdc  test    esi, esi
0x18001fbde  jns     loc_18001FC9B
0x18001fbe4  lea     r15, Class
0x18001fbeb  jmp     short loc_18001FC25
0x18001fbed  mov     rcx, rdi; char *
0x18001fbf0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001fbf5  lea     r15, Class
0x18001fbfc  mov     r9, rax
0x18001fbff  mov     [rsp+30h], r15
0x18001fc04  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001fc0b  mov     [rsp+1D0h+UserData], r8
0x18001fc10  xor     ecx, ecx
0x18001fc12  mov     r8d, esi
0x18001fc15  mov     [rsp+1D0h+UserDataCount], 0B40h
0x18001fc1d  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001fc22  mov     r14d, esi
0x18001fc25  mov     rcx, rdi; char *
0x18001fc28  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001fc2d  lea     rcx, aFailedSignatur; "Failed Signature count validation"
0x18001fc34  mov     [rsp+30h], r15
0x18001fc39  mov     [rsp+1D0h+UserData], rcx
0x18001fc3e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001fc45  xor     ecx, ecx
0x18001fc47  mov     [rsp+1D0h+UserDataCount], 0B45h
0x18001fc4f  mov     r9, rax
0x18001fc52  mov     r8d, esi
0x18001fc55  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001fc5a  cmp     r14d, 0C0000017h
0x18001fc61  jz      short loc_18001FC72
0x18001fc63  cmp     r14d, 0C000009Ah
0x18001fc6a  mov     eax, 0C000006Ah
0x18001fc6f  cmovnz  esi, eax
0x18001fc72  mov     rcx, rdi; char *
0x18001fc75  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001fc7a  mov     [rsp+30h], r15
0x18001fc7f  lea     rcx, aGetlogonpublic; "GetLogonPublicCacheForUser"
0x18001fc86  mov     [rsp+1D0h+UserData], rcx
0x18001fc8b  mov     r9, rax
0x18001fc8e  mov     [rsp+1D0h+UserDataCount], 0B4Ch
0x18001fc96  jmp     loc_18002066A
0x18001fc9b  mov     r14, [rsp+1D0h+var_160]
0x18001fca0  mov     r11, [rsp+1D0h+var_178]
0x18001fca5  cmp     dword ptr [r11], 4
0x18001fca9  jnz     short loc_18001FD06
0x18001fcab  test    r15, r15
0x18001fcae  jnz     short loc_18001FD06
0x18001fcb0  lea     rdx, [rbp+0D0h+var_120]; struct _SCARD_PIN **
0x18001fcb4  mov     rcx, r13; struct _USER_CACHE_ENTRY *
0x18001fcb7  call    ?GetScardPinFromCurrentUserLogonSession@@YAJPEAU_USER_CACHE_ENTRY@@PEAPEAU_SCARD_PIN@@@Z; GetScardPinFromCurrentUserLogonSession(_USER_CACHE_ENTRY *,_SCARD_PIN * *)
0x18001fcbc  mov     esi, eax
0x18001fcbe  test    eax, eax
0x18001fcc0  jz      short loc_18001FD02
0x18001fcc2  mov     rcx, rdi; char *
0x18001fcc5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001fcca  lea     rcx, Class
0x18001fcd1  mov     r9, rax
0x18001fcd4  mov     [rsp+30h], rcx
0x18001fcd9  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001fce0  lea     rcx, aGetscardpinfro; "GetScardPinFromCurrentUserLogonSession "...
0x18001fce7  mov     r8d, esi
0x18001fcea  mov     [rsp+1D0h+UserData], rcx
0x18001fcef  xor     ecx, ecx
0x18001fcf1  mov     [rsp+1D0h+UserDataCount], 0B55h
0x18001fcf9  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001fcfe  test    esi, esi
0x18001fd00  js      short loc_18001FD06
0x18001fd02  mov     r15, [rbp+0D0h+var_120]
0x18001fd06  lea     rax, [rsp+1D0h+hMem]
0x18001fd0b  mov     [rsp+30h], rax; struct _CloudAPCacheNodeData2 **
0x18001fd10  lea     rax, [rbp+0D0h+var_F8]
0x18001fd14  mov     [rsp+1D0h+UserData], rax; struct _tagCacheNodeIdentifier *
0x18001fd19  mov     rax, [rsp+1D0h+var_178]
0x18001fd1e  mov     qword ptr [rsp+1D0h+UserDataCount], r15; struct _SCARD_PIN *
0x18001fd23  mov     r15, [rsp+1D0h+var_188]
0x18001fd28  mov     rcx, r15; struct _CloudAPCache *
0x18001fd2b  mov     r9d, [rax+4]; unsigned int
0x18001fd2f  mov     r8, [rax+8]; unsigned __int8 *
0x18001fd33  mov     edx, [rax]; unsigned int
0x18001fd35  call    ?UnlockCloudAPCacheNodeData@@YAJPEAU_CloudAPCache@@KPEAEKPEAU_SCARD_PIN@@PEAU_tagCacheNodeIdentifier@@PEAPEAU_CloudAPCacheNodeData2@@@Z; UnlockCloudAPCacheNodeData(_CloudAPCache *,ulong,uchar *,ulong,_SCARD_PIN *,_tagCacheNodeIdentifier *,_CloudAPCacheNodeData2 * *)
0x18001fd3a  mov     esi, eax
0x18001fd3c  test    eax, eax
0x18001fd3e  jns     loc_18001FDD1
0x18001fd44  mov     rcx, rdi; char *
0x18001fd47  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001fd4c  lea     r15, Class
0x18001fd53  mov     r9, rax
0x18001fd56  mov     [rsp+30h], r15
0x18001fd5b  lea     r14, aUnlockcloudapc; "UnlockCloudAPCacheNodeData"
0x18001fd62  mov     [rsp+1D0h+UserData], r14
0x18001fd67  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001fd6e  mov     r8d, esi
0x18001fd71  mov     [rsp+1D0h+UserDataCount], 0B65h
0x18001fd79  xor     ecx, ecx
0x18001fd7b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001fd80  cmp     esi, 0C0000017h
0x18001fd86  jz      short loc_18001FDAF
0x18001fd88  cmp     esi, 0C000009Ah
0x18001fd8e  jz      short loc_18001FDAF
0x18001fd90  mov     rax, [rsp+1D0h+var_178]
0x18001fd95  mov     eax, [rax]
0x18001fd97  sub     eax, 4
0x18001fd9a  cmp     eax, 1
0x18001fd9d  ja      short loc_18001FDAA
0x18001fd9f  lea     eax, [rsi+3FFFFC80h]
0x18001fda5  cmp     eax, 1
0x18001fda8  jbe     short loc_18001FDAF
0x18001fdaa  mov     esi, 0C000006Ah
0x18001fdaf  mov     rcx, rdi; char *
0x18001fdb2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001fdb7  mov     [rsp+30h], r15
0x18001fdbc  mov     r9, rax
0x18001fdbf  mov     [rsp+1D0h+UserData], r14
0x18001fdc4  mov     [rsp+1D0h+UserDataCount], 0B6Fh
0x18001fdcc  jmp     loc_18002066A
0x18001fdd1  cmp     byte ptr [rsp+1D0h+var_190], 0
0x18001fdd6  jz      short loc_18001FE44
0x18001fdd8  mov     rdx, [rsp+1D0h+Token]; Token
0x18001fddd  xor     ecx, ecx; Thread
0x18001fddf  call    cs:__imp_SetThreadToken
0x18001fde5  test    eax, eax
0x18001fde7  jnz     short loc_18001FE3F
0x18001fde9  call    cs:__imp_GetLastError
0x18001fdef  mov     esi, eax
0x18001fdf1  test    eax, eax
0x18001fdf3  jle     short loc_18001FDFE
0x18001fdf5  movzx   esi, ax
0x18001fdf8  or      esi, 0C0070000h
0x18001fdfe  mov     rcx, rdi; char *
0x18001fe01  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001fe06  lea     r15, Class
0x18001fe0d  mov     r9, rax
0x18001fe10  mov     [rsp+30h], r15
0x18001fe15  lea     r12, aSetthreadtoken; "SetThreadToken"
0x18001fe1c  mov     [rsp+1D0h+UserData], r12
0x18001fe21  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001fe28  mov     r8d, esi
  ... truncated ...
```
