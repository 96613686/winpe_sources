# SpLookUpIdentityNameFromSID(void *,void *,void *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *)

- ea: `0x18004e7b0`
- end: `0x18004f5ec`
- name: `?SpLookUpIdentityNameFromSID@@YAJPEAX00PEAPEAG1111@Z`
- size: `3644`
- prototype: `int(void *, void *, void *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003e70`
- `0x180004634`
- `0x18000498c`
- `0x180006a80`
- `0x180007fc0`
- `0x18000a600`
- `0x18000a8f0`
- `0x18000b0c0`
- `0x18000b9b0`
- `0x18000e900`
- `0x18000ee60`
- `0x18002ea68`
- `0x1800307d0`
- `0x1800335d4`
- `0x180033e80`
- `0x180042410`
- `0x18004317c`
- `0x18004e6ec`
- `0x18004e7b0`
- `0x1800510f4`
- `0x180081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004ebff`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004eced`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004ebff`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004eced`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f5c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f5c1`
- `ntdll!RtlReleaseResource` at `0x18004ee28`
- `ntdll!RtlReleaseResource` at `0x18004ee7d`
- `ntdll!RtlReleaseResource` at `0x18004ee28`
- `ntdll!RtlReleaseResource` at `0x18004ee7d`
- `ntdll!RtlAcquireResourceShared` at `0x18004eb1b`
- `ntdll!RtlAcquireResourceShared` at `0x18004eb1b`

## string_xrefs

- `0x18004e907`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004e954`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004e995`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004e9f5`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004ea41`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004eabf`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004eb60`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004eb96`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004ee33`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004f412`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004f44c`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004eb52`: `FindUserInCacheBySid`
- `0x18004ee51`: `FindUserInCacheBySid`
- `0x18004e9b5`: `Surrogate plugin`
- `0x18004ed08`: `Cached SAM Name is invalid`
- `0x18004f25d`: `UpdateSidNameCaches`
- `0x18004ec29`: `Cached Identity Name is invalid`
- `0x18004efa1`: `LookupIdentityNameFromSID`
- `0x18004f3f3`: `SID-Name cannot be resolved`

## pseudocode

```c
__int64 __fastcall SpLookUpIdentityNameFromSID(
        void *a1,
        void *a2,
        void *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7,
        unsigned __int16 **a8)
{
  const unsigned __int16 *v11; // r12
  wchar_t *v12; // r13
  unsigned __int16 **v13; // rcx
  unsigned __int16 **v14; // rax
  unsigned int RegVal; // ebx
  const char *v16; // r9
  __int64 v17; // r8
  struct _ApPluginPkg *v18; // rdi
  int v19; // esi
  unsigned int AuthenticatingAuthority; // eax
  PCWSTR v21; // rdi
  const char *v22; // r9
  const WCHAR *v23; // rdi
  HKEY v24; // rbx
  unsigned int UserInCacheBySid; // eax
  const char *v26; // r15
  const char *v27; // rax
  const char *v28; // rax
  __int64 v29; // r8
  const char *v30; // rax
  const char *v31; // rax
  const char *v32; // rax
  const char *v33; // rax
  int v34; // r8d
  unsigned int v35; // r10d
  const char *v36; // rax
  __int64 v37; // r8
  struct _ApPluginPkg *v38; // r15
  __int64 (__fastcall *v39)(_QWORD, void *, void *, wchar_t **, void **, __int64 *, __int64 *, unsigned __int16 **, unsigned __int16 **, __int64 *, unsigned __int16 **); // rax
  const char *v40; // rax
  const char *v41; // rax
  bool v42; // bl
  const char *v43; // rax
  const char *v44; // r9
  const char *v45; // rax
  LPCWSTR v46; // rsi
  bool v47; // r10
  HKEY v48; // r11
  const char *v49; // rax
  unsigned __int16 **v50; // rcx
  unsigned __int16 **v51; // r8
  unsigned __int16 *v52; // rax
  const char *v53; // r9
  __int64 v54; // r8
  const char *v55; // r9
  __int64 v56; // r8
  void **v58; // [rsp+20h] [rbp-E0h]
  const char *v59; // [rsp+28h] [rbp-D8h]
  const char *v60; // [rsp+28h] [rbp-D8h]
  unsigned __int16 **v61; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v62; // [rsp+60h] [rbp-A0h]
  wchar_t *Str; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR SourceString; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v65; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v66; // [rsp+80h] [rbp-80h] BYREF
  int v67; // [rsp+88h] [rbp-78h]
  struct _ApPluginSubPkg *v68; // [rsp+90h] [rbp-70h] BYREF
  void *v69; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v70; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v71; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *Src; // [rsp+B0h] [rbp-50h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp-48h] BYREF
  struct _ApPluginPkg *v74; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v75; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v76; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v77; // [rsp+D8h] [rbp-28h] BYREF
  LPCWSTR lpSrcStr; // [rsp+E0h] [rbp-20h] BYREF
  void *v79; // [rsp+E8h] [rbp-18h]
  unsigned __int16 **v80; // [rsp+F0h] [rbp-10h]
  unsigned __int16 **v81; // [rsp+F8h] [rbp-8h]
  unsigned __int16 **v82; // [rsp+100h] [rbp+0h]
  unsigned __int16 **v83; // [rsp+108h] [rbp+8h]
  void *v84; // [rsp+110h] [rbp+10h]
  unsigned __int16 **v85; // [rsp+118h] [rbp+18h]
  _QWORD v86[4]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v87[16]; // [rsp+140h] [rbp+40h] BYREF
  void *v88; // [rsp+150h] [rbp+50h]
  void *v89; // [rsp+168h] [rbp+68h]
  __int64 v90; // [rsp+170h] [rbp+70h]
  __int64 v91; // [rsp+178h] [rbp+78h]
  unsigned __int16 *v92; // [rsp+188h] [rbp+88h]
  unsigned __int16 *v93; // [rsp+190h] [rbp+90h]
  __int64 v94; // [rsp+198h] [rbp+98h]
  struct _GUID v95; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 v96[72]; // [rsp+1E0h] [rbp+E0h] BYREF

  v82 = a7;
  v79 = a3;
  v84 = a2;
  v80 = a4;
  v85 = a5;
  v83 = a6;
  v81 = a8;
  v95 = 0;
  memset_0(v87, 0, 0x88u);
  SourceString = 0;
  v62 = 0;
  v11 = 0;
  lpSrcStr = 0;
  v12 = 0;
  v66 = 0;
  Str = 0;
  v69 = 0;
  v75 = 0;
  v76 = 0;
  Src = 0;
  v71 = 0;
  v77 = 0;
  v70 = 0;
  v74 = 0;
  v68 = 0;
  hKey = 0;
  if ( !v80 || !a5 || !a6 || (v13 = v81) == 0 || (v14 = v82) == 0 )
  {
    RegVal = -1073741811;
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    v61 = (unsigned __int16 **)&Class;
    v59 = "Invalid Arg";
    LODWORD(v58) = 1021;
    goto LABEL_107;
  }
  *v80 = 0;
  *a5 = 0;
  *a6 = 0;
  *v13 = 0;
  *v14 = 0;
  if ( !a1 || !a2 || !a3 )
  {
    RegVal = -1073741811;
    v55 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v56, v55, 1034, "Invalid Arg(s)", &Class);
    goto LABEL_108;
  }
  RegVal = (*((__int64 (__fastcall **)(void *, struct _GUID *))g_pLsaIdProvHostFunctionTable + 10))(a1, &v95);
  if ( RegVal )
  {
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    v61 = (unsigned __int16 **)&Class;
    v59 = "GetProvInfo";
    LODWORD(v58) = 1038;
LABEL_11:
    v17 = RegVal;
LABEL_107:
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v17, v16, v58, v59, v61);
    goto LABEL_108;
  }
  RegVal = RefPackage(&v95, &v74);
  if ( RegVal )
  {
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    v61 = (unsigned __int16 **)&Class;
    v59 = "RefPackage";
    LODWORD(v58) = 1041;
    goto LABEL_11;
  }
  v18 = v74;
  v19 = *((_DWORD *)v74 + 40);
  if ( (v19 & 4) != 0 )
  {
    RegVal = -1073741637;
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    v61 = (unsigned __int16 **)&Class;
    v59 = "Surrogate plugin";
    LODWORD(v58) = 1047;
    goto LABEL_11;
  }
  AuthenticatingAuthority = GetAuthenticatingAuthority(v74, 0, a3, (unsigned __int16 **)&SourceString);
  v11 = SourceString;
  RegVal = AuthenticatingAuthority;
  if ( AuthenticatingAuthority )
  {
    v21 = &Class;
    if ( SourceString )
      v21 = SourceString;
    v61 = (unsigned __int16 **)v21;
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    v59 = "GetAuthenticatingAuthorityForIdentity";
    LODWORD(v58) = 1063;
    goto LABEL_11;
  }
  if ( SourceString )
    goto LABEL_25;
  RegVal = DuplicateString((const unsigned __int16 *)v18 + 12, 0, (unsigned __int16 **)&SourceString);
  if ( !RegVal )
  {
    v11 = SourceString;
LABEL_25:
    if ( CloudAPCompareStrings(v11, (PCWSTR)v18 + 12) )
    {
      RegVal = RefSubPackage(v18, v11, &v68);
      if ( RegVal )
      {
        v23 = &Class;
        if ( v11 )
          v23 = v11;
        v61 = (unsigned __int16 **)v23;
        v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        v59 = "RefSubPackage";
        LODWORD(v58) = 1075;
        goto LABEL_11;
      }
      v24 = (HKEY)*((_QWORD *)v68 + 74);
    }
    else
    {
      v24 = (HKEY)*((_QWORD *)v18 + 44);
    }
    LOBYTE(v19) = (v19 & 1) == 0;
    v67 = v19;
    RtlAcquireResourceShared(&g_LookupsCacheLock, 1u);
    UserInCacheBySid = FindUserInCacheBySid(v24, a3, &hKey);
    RegVal = UserInCacheBySid;
    if ( UserInCacheBySid == -1073741275 )
    {
      v36 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v37, v36, 1172, "FindUserInCacheBySid", &Class);
    }
    else
    {
      if ( UserInCacheBySid )
      {
        v26 = "FindUserInCacheBySid";
LABEL_51:
        v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        LODWORD(v58) = v34;
        WPPTraceLogA(v35, "0x%08x %s:%u : %s:%ws", RegVal, v33, v58, v26, &Class);
        RtlReleaseResource(&g_LookupsCacheLock);
        goto LABEL_108;
      }
      v65 = 0;
      RegVal = GetRegVal(hKey, L"IdentityName", 6u, &v65, (void **)&Str);
      v26 = "GetStringRegVal";
      if ( (RegVal & 0x80000000) == 0 )
      {
        if ( !wcschr(Str, 0x40u) )
        {
          v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          LODWORD(v58) = 1114;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225570LL, v28, v58, "Cached Identity Name is invalid", v29);
          ((void (__fastcall *)(wchar_t *))g_pLsaFunctionTable->FreeLsaHeap)(Str);
          Str = 0;
        }
      }
      else
      {
        v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        LODWORD(v58) = 1103;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v27, v58, "GetStringRegVal", &Class);
        if ( RegVal != -1073741275 )
          goto LABEL_51;
      }
      if ( (_BYTE)v67 )
      {
        v65 = 0;
        RegVal = GetRegVal(hKey, L"SAMName", 6u, &v65, (void **)&v66);
        if ( (RegVal & 0x80000000) == 0 )
        {
          v12 = v66;
          if ( wcschr(v66, 0x40u) )
          {
            v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
            LODWORD(v58) = 1140;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225570LL, v31, v58, "Cached SAM Name is invalid", &Class);
            ((void (__fastcall *)(wchar_t *))g_pLsaFunctionTable->FreeLsaHeap)(Str);
            Str = 0;
          }
        }
        else
        {
          v30 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          LODWORD(v58) = 1129;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v30, v58, "GetStringRegVal", &Class);
          v12 = v66;
          if ( RegVal != -1073741275 )
            goto LABEL_51;
        }
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl) )
      {
        v65 = 0;
        RegVal = GetRegVal(hKey, L"DisplayName", 6u, &v65, &v69);
        if ( (RegVal & 0x80000000) != 0 )
        {
          v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          LODWORD(v58) = 1157;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v32, v58, "GetStringRegVal", &Class);
          if ( RegVal != -1073741275 )
            goto LABEL_51;
        }
        RegVal = DuplicateString(L"user", 1, &v70);
        if ( RegVal )
        {
          v26 = "DuplicateString";
          goto LABEL_51;
        }
      }
    }
    RtlReleaseResource(&g_LookupsCacheLock);
    if ( !Str || (_BYTE)v67 && !v12 )
    {
      if ( v12 )
      {
        ((void (__fastcall *)(wchar_t *))g_pLsaFunctionTable->FreeLsaHeap)(v12);
        v12 = 0;
        v66 = 0;
      }
      if ( Str )
      {
        ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
        Str = 0;
      }
      v38 = v74;
      v39 = (__int64 (__fastcall *)(_QWORD, void *, void *, wchar_t **, void **, __int64 *, __int64 *, unsigned __int16 **, unsigned __int16 **, __int64 *, unsigned __int16 **))*((_QWORD *)v74 + 35);
      if ( !v39 )
      {
        RegVal = -1073741709;
        v53 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        LODWORD(v58) = 1327;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v54, v53, v58, "SID-Name cannot be resolved", &Class);
        goto LABEL_108;
      }
      RegVal = v39(*((_QWORD *)v74 + 1), v84, v79, &Str, &v69, &v75, &v76, &Src, &v71, &v77, &v70);
      if ( (RegVal & 0x80000000) != 0 )
      {
        Str = 0;
        v69 = 0;
        v75 = 0;
        v76 = 0;
        Src = 0;
        v71 = 0;
        v77 = 0;
        v70 = 0;
        v40 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        LODWORD(v58) = 1220;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v40, v58, "LookupIdentityNameFromSID", &Class);
        if ( RegVal != -1073741801 && RegVal != -1073741670 && RegVal != -1073741822 )
          RegVal = -1073741709;
        v41 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        v61 = (unsigned __int16 **)&Class;
        v59 = "LookupIdentityNameFromSID";
        LODWORD(v58) = 1228;
        goto LABEL_67;
      }
      v42 = 0;
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl) )
        v42 = (unsigned int)IsUserSidNameType(v70) != 0;
      if ( (_BYTE)v67 )
      {
        if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl)
          || v42 )
        {
          RegVal = DuplicateString(Str, 1, (unsigned __int16 **)&lpSrcStr);
          if ( RegVal )
          {
            v45 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
            LODWORD(v58) = 1263;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v45, v58, "DuplicateString", &Class);
            v46 = lpSrcStr;
            goto LABEL_109;
          }
          v62 = (unsigned __int16 *)lpSrcStr;
          RegVal = GetHashString(lpSrcStr, v96);
          if ( RegVal )
          {
            v41 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
            v61 = (unsigned __int16 **)&Class;
            v59 = "DuplicateString";
            LODWORD(v58) = 1266;
            goto LABEL_67;
          }
          v88 = v79;
          v89 = v69;
          v90 = v75;
          v91 = v76;
          v92 = Src;
          v93 = v71;
          v94 = v77;
          DerefSubPackage((PRTL_RESOURCE *)v38, v68);
          v68 = 0;
          ((void (__fastcall *)(const unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v11);
          SourceString = 0;
          RegVal = UpdateSidNameCaches(
                     v38,
                     &v68,
                     (unsigned __int16 **)&SourceString,
                     v96,
                     v62,
                     (struct _APPLUGIN_USER_INFO *)v87,
                     0);
          if ( RegVal )
          {
            v44 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
            v60 = "UpdateSidNameCaches";
            LODWORD(v58) = 1294;
            goto LABEL_81;
          }
          v47 = 0;
          if ( v68 )
            v48 = (HKEY)*((_QWORD *)v68 + 74);
          else
            v48 = (HKEY)*((_QWORD *)v38 + 44);
          if ( (*((_BYTE *)v38 + 160) & 8) != 0 )
          {
            v86[0] = v92;
            v86[1] = v93;
            v86[2] = v94;
            if ( DoesUserHaveFederatedInfo(v86) )
              v47 = 1;
          }
          RegVal = GenAndPersistNT4StyleName(v47, v48, v79, v96, v62, (struct _APPLUGIN_USER_INFO *)v87, &v66);
          if ( RegVal )
          {
            v49 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
            LODWORD(v58) = 1320;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v49, v58, "GenAndPersistNT4StyleName", &Class);
            v11 = SourceString;
            goto LABEL_76;
          }
          v12 = v66;
        }
        else
        {
          if ( Src )
          {
            RegVal = DuplicateString(Src, 1, &v66);
            if ( RegVal )
            {
              v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
              LODWORD(v58) = 1250;
              WPPTraceLogA(
                0,
                "0x%08x %s:%u : %s:%ws",
                RegVal,
                v43,
                v58,
                "DuplicateString pwszUserDownLevelName",
                &Class);
LABEL_76:
              v12 = v66;
              goto LABEL_108;
            }
            v12 = v66;
          }
          if ( !v71 )
            goto LABEL_98;
          ((void (__fastcall *)(const unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v11);
          RegVal = DuplicateString(v71, 1, (unsigned __int16 **)&SourceString);
          if ( RegVal )
          {
            v44 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
            v60 = "DuplicateString  pwszUserDomainNetBiosName";
            LODWORD(v58) = 1256;
LABEL_81:
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v44, v58, v60, &Class);
            goto LABEL_23;
          }
        }
        v11 = SourceString;
      }
    }
LABEL_98:
    v50 = v81;
    v51 = v83;
    *v80 = (unsigned __int16 *)v11;
    v11 = 0;
    *v85 = v12;
    v12 = 0;
    *v50 = v70;
    v52 = (unsigned __int16 *)v69;
    v70 = 0;
    v69 = 0;
    *v82 = v52;
    if ( v62 )
    {
      *v51 = v62;
      v46 = 0;
LABEL_103:
      RegVal = 0;
      goto LABEL_109;
    }
    RegVal = DuplicateString(Str, 1, v51);
    if ( !RegVal )
    {
      v46 = 0;
      goto LABEL_103;
    }
    v41 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    v61 = (unsigned __int16 **)&Class;
    v59 = "DuplicateString";
    LODWORD(v58) = 1351;
LABEL_67:
    v16 = v41;
    v17 = RegVal;
    goto LABEL_107;
  }
  v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RegVal, v22, 1068, "DuplicateString", &Class);
LABEL_23:
  v11 = SourceString;
LABEL_108:
  v46 = v62;
LABEL_109:
  DerefSubPackage((PRTL_RESOURCE *)v74, v68);
  DerefPackage(v74);
  if ( v11 )
    ((void (__fastcall *)(const unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v11);
  if ( v12 )
    ((void (__fastcall *)(wchar_t *))g_pLsaFunctionTable->FreeLsaHeap)(v12);
  if ( Str )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v69 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v75 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v76 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( Src )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v46 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v46);
  if ( v71 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v77 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v70 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( hKey )
    RegCloseKey(hKey);
  return RegVal;
}

```

## disassembly

```asm
0x18004e7b0  push    rbp
0x18004e7b2  push    rbx
0x18004e7b3  push    rsi
0x18004e7b4  push    rdi
0x18004e7b5  push    r12
0x18004e7b7  push    r13
0x18004e7b9  push    r14
0x18004e7bb  push    r15
0x18004e7bd  lea     rbp, [rsp-188h]
0x18004e7c5  sub     rsp, 288h
0x18004e7cc  mov     rax, cs:__security_cookie
0x18004e7d3  xor     rax, rsp
0x18004e7d6  mov     [rbp+1C0h+var_50], rax
0x18004e7dd  mov     rax, [rbp+1C0h+arg_38]
0x18004e7e4  mov     rbx, rcx
0x18004e7e7  mov     rcx, [rbp+1C0h+arg_30]
0x18004e7ee  mov     r14, r8
0x18004e7f1  mov     r15, [rbp+1C0h+arg_20]
0x18004e7f8  mov     rsi, rdx
0x18004e7fb  mov     rdi, [rbp+1C0h+arg_28]
0x18004e802  xorps   xmm0, xmm0
0x18004e805  mov     [rbp+1C0h+var_1C0], rcx
0x18004e809  lea     rcx, [rbp+1C0h+var_180]; void *
0x18004e80d  mov     [rbp+1C0h+var_1D8], r8
0x18004e811  mov     r8d, 88h; Size
0x18004e817  mov     [rbp+1C0h+var_1B0], rdx
0x18004e81b  xor     edx, edx; Val
0x18004e81d  mov     [rbp+1C0h+var_1D0], r9
0x18004e821  mov     [rbp+1C0h+var_1A8], r15
0x18004e825  mov     [rbp+1C0h+var_1B8], rdi
0x18004e829  mov     [rbp+1C0h+var_1C8], rax
0x18004e82d  movups  xmmword ptr [rbp+1C0h+var_F0.Data1], xmm0
0x18004e834  call    memset_0
0x18004e839  mov     rdx, [rbp+1C0h+var_1D0]
0x18004e83d  xor     r8d, r8d
0x18004e840  mov     [rsp+2C0h+SourceString], r8
0x18004e845  mov     eax, r8d
0x18004e848  mov     [rsp+2C0h+var_260], rax
0x18004e84d  mov     r12d, r8d
0x18004e850  mov     [rbp+1C0h+lpSrcStr], rax
0x18004e854  mov     r13d, r8d
0x18004e857  mov     [rbp+1C0h+var_240], r8
0x18004e85b  mov     [rsp+2C0h+Str], r8
0x18004e860  mov     [rbp+1C0h+var_228], r8
0x18004e864  mov     [rbp+1C0h+var_1F8], r8
0x18004e868  mov     [rbp+1C0h+var_1F0], r8
0x18004e86c  mov     [rbp+1C0h+Src], r8
0x18004e870  mov     [rbp+1C0h+var_218], r8
0x18004e874  mov     [rbp+1C0h+var_1E8], r8
0x18004e878  mov     [rbp+1C0h+var_220], r8
0x18004e87c  mov     [rbp+1C0h+var_200], r8
0x18004e880  mov     [rbp+1C0h+var_230], r8
0x18004e884  mov     [rbp+1C0h+hKey], r8
0x18004e888  test    rdx, rdx
0x18004e88b  jz      loc_18004F446
0x18004e891  test    r15, r15
0x18004e894  jz      loc_18004F446
0x18004e89a  test    rdi, rdi
0x18004e89d  jz      loc_18004F446
0x18004e8a3  mov     rcx, [rbp+1C0h+var_1C8]
0x18004e8a7  test    rcx, rcx
0x18004e8aa  jz      loc_18004F446
0x18004e8b0  mov     rax, [rbp+1C0h+var_1C0]
0x18004e8b4  test    rax, rax
0x18004e8b7  jz      loc_18004F446
0x18004e8bd  mov     [rdx], r8
0x18004e8c0  mov     [r15], r8
0x18004e8c3  mov     [rdi], r8
0x18004e8c6  mov     [rcx], r8
0x18004e8c9  mov     [rax], r8
0x18004e8cc  test    rbx, rbx
0x18004e8cf  jz      loc_18004F40C
0x18004e8d5  test    rsi, rsi
0x18004e8d8  jz      loc_18004F40C
0x18004e8de  test    r14, r14
0x18004e8e1  jz      loc_18004F40C
0x18004e8e7  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x18004e8ee  lea     rdx, [rbp+1C0h+var_F0]
0x18004e8f5  mov     rcx, rbx
0x18004e8f8  mov     rax, [rax+50h]
0x18004e8fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e901  mov     ebx, eax
0x18004e903  test    eax, eax
0x18004e905  jz      short loc_18004E93E
0x18004e907  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004e90e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004e913  mov     r9, rax
0x18004e916  lea     rdi, Class
0x18004e91d  mov     [rsp+2C0h+var_290], rdi
0x18004e922  lea     rax, aGetprovinfo; "GetProvInfo"
0x18004e929  mov     [rsp+2C0h+var_298], rax
0x18004e92e  mov     dword ptr [rsp+2C0h+var_2A0], 40Eh
0x18004e936  mov     r8d, ebx
0x18004e939  jmp     loc_18004F47E
0x18004e93e  lea     rdx, [rbp+1C0h+var_200]; struct _ApPluginPkg **
0x18004e942  lea     rcx, [rbp+1C0h+var_F0]; struct _GUID *
0x18004e949  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x18004e94e  mov     ebx, eax
0x18004e950  test    eax, eax
0x18004e952  jz      short loc_18004E985
0x18004e954  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004e95b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004e960  mov     r9, rax
0x18004e963  lea     rdi, Class
0x18004e96a  mov     [rsp+2C0h+var_290], rdi
0x18004e96f  lea     rax, aRefpackage; "RefPackage"
0x18004e976  mov     [rsp+2C0h+var_298], rax
0x18004e97b  mov     dword ptr [rsp+2C0h+var_2A0], 411h
0x18004e983  jmp     short loc_18004E936
0x18004e985  mov     rdi, [rbp+1C0h+var_200]
0x18004e989  mov     esi, [rdi+0A0h]
0x18004e98f  test    sil, 4
0x18004e993  jz      short loc_18004E9CE
0x18004e995  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004e99c  mov     ebx, 0C00000BBh
0x18004e9a1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004e9a6  mov     r9, rax
0x18004e9a9  lea     rdi, Class
0x18004e9b0  mov     [rsp+2C0h+var_290], rdi
0x18004e9b5  lea     rax, aSurrogatePlugi_0; "Surrogate plugin"
0x18004e9bc  mov     [rsp+2C0h+var_298], rax
0x18004e9c1  mov     dword ptr [rsp+2C0h+var_2A0], 417h
0x18004e9c9  jmp     loc_18004E936
0x18004e9ce  lea     r9, [rsp+2C0h+SourceString]; unsigned __int16 **
0x18004e9d3  mov     r8, r14; void *
0x18004e9d6  xor     edx, edx; unsigned __int16 *
0x18004e9d8  mov     rcx, rdi; struct _ApPluginPkg *
0x18004e9db  call    ?GetAuthenticatingAuthority@@YAJPEAU_ApPluginPkg@@PEAGPEAXPEAPEAG@Z; GetAuthenticatingAuthority(_ApPluginPkg *,ushort *,void *,ushort * *)
0x18004e9e0  mov     r12, [rsp+2C0h+SourceString]
0x18004e9e5  mov     ebx, eax
0x18004e9e7  test    eax, eax
0x18004e9e9  jz      short loc_18004EA26
0x18004e9eb  test    r12, r12
0x18004e9ee  lea     rdi, Class
0x18004e9f5  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004e9fc  cmovnz  rdi, r12
0x18004ea00  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004ea05  mov     [rsp+2C0h+var_290], rdi
0x18004ea0a  mov     r9, rax
0x18004ea0d  lea     rax, aGetauthenticat_0; "GetAuthenticatingAuthorityForIdentity"
0x18004ea14  mov     [rsp+2C0h+var_298], rax
0x18004ea19  mov     dword ptr [rsp+2C0h+var_2A0], 427h
0x18004ea21  jmp     loc_18004E936
0x18004ea26  test    r12, r12
0x18004ea29  jnz     short loc_18004EA90
0x18004ea2b  lea     rcx, [rdi+18h]; Src
0x18004ea2f  xor     edx, edx; int
0x18004ea31  lea     r8, [rsp+2C0h+SourceString]; unsigned __int16 **
0x18004ea36  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18004ea3b  mov     ebx, eax
0x18004ea3d  test    eax, eax
0x18004ea3f  jz      short loc_18004EA8B
0x18004ea41  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004ea48  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004ea4d  lea     rdi, Class
0x18004ea54  mov     r9, rax
0x18004ea57  mov     [rsp+2C0h+var_290], rdi
0x18004ea5c  lea     r15, aDuplicatestrin_1; "DuplicateString"
0x18004ea63  mov     [rsp+2C0h+var_298], r15
0x18004ea68  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004ea6f  mov     dword ptr [rsp+2C0h+var_2A0], 42Ch
0x18004ea77  mov     r8d, ebx
0x18004ea7a  xor     ecx, ecx
0x18004ea7c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004ea81  mov     r12, [rsp+2C0h+SourceString]
0x18004ea86  jmp     loc_18004F48C
0x18004ea8b  mov     r12, [rsp+2C0h+SourceString]
0x18004ea90  lea     rdx, [rdi+18h]; PCWSTR
0x18004ea94  mov     rcx, r12; SourceString
0x18004ea97  call    ?CloudAPCompareStrings@@YAHPEBG0@Z; CloudAPCompareStrings(ushort const *,ushort const *)
0x18004ea9c  test    eax, eax
0x18004ea9e  jz      short loc_18004EAFD
0x18004eaa0  lea     r8, [rbp+1C0h+var_230]; struct _ApPluginSubPkg **
0x18004eaa4  mov     rdx, r12; unsigned __int16 *
0x18004eaa7  mov     rcx, rdi; struct _ApPluginPkg *
0x18004eaaa  call    ?RefSubPackage@@YAJPEAU_ApPluginPkg@@PEBGPEAPEAU_ApPluginSubPkg@@@Z; RefSubPackage(_ApPluginPkg *,ushort const *,_ApPluginSubPkg * *)
0x18004eaaf  mov     ebx, eax
0x18004eab1  test    eax, eax
0x18004eab3  jz      short loc_18004EAF0
0x18004eab5  test    r12, r12
0x18004eab8  lea     rdi, Class
0x18004eabf  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004eac6  cmovnz  rdi, r12
0x18004eaca  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004eacf  mov     [rsp+2C0h+var_290], rdi
0x18004ead4  mov     r9, rax
0x18004ead7  lea     rax, aRefsubpackage; "RefSubPackage"
0x18004eade  mov     [rsp+2C0h+var_298], rax
0x18004eae3  mov     dword ptr [rsp+2C0h+var_2A0], 433h
0x18004eaeb  jmp     loc_18004E936
0x18004eaf0  mov     rbx, [rbp+1C0h+var_230]
0x18004eaf4  mov     rbx, [rbx+250h]
0x18004eafb  jmp     short loc_18004EB04
0x18004eafd  mov     rbx, [rdi+160h]
0x18004eb04  mov     eax, 1
0x18004eb09  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18004eb10  not     sil
0x18004eb13  mov     dl, al; Wait
0x18004eb15  and     sil, al
0x18004eb18  mov     [rbp+1C0h+var_238], esi
0x18004eb1b  call    cs:__imp_RtlAcquireResourceShared
0x18004eb21  lea     r8, [rbp+1C0h+hKey]; phkResult
0x18004eb25  mov     rdx, r14; void *
0x18004eb28  mov     rcx, rbx; hKey
0x18004eb2b  call    ?FindUserInCacheBySid@@YAJPEAUHKEY__@@PEAXPEAPEAU1@@Z; FindUserInCacheBySid(HKEY__ *,void *,HKEY__ * *)
0x18004eb30  mov     r8d, 0C0000225h
0x18004eb36  mov     ebx, eax
0x18004eb38  cmp     eax, r8d
0x18004eb3b  jz      loc_18004EE33
0x18004eb41  test    eax, eax
0x18004eb43  jz      short loc_18004EB6C
0x18004eb45  lea     rsi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004eb4c  mov     r8d, 446h
0x18004eb52  lea     r15, aFinduserincach; "FindUserInCacheBySid"
0x18004eb59  lea     rdi, Class
0x18004eb60  lea     r14, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004eb67  jmp     loc_18004EDF6
0x18004eb6c  mov     rcx, [rbp+1C0h+hKey]; hkey
0x18004eb70  lea     rax, [rsp+2C0h+Str]
0x18004eb75  lea     r9, [rsp+2C0h+var_248]; unsigned int *
0x18004eb7a  mov     [rsp+2C0h+var_2A0], rax; void **
0x18004eb7f  mov     r8d, 6; dwFlags
0x18004eb85  mov     [rsp+2C0h+var_248], r13d
0x18004eb8a  lea     rdx, aIdentityname; "IdentityName"
0x18004eb91  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x18004eb96  lea     r14, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004eb9d  mov     ebx, eax
0x18004eb9f  lea     rdi, Class
0x18004eba6  lea     rsi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004ebad  lea     r15, aGetstringregva_3; "GetStringRegVal"
0x18004ebb4  test    eax, eax
0x18004ebb6  jns     short loc_18004EBF5
0x18004ebb8  mov     rcx, r14; char *
0x18004ebbb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004ebc0  mov     [rsp+2C0h+var_290], rdi
0x18004ebc5  mov     r9, rax
0x18004ebc8  mov     [rsp+2C0h+var_298], r15
0x18004ebcd  mov     rdx, rsi
0x18004ebd0  mov     r8d, ebx
0x18004ebd3  mov     dword ptr [rsp+2C0h+var_2A0], 44Fh
0x18004ebdb  xor     ecx, ecx
0x18004ebdd  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004ebe2  cmp     ebx, 0C0000225h
0x18004ebe8  jz      short loc_18004EC67
0x18004ebea  mov     r8d, 452h
0x18004ebf0  jmp     loc_18004EDF6
0x18004ebf5  mov     rcx, [rsp+2C0h+Str]; Str
0x18004ebfa  mov     edx, 40h ; '@'; Ch
0x18004ebff  call    cs:__imp_wcschr
0x18004ec05  test    rax, rax
0x18004ec08  jnz     short loc_18004EC67
0x18004ec0a  mov     rax, [rsp+2C0h+Str]
0x18004ec0f  mov     r8, rdi
0x18004ec12  test    rax, rax
0x18004ec15  mov     rcx, r14; char *
0x18004ec18  cmovnz  r8, rax
0x18004ec1c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004ec21  mov     [rsp+2C0h+var_290], r8
0x18004ec26  mov     r9, rax
0x18004ec29  lea     rax, aCachedIdentity; "Cached Identity Name is invalid"
0x18004ec30  mov     r8d, 0C0000062h
0x18004ec36  mov     [rsp+2C0h+var_298], rax
0x18004ec3b  mov     rdx, rsi
0x18004ec3e  xor     ecx, ecx
0x18004ec40  mov     dword ptr [rsp+2C0h+var_2A0], 45Ah
0x18004ec48  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004ec4d  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004ec54  mov     rcx, [rsp+2C0h+Str]
0x18004ec59  mov     rax, [rax+30h]
0x18004ec5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec62  mov     [rsp+2C0h+Str], r13
0x18004ec67  cmp     byte ptr [rbp+1C0h+var_238], r13b
0x18004ec6b  jz      loc_18004ED4A
0x18004ec71  mov     rcx, [rbp+1C0h+hKey]; hkey
0x18004ec75  lea     rax, [rbp+1C0h+var_240]
0x18004ec79  lea     r9, [rsp+2C0h+var_248]; unsigned int *
0x18004ec7e  mov     [rsp+2C0h+var_2A0], rax; void **
0x18004ec83  mov     r8d, 6; dwFlags
0x18004ec89  mov     [rsp+2C0h+var_248], r13d
0x18004ec8e  lea     rdx, aSamname; "SAMName"
0x18004ec95  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x18004ec9a  mov     ebx, eax
0x18004ec9c  test    eax, eax
0x18004ec9e  jns     short loc_18004ECE1
0x18004eca0  mov     rcx, r14; char *
0x18004eca3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004eca8  mov     [rsp+2C0h+var_290], rdi
0x18004ecad  mov     r9, rax
0x18004ecb0  mov     [rsp+2C0h+var_298], r15
0x18004ecb5  mov     rdx, rsi
0x18004ecb8  mov     r8d, ebx
0x18004ecbb  mov     dword ptr [rsp+2C0h+var_2A0], 469h
0x18004ecc3  xor     ecx, ecx
0x18004ecc5  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004ecca  mov     r13, [rbp+1C0h+var_240]
0x18004ecce  cmp     ebx, 0C0000225h
0x18004ecd4  jz      short loc_18004ED4A
0x18004ecd6  mov     r8d, 46Ch
0x18004ecdc  jmp     loc_18004EDF6
0x18004ece1  mov     r13, [rbp+1C0h+var_240]
  ... truncated ...
```
