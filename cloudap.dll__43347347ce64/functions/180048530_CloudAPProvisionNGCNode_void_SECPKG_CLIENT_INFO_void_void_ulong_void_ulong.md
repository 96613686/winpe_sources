# CloudAPProvisionNGCNode(void * *,_SECPKG_CLIENT_INFO *,void *,void *,ulong,void * *,ulong *)

- ea: `0x180048530`
- end: `0x180048d5d`
- name: `?CloudAPProvisionNGCNode@@YAJPEAPEAXPEAU_SECPKG_CLIENT_INFO@@PEAX2K0PEAK@Z`
- size: `2093`
- prototype: `__int64 __fastcall(void **, struct _SECPKG_CLIENT_INFO *, void *, void *, unsigned int, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007ef0`
- `0x180007fc0`
- `0x180009bf0`
- `0x18000a600`
- `0x18000e7e0`
- `0x18000e900`
- `0x18000ed04`
- `0x18000ee60`
- `0x18000fb70`
- `0x18000fd50`
- `0x180010320`
- `0x18002223c`
- `0x180024bb0`
- `0x180026ec0`
- `0x180034e20`
- `0x180048530`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048794`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004878a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004878a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800487ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048c87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048ca6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048cb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048cc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800487ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048c87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048ca6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048cb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048cc4`
- `cryptngc!NgcEnumContainers` at `0x180048803`
- `cryptngc!NgcEnumContainers` at `0x180048803`
- `cryptngc!NgcGetLogonDecryptionKeyName` at `0x1800488b2`
- `cryptngc!NgcGetLogonDecryptionKeyName` at `0x1800488b2`
- `cryptngc!NgcPackAuthBuffer` at `0x180048939`
- `cryptngc!NgcPackAuthBuffer` at `0x180048939`
- `cryptngc!NgcFreeEnumState` at `0x180048c96`
- `cryptngc!NgcFreeEnumState` at `0x180048c96`

## string_xrefs

- `0x1800485dc`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004863f`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800486d1`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048744`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800487a9`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048825`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048861`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800488bf`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048946`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800489a1`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800489eb`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048a40`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048ad6`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048b47`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048b9b`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048bd1`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048c20`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048bf1`: `No Token Blob with logon session`
- `0x1800487c4`: `ConvertSidToStringSid`
- `0x180048a2a`: `CacheData`
- `0x180048b82`: `CacheData`
- `0x180048a67`: `GetLogonCacheForUser`
- `0x180048af1`: `UpdatePluginOpaqueCacheBlob`
- `0x180048bb6`: `SaveLogonCacheForUser`
- `0x180048a06`: `GetUnlockBufferForDPAPICache`
- `0x180048b62`: `AddCloudAPCacheNode`

## pseudocode

```c
__int64 __fastcall CloudAPProvisionNGCNode(
        void **a1,
        struct _SECPKG_CLIENT_INFO *a2,
        void *a3,
        void *a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7)
{
  struct _LOGON_SESSION *v7; // r14
  struct _ApPluginPkg *v8; // rsi
  struct _CloudAPCache *v9; // r13
  unsigned int LogonCredsFromIdentityEx2; // ebx
  const char *v11; // rax
  const char *v12; // rax
  __int64 v13; // rdi
  const char *v14; // r9
  const char *v15; // r9
  void *v16; // rcx
  signed int LastError; // eax
  const char *v18; // r9
  HLOCAL v19; // rdx
  int v20; // eax
  const char *v21; // r9
  unsigned int v22; // eax
  const char *v23; // r9
  int LogonDecryptionKeyName; // eax
  unsigned int v25; // eax
  const char *v26; // r9
  int v27; // eax
  unsigned int v28; // eax
  const char *v29; // r9
  const char *v30; // r9
  const char *v31; // r9
  const char *v32; // rax
  const char *v33; // r9
  const char *v34; // r9
  const char *v35; // r9
  const char *v36; // r9
  const char *v37; // rax
  struct _tagCacheDataFuncs *v39; // [rsp+20h] [rbp-E0h]
  struct _tagCacheDataFuncs *v40; // [rsp+20h] [rbp-E0h]
  struct _tagCacheDataFuncs *v41; // [rsp+20h] [rbp-E0h]
  struct _tagCacheDataFuncs *v42; // [rsp+20h] [rbp-E0h]
  unsigned int AuthIdentityLength; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  int v46; // [rsp+68h] [rbp-98h] BYREF
  struct _LOGON_SESSION *v47; // [rsp+70h] [rbp-90h] BYREF
  struct _ApPluginPkg *v48; // [rsp+78h] [rbp-88h] BYREF
  struct _CloudAPCache *v49; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v50; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL v51; // [rsp+90h] [rbp-70h] BYREF
  void *v52; // [rsp+98h] [rbp-68h] BYREF
  __int64 v53; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v54; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 *v55[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v56; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v57; // [rsp+D0h] [rbp-30h]
  __int128 v58; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v59; // [rsp+E8h] [rbp-18h]

  v57 = 0;
  v7 = 0;
  v8 = 0;
  AuthIdentityLength = 0;
  v9 = 0;
  v58 = 0;
  v46 = 0;
  *a6 = 0;
  v59 = 0;
  v47 = 0;
  v48 = 0;
  *a7 = 0;
  v49 = 0;
  v53 = 0;
  hMem = 0;
  StringSid = 0;
  v50 = 0;
  v51 = 0;
  v56 = 0;
  v54 = 0;
  *(_OWORD *)v55 = 0;
  v52 = 0;
  if ( a5 >= 4 && a3 )
  {
    LogonCredsFromIdentityEx2 = _AcquireLogonSession(1, &a2->LogonId, &v47);
    if ( LogonCredsFromIdentityEx2 )
    {
      v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCredsFromIdentityEx2, v11, 3168, "AcquireLogonSession", &Class);
      v7 = v47;
      goto LABEL_55;
    }
    v7 = v47;
    LogonCredsFromIdentityEx2 = RefPackage((struct _GUID *)((char *)v47 + 36), &v48);
    if ( LogonCredsFromIdentityEx2 )
    {
      v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCredsFromIdentityEx2, v12, 3173, "RefPackage", &Class);
      v8 = v48;
      goto LABEL_55;
    }
    v13 = *((_QWORD *)v7 + 7);
    LockAndUnProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v13, 1);
    v8 = v48;
    if ( !*(_DWORD *)(v13 + 280) || !*(_QWORD *)(v13 + 288) )
    {
      LogonCredsFromIdentityEx2 = -1073741729;
      v36 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225567LL, v36, 3189, "No Token Blob with logon session", &Class);
      goto LABEL_53;
    }
    if ( (*((_DWORD *)v48 + 40) & 1) != 0 )
    {
      if ( !g_bAutoProvisionTBAL )
      {
        LogonCredsFromIdentityEx2 = -1073741790;
        v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          3221225506LL,
          v14,
          3201,
          "Provisioning of NGC only allowed for AAD or MSA for certain SKUs",
          &Class);
LABEL_53:
        UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v13);
        goto LABEL_55;
      }
      LogonCredsFromIdentityEx2 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, void **, int *))g_pLsaIdProvHostFunctionTable
                                   + 4))(
                                    *((_QWORD *)v48 + 2),
                                    *(_QWORD *)(v13 + 96),
                                    0,
                                    14,
                                    &v52,
                                    &v46);
      if ( LogonCredsFromIdentityEx2 )
      {
        v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        LODWORD(v39) = 3211;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCredsFromIdentityEx2, v15, v39, "LookUpUserInfo", &Class);
        goto LABEL_53;
      }
      v16 = v52;
    }
    else
    {
      v16 = *(void **)(v13 + 240);
    }
    if ( ConvertSidToStringSidW(v16, &StringSid) )
    {
      v19 = hMem;
      while ( 1 )
      {
        if ( v19 )
        {
          LocalFree(v19);
          hMem = 0;
        }
        v20 = NgcEnumContainers(StringSid, &hMem, &v53);
        v19 = hMem;
        if ( v20 == -2146893782 )
        {
LABEL_26:
          if ( hMem )
          {
            LogonDecryptionKeyName = NgcGetLogonDecryptionKeyName(
                                       StringSid,
                                       *((_QWORD *)hMem + 4),
                                       *((_QWORD *)hMem + 5),
                                       &v50);
            if ( LogonDecryptionKeyName >= 0 )
            {
              v27 = NgcPackAuthBuffer(L"FakeUser", L"FakeDomain", v50, 0, v50, 0, 1, &v51, &AuthIdentityLength);
              if ( v27 >= 0 )
              {
                LogonCredsFromIdentityEx2 = GetLogonCredsFromIdentityEx2(
                                              (char *)v51,
                                              AuthIdentityLength,
                                              (struct _DECRYPTED_AUTH_DATA *)&v56,
                                              &v54);
                if ( LogonCredsFromIdentityEx2 )
                {
                  v30 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                  LODWORD(v40) = 3298;
                  WPPTraceLogA(
                    0,
                    "0x%08x %s:%u : %s:%ws",
                    LogonCredsFromIdentityEx2,
                    v30,
                    v40,
                    "GetLogonCredsFromIdentityEx2",
                    &Class);
                }
                else
                {
                  LogonCredsFromIdentityEx2 = GetUnlockBufferForDPAPICache(
                                                v8,
                                                (struct _DECRYPTED_AUTH_DATA *)&v56,
                                                (struct _DPAPI_DECODED_AUTH_DATA *)v55);
                  if ( LogonCredsFromIdentityEx2 )
                  {
                    v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                    LODWORD(v40) = 3305;
                    WPPTraceLogA(
                      0,
                      "0x%08x %s:%u : %s:%ws",
                      LogonCredsFromIdentityEx2,
                      v31,
                      v40,
                      "GetUnlockBufferForDPAPICache",
                      &Class);
                  }
                  else
                  {
                    LogonCredsFromIdentityEx2 = _GetLogonCacheForUser(
                                                  *((const unsigned __int16 **)v8 + 43),
                                                  (const unsigned __int16 *)(v13 + 104),
                                                  L"CacheData",
                                                  &v49);
                    if ( LogonCredsFromIdentityEx2 )
                    {
                      v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                      LODWORD(v40) = 3311;
                      WPPTraceLogA(
                        0,
                        "0x%08x %s:%u : %s:%ws",
                        LogonCredsFromIdentityEx2,
                        v32,
                        v40,
                        "GetLogonCacheForUser",
                        &Class);
                      v9 = v49;
                    }
                    else
                    {
                      v9 = v49;
                      *((_QWORD *)&v58 + 1) = *((_QWORD *)v8 + 29);
                      *(_QWORD *)&v59 = *((_QWORD *)v8 + 30);
                      *((_QWORD *)&v59 + 1) = SecureFreeCacheData;
                      LogonCredsFromIdentityEx2 = UpdatePluginOpaqueCacheBlob(
                                                    v49,
                                                    (struct _tagCacheNodeIdentifier *)(v13 + 296),
                                                    *(struct _CREDENTIAL_KEY **)(v13 + 264),
                                                    (struct _AP_BLOB *)(v13 + 280),
                                                    (struct _tagCacheDataFuncs *)&v58);
                      if ( LogonCredsFromIdentityEx2 )
                      {
                        v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                        LODWORD(v41) = 3326;
                        WPPTraceLogA(
                          0,
                          "0x%08x %s:%u : %s:%ws",
                          LogonCredsFromIdentityEx2,
                          v33,
                          v41,
                          "UpdatePluginOpaqueCacheBlob",
                          &Class);
                      }
                      else
                      {
                        LogonCredsFromIdentityEx2 = AddCloudAPCacheNode(
                                                      v9,
                                                      1u,
                                                      (unsigned int)v55[0],
                                                      v55[1],
                                                      HIDWORD(v55[0]),
                                                      *(struct _CREDENTIAL_KEY **)(v13 + 264),
                                                      (struct _AP_BLOB *)(v13 + 280),
                                                      0,
                                                      0);
                        if ( LogonCredsFromIdentityEx2 )
                        {
                          v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                          LODWORD(v42) = 3346;
                          WPPTraceLogA(
                            0,
                            "0x%08x %s:%u : %s:%ws",
                            LogonCredsFromIdentityEx2,
                            v34,
                            v42,
                            "AddCloudAPCacheNode",
                            &Class);
                        }
                        else
                        {
                          LogonCredsFromIdentityEx2 = _SaveLogonCacheForUser(
                                                        *((const unsigned __int16 **)v8 + 43),
                                                        (const unsigned __int16 *)(v13 + 104),
                                                        L"CacheData",
                                                        v9);
                          if ( LogonCredsFromIdentityEx2 )
                          {
                            v35 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                            LODWORD(v42) = 3353;
                            WPPTraceLogA(
                              0,
                              "0x%08x %s:%u : %s:%ws",
                              LogonCredsFromIdentityEx2,
                              v35,
                              v42,
                              "SaveLogonCacheForUser",
                              &Class);
                          }
                          else
                          {
                            LogonCredsFromIdentityEx2 = 0;
                          }
                        }
                      }
                    }
                  }
                }
              }
              else
              {
                LogonCredsFromIdentityEx2 = (unsigned __int16)v27;
                v28 = (unsigned __int16)v27 | 0xC0070000;
                if ( LogonCredsFromIdentityEx2 )
                  LogonCredsFromIdentityEx2 = v28;
                v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                LODWORD(v40) = 3290;
                WPPTraceLogA(
                  0,
                  "0x%08x %s:%u : %s:%ws",
                  LogonCredsFromIdentityEx2,
                  v29,
                  v40,
                  "NgcPackAuthBuffer",
                  &Class);
              }
            }
            else
            {
              LogonCredsFromIdentityEx2 = (unsigned __int16)LogonDecryptionKeyName;
              v25 = (unsigned __int16)LogonDecryptionKeyName | 0xC0070000;
              if ( LogonCredsFromIdentityEx2 )
                LogonCredsFromIdentityEx2 = v25;
              v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
              LODWORD(v39) = 3274;
              WPPTraceLogA(
                0,
                "0x%08x %s:%u : %s:%ws",
                LogonCredsFromIdentityEx2,
                v26,
                v39,
                "NgcGetLogonDecryptionKeyName",
                &Class);
            }
          }
          else
          {
            LogonCredsFromIdentityEx2 = -1073740759;
            v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            LODWORD(v39) = 3263;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221226537LL, v21, v39, "No logon containers found", &Class);
          }
          goto LABEL_53;
        }
        if ( v20 < 0 )
          break;
        if ( (*((_DWORD *)hMem + 14) & 1) != 0 )
          goto LABEL_26;
      }
      LogonCredsFromIdentityEx2 = (unsigned __int16)v20;
      v22 = (unsigned __int16)v20 | 0xC0070000;
      if ( LogonCredsFromIdentityEx2 )
        LogonCredsFromIdentityEx2 = v22;
      v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(v39) = 3248;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCredsFromIdentityEx2, v23, v39, "NgcEnumContainers", &Class);
    }
    else
    {
      LastError = GetLastError();
      LogonCredsFromIdentityEx2 = LastError;
      if ( LastError > 0 )
        LogonCredsFromIdentityEx2 = (unsigned __int16)LastError | 0xC0070000;
      v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(v39) = 3227;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCredsFromIdentityEx2, v18, v39, "ConvertSidToStringSid", &Class);
    }
    goto LABEL_53;
  }
  LogonCredsFromIdentityEx2 = -1073741811;
  v37 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v37, 3161, "Invalid Arg(s)", &Class);
LABEL_55:
  DerefPackage(v8);
  ReleaseLogonSession(v7);
  FreeCloudAPCache(v9);
  if ( hMem )
    LocalFree(hMem);
  if ( v53 )
    NgcFreeEnumState();
  if ( StringSid )
    LocalFree(StringSid);
  if ( v50 )
    LocalFree(v50);
  if ( v51 )
    LocalFree(v51);
  if ( v55[1] )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v57 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( *((_QWORD *)&v56 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v54 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v52 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  return LogonCredsFromIdentityEx2;
}

```

## disassembly

```asm
0x180048530  push    rbp
0x180048532  push    rbx
0x180048533  push    rsi
0x180048534  push    rdi
0x180048535  push    r12
0x180048537  push    r13
0x180048539  push    r14
0x18004853b  push    r15
0x18004853d  lea     rbp, [rsp-8]
0x180048542  sub     rsp, 108h
0x180048549  xor     r15d, r15d
0x18004854c  xor     eax, eax
0x18004854e  cmp     [rbp+40h+arg_20], 4
0x180048552  xorps   xmm0, xmm0
0x180048555  mov     [rbp+40h+var_70], rax
0x180048559  mov     r14d, r15d
0x18004855c  mov     rax, [rbp+40h+arg_28]
0x180048560  mov     esi, r15d
0x180048563  mov     [rsp+140h+AuthIdentityLength], r15d
0x180048568  mov     r13d, r15d
0x18004856b  movups  [rbp+40h+var_68], xmm0
0x18004856f  mov     [rsp+140h+var_D8], r15d
0x180048574  mov     [rax], r15
0x180048577  mov     rax, [rbp+40h+arg_30]
0x18004857e  movups  [rbp+40h+var_58], xmm0
0x180048582  mov     [rsp+140h+var_D0], r15
0x180048587  mov     [rsp+140h+var_C8], r15
0x18004858c  mov     [rax], r15d
0x18004858f  mov     [rbp+40h+var_C0], r15
0x180048593  mov     [rbp+40h+var_A0], r15
0x180048597  mov     [rsp+140h+hMem], r15
0x18004859c  mov     [rsp+140h+StringSid], r15
0x1800485a1  mov     [rbp+40h+var_B8], r15
0x1800485a5  mov     [rbp+40h+var_B0], r15
0x1800485a9  movups  [rbp+40h+var_80], xmm0
0x1800485ad  mov     [rbp+40h+var_98], r15
0x1800485b1  movups  xmmword ptr [rbp+40h+var_90], xmm0
0x1800485b5  mov     [rbp+40h+var_A8], r15
0x1800485b9  jb      loc_180048C20
0x1800485bf  test    r8, r8
0x1800485c2  jz      loc_180048C20
0x1800485c8  lea     r8, [rsp+140h+var_D0]; struct _LOGON_SESSION **
0x1800485cd  lea     ecx, [r15+1]; int
0x1800485d1  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x1800485d6  mov     ebx, eax
0x1800485d8  test    eax, eax
0x1800485da  jz      short loc_180048626
0x1800485dc  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800485e3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800485e8  mov     r9, rax
0x1800485eb  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800485f2  lea     rax, Class
0x1800485f9  mov     r8d, ebx
0x1800485fc  mov     [rsp+140h+var_110], rax
0x180048601  xor     ecx, ecx
0x180048603  lea     rax, aAcquirelogonse_0; "AcquireLogonSession"
0x18004860a  mov     [rsp+140h+Source], rax
0x18004860f  mov     dword ptr [rsp+140h+var_120], 0C60h
0x180048617  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004861c  mov     r14, [rsp+140h+var_D0]
0x180048621  jmp     loc_180048C65
0x180048626  mov     r14, [rsp+140h+var_D0]
0x18004862b  lea     rdx, [rsp+140h+var_C8]; struct _ApPluginPkg **
0x180048630  lea     rcx, [r14+24h]; struct _GUID *
0x180048634  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x180048639  mov     ebx, eax
0x18004863b  test    eax, eax
0x18004863d  jz      short loc_180048689
0x18004863f  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180048646  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004864b  mov     r9, rax
0x18004864e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180048655  lea     rax, Class
0x18004865c  mov     r8d, ebx
0x18004865f  mov     [rsp+140h+var_110], rax
0x180048664  xor     ecx, ecx
0x180048666  lea     rax, aRefpackage; "RefPackage"
0x18004866d  mov     [rsp+140h+Source], rax
0x180048672  mov     dword ptr [rsp+140h+var_120], 0C65h
0x18004867a  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004867f  mov     rsi, [rsp+140h+var_C8]
0x180048684  jmp     loc_180048C65
0x180048689  mov     rdi, [r14+38h]
0x18004868d  mov     dl, 1; bool
0x18004868f  mov     rcx, rdi; struct _USER_CACHE_ENTRY *
0x180048692  call    ?LockAndUnProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@_N@Z; LockAndUnProtectUserCacheEntry(_USER_CACHE_ENTRY *,bool)
0x180048697  mov     rsi, [rsp+140h+var_C8]
0x18004869c  lea     r12, [rdi+118h]
0x1800486a3  cmp     [r12], r15d
0x1800486a7  jz      loc_180048BD1
0x1800486ad  cmp     [rdi+120h], r15
0x1800486b4  jz      loc_180048BD1
0x1800486ba  mov     eax, [rsi+0A0h]
0x1800486c0  test    al, 1
0x1800486c2  jz      loc_18004877E
0x1800486c8  cmp     cs:?g_bAutoProvisionTBAL@@3EA, r15b; uchar g_bAutoProvisionTBAL
0x1800486cf  jnz     short loc_18004870A
0x1800486d1  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800486d8  mov     ebx, 0C0000022h
0x1800486dd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800486e2  mov     r9, rax
0x1800486e5  lea     rax, Class
0x1800486ec  mov     [rsp+140h+var_110], rax
0x1800486f1  lea     rax, aProvisioningOf; "Provisioning of NGC only allowed for AA"...
0x1800486f8  mov     [rsp+140h+Source], rax
0x1800486fd  mov     dword ptr [rsp+140h+var_120], 0C81h
0x180048705  jmp     loc_180048C05
0x18004870a  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x180048711  lea     rcx, [rsp+140h+var_D8]
0x180048716  mov     rdx, [rdi+60h]
0x18004871a  mov     r9d, 0Eh
0x180048720  mov     [rsp+140h+Source], rcx
0x180048725  xor     r8d, r8d
0x180048728  lea     rcx, [rbp+40h+var_A8]
0x18004872c  mov     rax, [rax+20h]
0x180048730  mov     [rsp+140h+var_120], rcx
0x180048735  mov     rcx, [rsi+10h]
0x180048739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004873e  mov     ebx, eax
0x180048740  test    eax, eax
0x180048742  jz      short loc_180048778
0x180048744  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004874b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180048750  mov     r9, rax
0x180048753  lea     rax, Class
0x18004875a  mov     [rsp+140h+var_110], rax
0x18004875f  lea     rax, aLookupuserinfo; "LookUpUserInfo"
0x180048766  mov     [rsp+140h+Source], rax
0x18004876b  mov     dword ptr [rsp+140h+var_120], 0C8Bh
0x180048773  jmp     loc_180048C05
0x180048778  mov     rcx, [rbp+40h+var_A8]
0x18004877c  jmp     short loc_180048785
0x18004877e  mov     rcx, [rdi+0F0h]; Sid
0x180048785  lea     rdx, [rsp+140h+StringSid]; StringSid
0x18004878a  call    cs:__imp_ConvertSidToStringSidW
0x180048790  test    eax, eax
0x180048792  jnz     short loc_1800487DD
0x180048794  call    cs:__imp_GetLastError
0x18004879a  mov     ebx, eax
0x18004879c  test    eax, eax
0x18004879e  jle     short loc_1800487A9
0x1800487a0  movzx   ebx, ax
0x1800487a3  or      ebx, 0C0070000h
0x1800487a9  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800487b0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800487b5  mov     r9, rax
0x1800487b8  lea     rax, Class
0x1800487bf  mov     [rsp+140h+var_110], rax
0x1800487c4  lea     rax, aConvertsidtost; "ConvertSidToStringSid"
0x1800487cb  mov     [rsp+140h+Source], rax
0x1800487d0  mov     dword ptr [rsp+140h+var_120], 0C9Bh
0x1800487d8  jmp     loc_180048C05
0x1800487dd  mov     rdx, [rsp+140h+hMem]
0x1800487e2  test    rdx, rdx
0x1800487e5  jz      short loc_1800487F5
0x1800487e7  mov     rcx, rdx; hMem
0x1800487ea  call    cs:__imp_LocalFree
0x1800487f0  mov     [rsp+140h+hMem], r15
0x1800487f5  mov     rcx, [rsp+140h+StringSid]
0x1800487fa  lea     r8, [rbp+40h+var_A0]
0x1800487fe  lea     rdx, [rsp+140h+hMem]
0x180048803  call    cs:__imp_NgcEnumContainers
0x180048809  mov     rdx, [rsp+140h+hMem]
0x18004880e  cmp     eax, 8009002Ah
0x180048813  jz      short loc_180048820
0x180048815  test    eax, eax
0x180048817  js      short loc_18004885E
0x180048819  mov     eax, [rdx+38h]
0x18004881c  test    al, 1
0x18004881e  jz      short loc_1800487E2
0x180048820  test    rdx, rdx
0x180048823  jnz     short loc_1800488A1
0x180048825  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004882c  mov     ebx, 0C0000429h
0x180048831  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180048836  mov     r9, rax
0x180048839  lea     rax, Class
0x180048840  mov     [rsp+140h+var_110], rax
0x180048845  lea     rax, aNoLogonContain; "No logon containers found"
0x18004884c  mov     [rsp+140h+Source], rax
0x180048851  mov     dword ptr [rsp+140h+var_120], 0CBFh
0x180048859  jmp     loc_180048C05
0x18004885e  movzx   ebx, ax
0x180048861  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180048868  mov     eax, ebx
0x18004886a  or      eax, 0C0070000h
0x18004886f  test    ebx, ebx
0x180048871  cmovnz  ebx, eax
0x180048874  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180048879  mov     r9, rax
0x18004887c  lea     rax, Class
0x180048883  mov     [rsp+140h+var_110], rax
0x180048888  lea     rax, aNgcenumcontain_0; "NgcEnumContainers"
0x18004888f  mov     [rsp+140h+Source], rax
0x180048894  mov     dword ptr [rsp+140h+var_120], 0CB0h
0x18004889c  jmp     loc_180048C05
0x1800488a1  mov     r8, [rdx+28h]
0x1800488a5  lea     r9, [rbp+40h+var_B8]
0x1800488a9  mov     rdx, [rdx+20h]
0x1800488ad  mov     rcx, [rsp+140h+StringSid]
0x1800488b2  call    cs:__imp_NgcGetLogonDecryptionKeyName
0x1800488b8  test    eax, eax
0x1800488ba  jns     short loc_1800488FF
0x1800488bc  movzx   ebx, ax
0x1800488bf  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800488c6  mov     eax, ebx
0x1800488c8  or      eax, 0C0070000h
0x1800488cd  test    ebx, ebx
0x1800488cf  cmovnz  ebx, eax
0x1800488d2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800488d7  mov     r9, rax
0x1800488da  lea     rax, Class
0x1800488e1  mov     [rsp+140h+var_110], rax
0x1800488e6  lea     rax, aNgcgetlogondec_1; "NgcGetLogonDecryptionKeyName"
0x1800488ed  mov     [rsp+140h+Source], rax
0x1800488f2  mov     dword ptr [rsp+140h+var_120], 0CCAh
0x1800488fa  jmp     loc_180048C05
0x1800488ff  mov     r8, [rbp+40h+var_B8]
0x180048903  lea     rax, [rsp+140h+AuthIdentityLength]
0x180048908  mov     [rsp+140h+var_100], rax
0x18004890d  lea     rdx, aFakedomain; "FakeDomain"
0x180048914  lea     rax, [rbp+40h+var_B0]
0x180048918  xor     r9d, r9d
0x18004891b  mov     [rsp+140h+var_108], rax
0x180048920  lea     rcx, aFakeuser; "FakeUser"
0x180048927  mov     dword ptr [rsp+140h+var_110], 1
0x18004892f  mov     [rsp+140h+Source], r15
0x180048934  mov     [rsp+140h+var_120], r8
0x180048939  call    cs:__imp_NgcPackAuthBuffer
0x18004893f  test    eax, eax
0x180048941  jns     short loc_180048986
0x180048943  movzx   ebx, ax
0x180048946  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004894d  mov     eax, ebx
0x18004894f  or      eax, 0C0070000h
0x180048954  test    ebx, ebx
0x180048956  cmovnz  ebx, eax
0x180048959  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004895e  mov     r9, rax
0x180048961  lea     rax, Class
0x180048968  mov     [rsp+140h+var_110], rax
0x18004896d  lea     rax, aNgcpackauthbuf_0; "NgcPackAuthBuffer"
0x180048974  mov     [rsp+140h+Source], rax
0x180048979  mov     dword ptr [rsp+140h+var_120], 0CDAh
0x180048981  jmp     loc_180048C05
0x180048986  mov     edx, [rsp+140h+AuthIdentityLength]; AuthIdentityLength
0x18004898a  lea     r9, [rbp+40h+var_98]; unsigned __int16 **
0x18004898e  mov     rcx, [rbp+40h+var_B0]; AuthIdentityByteArray
0x180048992  lea     r8, [rbp+40h+var_80]; struct _DECRYPTED_AUTH_DATA *
0x180048996  call    ?GetLogonCredsFromIdentityEx2@@YAJPEAXKPEAU_DECRYPTED_AUTH_DATA@@PEAPEAG@Z; GetLogonCredsFromIdentityEx2(void *,ulong,_DECRYPTED_AUTH_DATA *,ushort * *)
0x18004899b  mov     ebx, eax
0x18004899d  test    eax, eax
0x18004899f  jz      short loc_1800489D5
0x1800489a1  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800489a8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800489ad  mov     r9, rax
0x1800489b0  lea     rax, Class
0x1800489b7  mov     [rsp+140h+var_110], rax
0x1800489bc  lea     rax, aGetlogoncredsf_0; "GetLogonCredsFromIdentityEx2"
0x1800489c3  mov     [rsp+140h+Source], rax
0x1800489c8  mov     dword ptr [rsp+140h+var_120], 0CE2h
0x1800489d0  jmp     loc_180048C05
0x1800489d5  lea     r8, [rbp+40h+var_90]; struct _DPAPI_DECODED_AUTH_DATA *
0x1800489d9  mov     rcx, rsi; struct _ApPluginPkg *
0x1800489dc  lea     rdx, [rbp+40h+var_80]; struct _DECRYPTED_AUTH_DATA *
0x1800489e0  call    ?GetUnlockBufferForDPAPICache@@YAJPEAU_ApPluginPkg@@PEAU_DECRYPTED_AUTH_DATA@@PEAU_DPAPI_DECODED_AUTH_DATA@@@Z; GetUnlockBufferForDPAPICache(_ApPluginPkg *,_DECRYPTED_AUTH_DATA *,_DPAPI_DECODED_AUTH_DATA *)
0x1800489e5  mov     ebx, eax
0x1800489e7  test    eax, eax
0x1800489e9  jz      short loc_180048A1F
0x1800489eb  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800489f2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800489f7  mov     r9, rax
0x1800489fa  lea     rax, Class
0x180048a01  mov     [rsp+140h+var_110], rax
0x180048a06  lea     rax, aGetunlockbuffe; "GetUnlockBufferForDPAPICache"
0x180048a0d  mov     [rsp+140h+Source], rax
0x180048a12  mov     dword ptr [rsp+140h+var_120], 0CE9h
0x180048a1a  jmp     loc_180048C05
0x180048a1f  mov     rcx, [rsi+158h]; unsigned __int16 *
0x180048a26  lea     r9, [rbp+40h+var_C0]; struct _CloudAPCache **
0x180048a2a  lea     r8, aCachedata; "CacheData"
0x180048a31  lea     rdx, [rdi+68h]; unsigned __int16 *
0x180048a35  call    ?_GetLogonCacheForUser@@YAJPEBG00PEAPEAU_CloudAPCache@@@Z; _GetLogonCacheForUser(ushort const *,ushort const *,ushort const *,_CloudAPCache * *)
0x180048a3a  mov     ebx, eax
0x180048a3c  test    eax, eax
0x180048a3e  jz      short loc_180048A89
0x180048a40  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180048a47  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180048a4c  mov     r9, rax
0x180048a4f  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180048a56  lea     rax, Class
0x180048a5d  mov     r8d, ebx
0x180048a60  mov     [rsp+140h+var_110], rax
0x180048a65  xor     ecx, ecx
0x180048a67  lea     rax, aGetlogoncachef; "GetLogonCacheForUser"
0x180048a6e  mov     [rsp+140h+Source], rax
0x180048a73  mov     dword ptr [rsp+140h+var_120], 0CEFh
0x180048a7b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180048a80  mov     r13, [rbp+40h+var_C0]
0x180048a84  jmp     loc_180048C16
  ... truncated ...
```
