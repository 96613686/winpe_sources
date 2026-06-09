# LsaApPostLogonUser(_SECPKG_POST_LOGON_USER_INFO *)

- ea: `0x180016a10`
- end: `0x180017777`
- name: `?LsaApPostLogonUser@@YAJPEAU_SECPKG_POST_LOGON_USER_INFO@@@Z`
- size: `3431`
- prototype: `__int64 __fastcall(struct _SECPKG_POST_LOGON_USER_INFO *)`
- caller_count: `0`
- callee_count: `22`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007ef0`
- `0x180009bf0`
- `0x18000a600`
- `0x18000ce50`
- `0x18000e7e0`
- `0x18000e900`
- `0x18000fb70`
- `0x18000fd50`
- `0x180010320`
- `0x180016a10`
- `0x18002223c`
- `0x18002ae10`
- `0x18002c130`
- `0x18002feb4`
- `0x1800363b8`
- `0x180039090`
- `0x18004317c`
- `0x18005a0d0`
- `0x1800651b8`
- `0x18007f9f0`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800172d6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800172d6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800172c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800172c1`
- `ntdll!RtlReleaseResource` at `0x180016c5c`
- `ntdll!RtlReleaseResource` at `0x180017667`
- `ntdll!RtlReleaseResource` at `0x180016c5c`
- `ntdll!RtlReleaseResource` at `0x180017667`
- `ntdll!RtlAcquireResourceShared` at `0x180016c4c`
- `ntdll!RtlAcquireResourceShared` at `0x180016c4c`
- `ntdll!NtClose` at `0x1800176ac`
- `ntdll!NtClose` at `0x1800176ac`

## string_xrefs

- `0x180016ebf`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180016f79`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x18001753f`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180016adf`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180016b77`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180016bec`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180016c69`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800171f5`: `CacheData`
- `0x18001722a`: `GetLogonCacheForUser`
- `0x1800173fa`: `UpdatePluginOpaqueCacheBlob`
- `0x18001746a`: `SaveCaches`
- `0x180016ba1`: `CreateLogonSession`
- `0x180017041`: `OpenTokenByLogonId`
- `0x18001732a`: `UpdatePwdExpiryInfo`
- `0x18001751a`: `Not updating cache as cred data has changed`

## pseudocode

```c
__int64 __fastcall LsaApPostLogonUser(struct _SECPKG_POST_LOGON_USER_INFO *a1)
{
  struct _CloudAPCache *v1; // r12
  struct _APPLUGIN_USER_INFO *v2; // r13
  LUID *p_LinkedLogonId; // r15
  unsigned int LogonCacheForUser; // edi
  const char *v6; // rbx
  char v7; // al
  const char *v8; // rcx
  bool v9; // zf
  struct _LOGON_SESSION *v10; // rbx
  char v11; // al
  struct _LOGON_SESSION *v12; // rdi
  LUID *p_LogonId; // r12
  char v14; // al
  int v15; // edi
  const char *v16; // rbx
  int KerberosCallbackSupplementalCredential; // eax
  const char *v18; // r9
  char v19; // cl
  const char *v20; // rdx
  bool v21; // zf
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v22; // rdi
  unsigned __int64 v23; // rdx
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *i; // rax
  struct _LOGON_SESSION *v25; // r14
  char v26; // al
  const char *v27; // rcx
  bool v28; // zf
  __int64 v29; // r14
  size_t v30; // r13
  struct _CloudAPCache *v31; // rax
  struct _CloudAPCache *v32; // rdi
  const char *v33; // r9
  char v34; // cl
  const char *v35; // rdx
  struct _CloudAPCache *v36; // r15
  const char *v37; // rax
  int v38; // ecx
  size_t v39; // r13
  void *v40; // rax
  void *v41; // r12
  char v42; // cl
  const char *v43; // rdx
  char v44; // al
  const char *v45; // r9
  char v46; // al
  const char *v47; // rcx
  bool v48; // zf
  char v49; // al
  struct _CloudAPCache *v50; // rax
  int v51; // ecx
  struct _ApPluginPkg *v52; // r13
  char v53; // al
  const char *v54; // rcx
  bool v55; // zf
  char v56; // al
  struct _APPLUGIN_USER_INFO *v57; // rdi
  char v58; // al
  struct _CloudAPCache *v59; // r15
  char v60; // al
  char v61; // al
  _BYTE *v62; // rax
  __int64 v63; // rcx
  char v64; // al
  char v65; // cl
  const char *v66; // rdx
  __int64 v67; // rdx
  struct _CloudAPCache *v68; // rax
  char v69; // al
  struct _CloudAPCache *v70; // rcx
  __int64 v71; // rax
  _BYTE *v72; // rcx
  __int64 v73; // rax
  struct _APPLUGIN_USER_INFO **v75; // [rsp+28h] [rbp-E0h]
  int v76; // [rsp+28h] [rbp-E0h]
  const char *v77; // [rsp+30h] [rbp-D8h]
  const char *v78; // [rsp+30h] [rbp-D8h]
  const char *v79; // [rsp+30h] [rbp-D8h]
  size_t v80[2]; // [rsp+58h] [rbp-B0h] BYREF
  struct _LOGON_SESSION *v81; // [rsp+68h] [rbp-A0h] BYREF
  struct _CloudAPCache *Size[3]; // [rsp+70h] [rbp-98h] BYREF
  struct _ApPluginPkg *v83; // [rsp+88h] [rbp-80h] BYREF
  struct _CloudAPCache *v84; // [rsp+90h] [rbp-78h]
  _FILETIME SystemTimeAsFileTime; // [rsp+98h] [rbp-70h] BYREF
  HANDLE Handle; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v87; // [rsp+A8h] [rbp-60h]
  void *Buf1[2]; // [rsp+B8h] [rbp-50h]
  __int128 v89; // [rsp+C8h] [rbp-40h]
  __int128 v90; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v91; // [rsp+E8h] [rbp-20h]
  _QWORD v92[10]; // [rsp+F8h] [rbp-10h] BYREF
  int v93; // [rsp+148h] [rbp+40h]
  char v94; // [rsp+218h] [rbp+110h]
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v95; // [rsp+220h] [rbp+118h] BYREF
  unsigned __int64 v96; // [rsp+228h] [rbp+120h] BYREF
  struct _APPLUGIN_USER_INFO *v97; // [rsp+230h] [rbp+128h] BYREF

  v1 = 0;
  v2 = 0;
  p_LinkedLogonId = &a1->LinkedLogonId;
  v9 = *(_QWORD *)&a1->LinkedLogonId == 0;
  v90 = 0;
  v94 = 0;
  v91 = 0;
  SystemTimeAsFileTime = 0;
  Handle = 0;
  v81 = 0;
  v83 = 0;
  memset(Size, 0, sizeof(Size));
  v97 = 0;
  *(_OWORD *)Buf1 = 0;
  *(_OWORD *)v80 = 0;
  if ( v9 )
  {
    p_LinkedLogonId = &a1->LogonId;
    goto LABEL_22;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl)
    || !(unsigned int)LUAIsShadowAdminEnabled() )
  {
    goto LABEL_22;
  }
  v95 = 0;
  LogonCacheForUser = _AcquireLogonSession(1, p_LinkedLogonId, (struct _LOGON_SESSION **)&v95);
  if ( !LogonCacheForUser )
  {
    v10 = (struct _LOGON_SESSION *)v95;
    p_LinkedLogonId = &a1->LogonId;
    LogonCacheForUser = CreateLogonSession(
                          &a1->LogonId,
                          (struct _USER_CACHE_ENTRY *)v95[1].Credentials[0].PackageName.Buffer,
                          *(struct _SCARD_PIN **)&v95[1].Credentials[0].CredentialSize,
                          &v81);
    ReleaseLogonSession(v10);
    if ( LogonCacheForUser )
    {
      v6 = "";
      while ( 1 )
      {
        v11 = *(v6 - 1);
        v8 = v6--;
        v9 = v11 == 92;
        if ( v11 == 92 )
          break;
        if ( v6 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v9 = v11 == 92;
          break;
        }
      }
      v77 = "CreateLogonSession";
      v76 = 10820;
      goto LABEL_10;
    }
    v12 = v81;
    if ( v81 )
    {
      p_LogonId = &a1->LogonId;
LABEL_29:
      RtlAcquireResourceShared(&g_LogonSessionListLock, 1u);
      v15 = *((_DWORD *)v12 + 6);
      RtlReleaseResource(&g_LogonSessionListLock);
      v16 = "";
      if ( v15 )
      {
        memset_0(v92, 0, 0xC8u);
        v92[0] = *p_LogonId;
        v93 = 0x400000;
        v95 = 0;
        v96 = 0;
        KerberosCallbackSupplementalCredential = MakeKerberosCallbackSupplementalCredential(&v96, &v95);
        if ( KerberosCallbackSupplementalCredential >= 0 )
        {
          v22 = v95;
          ((void (__fastcall *)(_QWORD *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *))g_pLsaFunctionTable->UpdateCredentials)(
            v92,
            v95);
          v23 = v96;
          for ( i = v22; v23; --v23 )
          {
            LOBYTE(i->CredentialCount) = 0;
            i = (struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *)((char *)i + 1);
          }
          ((void (__fastcall *)(struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *))g_pLsaFunctionTable->FreeLsaHeap)(v22);
        }
        else
        {
          v18 = "";
          while ( 1 )
          {
            v19 = *(v18 - 1);
            v20 = v18--;
            v21 = v19 == 92;
            if ( v19 == 92 )
              break;
            if ( v18 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
            {
              v21 = v19 == 92;
              break;
            }
          }
          if ( v21 )
            v18 = v20;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            (unsigned int)KerberosCallbackSupplementalCredential,
            v18,
            10848,
            "MakeKerberosCallbackSupplementalCredential",
            &Class);
        }
      }
      if ( (a1->Flags & 0x40000) != 0 )
      {
        LogonCacheForUser = 0;
LABEL_172:
        v2 = v97;
        v1 = Size[0];
        goto LABEL_173;
      }
      v25 = v81;
      LogonCacheForUser = RefPackage((struct _GUID *)((char *)v81 + 36), &v83);
      if ( LogonCacheForUser )
      {
        while ( 1 )
        {
          v26 = *(v16 - 1);
          v27 = v16--;
          v28 = v26 == 92;
          if ( v26 == 92 )
            break;
          if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
          {
            v28 = v26 == 92;
            break;
          }
        }
        v78 = "RefPackage";
        LODWORD(v75) = 10869;
LABEL_48:
        if ( v28 )
          v16 = v27;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCacheForUser, v16, v75, v78, &Class);
        goto LABEL_170;
      }
      if ( !*((_QWORD *)v83 + 42) || !*((_QWORD *)v83 + 23) || (*((_BYTE *)v83 + 160) & 4) != 0 )
        goto LABEL_169;
      v29 = *((_QWORD *)v25 + 7);
      LockAndUnProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v29, 0);
      v87 = 0;
      v89 = 0;
      if ( !v29 )
      {
        LogonCacheForUser = -1073741811;
        v33 = "";
        do
        {
          v65 = *(v33 - 1);
          v66 = v33--;
        }
        while ( v65 != 92 && v33 > "onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp" );
        v36 = (struct _CloudAPCache *)*((_QWORD *)&v87 + 1);
        v37 = "Null Arg(s)";
        v9 = v65 == 92;
        v38 = 824;
        if ( v9 )
          v33 = v66;
        LODWORD(v30) = v87;
        goto LABEL_155;
      }
      if ( Buf1[1] )
        ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
      if ( Size[2] )
        ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
      *(_OWORD *)&Size[1] = 0;
      if ( *(_QWORD *)(v29 + 288) )
      {
        LODWORD(v95) = *(_DWORD *)(v29 + 280);
        v30 = (unsigned int)v95;
        v31 = (struct _CloudAPCache *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)((unsigned int)v95);
        v84 = v31;
        v32 = v31;
        if ( !v31 )
        {
          LogonCacheForUser = -1073741801;
          v33 = "";
          do
          {
            v34 = *(v33 - 1);
            v35 = v33--;
          }
          while ( v34 != 92 && v33 > "onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp" );
          v36 = v84;
          v37 = "AllocateLsaHeap";
          v9 = v34 == 92;
          v38 = 847;
          if ( v9 )
            v33 = v35;
LABEL_155:
          v41 = (void *)*((_QWORD *)&v89 + 1);
          goto LABEL_156;
        }
        memcpy_0(v31, *(const void **)(v29 + 288), v30);
      }
      else
      {
        v32 = (struct _CloudAPCache *)*((_QWORD *)&v87 + 1);
        v84 = (struct _CloudAPCache *)*((_QWORD *)&v87 + 1);
        LODWORD(v95) = v87;
      }
      v9 = *(_QWORD *)(v29 + 304) == 0;
      v39 = *(unsigned int *)(v29 + 300);
      LODWORD(v96) = *(_DWORD *)(v29 + 296);
      if ( v9 )
      {
        v41 = (void *)*((_QWORD *)&v89 + 1);
      }
      else
      {
        v40 = (void *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)((unsigned int)v39);
        v41 = v40;
        if ( !v40 )
        {
          LogonCacheForUser = -1073741801;
          v33 = "";
          do
          {
            v42 = *(v33 - 1);
            v43 = v33--;
          }
          while ( v42 != 92 && v33 > "onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp" );
          v36 = v84;
          v37 = "AllocateLsaHeap";
          LODWORD(v30) = (_DWORD)v95;
          v9 = v42 == 92;
          v38 = 860;
          if ( v9 )
            v33 = v43;
LABEL_156:
          LODWORD(v75) = v38;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCacheForUser, v33, v75, v37, &Class);
          if ( v36 )
          {
            v67 = (unsigned int)v30;
            v68 = v36;
            if ( (_DWORD)v30 )
            {
              do
              {
                *(_BYTE *)v68 = 0;
                v68 = (struct _CloudAPCache *)((char *)v68 + 1);
                --v67;
              }
              while ( v67 );
            }
            ((void (__fastcall *)(struct _CloudAPCache *, __int64))g_pLsaFunctionTable->FreeLsaHeap)(v36, v67);
          }
          if ( v41 )
            ((void (__fastcall *)(void *))g_pLsaFunctionTable->FreeLsaHeap)(v41);
          while ( 1 )
          {
            v69 = *(v16 - 1);
            v54 = v16--;
            v55 = v69 == 92;
            if ( v69 == 92 )
              break;
            if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
            {
              v55 = v69 == 92;
              break;
            }
          }
          v79 = "DuplicateCredentialData";
          LODWORD(v75) = 10893;
LABEL_166:
          if ( v55 )
            v16 = v54;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCacheForUser, v16, v75, v79, &Class);
          UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v29);
          goto LABEL_170;
        }
        memcpy_0(v40, *(const void **)(v29 + 304), v39);
      }
      LODWORD(Size[1]) = (_DWORD)v95;
      Size[2] = v32;
      Buf1[1] = v41;
      UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v29);
      LogonCacheForUser = ((__int64 (__fastcall *)(LUID *, HANDLE *))g_pLsaFunctionTable->OpenTokenByLogonId)(
                            p_LinkedLogonId,
                            &Handle);
      if ( LogonCacheForUser )
      {
        while ( 1 )
        {
          v44 = *(v16 - 1);
          v27 = v16--;
          v28 = v44 == 92;
          if ( v44 == 92 )
            break;
          if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
          {
            v28 = v44 == 92;
            break;
          }
        }
        v78 = "OpenTokenByLogonId";
        LODWORD(v75) = 10902;
        goto LABEL_48;
      }
      LogonCacheForUser = (*((__int64 (__fastcall **)(_QWORD, HANDLE, struct _CloudAPCache **, size_t *))v83 + 42))(
                            *((_QWORD *)v83 + 1),
                            Handle,
                            &Size[1],
                            v80);
      if ( (LogonCacheForUser & 0x80000000) == 0 )
      {
        v50 = (struct _CloudAPCache *)v80[1];
        v51 = v80[0];
      }
      else
      {
        v45 = "";
        while ( 1 )
        {
          v46 = *(v45 - 1);
          v47 = v45--;
          v48 = v46 == 92;
          if ( v46 == 92 )
            break;
          if ( v45 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
          {
            v48 = v46 == 92;
            break;
          }
        }
        if ( v48 )
          v45 = v47;
        LODWORD(v75) = 10912;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCacheForUser, v45, v75, "PostLogonProcessing", &Class);
        if ( LogonCacheForUser != -1073741711 )
        {
          LODWORD(v80[0]) = 0;
          v80[1] = 0;
          while ( 1 )
          {
            v49 = *(v16 - 1);
            v27 = v16--;
            v28 = v49 == 92;
            if ( v49 == 92 )
              break;
            if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
            {
              v28 = v49 == 92;
              break;
            }
          }
          v78 = "PostLogonProcessing";
          LODWORD(v75) = 10917;
          goto LABEL_48;
        }
        v50 = Size[2];
        v51 = (int)Size[1];
        v80[1] = (size_t)Size[2];
        v94 = 1;
        LODWORD(v80[0]) = Size[1];
      }
      if ( v50 && v51 )
      {
        v29 = *((_QWORD *)v81 + 7);
        LockAndUnProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v29, 1);
        if ( (_DWORD)v96 != *(_DWORD *)(v29 + 296)
          || (_DWORD)v39 != *(_DWORD *)(v29 + 300)
          || (_DWORD)v39 && memcmp_0(Buf1[1], *(const void **)(v29 + 304), v39)
          || LODWORD(Size[1]) != *(_DWORD *)(v29 + 280)
          || memcmp_0(Size[2], *(const void **)(v29 + 288), LODWORD(Size[1])) )
        {
          LogonCacheForUser = -1073741564;
          while ( 1 )
          {
            v64 = *(v16 - 1);
            v54 = v16--;
            v55 = v64 == 92;
            if ( v64 == 92 )
              break;
            if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
            {
              v55 = v64 == 92;
              break;
            }
          }
          v79 = "Not updating cache as cred data has changed";
          LODWORD(v75) = 10954;
          goto LABEL_166;
        }
        v52 = v83;
        LogonCacheForUser = _GetLogonCacheForUser(
                              *((const unsigned __int16 **)v83 + 43),
                              (const unsigned __int16 *)(v29 + 104),
                              L"CacheData",
                              Size);
        if ( LogonCacheForUser )
        {
          while ( 1 )
          {
            v53 = *(v16 - 1);
            v54 = v16--;
            v55 = v53 == 92;
            if ( v53 == 92 )
              break;
            if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
            {
              v55 = v53 == 92;
              break;
            }
          }
          v79 = "GetLogonCacheForUser";
          LODWORD(v75) = 10965;
          goto LABEL_166;
        }
        LogonCacheForUser = ValidateUserInfo(
                              v52,
                              (struct _GUID *)((char *)Size[0] + 4),
                              (unsigned __int8 *)v80[1],
                              v80[0],
                              &v97,
                              0,
                              0,
                              0);
        if ( LogonCacheForUser )
        {
          while ( 1 )
          {
            v56 = *(v16 - 1);
            v54 = v16--;
            v55 = v56 == 92;
            if ( v56 == 92 )
              break;
            if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
            {
              v55 = v56 == 92;
              break;
            }
          }
          v79 = "ValidateUserInfo";
          LODWORD(v75) = 10977;
          goto LABEL_166;
        }
        if ( v94 )
        {
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          v57 = v97;
          if ( CompareFileTime((const FILETIME *)v97 + 13, &SystemTimeAsFileTime) >= 0 )
            *((_QWORD *)v57 + 13) = *(_QWORD *)&SystemTimeAsFileTime - 864000000000LL;
        }
        LogonCacheForUser = UpdatePwdExpiryInfo((struct _USER_CACHE_ENTRY *)v29, 1, v97);
        if ( LogonCacheForUser )
        {
          while ( 1 )
          {
            v58 = *(v16 - 1);
            v54 = v16--;
            v55 = v58 == 92;
            if ( v58 == 92 )
              break;
            if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
            {
              v55 = v58 == 92;
              break;
            }
          }
          v79 = "UpdatePwdExpiryInfo";
          LODWORD(v75) = 10993;
          goto LABEL_166;
        }
        if ( (LODWORD(v80[0]) != *(_DWORD *)(v29 + 280)
           || memcmp_0((const void *)v80[1], *(const void **)(v29 + 288), LODWORD(v80[0])))
          && !v94 )
        {
          v59 = Size[0];
          *(_QWORD *)&v90 = *((_QWORD *)v52 + 1);
          *((_QWORD *)&v90 + 1) = *((_QWORD *)v52 + 29);
          *(_QWORD *)&v91 = *((_QWORD *)v52 + 30);
          *((_QWORD *)&v91 + 1) = SecureFreeCacheData;
          LogonCacheForUser = UpdatePluginOpaqueCacheBlob(
                                Size[0],
                                (struct _tagCacheNodeIdentifier *)(v29 + 296),
                                *(struct _CREDENTIAL_KEY **)(v29 + 264),
                                (struct _AP_BLOB *)v80,
                                (struct _tagCacheDataFuncs *)&v90);
          if ( LogonCacheForUser )
          {
            while ( 1 )
            {
              v60 = *(v16 - 1);
              v54 = v16--;
              v55 = v60 == 92;
              if ( v60 == 92 )
                break;
              if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
              {
                v55 = v60 == 92;
                break;
              }
            }
            v79 = "UpdatePluginOpaqueCacheBlob";
            LODWORD(v75) = 11016;
          }
          else
          {
            LogonCacheForUser = SaveCaches(
                                  (const unsigned __int16 **)v52,
                                  1,
                                  1,
                                  v59,
                                  (struct _USER_CACHE_ENTRY *)v29,
                                  v97,
                                  0,
                                  0,
                                  0);
            if ( !LogonCacheForUser )
            {
              v62 = *(_BYTE **)(v29 + 288);
              if ( v62 )
              {
                v63 = *(unsigned int *)(v29 + 280);
                if ( *(_DWORD *)(v29 + 280) )
                {
                  do
                  {
                    *v62++ = 0;
                    --v63;
                  }
                  while ( v63 );
                }
                ((void (__fastcall *)(_QWORD))g_pLsaFunctionTable->FreeLsaHeap)(*(_QWORD *)(v29 + 288));
              }
              *(_QWORD *)(v29 + 288) = v80[1];
              *(_DWORD *)(v29 + 280) = v80[0];
              v80[1] = 0;
              LogonCacheForUser = 0;
              LODWORD(v80[0]) = 0;
              UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v29);
              goto LABEL_170;
            }
            while ( 1 )
            {
              v61 = *(v16 - 1);
              v54 = v16--;
              v55 = v61 == 92;
              if ( v61 == 92 )
                break;
              if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
              {
                v55 = v61 == 92;
                break;
              }
            }
            v79 = "SaveCaches";
            LODWORD(v75) = 11028;
          }
          goto LABEL_166;
        }
        LogonCacheForUser = 0;
        UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v29);
      }
      else
      {
LABEL_169:
        LogonCacheForUser = 0;
      }
LABEL_170:
      if ( v83 )
        RtlReleaseResource(&g_PackageListLock);
      goto LABEL_172;
    }
LABEL_22:
    LogonCacheForUser = _AcquireLogonSession(1, p_LinkedLogonId, &v81);
    if ( LogonCacheForUser )
    {
      v6 = "";
      while ( 1 )
      {
        v14 = *(v6 - 1);
        v8 = v6--;
        v9 = v14 == 92;
        if ( v14 == 92 )
          break;
        if ( v6 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v9 = v14 == 92;
          break;
        }
      }
      v77 = "AcquireLogonSession";
      v76 = 10832;
      goto LABEL_10;
    }
    v12 = v81;
    p_LogonId = &a1->LogonId;
    goto LABEL_29;
  }
  v6 = "";
  while ( 1 )
  {
    v7 = *(v6 - 1);
    v8 = v6--;
    v9 = v7 == 92;
    if ( v7 == 92 )
      break;
    if ( v6 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
    {
      v9 = v7 == 92;
      break;
    }
  }
  v77 = "AcquireLogonSession for Primary";
  v76 = 10808;
LABEL_10:
  if ( v9 )
    v6 = v8;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCacheForUser, v6, v76, v77, &Class);
LABEL_173:
  ReleaseLogonSession(v81);
  if ( Handle )
    NtClose(Handle);
  FreeCloudAPCache(v1);
  FreeUserInfo(v2);
  v70 = Size[2];
  if ( Size[2] )
  {
    v71 = LODWORD(Size[1]);
    if ( LODWORD(Size[1]) )
    {
      do
      {
        *(_BYTE *)v70 = 0;
        v70 = (struct _CloudAPCache *)((char *)v70 + 1);
        --v71;
      }
      while ( v71 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  if ( !v94 )
  {
    v72 = (_BYTE *)v80[1];
    if ( v80[1] )
    {
      v73 = LODWORD(v80[0]);
      if ( LODWORD(v80[0]) )
      {
        do
        {
          *v72++ = 0;
          --v73;
        }
        while ( v73 );
      }
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    }
  }
  if ( Buf1[1] )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  return LogonCacheForUser;
}

```

## disassembly

```asm
0x180016a10  mov     rax, rsp
0x180016a13  push    rbp
0x180016a14  push    rdi
0x180016a15  lea     rbp, [rax-108h]
0x180016a1c  sub     rsp, 1F8h
0x180016a23  mov     [rax-18h], rbx
0x180016a27  xorps   xmm0, xmm0
0x180016a2a  xor     ebx, ebx
0x180016a2c  mov     [rax-20h], rsi
0x180016a30  mov     [rax-28h], r12
0x180016a34  xorps   xmm1, xmm1
0x180016a37  mov     [rax-30h], r13
0x180016a3b  mov     r12d, ebx
0x180016a3e  mov     [rax-38h], r14
0x180016a42  mov     r13d, ebx
0x180016a45  mov     [rax-40h], r15
0x180016a49  mov     r14, rcx
0x180016a4c  mov     eax, [rcx+10h]
0x180016a4f  lea     r15, [rcx+0Ch]
0x180016a53  or      eax, [r15]
0x180016a56  movups  [rbp+100h+var_130], xmm0
0x180016a5a  mov     [rbp+100h+arg_0], 0
0x180016a61  movups  [rbp+100h+var_120], xmm0
0x180016a65  mov     qword ptr [rbp+100h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180016a69  mov     [rbp+100h+Handle], rbx
0x180016a6d  mov     [rsp+200h+var_1A0], rbx
0x180016a72  mov     [rbp+100h+var_180], rbx
0x180016a76  mov     qword ptr [rsp+200h+Size], rbx
0x180016a7b  mov     [rbp+100h+arg_18], rbx
0x180016a82  movups  xmmword ptr [rbp+100h+Buf1], xmm0
0x180016a86  movups  xmmword ptr [rsp+200h+Size+8], xmm1
0x180016a8b  movups  xmmword ptr [rsp+200h+var_1B8+8], xmm0
0x180016a90  jz      loc_180016BC9
0x180016a96  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x180016a9d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x180016aa2  test    al, al
0x180016aa4  jz      loc_180016BCD
0x180016aaa  call    LUAIsShadowAdminEnabled
0x180016aaf  test    eax, eax
0x180016ab1  jz      loc_180016BCD
0x180016ab7  lea     r8, [rbp+100h+arg_8]; struct _LOGON_SESSION **
0x180016abe  mov     [rbp+100h+arg_8], rbx
0x180016ac5  mov     rdx, r15; struct _LUID *
0x180016ac8  mov     ecx, 1; int
0x180016acd  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x180016ad2  mov     edi, eax
0x180016ad4  test    eax, eax
0x180016ad6  jz      short loc_180016B42
0x180016ad8  lea     rbx, aOnecoreDsExtCl_6+27h; ""
0x180016adf  lea     rsi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180016ae6  nop     word ptr [rax+rax+00000000h]
0x180016af0  movzx   eax, byte ptr [rbx-1]
0x180016af4  mov     rcx, rbx
0x180016af7  dec     rbx
0x180016afa  cmp     al, 5Ch ; '\'
0x180016afc  jz      short loc_180016B05
0x180016afe  cmp     rbx, rsi
0x180016b01  ja      short loc_180016AF0
0x180016b03  cmp     al, 5Ch ; '\'
0x180016b05  lea     rax, Class
0x180016b0c  mov     [rsp+200h+var_1D0], rax
0x180016b11  lea     rax, aAcquirelogonse; "AcquireLogonSession for Primary"
0x180016b18  mov     [rsp+200h+var_1D8], rax
0x180016b1d  mov     dword ptr [rsp+200h+var_1E0], 2A38h
0x180016b25  cmovz   rbx, rcx
0x180016b29  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180016b30  mov     r9, rbx
0x180016b33  mov     r8d, edi
0x180016b36  xor     ecx, ecx
0x180016b38  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180016b3d  jmp     loc_180017679
0x180016b42  mov     rbx, [rbp+100h+arg_8]
0x180016b49  lea     r15, [r14+4]
0x180016b4d  lea     r9, [rsp+200h+var_1A0]; struct _LOGON_SESSION **
0x180016b52  mov     rcx, r15; struct _LUID *
0x180016b55  mov     r8, [rbx+40h]; struct _SCARD_PIN *
0x180016b59  mov     rdx, [rbx+38h]; struct _USER_CACHE_ENTRY *
0x180016b5d  call    ?CreateLogonSession@@YAJPEAU_LUID@@PEAU_USER_CACHE_ENTRY@@PEAU_SCARD_PIN@@PEAPEAU_LOGON_SESSION@@@Z; CreateLogonSession(_LUID *,_USER_CACHE_ENTRY *,_SCARD_PIN *,_LOGON_SESSION * *)
0x180016b62  mov     rcx, rbx; struct _LOGON_SESSION *
0x180016b65  mov     edi, eax
0x180016b67  call    ?ReleaseLogonSession@@YAXPEAU_LOGON_SESSION@@@Z; ReleaseLogonSession(_LOGON_SESSION *)
0x180016b6c  test    edi, edi
0x180016b6e  jz      short loc_180016BBA
0x180016b70  lea     rbx, aOnecoreDsExtCl_6+27h; ""
0x180016b77  lea     rsi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180016b7e  xchg    ax, ax
0x180016b80  movzx   eax, byte ptr [rbx-1]
0x180016b84  mov     rcx, rbx
0x180016b87  dec     rbx
0x180016b8a  cmp     al, 5Ch ; '\'
0x180016b8c  jz      short loc_180016B95
0x180016b8e  cmp     rbx, rsi
0x180016b91  ja      short loc_180016B80
0x180016b93  cmp     al, 5Ch ; '\'
0x180016b95  lea     rax, Class
0x180016b9c  mov     [rsp+200h+var_1D0], rax
0x180016ba1  lea     rax, aCreatelogonses; "CreateLogonSession"
0x180016ba8  mov     [rsp+200h+var_1D8], rax
0x180016bad  mov     dword ptr [rsp+200h+var_1E0], 2A44h
0x180016bb5  jmp     loc_180016B25
0x180016bba  mov     rdi, [rsp+200h+var_1A0]
0x180016bbf  test    rdi, rdi
0x180016bc2  jz      short loc_180016BCD
0x180016bc4  mov     r12, r15
0x180016bc7  jmp     short loc_180016C43
0x180016bc9  lea     r15, [rcx+4]
0x180016bcd  lea     r8, [rsp+200h+var_1A0]; struct _LOGON_SESSION **
0x180016bd2  mov     rdx, r15; struct _LUID *
0x180016bd5  mov     ecx, 1; int
0x180016bda  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x180016bdf  mov     edi, eax
0x180016be1  test    eax, eax
0x180016be3  jz      short loc_180016C3A
0x180016be5  lea     rbx, aOnecoreDsExtCl_6+27h; ""
0x180016bec  lea     rsi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180016bf3  nop     dword ptr [rax+00h]
0x180016bf7  nop     word ptr [rax+rax+00000000h]
0x180016c00  movzx   eax, byte ptr [rbx-1]
0x180016c04  mov     rcx, rbx
0x180016c07  dec     rbx
0x180016c0a  cmp     al, 5Ch ; '\'
0x180016c0c  jz      short loc_180016C15
0x180016c0e  cmp     rbx, rsi
0x180016c11  ja      short loc_180016C00
0x180016c13  cmp     al, 5Ch ; '\'
0x180016c15  lea     rax, Class
0x180016c1c  mov     [rsp+200h+var_1D0], rax
0x180016c21  lea     rax, aAcquirelogonse_0; "AcquireLogonSession"
0x180016c28  mov     [rsp+200h+var_1D8], rax
0x180016c2d  mov     dword ptr [rsp+200h+var_1E0], 2A50h
0x180016c35  jmp     loc_180016B25
0x180016c3a  mov     rdi, [rsp+200h+var_1A0]
0x180016c3f  lea     r12, [r14+4]
0x180016c43  mov     dl, 1; Wait
0x180016c45  lea     rcx, ?g_LogonSessionListLock@@3U_RTL_RESOURCE@@A; Resource
0x180016c4c  call    cs:__imp_RtlAcquireResourceShared
0x180016c52  mov     edi, [rdi+18h]
0x180016c55  lea     rcx, ?g_LogonSessionListLock@@3U_RTL_RESOURCE@@A; Resource
0x180016c5c  call    cs:__imp_RtlReleaseResource
0x180016c62  lea     rbx, aOnecoreDsExtCl_6+27h; ""
0x180016c69  lea     rsi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180016c70  lea     r13, Class
0x180016c77  test    edi, edi
0x180016c79  jz      loc_180016D70
0x180016c7f  xor     edx, edx; Val
0x180016c81  lea     rcx, [rbp+100h+var_110]; void *
0x180016c85  mov     r8d, 0C8h; Size
0x180016c8b  call    memset_0
0x180016c90  mov     rax, [r12]
0x180016c94  lea     rdx, [rbp+100h+arg_8]; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x180016c9b  lea     rcx, [rbp+100h+arg_10]; unsigned __int64 *
0x180016ca2  mov     [rbp+100h+var_110], rax
0x180016ca6  mov     [rbp+100h+var_C0], 400000h
0x180016cad  mov     [rbp+100h+arg_8], 0
0x180016cb8  mov     [rbp+100h+arg_10], 0
0x180016cc3  call    ?MakeKerberosCallbackSupplementalCredential@@YAJPEA_KPEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z; MakeKerberosCallbackSupplementalCredential(unsigned __int64 *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)
0x180016cc8  test    eax, eax
0x180016cca  jns     short loc_180016D18
0x180016ccc  mov     r9, rbx
0x180016ccf  nop
0x180016cd0  movzx   ecx, byte ptr [r9-1]
0x180016cd5  mov     rdx, r9
0x180016cd8  dec     r9
0x180016cdb  cmp     cl, 5Ch ; '\'
0x180016cde  jz      short loc_180016CE8
0x180016ce0  cmp     r9, rsi
0x180016ce3  ja      short loc_180016CD0
0x180016ce5  cmp     cl, 5Ch ; '\'
0x180016ce8  cmovz   r9, rdx
0x180016cec  mov     [rsp+200h+var_1D0], r13
0x180016cf1  lea     rcx, aMakekerberosca; "MakeKerberosCallbackSupplementalCredent"...
0x180016cf8  mov     r8d, eax
0x180016cfb  mov     [rsp+200h+var_1D8], rcx
0x180016d00  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180016d07  xor     ecx, ecx
0x180016d09  mov     dword ptr [rsp+200h+var_1E0], 2A60h
0x180016d11  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180016d16  jmp     short loc_180016D70
0x180016d18  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180016d1f  lea     rcx, [rbp+100h+var_110]
0x180016d23  mov     rdi, [rbp+100h+arg_8]
0x180016d2a  mov     rdx, rdi
0x180016d2d  mov     rax, [rax+120h]
0x180016d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d39  mov     rdx, [rbp+100h+arg_10]
0x180016d40  mov     rax, rdi
0x180016d43  test    rdx, rdx
0x180016d46  jz      short loc_180016D5D
0x180016d48  nop     dword ptr [rax+rax+00000000h]
0x180016d50  mov     byte ptr [rax], 0
0x180016d53  lea     rax, [rax+1]
0x180016d57  sub     rdx, 1
0x180016d5b  jnz     short loc_180016D50
0x180016d5d  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180016d64  mov     rcx, rdi
0x180016d67  mov     rax, [rax+30h]
0x180016d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d70  test    dword ptr [r14], 40000h
0x180016d77  jz      short loc_180016D80
0x180016d79  xor     edi, edi
0x180016d7b  jmp     loc_18001766D
0x180016d80  mov     r14, [rsp+200h+var_1A0]
0x180016d85  lea     rdx, [rbp+100h+var_180]; struct _ApPluginPkg **
0x180016d89  lea     rcx, [r14+24h]; struct _GUID *
0x180016d8d  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x180016d92  mov     edi, eax
0x180016d94  test    eax, eax
0x180016d96  jz      short loc_180016DEB
0x180016d98  nop     dword ptr [rax+rax+00000000h]
0x180016da0  movzx   eax, byte ptr [rbx-1]
0x180016da4  mov     rcx, rbx
0x180016da7  dec     rbx
0x180016daa  cmp     al, 5Ch ; '\'
0x180016dac  jz      short loc_180016DB5
0x180016dae  cmp     rbx, rsi
0x180016db1  ja      short loc_180016DA0
0x180016db3  cmp     al, 5Ch ; '\'
0x180016db5  mov     [rsp+200h+var_1D0], r13
0x180016dba  lea     rax, aRefpackage; "RefPackage"
0x180016dc1  mov     [rsp+200h+var_1D8], rax
0x180016dc6  mov     dword ptr [rsp+200h+var_1E0], 2A75h
0x180016dce  cmovz   rbx, rcx
0x180016dd2  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180016dd9  mov     r9, rbx
0x180016ddc  mov     r8d, edi
0x180016ddf  xor     ecx, ecx
0x180016de1  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180016de6  jmp     loc_180017659
0x180016deb  mov     rdi, [rbp+100h+var_180]
0x180016def  cmp     qword ptr [rdi+150h], 0
0x180016df7  jz      loc_180017657
0x180016dfd  cmp     qword ptr [rdi+0B8h], 0
0x180016e05  jz      loc_180017657
0x180016e0b  test    byte ptr [rdi+0A0h], 4
0x180016e12  jnz     loc_180017657
0x180016e18  mov     r14, [r14+38h]
0x180016e1c  xor     edx, edx; bool
0x180016e1e  mov     rcx, r14; struct _USER_CACHE_ENTRY *
0x180016e21  call    ?LockAndUnProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@_N@Z; LockAndUnProtectUserCacheEntry(_USER_CACHE_ENTRY *,bool)
0x180016e26  xorps   xmm0, xmm0
0x180016e29  xorps   xmm1, xmm1
0x180016e2c  movups  [rbp+100h+var_160], xmm0
0x180016e30  movups  [rbp+100h+var_140], xmm1
0x180016e34  test    r14, r14
0x180016e37  jz      loc_180017533
0x180016e3d  mov     rcx, [rbp+100h+Buf1+8]
0x180016e41  test    rcx, rcx
0x180016e44  jz      short loc_180016E56
0x180016e46  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180016e4d  mov     rax, [rax+30h]
0x180016e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e56  mov     rcx, qword ptr [rsp+200h+Size+10h]
0x180016e5b  test    rcx, rcx
0x180016e5e  jz      short loc_180016E70
0x180016e60  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180016e67  mov     rax, [rax+30h]
0x180016e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e70  xorps   xmm0, xmm0
0x180016e73  movups  xmmword ptr [rsp+200h+Size+8], xmm0
0x180016e78  cmp     qword ptr [r14+120h], 0
0x180016e80  jz      loc_180016F1F
0x180016e86  mov     r13d, [r14+118h]
0x180016e8d  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180016e94  mov     ecx, r13d
0x180016e97  mov     dword ptr [rbp+100h+arg_8], r13d
0x180016e9e  mov     rax, [rax+28h]
0x180016ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ea7  mov     [rbp+100h+var_178], rax
0x180016eab  mov     rdi, rax
0x180016eae  test    rax, rax
0x180016eb1  jnz     short loc_180016F0B
0x180016eb3  mov     edi, 0C0000017h
0x180016eb8  lea     r9, aOnecoreDsExtCl_7+28h; ""
0x180016ebf  lea     rax, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x180016ec6  nop     word ptr [rax+rax+00000000h]
0x180016ed0  movzx   ecx, byte ptr [r9-1]
0x180016ed5  mov     rdx, r9
0x180016ed8  dec     r9
0x180016edb  cmp     cl, 5Ch ; '\'
0x180016ede  jz      short loc_180016EE5
0x180016ee0  cmp     r9, rax
0x180016ee3  ja      short loc_180016ED0
0x180016ee5  mov     r15, [rbp+100h+var_178]
0x180016ee9  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x180016ef0  xor     r10d, r10d
0x180016ef3  cmp     cl, 5Ch ; '\'
0x180016ef6  mov     ecx, 34Fh
0x180016efb  cmovz   r9, rdx
0x180016eff  lea     rdx, Class
0x180016f06  jmp     loc_180017586
0x180016f0b  mov     rdx, [r14+120h]; Src
0x180016f12  mov     r8, r13; Size
0x180016f15  mov     rcx, rax; void *
0x180016f18  call    memcpy_0
0x180016f1d  jmp     short loc_180016F30
0x180016f1f  mov     rdi, qword ptr [rbp+100h+var_160+8]
0x180016f23  mov     eax, dword ptr [rbp+100h+var_160]
0x180016f26  mov     [rbp+100h+var_178], rdi
0x180016f2a  mov     dword ptr [rbp+100h+arg_8], eax
0x180016f30  cmp     qword ptr [r14+130h], 0
  ... truncated ...
```
