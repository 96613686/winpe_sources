# LoadPlugin(bool,HKEY__ *,HKEY__ *,ushort *,ushort const *,_ApPluginPkg *,ulong *)

- ea: `0x18001a624`
- end: `0x18001b1e5`
- name: `?LoadPlugin@@YAJ_NPEAUHKEY__@@1PEAGPEBGPEAU_ApPluginPkg@@PEAK@Z`
- size: `3009`
- prototype: `__int64 __fastcall(char, HKEY, HKEY, unsigned __int16 *, const unsigned __int16 *lpSubKey, struct _ApPluginPkg *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019e48`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000a8f0`
- `0x18000c600`
- `0x18001a624`
- `0x18001b1ec`
- `0x180042410`
- `0x18004317c`
- `0x18004c808`
- `0x18004cf60`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001b16d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001b16d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001a990`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001a990`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a9f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a9f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a822`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b091`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b19d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a822`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b091`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b19d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a7a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a84a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a7a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a84a`
- `RPCRT4!UuidFromStringW` at `0x18001a6bd`
- `RPCRT4!UuidFromStringW` at `0x18001a6bd`
- `RPCRT4!UuidEqual` at `0x18001a750`
- `RPCRT4!UuidEqual` at `0x18001a77e`
- `RPCRT4!UuidEqual` at `0x18001a750`
- `RPCRT4!UuidEqual` at `0x18001a77e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001a96d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001a96d`
- `ntdll!RtlInitializeResource` at `0x18001ad54`
- `ntdll!RtlInitializeResource` at `0x18001ad54`
- `ntdll!RtlValidSid` at `0x18001abb8`
- `ntdll!RtlValidSid` at `0x18001ac0c`
- `ntdll!RtlValidSid` at `0x18001abb8`
- `ntdll!RtlValidSid` at `0x18001ac0c`
- `ntdll!RtlDeleteResource` at `0x18001b0f6`
- `ntdll!RtlDeleteResource` at `0x18001b0f6`

## string_xrefs

- `0x18001a7e2`: `RegOpenKeyEx`
- `0x18001a8f8`: `ApPluginDLLPath`
- `0x18001a9ed`: `CloudAPPluginInitialize`
- `0x18001a6ce`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001a7ce`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001a86c`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001a8b2`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001a90d`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001a9b8`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001aa17`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001aab8`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001ab18`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001ab77`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001abcb`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001ac1f`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001ac97`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001ad0c`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001ad86`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001ae04`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001ae6e`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001aec0`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001af37`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001afe1`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001b02f`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001a8c6`: `Not configured properly (not joined to a cloud domain)`
- `0x18001a9d4`: `LoadLibraryEx`
- `0x18001aad4`: `CloudAPPluginInitialze`
- `0x18001ab93`: `Plugin Capability is not mutually exclusive`
- `0x18001abe6`: `Provider SID is invalid`
- `0x18001ac3a`: `Token Broker Plugin SID is invalid`
- `0x18001acb2`: `InitializePluginCacheRoots`
- `0x18001ad9a`: `Invalid Plugin caps`
- `0x18001aed4`: `Invalid Plugin caps`

## pseudocode

```c
__int64 __fastcall LoadPlugin(
        char a1,
        HKEY a2,
        HKEY a3,
        unsigned __int16 *a4,
        const unsigned __int16 *lpSubKey,
        struct _ApPluginPkg *a6,
        unsigned int *a7)
{
  const WCHAR *v10; // r15
  LPCWSTR v12; // r13
  const char *v13; // rax
  __int64 v14; // r8
  unsigned int DWordRegVal; // ebx
  const char *v16; // r9
  LSTATUS v17; // eax
  const char *v18; // rax
  HMODULE Library; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  signed int v22; // eax
  unsigned __int64 v23; // rax
  __int64 v24; // r8
  const char *v25; // rax
  bool v26; // zf
  int v27; // eax
  struct _RTL_RESOURCE *v28; // rax
  struct _RTL_RESOURCE *v29; // rbx
  const char *v30; // rax
  bool v31; // zf
  int v32; // r10d
  __int64 v33; // r8
  const char *v34; // r9
  int v35; // r10d
  int v36; // r10d
  HMODULE *p_hLibModule; // rax
  __int64 v38; // rcx
  struct _RTL_BALANCED_NODE *v39; // rcx
  struct _RTL_BALANCED_NODE **v40; // rax
  ULONG_PTR ParentValue; // rsi
  unsigned __int64 v42; // rsi
  PHKEY phkResult; // [rsp+20h] [rbp-468h]
  const char *v45; // [rsp+28h] [rbp-460h]
  WCHAR *v46; // [rsp+30h] [rbp-458h]
  __int64 v47; // [rsp+30h] [rbp-458h]
  unsigned int v48; // [rsp+50h] [rbp-438h] BYREF
  RPC_STATUS v49; // [rsp+54h] [rbp-434h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-430h] BYREF
  RPC_STATUS Status; // [rsp+60h] [rbp-428h] BYREF
  struct _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE *v52; // [rsp+68h] [rbp-420h] BYREF
  LPCWSTR lpSrc; // [rsp+70h] [rbp-418h] BYREF
  unsigned int *v54; // [rsp+78h] [rbp-410h]
  HKEY v55; // [rsp+80h] [rbp-408h]
  HMODULE hLibModule; // [rsp+90h] [rbp-3F8h] BYREF
  __int64 v57; // [rsp+98h] [rbp-3F0h] BYREF
  __int64 v58; // [rsp+A0h] [rbp-3E8h] BYREF
  unsigned __int16 v59[22]; // [rsp+A8h] [rbp-3E0h] BYREF
  UUID v60; // [rsp+D4h] [rbp-3B4h] BYREF
  _BYTE Sid[68]; // [rsp+E4h] [rbp-3A4h] BYREF
  PSID v62; // [rsp+128h] [rbp-360h] BYREF
  int v63; // [rsp+130h] [rbp-358h] BYREF
  _BYTE v64[8]; // [rsp+138h] [rbp-350h] BYREF
  void (*v65)(void); // [rsp+140h] [rbp-348h]
  unsigned __int16 *v66; // [rsp+1E8h] [rbp-2A0h] BYREF
  HKEY v67; // [rsp+1F0h] [rbp-298h] BYREF
  PRTL_RESOURCE Resource; // [rsp+1F8h] [rbp-290h]
  int v69; // [rsp+200h] [rbp-288h]
  struct _RTL_BALANCED_NODE *v70; // [rsp+208h] [rbp-280h]
  __int64 v71; // [rsp+210h] [rbp-278h]
  UUID Uuid; // [rsp+220h] [rbp-268h] BYREF
  WCHAR Dst[264]; // [rsp+230h] [rbp-258h] BYREF

  v55 = a3;
  v10 = lpSubKey;
  v54 = a7;
  Uuid = 0;
  v48 = 0;
  v52 = 0;
  memset_0(&hLibModule, 0, 0x188u);
  v12 = 0;
  lpSrc = 0;
  hKey = 0;
  Status = UuidFromStringW(a4, &Uuid);
  if ( Status )
  {
    v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    if ( !a4 )
      a4 = (unsigned __int16 *)&Class;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v14, v13, 457, "UuidFromStringW", a4);
    DWordRegVal = -1073610719;
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    v46 = (WCHAR *)&Class;
    v45 = "UuidFromStringW";
    LODWORD(phkResult) = 459;
    goto LABEL_81;
  }
  if ( !UuidEqual(&Uuid, (UUID *)&Uuid2, &Status) && !a1 )
  {
    v49 = 0;
    if ( !UuidEqual(&Uuid, (UUID *)&stru_180088320, &v49) )
    {
      v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
      DWordRegVal = v17;
      if ( v17 )
      {
        if ( v17 > 0 )
          DWordRegVal = (unsigned __int16)v17 | 0xC0070000;
        if ( !lpSubKey )
          v10 = &Class;
        v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
        v46 = (WCHAR *)v10;
        v45 = "RegOpenKeyEx";
        LODWORD(phkResult) = 489;
        goto LABEL_81;
      }
      DWordRegVal = GetDWordRegVal(hKey, L"Enabled", &v48);
      if ( DWordRegVal == -1073741275 )
      {
        RegCloseKey(hKey);
        hKey = 0;
        if ( !RegOpenKeyExW(a2, L"LoadParameters", 0, 0x20019u, &hKey) )
          DWordRegVal = GetDWordRegVal(hKey, L"Enabled", &v48);
      }
      if ( DWordRegVal )
      {
        v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
        v46 = (WCHAR *)L"Enabled";
        v45 = "GetDWordRegVal";
        LODWORD(phkResult) = 517;
LABEL_81:
        v24 = DWordRegVal;
        goto LABEL_82;
      }
      if ( !v48 )
      {
        DWordRegVal = -1073741079;
        if ( !a4 )
          a4 = (unsigned __int16 *)&Class;
        v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
        v46 = a4;
        v45 = "Not configured properly (not joined to a cloud domain)";
        LODWORD(phkResult) = 522;
        goto LABEL_81;
      }
    }
  }
  v49 = 0;
  DWordRegVal = GetRegVal(a2, L"ApPluginDLLPath", 6u, (unsigned int *)&v49, (void **)&lpSrc);
  if ( DWordRegVal )
  {
    v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    LODWORD(phkResult) = 531;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", DWordRegVal, v18, phkResult, "GetStringRegVal", &Class);
    v12 = lpSrc;
    goto LABEL_83;
  }
  v12 = lpSrc;
  if ( ExpandEnvironmentStringsW(lpSrc, Dst, 0x105u) - 1 > 0x104 )
  {
    DWordRegVal = -1073741595;
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    v46 = (WCHAR *)&Class;
    v45 = "ExpandEnvironmentStringsW";
    LODWORD(phkResult) = 540;
    goto LABEL_81;
  }
  Library = LoadLibraryExW(Dst, 0, 0x880u);
  hLibModule = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    DWordRegVal = LastError;
    if ( LastError > 0 )
      DWordRegVal = (unsigned __int16)LastError | 0xC0070000;
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    v46 = Dst;
    v45 = "LoadLibraryEx";
    LODWORD(phkResult) = 552;
    goto LABEL_81;
  }
  ProcAddress = GetProcAddress(Library, "CloudAPPluginInitialize");
  if ( !ProcAddress )
  {
    v22 = GetLastError();
    DWordRegVal = v22;
    if ( v22 > 0 )
      DWordRegVal = (unsigned __int16)v22 | 0xC0070000;
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    v46 = Dst;
    v45 = "GetProcAddress";
    LODWORD(phkResult) = 560;
    goto LABEL_81;
  }
  DWordRegVal = ((__int64 (__fastcall *)(__int64, UUID *, void *, int *, unsigned __int16 *, _BYTE *, PSID *, __int64 *, _BYTE *))ProcAddress)(
                  1,
                  &Uuid,
                  &g_CloudAPFunctionTable,
                  &v63,
                  v59,
                  Sid,
                  &v62,
                  &v57,
                  v64);
  if ( DWordRegVal )
  {
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    v46 = Dst;
    v45 = "CloudAPPluginInitialze";
    LODWORD(phkResult) = 573;
    goto LABEL_81;
  }
  v23 = -1;
  do
    ++v23;
  while ( v59[v23] );
  if ( v23 >= 0x15 )
  {
    v24 = 3221225485LL;
    DWordRegVal = -1073741811;
    v16 = "";
    while ( 1 )
    {
      v25 = v16--;
      v26 = *v16 == 92;
      if ( *v16 == 92 )
        break;
      if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp" )
      {
        v26 = *v16 == 92;
        break;
      }
    }
    if ( v26 )
      v16 = v25;
    v46 = (WCHAR *)&Class;
    v45 = "Provider Name not NULL terminated";
    LODWORD(phkResult) = 578;
    goto LABEL_82;
  }
  v27 = v63 & 0x10;
  if ( (*v54 & v27) != 0 )
  {
    DWordRegVal = -1073741585;
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    v46 = v59;
    v45 = "Plugin Capability is not mutually exclusive";
    LODWORD(phkResult) = 586;
    goto LABEL_81;
  }
  *v54 |= v27;
  if ( !RtlValidSid(Sid) )
  {
    DWordRegVal = -1073741811;
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    v46 = (WCHAR *)&Class;
    v45 = "Provider SID is invalid";
    LODWORD(phkResult) = 595;
LABEL_82:
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v24, v16, phkResult, v45, v46);
    goto LABEL_83;
  }
  if ( v62 && !RtlValidSid(v62) )
  {
    DWordRegVal = -1073741811;
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    v46 = (WCHAR *)&Class;
    v45 = "Token Broker Plugin SID is invalid";
    LODWORD(phkResult) = 602;
    goto LABEL_82;
  }
  v60 = Uuid;
  DWordRegVal = InitializePluginCacheRoots(v55, a4, v59, &v66, &v67);
  if ( DWordRegVal )
  {
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    v46 = (WCHAR *)&Class;
    v45 = "InitializePluginCacheRoots";
    LODWORD(phkResult) = 613;
    goto LABEL_81;
  }
  v70 = 0;
  v71 = 0;
  v28 = (struct _RTL_RESOURCE *)((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(104);
  v29 = v28;
  Resource = v28;
  if ( !v28 )
  {
    DWordRegVal = -1073741801;
    v16 = "";
    while ( 1 )
    {
      v30 = v16--;
      v31 = *v16 == 92;
      if ( *v16 == 92 )
        break;
      if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp" )
      {
        v31 = *v16 == 92;
        break;
      }
    }
    if ( v31 )
      v16 = v30;
    v46 = (WCHAR *)&Class;
    v45 = "SCLockInitializeResource";
    LODWORD(phkResult) = 623;
    goto LABEL_81;
  }
  RtlInitializeResource(v28);
  LODWORD(v29[1].Lock.DebugInfo) = 0;
  v69 = 1;
  v32 = v63;
  if ( (v63 & 4) != 0 )
  {
    v63 &= ~0x40u;
    if ( (v32 & 0xFFFFFF8B) != 0 )
    {
      DWordRegVal = -1073740539;
      v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
      LODWORD(v47) = v36;
      LODWORD(phkResult) = 678;
      goto LABEL_66;
    }
    DWordRegVal = ((__int64 (__fastcall *)(UUID *, _BYTE *, _QWORD, void *, struct _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE **, __int64 *))g_pLsaFunctionTable->DummyFunction6)(
                    &v60,
                    Sid,
                    0,
                    &g_CloudAPIdProvTable,
                    &v52,
                    &v58);
    if ( DWordRegVal )
    {
      v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
      v46 = Dst;
      v45 = "RegisterIdentityProvider";
      LODWORD(phkResult) = 688;
      goto LABEL_81;
    }
    g_pLsaIdProvHostFunctionTable = v52;
  }
  else
  {
    if ( (v63 & 0x20) != 0 )
    {
      DWordRegVal = -1073740539;
      v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
      LODWORD(v47) = v35;
      LODWORD(phkResult) = 645;
LABEL_66:
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%u", v33, v34, phkResult, "Invalid Plugin caps", v47);
      goto LABEL_83;
    }
    DWordRegVal = ((__int64 (__fastcall *)(UUID *, _BYTE *, __int64, void *, struct _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE **, __int64 *))g_pLsaFunctionTable->DummyFunction6)(
                    &v60,
                    Sid,
                    1,
                    &g_CloudAPIdProvTable,
                    &v52,
                    &v58);
    if ( DWordRegVal )
    {
      v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
      v46 = Dst;
      v45 = "RegisterIdentityProvider";
      LODWORD(phkResult) = 655;
      goto LABEL_81;
    }
    g_pLsaIdProvHostFunctionTable = v52;
    if ( (v63 & 1) == 0 )
    {
      DWordRegVal = LoadSubPkgs((struct _ApPluginPkg *)&hLibModule);
      if ( DWordRegVal )
      {
        v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
        v46 = (WCHAR *)&Class;
        v45 = "LoadSubPkgs";
        LODWORD(phkResult) = 664;
        goto LABEL_81;
      }
    }
  }
  p_hLibModule = &hLibModule;
  v38 = 3;
  do
  {
    *(_OWORD *)a6 = *(_OWORD *)p_hLibModule;
    *((_OWORD *)a6 + 1) = *((_OWORD *)p_hLibModule + 1);
    *((_OWORD *)a6 + 2) = *((_OWORD *)p_hLibModule + 2);
    *((_OWORD *)a6 + 3) = *((_OWORD *)p_hLibModule + 3);
    *((_OWORD *)a6 + 4) = *((_OWORD *)p_hLibModule + 4);
    *((_OWORD *)a6 + 5) = *((_OWORD *)p_hLibModule + 5);
    *((_OWORD *)a6 + 6) = *((_OWORD *)p_hLibModule + 6);
    *((_OWORD *)a6 + 7) = *((_OWORD *)p_hLibModule + 7);
    a6 = (struct _ApPluginPkg *)((char *)a6 + 128);
    p_hLibModule += 16;
    --v38;
  }
  while ( v38 );
  *(_QWORD *)a6 = *p_hLibModule;
  DWordRegVal = 0;
LABEL_83:
  if ( v12 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v12);
  if ( hKey )
    RegCloseKey(hKey);
  if ( (DWordRegVal & 0x80000000) != 0 )
  {
    if ( v58 && g_pLsaIdProvHostFunctionTable )
      (*((void (**)(void))g_pLsaIdProvHostFunctionTable + 1))();
    if ( v57 && v65 )
      v65();
    if ( Resource )
    {
      if ( v69 )
        RtlDeleteResource(Resource);
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    }
    v39 = v70;
    if ( v70 )
    {
      while ( !v39->Children[0] )
      {
        v40 = &v39->Children[1];
        if ( v39->Children[1] )
        {
          v39 = *v40;
LABEL_103:
          *v40 = 0;
        }
        else
        {
          ParentValue = v39->ParentValue;
          SubPkgTable_FreeRoutine(v39, 0);
          v42 = ParentValue & 0xFFFFFFFFFFFFFFFCuLL;
          if ( !v42 )
            goto LABEL_106;
          v39 = (struct _RTL_BALANCED_NODE *)v42;
        }
      }
      v40 = (struct _RTL_BALANCED_NODE **)v39;
      v39 = v39->Children[0];
      goto LABEL_103;
    }
LABEL_106:
    v70 = 0;
    if ( hLibModule )
      FreeLibrary(hLibModule);
    if ( v66 )
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    if ( v67 )
      RegCloseKey(v67);
    if ( v62 )
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  return DWordRegVal;
}

```

## disassembly

```asm
0x18001a624  push    rbx
0x18001a626  push    rsi
0x18001a627  push    rdi
0x18001a628  push    r12
0x18001a62a  push    r13
0x18001a62c  push    r14
0x18001a62e  push    r15
0x18001a630  sub     rsp, 450h
0x18001a637  mov     rax, cs:__security_cookie
0x18001a63e  xor     rax, rsp
0x18001a641  mov     [rsp+488h+var_48], rax
0x18001a649  mov     r12, r9
0x18001a64c  mov     [rsp+488h+var_408], r8
0x18001a654  mov     r14, rdx
0x18001a657  mov     bl, cl
0x18001a659  mov     r15, [rsp+488h+lpSubKey]
0x18001a661  mov     rsi, [rsp+488h+arg_28]
0x18001a669  mov     rax, [rsp+488h+arg_30]
0x18001a671  mov     [rsp+488h+var_410], rax
0x18001a676  xor     edi, edi
0x18001a678  mov     [rsp+488h+Status], edi
0x18001a67c  xorps   xmm0, xmm0
0x18001a67f  movups  xmmword ptr [rsp+488h+Uuid.Data1], xmm0
0x18001a687  mov     [rsp+488h+var_438], edi
0x18001a68b  mov     [rsp+488h+var_420], rdi
0x18001a690  xor     edx, edx; Val
0x18001a692  mov     r8d, 188h; Size
0x18001a698  lea     rcx, [rsp+488h+hLibModule]; void *
0x18001a6a0  call    memset_0
0x18001a6a5  mov     r13d, edi
0x18001a6a8  mov     [rsp+488h+lpSrc], rdi
0x18001a6ad  mov     [rsp+488h+hKey], rdi
0x18001a6b2  lea     rdx, [rsp+488h+Uuid]; Uuid
0x18001a6ba  mov     rcx, r12; StringUuid
0x18001a6bd  call    cs:__imp_UuidFromStringW
0x18001a6c3  mov     r8d, eax
0x18001a6c6  mov     [rsp+488h+Status], eax
0x18001a6ca  test    eax, eax
0x18001a6cc  jz      short loc_18001A73C
0x18001a6ce  lea     rsi, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001a6d5  mov     rcx, rsi; char *
0x18001a6d8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001a6dd  lea     r14, Class
0x18001a6e4  test    r12, r12
0x18001a6e7  cmovz   r12, r14
0x18001a6eb  mov     [rsp+488h+var_458], r12
0x18001a6f0  lea     r15, aUuidfromstring; "UuidFromStringW"
0x18001a6f7  mov     [rsp+488h+var_460], r15
0x18001a6fc  mov     dword ptr [rsp+488h+phkResult], 1C9h
0x18001a704  mov     r9, rax
0x18001a707  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001a70e  xor     ecx, ecx
0x18001a710  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001a715  mov     ebx, 0C0020021h
0x18001a71a  mov     rcx, rsi; char *
0x18001a71d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001a722  mov     r9, rax
0x18001a725  mov     [rsp+488h+var_458], r14
0x18001a72a  mov     [rsp+488h+var_460], r15
0x18001a72f  mov     dword ptr [rsp+488h+phkResult], 1CBh
0x18001a737  jmp     loc_18001B05E
0x18001a73c  lea     r8, [rsp+488h+Status]; Status
0x18001a741  lea     rdx, Uuid2; Uuid2
0x18001a748  lea     rcx, [rsp+488h+Uuid]; Uuid1
0x18001a750  call    cs:__imp_UuidEqual
0x18001a756  test    eax, eax
0x18001a758  jnz     loc_18001A8DF
0x18001a75e  test    bl, bl
0x18001a760  jnz     loc_18001A8DF
0x18001a766  mov     [rsp+488h+var_434], edi
0x18001a76a  lea     r8, [rsp+488h+var_434]; Status
0x18001a76f  lea     rdx, stru_180088320; Uuid2
0x18001a776  lea     rcx, [rsp+488h+Uuid]; Uuid1
0x18001a77e  call    cs:__imp_UuidEqual
0x18001a784  test    eax, eax
0x18001a786  jnz     loc_18001A8DF
0x18001a78c  lea     rax, [rsp+488h+hKey]
0x18001a791  mov     [rsp+488h+phkResult], rax; phkResult
0x18001a796  mov     r9d, 20019h; samDesired
0x18001a79c  xor     r8d, r8d; ulOptions
0x18001a79f  mov     rdx, r15; lpSubKey
0x18001a7a2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a7a9  call    cs:__imp_RegOpenKeyExW
0x18001a7af  mov     ebx, eax
0x18001a7b1  test    eax, eax
0x18001a7b3  jz      short loc_18001A7FB
0x18001a7b5  jle     short loc_18001A7C0
0x18001a7b7  movzx   ebx, ax
0x18001a7ba  or      ebx, 0C0070000h
0x18001a7c0  lea     r14, Class
0x18001a7c7  test    r15, r15
0x18001a7ca  cmovz   r15, r14
0x18001a7ce  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001a7d5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001a7da  mov     r9, rax
0x18001a7dd  mov     [rsp+488h+var_458], r15
0x18001a7e2  lea     rax, aRegopenkeyex_0; "RegOpenKeyEx"
0x18001a7e9  mov     [rsp+488h+var_460], rax
0x18001a7ee  mov     dword ptr [rsp+488h+phkResult], 1E9h
0x18001a7f6  jmp     loc_18001B05E
0x18001a7fb  lea     r8, [rsp+488h+var_438]; unsigned int *
0x18001a800  lea     r15, aEnabled; "Enabled"
0x18001a807  mov     rdx, r15; unsigned __int16 *
0x18001a80a  mov     rcx, [rsp+488h+hKey]; HKEY
0x18001a80f  call    ?GetDWordRegVal@@YAJPEAUHKEY__@@PEBGPEAK@Z; GetDWordRegVal(HKEY__ *,ushort const *,ulong *)
0x18001a814  mov     ebx, eax
0x18001a816  cmp     eax, 0C0000225h
0x18001a81b  jnz     short loc_18001A868
0x18001a81d  mov     rcx, [rsp+488h+hKey]; hKey
0x18001a822  call    cs:__imp_RegCloseKey
0x18001a828  mov     [rsp+488h+hKey], rdi
0x18001a82d  lea     rax, [rsp+488h+hKey]
0x18001a832  mov     [rsp+488h+phkResult], rax; phkResult
0x18001a837  mov     r9d, 20019h; samDesired
0x18001a83d  xor     r8d, r8d; ulOptions
0x18001a840  lea     rdx, aLoadparameters; "LoadParameters"
0x18001a847  mov     rcx, r14; hKey
0x18001a84a  call    cs:__imp_RegOpenKeyExW
0x18001a850  test    eax, eax
0x18001a852  jnz     short loc_18001A868
0x18001a854  lea     r8, [rsp+488h+var_438]; unsigned int *
0x18001a859  mov     rdx, r15; unsigned __int16 *
0x18001a85c  mov     rcx, [rsp+488h+hKey]; HKEY
0x18001a861  call    ?GetDWordRegVal@@YAJPEAUHKEY__@@PEBGPEAK@Z; GetDWordRegVal(HKEY__ *,ushort const *,ulong *)
0x18001a866  mov     ebx, eax
0x18001a868  test    ebx, ebx
0x18001a86a  jz      short loc_18001A899
0x18001a86c  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001a873  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001a878  mov     r9, rax
0x18001a87b  mov     [rsp+488h+var_458], r15
0x18001a880  lea     rax, aGetdwordregval_0; "GetDWordRegVal"
0x18001a887  mov     [rsp+488h+var_460], rax
0x18001a88c  mov     dword ptr [rsp+488h+phkResult], 205h
0x18001a894  jmp     loc_18001B05E
0x18001a899  cmp     [rsp+488h+var_438], edi
0x18001a89d  jnz     short loc_18001A8DF
0x18001a89f  mov     ebx, 0C00002E9h
0x18001a8a4  lea     r14, Class
0x18001a8ab  test    r12, r12
0x18001a8ae  cmovz   r12, r14
0x18001a8b2  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001a8b9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001a8be  mov     r9, rax
0x18001a8c1  mov     [rsp+488h+var_458], r12
0x18001a8c6  lea     rax, aNotConfiguredP; "Not configured properly (not joined to "...
0x18001a8cd  mov     [rsp+488h+var_460], rax
0x18001a8d2  mov     dword ptr [rsp+488h+phkResult], 20Ah
0x18001a8da  jmp     loc_18001B05E
0x18001a8df  mov     [rsp+488h+var_434], edi
0x18001a8e3  lea     rax, [rsp+488h+lpSrc]
0x18001a8e8  mov     [rsp+488h+phkResult], rax; void **
0x18001a8ed  lea     r9, [rsp+488h+var_434]; unsigned int *
0x18001a8f2  mov     r8d, 6; dwFlags
0x18001a8f8  lea     rdx, aApplugindllpat; "ApPluginDLLPath"
0x18001a8ff  mov     rcx, r14; hkey
0x18001a902  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x18001a907  mov     ebx, eax
0x18001a909  test    eax, eax
0x18001a90b  jz      short loc_18001A957
0x18001a90d  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001a914  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001a919  mov     r9, rax
0x18001a91c  lea     r14, Class
0x18001a923  mov     [rsp+488h+var_458], r14
0x18001a928  lea     rax, aGetstringregva_3; "GetStringRegVal"
0x18001a92f  mov     [rsp+488h+var_460], rax
0x18001a934  mov     dword ptr [rsp+488h+phkResult], 213h
0x18001a93c  mov     r8d, ebx
0x18001a93f  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001a946  xor     ecx, ecx
0x18001a948  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001a94d  mov     r13, [rsp+488h+lpSrc]
0x18001a952  jmp     loc_18001B06F
0x18001a957  mov     r8d, 105h; nSize
0x18001a95d  lea     rdx, [rsp+488h+Dst]; lpDst
0x18001a965  mov     r13, [rsp+488h+lpSrc]
0x18001a96a  mov     rcx, r13; lpSrc
0x18001a96d  call    cs:__imp_ExpandEnvironmentStringsW
0x18001a973  dec     eax
0x18001a975  cmp     eax, 104h
0x18001a97a  ja      loc_18001B02A
0x18001a980  xor     edx, edx; hFile
0x18001a982  mov     r8d, 880h; dwFlags
0x18001a988  lea     rcx, [rsp+488h+Dst]; lpLibFileName
0x18001a990  call    cs:__imp_LoadLibraryExW
0x18001a996  mov     [rsp+488h+hLibModule], rax
0x18001a99e  test    rax, rax
0x18001a9a1  jnz     short loc_18001A9ED
0x18001a9a3  call    cs:__imp_GetLastError
0x18001a9a9  mov     ebx, eax
0x18001a9ab  test    eax, eax
0x18001a9ad  jle     short loc_18001A9B8
0x18001a9af  movzx   ebx, ax
0x18001a9b2  or      ebx, 0C0070000h
0x18001a9b8  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001a9bf  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001a9c4  mov     r9, rax
0x18001a9c7  lea     rax, [rsp+488h+Dst]
0x18001a9cf  mov     [rsp+488h+var_458], rax
0x18001a9d4  lea     rax, aLoadlibraryex; "LoadLibraryEx"
0x18001a9db  mov     [rsp+488h+var_460], rax
0x18001a9e0  mov     dword ptr [rsp+488h+phkResult], 228h
0x18001a9e8  jmp     loc_18001B05E
0x18001a9ed  lea     rdx, ProcName; "CloudAPPluginInitialize"
0x18001a9f4  mov     rcx, rax; hModule
0x18001a9f7  call    cs:__imp_GetProcAddress
0x18001a9fd  test    rax, rax
0x18001aa00  jnz     short loc_18001AA4C
0x18001aa02  call    cs:__imp_GetLastError
0x18001aa08  mov     ebx, eax
0x18001aa0a  test    eax, eax
0x18001aa0c  jle     short loc_18001AA17
0x18001aa0e  movzx   ebx, ax
0x18001aa11  or      ebx, 0C0070000h
0x18001aa17  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001aa1e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001aa23  mov     r9, rax
0x18001aa26  lea     rax, [rsp+488h+Dst]
0x18001aa2e  mov     [rsp+488h+var_458], rax
0x18001aa33  lea     rax, aGetprocaddress; "GetProcAddress"
0x18001aa3a  mov     [rsp+488h+var_460], rax
0x18001aa3f  mov     dword ptr [rsp+488h+phkResult], 230h
0x18001aa47  jmp     loc_18001B05E
0x18001aa4c  lea     rcx, [rsp+488h+var_350]
0x18001aa54  mov     [rsp+488h+var_448], rcx
0x18001aa59  lea     rcx, [rsp+488h+var_3F0]
0x18001aa61  mov     [rsp+488h+var_450], rcx
0x18001aa66  lea     rcx, [rsp+488h+var_360]
0x18001aa6e  mov     [rsp+488h+var_458], rcx
0x18001aa73  lea     rcx, [rsp+488h+Sid]
0x18001aa7b  mov     [rsp+488h+var_460], rcx
0x18001aa80  lea     rcx, [rsp+488h+var_3E0]
0x18001aa88  mov     [rsp+488h+phkResult], rcx
0x18001aa8d  lea     r9, [rsp+488h+var_358]
0x18001aa95  lea     r8, ?g_CloudAPFunctionTable@@3U_CLOUDAP_SECPKG_FUNCTION_TABLE@@A; _CLOUDAP_SECPKG_FUNCTION_TABLE g_CloudAPFunctionTable
0x18001aa9c  lea     rdx, [rsp+488h+Uuid]
0x18001aaa4  mov     r14d, 1
0x18001aaaa  mov     ecx, r14d
0x18001aaad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aab2  mov     ebx, eax
0x18001aab4  test    eax, eax
0x18001aab6  jz      short loc_18001AAED
0x18001aab8  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001aabf  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001aac4  mov     r9, rax
0x18001aac7  lea     rax, [rsp+488h+Dst]
0x18001aacf  mov     [rsp+488h+var_458], rax
0x18001aad4  lea     rax, aCloudapplugini; "CloudAPPluginInitialze"
0x18001aadb  mov     [rsp+488h+var_460], rax
0x18001aae0  mov     dword ptr [rsp+488h+phkResult], 23Dh
0x18001aae8  jmp     loc_18001B05E
0x18001aaed  lea     rcx, [rsp+488h+var_3E0]
0x18001aaf5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001aaf9  inc     rax
0x18001aafc  cmp     [rcx+rax*2], di
0x18001ab00  jnz     short loc_18001AAF9
0x18001ab02  cmp     rax, 15h
0x18001ab06  jb      short loc_18001AB5D
0x18001ab08  mov     r8d, 0C000000Dh
0x18001ab0e  mov     ebx, r8d
0x18001ab11  lea     r9, aOnecoreDsExtCl+2Eh; ""
0x18001ab18  lea     rsi, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001ab1f  mov     rax, r9
0x18001ab22  dec     r9
0x18001ab25  cmp     byte ptr [r9], 5Ch ; '\'
0x18001ab29  jz      short loc_18001AB34
0x18001ab2b  cmp     r9, rsi
0x18001ab2e  ja      short loc_18001AB1F
0x18001ab30  cmp     byte ptr [r9], 5Ch ; '\'
0x18001ab34  cmovz   r9, rax
0x18001ab38  lea     r14, Class
0x18001ab3f  mov     [rsp+488h+var_458], r14
0x18001ab44  lea     rax, aProviderNameNo; "Provider Name not NULL terminated"
0x18001ab4b  mov     [rsp+488h+var_460], rax
0x18001ab50  mov     dword ptr [rsp+488h+phkResult], 242h
0x18001ab58  jmp     loc_18001B061
0x18001ab5d  mov     eax, [rsp+488h+var_358]
0x18001ab64  and     eax, 10h
0x18001ab67  mov     rdx, [rsp+488h+var_410]
0x18001ab6c  mov     ecx, [rdx]
0x18001ab6e  test    eax, ecx
0x18001ab70  jz      short loc_18001ABAC
0x18001ab72  mov     ebx, 0C00000EFh
0x18001ab77  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001ab7e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001ab83  mov     r9, rax
0x18001ab86  lea     rax, [rsp+488h+var_3E0]
0x18001ab8e  mov     [rsp+488h+var_458], rax
0x18001ab93  lea     rax, aPluginCapabili; "Plugin Capability is not mutually exclu"...
0x18001ab9a  mov     [rsp+488h+var_460], rax
0x18001ab9f  mov     dword ptr [rsp+488h+phkResult], 24Ah
0x18001aba7  jmp     loc_18001B05E
0x18001abac  or      ecx, eax
0x18001abae  mov     [rdx], ecx
0x18001abb0  lea     rcx, [rsp+488h+Sid]; Sid
0x18001abb8  call    cs:__imp_RtlValidSid
0x18001abbe  test    al, al
0x18001abc0  jnz     short loc_18001ABFF
0x18001abc2  mov     r8d, 0C000000Dh
  ... truncated ...
```
