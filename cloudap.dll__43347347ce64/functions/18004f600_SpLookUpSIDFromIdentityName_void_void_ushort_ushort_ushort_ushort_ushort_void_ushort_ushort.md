# SpLookUpSIDFromIdentityName(void *,void *,ushort *,ushort *,ushort * *,ushort * *,ushort * *,void * *,ushort * *,ushort * *)

- ea: `0x18004f600`
- end: `0x1800510ec`
- name: `?SpLookUpSIDFromIdentityName@@YAJPEAX0PEAG1PEAPEAG22PEAPEAX22@Z`
- size: `6892`
- prototype: `int(void *, void *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, void **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003e70`
- `0x180004634`
- `0x18000498c`
- `0x180007690`
- `0x180007fc0`
- `0x180009a10`
- `0x18000a600`
- `0x18000a8f0`
- `0x18000b0c0`
- `0x18000b9b0`
- `0x18000e900`
- `0x18000ee60`
- `0x180014aa0`
- `0x18002ea68`
- `0x18002fd40`
- `0x1800307d0`
- `0x180031260`
- `0x1800335d4`
- `0x180033e80`
- `0x180042410`
- `0x18004317c`
- `0x18004e3b4`
- `0x18004e6ec`
- `0x18004f600`
- `0x1800510f4`
- `0x180081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004f8dc`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800501fd`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180050904`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004f8dc`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800501fd`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180050904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800500c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005079c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800500c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005079c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800500ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180050792`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800500ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180050792`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fb6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050fea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fb6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050fea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004febb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800505a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004febb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800505a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005102b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005102b`
- `ntdll!RtlReleaseResource` at `0x18004fb7c`
- `ntdll!RtlReleaseResource` at `0x1800508e4`
- `ntdll!RtlReleaseResource` at `0x1800509a8`
- `ntdll!RtlReleaseResource` at `0x18004fb7c`
- `ntdll!RtlReleaseResource` at `0x1800508e4`
- `ntdll!RtlReleaseResource` at `0x1800509a8`
- `ntdll!RtlAcquireResourceShared` at `0x18004f9c0`
- `ntdll!RtlAcquireResourceShared` at `0x18004fdde`
- `ntdll!RtlAcquireResourceShared` at `0x1800504c4`
- `ntdll!RtlAcquireResourceShared` at `0x18004f9c0`
- `ntdll!RtlAcquireResourceShared` at `0x18004fdde`
- `ntdll!RtlAcquireResourceShared` at `0x1800504c4`

## string_xrefs

- `0x18004f78f`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004f7dd`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004f81f`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004f873`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004f8e2`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180050eb3`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180050eed`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004fe14`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18004fe75`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18004fecb`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18004ff23`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18004ff5a`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x1800504fa`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005055b`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x1800505b1`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180050609`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180050640`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18004fe50`: `Name2Sid`
- `0x180050536`: `Name2Sid`
- `0x18005015e`: `DuplicateSID`
- `0x180050021`: `FindUserInCacheByName`
- `0x18005097a`: `FindUserInCacheByName`
- `0x18004f83f`: `Surrogate plugin`
- `0x18004feda`: `RegOpenKeyExW`
- `0x1800505c0`: `RegOpenKeyExW`
- `0x1800500e3`: `ConvertStringSidToSid`
- `0x1800507bb`: `ConvertStringSidToSid`
- `0x18004f922`: `SAM account passed to shadow account plugin `
- `0x18004f9fe`: `FindUserInCacheBySAMName`
- `0x18004fba8`: `FindUserInCacheBySAMName`
- `0x18004fb3b`: `Non UPN name not found in cache`
- `0x180050222`: `Cached SAM Name is invalid`
- `0x18005092d`: `Cached SAM Name is invalid`
- `0x180050a8e`: `LookupSIDFromIdentityName`
- `0x180050d1b`: `UpdateSidNameCaches`
- `0x180050e94`: `Name-SID cannot be resolved`

## pseudocode

```c
__int64 __fastcall SpLookUpSIDFromIdentityName(
        void *a1,
        void *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7,
        void **a8,
        unsigned __int16 **a9,
        unsigned __int16 **a10)
{
  wchar_t *v14; // r13
  void **v15; // rax
  unsigned __int16 **v16; // rdx
  unsigned __int16 **v17; // rcx
  unsigned int RegVal; // ebx
  const char *v19; // r9
  __int64 v20; // r8
  struct _ApPluginPkg *v21; // rdi
  int v22; // esi
  const char *v23; // rax
  wchar_t *v24; // r15
  unsigned __int16 *v25; // rbx
  char v26; // r12
  __int64 v27; // r8
  const char *v28; // r9
  int v29; // eax
  HKEY v30; // rbx
  unsigned int UserInCacheBySAMName; // eax
  const char *v32; // rax
  __int64 v33; // r8
  __int64 v34; // r10
  int v35; // ecx
  const char *v36; // r14
  LPCWSTR v37; // rdi
  const char *v38; // rax
  char v39; // r14
  const char *v40; // rax
  const char *v41; // rax
  struct _ApPluginPkg *v42; // r12
  const char *v43; // r9
  unsigned __int16 *v44; // rcx
  struct _ApPluginPkg *v45; // rbx
  const unsigned __int16 *v46; // r14
  HKEY v47; // r12
  const char *v48; // r9
  __int64 v49; // r8
  const char *v50; // rax
  UCHAR *v51; // rax
  unsigned __int16 *v52; // rcx
  const char *v53; // rax
  DWORD LastError; // ebx
  const char *v55; // rax
  __int64 v56; // r8
  const char *v57; // rax
  const char *v58; // rax
  __int64 v59; // r8
  const char *v60; // rax
  unsigned __int16 *v61; // rcx
  struct _ApPluginPkg *v62; // rbx
  const unsigned __int16 *v63; // r14
  HKEY v64; // r12
  const char *v65; // r9
  __int64 v66; // r8
  const char *v67; // rax
  UCHAR *v68; // rax
  unsigned __int16 *v69; // rcx
  const char *v70; // rax
  DWORD v71; // ebx
  const char *v72; // rax
  __int64 v73; // r8
  const char *v74; // rax
  const char *v75; // rax
  __int64 v76; // r8
  const char *v77; // rax
  char v78; // r14
  __int64 (__fastcall *v79)(_QWORD, void *, unsigned __int16 *, void **, void **, __int64 *, __int64 *, unsigned __int16 **, unsigned __int16 **, __int64 *, unsigned __int16 **); // rax
  const char *v80; // rax
  bool v81; // bl
  const char *v82; // rax
  unsigned __int16 *v83; // r14
  const char *v84; // rax
  bool v85; // r10
  HKEY v86; // r11
  const char *v87; // rax
  void *v88; // rax
  PCWSTR v89; // rax
  unsigned __int16 **v90; // rcx
  unsigned __int16 *v91; // rax
  const char *v92; // r9
  __int64 v93; // r8
  const char *v94; // r9
  __int64 v95; // r8
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultc; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultd; // [rsp+20h] [rbp-E0h]
  const char *v102; // [rsp+28h] [rbp-D8h]
  const char *v103; // [rsp+28h] [rbp-D8h]
  const char *v104; // [rsp+28h] [rbp-D8h]
  const char *v105; // [rsp+28h] [rbp-D8h]
  const char *v106; // [rsp+28h] [rbp-D8h]
  const WCHAR *v107; // [rsp+30h] [rbp-D0h]
  WCHAR *v108; // [rsp+30h] [rbp-D0h]
  WCHAR *v109; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *lpSrcStr; // [rsp+60h] [rbp-A0h]
  char v111; // [rsp+68h] [rbp-98h]
  struct _ApPluginPkg *v112; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR SourceString; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *Str; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v115; // [rsp+88h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  int v117; // [rsp+98h] [rbp-68h]
  struct _ApPluginSubPkg *v118; // [rsp+A0h] [rbp-60h] BYREF
  PUCHAR pbInput; // [rsp+A8h] [rbp-58h] BYREF
  void *v120; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *Src; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v122; // [rsp+C0h] [rbp-40h] BYREF
  LPCWSTR StringSid; // [rsp+C8h] [rbp-38h] BYREF
  void *v124; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v125; // [rsp+D8h] [rbp-28h]
  PSID Sid; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v127; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v128; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v129; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v130; // [rsp+100h] [rbp+0h] BYREF
  __int64 v131; // [rsp+108h] [rbp+8h] BYREF
  void **v132; // [rsp+110h] [rbp+10h]
  unsigned __int16 **v133; // [rsp+118h] [rbp+18h]
  unsigned __int16 **v134; // [rsp+120h] [rbp+20h]
  unsigned __int16 **v135; // [rsp+128h] [rbp+28h]
  void *v136; // [rsp+130h] [rbp+30h]
  unsigned __int16 **v137; // [rsp+138h] [rbp+38h]
  unsigned __int16 **v138; // [rsp+140h] [rbp+40h]
  _QWORD v139[4]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v140[16]; // [rsp+170h] [rbp+70h] BYREF
  void *v141; // [rsp+180h] [rbp+80h]
  void *v142; // [rsp+198h] [rbp+98h]
  __int64 v143; // [rsp+1A0h] [rbp+A0h]
  __int64 v144; // [rsp+1A8h] [rbp+A8h]
  unsigned __int16 *v145; // [rsp+1B8h] [rbp+B8h]
  unsigned __int16 *v146; // [rsp+1C0h] [rbp+C0h]
  __int64 v147; // [rsp+1C8h] [rbp+C8h]
  struct _GUID v148; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v149[72]; // [rsp+210h] [rbp+110h] BYREF
  WCHAR SubKey[80]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR v151[80]; // [rsp+340h] [rbp+240h] BYREF
  unsigned __int16 v152[72]; // [rsp+3E0h] [rbp+2E0h] BYREF

  v133 = a5;
  v135 = a9;
  v136 = a2;
  v132 = a8;
  v134 = a10;
  v125 = a4;
  v138 = a6;
  v137 = a7;
  v148 = 0;
  memset_0(v140, 0, 0x88u);
  SourceString = 0;
  Str = 0;
  v14 = 0;
  v115 = 0;
  pbInput = 0;
  Src = 0;
  v112 = 0;
  v118 = 0;
  hKey = 0;
  StringSid = 0;
  v120 = 0;
  Sid = 0;
  v124 = 0;
  v129 = 0;
  v130 = 0;
  v127 = 0;
  v128 = 0;
  v131 = 0;
  v122 = 0;
  if ( !a5 || !a6 || !a7 || (v15 = v132) == 0 || (v16 = v134) == 0 || (v17 = v135) == 0 )
  {
    RegVal = -1073741811;
    v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    v102 = "Invalid Arg(s)";
    phkResulta = 243;
    goto LABEL_247;
  }
  *v133 = 0;
  *a6 = 0;
  *a7 = 0;
  *v15 = 0;
  *v16 = 0;
  *v17 = 0;
  if ( !a1 || !a2 || !a4 || !*a4 )
  {
    RegVal = -1073741811;
    v94 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v95, v94, 259, "Invalid Arg(s)", &Class);
LABEL_248:
    v24 = 0;
    goto LABEL_249;
  }
  RegVal = (*((__int64 (__fastcall **)(void *, struct _GUID *))g_pLsaIdProvHostFunctionTable + 10))(a1, &v148);
  if ( RegVal )
  {
    v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    v102 = "GetProvInfo";
    phkResulta = 263;
LABEL_13:
    v20 = RegVal;
LABEL_247:
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v20, v19, phkResulta, v102, &Class);
    goto LABEL_248;
  }
  RegVal = RefPackage(&v148, &v112);
  if ( RegVal )
  {
    v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    v102 = "RefPackage";
    phkResulta = 266;
    goto LABEL_13;
  }
  v21 = v112;
  v22 = *((_DWORD *)v112 + 40);
  if ( (v22 & 4) != 0 )
  {
    RegVal = -1073741637;
    v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    v102 = "Surrogate plugin";
    phkResulta = 272;
    goto LABEL_13;
  }
  RegVal = DuplicateString(a4, 1, &Str);
  if ( !RegVal )
  {
    v25 = Str;
    v117 = v22 & 1;
    v111 = 0;
    lpSrcStr = Str;
    v26 = 0;
    if ( wcschr(Str, 0x40u) )
    {
      v39 = 0;
    }
    else
    {
      if ( (*((_BYTE *)v21 + 160) & 1) != 0 )
      {
        RegVal = -1073741709;
        v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        v107 = &Class;
        v103 = "SAM account passed to shadow account plugin ";
        LODWORD(phkResult) = 298;
LABEL_23:
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v27, v28, phkResult, v103, v107);
        v24 = lpSrcStr;
        goto LABEL_249;
      }
      v29 = RefSubPackage(v21, a3, &v118);
      RegVal = 0;
      if ( v29 != -2146893039 )
        RegVal = v29;
      if ( RegVal )
      {
        if ( !a3 )
          a3 = (unsigned __int16 *)&Class;
        v107 = a3;
        v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        v103 = "RefSubPackage";
        LODWORD(phkResult) = 308;
LABEL_30:
        v27 = RegVal;
        goto LABEL_23;
      }
      if ( v118 )
        v30 = (HKEY)*((_QWORD *)v118 + 74);
      else
        v30 = (HKEY)*((_QWORD *)v21 + 44);
      RtlAcquireResourceShared(&g_LookupsCacheLock, 1u);
      UserInCacheBySAMName = FindUserInCacheBySAMName(v30, lpSrcStr, &hKey);
      RegVal = UserInCacheBySAMName;
      if ( UserInCacheBySAMName == -1073741275 )
      {
        if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl) )
        {
          v41 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          v37 = &Class;
          v36 = "FindUserInCacheBySAMName";
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221226021LL, v41, 365, "FindUserInCacheBySAMName", &Class);
          RegVal = -1073741709;
          v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          v35 = 367;
          goto LABEL_194;
        }
        v40 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        WPPTraceLogA(2, "0x%08x %s:%u : %s:%ws", 3221226021LL, v40, 359, "Non UPN name not found in cache", v125);
        v25 = lpSrcStr;
        v39 = 1;
      }
      else
      {
        if ( UserInCacheBySAMName )
        {
          v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          v35 = 328;
          v36 = "FindUserInCacheBySAMName";
          v37 = &Class;
LABEL_194:
          v24 = lpSrcStr;
          goto LABEL_195;
        }
        LODWORD(Str) = 0;
        RegVal = GetRegVal(hKey, L"IdentityName", 6u, (unsigned int *)&Str, (void **)&Src);
        if ( (RegVal & 0x80000000) != 0 )
        {
          v38 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          v37 = &Class;
          v36 = "GetStringRegVal(IdentityName)";
          LODWORD(phkResult) = 338;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v38, phkResult, "GetStringRegVal(IdentityName)", &Class);
          if ( RegVal == -1073741275 )
            RegVal = -1073741709;
          v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          v35 = 343;
          goto LABEL_194;
        }
        ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(lpSrcStr);
        v39 = 1;
        Str = 0;
        RegVal = DuplicateString(Src, 1, &Str);
        if ( RegVal )
        {
          v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          v24 = Str;
          v36 = "DuplicateString";
          v35 = 351;
          v37 = &Class;
LABEL_195:
          LODWORD(phkResult) = v35;
          WPPTraceLogA(v34, "0x%08x %s:%u : %s:%ws", v33, v32, phkResult, v36, v37);
          RtlReleaseResource(&g_LookupsCacheLock);
          goto LABEL_249;
        }
        v25 = Str;
        v26 = 1;
        lpSrcStr = Str;
      }
      v111 = 1;
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      RtlReleaseResource(&g_LookupsCacheLock);
      DerefSubPackage((PRTL_RESOURCE *)v21, v118);
      v118 = 0;
    }
    LOBYTE(v117) = v117 ^ 1;
    v37 = &Class;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl) )
    {
      if ( v39 && !v26 || !v25 )
      {
LABEL_201:
        v78 = v117;
        if ( v120 && (!(_BYTE)v117 || v14) )
        {
          v42 = v112;
        }
        else
        {
          if ( v14 )
          {
            ((void (__fastcall *)(wchar_t *))g_pLsaFunctionTable->FreeLsaHeap)(v14);
            v14 = 0;
            v115 = 0;
          }
          v42 = v112;
          v79 = (__int64 (__fastcall *)(_QWORD, void *, unsigned __int16 *, void **, void **, __int64 *, __int64 *, unsigned __int16 **, unsigned __int16 **, __int64 *, unsigned __int16 **))*((_QWORD *)v112 + 34);
          if ( !v79 )
          {
            RegVal = -1073741709;
            v92 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
            LODWORD(phkResult) = 874;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v93, v92, phkResult, "Name-SID cannot be resolved", &Class);
            goto LABEL_58;
          }
          RegVal = v79(*((_QWORD *)v112 + 1), v136, v125, &v120, &v124, &v129, &v130, &v127, &v128, &v131, &v122);
          if ( (RegVal & 0x80000000) != 0 )
          {
            v120 = 0;
            v124 = 0;
            v129 = 0;
            v130 = 0;
            v127 = 0;
            v128 = 0;
            v131 = 0;
            v122 = 0;
            v80 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
            LODWORD(phkResult) = 760;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v80, phkResult, "LookupSIDFromIdentityName", &Class);
            if ( RegVal != -1073741801 && RegVal != -1073741670 && RegVal != -1073741822 )
              RegVal = -1073741709;
            v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
            v104 = "LookupSIDFromIdentityName";
            LODWORD(phkResult) = 768;
            goto LABEL_57;
          }
          v81 = 0;
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl) )
            v81 = (unsigned int)IsUserSidNameType(v122) != 0;
          if ( v78 )
          {
            if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl)
              || v81 )
            {
              v83 = lpSrcStr;
              RegVal = GetHashString(lpSrcStr, v152);
              if ( RegVal )
              {
                v104 = "DuplicateString";
                v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                LODWORD(phkResult) = 811;
                goto LABEL_57;
              }
              v141 = v120;
              v142 = v124;
              v143 = v129;
              v144 = v130;
              v145 = v127;
              v146 = v128;
              v147 = v131;
              DerefSubPackage((PRTL_RESOURCE *)v42, v118);
              v118 = 0;
              ((void (__fastcall *)(PCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(SourceString);
              SourceString = 0;
              RegVal = UpdateSidNameCaches(
                         v42,
                         &v118,
                         (unsigned __int16 **)&SourceString,
                         v152,
                         lpSrcStr,
                         (struct _APPLUGIN_USER_INFO *)v140,
                         0);
              if ( RegVal )
              {
                v84 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                LODWORD(phkResultc) = 839;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v84, phkResultc, "UpdateSidNameCaches", &Class);
              }
              else
              {
                v85 = 0;
                if ( v118 )
                  v86 = (HKEY)*((_QWORD *)v118 + 74);
                else
                  v86 = (HKEY)*((_QWORD *)v42 + 44);
                if ( (*((_BYTE *)v42 + 160) & 8) != 0 )
                {
                  v139[0] = v145;
                  v139[1] = v146;
                  v139[2] = v147;
                  if ( DoesUserHaveFederatedInfo(v139) )
                    v85 = 1;
                }
                RegVal = GenAndPersistNT4StyleName(
                           v85,
                           v86,
                           v120,
                           v152,
                           lpSrcStr,
                           (struct _APPLUGIN_USER_INFO *)v140,
                           &v115);
                if ( !RegVal )
                {
                  v14 = v115;
LABEL_243:
                  v88 = v120;
                  RegVal = 0;
                  v24 = 0;
                  v120 = 0;
                  *v132 = v88;
                  v89 = SourceString;
                  SourceString = 0;
                  *v133 = (unsigned __int16 *)v89;
                  v90 = v134;
                  *v137 = v83;
                  *v138 = v14;
                  v14 = 0;
                  *v90 = v122;
                  v91 = (unsigned __int16 *)v124;
                  v122 = 0;
                  v124 = 0;
                  *v135 = v91;
                  goto LABEL_250;
                }
                v87 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                LODWORD(phkResultd) = 866;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v87, phkResultd, "GenAndPersistNT4StyleName", &Class);
                v14 = v115;
              }
              v24 = lpSrcStr;
              goto LABEL_250;
            }
            if ( v127 )
            {
              RegVal = DuplicateString(v127, 1, &v115);
              if ( RegVal )
              {
                v82 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                LODWORD(phkResult) = 790;
                WPPTraceLogA(
                  0,
                  "0x%08x %s:%u : %s:%ws",
                  RegVal,
                  v82,
                  phkResult,
                  "DuplicateString pwszUserDownLevelName",
                  &Class);
                v14 = v115;
                goto LABEL_58;
              }
              v14 = v115;
            }
            if ( v128 )
            {
              RegVal = DuplicateString(v128, 1, (unsigned __int16 **)&SourceString);
              if ( RegVal )
              {
                v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                v104 = "DuplicateString pwszUserDomainNetBiosName";
                LODWORD(phkResult) = 798;
                goto LABEL_57;
              }
            }
            else
            {
              RegVal = DuplicateString((const unsigned __int16 *)v42 + 12, 0, (unsigned __int16 **)&SourceString);
              if ( RegVal )
              {
                v104 = "DuplicateString";
                v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                LODWORD(phkResult) = 803;
                goto LABEL_57;
              }
            }
          }
        }
        v83 = lpSrcStr;
        goto LABEL_243;
      }
      v42 = v112;
      RegVal = GetAuthenticatingAuthority(v112, v25, 0, (unsigned __int16 **)&SourceString);
      if ( RegVal )
      {
        v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        v104 = "GetAuthenticatingAuthority";
        LODWORD(phkResult) = 401;
LABEL_57:
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v43, phkResult, v104, &Class);
LABEL_58:
        v24 = lpSrcStr;
        goto LABEL_250;
      }
      if ( !SourceString )
      {
        if ( (g_ulTestFlags & 2) != 0 )
          goto LABEL_68;
        v44 = v125;
        if ( v39 )
          v44 = Src;
        RegVal = DuplicateStringPreRS2(v44, 1, (unsigned __int16 **)&pbInput);
        if ( RegVal )
        {
          v104 = "DuplicateStringPreRS2";
          v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          LODWORD(phkResult) = 414;
          goto LABEL_57;
        }
        RegVal = GetAuthenticatingAuthorityPreRS2((HKEY *)v42, pbInput, (unsigned __int16 **)&SourceString);
        if ( RegVal )
        {
          v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          v104 = "GetAuthenticatingAuthorityPreRS2";
          LODWORD(phkResult) = 421;
          goto LABEL_57;
        }
        if ( !SourceString )
        {
LABEL_68:
          RegVal = DuplicateString((const unsigned __int16 *)v42 + 12, 0, (unsigned __int16 **)&SourceString);
          if ( RegVal )
          {
            v104 = "DuplicateString";
            v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
            LODWORD(phkResult) = 428;
            goto LABEL_57;
          }
        }
      }
      v45 = v112;
      v46 = SourceString;
      if ( CloudAPCompareStrings(SourceString, (PCWSTR)v112 + 12) )
      {
        RegVal = RefSubPackage(v45, v46, &v118);
        if ( RegVal )
        {
          if ( v46 )
            v37 = v46;
          v107 = v37;
          v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          v103 = "RefSubPackage";
          LODWORD(phkResult) = 436;
          goto LABEL_30;
        }
        v47 = (HKEY)*((_QWORD *)v118 + 74);
      }
      else
      {
        v47 = (HKEY)*((_QWORD *)v45 + 44);
      }
      RtlAcquireResourceShared(&g_LookupsCacheLock, 1u);
      hKey = 0;
      if ( v47 && lpSrcStr )
      {
        RegVal = GetHashString(lpSrcStr, v149);
        if ( RegVal )
        {
          v108 = (WCHAR *)&Class;
          v48 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          v105 = "GetHashString";
          LODWORD(phkResult) = 1279;
        }
        else
        {
          RegVal = RtlStringCchPrintfW(SubKey, 0x4Au, L"%ws\\%ws", L"Name2Sid", v149);
          if ( RegVal )
          {
            v108 = (WCHAR *)&Class;
            v48 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
            v105 = "RtlStringCchPrintfW";
            LODWORD(phkResult) = 1287;
          }
          else
          {
            RegVal = RegOpenKeyExW(v47, SubKey, 0, 0x20019u, &hKey);
            if ( !RegVal )
            {
              RegVal = 0;
LABEL_93:
              if ( (g_ulTestFlags & 2) == 0 )
              {
                if ( RegVal != -1073741275 )
                {
LABEL_104:
                  if ( RegVal )
                  {
                    v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                    v35 = 480;
LABEL_106:
                    v36 = "FindUserInCacheByName";
                    goto LABEL_194;
                  }
                  LODWORD(Str) = 0;
                  v36 = "GetStringRegVal";
                  RegVal = GetRegVal(hKey, L"Sid", 6u, (unsigned int *)&Str, (void **)&StringSid);
                  if ( (RegVal & 0x80000000) != 0 )
                  {
                    v53 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                    LODWORD(phkResult) = 488;
                    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v53, phkResult, "GetStringRegVal", &Class);
                    if ( RegVal != -1073741275 )
                    {
                      v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                      v35 = 491;
                      goto LABEL_194;
                    }
                    goto LABEL_119;
                  }
                  if ( !ConvertStringSidToSidW(StringSid, &Sid) )
                  {
                    LastError = GetLastError();
                    v55 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                    LODWORD(phkResult) = 499;
                    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v55, phkResult, "ConvertStringSidToSid", v56);
                    if ( LastError == 14 )
                    {
                      RegVal = -1073283058;
                      if ( StringSid )
                        v37 = StringSid;
                      v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                      v35 = 503;
LABEL_115:
                      v36 = "ConvertStringSidToSid";
                      goto LABEL_194;
                    }
LABEL_119:
                    if ( (_BYTE)v117 )
                    {
                      LODWORD(Str) = 0;
                      RegVal = GetRegVal(hKey, L"SAMName", 6u, (unsigned int *)&Str, (void **)&v115);
                      if ( (RegVal & 0x80000000) == 0 )
                      {
                        v14 = v115;
                        if ( wcschr(v115, 0x40u) )
                        {
                          v58 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                          LODWORD(phkResultb) = 533;
                          WPPTraceLogA(
                            0,
                            "0x%08x %s:%u : %s:%ws",
                            3221225570LL,
                            v58,
                            phkResultb,
                            "Cached SAM Name is invalid",
                            v59);
                          ((void (__fastcall *)(wchar_t *))g_pLsaFunctionTable->FreeLsaHeap)(v14);
                          v14 = 0;
                          v115 = 0;
                        }
                      }
                      else
                      {
                        v57 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                        LODWORD(phkResultb) = 522;
                        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v57, phkResultb, "GetStringRegVal", &Class);
                        if ( RegVal != -1073741275 )
                        {
                          v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                          v35 = 525;
LABEL_193:
                          v14 = v115;
                          goto LABEL_194;
                        }
                        v14 = v115;
                      }
                    }
                    LODWORD(Str) = 0;
                    RegVal = GetRegVal(hKey, L"DisplayName", 6u, (unsigned int *)&Str, &v124);
                    if ( (RegVal & 0x80000000) != 0 )
                    {
                      v60 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                      LODWORD(phkResult) = 547;
                      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v60, phkResult, "GetStringRegVal", &Class);
                      if ( RegVal != -1073741275 )
                      {
                        v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                        v35 = 550;
                        goto LABEL_194;
                      }
                    }
                    RegVal = DuplicateString(L"user", 1, &v122);
                    if ( RegVal )
                    {
                      v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                      v35 = 556;
                      v36 = "DuplicateString";
                      goto LABEL_194;
                    }
                    goto LABEL_200;
                  }
                  RegVal = DuplicateSID(Sid, &v120);
                  if ( !RegVal )
                    goto LABEL_119;
                  v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                  v35 = 509;
LABEL_118:
                  v36 = "DuplicateSID";
                  goto LABEL_194;
                }
                v51 = pbInput;
                if ( !pbInput )
                {
                  v52 = v125;
                  if ( v111 )
                    v52 = Src;
                  RegVal = DuplicateStringPreRS2(v52, 1, (unsigned __int16 **)&pbInput);
                  if ( RegVal )
                  {
                    v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                    v35 = 468;
LABEL_100:
                    v36 = "DuplicateStringPreRS2";
                    goto LABEL_194;
                  }
                  v51 = pbInput;
                }
                RegVal = FindUserInCacheByNamePreRS2(v47, v51, &hKey);
              }
              if ( RegVal != -1073741275 )
                goto LABEL_104;
LABEL_200:
              RtlReleaseResource(&g_LookupsCacheLock);
              goto LABEL_201;
            }
            v50 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
            LODWORD(phkResult) = 1298;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v50, phkResult, "RegOpenKeyExW", SubKey);
            if ( RegVal - 2 <= 1 )
            {
              RegVal = -1073741275;
            }
            else if ( (int)RegVal > 0 )
            {
              RegVal = (unsigned __int16)RegVal | 0xC0070000;
            }
            v48 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
            v108 = SubKey;
            v105 = "RegOpenKeyExW";
            LODWORD(phkResult) = 1308;
          }
        }
        v49 = RegVal;
      }
      else
      {
        RegVal = -1073741811;
        v108 = (WCHAR *)&Class;
        v48 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        v105 = "Invalid Arg(s)";
        LODWORD(phkResult) = 1273;
      }
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v49, v48, phkResult, v105, v108);
      goto LABEL_93;
    }
    v42 = v112;
    RegVal = GetAuthenticatingAuthority(v112, v25, 0, (unsigned __int16 **)&SourceString);
    if ( RegVal )
    {
      v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
      v104 = "GetAuthenticatingAuthority";
      LODWORD(phkResult) = 571;
      goto LABEL_57;
    }
    if ( !SourceString )
    {
      if ( (g_ulTestFlags & 2) != 0 )
        goto LABEL_142;
      v61 = v125;
      if ( v39 )
        v61 = Src;
      RegVal = DuplicateStringPreRS2(v61, 1, (unsigned __int16 **)&pbInput);
      if ( RegVal )
      {
        v104 = "DuplicateStringPreRS2";
        v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        LODWORD(phkResult) = 584;
        goto LABEL_57;
      }
      RegVal = GetAuthenticatingAuthorityPreRS2((HKEY *)v42, pbInput, (unsigned __int16 **)&SourceString);
      if ( RegVal )
      {
        v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        v104 = "GetAuthenticatingAuthorityPreRS2";
        LODWORD(phkResult) = 591;
        goto LABEL_57;
      }
      if ( !SourceString )
      {
LABEL_142:
        RegVal = DuplicateString((const unsigned __int16 *)v42 + 12, 0, (unsigned __int16 **)&SourceString);
        if ( RegVal )
        {
          v104 = "DuplicateString";
          v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          LODWORD(phkResult) = 598;
          goto LABEL_57;
        }
      }
    }
    v62 = v112;
    v63 = SourceString;
    if ( CloudAPCompareStrings(SourceString, (PCWSTR)v112 + 12) )
    {
      RegVal = RefSubPackage(v62, v63, &v118);
      if ( RegVal )
      {
        if ( v63 )
          v37 = v63;
        v107 = v37;
        v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        v103 = "RefSubPackage";
        LODWORD(phkResult) = 606;
        goto LABEL_30;
      }
      v64 = (HKEY)*((_QWORD *)v118 + 74);
    }
    else
    {
      v64 = (HKEY)*((_QWORD *)v62 + 44);
    }
    RtlAcquireResourceShared(&g_LookupsCacheLock, 1u);
    hKey = 0;
    if ( v64 && lpSrcStr )
    {
      RegVal = GetHashString(lpSrcStr, v149);
      if ( RegVal )
      {
        v109 = (WCHAR *)&Class;
        v65 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        v106 = "GetHashString";
        LODWORD(phkResult) = 1279;
      }
      else
      {
        RegVal = RtlStringCchPrintfW(v151, 0x4Au, L"%ws\\%ws", L"Name2Sid", v149);
        if ( RegVal )
        {
          v109 = (WCHAR *)&Class;
          v65 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          v106 = "RtlStringCchPrintfW";
          LODWORD(phkResult) = 1287;
        }
        else
        {
          RegVal = RegOpenKeyExW(v64, v151, 0, 0x20019u, &hKey);
          if ( !RegVal )
          {
            RegVal = 0;
            goto LABEL_167;
          }
          v67 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          LODWORD(phkResult) = 1298;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v67, phkResult, "RegOpenKeyExW", v151);
          if ( RegVal - 2 <= 1 )
          {
            RegVal = -1073741275;
          }
          else if ( (int)RegVal > 0 )
          {
            RegVal = (unsigned __int16)RegVal | 0xC0070000;
          }
          v65 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          v109 = v151;
          v106 = "RegOpenKeyExW";
          LODWORD(phkResult) = 1308;
        }
      }
      v66 = RegVal;
    }
    else
    {
      RegVal = -1073741811;
      v109 = (WCHAR *)&Class;
      v65 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      v106 = "Invalid Arg(s)";
      LODWORD(phkResult) = 1273;
    }
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v66, v65, phkResult, v106, v109);
LABEL_167:
    if ( (g_ulTestFlags & 2) == 0 )
    {
      if ( RegVal != -1073741275 )
        goto LABEL_177;
      v68 = pbInput;
      if ( !pbInput )
      {
        v69 = v125;
        if ( v111 )
          v69 = Src;
        RegVal = DuplicateStringPreRS2(v69, 1, (unsigned __int16 **)&pbInput);
        if ( RegVal )
        {
          v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          v35 = 638;
          goto LABEL_100;
        }
        v68 = pbInput;
      }
      RegVal = FindUserInCacheByNamePreRS2(v64, v68, &hKey);
    }
    if ( RegVal == -1073741275 )
    {
      v77 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
      LODWORD(phkResult) = 713;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221226021LL, v77, phkResult, "FindUserInCacheByName", &Class);
      goto LABEL_200;
    }
LABEL_177:
    if ( RegVal )
    {
      v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
      v35 = 650;
      goto LABEL_106;
    }
    LODWORD(Str) = 0;
    v36 = "GetStringRegVal";
    RegVal = GetRegVal(hKey, L"Sid", 6u, (unsigned int *)&Str, (void **)&StringSid);
    if ( (RegVal & 0x80000000) == 0 )
    {
      if ( ConvertStringSidToSidW(StringSid, &Sid) )
      {
        RegVal = DuplicateSID(Sid, &v120);
        if ( RegVal )
        {
          v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          v35 = 679;
          goto LABEL_118;
        }
      }
      else
      {
        v71 = GetLastError();
        v72 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        LODWORD(phkResult) = 669;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v71, v72, phkResult, "ConvertStringSidToSid", v73);
        if ( v71 == 14 )
        {
          RegVal = -1073283058;
          if ( StringSid )
            v37 = StringSid;
          v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          v35 = 673;
          goto LABEL_115;
        }
      }
    }
    else
    {
      v70 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
      LODWORD(phkResult) = 658;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v70, phkResult, "GetStringRegVal", &Class);
      if ( RegVal != -1073741275 )
      {
        v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        v35 = 661;
        goto LABEL_194;
      }
    }
    if ( (_BYTE)v117 )
    {
      LODWORD(Str) = 0;
      RegVal = GetRegVal(hKey, L"SAMName", 6u, (unsigned int *)&Str, (void **)&v115);
      if ( (RegVal & 0x80000000) == 0 )
      {
        v14 = v115;
        if ( wcschr(v115, 0x40u) )
        {
          v75 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          LODWORD(phkResult) = 703;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225570LL, v75, phkResult, "Cached SAM Name is invalid", v76);
          ((void (__fastcall *)(wchar_t *))g_pLsaFunctionTable->FreeLsaHeap)(v14);
          v14 = 0;
          v115 = 0;
        }
      }
      else
      {
        v74 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        LODWORD(phkResult) = 692;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v74, phkResult, "GetStringRegVal", &Class);
        if ( RegVal != -1073741275 )
        {
          v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          v35 = 695;
          goto LABEL_193;
        }
        v14 = v115;
      }
    }
    goto LABEL_200;
  }
  v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v23, 283, "DuplicateString", &Class);
  v24 = Str;
LABEL_249:
  v42 = v112;
LABEL_250:
  DerefSubPackage((PRTL_RESOURCE *)v42, v118);
  DerefPackage(v42);
  if ( SourceString )
    ((void (__fastcall *)(PCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(SourceString);
  if ( v14 )
    ((void (__fastcall *)(wchar_t *))g_pLsaFunctionTable->FreeLsaHeap)(v14);
  if ( v24 )
    ((void (__fastcall *)(wchar_t *))g_pLsaFunctionTable->FreeLsaHeap)(v24);
  if ( pbInput )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( Src )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v122 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( hKey )
    RegCloseKey(hKey);
  if ( StringSid )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v120 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( Sid )
    LocalFree(Sid);
  if ( v124 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v129 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v130 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v127 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v128 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v131 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  return RegVal;
}

```

## disassembly

```asm
0x18004f600  push    rbp
0x18004f602  push    rbx
0x18004f603  push    rsi
0x18004f604  push    rdi
0x18004f605  push    r12
0x18004f607  push    r13
0x18004f609  push    r14
0x18004f60b  push    r15
0x18004f60d  lea     rbp, [rsp-388h]
0x18004f615  sub     rsp, 488h
0x18004f61c  mov     rax, cs:__security_cookie
0x18004f623  xor     rax, rsp
0x18004f626  mov     [rbp+3C0h+var_50], rax
0x18004f62d  mov     rax, [rbp+3C0h+arg_20]
0x18004f634  mov     rbx, rcx
0x18004f637  mov     rcx, [rbp+3C0h+arg_38]
0x18004f63e  mov     r14, r8
0x18004f641  mov     rsi, [rbp+3C0h+arg_28]
0x18004f648  mov     rdi, rdx
0x18004f64b  mov     r12, [rbp+3C0h+arg_30]
0x18004f652  xorps   xmm0, xmm0
0x18004f655  mov     [rbp+3C0h+var_3A8], rax
0x18004f659  mov     r8d, 88h; Size
0x18004f65f  mov     rax, [rbp+3C0h+arg_40]
0x18004f666  mov     r15, r9
0x18004f669  mov     [rbp+3C0h+var_398], rax
0x18004f66d  mov     rax, [rbp+3C0h+arg_48]
0x18004f674  mov     [rbp+3C0h+var_390], rdx
0x18004f678  xor     edx, edx; Val
0x18004f67a  mov     [rbp+3C0h+var_3B0], rcx
0x18004f67e  lea     rcx, [rbp+3C0h+var_350]; void *
0x18004f682  mov     [rbp+3C0h+var_3A0], rax
0x18004f686  mov     [rbp+3C0h+var_3E8], r9
0x18004f68a  mov     [rbp+3C0h+var_380], rsi
0x18004f68e  mov     [rbp+3C0h+var_388], r12
0x18004f692  movups  xmmword ptr [rbp+3C0h+var_2C0.Data1], xmm0
0x18004f699  call    memset_0
0x18004f69e  mov     r8, [rbp+3C0h+var_3A8]
0x18004f6a2  xor     r9d, r9d
0x18004f6a5  mov     [rsp+4C0h+SourceString], r9
0x18004f6aa  mov     eax, r9d
0x18004f6ad  mov     [rbp+3C0h+Str], rax
0x18004f6b1  mov     r13d, r9d
0x18004f6b4  mov     [rbp+3C0h+var_438], r9
0x18004f6b8  mov     [rbp+3C0h+pbInput], r9
0x18004f6bc  mov     [rbp+3C0h+Src], r9
0x18004f6c0  mov     [rsp+4C0h+var_450], r9
0x18004f6c5  mov     [rbp+3C0h+var_420], r9
0x18004f6c9  mov     [rbp+3C0h+hKey], r9
0x18004f6cd  mov     [rbp+3C0h+StringSid], r9
0x18004f6d1  mov     [rbp+3C0h+var_410], r9
0x18004f6d5  mov     [rbp+3C0h+Sid], r9
0x18004f6d9  mov     [rbp+3C0h+var_3F0], r9
0x18004f6dd  mov     [rbp+3C0h+var_3C8], r9
0x18004f6e1  mov     [rbp+3C0h+var_3C0], r9
0x18004f6e5  mov     [rbp+3C0h+var_3D8], r9
0x18004f6e9  mov     [rbp+3C0h+var_3D0], r9
0x18004f6ed  mov     [rbp+3C0h+var_3B8], r9
0x18004f6f1  mov     [rbp+3C0h+var_400], r9
0x18004f6f5  test    r8, r8
0x18004f6f8  jz      loc_180050EE7
0x18004f6fe  test    rsi, rsi
0x18004f701  jz      loc_180050EE7
0x18004f707  test    r12, r12
0x18004f70a  jz      loc_180050EE7
0x18004f710  mov     rax, [rbp+3C0h+var_3B0]
0x18004f714  test    rax, rax
0x18004f717  jz      loc_180050EE7
0x18004f71d  mov     rdx, [rbp+3C0h+var_3A0]
0x18004f721  test    rdx, rdx
0x18004f724  jz      loc_180050EE7
0x18004f72a  mov     rcx, [rbp+3C0h+var_398]
0x18004f72e  test    rcx, rcx
0x18004f731  jz      loc_180050EE7
0x18004f737  mov     [r8], r9
0x18004f73a  mov     [rsi], r9
0x18004f73d  mov     [r12], r9
0x18004f741  mov     [rax], r9
0x18004f744  mov     [rdx], r9
0x18004f747  mov     [rcx], r9
0x18004f74a  test    rbx, rbx
0x18004f74d  jz      loc_180050EAD
0x18004f753  test    rdi, rdi
0x18004f756  jz      loc_180050EAD
0x18004f75c  test    r15, r15
0x18004f75f  jz      loc_180050EAD
0x18004f765  cmp     r9w, [r15]
0x18004f769  jz      loc_180050EAD
0x18004f76f  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x18004f776  lea     rdx, [rbp+3C0h+var_2C0]
0x18004f77d  mov     rcx, rbx
0x18004f780  mov     rax, [rax+50h]
0x18004f784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f789  mov     ebx, eax
0x18004f78b  test    eax, eax
0x18004f78d  jz      short loc_18004F7C6
0x18004f78f  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004f796  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004f79b  mov     r9, rax
0x18004f79e  lea     rdi, Class
0x18004f7a5  mov     [rsp+4C0h+var_490], rdi
0x18004f7aa  lea     rax, aGetprovinfo; "GetProvInfo"
0x18004f7b1  mov     [rsp+4C0h+var_498], rax
0x18004f7b6  mov     dword ptr [rsp+4C0h+phkResult], 107h
0x18004f7be  mov     r8d, ebx
0x18004f7c1  jmp     loc_180050F1F
0x18004f7c6  lea     rdx, [rsp+4C0h+var_450]; struct _ApPluginPkg **
0x18004f7cb  lea     rcx, [rbp+3C0h+var_2C0]; struct _GUID *
0x18004f7d2  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x18004f7d7  mov     ebx, eax
0x18004f7d9  test    eax, eax
0x18004f7db  jz      short loc_18004F80E
0x18004f7dd  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004f7e4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004f7e9  mov     r9, rax
0x18004f7ec  lea     rdi, Class
0x18004f7f3  mov     [rsp+4C0h+var_490], rdi
0x18004f7f8  lea     rax, aRefpackage; "RefPackage"
0x18004f7ff  mov     [rsp+4C0h+var_498], rax
0x18004f804  mov     dword ptr [rsp+4C0h+phkResult], 10Ah
0x18004f80c  jmp     short loc_18004F7BE
0x18004f80e  mov     rdi, [rsp+4C0h+var_450]
0x18004f813  mov     esi, [rdi+0A0h]
0x18004f819  test    sil, 4
0x18004f81d  jz      short loc_18004F858
0x18004f81f  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004f826  mov     ebx, 0C00000BBh
0x18004f82b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004f830  mov     r9, rax
0x18004f833  lea     rdi, Class
0x18004f83a  mov     [rsp+4C0h+var_490], rdi
0x18004f83f  lea     rax, aSurrogatePlugi_0; "Surrogate plugin"
0x18004f846  mov     [rsp+4C0h+var_498], rax
0x18004f84b  mov     dword ptr [rsp+4C0h+phkResult], 110h
0x18004f853  jmp     loc_18004F7BE
0x18004f858  mov     r12d, 1
0x18004f85e  lea     r8, [rbp+3C0h+Str]; unsigned __int16 **
0x18004f862  mov     edx, r12d; int
0x18004f865  mov     rcx, r15; Src
0x18004f868  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18004f86d  mov     ebx, eax
0x18004f86f  test    eax, eax
0x18004f871  jz      short loc_18004F8BC
0x18004f873  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004f87a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004f87f  lea     rdi, Class
0x18004f886  mov     r9, rax
0x18004f889  mov     [rsp+4C0h+var_490], rdi
0x18004f88e  lea     r14, aDuplicatestrin_1; "DuplicateString"
0x18004f895  mov     [rsp+4C0h+var_498], r14
0x18004f89a  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004f8a1  mov     r8d, ebx
0x18004f8a4  mov     dword ptr [rsp+4C0h+phkResult], 11Bh
0x18004f8ac  xor     ecx, ecx
0x18004f8ae  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004f8b3  mov     r15, [rbp+3C0h+Str]
0x18004f8b7  jmp     loc_180050F30
0x18004f8bc  mov     rbx, [rbp+3C0h+Str]
0x18004f8c0  and     esi, r12d
0x18004f8c3  xor     al, al
0x18004f8c5  mov     [rbp+3C0h+var_428], esi
0x18004f8c8  mov     rcx, rbx; Str
0x18004f8cb  mov     [rsp+4C0h+var_458], al
0x18004f8cf  mov     edx, 40h ; '@'; Ch
0x18004f8d4  mov     [rsp+4C0h+lpSrcStr], rbx
0x18004f8d9  xor     r12b, r12b
0x18004f8dc  call    cs:__imp_wcschr
0x18004f8e2  lea     r15, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004f8e9  lea     rsi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004f8f0  test    rax, rax
0x18004f8f3  jnz     loc_18004FBEA
0x18004f8f9  test    byte ptr [rdi+0A0h], 1
0x18004f900  jz      short loc_18004F94A
0x18004f902  mov     r8d, 0C0000073h
0x18004f908  mov     rcx, r15; char *
0x18004f90b  mov     ebx, r8d
0x18004f90e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004f913  mov     r9, rax
0x18004f916  lea     rdi, Class
0x18004f91d  mov     [rsp+4C0h+var_490], rdi
0x18004f922  lea     rax, aSamAccountPass; "SAM account passed to shadow account pl"...
0x18004f929  mov     [rsp+4C0h+var_498], rax
0x18004f92e  mov     dword ptr [rsp+4C0h+phkResult], 12Ah
0x18004f936  mov     rdx, rsi
0x18004f939  xor     ecx, ecx
0x18004f93b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004f940  mov     r15, [rsp+4C0h+lpSrcStr]
0x18004f945  jmp     loc_180050F30
0x18004f94a  lea     r8, [rbp+3C0h+var_420]; struct _ApPluginSubPkg **
0x18004f94e  mov     rdx, r14; unsigned __int16 *
0x18004f951  mov     rcx, rdi; struct _ApPluginPkg *
0x18004f954  call    ?RefSubPackage@@YAJPEAU_ApPluginPkg@@PEBGPEAPEAU_ApPluginSubPkg@@@Z; RefSubPackage(_ApPluginPkg *,ushort const *,_ApPluginSubPkg * *)
0x18004f959  xor     ebx, ebx
0x18004f95b  cmp     eax, 80090311h
0x18004f960  cmovnz  ebx, eax
0x18004f963  test    ebx, ebx
0x18004f965  jz      short loc_18004F99E
0x18004f967  test    r14, r14
0x18004f96a  lea     rdi, Class
0x18004f971  mov     rcx, r15; char *
0x18004f974  cmovz   r14, rdi
0x18004f978  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004f97d  mov     [rsp+4C0h+var_490], r14
0x18004f982  mov     r9, rax
0x18004f985  lea     rax, aRefsubpackage; "RefSubPackage"
0x18004f98c  mov     [rsp+4C0h+var_498], rax
0x18004f991  mov     dword ptr [rsp+4C0h+phkResult], 134h
0x18004f999  mov     r8d, ebx
0x18004f99c  jmp     short loc_18004F936
0x18004f99e  mov     rax, [rbp+3C0h+var_420]
0x18004f9a2  test    rax, rax
0x18004f9a5  jz      short loc_18004F9B0
0x18004f9a7  mov     rbx, [rax+250h]
0x18004f9ae  jmp     short loc_18004F9B7
0x18004f9b0  mov     rbx, [rdi+160h]
0x18004f9b7  mov     dl, 1; Wait
0x18004f9b9  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18004f9c0  call    cs:__imp_RtlAcquireResourceShared
0x18004f9c6  mov     r14, [rsp+4C0h+lpSrcStr]
0x18004f9cb  lea     r8, [rbp+3C0h+hKey]; phkResult
0x18004f9cf  mov     rdx, r14; unsigned __int16 *
0x18004f9d2  mov     rcx, rbx; hKey
0x18004f9d5  call    ?FindUserInCacheBySAMName@@YAJPEAUHKEY__@@PEAGPEAPEAU1@@Z; FindUserInCacheBySAMName(HKEY__ *,ushort *,HKEY__ * *)
0x18004f9da  mov     ebx, eax
0x18004f9dc  cmp     eax, 0C0000225h
0x18004f9e1  jz      loc_18004FB09
0x18004f9e7  test    eax, eax
0x18004f9e9  jz      short loc_18004FA11
0x18004f9eb  xor     r10d, r10d
0x18004f9ee  mov     rcx, r15; char *
0x18004f9f1  mov     r8d, eax
0x18004f9f4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004f9f9  mov     ecx, 148h
0x18004f9fe  lea     r14, aFinduserincach_0; "FindUserInCacheBySAMName"
0x18004fa05  lea     rdi, Class
0x18004fa0c  jmp     loc_1800508BC
0x18004fa11  mov     rcx, [rbp+3C0h+hKey]; hkey
0x18004fa15  lea     rax, [rbp+3C0h+Src]
0x18004fa19  lea     r9, [rbp+3C0h+Str]; unsigned int *
0x18004fa1d  mov     [rsp+4C0h+phkResult], rax; void **
0x18004fa22  mov     r8d, 6; dwFlags
0x18004fa28  mov     dword ptr [rbp+3C0h+Str], r13d
0x18004fa2c  lea     rdx, aIdentityname; "IdentityName"
0x18004fa33  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x18004fa38  mov     ebx, eax
0x18004fa3a  test    eax, eax
0x18004fa3c  jns     short loc_18004FA9E
0x18004fa3e  mov     rcx, r15; char *
0x18004fa41  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004fa46  lea     rdi, Class
0x18004fa4d  mov     r9, rax
0x18004fa50  mov     [rsp+4C0h+var_490], rdi
0x18004fa55  lea     r14, aGetstringregva; "GetStringRegVal(IdentityName)"
0x18004fa5c  mov     [rsp+4C0h+var_498], r14
0x18004fa61  mov     r8d, ebx
0x18004fa64  mov     rdx, rsi
0x18004fa67  mov     dword ptr [rsp+4C0h+phkResult], 152h
0x18004fa6f  xor     ecx, ecx
0x18004fa71  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004fa76  cmp     ebx, 0C0000225h
0x18004fa7c  mov     r8d, 0C0000073h
0x18004fa82  mov     rcx, r15; char *
0x18004fa85  cmovz   ebx, r8d
0x18004fa89  xor     r10d, r10d
0x18004fa8c  mov     r8d, ebx
0x18004fa8f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004fa94  mov     ecx, 157h
0x18004fa99  jmp     loc_1800508BC
0x18004fa9e  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004faa5  mov     rcx, r14
0x18004faa8  mov     rax, [rax+30h]
0x18004faac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fab1  mov     rcx, [rbp+3C0h+Src]; Src
0x18004fab5  lea     r8, [rbp+3C0h+Str]; unsigned __int16 **
0x18004fab9  mov     r14d, 1
0x18004fabf  mov     [rbp+3C0h+Str], r13
0x18004fac3  mov     edx, r14d; int
0x18004fac6  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18004facb  mov     ebx, eax
0x18004facd  test    eax, eax
0x18004facf  jz      short loc_18004FAFB
0x18004fad1  xor     r10d, r10d
0x18004fad4  mov     rcx, r15; char *
0x18004fad7  mov     r8d, eax
0x18004fada  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004fadf  mov     r15, [rbp+3C0h+Str]
0x18004fae3  lea     r14, aDuplicatestrin_1; "DuplicateString"
0x18004faea  mov     ecx, 15Fh
0x18004faef  lea     rdi, Class
0x18004faf6  jmp     loc_1800508C1
0x18004fafb  mov     rbx, [rbp+3C0h+Str]
0x18004faff  mov     r12b, r14b
0x18004fb02  mov     [rsp+4C0h+lpSrcStr], rbx
0x18004fb07  jmp     short loc_18004FB5D
0x18004fb09  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support> `wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl(void)'::`2'::impl
0x18004fb10  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled(void)
0x18004fb15  mov     rcx, r15; char *
0x18004fb18  test    al, al
0x18004fb1a  jz      short loc_18004FB94
0x18004fb1c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
  ... truncated ...
```
