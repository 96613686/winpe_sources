# GetLogonCache(_ApPluginPkg *,_USER_CACHE_ENTRY *,_DPAPI_DECODED_AUTH_DATA *,_CloudAPCache * *,bool *)

- ea: `0x18000f700`
- end: `0x18000fb5c`
- name: `?GetLogonCache@@YAJPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@PEAU_DPAPI_DECODED_AUTH_DATA@@PEAPEAU_CloudAPCache@@PEA_N@Z`
- size: `1116`
- prototype: `__int64 __fastcall(const unsigned __int16 **, struct _USER_CACHE_ENTRY *, struct _DPAPI_DECODED_AUTH_DATA *, HLOCAL *, bool *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180018a20`
- `0x180037240`

## callees

- `0x180007fc0`
- `0x180009a10`
- `0x18000a600`
- `0x18000f700`
- `0x18000fb70`
- `0x18000fd50`
- `0x1800156f0`
- `0x180042410`
- `0x180055eb0`
- `0x18005f95c`
- `0x180081010`

## string_xrefs

- `0x18000f774`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000f7ef`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000f851`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000f8e0`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000f97d`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000f9d3`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000fa20`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000fa76`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000fb28`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000f75c`: `CacheData`
- `0x18000f8a2`: `CacheData`
- `0x18000f79b`: `GetLogonCacheForUser`
- `0x18000fb43`: `GetLogonCacheForUser`
- `0x18000fa3b`: `MigrateLiveSSPCache`

## pseudocode

```c
__int64 __fastcall GetLogonCache(
        const unsigned __int16 **a1,
        struct _USER_CACHE_ENTRY *a2,
        struct _DPAPI_DECODED_AUTH_DATA *a3,
        HLOCAL *a4,
        bool *a5)
{
  const unsigned __int16 *v9; // rdi
  int LogonCacheForUser; // ebx
  const char *v11; // rax
  const unsigned __int16 *v12; // rcx
  const char *v13; // rax
  const char *v14; // r9
  const char *v15; // rax
  const char *v16; // rax
  const char *v17; // r9
  const char *v18; // rax
  const char *v19; // r9
  const char *v21; // r9
  int v22; // [rsp+20h] [rbp-E0h]
  struct _CloudAPCache **v23; // [rsp+20h] [rbp-E0h]
  struct _CloudAPCache **v24; // [rsp+20h] [rbp-E0h]
  struct _CloudAPCache **v25; // [rsp+20h] [rbp-E0h]
  struct _CloudAPCache **v26; // [rsp+20h] [rbp-E0h]
  struct _CloudAPCache **v27; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  struct _CloudAPCacheNodeData2 *v29; // [rsp+48h] [rbp-B8h] BYREF
  PUCHAR pbInput; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v31; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v32[72]; // [rsp+60h] [rbp-A0h] BYREF

  LODWORD(v29) = 0;
  v31 = 0;
  hMem = 0;
  pbInput = 0;
  v9 = 0;
  LogonCacheForUser = _GetLogonCacheForUser(
                        a1[43],
                        (const unsigned __int16 *)a2 + 52,
                        L"CacheData",
                        (struct _CloudAPCache **)&hMem);
  if ( LogonCacheForUser >= 0 )
    goto LABEL_26;
  v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
  v22 = 2397;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)LogonCacheForUser, v11, v22, "GetLogonCacheForUser", &Class);
  if ( (g_ulTestFlags & 2) == 0 )
  {
    v12 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
    if ( v12 )
    {
      if ( *v12 )
      {
        LogonCacheForUser = DuplicateStringPreRS2(v12, 1, (unsigned __int16 **)&pbInput);
        if ( LogonCacheForUser )
        {
          v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v23) = 2412;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            (unsigned int)LogonCacheForUser,
            v13,
            v23,
            "DuplicateStringPreRS2",
            &Class);
          v9 = (const unsigned __int16 *)pbInput;
          goto LABEL_27;
        }
        v9 = (const unsigned __int16 *)pbInput;
        LogonCacheForUser = GetHashStringPreRS2(pbInput, v32);
        if ( LogonCacheForUser )
        {
          v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v23) = 2416;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            (unsigned int)LogonCacheForUser,
            v14,
            v23,
            "GetHashStringPreRS2",
            &Class);
          goto LABEL_27;
        }
        LogonCacheForUser = _GetLogonCacheForUser(a1[43], v32, L"CacheData", (struct _CloudAPCache **)&hMem);
        if ( LogonCacheForUser >= 0 )
        {
          LogonCacheForUser = PerformMigrationFromPreRS2((struct _ApPluginPkg *)a1, a2, v9, v32);
          if ( LogonCacheForUser >= 0 )
            goto LABEL_26;
          FreeCloudAPCache(hMem);
          hMem = 0;
          v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v23) = 2434;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            (unsigned int)LogonCacheForUser,
            v15,
            v23,
            "PerformMigrationFromPreRS2",
            &Class);
        }
      }
    }
  }
  if ( ((_BYTE)a1[20] & 1) != 0 && *(_DWORD *)a3 == 1 )
  {
    LogonCacheForUser = (*((__int64 (__fastcall **)(const unsigned __int16 *, _QWORD, _QWORD, __int64, unsigned __int8 **))g_pLsaIdProvHostFunctionTable
                         + 4))(
                          a1[2],
                          *((_QWORD *)a2 + 12),
                          0,
                          3,
                          &v31);
    if ( LogonCacheForUser < 0 )
    {
      v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v24) = 2459;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)LogonCacheForUser, v16, v24, "LookUpUserInfo", &Class);
      if ( LogonCacheForUser != -1073741801 && LogonCacheForUser != -1073741670 )
        LogonCacheForUser = -1073741718;
      v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v25) = 2466;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)LogonCacheForUser, v17, v25, "LookUpUserInfo", &Class);
      goto LABEL_27;
    }
    LogonCacheForUser = MigrateLiveSSPCache(
                          *((unsigned __int8 **)a3 + 1),
                          *((_DWORD *)a3 + 1),
                          v31,
                          (unsigned int)v29,
                          (struct _CloudAPCache **)&hMem,
                          &v29);
    if ( LogonCacheForUser < 0 )
    {
      v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v26) = 2479;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)LogonCacheForUser, v18, v26, "MigrateLiveSSPCache", &Class);
      if ( LogonCacheForUser != -1073741801 && LogonCacheForUser != -1073741670 )
        LogonCacheForUser = -1073741718;
      v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v27) = 2486;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)LogonCacheForUser, v19, v27, "MigrateLiveSSPCache", &Class);
      goto LABEL_27;
    }
    *a5 = 1;
LABEL_26:
    LogonCacheForUser = 0;
    *a4 = hMem;
    hMem = 0;
    goto LABEL_27;
  }
  if ( LogonCacheForUser != -1073741801 && LogonCacheForUser != -1073741670 )
    LogonCacheForUser = -1073741718;
  v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
  LODWORD(v23) = 2500;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)LogonCacheForUser, v21, v23, "GetLogonCacheForUser", &Class);
LABEL_27:
  FreeCloudAPCache(hMem);
  if ( v31 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v9 )
    ((void (__fastcall *)(const unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v9);
  return (unsigned int)LogonCacheForUser;
}

```

## disassembly

```asm
0x18000f700  push    rbp
0x18000f702  push    rbx
0x18000f703  push    rsi
0x18000f704  push    rdi
0x18000f705  push    r12
0x18000f707  push    r13
0x18000f709  push    r14
0x18000f70b  push    r15
0x18000f70d  lea     rbp, [rsp-8]
0x18000f712  sub     rsp, 108h
0x18000f719  mov     rax, cs:__security_cookie
0x18000f720  xor     rax, rsp
0x18000f723  mov     [rbp+40h+var_50], rax
0x18000f727  mov     r12, [rbp+40h+arg_20]
0x18000f72b  xor     eax, eax
0x18000f72d  mov     rsi, r9
0x18000f730  mov     dword ptr [rsp+140h+var_F8], eax
0x18000f734  mov     r13, r8
0x18000f737  mov     [rsp+140h+var_E8], rax
0x18000f73c  mov     r15, rdx
0x18000f73f  mov     [rsp+140h+hMem], rax
0x18000f744  mov     r14, rcx
0x18000f747  mov     [rsp+140h+pbInput], rax
0x18000f74c  mov     rcx, [rcx+158h]; unsigned __int16 *
0x18000f753  lea     r9, [rsp+140h+hMem]; struct _CloudAPCache **
0x18000f758  add     rdx, 68h ; 'h'; unsigned __int16 *
0x18000f75c  lea     r8, aCachedata; "CacheData"
0x18000f763  mov     edi, eax
0x18000f765  call    ?_GetLogonCacheForUser@@YAJPEBG00PEAPEAU_CloudAPCache@@@Z; _GetLogonCacheForUser(ushort const *,ushort const *,ushort const *,_CloudAPCache * *)
0x18000f76a  mov     ebx, eax
0x18000f76c  test    eax, eax
0x18000f76e  jns     loc_18000FAA1
0x18000f774  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000f77b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000f780  mov     r9, rax
0x18000f783  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000f78a  lea     rax, Class
0x18000f791  mov     r8d, ebx
0x18000f794  mov     [rsp+140h+var_110], rax
0x18000f799  xor     ecx, ecx
0x18000f79b  lea     rax, aGetlogoncachef; "GetLogonCacheForUser"
0x18000f7a2  mov     [rsp+140h+var_118], rax
0x18000f7a7  mov     dword ptr [rsp+140h+var_120], 95Dh
0x18000f7af  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000f7b4  mov     eax, cs:?g_ulTestFlags@@3KA; ulong g_ulTestFlags
0x18000f7ba  test    al, 2
0x18000f7bc  jnz     loc_18000F929
0x18000f7c2  mov     rcx, [r15+58h]; Src
0x18000f7c6  test    rcx, rcx
0x18000f7c9  jz      loc_18000F929
0x18000f7cf  xor     eax, eax
0x18000f7d1  cmp     ax, [rcx]
0x18000f7d4  jz      loc_18000F929
0x18000f7da  lea     r8, [rsp+140h+pbInput]; unsigned __int16 **
0x18000f7df  mov     edx, 1; int
0x18000f7e4  call    ?DuplicateStringPreRS2@@YAJPEBGHPEAPEAG@Z; DuplicateStringPreRS2(ushort const *,int,ushort * *)
0x18000f7e9  mov     ebx, eax
0x18000f7eb  test    eax, eax
0x18000f7ed  jz      short loc_18000F839
0x18000f7ef  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000f7f6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000f7fb  mov     r9, rax
0x18000f7fe  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000f805  lea     rax, Class
0x18000f80c  mov     r8d, ebx
0x18000f80f  mov     [rsp+140h+var_110], rax
0x18000f814  xor     ecx, ecx
0x18000f816  lea     rax, aDuplicatestrin_0; "DuplicateStringPreRS2"
0x18000f81d  mov     [rsp+140h+var_118], rax
0x18000f822  mov     dword ptr [rsp+140h+var_120], 96Ch
0x18000f82a  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000f82f  mov     rdi, [rsp+140h+pbInput]
0x18000f834  jmp     loc_18000FAB4
0x18000f839  mov     rdi, [rsp+140h+pbInput]
0x18000f83e  lea     rdx, [rsp+140h+var_E0]; unsigned __int16 *
0x18000f843  mov     rcx, rdi; pbInput
0x18000f846  call    ?GetHashStringPreRS2@@YAJPEBGQEAG@Z; GetHashStringPreRS2(ushort const *,ushort * const)
0x18000f84b  mov     ebx, eax
0x18000f84d  test    eax, eax
0x18000f84f  jz      short loc_18000F896
0x18000f851  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000f858  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000f85d  mov     r9, rax
0x18000f860  lea     rax, Class
0x18000f867  mov     [rsp+140h+var_110], rax
0x18000f86c  lea     rax, aGethashstringp; "GetHashStringPreRS2"
0x18000f873  mov     [rsp+140h+var_118], rax
0x18000f878  mov     dword ptr [rsp+140h+var_120], 970h
0x18000f880  mov     r8d, ebx
0x18000f883  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000f88a  xor     ecx, ecx
0x18000f88c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000f891  jmp     loc_18000FAB4
0x18000f896  mov     rcx, [r14+158h]; unsigned __int16 *
0x18000f89d  lea     r9, [rsp+140h+hMem]; struct _CloudAPCache **
0x18000f8a2  lea     r8, aCachedata; "CacheData"
0x18000f8a9  lea     rdx, [rsp+140h+var_E0]; unsigned __int16 *
0x18000f8ae  call    ?_GetLogonCacheForUser@@YAJPEBG00PEAPEAU_CloudAPCache@@@Z; _GetLogonCacheForUser(ushort const *,ushort const *,ushort const *,_CloudAPCache * *)
0x18000f8b3  mov     ebx, eax
0x18000f8b5  test    eax, eax
0x18000f8b7  js      short loc_18000F929
0x18000f8b9  lea     r9, [rsp+140h+var_E0]; unsigned __int16 *
0x18000f8be  mov     r8, rdi; unsigned __int16 *
0x18000f8c1  mov     rdx, r15; struct _USER_CACHE_ENTRY *
0x18000f8c4  mov     rcx, r14; struct _ApPluginPkg *
0x18000f8c7  call    ?PerformMigrationFromPreRS2@@YAJPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@PEBG2@Z; PerformMigrationFromPreRS2(_ApPluginPkg *,_USER_CACHE_ENTRY *,ushort const *,ushort const *)
0x18000f8cc  mov     ebx, eax
0x18000f8ce  test    eax, eax
0x18000f8d0  jns     loc_18000FAA1
0x18000f8d6  mov     rcx, [rsp+140h+hMem]; hMem
0x18000f8db  call    ?FreeCloudAPCache@@YAXPEAU_CloudAPCache@@@Z; FreeCloudAPCache(_CloudAPCache *)
0x18000f8e0  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000f8e7  mov     [rsp+140h+hMem], 0
0x18000f8f0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000f8f5  mov     r9, rax
0x18000f8f8  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000f8ff  lea     rax, Class
0x18000f906  mov     r8d, ebx
0x18000f909  mov     [rsp+140h+var_110], rax
0x18000f90e  xor     ecx, ecx
0x18000f910  lea     rax, aPerformmigrati; "PerformMigrationFromPreRS2"
0x18000f917  mov     [rsp+140h+var_118], rax
0x18000f91c  mov     dword ptr [rsp+140h+var_120], 982h
0x18000f924  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000f929  test    byte ptr [r14+0A0h], 1
0x18000f931  jz      loc_18000FB12
0x18000f937  cmp     dword ptr [r13+0], 1
0x18000f93c  jnz     loc_18000FB12
0x18000f942  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x18000f949  lea     r8, [rsp+140h+var_F8]
0x18000f94e  mov     rdx, [r15+60h]
0x18000f952  mov     r9d, 3
0x18000f958  mov     rcx, [r14+10h]
0x18000f95c  mov     [rsp+140h+var_118], r8; struct _CloudAPCacheNodeData2 **
0x18000f961  lea     r8, [rsp+140h+var_E8]
0x18000f966  mov     rax, [rax+20h]
0x18000f96a  mov     [rsp+140h+var_120], r8
0x18000f96f  xor     r8d, r8d
0x18000f972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f977  mov     ebx, eax
0x18000f979  test    eax, eax
0x18000f97b  jns     short loc_18000F9F9
0x18000f97d  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000f984  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000f989  lea     rsi, Class
0x18000f990  mov     r9, rax
0x18000f993  mov     [rsp+140h+var_110], rsi
0x18000f998  lea     r14, aLookupuserinfo; "LookUpUserInfo"
0x18000f99f  mov     [rsp+140h+var_118], r14
0x18000f9a4  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000f9ab  mov     r8d, ebx
0x18000f9ae  mov     dword ptr [rsp+140h+var_120], 99Bh
0x18000f9b6  xor     ecx, ecx
0x18000f9b8  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000f9bd  cmp     ebx, 0C0000017h
0x18000f9c3  jz      short loc_18000F9D3
0x18000f9c5  cmp     ebx, 0C000009Ah
0x18000f9cb  mov     eax, 0C000006Ah
0x18000f9d0  cmovnz  ebx, eax
0x18000f9d3  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000f9da  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000f9df  mov     [rsp+140h+var_110], rsi
0x18000f9e4  mov     r9, rax
0x18000f9e7  mov     [rsp+140h+var_118], r14
0x18000f9ec  mov     dword ptr [rsp+140h+var_120], 9A2h
0x18000f9f4  jmp     loc_18000F880
0x18000f9f9  mov     r9d, dword ptr [rsp+140h+var_F8]; unsigned int
0x18000f9fe  lea     rax, [rsp+140h+hMem]
0x18000fa03  mov     r8, [rsp+140h+var_E8]; unsigned __int8 *
0x18000fa08  mov     edx, [r13+4]; unsigned int
0x18000fa0c  mov     rcx, [r13+8]; unsigned __int8 *
0x18000fa10  mov     [rsp+140h+var_120], rax; struct _CloudAPCache **
0x18000fa15  call    ?MigrateLiveSSPCache@@YAJPEAEK0KPEAPEAU_CloudAPCache@@PEAPEAU_CloudAPCacheNodeData2@@@Z; MigrateLiveSSPCache(uchar *,ulong,uchar *,ulong,_CloudAPCache * *,_CloudAPCacheNodeData2 * *)
0x18000fa1a  mov     ebx, eax
0x18000fa1c  test    eax, eax
0x18000fa1e  jns     short loc_18000FA9C
0x18000fa20  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000fa27  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000fa2c  lea     rsi, Class
0x18000fa33  mov     r9, rax
0x18000fa36  mov     [rsp+140h+var_110], rsi
0x18000fa3b  lea     r14, aMigratelivessp; "MigrateLiveSSPCache"
0x18000fa42  mov     [rsp+140h+var_118], r14
0x18000fa47  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000fa4e  mov     r8d, ebx
0x18000fa51  mov     dword ptr [rsp+140h+var_120], 9AFh
0x18000fa59  xor     ecx, ecx
0x18000fa5b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000fa60  cmp     ebx, 0C0000017h
0x18000fa66  jz      short loc_18000FA76
0x18000fa68  cmp     ebx, 0C000009Ah
0x18000fa6e  mov     eax, 0C000006Ah
0x18000fa73  cmovnz  ebx, eax
0x18000fa76  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000fa7d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000fa82  mov     [rsp+140h+var_110], rsi
0x18000fa87  mov     r9, rax
0x18000fa8a  mov     [rsp+140h+var_118], r14
0x18000fa8f  mov     dword ptr [rsp+140h+var_120], 9B6h
0x18000fa97  jmp     loc_18000F880
0x18000fa9c  mov     byte ptr [r12], 1
0x18000faa1  mov     rax, [rsp+140h+hMem]
0x18000faa6  xor     ebx, ebx
0x18000faa8  mov     [rsi], rax
0x18000faab  mov     [rsp+140h+hMem], 0
0x18000fab4  mov     rcx, [rsp+140h+hMem]; hMem
0x18000fab9  call    ?FreeCloudAPCache@@YAXPEAU_CloudAPCache@@@Z; FreeCloudAPCache(_CloudAPCache *)
0x18000fabe  mov     rcx, [rsp+140h+var_E8]
0x18000fac3  test    rcx, rcx
0x18000fac6  jz      short loc_18000FAD8
0x18000fac8  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000facf  mov     rax, [rax+30h]
0x18000fad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fad8  test    rdi, rdi
0x18000fadb  jz      short loc_18000FAF0
0x18000fadd  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000fae4  mov     rcx, rdi
0x18000fae7  mov     rax, [rax+30h]
0x18000faeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faf0  mov     eax, ebx
0x18000faf2  mov     rcx, [rbp+40h+var_50]
0x18000faf6  xor     rcx, rsp; StackCookie
0x18000faf9  call    __security_check_cookie
0x18000fafe  add     rsp, 108h
0x18000fb05  pop     r15
0x18000fb07  pop     r14
0x18000fb09  pop     r13
0x18000fb0b  pop     r12
0x18000fb0d  pop     rdi
0x18000fb0e  pop     rsi
0x18000fb0f  pop     rbx
0x18000fb10  pop     rbp
0x18000fb11  retn
0x18000fb12  cmp     ebx, 0C0000017h
0x18000fb18  jz      short loc_18000FB28
0x18000fb1a  cmp     ebx, 0C000009Ah
0x18000fb20  mov     eax, 0C000006Ah
0x18000fb25  cmovnz  ebx, eax
0x18000fb28  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000fb2f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000fb34  mov     r9, rax
0x18000fb37  lea     rax, Class
0x18000fb3e  mov     [rsp+140h+var_110], rax
0x18000fb43  lea     rax, aGetlogoncachef; "GetLogonCacheForUser"
0x18000fb4a  mov     [rsp+140h+var_118], rax
0x18000fb4f  mov     dword ptr [rsp+140h+var_120], 9C4h
0x18000fb57  jmp     loc_18000F880
```
