# SpOnProfileLoaded(void *,void *,uchar)

- ea: `0x18000f210`
- end: `0x18000f6f4`
- name: `?SpOnProfileLoaded@@YAJPEAX0E@Z`
- size: `1252`
- prototype: `int(void *, void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007ef0`
- `0x180007fc0`
- `0x180009bf0`
- `0x18000a600`
- `0x18000ed04`
- `0x18000f210`
- `0x18000fb70`
- `0x18000fd50`
- `0x180010320`
- `0x1800103c0`
- `0x180010460`
- `0x1800104c0`
- `0x180011294`
- `0x180011424`
- `0x18003ff84`
- `0x180042410`
- `0x18004d79c`
- `0x180081010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18000f642`
- `ntdll!RtlReleaseResource` at `0x18000f6bd`
- `ntdll!RtlReleaseResource` at `0x18000f642`
- `ntdll!RtlReleaseResource` at `0x18000f6bd`
- `ntdll!NtQueryInformationToken` at `0x18000f3cd`
- `ntdll!NtQueryInformationToken` at `0x18000f3cd`
- `ntdll!RtlAcquireResourceShared` at `0x18000f2cf`
- `ntdll!RtlAcquireResourceShared` at `0x18000f2cf`
- `ntdll!RtlEnterCriticalSection` at `0x18000f49f`
- `ntdll!RtlEnterCriticalSection` at `0x18000f49f`
- `ntdll!RtlLeaveCriticalSection` at `0x18000f4b9`
- `ntdll!RtlLeaveCriticalSection` at `0x18000f4b9`

## string_xrefs

- `0x18000f292`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000f330`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000f37a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000f3d9`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000f42c`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000f4d0`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000f654`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000f50a`: `CacheData`
- `0x18000f5df`: `CacheData`
- `0x18000f3f4`: `NtQueryInformationToken`
- `0x18000f54c`: `GetLogonCacheForUser`
- `0x18000f35c`: `Surrogate plugin`
- `0x18000f613`: `SaveLogonCacheForUser`

## pseudocode

```c
__int64 __fastcall SpOnProfileLoaded(void *a1, void *a2, char a3)
{
  struct _LOGON_SESSION *v3; // r13
  struct _CloudAPCache *v4; // rdi
  char *v5; // r14
  unsigned int LogonCacheForUser; // ebx
  const char *v8; // r9
  unsigned int i; // edx
  __int64 v10; // rax
  const char *v11; // r9
  const char *v12; // rax
  bool v13; // zf
  const char *v14; // r9
  const char *v15; // r9
  const char *v16; // r9
  const char *v17; // rax
  bool v18; // zf
  __int64 v19; // rsi
  int v20; // eax
  const char *v21; // r9
  const char *v22; // rax
  bool v23; // zf
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // rax
  bool v28; // zf
  PULONG ReturnLength; // [rsp+20h] [rbp-69h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-69h]
  bool v32; // [rsp+40h] [rbp-49h] BYREF
  struct _CloudAPCache *v33; // [rsp+48h] [rbp-41h] BYREF
  ULONG v34; // [rsp+50h] [rbp-39h] BYREF
  struct _LOGON_SESSION *v35; // [rsp+58h] [rbp-31h] BYREF
  __int128 v36; // [rsp+60h] [rbp-29h] BYREF
  _OWORD TokenInformation[3]; // [rsp+70h] [rbp-19h] BYREF
  __int64 v38; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v3 = 0;
  v38 = 0;
  v4 = 0;
  v34 = 0;
  v5 = 0;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v36 = 0;
  if ( a3 )
  {
    LogonCacheForUser = (*((__int64 (__fastcall **)(void *, __int128 *))g_pLsaIdProvHostFunctionTable + 10))(a1, &v36);
    if ( LogonCacheForUser )
    {
      v8 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCacheForUser, v8, 8340, "GetProvInfo", &Class);
    }
    else
    {
      RtlAcquireResourceShared(&g_PackageListLock, 1u);
      if ( g_pPlugins )
      {
        for ( i = 0; i < g_cPlugins; ++i )
        {
          v5 = (char *)g_pPlugins + 392 * i;
          v10 = v36 - *(_QWORD *)(v5 + 68);
          if ( (_QWORD)v36 == *(_QWORD *)(v5 + 68) )
            v10 = *((_QWORD *)&v36 + 1) - *(_QWORD *)(v5 + 76);
          if ( !v10 )
          {
            if ( (v5[160] & 4) != 0 )
            {
              LogonCacheForUser = -1073741637;
              v11 = "";
              while ( 1 )
              {
                v12 = v11--;
                v13 = *v11 == 92;
                if ( *v11 == 92 )
                  break;
                if ( v11 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
                {
                  v13 = *v11 == 92;
                  break;
                }
              }
              if ( v13 )
                v11 = v12;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225659LL, v11, 8349, "Surrogate plugin", &Class);
            }
            else if ( a2 )
            {
              LogonCacheForUser = NtQueryInformationToken(a2, TokenStatistics, TokenInformation, 0x38u, &v34);
              if ( LogonCacheForUser )
              {
                v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(ReturnLength) = 8366;
                WPPTraceLogA(
                  0,
                  "0x%08x %s:%u : %s:%ws",
                  LogonCacheForUser,
                  v15,
                  ReturnLength,
                  "NtQueryInformationToken",
                  &Class);
              }
              else
              {
                LogonCacheForUser = _AcquireLogonSession(1, (struct _LUID *)TokenInformation + 1, &v35);
                if ( LogonCacheForUser )
                {
                  v16 = "";
                  while ( 1 )
                  {
                    v17 = v16--;
                    v18 = *v16 == 92;
                    if ( *v16 == 92 )
                      break;
                    if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
                    {
                      v18 = *v16 == 92;
                      break;
                    }
                  }
                  if ( v18 )
                    v16 = v17;
                  LODWORD(ReturnLength) = 8371;
                  WPPTraceLogA(
                    0,
                    "0x%08x %s:%u : %s:%ws",
                    LogonCacheForUser,
                    v16,
                    ReturnLength,
                    "AcquireLogonSession",
                    &Class);
                  v3 = v35;
                }
                else
                {
                  v3 = v35;
                  v19 = *((_QWORD *)v35 + 7);
                  SCLockAcquireResourceExclusive((PRTL_RESOURCE)(*(_QWORD *)(v19 + 24) + 24LL));
                  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v19 + 32));
                  if ( !*(_DWORD *)(v19 + 76) )
                    _UnprotectUserCacheEntry((struct _USER_CACHE_ENTRY *)v19);
                  ++*(_DWORD *)(v19 + 76);
                  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v19 + 32));
                  wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::GetImpl'::`2'::impl);
                  if ( IsLoadAadCredKeyFromProfileEnabled() )
                  {
                    v20 = RemoveUserSidFromDeferredCacheCleanup(*(void **)(v19 + 240));
                    if ( v20 < 0 )
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0x20BD,
                        (int)"onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp",
                        (const char *)(unsigned int)v20);
                  }
                  LogonCacheForUser = _GetLogonCacheForUser(
                                        *((const unsigned __int16 **)v5 + 43),
                                        (const unsigned __int16 *)(v19 + 104),
                                        L"CacheData",
                                        &v33);
                  if ( LogonCacheForUser )
                  {
                    v21 = "";
                    while ( 1 )
                    {
                      v22 = v21--;
                      v23 = *v21 == 92;
                      if ( *v21 == 92 )
                        break;
                      if ( v21 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
                      {
                        v23 = *v21 == 92;
                        break;
                      }
                    }
                    if ( v23 )
                      v21 = v22;
                    LODWORD(ReturnLength) = 8388;
                    WPPTraceLogA(
                      0,
                      "0x%08x %s:%u : %s:%ws",
                      LogonCacheForUser,
                      v21,
                      ReturnLength,
                      "GetLogonCacheForUser",
                      &Class);
                  }
                  else
                  {
                    LogonCacheForUser = SyncDpapiKey(
                                          a2,
                                          1,
                                          (struct _ApPluginPkg *)v5,
                                          (struct _USER_CACHE_ENTRY *)v19,
                                          0,
                                          1,
                                          v33,
                                          &v32);
                    if ( LogonCacheForUser )
                    {
                      v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                      LODWORD(ReturnLengtha) = 8399;
                      WPPTraceLogA(
                        0,
                        "0x%08x %s:%u : %s:%ws",
                        LogonCacheForUser,
                        v24,
                        ReturnLengtha,
                        "SyncDpapiKey",
                        &Class);
                    }
                    else if ( v32
                           && (LogonCacheForUser = _SaveLogonCacheForUser(
                                                     *((const unsigned __int16 **)v5 + 43),
                                                     (const unsigned __int16 *)(v19 + 104),
                                                     L"CacheData",
                                                     v33)) != 0 )
                    {
                      v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                      LODWORD(ReturnLengtha) = 8408;
                      WPPTraceLogA(
                        0,
                        "0x%08x %s:%u : %s:%ws",
                        LogonCacheForUser,
                        v25,
                        ReturnLengtha,
                        "SaveLogonCacheForUser",
                        &Class);
                    }
                    else
                    {
                      LogonCacheForUser = 0;
                    }
                  }
                  UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v19);
                }
              }
            }
            else
            {
              LogonCacheForUser = -1073741811;
              v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v14, 8357, "Null Arg(s)", &Class);
            }
            goto LABEL_60;
          }
        }
      }
      v5 = 0;
      RtlReleaseResource(&g_PackageListLock);
      v26 = "";
      LogonCacheForUser = -2146893039;
      while ( 1 )
      {
        v27 = v26--;
        v28 = *v26 == 92;
        if ( *v26 == 92 )
          break;
        if ( v26 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v28 = *v26 == 92;
          break;
        }
      }
      if ( v28 )
        v26 = v27;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 2148074257LL, v26, 8343, "RefPackage", &Class);
    }
LABEL_60:
    v4 = v33;
  }
  else
  {
    LogonCacheForUser = 0;
  }
  ReleaseLogonSession(v3);
  if ( v5 )
    RtlReleaseResource(&g_PackageListLock);
  FreeCloudAPCache(v4);
  return LogonCacheForUser;
}

```

## disassembly

```asm
0x18000f210  mov     [rsp-8+arg_10], rbx
0x18000f215  push    rbp
0x18000f216  push    rsi
0x18000f217  push    rdi
0x18000f218  push    r12
0x18000f21a  push    r13
0x18000f21c  push    r14
0x18000f21e  push    r15
0x18000f220  lea     rbp, [rsp-27h]
0x18000f225  sub     rsp, 0B0h
0x18000f22c  mov     rax, cs:__security_cookie
0x18000f233  xor     rax, rsp
0x18000f236  mov     [rbp+57h+var_38], rax
0x18000f23a  xor     eax, eax
0x18000f23c  xorps   xmm0, xmm0
0x18000f23f  xor     r13d, r13d
0x18000f242  mov     [rbp+57h+var_40], rax
0x18000f246  xor     edi, edi
0x18000f248  mov     [rbp+57h+var_90], eax
0x18000f24b  xor     r14d, r14d
0x18000f24e  mov     [rbp+57h+var_A0], al
0x18000f251  mov     [rbp+57h+var_88], r13
0x18000f255  mov     r12, rdx
0x18000f258  mov     [rbp+57h+var_98], rdi
0x18000f25c  movups  [rbp+57h+TokenInformation], xmm0
0x18000f260  movups  [rbp+57h+var_60], xmm0
0x18000f264  movups  [rbp+57h+var_50], xmm0
0x18000f268  movups  [rbp+57h+var_80], xmm0
0x18000f26c  test    r8b, r8b
0x18000f26f  jnz     short loc_18000F278
0x18000f271  xor     ebx, ebx
0x18000f273  jmp     loc_18000F6A9
0x18000f278  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x18000f27f  lea     rdx, [rbp+57h+var_80]
0x18000f283  mov     rax, [rax+50h]
0x18000f287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f28c  mov     ebx, eax
0x18000f28e  test    eax, eax
0x18000f290  jz      short loc_18000F2C6
0x18000f292  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000f299  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000f29e  mov     r9, rax
0x18000f2a1  lea     rax, Class
0x18000f2a8  mov     [rsp+0E0h+var_B0], rax
0x18000f2ad  lea     rax, aGetprovinfo; "GetProvInfo"
0x18000f2b4  mov     qword ptr [rsp+0E0h+var_B8], rax
0x18000f2b9  mov     dword ptr [rsp+0E0h+ReturnLength], 2094h
0x18000f2c1  jmp     loc_18000F694
0x18000f2c6  mov     dl, 1; Wait
0x18000f2c8  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18000f2cf  call    cs:__imp_RtlAcquireResourceShared
0x18000f2d5  mov     r8, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x18000f2dc  test    r8, r8
0x18000f2df  jz      loc_18000F638
0x18000f2e5  xor     edx, edx
0x18000f2e7  cmp     edx, cs:?g_cPlugins@@3KA; ulong g_cPlugins
0x18000f2ed  jnb     loc_18000F638
0x18000f2f3  mov     eax, edx
0x18000f2f5  imul    r14, rax, 188h
0x18000f2fc  mov     rax, qword ptr [rbp+57h+var_80]
0x18000f300  add     r14, r8
0x18000f303  sub     rax, [r14+44h]
0x18000f307  jnz     short loc_18000F311
0x18000f309  mov     rax, qword ptr [rbp+57h+var_80+8]
0x18000f30d  sub     rax, [r14+4Ch]
0x18000f311  test    rax, rax
0x18000f314  jz      short loc_18000F31A
0x18000f316  inc     edx
0x18000f318  jmp     short loc_18000F2E7
0x18000f31a  test    byte ptr [r14+0A0h], 4
0x18000f322  jz      short loc_18000F375
0x18000f324  mov     ebx, 0C00000BBh
0x18000f329  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x18000f330  lea     rdi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000f337  mov     rax, r9
0x18000f33a  dec     r9
0x18000f33d  cmp     byte ptr [r9], 5Ch ; '\'
0x18000f341  jz      short loc_18000F34C
0x18000f343  cmp     r9, rdi
0x18000f346  ja      short loc_18000F337
0x18000f348  cmp     byte ptr [r9], 5Ch ; '\'
0x18000f34c  cmovz   r9, rax
0x18000f350  lea     rax, Class
0x18000f357  mov     [rsp+0E0h+var_B0], rax
0x18000f35c  lea     rax, aSurrogatePlugi_0; "Surrogate plugin"
0x18000f363  mov     qword ptr [rsp+0E0h+var_B8], rax
0x18000f368  mov     dword ptr [rsp+0E0h+ReturnLength], 209Dh
0x18000f370  jmp     loc_18000F694
0x18000f375  test    r12, r12
0x18000f378  jnz     short loc_18000F3B3
0x18000f37a  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000f381  mov     ebx, 0C000000Dh
0x18000f386  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000f38b  mov     r9, rax
0x18000f38e  lea     rax, Class
0x18000f395  mov     [rsp+0E0h+var_B0], rax
0x18000f39a  lea     rax, aNullArgS; "Null Arg(s)"
0x18000f3a1  mov     qword ptr [rsp+0E0h+var_B8], rax
0x18000f3a6  mov     dword ptr [rsp+0E0h+ReturnLength], 20A5h
0x18000f3ae  jmp     loc_18000F694
0x18000f3b3  mov     r9d, 38h ; '8'; TokenInformationLength
0x18000f3b9  lea     rax, [rbp+57h+var_90]
0x18000f3bd  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18000f3c1  mov     [rsp+0E0h+ReturnLength], rax; int
0x18000f3c6  mov     rcx, r12; TokenHandle
0x18000f3c9  lea     edx, [r9-2Eh]; TokenInformationClass
0x18000f3cd  call    cs:__imp_NtQueryInformationToken
0x18000f3d3  mov     ebx, eax
0x18000f3d5  test    eax, eax
0x18000f3d7  jz      short loc_18000F40D
0x18000f3d9  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000f3e0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000f3e5  mov     r9, rax
0x18000f3e8  lea     rax, Class
0x18000f3ef  mov     [rsp+0E0h+var_B0], rax
0x18000f3f4  lea     rax, aNtqueryinforma_1; "NtQueryInformationToken"
0x18000f3fb  mov     qword ptr [rsp+0E0h+var_B8], rax
0x18000f400  mov     dword ptr [rsp+0E0h+ReturnLength], 20AEh
0x18000f408  jmp     loc_18000F694
0x18000f40d  lea     r8, [rbp+57h+var_88]; struct _LOGON_SESSION **
0x18000f411  mov     ecx, 1; int
0x18000f416  lea     rdx, [rbp+57h+TokenInformation+8]; struct _LUID *
0x18000f41a  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x18000f41f  mov     ebx, eax
0x18000f421  test    eax, eax
0x18000f423  jz      short loc_18000F486
0x18000f425  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x18000f42c  lea     rdi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000f433  mov     rax, r9
0x18000f436  dec     r9
0x18000f439  cmp     byte ptr [r9], 5Ch ; '\'
0x18000f43d  jz      short loc_18000F448
0x18000f43f  cmp     r9, rdi
0x18000f442  ja      short loc_18000F433
0x18000f444  cmp     byte ptr [r9], 5Ch ; '\'
0x18000f448  cmovz   r9, rax
0x18000f44c  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000f453  lea     rax, Class
0x18000f45a  mov     r8d, ebx
0x18000f45d  mov     [rsp+0E0h+var_B0], rax
0x18000f462  xor     ecx, ecx
0x18000f464  lea     rax, aAcquirelogonse_0; "AcquireLogonSession"
0x18000f46b  mov     qword ptr [rsp+0E0h+var_B8], rax
0x18000f470  mov     dword ptr [rsp+0E0h+ReturnLength], 20B3h
0x18000f478  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000f47d  mov     r13, [rbp+57h+var_88]
0x18000f481  jmp     loc_18000F6A5
0x18000f486  mov     r13, [rbp+57h+var_88]
0x18000f48a  mov     rsi, [r13+38h]
0x18000f48e  mov     rcx, [rsi+18h]
0x18000f492  add     rcx, 18h; Resource
0x18000f496  call    SCLockAcquireResourceExclusive
0x18000f49b  lea     rcx, [rsi+20h]; CriticalSection
0x18000f49f  call    cs:__imp_RtlEnterCriticalSection
0x18000f4a5  cmp     [rsi+4Ch], edi
0x18000f4a8  jnz     short loc_18000F4B2
0x18000f4aa  mov     rcx, rsi; struct _USER_CACHE_ENTRY *
0x18000f4ad  call    ?_UnprotectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; _UnprotectUserCacheEntry(_USER_CACHE_ENTRY *)
0x18000f4b2  inc     dword ptr [rsi+4Ch]
0x18000f4b5  lea     rcx, [rsi+20h]; CriticalSection
0x18000f4b9  call    cs:__imp_RtlLeaveCriticalSection
0x18000f4bf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile> `wil::Feature<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::GetImpl(void)'::`2'::impl
0x18000f4c6  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18000f4cb  call    ?IsLoadAadCredKeyFromProfileEnabled@@YA_NXZ; IsLoadAadCredKeyFromProfileEnabled(void)
0x18000f4d0  lea     rdi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000f4d7  test    al, al
0x18000f4d9  jz      short loc_18000F4FF
0x18000f4db  mov     rcx, [rsi+0F0h]; void *
0x18000f4e2  call    ?RemoveUserSidFromDeferredCacheCleanup@@YAJPEAX@Z; RemoveUserSidFromDeferredCacheCleanup(void *)
0x18000f4e7  test    eax, eax
0x18000f4e9  jns     short loc_18000F4FF
0x18000f4eb  mov     rcx, [rbp+5Fh]; this
0x18000f4ef  mov     r9d, eax; char *
0x18000f4f2  mov     r8, rdi; unsigned int
0x18000f4f5  mov     edx, 20BDh; void *
0x18000f4fa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f4ff  mov     rcx, [r14+158h]; unsigned __int16 *
0x18000f506  lea     r9, [rbp+57h+var_98]; struct _CloudAPCache **
0x18000f50a  lea     r8, aCachedata; "CacheData"
0x18000f511  lea     rdx, [rsi+68h]; unsigned __int16 *
0x18000f515  call    ?_GetLogonCacheForUser@@YAJPEBG00PEAPEAU_CloudAPCache@@@Z; _GetLogonCacheForUser(ushort const *,ushort const *,ushort const *,_CloudAPCache * *)
0x18000f51a  mov     ebx, eax
0x18000f51c  test    eax, eax
0x18000f51e  jz      short loc_18000F576
0x18000f520  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x18000f527  mov     rax, r9
0x18000f52a  dec     r9
0x18000f52d  cmp     byte ptr [r9], 5Ch ; '\'
0x18000f531  jz      short loc_18000F53C
0x18000f533  cmp     r9, rdi
0x18000f536  ja      short loc_18000F527
0x18000f538  cmp     byte ptr [r9], 5Ch ; '\'
0x18000f53c  cmovz   r9, rax
0x18000f540  lea     rax, Class
0x18000f547  mov     [rsp+0E0h+var_B0], rax
0x18000f54c  lea     rax, aGetlogoncachef; "GetLogonCacheForUser"
0x18000f553  mov     qword ptr [rsp+0E0h+var_B8], rax
0x18000f558  mov     dword ptr [rsp+0E0h+ReturnLength], 20C4h
0x18000f560  mov     r8d, ebx
0x18000f563  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000f56a  xor     ecx, ecx
0x18000f56c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000f571  jmp     loc_18000F62E
0x18000f576  lea     rax, [rbp+57h+var_A0]
0x18000f57a  mov     r9, rsi; struct _USER_CACHE_ENTRY *
0x18000f57d  mov     [rsp+0E0h+var_A8], rax; bool *
0x18000f582  mov     r8, r14; struct _ApPluginPkg *
0x18000f585  mov     rax, [rbp+57h+var_98]
0x18000f589  mov     dl, 1; bool
0x18000f58b  mov     [rsp+0E0h+var_B0], rax; struct _CloudAPCache *
0x18000f590  mov     rcx, r12; TokenHandle
0x18000f593  mov     [rsp+0E0h+var_B8], 1; bool
0x18000f598  mov     byte ptr [rsp+0E0h+ReturnLength], 0; bool
0x18000f59d  call    ?SyncDpapiKey@@YAJPEAX_NPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@11PEAU_CloudAPCache@@PEA_N@Z; SyncDpapiKey(void *,bool,_ApPluginPkg *,_USER_CACHE_ENTRY *,bool,bool,_CloudAPCache *,bool *)
0x18000f5a2  mov     ebx, eax
0x18000f5a4  test    eax, eax
0x18000f5a6  jz      short loc_18000F5D5
0x18000f5a8  mov     rcx, rdi; char *
0x18000f5ab  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000f5b0  mov     r9, rax
0x18000f5b3  lea     rax, Class
0x18000f5ba  mov     [rsp+0E0h+var_B0], rax
0x18000f5bf  lea     rax, aSyncdpapikey; "SyncDpapiKey"
0x18000f5c6  mov     qword ptr [rsp+0E0h+var_B8], rax
0x18000f5cb  mov     dword ptr [rsp+0E0h+ReturnLength], 20CFh
0x18000f5d3  jmp     short loc_18000F560
0x18000f5d5  cmp     [rbp+57h+var_A0], 0
0x18000f5d9  jz      short loc_18000F62C
0x18000f5db  mov     r9, [rbp+57h+var_98]; struct _CloudAPCache *
0x18000f5df  lea     r8, aCachedata; "CacheData"
0x18000f5e6  mov     rcx, [r14+158h]; unsigned __int16 *
0x18000f5ed  lea     rdx, [rsi+68h]; unsigned __int16 *
0x18000f5f1  call    ?_SaveLogonCacheForUser@@YAJPEBG00PEAU_CloudAPCache@@@Z; _SaveLogonCacheForUser(ushort const *,ushort const *,ushort const *,_CloudAPCache *)
0x18000f5f6  mov     ebx, eax
0x18000f5f8  test    eax, eax
0x18000f5fa  jz      short loc_18000F62C
0x18000f5fc  mov     rcx, rdi; char *
0x18000f5ff  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000f604  mov     r9, rax
0x18000f607  lea     rax, Class
0x18000f60e  mov     [rsp+0E0h+var_B0], rax
0x18000f613  lea     rax, aSavelogoncache; "SaveLogonCacheForUser"
0x18000f61a  mov     qword ptr [rsp+0E0h+var_B8], rax
0x18000f61f  mov     dword ptr [rsp+0E0h+ReturnLength], 20D8h
0x18000f627  jmp     loc_18000F560
0x18000f62c  xor     ebx, ebx
0x18000f62e  mov     rcx, rsi; struct _USER_CACHE_ENTRY *
0x18000f631  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x18000f636  jmp     short loc_18000F6A5
0x18000f638  xor     r14d, r14d
0x18000f63b  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18000f642  call    cs:__imp_RtlReleaseResource
0x18000f648  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x18000f64f  mov     ebx, 80090311h
0x18000f654  lea     rdi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000f65b  mov     rax, r9
0x18000f65e  dec     r9
0x18000f661  cmp     byte ptr [r9], 5Ch ; '\'
0x18000f665  jz      short loc_18000F670
0x18000f667  cmp     r9, rdi
0x18000f66a  ja      short loc_18000F65B
0x18000f66c  cmp     byte ptr [r9], 5Ch ; '\'
0x18000f670  cmovz   r9, rax
0x18000f674  lea     rax, Class
0x18000f67b  mov     [rsp+0E0h+var_B0], rax
0x18000f680  lea     rax, aRefpackage; "RefPackage"
0x18000f687  mov     qword ptr [rsp+0E0h+var_B8], rax
0x18000f68c  mov     dword ptr [rsp+0E0h+ReturnLength], 2097h
0x18000f694  mov     r8d, ebx
0x18000f697  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000f69e  xor     ecx, ecx
0x18000f6a0  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000f6a5  mov     rdi, [rbp+57h+var_98]
0x18000f6a9  mov     rcx, r13; struct _LOGON_SESSION *
0x18000f6ac  call    ?ReleaseLogonSession@@YAXPEAU_LOGON_SESSION@@@Z; ReleaseLogonSession(_LOGON_SESSION *)
0x18000f6b1  test    r14, r14
0x18000f6b4  jz      short loc_18000F6C3
0x18000f6b6  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18000f6bd  call    cs:__imp_RtlReleaseResource
0x18000f6c3  mov     rcx, rdi; hMem
0x18000f6c6  call    ?FreeCloudAPCache@@YAXPEAU_CloudAPCache@@@Z; FreeCloudAPCache(_CloudAPCache *)
0x18000f6cb  mov     eax, ebx
0x18000f6cd  mov     rcx, [rbp+57h+var_38]
0x18000f6d1  xor     rcx, rsp; StackCookie
0x18000f6d4  call    __security_check_cookie
0x18000f6d9  mov     rbx, [rsp+0E0h+arg_10]
0x18000f6e1  add     rsp, 0B0h
0x18000f6e8  pop     r15
0x18000f6ea  pop     r14
0x18000f6ec  pop     r13
0x18000f6ee  pop     r12
0x18000f6f0  pop     rdi
0x18000f6f1  pop     rsi
0x18000f6f2  pop     rbp
0x18000f6f3  retn
```
