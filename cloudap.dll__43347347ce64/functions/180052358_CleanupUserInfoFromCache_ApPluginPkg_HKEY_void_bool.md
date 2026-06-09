# CleanupUserInfoFromCache(_ApPluginPkg *,HKEY__ *,void *,bool)

- ea: `0x180052358`
- end: `0x1800528b7`
- name: `?CleanupUserInfoFromCache@@YAJPEAU_ApPluginPkg@@PEAUHKEY__@@PEAX_N@Z`
- size: `1375`
- prototype: `__int64 __fastcall(struct _ApPluginPkg *, HKEY, void *, char)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18004c6ec`
- `0x180052288`

## callees

- `0x180006a80`
- `0x180007ef0`
- `0x180007fc0`
- `0x18000a600`
- `0x18000a8f0`
- `0x18000ac40`
- `0x18000e7e0`
- `0x18000f100`
- `0x18002d0a4`
- `0x180032998`
- `0x18003fcdc`
- `0x180041210`
- `0x180052358`
- `0x18005d774`
- `0x18005da64`
- `0x18005dc18`
- `0x18005e654`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052854`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052854`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800523ba`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800523ba`
- `ntdll!RtlReleaseResource` at `0x18005246b`
- `ntdll!RtlReleaseResource` at `0x180052731`
- `ntdll!RtlReleaseResource` at `0x18005246b`
- `ntdll!RtlReleaseResource` at `0x180052731`

## string_xrefs

- `0x180052424`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005248f`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800527fc`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800523db`: `FindUserInCacheBySid`
- `0x18005268c`: `CacheData`
- `0x1800526e2`: `PublicCacheData`
- `0x180052767`: `CreateOrAcquireUserCacheEntry`
- `0x1800525d6`: `RemoveUserFromName2SidCache`
- `0x180052623`: `RemoveUserFromSAMNameCache`
- `0x180052547`: `DeleteMappedAadAccountSidMap`
- `0x18005258b`: `RemoveUserFromSid2NameCache`
- `0x18005266f`: `RemoveLogonCacheAndKeysForUser`
- `0x1800526b9`: `RemoveLogonCacheForUser`
- `0x180052708`: `RemoveLogonPublicCacheForUser`

## pseudocode

```c
__int64 __fastcall CleanupUserInfoFromCache(struct _ApPluginPkg *a1, HKEY a2, void *a3, char a4)
{
  struct _USER_CACHE_ENTRY *v7; // r12
  const WCHAR *v8; // r15
  unsigned int UserInCacheBySid; // ebx
  const char *v10; // rax
  int v11; // r8d
  __int64 v12; // r10
  __int64 v13; // r11
  int v14; // eax
  const char *v15; // rax
  __int64 v16; // r8
  void *v17; // rbx
  const char *v18; // rax
  __int64 v19; // r8
  void *v20; // rdx
  HKEY v21; // rbx
  const char *v22; // rax
  __int64 v23; // r8
  const char *v24; // rax
  __int64 v25; // r8
  const char *v26; // rax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // rax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // rax
  const char *v35; // rax
  __int64 v36; // r8
  char v37; // al
  const char *v38; // rax
  struct _USER_CACHE_ENTRY **v40; // [rsp+20h] [rbp-58h]
  struct _USER_CACHE_ENTRY **v41; // [rsp+20h] [rbp-58h]
  unsigned int v42; // [rsp+40h] [rbp-38h] BYREF
  LPCWSTR lpSrcStr; // [rsp+48h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  struct _USER_CACHE_ENTRY *v45; // [rsp+58h] [rbp-20h] BYREF
  unsigned __int16 *v46; // [rsp+60h] [rbp-18h] BYREF
  void *v47; // [rsp+68h] [rbp-10h] BYREF
  unsigned int v48; // [rsp+C0h] [rbp+48h] BYREF
  HKEY v49; // [rsp+C8h] [rbp+50h]
  void *v50; // [rsp+D0h] [rbp+58h]
  char v51; // [rsp+D8h] [rbp+60h]

  v51 = a4;
  v50 = a3;
  v49 = a2;
  v45 = 0;
  hKey = 0;
  lpSrcStr = 0;
  v7 = 0;
  v46 = 0;
  v8 = 0;
  v47 = 0;
  if ( !a1 || !a3 )
  {
    UserInCacheBySid = -1073741811;
    v38 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v38, 8451, "InvalidArg(s)", &Class);
    goto LABEL_36;
  }
  RtlAcquireResourceExclusive(&g_LookupsCacheLock, 1u);
  UserInCacheBySid = FindUserInCacheBySid(a2, a3, &hKey);
  if ( UserInCacheBySid )
  {
LABEL_6:
    v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(v40) = v11;
    WPPTraceLogA(v12, "0x%08x %s:%u : %s:%ws", UserInCacheBySid, v10, v40, v13, &Class);
    RtlReleaseResource(&g_LookupsCacheLock);
    goto LABEL_36;
  }
  v48 = 0;
  UserInCacheBySid = GetRegVal(hKey, L"IdentityName", 6u, &v48, (void **)&lpSrcStr);
  if ( UserInCacheBySid )
  {
    v8 = lpSrcStr;
    goto LABEL_6;
  }
  v14 = *((_DWORD *)a1 + 40);
  LOBYTE(v48) = 0;
  if ( (v14 & 5) == 0 )
  {
    v42 = 0;
    if ( (int)GetRegVal(hKey, L"SAMName", 6u, &v42, (void **)&v46) < 0 )
    {
      v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v40) = 8478;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v16, v15, v40, "GetStringRegVal:SAM_Name", &Class);
      LOBYTE(v48) = 1;
    }
  }
  if ( v51 )
  {
    v17 = v50;
    if ( *((char *)a1 + 160) < 0
      && SpFindMappedSid(*((void **)a1 + 2), v50, &v47) >= 0
      && DeleteMappedAadAccountSidMap((struct _GUID *)((char *)a1 + 68), v47) )
    {
      v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v40) = 8499;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v19, v18, v40, "DeleteMappedAadAccountSidMap", &Class);
    }
    v20 = v17;
    v21 = v49;
    if ( (int)RemoveUserFromSid2NameCache(v49, v20) < 0 )
    {
      v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v40) = 8509;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v23, v22, v40, "RemoveUserFromSid2NameCache", &Class);
      LOBYTE(v48) = 1;
    }
    v8 = lpSrcStr;
    if ( (int)_RemoveUserFromName2SidCache(v21, (UCHAR *)lpSrcStr, 0) < 0 )
    {
      v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v40) = 8519;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v25, v24, v40, "RemoveUserFromName2SidCache", &Class);
      LOBYTE(v48) = 1;
    }
    if ( v46 && (int)RemoveUserFromSAMNameCache(v21, v46) < 0 )
    {
      v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v40) = 8532;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v27, v26, v40, "RemoveUserFromSAMNameCache", &Class);
      LOBYTE(v48) = 1;
    }
    if ( (int)RemoveLogonCacheAndKeysForUser(*((const unsigned __int16 **)a1 + 43), v8) >= 0 )
      goto LABEL_29;
    v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(v40) = 8543;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v29, v28, v40, "RemoveLogonCacheAndKeysForUser", &Class);
  }
  else
  {
    v8 = lpSrcStr;
    if ( (int)_RemoveLogonCacheForUser(*((const unsigned __int16 **)a1 + 43), lpSrcStr, L"CacheData") < 0 )
    {
      v30 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v40) = 8555;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v31, v30, v40, "RemoveLogonCacheForUser", &Class);
      LOBYTE(v48) = 1;
    }
    if ( (int)_RemoveLogonCacheForUser(*((const unsigned __int16 **)a1 + 43), v8, L"PublicCacheData") >= 0 )
      goto LABEL_29;
    v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(v40) = 8564;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v33, v32, v40, "RemoveLogonPublicCacheForUser", &Class);
  }
  LOBYTE(v48) = 1;
LABEL_29:
  RtlReleaseResource(&g_LookupsCacheLock);
  UserInCacheBySid = _CreateOrAcquireUserCacheEntry(0, (struct _GUID *)((char *)a1 + 68), v8, 0, &v45);
  if ( UserInCacheBySid )
  {
    v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(v41) = 8580;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserInCacheBySid, v34, v41, "CreateOrAcquireUserCacheEntry", &Class);
    v7 = v45;
  }
  else
  {
    v7 = v45;
    LockAndUnProtectUserCacheEntry(v45, 1);
    if ( UnprovisionTBAL(v7, 0, 0) >= 0 )
    {
      v37 = v48;
    }
    else
    {
      v35 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v41) = 8594;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v36, v35, v41, "UnprovisionTBAL", &Class);
      v37 = 1;
    }
    UserInCacheBySid = v37 != 0 ? 0xC0000001 : 0;
    UnlockAndProtectUserCacheEntry(v7);
  }
LABEL_36:
  _ReleaseUserCacheEntry(0, v7);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v8 )
    ((void (__fastcall *)(const WCHAR *))g_pLsaFunctionTable->FreeLsaHeap)(v8);
  if ( v46 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v47 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  return UserInCacheBySid;
}

```

## disassembly

```asm
0x180052358  mov     [rsp-40h+arg_18], r9b
0x18005235d  mov     [rsp-40h+arg_10], r8
0x180052362  mov     [rsp-40h+arg_8], rdx
0x180052367  push    rbp
0x180052368  push    rbx
0x180052369  push    rsi
0x18005236a  push    rdi
0x18005236b  push    r12
0x18005236d  push    r13
0x18005236f  push    r14
0x180052371  push    r15
0x180052373  mov     rbp, rsp
0x180052376  sub     rsp, 78h
0x18005237a  xor     esi, esi
0x18005237c  mov     rbx, r8
0x18005237f  mov     [rbp+var_20], rsi
0x180052383  mov     rdi, rdx
0x180052386  mov     [rbp+hKey], rsi
0x18005238a  mov     r13, rcx
0x18005238d  mov     [rbp+lpSrcStr], rsi
0x180052391  mov     r12d, esi
0x180052394  mov     [rbp+var_18], rsi
0x180052398  mov     r15d, esi
0x18005239b  mov     [rbp+var_10], rsi
0x18005239f  test    rcx, rcx
0x1800523a2  jz      loc_1800527FC
0x1800523a8  test    rbx, rbx
0x1800523ab  jz      loc_1800527FC
0x1800523b1  mov     dl, 1; Wait
0x1800523b3  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x1800523ba  call    cs:__imp_RtlAcquireResourceExclusive
0x1800523c0  lea     r8, [rbp+hKey]; phkResult
0x1800523c4  mov     rdx, rbx; void *
0x1800523c7  mov     rcx, rdi; hKey
0x1800523ca  call    ?FindUserInCacheBySid@@YAJPEAUHKEY__@@PEAXPEAPEAU1@@Z; FindUserInCacheBySid(HKEY__ *,void *,HKEY__ * *)
0x1800523cf  mov     ebx, eax
0x1800523d1  test    eax, eax
0x1800523d3  jz      short loc_1800523E4
0x1800523d5  mov     r8d, 210Eh
0x1800523db  lea     r11, aFinduserincach; "FindUserInCacheBySid"
0x1800523e2  jmp     short loc_180052424
0x1800523e4  mov     rcx, [rbp+hKey]; hkey
0x1800523e8  lea     rax, [rbp+lpSrcStr]
0x1800523ec  mov     r15d, 6
0x1800523f2  mov     [rbp+arg_0], esi
0x1800523f5  mov     r8d, r15d; dwFlags
0x1800523f8  mov     [rsp+78h+var_58], rax; void **
0x1800523fd  lea     r9, [rbp+arg_0]; unsigned int *
0x180052401  lea     rdx, aIdentityname; "IdentityName"
0x180052408  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x18005240d  mov     ebx, eax
0x18005240f  test    eax, eax
0x180052411  jz      short loc_180052476
0x180052413  mov     r15, [rbp+lpSrcStr]
0x180052417  lea     r11, aGetstringregva; "GetStringRegVal(IdentityName)"
0x18005241e  mov     r8d, 2114h
0x180052424  lea     r14, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18005242b  mov     r10, rsi
0x18005242e  mov     rcx, r14; char *
0x180052431  lea     rsi, Class
0x180052438  lea     rdi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005243f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180052444  mov     [rsp+78h+var_48], rsi
0x180052449  mov     r9, rax
0x18005244c  mov     [rsp+78h+var_50], r11
0x180052451  mov     rdx, rdi
0x180052454  mov     dword ptr [rsp+78h+var_58], r8d
0x180052459  mov     rcx, r10
0x18005245c  mov     r8d, ebx
0x18005245f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180052464  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18005246b  call    cs:__imp_RtlReleaseResource
0x180052471  jmp     loc_180052841
0x180052476  mov     eax, [r13+0A0h]
0x18005247d  lea     rdi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180052484  mov     byte ptr [rbp+arg_0], sil
0x180052488  lea     rsi, Class
0x18005248f  lea     r14, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180052496  test    al, 5
0x180052498  jnz     short loc_1800524F7
0x18005249a  mov     rcx, [rbp+hKey]; hkey
0x18005249e  lea     rax, [rbp+var_18]
0x1800524a2  lea     r9, [rbp+var_38]; unsigned int *
0x1800524a6  mov     [rsp+78h+var_58], rax; void **
0x1800524ab  mov     r8d, r15d; dwFlags
0x1800524ae  mov     [rbp+var_38], r12d
0x1800524b2  lea     rdx, aSamname; "SAMName"
0x1800524b9  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x1800524be  mov     r8d, eax
0x1800524c1  test    eax, eax
0x1800524c3  jns     short loc_1800524F7
0x1800524c5  mov     rcx, r14; char *
0x1800524c8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800524cd  mov     r9, rax
0x1800524d0  mov     [rsp+78h+var_48], rsi
0x1800524d5  lea     rax, aGetstringregva_6; "GetStringRegVal:SAM_Name"
0x1800524dc  mov     rdx, rdi
0x1800524df  mov     [rsp+78h+var_50], rax
0x1800524e4  xor     ecx, ecx
0x1800524e6  mov     dword ptr [rsp+78h+var_58], 211Eh
0x1800524ee  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800524f3  mov     byte ptr [rbp+arg_0], 1
0x1800524f7  cmp     [rbp+arg_18], r12b
0x1800524fb  jz      loc_180052688
0x180052501  test    byte ptr [r13+0A0h], 80h
0x180052509  mov     rbx, [rbp+arg_10]
0x18005250d  jz      short loc_180052565
0x18005250f  mov     rcx, [r13+10h]; void *
0x180052513  lea     r8, [rbp+var_10]; void **
0x180052517  mov     rdx, rbx; void *
0x18005251a  call    ?SpFindMappedSid@@YAJPEAX0PEAPEAX@Z; SpFindMappedSid(void *,void *,void * *)
0x18005251f  test    eax, eax
0x180052521  js      short loc_180052565
0x180052523  mov     rdx, [rbp+var_10]; void *
0x180052527  lea     rcx, [r13+44h]; struct _GUID *
0x18005252b  call    ?DeleteMappedAadAccountSidMap@@YAJPEAU_GUID@@PEAX@Z; DeleteMappedAadAccountSidMap(_GUID *,void *)
0x180052530  mov     r8d, eax
0x180052533  test    eax, eax
0x180052535  jz      short loc_180052565
0x180052537  mov     rcx, r14; char *
0x18005253a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005253f  mov     r9, rax
0x180052542  mov     [rsp+78h+var_48], rsi
0x180052547  lea     rax, aDeletemappedaa; "DeleteMappedAadAccountSidMap"
0x18005254e  mov     rdx, rdi
0x180052551  mov     [rsp+78h+var_50], rax
0x180052556  xor     ecx, ecx
0x180052558  mov     dword ptr [rsp+78h+var_58], 2133h
0x180052560  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180052565  mov     rdx, rbx; void *
0x180052568  mov     rbx, [rbp+arg_8]
0x18005256c  mov     rcx, rbx; hKey
0x18005256f  call    ?RemoveUserFromSid2NameCache@@YAJPEAUHKEY__@@PEAX@Z; RemoveUserFromSid2NameCache(HKEY__ *,void *)
0x180052574  mov     r8d, eax
0x180052577  test    eax, eax
0x180052579  jns     short loc_1800525AD
0x18005257b  mov     rcx, r14; char *
0x18005257e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180052583  mov     r9, rax
0x180052586  mov     [rsp+78h+var_48], rsi
0x18005258b  lea     rax, aRemoveuserfrom; "RemoveUserFromSid2NameCache"
0x180052592  mov     rdx, rdi
0x180052595  mov     [rsp+78h+var_50], rax
0x18005259a  xor     ecx, ecx
0x18005259c  mov     dword ptr [rsp+78h+var_58], 213Dh
0x1800525a4  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800525a9  mov     byte ptr [rbp+arg_0], 1
0x1800525ad  mov     r15, [rbp+lpSrcStr]
0x1800525b1  xor     r8d, r8d; bool
0x1800525b4  mov     rdx, r15; lpSrcStr
0x1800525b7  mov     rcx, rbx; hKey
0x1800525ba  call    ?_RemoveUserFromName2SidCache@@YAJPEAUHKEY__@@PEAG_N@Z; _RemoveUserFromName2SidCache(HKEY__ *,ushort *,bool)
0x1800525bf  mov     r8d, eax
0x1800525c2  test    eax, eax
0x1800525c4  jns     short loc_1800525F8
0x1800525c6  mov     rcx, r14; char *
0x1800525c9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800525ce  mov     r9, rax
0x1800525d1  mov     [rsp+78h+var_48], rsi
0x1800525d6  lea     rax, aRemoveuserfrom_0; "RemoveUserFromName2SidCache"
0x1800525dd  mov     rdx, rdi
0x1800525e0  mov     [rsp+78h+var_50], rax
0x1800525e5  xor     ecx, ecx
0x1800525e7  mov     dword ptr [rsp+78h+var_58], 2147h
0x1800525ef  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800525f4  mov     byte ptr [rbp+arg_0], 1
0x1800525f8  mov     rax, [rbp+var_18]
0x1800525fc  test    rax, rax
0x1800525ff  jz      short loc_180052645
0x180052601  mov     rdx, rax; unsigned __int16 *
0x180052604  mov     rcx, rbx; hKey
0x180052607  call    ?RemoveUserFromSAMNameCache@@YAJPEAUHKEY__@@PEAG@Z; RemoveUserFromSAMNameCache(HKEY__ *,ushort *)
0x18005260c  mov     r8d, eax
0x18005260f  test    eax, eax
0x180052611  jns     short loc_180052645
0x180052613  mov     rcx, r14; char *
0x180052616  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005261b  mov     r9, rax
0x18005261e  mov     [rsp+78h+var_48], rsi
0x180052623  lea     rax, aRemoveuserfrom_1; "RemoveUserFromSAMNameCache"
0x18005262a  mov     rdx, rdi
0x18005262d  mov     [rsp+78h+var_50], rax
0x180052632  xor     ecx, ecx
0x180052634  mov     dword ptr [rsp+78h+var_58], 2154h
0x18005263c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180052641  mov     byte ptr [rbp+arg_0], 1
0x180052645  mov     rcx, [r13+158h]; unsigned __int16 *
0x18005264c  mov     rdx, r15; lpSrcStr
0x18005264f  call    ?RemoveLogonCacheAndKeysForUser@@YAJPEBG0@Z; RemoveLogonCacheAndKeysForUser(ushort const *,ushort const *)
0x180052654  mov     r8d, eax
0x180052657  test    eax, eax
0x180052659  jns     loc_18005272A
0x18005265f  mov     rcx, r14; char *
0x180052662  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180052667  mov     [rsp+78h+var_48], rsi
0x18005266c  mov     r9, rax
0x18005266f  lea     rax, aRemovelogoncac; "RemoveLogonCacheAndKeysForUser"
0x180052676  mov     [rsp+78h+var_50], rax
0x18005267b  mov     dword ptr [rsp+78h+var_58], 215Fh
0x180052683  jmp     loc_18005271C
0x180052688  mov     r15, [rbp+lpSrcStr]
0x18005268c  lea     r8, aCachedata; "CacheData"
0x180052693  mov     rcx, [r13+158h]; unsigned __int16 *
0x18005269a  mov     rdx, r15; unsigned __int16 *
0x18005269d  call    ?_RemoveLogonCacheForUser@@YAJPEBG00@Z; _RemoveLogonCacheForUser(ushort const *,ushort const *,ushort const *)
0x1800526a2  mov     r8d, eax
0x1800526a5  test    eax, eax
0x1800526a7  jns     short loc_1800526DB
0x1800526a9  mov     rcx, r14; char *
0x1800526ac  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800526b1  mov     r9, rax
0x1800526b4  mov     [rsp+78h+var_48], rsi
0x1800526b9  lea     rax, aRemovelogoncac_0; "RemoveLogonCacheForUser"
0x1800526c0  mov     rdx, rdi
0x1800526c3  mov     [rsp+78h+var_50], rax
0x1800526c8  xor     ecx, ecx
0x1800526ca  mov     dword ptr [rsp+78h+var_58], 216Bh
0x1800526d2  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800526d7  mov     byte ptr [rbp+arg_0], 1
0x1800526db  mov     rcx, [r13+158h]; unsigned __int16 *
0x1800526e2  lea     r8, aPubliccachedat; "PublicCacheData"
0x1800526e9  mov     rdx, r15; unsigned __int16 *
0x1800526ec  call    ?_RemoveLogonCacheForUser@@YAJPEBG00@Z; _RemoveLogonCacheForUser(ushort const *,ushort const *,ushort const *)
0x1800526f1  mov     r8d, eax
0x1800526f4  test    eax, eax
0x1800526f6  jns     short loc_18005272A
0x1800526f8  mov     rcx, r14; char *
0x1800526fb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180052700  mov     [rsp+78h+var_48], rsi
0x180052705  mov     r9, rax
0x180052708  lea     rax, aRemovelogonpub; "RemoveLogonPublicCacheForUser"
0x18005270f  mov     [rsp+78h+var_50], rax
0x180052714  mov     dword ptr [rsp+78h+var_58], 2174h
0x18005271c  mov     rdx, rdi
0x18005271f  xor     ecx, ecx
0x180052721  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180052726  mov     byte ptr [rbp+arg_0], 1
0x18005272a  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180052731  call    cs:__imp_RtlReleaseResource
0x180052737  lea     rax, [rbp+var_20]
0x18005273b  xor     r9d, r9d; int
0x18005273e  lea     rdx, [r13+44h]; struct _GUID *
0x180052742  mov     [rsp+78h+var_58], rax; struct _USER_CACHE_ENTRY **
0x180052747  mov     r8, r15; unsigned __int16 *
0x18005274a  xor     ecx, ecx; int
0x18005274c  call    ?_CreateOrAcquireUserCacheEntry@@YAJHPEAU_GUID@@PEBGHPEAPEAU_USER_CACHE_ENTRY@@@Z; _CreateOrAcquireUserCacheEntry(int,_GUID *,ushort const *,int,_USER_CACHE_ENTRY * *)
0x180052751  mov     ebx, eax
0x180052753  test    eax, eax
0x180052755  jz      short loc_180052791
0x180052757  mov     rcx, r14; char *
0x18005275a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005275f  mov     r9, rax
0x180052762  mov     [rsp+78h+var_48], rsi
0x180052767  lea     rax, aCreateoracquir_3; "CreateOrAcquireUserCacheEntry"
0x18005276e  mov     r8d, ebx
0x180052771  mov     [rsp+78h+var_50], rax
0x180052776  mov     rdx, rdi
0x180052779  xor     ecx, ecx
0x18005277b  mov     dword ptr [rsp+78h+var_58], 2184h
0x180052783  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180052788  mov     r12, [rbp+var_20]
0x18005278c  jmp     loc_180052841
0x180052791  mov     r12, [rbp+var_20]
0x180052795  mov     dl, 1; bool
0x180052797  mov     rcx, r12; struct _USER_CACHE_ENTRY *
0x18005279a  call    ?LockAndUnProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@_N@Z; LockAndUnProtectUserCacheEntry(_USER_CACHE_ENTRY *,bool)
0x18005279f  xor     r8d, r8d; bool *
0x1800527a2  xor     edx, edx; struct _CloudAPCache *
0x1800527a4  mov     rcx, r12; struct _USER_CACHE_ENTRY *
0x1800527a7  call    ?UnprovisionTBAL@@YAJPEAU_USER_CACHE_ENTRY@@PEAU_CloudAPCache@@PEA_N@Z; UnprovisionTBAL(_USER_CACHE_ENTRY *,_CloudAPCache *,bool *)
0x1800527ac  mov     r8d, eax
0x1800527af  test    eax, eax
0x1800527b1  jns     short loc_1800527E5
0x1800527b3  mov     rcx, r14; char *
0x1800527b6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800527bb  mov     r9, rax
0x1800527be  mov     [rsp+78h+var_48], rsi
0x1800527c3  lea     rax, aUnprovisiontba; "UnprovisionTBAL"
0x1800527ca  mov     rdx, rdi
0x1800527cd  mov     [rsp+78h+var_50], rax
0x1800527d2  xor     ecx, ecx
0x1800527d4  mov     dword ptr [rsp+78h+var_58], 2192h
0x1800527dc  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800527e1  mov     al, 1
0x1800527e3  jmp     short loc_1800527E8
0x1800527e5  mov     al, byte ptr [rbp+arg_0]
0x1800527e8  neg     al
0x1800527ea  mov     rcx, r12; struct _USER_CACHE_ENTRY *
0x1800527ed  sbb     ebx, ebx
0x1800527ef  and     ebx, 0C0000001h
0x1800527f5  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x1800527fa  jmp     short loc_180052841
0x1800527fc  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180052803  mov     ebx, 0C000000Dh
0x180052808  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005280d  mov     r9, rax
0x180052810  lea     rsi, Class
0x180052817  lea     rax, aInvalidargS; "InvalidArg(s)"
0x18005281e  mov     [rsp+78h+var_48], rsi
0x180052823  mov     [rsp+78h+var_50], rax
  ... truncated ...
```
