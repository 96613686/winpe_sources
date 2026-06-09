# CloudAPRenameAccount(void * *,_SECPKG_CLIENT_INFO *,void *,void *,ulong,void * *,ulong *)

- ea: `0x180048e60`
- end: `0x180049f46`
- name: `?CloudAPRenameAccount@@YAJPEAPEAXPEAU_SECPKG_CLIENT_INFO@@PEAX2K0PEAK@Z`
- size: `4326`
- prototype: `__int64 __fastcall(void **, struct _SECPKG_CLIENT_INFO *, char *, void *, unsigned int, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000477c`
- `0x180007690`
- `0x180007ef0`
- `0x180007fc0`
- `0x18000a600`
- `0x18000a8f0`
- `0x18000b0c0`
- `0x18000e7e0`
- `0x18000e900`
- `0x18000ee60`
- `0x18000f100`
- `0x1800293c0`
- `0x180032998`
- `0x18003fcdc`
- `0x180042410`
- `0x180048e60`
- `0x18005cd60`
- `0x180060e14`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800494c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800497a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800494c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800497a6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18004979c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18004979c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800494bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800494bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049e9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049e9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049352`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049352`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049ebe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049ebe`

## string_xrefs

- `0x1800492bd`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180049313`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180049365`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x1800493bd`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x1800493e0`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180048f34`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048fa7`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049011`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049065`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800490b1`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800490f9`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049157`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800491b3`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049235`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049427`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049483`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800494e0`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049565`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800495c8`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004963a`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800496a1`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800496ff`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049761`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800497be`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004985a`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800498b6`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800498e3`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049940`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800499c7`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049a2c`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049ab3`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049b17`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049b9a`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049c7a`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049ca7`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049cd4`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049d01`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049d2e`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049d5b`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049d88`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049e17`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180049e51`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800492ef`: `Name2Sid`
- `0x18004943b`: `FindUserInCacheByName`
- `0x180049374`: `RegOpenKeyExW`
- `0x180049e35`: `InvalidArg:pvProtocolSubmitBuffer`
- `0x18004902c`: `Deserialize<WlidPropertyBag>`
- `0x180049177`: `Account rename is only supported for shadow accounts`
- `0x1800491ce`: `CreateOrAcquireUserCacheEntry`
- `0x180049250`: `CreateEphemeralUserCacheEntry`
- `0x1800494f8`: `ConvertStringSidToSid`
- `0x180049579`: `AddEntryInLookupCacheEx`
- `0x1800495dc`: `RemoveUserFromName2SidCache`
- `0x180049d9c`: `RemoveUserFromName2SidCache`
- `0x1800497d2`: `MoveFileW`
- `0x18004986e`: `DeleteUnverifiedConnectedAccount`

## pseudocode

```c
__int64 __fastcall CloudAPRenameAccount(
        void **a1,
        struct _SECPKG_CLIENT_INFO *a2,
        char *a3,
        void *a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7)
{
  struct _ApPluginPkg *v8; // r12
  struct _USER_CACHE_ENTRY *v9; // r15
  LPCWSTR v10; // r14
  LPCWSTR v11; // r13
  unsigned int v12; // eax
  unsigned int WLIDProperty; // ebx
  const char *v14; // r9
  __int64 v15; // r13
  const char *v16; // rax
  const char *v17; // r9
  const char *v18; // r9
  const char *v19; // r9
  const char *v20; // r9
  const char *v21; // r9
  const char *v22; // r9
  const char *v23; // r9
  const WCHAR *v24; // rsi
  HKEY v25; // r14
  const WCHAR *v26; // rcx
  const char *v27; // rax
  __int64 v28; // r8
  __int64 v29; // r10
  const char *v30; // r11
  int v31; // ecx
  const char *v32; // r14
  const char *v33; // rax
  WCHAR *v34; // rdx
  const char *v35; // r9
  const char *v36; // r9
  LPCWSTR v37; // r14
  const char *v38; // r9
  PSID v39; // rcx
  const char *v40; // r9
  unsigned int v41; // eax
  const char *v42; // rax
  __int64 v43; // rax
  unsigned int v44; // ebx
  unsigned int v45; // r12d
  const char *v46; // r9
  unsigned __int64 v47; // r15
  const char *v48; // r9
  const char *v49; // r9
  const char *v50; // r9
  LPCWSTR v51; // rbx
  const char *v52; // rax
  __int64 v53; // r8
  int v54; // r15d
  int v55; // eax
  unsigned int v56; // eax
  const char *v57; // rax
  unsigned int v58; // eax
  const char *v59; // rax
  unsigned int v60; // eax
  const char *v61; // rax
  unsigned int v62; // eax
  const char *v63; // rax
  unsigned int v64; // eax
  const char *v65; // rax
  unsigned int v66; // eax
  const char *v67; // rax
  struct _USER_CACHE_ENTRY *v68; // rcx
  const char *v69; // r9
  unsigned int i; // edi
  const char *v71; // r9
  __int64 v72; // r8
  const char *v73; // r9
  __int64 v74; // r8
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultc; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultd; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulte; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultf; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultg; // [rsp+20h] [rbp-E0h]
  const char *SourceSid; // [rsp+28h] [rbp-D8h]
  char v85; // [rsp+50h] [rbp-B0h]
  struct _USER_CACHE_ENTRY *v86; // [rsp+58h] [rbp-A8h] BYREF
  struct _ApPluginPkg *v87; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v88; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v89; // [rsp+70h] [rbp-90h] BYREF
  int v90; // [rsp+74h] [rbp-8Ch] BYREF
  int v91; // [rsp+78h] [rbp-88h] BYREF
  int v92; // [rsp+7Ch] [rbp-84h] BYREF
  int v93; // [rsp+80h] [rbp-80h] BYREF
  struct _USER_CACHE_ENTRY *v94; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v95; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR StringSid; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+A0h] [rbp-60h]
  HKEY hKey; // [rsp+A8h] [rbp-58h] BYREF
  PSID Sid; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR lpNewFileName; // [rsp+B8h] [rbp-48h]
  __int64 v101; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v102; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v103; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR SubKey[80]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v105[72]; // [rsp+180h] [rbp+80h] BYREF

  v85 = 0;
  v8 = 0;
  v95 = 0;
  v9 = 0;
  v89 = 0;
  v10 = 0;
  v88 = 0;
  v11 = 0;
  v90 = 0;
  v101 = 0;
  v91 = 0;
  v102 = 0;
  v92 = 0;
  v103 = 0;
  v93 = 0;
  v87 = 0;
  v86 = 0;
  v94 = 0;
  hKey = 0;
  StringSid = 0;
  Sid = 0;
  lpExistingFileName = 0;
  lpNewFileName = 0;
  if ( !a3 || !a6 || !a7 || a5 < 0x1C )
  {
    WLIDProperty = -1073741811;
    v73 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v74, v73, 1996, "InvalidArg(s)", &Class);
    goto LABEL_124;
  }
  *a6 = 0;
  *a7 = 0;
  v12 = *((_DWORD *)a3 + 5);
  if ( v12 >= 0xFFFFFFE5 )
  {
    WLIDProperty = -1073741675;
    v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v14, 2005, "RtlDWordAdd", &Class);
    goto LABEL_124;
  }
  if ( !v12 || a5 != v12 + 27 )
  {
    WLIDProperty = -1073741811;
    v71 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v72, v71, 2011, "InvalidArg:pvProtocolSubmitBuffer", &Class);
    goto LABEL_124;
  }
  v15 = ((__int64 (__fastcall *)(__int64, struct _SECPKG_CLIENT_INFO *, char *, void *))g_pLsaFunctionTable->AllocateLsaHeap)(
          16,
          a2,
          a3,
          a4);
  if ( !v15 )
  {
    WLIDProperty = -1073741801;
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v16, 2019, "AllocateLsaHeap", &Class);
    v10 = StringSid;
    v11 = 0;
    goto LABEL_124;
  }
  WLIDProperty = Deserialize<_WlidPropertyBag>(a3 + 24, *((_DWORD *)a3 + 5));
  if ( !WLIDProperty )
  {
    WLIDProperty = GetWLIDProperty(v15, 0, &v95, &v89);
    if ( WLIDProperty )
    {
      v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v18, 2035, "GetWLIDProperty:UserOldEmailId", &Class);
      goto LABEL_117;
    }
    WLIDProperty = GetWLIDProperty(v15, 1, &v88, &v90);
    if ( WLIDProperty )
    {
      v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v19, 2042, "GetWLIDProperty:UserNewEmailId", &Class);
      goto LABEL_117;
    }
    WLIDProperty = RefPackage((struct _GUID *)(a3 + 4), &v87);
    if ( WLIDProperty )
    {
      v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v20, 2047, "RefPackage", &Class);
LABEL_19:
      v8 = v87;
      goto LABEL_117;
    }
    v8 = v87;
    if ( (*((_BYTE *)v87 + 160) & 1) == 0 )
    {
      WLIDProperty = -1073741637;
      v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        3221225659LL,
        v21,
        2052,
        "Account rename is only supported for shadow accounts",
        &Class);
      goto LABEL_117;
    }
    WLIDProperty = _CreateOrAcquireUserCacheEntry(0, (struct _GUID *)((char *)v87 + 68), v95, 0, &v86);
    if ( WLIDProperty )
    {
      v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(phkResult) = 2061;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v22, phkResult, "CreateOrAcquireUserCacheEntry", &Class);
LABEL_24:
      v9 = v86;
      goto LABEL_117;
    }
    v9 = v86;
    LockAndUnProtectUserCacheEntry(v86, 1);
    v85 = 1;
    WLIDProperty = _CreateOrAcquireUserCacheEntry(0, (struct _GUID *)((char *)v8 + 68), v88, 1, &v94);
    if ( WLIDProperty )
    {
      v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(phkResulta) = 2075;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v23, phkResulta, "CreateEphemeralUserCacheEntry", &Class);
      goto LABEL_117;
    }
    v24 = &Class;
    if ( !*((_QWORD *)v9 + 30) )
    {
      v25 = (HKEY)*((_QWORD *)v8 + 44);
      v26 = (const WCHAR *)*((_QWORD *)v9 + 12);
      hKey = 0;
      if ( !v25 || !v26 )
      {
        WLIDProperty = -1073741811;
        v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        v31 = 1273;
        v32 = "Invalid Arg(s)";
        goto LABEL_41;
      }
      WLIDProperty = GetHashString(v26, v105);
      if ( WLIDProperty )
      {
        v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        v31 = 1279;
        v32 = "GetHashString";
LABEL_41:
        v34 = (WCHAR *)&Class;
LABEL_42:
        LODWORD(phkResulta) = v31;
        WPPTraceLogA(v29, v30, v28, v27, phkResulta, v32, v34);
        v35 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        LODWORD(phkResultc) = 2087;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v35, phkResultc, "FindUserInCacheByName", &Class);
        goto LABEL_117;
      }
      WLIDProperty = RtlStringCchPrintfW(SubKey, 0x4Au, L"%ws\\%ws", L"Name2Sid", v105);
      if ( WLIDProperty )
      {
        v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        v31 = 1287;
        v32 = "RtlStringCchPrintfW";
        goto LABEL_41;
      }
      WLIDProperty = RegOpenKeyExW(v25, SubKey, 0, 0x20019u, &hKey);
      if ( WLIDProperty )
      {
        v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        v32 = "RegOpenKeyExW";
        LODWORD(phkResultb) = 1298;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v33, phkResultb, "RegOpenKeyExW", SubKey);
        if ( WLIDProperty - 2 <= 1 )
        {
          WLIDProperty = -1073741275;
        }
        else if ( (int)WLIDProperty > 0 )
        {
          WLIDProperty = (unsigned __int16)WLIDProperty | 0xC0070000;
        }
        v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        v34 = SubKey;
        v31 = 1308;
        goto LABEL_42;
      }
      v89 = 0;
      WLIDProperty = GetRegVal(hKey, L"Sid", 6u, &v89, (void **)&StringSid);
      if ( WLIDProperty )
      {
        v36 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        LODWORD(phkResultd) = 2093;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v36, phkResultd, "GetStringRegVal", &Class);
        goto LABEL_117;
      }
      v37 = StringSid;
      if ( !ConvertStringSidToSidW(StringSid, &Sid) )
      {
        WLIDProperty = GetLastError();
        if ( (int)WLIDProperty > 0 )
          WLIDProperty = (unsigned __int16)WLIDProperty | 0xC0070000;
        if ( v37 )
          v24 = v37;
        v38 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        LODWORD(phkResultd) = 2101;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v38, phkResultd, "ConvertStringSidToSid", v24);
        goto LABEL_117;
      }
    }
    v39 = Sid;
    if ( *((_QWORD *)v9 + 30) )
      v39 = (PSID)*((_QWORD *)v9 + 30);
    WLIDProperty = AddEntryInLookupCache(
                     *((HKEY *)v8 + 44),
                     0,
                     (const unsigned __int16 *)v8 + 12,
                     (const unsigned __int16 *)v94 + 52,
                     *((const unsigned __int16 **)v94 + 12),
                     v39,
                     0,
                     0,
                     0);
    if ( WLIDProperty )
    {
      v40 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(phkResulte) = 2116;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v40, phkResulte, "AddEntryInLookupCacheEx", &Class);
      goto LABEL_117;
    }
    v41 = _RemoveUserFromName2SidCache(*((HKEY *)v8 + 44), *((LPCWSTR *)v9 + 12), 0);
    WLIDProperty = v41;
    if ( v41 == -1073741801 || v41 == -1073741670 )
    {
      LODWORD(phkResulte) = 2126;
      v69 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v69, phkResulte, "RemoveUserFromName2SidCache", &Class);
      goto LABEL_117;
    }
    if ( v41 )
    {
      v42 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(phkResulte) = 2128;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v42, phkResulte, "RemoveUserFromName2SidCache", &Class);
    }
    v43 = -1;
    do
      ++v43;
    while ( *(_WORD *)(*((_QWORD *)v8 + 43) + 2 * v43) );
    v44 = v43 + 67;
    v45 = 2 * (v43 + 67);
    lpExistingFileName = (LPCWSTR)((__int64 (__fastcall *)(_QWORD, _QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(v45, 0);
    if ( !lpExistingFileName )
    {
      WLIDProperty = -1073741801;
      v46 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(phkResulte) = 2138;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v46, phkResulte, "AllocateLsaHeap", &Class);
      goto LABEL_19;
    }
    v47 = v44;
    WLIDProperty = RtlStringCchPrintfW(
                     (unsigned __int16 *)lpExistingFileName,
                     v44,
                     L"%ws\\%ws",
                     *((_QWORD *)v87 + 43),
                     (char *)v86 + 104);
    if ( WLIDProperty )
    {
      v48 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(phkResultf) = 2147;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v48, phkResultf, "RtlStringCchPrintfW", &Class);
LABEL_66:
      v8 = v87;
      goto LABEL_24;
    }
    lpNewFileName = (LPCWSTR)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(v45);
    if ( !lpNewFileName )
    {
      WLIDProperty = -1073741801;
      v49 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(phkResultf) = 2153;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v49, phkResultf, "AllocateLsaHeap", &Class);
      goto LABEL_66;
    }
    v8 = v87;
    WLIDProperty = RtlStringCchPrintfW(
                     (unsigned __int16 *)lpNewFileName,
                     v47,
                     L"%ws\\%ws",
                     *((_QWORD *)v87 + 43),
                     (char *)v94 + 104);
    if ( WLIDProperty )
    {
      v50 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      SourceSid = "RtlStringCchPrintfW";
      LODWORD(phkResultg) = 2162;
LABEL_71:
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v50, phkResultg, SourceSid, &Class);
      goto LABEL_24;
    }
    v51 = lpExistingFileName;
    if ( !MoveFileW(lpExistingFileName, lpNewFileName) )
    {
      GetLastError();
      v52 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(phkResultg) = 2170;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v53, v52, phkResultg, "MoveFileW", v51);
    }
    v54 = 2 * v90 + 2;
    v55 = (*((__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64, unsigned __int16 *, int))g_pLsaIdProvHostFunctionTable
           + 5))(
            *((_QWORD *)v8 + 2),
            v95,
            11,
            v88,
            v54);
    WLIDProperty = v55;
    if ( v55 < 0 )
    {
      if ( v55 != -1073741725 )
      {
        v50 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        SourceSid = "SaveUserInfo";
        LODWORD(phkResultg) = 2203;
        goto LABEL_71;
      }
      WLIDProperty = (*((__int64 (__fastcall **)(_QWORD, unsigned __int16 *))g_pLsaIdProvHostFunctionTable + 8))(
                       *((_QWORD *)v8 + 2),
                       v88);
      if ( WLIDProperty )
      {
        v50 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        SourceSid = "DeleteUnverifiedConnectedAccount";
        LODWORD(phkResultg) = 2190;
        goto LABEL_71;
      }
      WLIDProperty = (*((__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64, unsigned __int16 *, int))g_pLsaIdProvHostFunctionTable
                      + 5))(
                       *((_QWORD *)v8 + 2),
                       v95,
                       11,
                       v88,
                       v54);
      if ( WLIDProperty )
      {
        v50 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        SourceSid = "SaveUserInfo(retry)";
        LODWORD(phkResultg) = 2199;
        goto LABEL_71;
      }
    }
    v56 = GetWLIDProperty(v15, 2, &v101, &v91);
    WLIDProperty = v56;
    if ( v56 == -1073741801 || v56 == -1073741670 )
    {
      v50 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      SourceSid = "GetWLIDProperty:UserFirstName";
      LODWORD(phkResultg) = 2216;
      goto LABEL_71;
    }
    if ( v56 )
    {
      v57 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(phkResultg) = 2218;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v57, phkResultg, "GetWLIDProperty:UserFirstName", &Class);
    }
    if ( v101 )
    {
      v58 = (*((__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64))g_pLsaIdProvHostFunctionTable + 5))(
              *((_QWORD *)v8 + 2),
              v88,
              7);
      WLIDProperty = v58;
      if ( v58 == -1073741801 || v58 == -1073741670 )
      {
        v50 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        SourceSid = "SaveUserInfo:UserGivenName";
        LODWORD(phkResultg) = 2232;
        goto LABEL_71;
      }
      if ( v58 )
      {
        v59 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        LODWORD(phkResultg) = 2234;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v59, phkResultg, "SaveUserInfo:UserGivenName", &Class);
      }
    }
    v60 = GetWLIDProperty(v15, 3, &v102, &v92);
    WLIDProperty = v60;
    if ( v60 == -1073741801 || v60 == -1073741670 )
    {
      v50 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      SourceSid = "GetWLIDProperty:UserLastName";
      LODWORD(phkResultg) = 2246;
      goto LABEL_71;
    }
    if ( v60 )
    {
      v61 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(phkResultg) = 2248;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v61, phkResultg, "GetWLIDProperty:UserLastName", &Class);
    }
    if ( v102 )
    {
      v62 = (*((__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64))g_pLsaIdProvHostFunctionTable + 5))(
              *((_QWORD *)v8 + 2),
              v88,
              8);
      WLIDProperty = v62;
      if ( v62 == -1073741801 || v62 == -1073741670 )
      {
        v50 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        SourceSid = "SaveUserInfo:UserSurname";
        LODWORD(phkResultg) = 2262;
        goto LABEL_71;
      }
      if ( v62 )
      {
        v63 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        LODWORD(phkResultg) = 2264;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v63, phkResultg, "SaveUserInfo:UserSurname", &Class);
      }
    }
    v64 = GetWLIDProperty(v15, 4, &v103, &v93);
    WLIDProperty = v64;
    if ( v64 == -1073741801 || v64 == -1073741670 )
    {
      v50 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      SourceSid = "GetWLIDProperty:UserDisplayName";
      LODWORD(phkResultg) = 2276;
      goto LABEL_71;
    }
    if ( v64 )
    {
      v65 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(phkResultg) = 2278;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v65, phkResultg, "GetWLIDProperty:UserDisplayName", &Class);
    }
    if ( v103 )
    {
      v66 = (*((__int64 (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD))g_pLsaIdProvHostFunctionTable + 5))(
              *((_QWORD *)v8 + 2),
              v88,
              0);
      WLIDProperty = v66;
      if ( v66 == -1073741801 || v66 == -1073741670 )
      {
        v50 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        SourceSid = "SaveUserInfo:UserDisplayName";
        LODWORD(phkResultg) = 2292;
        goto LABEL_71;
      }
      if ( v66 )
      {
        v67 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        LODWORD(phkResultg) = 2294;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v67, phkResultg, "SaveUserInfo:UserDisplayName", &Class);
      }
    }
    v9 = v86;
    ((void (__fastcall *)(_QWORD))g_pLsaFunctionTable->FreeLsaHeap)(*((_QWORD *)v86 + 12));
    v68 = v94;
    WLIDProperty = 0;
    *((_QWORD *)v9 + 12) = *((_QWORD *)v94 + 12);
    *((_QWORD *)v68 + 12) = 0;
    *(_OWORD *)((char *)v9 + 104) = *(_OWORD *)((char *)v68 + 104);
    *(_OWORD *)((char *)v9 + 120) = *(_OWORD *)((char *)v68 + 120);
    *(_OWORD *)((char *)v9 + 136) = *(_OWORD *)((char *)v68 + 136);
    *(_OWORD *)((char *)v9 + 152) = *(_OWORD *)((char *)v68 + 152);
    *(_OWORD *)((char *)v9 + 168) = *(_OWORD *)((char *)v68 + 168);
    *(_OWORD *)((char *)v9 + 184) = *(_OWORD *)((char *)v68 + 184);
    *(_OWORD *)((char *)v9 + 200) = *(_OWORD *)((char *)v68 + 200);
    *(_OWORD *)((char *)v9 + 216) = *(_OWORD *)((char *)v68 + 216);
    *((_WORD *)v9 + 116) = *((_WORD *)v68 + 116);
    goto LABEL_117;
  }
  v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", WLIDProperty, v17, 2027, "Deserialize<WlidPropertyBag>", &Class);
LABEL_117:
  if ( *(_QWORD *)(v15 + 8) )
  {
    for ( i = 0; i < *(_DWORD *)v15; ++i )
      FreeMemory(*(void **)(*(_QWORD *)(v15 + 8) + 16LL * i + 8));
    FreeMemory(*(void **)(v15 + 8));
  }
  ((void (__fastcall *)(__int64))g_pLsaFunctionTable->FreeLsaHeap)(v15);
  v10 = StringSid;
  v11 = lpExistingFileName;
LABEL_124:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v10 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v10);
  LocalFree(Sid);
  if ( v11 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v11);
  if ( lpNewFileName )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v85 )
    UnlockAndProtectUserCacheEntry(v9);
  _ReleaseUserCacheEntry(0, v9);
  _ReleaseUserCacheEntry(0, v94);
  DerefPackage(v8);
  return WLIDProperty;
}

```

## disassembly

```asm
0x180048e60  push    rbp
0x180048e62  push    rbx
0x180048e63  push    rsi
0x180048e64  push    rdi
0x180048e65  push    r12
0x180048e67  push    r13
0x180048e69  push    r14
0x180048e6b  push    r15
0x180048e6d  lea     rbp, [rsp-128h]
0x180048e75  sub     rsp, 228h
0x180048e7c  mov     rax, cs:__security_cookie
0x180048e83  xor     rax, rsp
0x180048e86  mov     [rbp+160h+var_50], rax
0x180048e8d  mov     rax, [rbp+160h+arg_28]
0x180048e94  xor     esi, esi
0x180048e96  mov     rcx, [rbp+160h+arg_30]
0x180048e9d  mov     rdi, r8
0x180048ea0  mov     [rsp+260h+var_210], sil
0x180048ea5  mov     r12d, esi
0x180048ea8  mov     [rbp+160h+var_1D0], rsi
0x180048eac  mov     r15d, esi
0x180048eaf  mov     [rsp+260h+var_1F0], esi
0x180048eb3  mov     r14d, esi
0x180048eb6  mov     [rsp+260h+var_1F8], rsi
0x180048ebb  mov     r13d, esi
0x180048ebe  mov     [rsp+260h+var_1EC], esi
0x180048ec2  mov     [rbp+160h+var_1A0], rsi
0x180048ec6  mov     [rsp+260h+var_1E8], esi
0x180048eca  mov     [rbp+160h+var_198], rsi
0x180048ece  mov     [rsp+260h+var_1E4], esi
0x180048ed2  mov     [rbp+160h+var_190], rsi
0x180048ed6  mov     [rbp+160h+var_1E0], esi
0x180048ed9  mov     [rsp+260h+var_200], rsi
0x180048ede  mov     [rsp+260h+var_208], rsi
0x180048ee3  mov     [rbp+160h+var_1D8], rsi
0x180048ee7  mov     [rbp+160h+hKey], rsi
0x180048eeb  mov     [rbp+160h+StringSid], rsi
0x180048eef  mov     [rbp+160h+Sid], rsi
0x180048ef3  mov     [rbp+160h+lpExistingFileName], rsi
0x180048ef7  mov     [rbp+160h+lpNewFileName], rsi
0x180048efb  test    r8, r8
0x180048efe  jz      loc_180049E4B
0x180048f04  test    rax, rax
0x180048f07  jz      loc_180049E4B
0x180048f0d  test    rcx, rcx
0x180048f10  jz      loc_180049E4B
0x180048f16  cmp     [rbp+160h+arg_20], 1Ch
0x180048f1d  jb      loc_180049E4B
0x180048f23  mov     [rax], rsi
0x180048f26  mov     [rcx], esi
0x180048f28  mov     eax, [r8+14h]
0x180048f2c  lea     ecx, [rax+1Bh]
0x180048f2f  cmp     ecx, 1Bh
0x180048f32  jnb     short loc_180048F70
0x180048f34  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180048f3b  mov     ebx, 0C0000095h
0x180048f40  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180048f45  mov     r9, rax
0x180048f48  lea     rsi, Class
0x180048f4f  mov     qword ptr [rsp+260h+var_230], rsi
0x180048f54  lea     rax, aRtldwordadd; "RtlDWordAdd"
0x180048f5b  mov     [rsp+260h+SourceSid], rax
0x180048f60  mov     r8d, ebx
0x180048f63  mov     dword ptr [rsp+260h+phkResult], 7D5h
0x180048f6b  jmp     loc_180049E83
0x180048f70  test    eax, eax
0x180048f72  jz      loc_180049E11
0x180048f78  cmp     [rbp+160h+arg_20], ecx
0x180048f7e  jnz     loc_180049E11
0x180048f84  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180048f8b  mov     ecx, 10h
0x180048f90  mov     rax, [rax+28h]
0x180048f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f99  mov     r13, rax
0x180048f9c  test    rax, rax
0x180048f9f  jnz     short loc_180048FF6
0x180048fa1  mov     r14d, 0C0000017h
0x180048fa7  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180048fae  mov     ebx, r14d
0x180048fb1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180048fb6  mov     r9, rax
0x180048fb9  lea     rsi, Class
0x180048fc0  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x180048fc7  mov     qword ptr [rsp+260h+var_230], rsi
0x180048fcc  mov     [rsp+260h+SourceSid], rax
0x180048fd1  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180048fd8  mov     r8d, r14d
0x180048fdb  mov     dword ptr [rsp+260h+phkResult], 7E3h
0x180048fe3  xor     ecx, ecx
0x180048fe5  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180048fea  mov     r14, [rbp+160h+StringSid]
0x180048fee  mov     r13, r12
0x180048ff1  jmp     loc_180049E91
0x180048ff6  mov     edx, [rdi+14h]; BufferSize
0x180048ff9  lea     rcx, [rdi+18h]; Source
0x180048ffd  mov     r9, r13
0x180049000  call    ??$Deserialize@U_WlidPropertyBag@@@@YAJPEAEKP6AXPEAX1@ZPEAU_WlidPropertyBag@@@Z; Deserialize<_WlidPropertyBag>(uchar *,ulong,void (*)(void *,void *),_WlidPropertyBag *)
0x180049005  mov     ebx, eax
0x180049007  mov     r14d, 1
0x18004900d  test    eax, eax
0x18004900f  jz      short loc_18004904C
0x180049011  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180049018  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004901d  mov     r9, rax
0x180049020  lea     rsi, Class
0x180049027  mov     qword ptr [rsp+260h+var_230], rsi
0x18004902c  lea     rax, aDeserializeWli; "Deserialize<WlidPropertyBag>"
0x180049033  mov     [rsp+260h+SourceSid], rax
0x180049038  mov     dword ptr [rsp+260h+phkResult], 7EBh
0x180049040  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180049047  jmp     loc_180049DB3
0x18004904c  lea     r9, [rsp+260h+var_1F0]
0x180049051  xor     edx, edx
0x180049053  lea     r8, [rbp+160h+var_1D0]
0x180049057  mov     rcx, r13
0x18004905a  call    ?GetWLIDProperty@@YAJPEAU_WlidPropertyBag@@W4_WlidPropertyIndex@@PEAPEBGPEAK@Z; GetWLIDProperty(_WlidPropertyBag *,_WlidPropertyIndex,ushort const * *,ulong *)
0x18004905f  mov     ebx, eax
0x180049061  test    eax, eax
0x180049063  jz      short loc_180049096
0x180049065  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004906c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180049071  mov     r9, rax
0x180049074  lea     rsi, Class
0x18004907b  mov     qword ptr [rsp+260h+var_230], rsi
0x180049080  lea     rax, aGetwlidpropert_1; "GetWLIDProperty:UserOldEmailId"
0x180049087  mov     [rsp+260h+SourceSid], rax
0x18004908c  mov     dword ptr [rsp+260h+phkResult], 7F3h
0x180049094  jmp     short loc_180049040
0x180049096  lea     r9, [rsp+260h+var_1EC]
0x18004909b  mov     edx, r14d
0x18004909e  lea     r8, [rsp+260h+var_1F8]
0x1800490a3  mov     rcx, r13
0x1800490a6  call    ?GetWLIDProperty@@YAJPEAU_WlidPropertyBag@@W4_WlidPropertyIndex@@PEAPEBGPEAK@Z; GetWLIDProperty(_WlidPropertyBag *,_WlidPropertyIndex,ushort const * *,ulong *)
0x1800490ab  mov     ebx, eax
0x1800490ad  test    eax, eax
0x1800490af  jz      short loc_1800490E5
0x1800490b1  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800490b8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800490bd  mov     r9, rax
0x1800490c0  lea     rsi, Class
0x1800490c7  mov     qword ptr [rsp+260h+var_230], rsi
0x1800490cc  lea     rax, aGetwlidpropert_2; "GetWLIDProperty:UserNewEmailId"
0x1800490d3  mov     [rsp+260h+SourceSid], rax
0x1800490d8  mov     dword ptr [rsp+260h+phkResult], 7FAh
0x1800490e0  jmp     loc_180049040
0x1800490e5  lea     rcx, [rdi+4]; struct _GUID *
0x1800490e9  lea     rdx, [rsp+260h+var_200]; struct _ApPluginPkg **
0x1800490ee  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x1800490f3  mov     ebx, eax
0x1800490f5  test    eax, eax
0x1800490f7  jz      short loc_180049143
0x1800490f9  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180049100  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180049105  mov     r9, rax
0x180049108  lea     rsi, Class
0x18004910f  mov     qword ptr [rsp+260h+var_230], rsi
0x180049114  lea     rax, aRefpackage; "RefPackage"
0x18004911b  mov     [rsp+260h+SourceSid], rax
0x180049120  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180049127  mov     dword ptr [rsp+260h+phkResult], 7FFh
0x18004912f  mov     r8d, ebx
0x180049132  xor     ecx, ecx
0x180049134  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180049139  mov     r12, [rsp+260h+var_200]
0x18004913e  jmp     loc_180049DBD
0x180049143  mov     r12, [rsp+260h+var_200]
0x180049148  mov     eax, [r12+0A0h]
0x180049150  and     eax, r14d
0x180049153  test    al, al
0x180049155  jnz     short loc_180049190
0x180049157  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004915e  mov     ebx, 0C00000BBh
0x180049163  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180049168  mov     r9, rax
0x18004916b  lea     rsi, Class
0x180049172  mov     qword ptr [rsp+260h+var_230], rsi
0x180049177  lea     rax, aAccountRenameI; "Account rename is only supported for sh"...
0x18004917e  mov     [rsp+260h+SourceSid], rax
0x180049183  mov     dword ptr [rsp+260h+phkResult], 804h
0x18004918b  jmp     loc_180049040
0x180049190  mov     r8, [rbp+160h+var_1D0]; unsigned __int16 *
0x180049194  lea     rax, [rsp+260h+var_208]
0x180049199  xor     r9d, r9d; int
0x18004919c  mov     [rsp+260h+phkResult], rax; struct _USER_CACHE_ENTRY **
0x1800491a1  lea     rdx, [r12+44h]; struct _GUID *
0x1800491a6  xor     ecx, ecx; int
0x1800491a8  call    ?_CreateOrAcquireUserCacheEntry@@YAJHPEAU_GUID@@PEBGHPEAPEAU_USER_CACHE_ENTRY@@@Z; _CreateOrAcquireUserCacheEntry(int,_GUID *,ushort const *,int,_USER_CACHE_ENTRY * *)
0x1800491ad  mov     ebx, eax
0x1800491af  test    eax, eax
0x1800491b1  jz      short loc_1800491FD
0x1800491b3  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800491ba  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800491bf  mov     r9, rax
0x1800491c2  lea     rsi, Class
0x1800491c9  mov     qword ptr [rsp+260h+var_230], rsi
0x1800491ce  lea     rax, aCreateoracquir_3; "CreateOrAcquireUserCacheEntry"
0x1800491d5  mov     [rsp+260h+SourceSid], rax
0x1800491da  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800491e1  mov     dword ptr [rsp+260h+phkResult], 80Dh
0x1800491e9  mov     r8d, ebx
0x1800491ec  xor     ecx, ecx
0x1800491ee  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800491f3  mov     r15, [rsp+260h+var_208]
0x1800491f8  jmp     loc_180049DBD
0x1800491fd  mov     r15, [rsp+260h+var_208]
0x180049202  mov     dl, r14b; bool
0x180049205  mov     rcx, r15; struct _USER_CACHE_ENTRY *
0x180049208  call    ?LockAndUnProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@_N@Z; LockAndUnProtectUserCacheEntry(_USER_CACHE_ENTRY *,bool)
0x18004920d  mov     r8, [rsp+260h+var_1F8]; unsigned __int16 *
0x180049212  lea     rax, [rbp+160h+var_1D8]
0x180049216  mov     r9d, r14d; int
0x180049219  mov     [rsp+260h+phkResult], rax; struct _USER_CACHE_ENTRY **
0x18004921e  lea     rdx, [r12+44h]; struct _GUID *
0x180049223  mov     [rsp+260h+var_210], r14b
0x180049228  xor     ecx, ecx; int
0x18004922a  call    ?_CreateOrAcquireUserCacheEntry@@YAJHPEAU_GUID@@PEBGHPEAPEAU_USER_CACHE_ENTRY@@@Z; _CreateOrAcquireUserCacheEntry(int,_GUID *,ushort const *,int,_USER_CACHE_ENTRY * *)
0x18004922f  mov     ebx, eax
0x180049231  test    eax, eax
0x180049233  jz      short loc_180049269
0x180049235  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004923c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180049241  mov     r9, rax
0x180049244  lea     rsi, Class
0x18004924b  mov     qword ptr [rsp+260h+var_230], rsi
0x180049250  lea     rax, aCreateephemera; "CreateEphemeralUserCacheEntry"
0x180049257  mov     [rsp+260h+SourceSid], rax
0x18004925c  mov     dword ptr [rsp+260h+phkResult], 81Bh
0x180049264  jmp     loc_180049040
0x180049269  xor     r9d, r9d
0x18004926c  lea     rsi, Class
0x180049273  lea     rdi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004927a  cmp     [r15+0F0h], r9
0x180049281  jnz     loc_180049511
0x180049287  mov     r14, [r12+160h]
0x18004928f  mov     rcx, [r15+60h]; lpSrcStr
0x180049293  mov     [rbp+160h+hKey], r9
0x180049297  test    r14, r14
0x18004929a  jz      loc_1800493DA
0x1800492a0  test    rcx, rcx
0x1800492a3  jz      loc_1800493DA
0x1800492a9  lea     rdx, [rbp+160h+var_E0]; unsigned __int16 *
0x1800492b0  call    ?GetHashString@@YAJPEBGQEAG@Z; GetHashString(ushort const *,ushort * const)
0x1800492b5  mov     ebx, eax
0x1800492b7  xor     eax, eax
0x1800492b9  test    ebx, ebx
0x1800492bb  jz      short loc_1800492E3
0x1800492bd  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x1800492c4  mov     r10d, eax
0x1800492c7  mov     r11, rdi
0x1800492ca  mov     r8d, ebx
0x1800492cd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800492d2  mov     ecx, 4FFh
0x1800492d7  lea     r14, aGethashstring; "GetHashString"
0x1800492de  jmp     loc_180049401
0x1800492e3  lea     rax, [rbp+160h+var_E0]
0x1800492ea  mov     edx, 4Ah ; 'J'; unsigned __int64
0x1800492ef  lea     r9, aName2sid; "Name2Sid"
0x1800492f6  mov     [rsp+260h+phkResult], rax
0x1800492fb  lea     r8, aWsWs_1; "%ws\\%ws"
0x180049302  lea     rcx, [rbp+160h+SubKey]; unsigned __int16 *
0x180049306  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004930b  mov     ebx, eax
0x18004930d  xor     eax, eax
0x18004930f  test    ebx, ebx
0x180049311  jz      short loc_180049339
0x180049313  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18004931a  mov     r10d, eax
0x18004931d  mov     r11, rdi
0x180049320  mov     r8d, ebx
0x180049323  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180049328  mov     ecx, 507h
0x18004932d  lea     r14, aRtlstringcchpr; "RtlStringCchPrintfW"
0x180049334  jmp     loc_180049401
0x180049339  lea     rax, [rbp+160h+hKey]
0x18004933d  mov     r9d, 20019h; samDesired
0x180049343  xor     r8d, r8d; ulOptions
0x180049346  mov     [rsp+260h+phkResult], rax; phkResult
0x18004934b  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18004934f  mov     rcx, r14; hKey
0x180049352  call    cs:__imp_RegOpenKeyExW
0x180049358  xor     r14d, r14d
0x18004935b  mov     ebx, eax
0x18004935d  test    eax, eax
0x18004935f  jz      loc_180049454
0x180049365  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18004936c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180049371  mov     r9, rax
0x180049374  lea     r14, aRegopenkeyexw; "RegOpenKeyExW"
0x18004937b  lea     rax, [rbp+160h+SubKey]
0x18004937f  mov     r8d, ebx
0x180049382  mov     qword ptr [rsp+260h+var_230], rax
0x180049387  mov     rdx, rdi
0x18004938a  mov     [rsp+260h+SourceSid], r14
0x18004938f  xor     ecx, ecx
0x180049391  mov     dword ptr [rsp+260h+phkResult], 512h
0x180049399  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004939e  lea     eax, [rbx-2]
0x1800493a1  cmp     eax, 1
0x1800493a4  jbe     short loc_1800493B5
0x1800493a6  test    ebx, ebx
  ... truncated ...
```
