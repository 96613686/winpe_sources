# InteractiveLogon(_SECURITY_LOGON_TYPE,_ApPluginPkg *,int,_USER_CACHE_ENTRY * *,_DECRYPTED_AUTH_DATA *,_DPAPI_DECODED_AUTH_DATA *,bool,_CloudAPCache * *,_APPLUGIN_USER_INFO * *,bool *,_SCARD_PIN *,_AP_BLOB *,_tagCacheNodeIdentifier *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x180037240`
- end: `0x180038db6`
- name: `?InteractiveLogon@@YAJW4_SECURITY_LOGON_TYPE@@PEAU_ApPluginPkg@@HPEAPEAU_USER_CACHE_ENTRY@@PEAU_DECRYPTED_AUTH_DATA@@PEAU_DPAPI_DECODED_AUTH_DATA@@_NPEAPEAU_CloudAPCache@@PEAPEAU_APPLUGIN_USER_INFO@@PEA_NPEAU_SCARD_PIN@@PEAU_AP_BLOB@@PEAU_tagCacheNodeIdentifier@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `7030`
- prototype: `int(enum _SECURITY_LOGON_TYPE, struct _ApPluginPkg *, int, struct _USER_CACHE_ENTRY **, struct _DECRYPTED_AUTH_DATA *, struct _DPAPI_DECODED_AUTH_DATA *, bool, struct _CloudAPCache **, struct _APPLUGIN_USER_INFO **, bool *, struct _SCARD_PIN *, struct _AP_BLOB *, struct _tagCacheNodeIdentifier *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `1`
- callee_count: `38`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180018a20`

## callees

- `0x180003e70`
- `0x180006a80`
- `0x180007690`
- `0x180007ef0`
- `0x180007fc0`
- `0x18000a600`
- `0x18000a8f0`
- `0x18000b9b0`
- `0x18000ce50`
- `0x18000e7e0`
- `0x18000f100`
- `0x18000f700`
- `0x18000fd50`
- `0x18002223c`
- `0x180022980`
- `0x1800239f0`
- `0x180024bb0`
- `0x18002ce50`
- `0x180032884`
- `0x180032998`
- `0x1800335f4`
- `0x180037240`
- `0x18003bfdc`
- `0x18003c07c`
- `0x18003faf4`
- `0x180041504`
- `0x180042410`
- `0x18004d570`
- `0x180051260`
- `0x1800514d4`
- `0x1800515b4`
- `0x1800517d4`
- `0x180051f34`
- `0x180052e08`
- `0x180052e64`
- `0x1800545f0`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800375fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003878f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038aef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800375fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003878f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038aef`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800375f3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180038785`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180038ae5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800375f3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180038785`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180038ae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038b5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038b5c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180037af9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180037af9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037782`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038d8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037782`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038d8b`
- `RPCRT4!RpcStringFreeW` at `0x1800381e6`
- `RPCRT4!RpcStringFreeW` at `0x1800381f6`
- `RPCRT4!RpcStringFreeW` at `0x180038394`
- `RPCRT4!RpcStringFreeW` at `0x1800381e6`
- `RPCRT4!RpcStringFreeW` at `0x1800381f6`
- `RPCRT4!RpcStringFreeW` at `0x180038394`
- `RPCRT4!UuidToStringW` at `0x180038142`
- `RPCRT4!UuidToStringW` at `0x180038155`
- `RPCRT4!UuidToStringW` at `0x180038337`
- `RPCRT4!UuidToStringW` at `0x180038142`
- `RPCRT4!UuidToStringW` at `0x180038155`
- `RPCRT4!UuidToStringW` at `0x180038337`
- `RPCRT4!UuidEqual` at `0x180038044`
- `RPCRT4!UuidEqual` at `0x180038122`
- `RPCRT4!UuidEqual` at `0x1800382ab`
- `RPCRT4!UuidEqual` at `0x1800383c4`
- `RPCRT4!UuidEqual` at `0x1800387fd`
- `RPCRT4!UuidEqual` at `0x180038044`
- `RPCRT4!UuidEqual` at `0x180038122`
- `RPCRT4!UuidEqual` at `0x1800382ab`
- `RPCRT4!UuidEqual` at `0x1800383c4`
- `RPCRT4!UuidEqual` at `0x1800387fd`
- `ntdll!RtlReleaseResource` at `0x180037793`
- `ntdll!RtlReleaseResource` at `0x180038b45`
- `ntdll!RtlReleaseResource` at `0x180037793`
- `ntdll!RtlReleaseResource` at `0x180038b45`
- `ntdll!RtlLengthSid` at `0x180038894`
- `ntdll!RtlLengthSid` at `0x180038894`
- `ntdll!RtlAcquireResourceShared` at `0x1800376d5`
- `ntdll!RtlAcquireResourceShared` at `0x1800376d5`

## string_xrefs

- `0x1800373aa`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180037415`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180037484`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800375b2`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180037612`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180037698`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003774a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800377b0`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180037862`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003787d`: `FindUserInCacheBySid`
- `0x1800378e3`: `CreateOrAcquireUserCacheEntry`
- `0x180037b44`: `MoveFileW`
- `0x1800384a0`: `UpdatePluginOpaqueCacheBlob`
- `0x180038566`: `UpdatePluginOpaqueCacheBlob`
- `0x18003858c`: `UpdatePluginOpaqueCacheBlob`
- `0x18003873d`: `AddCloudAPCacheNode`
- `0x180037421`: `ImpersonateClient`
- `0x1800385d1`: `ImpersonateClient`
- `0x180038835`: `UpdateDPAPICredKey`
- `0x180038527`: `AllocateCloudAPCache`
- `0x18003762d`: `SetThreadToken`
- `0x1800387b1`: `SetThreadToken`
- `0x180038ad8`: `SetThreadToken`
- `0x1800373bb`: `Plugin doesnt support cached logon`
- `0x1800375cd`: `GetToken`
- `0x180037820`: `CreateOrAcquireUserCacheEntry(DetectNameChange)`
- `0x180037cb5`: `GetLogonCache`
- `0x180037ec0`: `GetLogonCache`
- `0x180037e31`: `CreateOrAcquireUserCacheEntry(DetectAlias)`
- `0x18003823d`: `Plugin returned Current Key Id when none was requested`
- `0x180038363`: `Plugin didnt return the Cred key requested`

## pseudocode

```c
__int64 __fastcall InteractiveLogon(
        unsigned int a1,
        struct _ApPluginPkg *a2,
        int a3,
        struct _USER_CACHE_ENTRY **a4,
        struct _DECRYPTED_AUTH_DATA *a5,
        struct _DPAPI_DECODED_AUTH_DATA *a6,
        bool a7,
        struct _CloudAPCache **a8,
        struct _APPLUGIN_USER_INFO **a9,
        bool *a10,
        struct _SCARD_PIN *a11,
        struct _AP_BLOB *a12,
        struct _tagCacheNodeIdentifier *a13,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a14)
{
  struct _USER_CACHE_ENTRY *v15; // r15
  struct _USER_CACHE_ENTRY *v18; // r12
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v19; // r8
  unsigned int RegVal; // ebx
  const char *v21; // rax
  struct _CloudAPCache *v22; // r13
  const char *v23; // rax
  const char *v24; // rax
  _QWORD *v25; // r12
  __int64 v26; // rax
  __int64 v27; // rax
  const char *v28; // rax
  signed int LastError; // eax
  const char *v30; // rax
  const unsigned __int16 *v31; // rcx
  unsigned int v32; // eax
  const char *v33; // rax
  const char *v34; // rax
  struct _ApPluginPkg *v35; // rbx
  struct _GUID *v36; // r12
  const char *v37; // rax
  const char *v38; // rax
  struct _USER_CACHE_ENTRY *v39; // r13
  const char *v40; // rax
  struct _USER_CACHE_ENTRY *v41; // r12
  char v42; // bl
  char *v43; // rcx
  bool v44; // zf
  struct _USER_CACHE_ENTRY **v45; // rbx
  struct _ApPluginPkg *v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rcx
  unsigned int v49; // ebx
  unsigned int v50; // r15d
  const char *v51; // rax
  __int64 v52; // r8
  char *v53; // r13
  unsigned __int64 v54; // r12
  const char *v55; // rax
  const char *v56; // rax
  __int64 v57; // r8
  char *v58; // r15
  const char *v59; // rax
  const char *v60; // rax
  struct _USER_CACHE_ENTRY *v61; // rbx
  const char *v62; // rax
  struct _USER_CACHE_ENTRY *v63; // rbx
  const char *v64; // rax
  __int16 v65; // ax
  const char *v66; // rax
  const char *v67; // rax
  RPC_WSTR v68; // rbx
  void *v69; // r12
  struct _DECRYPTED_AUTH_DATA *v70; // r13
  struct _LSA_SECPKG_FUNCTION_TABLE *v71; // rax
  __int64 v72; // rcx
  const char *v73; // rax
  const WCHAR *v74; // rdx
  struct _DECRYPTED_AUTH_DATA *v75; // r13
  const unsigned __int16 **v76; // r15
  const char *v77; // rax
  struct _USER_CACHE_ENTRY **v78; // rbx
  struct _USER_CACHE_ENTRY *v79; // rcx
  const char *v80; // rax
  const char *v81; // rax
  RPC_WSTR v82; // rbx
  struct _LSA_SECPKG_FUNCTION_TABLE *v83; // rax
  __int64 v84; // rcx
  const char *v85; // rax
  const char *v86; // rax
  struct _ApPluginPkg *v87; // r13
  const char *v88; // rax
  UUID *p_Uuid1; // r12
  unsigned int DPAPIKeys; // eax
  GUID *v91; // r9
  GUID *v92; // rcx
  const char *v93; // rax
  char v94; // r13
  const char *v95; // rax
  __int64 v96; // r8
  const char *v97; // rax
  __int64 v98; // r8
  const char *v99; // rax
  const char *v100; // rax
  __int64 v101; // r8
  const char *v102; // rax
  __int64 v103; // r8
  UUID *v104; // rcx
  __int64 v105; // rdx
  struct _CREDENTIAL_KEY *v106; // rax
  const char *v107; // rax
  __int64 v108; // r8
  const char *v109; // rax
  __int64 v110; // r8
  struct _CloudAPCache *v111; // rbx
  int v112; // r12d
  int updated; // eax
  const char *v114; // rax
  const char *v115; // rax
  const char *v116; // rax
  const char *v117; // rax
  struct _DPAPI_DECODED_AUTH_DATA *v118; // r12
  int v119; // eax
  const char *v120; // rax
  int v121; // ecx
  __int64 v122; // rbx
  void *v123; // rax
  const char *v124; // rax
  __int64 v125; // r8
  struct _SCARD_PIN *v126; // rax
  int ScardPinFromCurrentUserLogonSession; // ebx
  const char *v128; // rax
  struct _CloudAPCache *v129; // r13
  const char *v130; // rax
  signed int v131; // eax
  const char *v132; // rax
  const char *v133; // rax
  struct _CREDENTIAL_KEY *v134; // rcx
  __int64 v135; // rax
  size_t v136; // rbx
  void *v137; // rax
  void *v138; // r12
  const char *v139; // rax
  __int64 v140; // r8
  const char *v141; // rax
  _BYTE *v142; // rax
  __int64 v143; // rcx
  unsigned int *v144; // rax
  __int64 v145; // rcx
  unsigned int *v146; // rax
  __int64 v147; // rcx
  struct _APPLUGIN_USER_INFO *v148; // rax
  signed int v149; // eax
  unsigned int v150; // r15d
  const char *v151; // rax
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v152; // rcx
  __int64 v153; // rdx
  __int64 v154; // rax
  __int64 CredentialSize; // r9
  PUCHAR Credentials; // r8
  _BYTE *v157; // rcx
  __int64 v158; // rax
  struct _CREDENTIAL_KEY *v159; // rcx
  __int64 v160; // rax
  struct _CREDENTIAL_KEY *v161; // rcx
  __int64 v162; // rax
  _BYTE *v163; // rcx
  __int64 v164; // rax
  struct _USER_CACHE_ENTRY *v165; // rdi
  struct _GUID *v167; // [rsp+20h] [rbp-E0h]
  struct _GUID *v168; // [rsp+20h] [rbp-E0h]
  struct _GUID *v169; // [rsp+20h] [rbp-E0h]
  struct _GUID *v170; // [rsp+20h] [rbp-E0h]
  struct _GUID *v171; // [rsp+20h] [rbp-E0h]
  struct _GUID *v172; // [rsp+20h] [rbp-E0h]
  struct _GUID *v173; // [rsp+20h] [rbp-E0h]
  struct _GUID *v174; // [rsp+20h] [rbp-E0h]
  struct _GUID *v175; // [rsp+20h] [rbp-E0h]
  struct _GUID *v176; // [rsp+20h] [rbp-E0h]
  struct _GUID *v177; // [rsp+20h] [rbp-E0h]
  struct _GUID *v178; // [rsp+20h] [rbp-E0h]
  struct _GUID *v179; // [rsp+20h] [rbp-E0h]
  char v180; // [rsp+50h] [rbp-B0h]
  char v181; // [rsp+51h] [rbp-AFh]
  char v182; // [rsp+52h] [rbp-AEh]
  struct _CloudAPCache *v183; // [rsp+58h] [rbp-A8h]
  char v184; // [rsp+60h] [rbp-A0h]
  char v185; // [rsp+61h] [rbp-9Fh]
  struct _CREDENTIAL_KEY *Source; // [rsp+68h] [rbp-98h] BYREF
  struct _USER_CACHE_ENTRY *v187; // [rsp+70h] [rbp-90h]
  struct _APPLUGIN_USER_INFO *v188; // [rsp+78h] [rbp-88h] BYREF
  struct _CREDENTIAL_KEY *v189; // [rsp+80h] [rbp-80h] BYREF
  struct _CloudAPCache *v190; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp-70h]
  RPC_WSTR String; // [rsp+98h] [rbp-68h] BYREF
  RPC_WSTR v193; // [rsp+A0h] [rbp-60h] BYREF
  RPC_STATUS Status; // [rsp+A8h] [rbp-58h] BYREF
  RPC_WSTR StringUuid; // [rsp+B0h] [rbp-50h] BYREF
  struct _ApPluginPkg *v196; // [rsp+B8h] [rbp-48h]
  unsigned int v197[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v198; // [rsp+C8h] [rbp-38h]
  struct _USER_CACHE_ENTRY *v199; // [rsp+D0h] [rbp-30h]
  struct _USER_CACHE_ENTRY *v200; // [rsp+D8h] [rbp-28h] BYREF
  HANDLE Token; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v202; // [rsp+E8h] [rbp-18h] BYREF
  int v203; // [rsp+F8h] [rbp-8h]
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v204; // [rsp+100h] [rbp+0h] BYREF
  PCWSTR SourceString; // [rsp+108h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+110h] [rbp+10h] BYREF
  __int128 v207; // [rsp+118h] [rbp+18h] BYREF
  PCWSTR v208; // [rsp+128h] [rbp+28h] BYREF
  int v209; // [rsp+130h] [rbp+30h]
  struct _USER_CACHE_ENTRY *v210; // [rsp+138h] [rbp+38h] BYREF
  struct _DPAPI_DECODED_AUTH_DATA *v211; // [rsp+140h] [rbp+40h]
  bool *v212; // [rsp+148h] [rbp+48h]
  struct _SCARD_PIN *v213; // [rsp+150h] [rbp+50h] BYREF
  void *v214; // [rsp+158h] [rbp+58h]
  LPCWSTR lpExistingFileName; // [rsp+160h] [rbp+60h]
  LPCWSTR lpNewFileName; // [rsp+168h] [rbp+68h]
  __int128 v217; // [rsp+170h] [rbp+70h] BYREF
  struct _APPLUGIN_USER_INFO **v218; // [rsp+180h] [rbp+80h]
  struct _DECRYPTED_AUTH_DATA *v219; // [rsp+188h] [rbp+88h]
  struct _AP_BLOB *v220; // [rsp+190h] [rbp+90h]
  struct _tagCacheNodeIdentifier *v221; // [rsp+198h] [rbp+98h]
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v222; // [rsp+1A0h] [rbp+A0h]
  __int128 v223; // [rsp+1A8h] [rbp+A8h] BYREF
  __int128 v224; // [rsp+1B8h] [rbp+B8h] BYREF
  __int128 v225; // [rsp+1C8h] [rbp+C8h]
  UUID Uuid1; // [rsp+1D8h] [rbp+D8h] BYREF

  v15 = *a4;
  v212 = a10;
  v18 = 0;
  StringUuid = (RPC_WSTR)a11;
  v220 = a12;
  v221 = a13;
  v196 = a2;
  v209 = a3;
  v19 = a14;
  v193 = (RPC_WSTR)a4;
  hMem = *a8;
  v183 = 0;
  v190 = 0;
  v199 = 0;
  v210 = 0;
  v219 = a5;
  v211 = a6;
  String = (RPC_WSTR)a8;
  v218 = a9;
  v222 = a14;
  Status = 0;
  v214 = 0;
  v188 = 0;
  Source = 0;
  v189 = 0;
  Token = 0;
  v187 = 0;
  v200 = 0;
  v181 = 0;
  v213 = 0;
  v208 = 0;
  SourceString = 0;
  hKey = 0;
  v182 = 0;
  lpExistingFileName = 0;
  lpNewFileName = 0;
  v204 = 0;
  *a9 = 0;
  Uuid1 = stru_180085DB8;
  v224 = 0;
  v225 = 0;
  v207 = 0;
  v202 = 0;
  v217 = 0;
  v223 = 0;
  if ( v19 )
    *v19 = 0;
  if ( !*((_QWORD *)a2 + 31) )
  {
    RegVal = -2146893039;
    v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 2148074257LL, v21, 3592, "Plugin doesnt support cached logon", &Class);
    v22 = 0;
    goto LABEL_241;
  }
  v180 = 0;
  if ( *(_DWORD *)a6 != 4 )
  {
LABEL_9:
    v184 = 0;
    RegVal = DuplicateCredentialData(v15, (struct _AP_BLOB *)&v217, (struct _tagCacheNodeIdentifier *)&v223);
    if ( RegVal )
    {
      v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v24, 3614, "DuplicateCredentialData", &Class);
      goto LABEL_11;
    }
    v25 = (_QWORD *)((char *)v15 + 360);
    v203 = 0;
    *(_QWORD *)v197 = *((_QWORD *)v15 + 45);
    v26 = *((_QWORD *)v15 + 46);
    v198 = v26;
    if ( v26 )
      _InterlockedIncrement((volatile signed __int32 *)(v26 + 8));
    IncrementSharedPtrAtomicCounter(v197);
    UnlockAndProtectUserCacheEntry(v15);
    RegVal = (*((__int64 (__fastcall **)(_QWORD, _QWORD, struct _DECRYPTED_AUTH_DATA *, __int128 *, __int128 *, struct _APPLUGIN_USER_INFO **, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **))a2
              + 31))(
               *((_QWORD *)a2 + 1),
               a1,
               a5,
               &v217,
               &v202,
               &v188,
               &v204);
    if ( v188 )
    {
      v203 = *((_DWORD *)v188 + 32);
      *((_DWORD *)v188 + 32) = v203 & 0xFFFFFFFB;
    }
    LockAndUnProtectUserCacheEntry(v15, 1);
    *(_QWORD *)v197 = *v25;
    v27 = *((_QWORD *)v15 + 46);
    v198 = v27;
    if ( v27 )
      _InterlockedIncrement((volatile signed __int32 *)(v27 + 8));
    DecrementSharedPtrAtomicCounter((__int64)v197);
    if ( (RegVal & 0x80000000) != 0 )
    {
      if ( RegVal == -1073741711 )
        *v218 = v188;
      LODWORD(v202) = 0;
      *((_QWORD *)&v202 + 1) = 0;
      v188 = 0;
      v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v168) = 3656;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v28, v168, "GetToken", &Class);
      goto LABEL_11;
    }
    if ( v180 )
    {
      if ( !SetThreadToken(0, Token) )
      {
        LastError = GetLastError();
        RegVal = LastError;
        if ( LastError > 0 )
          RegVal = (unsigned __int16)LastError | 0xC0070000;
        v30 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v168) = 3665;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v30, v168, "SetThreadToken", &Class);
LABEL_27:
        v22 = v183;
        goto LABEL_231;
      }
      v180 = 0;
    }
    v31 = (const unsigned __int16 *)*((_QWORD *)v188 + 8);
    if ( v31 && *v31 || (v31 = (const unsigned __int16 *)*((_QWORD *)v15 + 11)) != 0 )
    {
      v32 = DuplicateString(v31, 0, (unsigned __int16 **)&SourceString);
      RegVal = v32;
    }
    else
    {
      v32 = RegVal;
    }
    if ( v32 )
    {
      v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v168) = 3700;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v33, v168, "DuplicateString(NewName)", &Class);
      goto LABEL_11;
    }
    RtlAcquireResourceShared(&g_LookupsCacheLock, 1u);
    v184 = 1;
    v197[0] = FindUserInCacheBySid(*((HKEY *)a2 + 44), *((void **)v188 + 2), &hKey);
    RegVal = v197[0];
    CloudAPProvider::FindUserInCacheBySid<long &>((int *)v197);
    if ( (RegVal & 0x80000000) != 0 )
    {
      if ( RegVal != -1073741275 )
      {
        v38 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v168) = 3734;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v38, v168, "FindUserInCacheBySid", &Class);
        goto LABEL_11;
      }
    }
    else
    {
      v197[0] = 0;
      RegVal = GetRegVal(hKey, L"IdentityName", 6u, v197, (void **)&v208);
      if ( (int)(RegVal + 0x80000000) >= 0 && RegVal != -1073741275 )
      {
        v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v168) = 3721;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v34, v168, "GetStringRegVal(IdentityName)", &Class);
        goto LABEL_11;
      }
      RegCloseKey(hKey);
      hKey = 0;
    }
    RtlReleaseResource(&g_LookupsCacheLock);
    v35 = v196;
    v184 = 0;
    if ( (*((_BYTE *)v196 + 160) & 1) == 0 && v208 && SourceString && CloudAPCompareStrings(SourceString, v208) )
    {
      CloudAPProvider::DetectNameChange();
      v36 = (struct _GUID *)((char *)v35 + 68);
      RegVal = _CreateOrAcquireUserCacheEntry(a3, (struct _GUID *)((char *)v35 + 68), v208, 0, &v210);
      if ( RegVal )
      {
        v37 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v169) = 3760;
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          RegVal,
          v37,
          v169,
          "CreateOrAcquireUserCacheEntry(DetectNameChange)",
          &Class);
        v199 = v210;
        goto LABEL_11;
      }
      v39 = v210;
      v199 = v210;
      if ( v210 != v15 )
      {
        LockAndUnProtectUserCacheEntry(v210, 1);
        v182 = 1;
      }
      RegVal = _CreateOrAcquireUserCacheEntry(1, v36, SourceString, 0, &v200);
      if ( RegVal )
      {
        v40 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v170) = 3773;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v40, v170, "CreateOrAcquireUserCacheEntry", &Class);
LABEL_53:
        v187 = v200;
        goto LABEL_11;
      }
      v41 = v200;
      v187 = v200;
      if ( v200 == v15 )
      {
        v42 = 0;
      }
      else
      {
        LockAndUnProtectUserCacheEntry(v200, 1);
        v42 = 1;
        v181 = 1;
      }
      if ( !v182 || v42 )
      {
        v185 = 1;
        v43 = (char *)v39 + 360;
      }
      else
      {
        v185 = 0;
        v43 = (char *)v41 + 360;
      }
      utl::shared_ptr<utl::atomic<unsigned long>>::operator=(v43, (char *)v15 + 360);
      v44 = v42 == 0;
      v45 = (struct _USER_CACHE_ENTRY **)v193;
      if ( !v44 && v182 )
        UnlockAndProtectUserCacheEntry(*(struct _USER_CACHE_ENTRY **)v193);
      _ReleaseUserCacheEntry(0, *v45);
      v46 = v196;
      v47 = -1;
      *v45 = 0;
      v48 = *((_QWORD *)v46 + 43);
      do
        ++v47;
      while ( *(_WORD *)(v48 + 2 * v47) );
      v49 = v47 + 67;
      v50 = 2 * (v47 + 67);
      lpExistingFileName = (LPCWSTR)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(v50);
      if ( !lpExistingFileName )
      {
        RegVal = -1073741801;
        v51 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v170) = 3806;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v52, v51, v170, "AllocateLsaHeap", &Class);
        goto LABEL_11;
      }
      v53 = (char *)v39 + 104;
      v54 = v49;
      RegVal = RtlStringCchPrintfW(
                 (unsigned __int16 *)lpExistingFileName,
                 v49,
                 L"%ws\\%ws",
                 *((_QWORD *)v196 + 43),
                 v53);
      if ( RegVal )
      {
        v55 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v171) = 3814;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v55, v171, "RtlStringCchPrintfW", &Class);
        goto LABEL_11;
      }
      lpNewFileName = (LPCWSTR)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(v50);
      if ( !lpNewFileName )
      {
        RegVal = -1073741801;
        v56 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v171) = 3820;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v57, v56, v171, "AllocateLsaHeap", &Class);
        goto LABEL_11;
      }
      v58 = (char *)v187 + 104;
      RegVal = RtlStringCchPrintfW(
                 (unsigned __int16 *)lpNewFileName,
                 v54,
                 L"%ws\\%ws",
                 *((_QWORD *)v196 + 43),
                 (char *)v187 + 104);
      if ( RegVal )
      {
        v59 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v172) = 3828;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v59, v172, "RtlStringCchPrintfW", &Class);
        goto LABEL_11;
      }
      if ( !MoveFileW(lpExistingFileName, lpNewFileName) )
      {
        v197[0] = GetLastError();
        RegVal = v197[0];
        CloudAPProvider::MoveFileW<unsigned long &>((int *)v197);
        if ( RegVal != 2 && RegVal != 183 )
        {
          if ( (int)RegVal > 0 )
            RegVal = (unsigned __int16)RegVal | 0xC0070000;
          if ( RegVal )
          {
            v60 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(v172) = 3840;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v60, v172, "MoveFileW", &Class);
            goto LABEL_11;
          }
        }
      }
      if ( v185 )
      {
        v61 = v199;
        ((void (__fastcall *)(_QWORD))g_pLsaFunctionTable->FreeLsaHeap)(*((_QWORD *)v199 + 12));
        RegVal = DuplicateString(*((const unsigned __int16 **)v187 + 12), 1, (unsigned __int16 **)v61 + 12);
        if ( RegVal )
        {
          v62 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v172) = 3856;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v62, v172, "DuplicateString", &Class);
          goto LABEL_11;
        }
        v63 = v199;
        ((void (__fastcall *)(_QWORD))g_pLsaFunctionTable->FreeLsaHeap)(*((_QWORD *)v199 + 11));
        RegVal = DuplicateString(*((const unsigned __int16 **)v187 + 11), 0, (unsigned __int16 **)v63 + 11);
        if ( RegVal )
        {
          v64 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v172) = 3864;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v64, v172, "DuplicateString", &Class);
          goto LABEL_11;
        }
        *(_OWORD *)v53 = *(_OWORD *)v58;
        *((_OWORD *)v53 + 1) = *((_OWORD *)v58 + 1);
        *((_OWORD *)v53 + 2) = *((_OWORD *)v58 + 2);
        *((_OWORD *)v53 + 3) = *((_OWORD *)v58 + 3);
        *((_OWORD *)v53 + 4) = *((_OWORD *)v58 + 4);
        *((_OWORD *)v53 + 5) = *((_OWORD *)v58 + 5);
        *((_OWORD *)v53 + 6) = *((_OWORD *)v58 + 6);
        *((_OWORD *)v53 + 7) = *((_OWORD *)v58 + 7);
        v65 = *((_WORD *)v58 + 64);
        v15 = v199;
        *((_WORD *)v53 + 64) = v65;
      }
      else
      {
        v15 = v187;
      }
      RegVal = GetLogonCache((const unsigned __int16 **)v196, v15, v211, (HLOCAL *)&v190, v212);
      if ( (RegVal & 0x80000000) != 0 )
      {
        v66 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v173) = 3888;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v66, v173, "GetLogonCache", &Class);
        if ( RegVal == -1073741801 || RegVal == -1073741670 )
        {
          v67 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v173) = 3892;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v67, v173, "GetLogonCache", &Class);
LABEL_92:
          v183 = v190;
          goto LABEL_11;
        }
      }
      v68 = String;
      FreeCloudAPCache(*(_QWORD **)String);
      v69 = v190;
      v70 = v219;
      v183 = 0;
      v190 = 0;
      v71 = g_pLsaFunctionTable;
      *(_QWORD *)v68 = v69;
      v72 = *((_QWORD *)v70 + 1);
      hMem = v69;
      ((void (__fastcall *)(__int64))v71->FreeLsaHeap)(v72);
      RegVal = DuplicateString(*((const unsigned __int16 **)v187 + 12), 0, (unsigned __int16 **)v70 + 1);
      if ( RegVal )
      {
        v73 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v173) = 3905;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v73, v173, "DuplicateString", &Class);
        goto LABEL_11;
      }
      *(_QWORD *)v193 = v15;
      if ( v15 == v199 )
      {
        v199 = 0;
        v182 = 0;
        goto LABEL_113;
      }
    }
    else
    {
      v74 = (const WCHAR *)*((_QWORD *)v188 + 8);
      if ( !v74 || !*v74 || (v75 = v219, !CloudAPCompareStrings(*((PCWSTR *)v219 + 1), v74)) )
      {
        if ( !(unsigned int)IsCredentialDataSame(v15, (struct _AP_BLOB *)&v217, (struct _tagCacheNodeIdentifier *)&v223) )
        {
          RegVal = -1073741564;
          v86 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v168) = 3992;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            3221225732LL,
            v86,
            v168,
            "InteractiveLogon:Bailing out of network logon as state has changed",
            &Class);
          goto LABEL_11;
        }
        v69 = hMem;
LABEL_113:
        v87 = v196;
        RegVal = GetCurrentCredKeyIdForUser(v196, v15, v188, (struct _CloudAPCache *)v69, &Uuid1);
        if ( RegVal )
        {
          v88 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v176) = 4005;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v88, v176, "GetCurrentCredKeyIdForUser", &Class);
          goto LABEL_11;
        }
        p_Uuid1 = &Uuid1;
        if ( UuidEqual(&Uuid1, (UUID *)&stru_180085DB8, &Status) )
          p_Uuid1 = 0;
        DPAPIKeys = GetDPAPIKeys(v87, v15, (struct _AP_BLOB *)&v202, p_Uuid1, a7, &Source, &v189);
        v91 = &GUID_00000000_0000_0000_0000_000000000000;
        v197[0] = DPAPIKeys;
        RegVal = DPAPIKeys;
        if ( v189 )
          v92 = (GUID *)((char *)v189 + 16);
        else
          v92 = &GUID_00000000_0000_0000_0000_000000000000;
        if ( Source )
          LODWORD(v91) = (_DWORD)Source + 16;
        CloudAPProvider::GetDpapiKeys<long &,_GUID &,bool &,_GUID &,_GUID &>(
          (unsigned int)v197,
          (unsigned int)&Uuid1,
          (unsigned int)&a7,
          (_DWORD)v91,
          (__int64)v92);
        if ( RegVal )
        {
          v93 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v177) = 4032;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v93, v177, "GetDPAPIKeys", &Class);
          goto LABEL_11;
        }
        v94 = 0;
        if ( Source )
        {
          if ( !p_Uuid1 )
          {
            RegVal = -1073741595;
            v100 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(v177) = 4063;
            WPPTraceLogA(
              0,
              "0x%08x %s:%u : %s:%ws",
              v101,
              v100,
              v177,
              "Plugin returned Current Key Id when none was requested",
              &Class);
            goto LABEL_11;
          }
          if ( !UuidEqual(p_Uuid1, (UUID *)Source + 1, &Status) )
          {
            StringUuid = 0;
            String = 0;
            UuidToStringW(p_Uuid1, &StringUuid);
            UuidToStringW((const UUID *)Source + 1, &String);
            v95 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(v177) = 4050;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 0, v95, v177, "Cred key requested", v96);
            v97 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(v178) = 4051;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 0, v97, v178, "Cred key received", v98);
            if ( StringUuid )
              RpcStringFreeW(&StringUuid);
            if ( String )
              RpcStringFreeW(&String);
            RegVal = -1073741735;
            v99 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(v179) = 4057;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225561LL, v99, v179, "Cred key versions do not match", &Class);
            goto LABEL_11;
          }
        }
        else
        {
          if ( !v189 )
          {
            RegVal = -1073741595;
            v102 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(v177) = 4073;
            WPPTraceLogA(
              0,
              "0x%08x %s:%u : %s:%ws",
              v103,
              v102,
              v177,
              "GetKeys succeeded without current or latest keys",
              &Class);
            goto LABEL_11;
          }
          if ( !p_Uuid1 )
            goto LABEL_148;
          v104 = (UUID *)*((_QWORD *)v15 + 33);
          if ( v104 && UuidEqual(v104 + 1, p_Uuid1, &Status) )
          {
            v106 = (struct _CREDENTIAL_KEY *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(
                                               **((unsigned int **)v15 + 33),
                                               v105,
                                               0);
            Source = v106;
            if ( !v106 )
            {
              RegVal = -1073741801;
              v107 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
              LODWORD(v177) = 4088;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v108, v107, v177, "AllocateLsaHeap", &Class);
              goto LABEL_11;
            }
            memcpy_0(v106, *((const void **)v15 + 33), **((unsigned int **)v15 + 33));
          }
          else if ( (*((_DWORD *)v196 + 40) & 4) == 0 )
          {
            v193 = 0;
            UuidToStringW(p_Uuid1, &v193);
            CloudAPProvider::CloudAPLogonUserKeyLost<_GUID &>(p_Uuid1);
            v109 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(v177) = 4105;
            WPPTraceLogA(
              0,
              "0x%08x %s:%u : %s:%ws",
              2148074272LL,
              v109,
              v177,
              "Plugin didnt return the Cred key requested",
              v110);
            if ( v193 )
              RpcStringFreeW(&v193);
          }
          v94 = 1;
          if ( !Source )
          {
LABEL_148:
            FreeCloudAPCache(hMem);
            v112 = 0;
            *(_QWORD *)String = 0;
            Source = v189;
            v189 = 0;
            goto LABEL_149;
          }
        }
        v111 = (struct _CloudAPCache *)hMem;
        v112 = 0;
        if ( !hMem || UuidEqual((UUID *)((char *)hMem + 4), (UUID *)Source + 1, &Status) )
          goto LABEL_150;
        FreeCloudAPCache(v111);
        *(_QWORD *)String = 0;
LABEL_149:
        v111 = 0;
        hMem = 0;
LABEL_150:
        *(_QWORD *)&v224 = *((_QWORD *)v196 + 1);
        *((_QWORD *)&v224 + 1) = *((_QWORD *)v196 + 29);
        *(_QWORD *)&v225 = *((_QWORD *)v196 + 30);
        *((_QWORD *)&v225 + 1) = SecureFreeCacheData;
        if ( !v111 )
          goto LABEL_158;
        *(_DWORD *)v111 |= 1u;
        while ( 1 )
        {
          if ( v94 )
            *(_DWORD *)v111 |= 2u;
          updated = UpdatePluginOpaqueCacheBlob(
                      v111,
                      0,
                      Source,
                      (struct _AP_BLOB *)&v202,
                      (struct _tagCacheDataFuncs *)&v224);
          RegVal = updated;
          if ( updated >= 0 )
            break;
          if ( updated == -1073741801 || updated == -1073741670 )
          {
            v117 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(v167) = 4183;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v117, v167, "UpdatePluginOpaqueCacheBlob", &Class);
            goto LABEL_11;
          }
          v114 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v167) = 4185;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v114, v167, "UpdatePluginOpaqueCacheBlob", &Class);
          FreeCloudAPCache(hMem);
          ++v112;
          v183 = 0;
          v190 = 0;
          *(_QWORD *)String = 0;
          if ( v112 >= 2 )
          {
            v116 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(v177) = 4204;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v116, v177, "UpdatePluginOpaqueCacheBlob", &Class);
            goto LABEL_11;
          }
LABEL_158:
          RegVal = AllocateCloudAPCache(1, (struct _GUID *)Source + 1, &v190);
          if ( RegVal )
          {
            v115 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(v177) = 4158;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v115, v177, "AllocateCloudAPCache", &Class);
            v22 = v190;
            goto LABEL_230;
          }
          v183 = v190;
          v111 = v190;
          hMem = v190;
        }
        v118 = v211;
        v119 = *(_DWORD *)v211;
        if ( *(_DWORD *)v211 == 4 )
        {
          RegVal = ImpersonateClient(&Token);
          if ( RegVal )
          {
            v120 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(v167) = 4211;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v120, v167, "ImpersonateClient", &Class);
            goto LABEL_11;
          }
          v119 = *(_DWORD *)v118;
          v180 = 1;
        }
        v121 = v119;
        if ( (v203 & 4) != 0 )
          goto LABEL_170;
        if ( v119 == 1 )
        {
          if ( !*((_DWORD *)v118 + 1) )
          {
LABEL_170:
            if ( v119 == 7 )
            {
              v122 = *((_QWORD *)v118 + 1);
              LODWORD(v207) = 7;
              DWORD1(v207) = *(_DWORD *)(v122 + 20);
              v123 = (void *)((__int64 (*)(void))g_pLsaFunctionTable->AllocateLsaHeap)();
              *((_QWORD *)&v207 + 1) = v123;
              if ( !v123 )
              {
                RegVal = -1073741801;
                v124 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(v167) = 4273;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v125, v124, v167, "AllocateLsaHeap", &Class);
                goto LABEL_11;
              }
              memcpy_0(
                v123,
                (const void *)(*((_QWORD *)v118 + 1) + *(unsigned int *)(v122 + 16)),
                *(unsigned int *)(v122 + 20));
            }
            else
            {
              LODWORD(v207) = 6;
            }
            v129 = (struct _CloudAPCache *)hMem;
LABEL_187:
            if ( v180 )
            {
              if ( !SetThreadToken(0, Token) )
              {
                v131 = GetLastError();
                RegVal = v131;
                if ( v131 > 0 )
                  RegVal = (unsigned __int16)v131 | 0xC0070000;
                v132 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(v167) = 4293;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v132, v167, "SetThreadToken", &Class);
                goto LABEL_27;
              }
              v180 = 0;
            }
            if ( (*((_BYTE *)v196 + 160) & 4) != 0 && v189 && !UuidEqual((UUID *)v189 + 1, (UUID *)Source + 1, &Status) )
            {
              RegVal = UpdateDPAPICredKey(v129, Source, v189, (struct _AP_BLOB *)&v202);
              if ( RegVal )
              {
                v133 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(v167) = 4316;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v133, v167, "UpdateDPAPICredKey", &Class);
                goto LABEL_11;
              }
              v134 = Source;
              v135 = *(unsigned int *)Source;
              if ( *(_DWORD *)Source )
              {
                do
                {
                  *(_BYTE *)v134 = 0;
                  v134 = (struct _CREDENTIAL_KEY *)((char *)v134 + 1);
                  --v135;
                }
                while ( v135 );
                v134 = Source;
              }
              ((void (__fastcall *)(struct _CREDENTIAL_KEY *, _QWORD))g_pLsaFunctionTable->FreeLsaHeap)(v134, 0);
              Source = v189;
              v189 = 0;
            }
            v136 = RtlLengthSid(*((PSID *)v188 + 2));
            v137 = (void *)((__int64 (__fastcall *)(size_t))g_pLsaFunctionTable->AllocateLsaHeap)(v136);
            v214 = v137;
            v138 = v137;
            if ( v137 )
            {
              memcpy_0(v137, *((const void **)v188 + 2), v136);
              RegVal = 0;
              if ( v220 && v221 )
              {
                RegVal = DuplicateCredentialData(v15, v220, v221);
                if ( RegVal )
                {
                  v141 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                  LODWORD(v167) = 4350;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v141, v167, "DuplicateCredentialData", &Class);
                  goto LABEL_11;
                }
                RegVal = 0;
              }
              if ( *((_QWORD *)v15 + 30) )
                ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
              v142 = (_BYTE *)*((_QWORD *)v15 + 36);
              *((_QWORD *)v15 + 30) = v138;
              v214 = 0;
              if ( v142 )
              {
                v143 = *((unsigned int *)v15 + 70);
                if ( *((_DWORD *)v15 + 70) )
                {
                  do
                  {
                    *v142++ = 0;
                    --v143;
                  }
                  while ( v143 );
                }
                ((void (__fastcall *)(_QWORD))g_pLsaFunctionTable->FreeLsaHeap)(*((_QWORD *)v15 + 36));
              }
              *(_OWORD *)((char *)v15 + 280) = v202;
              LODWORD(v202) = 0;
              *((_QWORD *)&v202 + 1) = 0;
              v144 = (unsigned int *)*((_QWORD *)v15 + 33);
              if ( v144 )
              {
                v145 = *v144;
                if ( *v144 )
                {
                  do
                  {
                    *(_BYTE *)v144 = 0;
                    v144 = (unsigned int *)((char *)v144 + 1);
                    --v145;
                  }
                  while ( v145 );
                }
                ((void (__fastcall *)(_QWORD))g_pLsaFunctionTable->FreeLsaHeap)(*((_QWORD *)v15 + 33));
              }
              *((_QWORD *)v15 + 33) = Source;
              Source = 0;
              v146 = (unsigned int *)*((_QWORD *)v15 + 34);
              if ( v146 )
              {
                v147 = *v146;
                if ( *v146 )
                {
                  do
                  {
                    *(_BYTE *)v146 = 0;
                    v146 = (unsigned int *)((char *)v146 + 1);
                    --v147;
                  }
                  while ( v147 );
                }
                ((void (__fastcall *)(_QWORD))g_pLsaFunctionTable->FreeLsaHeap)(*((_QWORD *)v15 + 34));
              }
              *((_QWORD *)v15 + 34) = v189;
              v189 = 0;
              if ( *((_QWORD *)v15 + 38) )
                ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
              *(_OWORD *)((char *)v15 + 296) = v207;
              v207 = 0u;
              v22 = 0;
              if ( v183 )
                *(_QWORD *)String = v183;
              v148 = v188;
              v188 = 0;
              *v218 = v148;
              if ( v222 )
              {
                *v222 = v204;
                v204 = 0;
              }
              *v212 = 1;
LABEL_230:
              if ( !v180 )
              {
LABEL_236:
                if ( v184 )
                  RtlReleaseResource(&g_LookupsCacheLock);
                v18 = v187;
                goto LABEL_239;
              }
LABEL_231:
              if ( !SetThreadToken(0, Token) )
              {
                v149 = GetLastError();
                v150 = v149;
                if ( v149 > 0 )
                  v150 = (unsigned __int16)v149 | 0xC0070000;
                v151 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(v167) = 4424;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v150, v151, v167, "SetThreadToken", &Class);
                if ( (RegVal & 0x80000000) == 0 )
                  RegVal = v150;
              }
              goto LABEL_236;
            }
            RegVal = -1073741801;
            v139 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(v167) = 4337;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v140, v139, v167, "AllocateLsaHeap", &Class);
LABEL_11:
            v22 = v183;
            goto LABEL_230;
          }
        }
        else if ( v119 == 7 )
        {
          if ( !*(_DWORD *)(*((_QWORD *)v118 + 1) + 36LL) )
          {
            v119 = 7;
            goto LABEL_170;
          }
        }
        else
        {
          v126 = (struct _SCARD_PIN *)StringUuid;
          if ( v121 != 4 || StringUuid )
          {
LABEL_182:
            v129 = (struct _CloudAPCache *)hMem;
            RegVal = AddCloudAPCacheNode(
                       (struct _CloudAPCache *)hMem,
                       0,
                       *(_DWORD *)v118,
                       *((unsigned __int8 **)v118 + 1),
                       *((_DWORD *)v118 + 1),
                       Source,
                       (struct _AP_BLOB *)&v202,
                       v126,
                       (struct _tagCacheNodeIdentifier *)&v207);
            if ( RegVal )
            {
              v130 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
              LODWORD(v167) = 4260;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v130, v167, "AddCloudAPCacheNode", &Class);
              goto LABEL_11;
            }
            goto LABEL_187;
          }
          ScardPinFromCurrentUserLogonSession = GetScardPinFromCurrentUserLogonSession(v15, &v213);
          if ( !ScardPinFromCurrentUserLogonSession
            || (v128 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp"),
                LODWORD(v167) = 4246,
                WPPTraceLogA(
                  0,
                  "0x%08x %s:%u : %s:%ws",
                  (unsigned int)ScardPinFromCurrentUserLogonSession,
                  v128,
                  v167,
                  "Error in GetScardPinFromCurrentUserLogonSession",
                  &Class),
                ScardPinFromCurrentUserLogonSession >= 0) )
          {
            v126 = v213;
            goto LABEL_182;
          }
        }
        v126 = (struct _SCARD_PIN *)StringUuid;
        goto LABEL_182;
      }
      CloudAPProvider::DetectAlias();
      v76 = (const unsigned __int16 **)v196;
      RegVal = _CreateOrAcquireUserCacheEntry(
                 v209,
                 (struct _GUID *)((char *)v196 + 68),
                 *((const unsigned __int16 **)v188 + 8),
                 0,
                 &v200);
      if ( RegVal )
      {
        v77 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v174) = 3936;
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          RegVal,
          v77,
          v174,
          "CreateOrAcquireUserCacheEntry(DetectAlias)",
          &Class);
        goto LABEL_53;
      }
      v187 = v200;
      utl::shared_ptr<utl::atomic<unsigned long>>::operator=((char *)v200 + 360, v25);
      v78 = (struct _USER_CACHE_ENTRY **)v193;
      UnlockAndProtectUserCacheEntry(*(struct _USER_CACHE_ENTRY **)v193);
      _ReleaseUserCacheEntry(0, *v78);
      v79 = v187;
      *v78 = 0;
      LockAndUnProtectUserCacheEntry(v79, 1);
      v181 = 1;
      RegVal = GetLogonCache(v76, v187, v211, (HLOCAL *)&v190, v212);
      if ( (RegVal & 0x80000000) != 0 )
      {
        v80 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v175) = 3957;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v80, v175, "GetLogonCache", &Class);
        if ( RegVal == -1073741801 || RegVal == -1073741670 )
        {
          v81 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v175) = 3961;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v81, v175, "GetLogonCache", &Class);
          goto LABEL_92;
        }
      }
      v82 = String;
      FreeCloudAPCache(*(_QWORD **)String);
      v69 = v190;
      v183 = 0;
      v190 = 0;
      v83 = g_pLsaFunctionTable;
      *(_QWORD *)v82 = v69;
      v84 = *((_QWORD *)v75 + 1);
      hMem = v69;
      ((void (__fastcall *)(__int64))v83->FreeLsaHeap)(v84);
      v15 = v187;
      RegVal = DuplicateString(*((const unsigned __int16 **)v187 + 12), 0, (unsigned __int16 **)v75 + 1);
      if ( RegVal )
      {
        v85 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v175) = 3974;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v85, v175, "DuplicateString", &Class);
        goto LABEL_11;
      }
      *(_QWORD *)v193 = v187;
    }
    v187 = 0;
    v181 = 0;
    goto LABEL_113;
  }
  RegVal = ImpersonateClient(&Token);
  if ( !RegVal )
  {
    v180 = 1;
    goto LABEL_9;
  }
  v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v23, 3599, "ImpersonateClient", &Class);
  v22 = 0;
LABEL_239:
  if ( Token )
    CloseHandle(Token);
LABEL_241:
  FreeUserInfo(v188);
  FreeCloudAPCache(v22);
  FreeScardPin(v213);
  v152 = v204;
  if ( v204 )
  {
    v153 = 0;
    if ( v204->CredentialCount )
    {
      do
      {
        v154 = (unsigned int)v153;
        CredentialSize = v152->Credentials[v154].CredentialSize;
        Credentials = v152->Credentials[v154].Credentials;
        if ( v152->Credentials[v154].CredentialSize )
        {
          do
          {
            *Credentials++ = 0;
            --CredentialSize;
          }
          while ( CredentialSize );
          v152 = v204;
        }
        v153 = (unsigned int)(v153 + 1);
      }
      while ( (unsigned int)v153 < v152->CredentialCount );
    }
    ((void (__fastcall *)(struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *, __int64))g_pLsaFunctionTable->FreeLsaHeap)(
      v152,
      v153);
  }
  if ( v18 )
  {
    if ( v181 )
      UnlockAndProtectUserCacheEntry(v18);
    _ReleaseUserCacheEntry(0, v18);
  }
  if ( v214 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v157 = (_BYTE *)*((_QWORD *)&v202 + 1);
  if ( *((_QWORD *)&v202 + 1) )
  {
    v158 = (unsigned int)v202;
    if ( (_DWORD)v202 )
    {
      do
      {
        *v157++ = 0;
        --v158;
      }
      while ( v158 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  v159 = Source;
  if ( Source )
  {
    v160 = *(unsigned int *)Source;
    if ( *(_DWORD *)Source )
    {
      do
      {
        *(_BYTE *)v159 = 0;
        v159 = (struct _CREDENTIAL_KEY *)((char *)v159 + 1);
        --v160;
      }
      while ( v160 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  v161 = v189;
  if ( v189 )
  {
    v162 = *(unsigned int *)v189;
    if ( *(_DWORD *)v189 )
    {
      do
      {
        *(_BYTE *)v161 = 0;
        v161 = (struct _CREDENTIAL_KEY *)((char *)v161 + 1);
        --v162;
      }
      while ( v162 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  if ( *((_QWORD *)&v207 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v163 = (_BYTE *)*((_QWORD *)&v217 + 1);
  if ( *((_QWORD *)&v217 + 1) )
  {
    v164 = (unsigned int)v217;
    if ( (_DWORD)v217 )
    {
      do
      {
        *v163++ = 0;
        --v164;
      }
      while ( v164 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  if ( *((_QWORD *)&v223 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v208 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( SourceString )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( lpExistingFileName )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( lpNewFileName )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v165 = v199;
  if ( v199 )
  {
    if ( v182 )
      UnlockAndProtectUserCacheEntry(v199);
    _ReleaseUserCacheEntry(0, v165);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return RegVal;
}

```

## disassembly

```asm
0x180037240  push    rbp
0x180037242  push    rbx
0x180037243  push    rsi
0x180037244  push    rdi
0x180037245  push    r12
0x180037247  push    r13
0x180037249  push    r14
0x18003724b  push    r15
0x18003724d  lea     rbp, [rsp-0F8h]
0x180037255  sub     rsp, 1F8h
0x18003725c  mov     rax, cs:__security_cookie
0x180037263  xor     rax, rsp
0x180037266  mov     [rbp+130h+var_48], rax
0x18003726d  movups  xmm0, xmmword ptr cs:stru_180085DB8.Data1
0x180037274  mov     rax, [rbp+130h+arg_48]
0x18003727b  xor     r11d, r11d
0x18003727e  mov     r10, [rbp+130h+arg_40]
0x180037285  xorps   xmm1, xmm1
0x180037288  mov     rsi, [rbp+130h+arg_20]
0x18003728f  mov     r14, rdx
0x180037292  mov     r15, [r9]
0x180037295  mov     r13d, r8d
0x180037298  mov     [rbp+130h+var_E8], rax
0x18003729c  mov     edi, ecx
0x18003729e  mov     rax, [rbp+130h+arg_50]
0x1800372a5  mov     r12d, r11d
0x1800372a8  mov     rcx, [rbp+130h+arg_28]
0x1800372af  mov     [rbp+130h+StringUuid], rax
0x1800372b3  mov     rax, [rbp+130h+arg_58]
0x1800372ba  mov     [rbp+130h+var_A0], rax
0x1800372c1  mov     rax, [rbp+130h+arg_60]
0x1800372c8  mov     [rbp+130h+var_98], rax
0x1800372cf  mov     [rbp+130h+var_178], rdx
0x1800372d3  mov     rdx, [rbp+130h+arg_38]
0x1800372da  mov     [rbp+130h+var_100], r8d
0x1800372de  mov     r8, [rbp+130h+arg_68]
0x1800372e5  mov     [rbp+130h+var_190], r9
0x1800372e9  mov     rax, [rdx]
0x1800372ec  mov     [rbp+130h+hMem], rax
0x1800372f0  mov     eax, r11d
0x1800372f3  mov     [rsp+230h+var_1D8], rax
0x1800372f8  mov     [rbp+130h+var_1A8], rax
0x1800372fc  mov     [rbp+130h+var_160], rax
0x180037300  mov     [rbp+130h+var_F8], rax
0x180037304  mov     [rbp+130h+var_A8], rsi
0x18003730b  mov     [rbp+130h+var_F0], rcx
0x18003730f  mov     [rbp+130h+String], rdx
0x180037313  mov     [rbp+130h+var_B0], r10
0x18003731a  mov     [rbp+130h+var_90], r8
0x180037321  mov     [rbp+130h+Status], r11d
0x180037325  mov     [rbp+130h+var_D8], r11
0x180037329  mov     [rsp+230h+var_1B8], r11
0x18003732e  mov     [rsp+230h+Source], r11
0x180037333  mov     [rbp+130h+var_1B0], r11
0x180037337  mov     [rbp+130h+Token], r11
0x18003733b  mov     [rsp+230h+var_1C0], r11
0x180037340  mov     [rbp+130h+var_158], r11
0x180037344  mov     [rsp+230h+var_1DF], r11b
0x180037349  mov     [rbp+130h+var_E0], r11
0x18003734d  mov     [rbp+130h+var_108], r11
0x180037351  mov     [rbp+130h+SourceString], r11
0x180037355  mov     [rbp+130h+hKey], r11
0x180037359  mov     [rsp+230h+var_1DE], r11b
0x18003735e  mov     [rbp+130h+lpExistingFileName], r11
0x180037362  mov     [rbp+130h+lpNewFileName], r11
0x180037366  mov     [rbp+130h+var_130], r11
0x18003736a  mov     [r10], r11
0x18003736d  movdqu  xmmword ptr [rbp+130h+Uuid1.Data1], xmm0
0x180037375  xorps   xmm0, xmm0
0x180037378  movups  [rbp+130h+var_78], xmm1
0x18003737f  movups  [rbp+130h+var_68], xmm1
0x180037386  movups  [rbp+130h+var_118], xmm0
0x18003738a  movups  [rbp+130h+var_148], xmm0
0x18003738e  movups  [rbp+130h+var_C0], xmm0
0x180037392  movups  [rbp+130h+var_88], xmm1
0x180037399  test    r8, r8
0x18003739c  jz      short loc_1800373A1
0x18003739e  mov     [r8], r11
0x1800373a1  cmp     [r14+0F8h], r11
0x1800373a8  jnz     short loc_1800373F9
0x1800373aa  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800373b1  mov     ebx, 80090311h
0x1800373b6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800373bb  lea     rcx, aPluginDoesntSu_0; "Plugin doesnt support cached logon"
0x1800373c2  mov     r9, rax
0x1800373c5  lea     r14, Class
0x1800373cc  mov     r8d, ebx
0x1800373cf  mov     [rsp+230h+var_200], r14
0x1800373d4  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800373db  mov     [rsp+230h+var_208], rcx
0x1800373e0  xor     ecx, ecx
0x1800373e2  mov     dword ptr [rsp+230h+var_210], 0E08h
0x1800373ea  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800373ef  mov     r13, [rsp+230h+var_1D8]
0x1800373f4  jmp     loc_180038B62
0x1800373f9  cmp     dword ptr [rcx], 4
0x1800373fc  mov     [rsp+230h+var_1E0], r11b
0x180037401  jnz     short loc_180037464
0x180037403  lea     rcx, [rbp+130h+Token]; void **
0x180037407  call    ?ImpersonateClient@@YAJPEAPEAX@Z; ImpersonateClient(void * *)
0x18003740c  xor     r11d, r11d
0x18003740f  mov     ebx, eax
0x180037411  test    eax, eax
0x180037413  jz      short loc_18003745F
0x180037415  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18003741c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180037421  lea     rcx, aImpersonatecli; "ImpersonateClient"
0x180037428  mov     r9, rax
0x18003742b  lea     r14, Class
0x180037432  mov     r8d, ebx
0x180037435  mov     [rsp+230h+var_200], r14
0x18003743a  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180037441  mov     [rsp+230h+var_208], rcx
0x180037446  xor     ecx, ecx
0x180037448  mov     dword ptr [rsp+230h+var_210], 0E0Fh
0x180037450  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180037455  mov     r13, [rsp+230h+var_1D8]
0x18003745a  jmp     loc_180038B50
0x18003745f  mov     [rsp+230h+var_1E0], 1
0x180037464  lea     r8, [rbp+130h+var_88]; struct _tagCacheNodeIdentifier *
0x18003746b  mov     [rsp+230h+var_1D0], r11b
0x180037470  lea     rdx, [rbp+130h+var_C0]; struct _AP_BLOB *
0x180037474  mov     rcx, r15; struct _USER_CACHE_ENTRY *
0x180037477  call    ?DuplicateCredentialData@@YAJPEAU_USER_CACHE_ENTRY@@PEAU_AP_BLOB@@PEAU_tagCacheNodeIdentifier@@@Z; DuplicateCredentialData(_USER_CACHE_ENTRY *,_AP_BLOB *,_tagCacheNodeIdentifier *)
0x18003747c  xor     ecx, ecx
0x18003747e  mov     ebx, eax
0x180037480  test    eax, eax
0x180037482  jz      short loc_1800374D4
0x180037484  lea     rdi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18003748b  mov     rcx, rdi; char *
0x18003748e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180037493  lea     r14, Class
0x18003749a  mov     [rsp+230h+var_200], r14
0x18003749f  lea     rcx, aDuplicatecrede; "DuplicateCredentialData"
0x1800374a6  mov     [rsp+230h+var_208], rcx
0x1800374ab  mov     dword ptr [rsp+230h+var_210], 0E1Eh
0x1800374b3  lea     rsi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800374ba  mov     r8d, ebx
0x1800374bd  mov     r9, rax
0x1800374c0  mov     rdx, rsi
0x1800374c3  xor     ecx, ecx
0x1800374c5  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800374ca  mov     r13, [rsp+230h+var_1D8]
0x1800374cf  jmp     loc_180038AD1
0x1800374d4  lea     r12, [r15+168h]
0x1800374db  mov     [rbp+130h+var_138], ecx
0x1800374de  mov     rax, [r12]
0x1800374e2  mov     qword ptr [rbp+130h+var_170], rax
0x1800374e6  mov     rax, [r12+8]
0x1800374eb  mov     [rbp+130h+var_168], rax
0x1800374ef  test    rax, rax
0x1800374f2  jz      short loc_1800374F8
0x1800374f4  lock inc dword ptr [rax+8]
0x1800374f8  lea     rcx, [rbp+130h+var_170]
0x1800374fc  call    ?IncrementSharedPtrAtomicCounter@@YAXV?$shared_ptr@U?$atomic@K@utl@@@utl@@@Z; IncrementSharedPtrAtomicCounter(utl::shared_ptr<utl::atomic<ulong>>)
0x180037501  mov     rcx, r15; struct _USER_CACHE_ENTRY *
0x180037504  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x180037509  mov     rcx, [r14+8]
0x18003750d  lea     rax, [rbp+130h+var_130]
0x180037511  mov     [rsp+230h+var_200], rax
0x180037516  lea     r9, [rbp+130h+var_C0]
0x18003751a  lea     rax, [rsp+230h+var_1B8]
0x18003751f  mov     r8, rsi
0x180037522  mov     [rsp+230h+var_208], rax
0x180037527  mov     edx, edi
0x180037529  lea     rax, [rbp+130h+var_148]
0x18003752d  mov     [rsp+230h+var_210], rax
0x180037532  mov     rax, [r14+0F8h]
0x180037539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003753e  mov     ebx, eax
0x180037540  mov     rcx, [rsp+230h+var_1B8]
0x180037545  xor     edi, edi
0x180037547  test    rcx, rcx
0x18003754a  jz      short loc_18003755E
0x18003754c  mov     eax, [rcx+80h]
0x180037552  mov     [rbp+130h+var_138], eax
0x180037555  and     eax, 0FFFFFFFBh
0x180037558  mov     [rcx+80h], eax
0x18003755e  mov     dl, 1; bool
0x180037560  mov     rcx, r15; struct _USER_CACHE_ENTRY *
0x180037563  call    ?LockAndUnProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@_N@Z; LockAndUnProtectUserCacheEntry(_USER_CACHE_ENTRY *,bool)
0x180037568  mov     rax, [r12]
0x18003756c  mov     qword ptr [rbp+130h+var_170], rax
0x180037570  mov     rax, [r12+8]
0x180037575  mov     [rbp+130h+var_168], rax
0x180037579  test    rax, rax
0x18003757c  jz      short loc_180037582
0x18003757e  lock inc dword ptr [rax+8]
0x180037582  lea     rcx, [rbp+130h+var_170]
0x180037586  call    ?DecrementSharedPtrAtomicCounter@@YAXV?$shared_ptr@U?$atomic@K@utl@@@utl@@@Z; DecrementSharedPtrAtomicCounter(utl::shared_ptr<utl::atomic<ulong>>)
0x18003758b  test    ebx, ebx
0x18003758d  jns     short loc_1800375E6
0x18003758f  cmp     ebx, 0C0000071h
0x180037595  jnz     short loc_1800375A6
0x180037597  mov     rcx, [rbp+130h+var_B0]
0x18003759e  mov     rax, [rsp+230h+var_1B8]
0x1800375a3  mov     [rcx], rax
0x1800375a6  mov     dword ptr [rbp+130h+var_148], edi
0x1800375a9  mov     qword ptr [rbp+130h+var_148+8], rdi
0x1800375ad  mov     [rsp+230h+var_1B8], rdi
0x1800375b2  lea     rdi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800375b9  mov     rcx, rdi; char *
0x1800375bc  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800375c1  lea     r14, Class
0x1800375c8  mov     [rsp+230h+var_200], r14
0x1800375cd  lea     rcx, aGettoken; "GetToken"
0x1800375d4  mov     [rsp+230h+var_208], rcx
0x1800375d9  mov     dword ptr [rsp+230h+var_210], 0E48h
0x1800375e1  jmp     loc_1800374B3
0x1800375e6  cmp     [rsp+230h+var_1E0], dil
0x1800375eb  jz      short loc_180037667
0x1800375ed  mov     rdx, [rbp+130h+Token]; Token
0x1800375f1  xor     ecx, ecx; Thread
0x1800375f3  call    cs:__imp_SetThreadToken
0x1800375f9  test    eax, eax
0x1800375fb  jnz     short loc_180037662
0x1800375fd  call    cs:__imp_GetLastError
0x180037603  mov     ebx, eax
0x180037605  test    eax, eax
0x180037607  jle     short loc_180037612
0x180037609  movzx   ebx, ax
0x18003760c  or      ebx, 0C0070000h
0x180037612  lea     rdi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180037619  mov     rcx, rdi; char *
0x18003761c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180037621  lea     r14, Class
0x180037628  mov     [rsp+230h+var_200], r14
0x18003762d  lea     r12, aSetthreadtoken; "SetThreadToken"
0x180037634  mov     [rsp+230h+var_208], r12
0x180037639  lea     rsi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180037640  mov     dword ptr [rsp+230h+var_210], 0E51h
0x180037648  mov     r8d, ebx
0x18003764b  mov     r9, rax
0x18003764e  mov     rdx, rsi
0x180037651  xor     ecx, ecx
0x180037653  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180037658  mov     r13, [rsp+230h+var_1D8]
0x18003765d  jmp     loc_180038ADF
0x180037662  mov     [rsp+230h+var_1E0], dil
0x180037667  mov     rax, [rsp+230h+var_1B8]
0x18003766c  mov     rcx, [rax+40h]; Src
0x180037670  test    rcx, rcx
0x180037673  jz      short loc_180037689
0x180037675  cmp     [rcx], di
0x180037678  jz      short loc_180037689
0x18003767a  lea     r8, [rbp+130h+SourceString]; unsigned __int16 **
0x18003767e  xor     edx, edx; int
0x180037680  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x180037685  mov     ebx, eax
0x180037687  jmp     short loc_180037694
0x180037689  mov     rcx, [r15+58h]
0x18003768d  test    rcx, rcx
0x180037690  jnz     short loc_18003767A
0x180037692  mov     eax, ebx
0x180037694  test    eax, eax
0x180037696  jz      short loc_1800376CC
0x180037698  lea     rdi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18003769f  mov     rcx, rdi; char *
0x1800376a2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800376a7  lea     r14, Class
0x1800376ae  mov     [rsp+230h+var_200], r14
0x1800376b3  lea     rcx, aDuplicatestrin_4; "DuplicateString(NewName)"
0x1800376ba  mov     [rsp+230h+var_208], rcx
0x1800376bf  mov     dword ptr [rsp+230h+var_210], 0E74h
0x1800376c7  jmp     loc_1800374B3
0x1800376cc  mov     dl, 1; Wait
0x1800376ce  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x1800376d5  call    cs:__imp_RtlAcquireResourceShared
0x1800376db  mov     rdx, [rsp+230h+var_1B8]
0x1800376e0  lea     r8, [rbp+130h+hKey]; phkResult
0x1800376e4  mov     rcx, [r14+160h]; hKey
0x1800376eb  mov     [rsp+230h+var_1D0], 1
0x1800376f0  mov     rdx, [rdx+10h]; void *
0x1800376f4  call    ?FindUserInCacheBySid@@YAJPEAUHKEY__@@PEAXPEAPEAU1@@Z; FindUserInCacheBySid(HKEY__ *,void *,HKEY__ * *)
0x1800376f9  lea     rcx, [rbp+130h+var_170]
0x1800376fd  mov     [rbp+130h+var_170], eax
0x180037700  mov     ebx, eax
0x180037702  call    ??$FindUserInCacheBySid@AEAJ@CloudAPProvider@@SAXAEAJ@Z; CloudAPProvider::FindUserInCacheBySid<long &>(long &)
0x180037707  test    ebx, ebx
0x180037709  js      loc_180037856
0x18003770f  mov     rcx, [rbp+130h+hKey]; hkey
0x180037713  lea     rax, [rbp+130h+var_108]
0x180037717  lea     r9, [rbp+130h+var_170]; unsigned int *
0x18003771b  mov     [rsp+230h+var_210], rax; void **
0x180037720  mov     r8d, 6; dwFlags
0x180037726  mov     [rbp+130h+var_170], edi
0x180037729  lea     rdx, aIdentityname; "IdentityName"
0x180037730  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x180037735  mov     ecx, 80000000h
0x18003773a  mov     ebx, eax
0x18003773c  add     eax, ecx
0x18003773e  test    ecx, eax
0x180037740  jnz     short loc_18003777E
0x180037742  cmp     ebx, 0C0000225h
0x180037748  jz      short loc_18003777E
0x18003774a  lea     rdi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180037751  mov     rcx, rdi; char *
0x180037754  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180037759  lea     r14, Class
0x180037760  mov     [rsp+230h+var_200], r14
  ... truncated ...
```
