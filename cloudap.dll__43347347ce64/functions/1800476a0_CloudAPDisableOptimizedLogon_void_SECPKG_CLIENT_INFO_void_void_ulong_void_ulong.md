# CloudAPDisableOptimizedLogon(void * *,_SECPKG_CLIENT_INFO *,void *,void *,ulong,void * *,ulong *)

- ea: `0x1800476a0`
- end: `0x1800479e3`
- name: `?CloudAPDisableOptimizedLogon@@YAJPEAPEAXPEAU_SECPKG_CLIENT_INFO@@PEAX2K0PEAK@Z`
- size: `835`
- prototype: `__int64 __fastcall(void **, struct _SECPKG_CLIENT_INFO *, char *, void *, unsigned int, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x180007ef0`
- `0x180007fc0`
- `0x180009bf0`
- `0x18000a600`
- `0x18000c450`
- `0x18000e7e0`
- `0x18000e900`
- `0x18000ed04`
- `0x18000ee60`
- `0x18000fb70`
- `0x18000fd50`
- `0x180010320`
- `0x1800476a0`
- `0x18005fc44`

## string_xrefs

- `0x1800476e4`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180047753`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800477b6`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180047816`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004787f`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800478e6`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180047937`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180047977`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180047831`: `CheckPkgSID`
- `0x180047864`: `CacheData`
- `0x18004791e`: `CacheData`
- `0x18004789a`: `GetLogonCacheForUser`
- `0x180047952`: `SaveLogonCacheForUser`
- `0x180047901`: `EnableCacheNodeFlags`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudAPDisableOptimizedLogon(
        void **a1,
        struct _SECPKG_CLIENT_INFO *a2,
        char *a3,
        void *a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7)
{
  struct _ApPluginPkg *v7; // rsi
  struct _CloudAPCache *v8; // r14
  struct _LOGON_SESSION *v9; // rbp
  struct _SECPKG_CLIENT_INFO *v10; // rdi
  unsigned int updated; // ebx
  const char *v12; // r9
  const char *v13; // rax
  const char *v14; // rax
  const char *v15; // r9
  __int64 v16; // rdi
  unsigned int LogonCacheForUser; // eax
  const char *v18; // r9
  const char *v19; // r9
  const char *v20; // r9
  const char *v21; // r9
  unsigned int v23; // [rsp+20h] [rbp-78h]
  __int64 v24; // [rsp+20h] [rbp-78h]
  struct _LOGON_SESSION *v25; // [rsp+40h] [rbp-58h] BYREF
  struct _ApPluginPkg *v26; // [rsp+48h] [rbp-50h] BYREF
  struct _CloudAPCache *v27; // [rsp+50h] [rbp-48h] BYREF

  v7 = 0;
  v8 = 0;
  v26 = 0;
  v9 = 0;
  v27 = 0;
  v10 = a2;
  v25 = 0;
  *a6 = 0;
  *a7 = 0;
  if ( g_ulPlatformId == 3 )
  {
    if ( a5 >= 0xC && a3 )
    {
      if ( a2->HasTcbPrivilege )
        a2 = (struct _SECPKG_CLIENT_INFO *)(a3 + 4);
      updated = _AcquireLogonSession(1, &a2->LogonId, &v25);
      if ( updated )
      {
        v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v13, 3866, "AcquireLogonSession", &Class);
        v9 = v25;
      }
      else
      {
        v9 = v25;
        updated = RefPackage((struct _GUID *)((char *)v25 + 36), &v26);
        if ( updated )
        {
          v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v14, 3871, "RefPackage", &Class);
          v7 = v26;
        }
        else
        {
          v7 = v26;
          updated = CheckPkgSID(v10, v26);
          if ( updated )
          {
            v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v15, 3875, "CheckPkgSID", &Class);
          }
          else
          {
            v16 = *((_QWORD *)v9 + 7);
            LockAndUnProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v16, 0);
            LogonCacheForUser = _GetLogonCacheForUser(
                                  *((const unsigned __int16 **)v7 + 43),
                                  (const unsigned __int16 *)(v16 + 104),
                                  L"CacheData",
                                  &v27);
            v8 = v27;
            updated = LogonCacheForUser;
            if ( LogonCacheForUser )
            {
              v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v18, 3885, "GetLogonCacheForUser", &Class);
            }
            else
            {
              updated = UpdateCacheNodeFlags(
                          v27,
                          (struct _tagCacheNodeIdentifier *)(v16 + 296),
                          *(struct _CREDENTIAL_KEY **)(v16 + 264),
                          2u,
                          v23);
              if ( updated )
              {
                v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                LODWORD(v24) = 3892;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v19, v24, "EnableCacheNodeFlags", &Class);
              }
              else
              {
                updated = _SaveLogonCacheForUser(
                            *((const unsigned __int16 **)v7 + 43),
                            (const unsigned __int16 *)(v16 + 104),
                            L"CacheData",
                            v8);
                if ( updated )
                {
                  v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                  LODWORD(v24) = 3898;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v20, v24, "SaveLogonCacheForUser", &Class);
                }
                else
                {
                  updated = 0;
                }
              }
            }
            UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v16);
          }
        }
      }
    }
    else
    {
      updated = -1073741811;
      v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v21, 3851, "Invalid Arg(s)", &Class);
    }
  }
  else
  {
    updated = -1073741637;
    v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%ws",
      3221225659LL,
      v12,
      3844,
      "optimized logon can only be disabled for desktop SKUs",
      &Class);
  }
  DerefPackage(v7);
  ReleaseLogonSession(v9);
  FreeCloudAPCache(v8);
  return updated;
}

```

## disassembly

```asm
0x1800476a0  push    rbx
0x1800476a2  push    rbp
0x1800476a3  push    rsi
0x1800476a4  push    rdi
0x1800476a5  push    r14
0x1800476a7  push    r15
0x1800476a9  sub     rsp, 68h
0x1800476ad  mov     rax, [rsp+98h+arg_28]
0x1800476b5  xor     esi, esi
0x1800476b7  xor     r14d, r14d
0x1800476ba  mov     [rsp+98h+var_50], rsi
0x1800476bf  xor     ebp, ebp
0x1800476c1  mov     [rsp+98h+var_48], r14
0x1800476c6  mov     rdi, rdx
0x1800476c9  mov     [rsp+98h+var_58], rbp
0x1800476ce  mov     [rax], rsi
0x1800476d1  mov     rax, [rsp+98h+arg_30]
0x1800476d9  mov     [rax], esi
0x1800476db  cmp     cs:?g_ulPlatformId@@3KA, 3; ulong g_ulPlatformId
0x1800476e2  jz      short loc_18004771D
0x1800476e4  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800476eb  mov     ebx, 0C00000BBh
0x1800476f0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800476f5  mov     r9, rax
0x1800476f8  lea     rax, Class
0x1800476ff  mov     [rsp+98h+var_68], rax
0x180047704  lea     rax, aOptimizedLogon; "optimized logon can only be disabled fo"...
0x18004770b  mov     [rsp+98h+var_70], rax
0x180047710  mov     dword ptr [rsp+98h+var_78], 0F04h
0x180047718  jmp     loc_1800479AB
0x18004771d  cmp     [rsp+98h+arg_20], 0Ch
0x180047725  jb      loc_180047977
0x18004772b  test    r8, r8
0x18004772e  jz      loc_180047977
0x180047734  cmp     [rdx+10h], sil
0x180047738  jz      short loc_18004773E
0x18004773a  lea     rdx, [r8+4]; struct _LUID *
0x18004773e  lea     r8, [rsp+98h+var_58]; struct _LOGON_SESSION **
0x180047743  mov     ecx, 1; int
0x180047748  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x18004774d  mov     ebx, eax
0x18004774f  test    eax, eax
0x180047751  jz      short loc_18004779D
0x180047753  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004775a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004775f  mov     r9, rax
0x180047762  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180047769  lea     rax, Class
0x180047770  mov     r8d, ebx
0x180047773  mov     [rsp+98h+var_68], rax
0x180047778  xor     ecx, ecx
0x18004777a  lea     rax, aAcquirelogonse_0; "AcquireLogonSession"
0x180047781  mov     [rsp+98h+var_70], rax
0x180047786  mov     dword ptr [rsp+98h+var_78], 0F1Ah
0x18004778e  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180047793  mov     rbp, [rsp+98h+var_58]
0x180047798  jmp     loc_1800479BC
0x18004779d  mov     rbp, [rsp+98h+var_58]
0x1800477a2  lea     rdx, [rsp+98h+var_50]; struct _ApPluginPkg **
0x1800477a7  lea     rcx, [rbp+24h]; struct _GUID *
0x1800477ab  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x1800477b0  mov     ebx, eax
0x1800477b2  test    eax, eax
0x1800477b4  jz      short loc_180047800
0x1800477b6  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800477bd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800477c2  mov     r9, rax
0x1800477c5  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800477cc  lea     rax, Class
0x1800477d3  mov     r8d, ebx
0x1800477d6  mov     [rsp+98h+var_68], rax
0x1800477db  xor     ecx, ecx
0x1800477dd  lea     rax, aRefpackage; "RefPackage"
0x1800477e4  mov     [rsp+98h+var_70], rax
0x1800477e9  mov     dword ptr [rsp+98h+var_78], 0F1Fh
0x1800477f1  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800477f6  mov     rsi, [rsp+98h+var_50]
0x1800477fb  jmp     loc_1800479BC
0x180047800  mov     rsi, [rsp+98h+var_50]
0x180047805  mov     rcx, rdi; struct _SECPKG_CLIENT_INFO *
0x180047808  mov     rdx, rsi; struct _ApPluginPkg *
0x18004780b  call    ?CheckPkgSID@@YAJPEAU_SECPKG_CLIENT_INFO@@PEAU_ApPluginPkg@@@Z; CheckPkgSID(_SECPKG_CLIENT_INFO *,_ApPluginPkg *)
0x180047810  mov     ebx, eax
0x180047812  test    eax, eax
0x180047814  jz      short loc_18004784A
0x180047816  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004781d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180047822  mov     r9, rax
0x180047825  lea     rax, Class
0x18004782c  mov     [rsp+98h+var_68], rax
0x180047831  lea     rax, aCheckpkgsid; "CheckPkgSID"
0x180047838  mov     [rsp+98h+var_70], rax
0x18004783d  mov     dword ptr [rsp+98h+var_78], 0F23h
0x180047845  jmp     loc_1800479AB
0x18004784a  mov     rdi, [rbp+38h]
0x18004784e  xor     edx, edx; bool
0x180047850  mov     rcx, rdi; struct _USER_CACHE_ENTRY *
0x180047853  call    ?LockAndUnProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@_N@Z; LockAndUnProtectUserCacheEntry(_USER_CACHE_ENTRY *,bool)
0x180047858  mov     rcx, [rsi+158h]; unsigned __int16 *
0x18004785f  lea     r9, [rsp+98h+var_48]; struct _CloudAPCache **
0x180047864  lea     r8, aCachedata; "CacheData"
0x18004786b  lea     rdx, [rdi+68h]; unsigned __int16 *
0x18004786f  call    ?_GetLogonCacheForUser@@YAJPEBG00PEAPEAU_CloudAPCache@@@Z; _GetLogonCacheForUser(ushort const *,ushort const *,ushort const *,_CloudAPCache * *)
0x180047874  mov     r14, [rsp+98h+var_48]
0x180047879  mov     ebx, eax
0x18004787b  test    eax, eax
0x18004787d  jz      short loc_1800478C4
0x18004787f  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180047886  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004788b  mov     r9, rax
0x18004788e  lea     rax, Class
0x180047895  mov     [rsp+98h+var_68], rax
0x18004789a  lea     rax, aGetlogoncachef; "GetLogonCacheForUser"
0x1800478a1  mov     [rsp+98h+var_70], rax
0x1800478a6  mov     dword ptr [rsp+98h+var_78], 0F2Dh
0x1800478ae  mov     r8d, ebx
0x1800478b1  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800478b8  xor     ecx, ecx
0x1800478ba  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800478bf  jmp     loc_18004796D
0x1800478c4  mov     r8, [rdi+108h]; struct _CREDENTIAL_KEY *
0x1800478cb  lea     rdx, [rdi+128h]; struct _tagCacheNodeIdentifier *
0x1800478d2  mov     r9d, 2; unsigned int
0x1800478d8  mov     rcx, r14; struct _CloudAPCache *
0x1800478db  call    ?UpdateCacheNodeFlags@@YAJPEAU_CloudAPCache@@PEAU_tagCacheNodeIdentifier@@PEAU_CREDENTIAL_KEY@@KK@Z; UpdateCacheNodeFlags(_CloudAPCache *,_tagCacheNodeIdentifier *,_CREDENTIAL_KEY *,ulong,ulong)
0x1800478e0  mov     ebx, eax
0x1800478e2  test    eax, eax
0x1800478e4  jz      short loc_180047917
0x1800478e6  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800478ed  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800478f2  mov     r9, rax
0x1800478f5  lea     rax, Class
0x1800478fc  mov     [rsp+98h+var_68], rax
0x180047901  lea     rax, aEnablecachenod; "EnableCacheNodeFlags"
0x180047908  mov     [rsp+98h+var_70], rax
0x18004790d  mov     dword ptr [rsp+98h+var_78], 0F34h
0x180047915  jmp     short loc_1800478AE
0x180047917  mov     rcx, [rsi+158h]; unsigned __int16 *
0x18004791e  lea     r8, aCachedata; "CacheData"
0x180047925  mov     r9, r14; struct _CloudAPCache *
0x180047928  lea     rdx, [rdi+68h]; unsigned __int16 *
0x18004792c  call    ?_SaveLogonCacheForUser@@YAJPEBG00PEAU_CloudAPCache@@@Z; _SaveLogonCacheForUser(ushort const *,ushort const *,ushort const *,_CloudAPCache *)
0x180047931  mov     ebx, eax
0x180047933  test    eax, eax
0x180047935  jz      short loc_18004796B
0x180047937  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004793e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180047943  mov     r9, rax
0x180047946  lea     rax, Class
0x18004794d  mov     [rsp+98h+var_68], rax
0x180047952  lea     rax, aSavelogoncache; "SaveLogonCacheForUser"
0x180047959  mov     [rsp+98h+var_70], rax
0x18004795e  mov     dword ptr [rsp+98h+var_78], 0F3Ah
0x180047966  jmp     loc_1800478AE
0x18004796b  xor     ebx, ebx
0x18004796d  mov     rcx, rdi; struct _USER_CACHE_ENTRY *
0x180047970  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x180047975  jmp     short loc_1800479BC
0x180047977  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004797e  mov     ebx, 0C000000Dh
0x180047983  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180047988  mov     r9, rax
0x18004798b  lea     rax, Class
0x180047992  mov     [rsp+98h+var_68], rax
0x180047997  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x18004799e  mov     [rsp+98h+var_70], rax
0x1800479a3  mov     dword ptr [rsp+98h+var_78], 0F0Bh
0x1800479ab  mov     r8d, ebx
0x1800479ae  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800479b5  xor     ecx, ecx
0x1800479b7  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800479bc  mov     rcx, rsi; struct _ApPluginPkg *
0x1800479bf  call    ?DerefPackage@@YAXPEAU_ApPluginPkg@@@Z; DerefPackage(_ApPluginPkg *)
0x1800479c4  mov     rcx, rbp; struct _LOGON_SESSION *
0x1800479c7  call    ?ReleaseLogonSession@@YAXPEAU_LOGON_SESSION@@@Z; ReleaseLogonSession(_LOGON_SESSION *)
0x1800479cc  mov     rcx, r14; hMem
0x1800479cf  call    ?FreeCloudAPCache@@YAXPEAU_CloudAPCache@@@Z; FreeCloudAPCache(_CloudAPCache *)
0x1800479d4  mov     eax, ebx
0x1800479d6  add     rsp, 68h
0x1800479da  pop     r15
0x1800479dc  pop     r14
0x1800479de  pop     rdi
0x1800479df  pop     rsi
0x1800479e0  pop     rbp
0x1800479e1  pop     rbx
0x1800479e2  retn
```
