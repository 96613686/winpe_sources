# CloudAPGenARSOPwd(void * *,_SECPKG_CLIENT_INFO *,void *,void *,ulong,void * *,ulong *)

- ea: `0x18000e990`
- end: `0x18000ecfd`
- name: `?CloudAPGenARSOPwd@@YAJPEAPEAXPEAU_SECPKG_CLIENT_INFO@@PEAX2K0PEAK@Z`
- size: `877`
- prototype: `__int64 __fastcall(void **, struct _SECPKG_CLIENT_INFO *, char *, void *, unsigned int, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting`

## callees

- `0x180007ef0`
- `0x180007fc0`
- `0x180009bf0`
- `0x18000a600`
- `0x18000e1ec`
- `0x18000e7e0`
- `0x18000e900`
- `0x18000e990`
- `0x18000ed04`
- `0x18000ee60`
- `0x18000fb70`
- `0x18000fd50`
- `0x180010320`
- `0x180081010`

## string_xrefs

- `0x18000ea12`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000ea63`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000eac3`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000eb30`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000eb9c`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000ebf2`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000ec43`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000ec8d`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000eb82`: `CacheData`
- `0x18000ec2a`: `CacheData`
- `0x18000ebb7`: `GetLogonCacheForUser`
- `0x18000ec5e`: `SaveLogonCacheForUser`

## pseudocode

```c
__int64 __fastcall CloudAPGenARSOPwd(
        void **a1,
        struct _SECPKG_CLIENT_INFO *a2,
        char *a3,
        void *a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7)
{
  struct _LOGON_SESSION *v7; // rsi
  struct _ApPluginPkg *v8; // rdi
  struct _CloudAPCache *v9; // r15
  unsigned int v11; // ebx
  const char *v12; // r9
  const char *v13; // rax
  const char *v14; // rax
  int v15; // ecx
  const char *v16; // r9
  __int64 v17; // r13
  unsigned int LogonCacheForUser; // eax
  const char *v19; // r9
  unsigned int v20; // r8d
  unsigned __int8 *v21; // r9
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  struct _ApPluginPkg *v26; // [rsp+40h] [rbp-38h] BYREF
  struct _CloudAPCache *v27; // [rsp+48h] [rbp-30h] BYREF
  __int128 v28; // [rsp+50h] [rbp-28h] BYREF
  __int64 v29; // [rsp+60h] [rbp-18h]
  struct _LOGON_SESSION *v30; // [rsp+D0h] [rbp+58h] BYREF

  v7 = 0;
  v29 = 0;
  v8 = 0;
  v9 = 0;
  v30 = 0;
  v26 = 0;
  v27 = 0;
  *a6 = 0;
  v28 = 0;
  *a7 = 0;
  if ( a3 && a5 >= 0x14 && a5 >= *((_DWORD *)a3 + 3) + 16 )
  {
    if ( ((unsigned __int8 (__fastcall *)(__int128 *, struct _SECPKG_CLIENT_INFO *, char *, void *))g_pLsaFunctionTable->GetCallInfo)(
           &v28,
           a2,
           a3,
           a4) )
    {
      v11 = _AcquireLogonSession(1, (struct _LUID *)(a3 + 4), &v30);
      if ( v11 )
      {
        v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v13, 2775, "AcquireLogonSession", &Class);
        v7 = v30;
      }
      else
      {
        v7 = v30;
        v11 = RefPackage((struct _GUID *)((char *)v30 + 36), &v26);
        if ( v11 )
        {
          v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v14, 2780, "RefPackage", &Class);
          v8 = v26;
        }
        else
        {
          v8 = v26;
          v15 = *((_DWORD *)v26 + 40);
          if ( (v15 & 1) != 0 || (v15 & 8) != 0 && (g_ulPlatformId == 10 || g_ulPlatformId == 3) )
          {
            v17 = *((_QWORD *)v7 + 7);
            LockAndUnProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v17, 1);
            LogonCacheForUser = _GetLogonCacheForUser(
                                  *((const unsigned __int16 **)v8 + 43),
                                  (const unsigned __int16 *)(v17 + 104),
                                  L"CacheData",
                                  &v27);
            v9 = v27;
            v11 = LogonCacheForUser;
            if ( LogonCacheForUser )
            {
              v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v19, 2820, "GetLogonCacheForUser", &Class);
            }
            else
            {
              v20 = *((_DWORD *)a3 + 3);
              v21 = (unsigned __int8 *)(a3 + 16);
              if ( !v20 )
                v21 = 0;
              v11 = ProvisionTBAL((struct _USER_CACHE_ENTRY *)v17, v27, v20, v21);
              if ( v11 )
              {
                v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v22, 2830, "ProvisionTBAL", &Class);
              }
              else
              {
                v11 = _SaveLogonCacheForUser(
                        *((const unsigned __int16 **)v8 + 43),
                        (const unsigned __int16 *)(v17 + 104),
                        L"CacheData",
                        v9);
                if ( v11 )
                {
                  v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v23, 2838, "SaveLogonCacheForUser", &Class);
                }
              }
            }
            UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v17);
          }
          else
          {
            v11 = -1073741790;
            v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225506LL, v16, 2809, "ARSO not allowed", &Class);
          }
        }
      }
    }
    else
    {
      v11 = -1073741595;
      v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v12, 2769, "GetCallInfo", &Class);
    }
  }
  else
  {
    v11 = -1073741811;
    v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v24, 2763, "Invalid Arg(s)", &Class);
  }
  DerefPackage(v8);
  ReleaseLogonSession(v7);
  FreeCloudAPCache(v9);
  return v11;
}

```

## disassembly

```asm
0x18000e990  push    rbp
0x18000e992  push    rbx
0x18000e993  push    rsi
0x18000e994  push    rdi
0x18000e995  push    r12
0x18000e997  push    r13
0x18000e999  push    r14
0x18000e99b  push    r15
0x18000e99d  mov     rbp, rsp
0x18000e9a0  sub     rsp, 78h
0x18000e9a4  xor     eax, eax
0x18000e9a6  xor     esi, esi
0x18000e9a8  mov     [rbp+var_18], rax
0x18000e9ac  xor     edi, edi
0x18000e9ae  mov     rax, [rbp+arg_28]
0x18000e9b2  xor     r15d, r15d
0x18000e9b5  mov     [rbp+arg_10], rsi
0x18000e9b9  xorps   xmm0, xmm0
0x18000e9bc  mov     [rbp+var_38], rdi
0x18000e9c0  mov     r14, r8
0x18000e9c3  mov     [rbp+var_30], r15
0x18000e9c7  mov     [rax], rsi
0x18000e9ca  mov     rax, [rbp+arg_30]
0x18000e9ce  movups  [rbp+var_28], xmm0
0x18000e9d2  mov     [rax], esi
0x18000e9d4  test    r8, r8
0x18000e9d7  jz      loc_18000EC8D
0x18000e9dd  cmp     [rbp+arg_20], 14h
0x18000e9e1  jb      loc_18000EC8D
0x18000e9e7  mov     eax, [r8+0Ch]
0x18000e9eb  add     eax, 10h
0x18000e9ee  cmp     [rbp+arg_20], eax
0x18000e9f1  jb      loc_18000EC8D
0x18000e9f7  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000e9fe  lea     rcx, [rbp+var_28]
0x18000ea02  mov     rax, [rax+0C0h]
0x18000ea09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea0e  test    al, al
0x18000ea10  jnz     short loc_18000EA4B
0x18000ea12  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000ea19  mov     ebx, 0C00000E5h
0x18000ea1e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ea23  mov     r9, rax
0x18000ea26  lea     rax, Class
0x18000ea2d  mov     [rsp+78h+var_48], rax
0x18000ea32  lea     rax, aGetcallinfo; "GetCallInfo"
0x18000ea39  mov     [rsp+78h+var_50], rax
0x18000ea3e  mov     [rsp+78h+var_58], 0AD1h
0x18000ea46  jmp     loc_18000ECC1
0x18000ea4b  lea     rdx, [r14+4]; struct _LUID *
0x18000ea4f  mov     ecx, 1; int
0x18000ea54  lea     r8, [rbp+arg_10]; struct _LOGON_SESSION **
0x18000ea58  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x18000ea5d  mov     ebx, eax
0x18000ea5f  test    eax, eax
0x18000ea61  jz      short loc_18000EAAC
0x18000ea63  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000ea6a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ea6f  mov     r9, rax
0x18000ea72  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000ea79  lea     rax, Class
0x18000ea80  mov     r8d, ebx
0x18000ea83  mov     [rsp+78h+var_48], rax
0x18000ea88  xor     ecx, ecx
0x18000ea8a  lea     rax, aAcquirelogonse_0; "AcquireLogonSession"
0x18000ea91  mov     [rsp+78h+var_50], rax
0x18000ea96  mov     [rsp+78h+var_58], 0AD7h
0x18000ea9e  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000eaa3  mov     rsi, [rbp+arg_10]
0x18000eaa7  jmp     loc_18000ECD2
0x18000eaac  mov     rsi, [rbp+arg_10]
0x18000eab0  lea     rdx, [rbp+var_38]; struct _ApPluginPkg **
0x18000eab4  lea     rcx, [rsi+24h]; struct _GUID *
0x18000eab8  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x18000eabd  mov     ebx, eax
0x18000eabf  test    eax, eax
0x18000eac1  jz      short loc_18000EB0C
0x18000eac3  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000eaca  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000eacf  mov     r9, rax
0x18000ead2  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000ead9  lea     rax, Class
0x18000eae0  mov     r8d, ebx
0x18000eae3  mov     [rsp+78h+var_48], rax
0x18000eae8  xor     ecx, ecx
0x18000eaea  lea     rax, aRefpackage; "RefPackage"
0x18000eaf1  mov     [rsp+78h+var_50], rax
0x18000eaf6  mov     [rsp+78h+var_58], 0ADCh
0x18000eafe  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000eb03  mov     rdi, [rbp+var_38]
0x18000eb07  jmp     loc_18000ECD2
0x18000eb0c  mov     rdi, [rbp+var_38]
0x18000eb10  mov     ecx, [rdi+0A0h]
0x18000eb16  test    cl, 1
0x18000eb19  jnz     short loc_18000EB69
0x18000eb1b  test    cl, 8
0x18000eb1e  jz      short loc_18000EB30
0x18000eb20  mov     eax, cs:?g_ulPlatformId@@3KA; ulong g_ulPlatformId
0x18000eb26  cmp     eax, 0Ah
0x18000eb29  jz      short loc_18000EB69
0x18000eb2b  cmp     eax, 3
0x18000eb2e  jz      short loc_18000EB69
0x18000eb30  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000eb37  mov     ebx, 0C0000022h
0x18000eb3c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000eb41  mov     r9, rax
0x18000eb44  lea     rax, Class
0x18000eb4b  mov     [rsp+78h+var_48], rax
0x18000eb50  lea     rax, aArsoNotAllowed; "ARSO not allowed"
0x18000eb57  mov     [rsp+78h+var_50], rax
0x18000eb5c  mov     [rsp+78h+var_58], 0AF9h
0x18000eb64  jmp     loc_18000ECC1
0x18000eb69  mov     r13, [rsi+38h]
0x18000eb6d  mov     dl, 1; bool
0x18000eb6f  mov     rcx, r13; struct _USER_CACHE_ENTRY *
0x18000eb72  call    ?LockAndUnProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@_N@Z; LockAndUnProtectUserCacheEntry(_USER_CACHE_ENTRY *,bool)
0x18000eb77  mov     rcx, [rdi+158h]; unsigned __int16 *
0x18000eb7e  lea     r9, [rbp+var_30]; struct _CloudAPCache **
0x18000eb82  lea     r8, aCachedata; "CacheData"
0x18000eb89  lea     rdx, [r13+68h]; unsigned __int16 *
0x18000eb8d  call    ?_GetLogonCacheForUser@@YAJPEBG00PEAPEAU_CloudAPCache@@@Z; _GetLogonCacheForUser(ushort const *,ushort const *,ushort const *,_CloudAPCache * *)
0x18000eb92  mov     r15, [rbp+var_30]
0x18000eb96  mov     ebx, eax
0x18000eb98  test    eax, eax
0x18000eb9a  jz      short loc_18000EBD0
0x18000eb9c  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000eba3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000eba8  mov     r9, rax
0x18000ebab  lea     rax, Class
0x18000ebb2  mov     [rsp+78h+var_48], rax
0x18000ebb7  lea     rax, aGetlogoncachef; "GetLogonCacheForUser"
0x18000ebbe  mov     [rsp+78h+var_50], rax
0x18000ebc3  mov     [rsp+78h+var_58], 0B04h
0x18000ebcb  jmp     loc_18000EC72
0x18000ebd0  mov     r8d, [r14+0Ch]; unsigned int
0x18000ebd4  lea     r9, [r14+10h]
0x18000ebd8  xor     eax, eax
0x18000ebda  mov     rdx, r15; struct _CloudAPCache *
0x18000ebdd  test    r8d, r8d
0x18000ebe0  mov     rcx, r13; struct _USER_CACHE_ENTRY *
0x18000ebe3  cmovz   r9, rax; unsigned __int8 *
0x18000ebe7  call    ?ProvisionTBAL@@YAJPEAU_USER_CACHE_ENTRY@@PEAU_CloudAPCache@@KPEAE@Z; ProvisionTBAL(_USER_CACHE_ENTRY *,_CloudAPCache *,ulong,uchar *)
0x18000ebec  mov     ebx, eax
0x18000ebee  test    eax, eax
0x18000ebf0  jz      short loc_18000EC23
0x18000ebf2  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000ebf9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ebfe  mov     r9, rax
0x18000ec01  lea     rax, Class
0x18000ec08  mov     [rsp+78h+var_48], rax
0x18000ec0d  lea     rax, aProvisiontbal; "ProvisionTBAL"
0x18000ec14  mov     [rsp+78h+var_50], rax
0x18000ec19  mov     [rsp+78h+var_58], 0B0Eh
0x18000ec21  jmp     short loc_18000EC72
0x18000ec23  mov     rcx, [rdi+158h]; unsigned __int16 *
0x18000ec2a  lea     r8, aCachedata; "CacheData"
0x18000ec31  mov     r9, r15; struct _CloudAPCache *
0x18000ec34  lea     rdx, [r13+68h]; unsigned __int16 *
0x18000ec38  call    ?_SaveLogonCacheForUser@@YAJPEBG00PEAU_CloudAPCache@@@Z; _SaveLogonCacheForUser(ushort const *,ushort const *,ushort const *,_CloudAPCache *)
0x18000ec3d  mov     ebx, eax
0x18000ec3f  test    eax, eax
0x18000ec41  jz      short loc_18000EC83
0x18000ec43  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000ec4a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ec4f  mov     r9, rax
0x18000ec52  lea     rax, Class
0x18000ec59  mov     [rsp+78h+var_48], rax
0x18000ec5e  lea     rax, aSavelogoncache; "SaveLogonCacheForUser"
0x18000ec65  mov     [rsp+78h+var_50], rax
0x18000ec6a  mov     [rsp+78h+var_58], 0B16h
0x18000ec72  mov     r8d, ebx
0x18000ec75  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000ec7c  xor     ecx, ecx
0x18000ec7e  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000ec83  mov     rcx, r13; struct _USER_CACHE_ENTRY *
0x18000ec86  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x18000ec8b  jmp     short loc_18000ECD2
0x18000ec8d  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000ec94  mov     ebx, 0C000000Dh
0x18000ec99  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ec9e  mov     r9, rax
0x18000eca1  lea     rax, Class
0x18000eca8  mov     [rsp+78h+var_48], rax
0x18000ecad  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x18000ecb4  mov     [rsp+78h+var_50], rax
0x18000ecb9  mov     [rsp+78h+var_58], 0ACBh
0x18000ecc1  mov     r8d, ebx
0x18000ecc4  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000eccb  xor     ecx, ecx
0x18000eccd  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000ecd2  mov     rcx, rdi; struct _ApPluginPkg *
0x18000ecd5  call    ?DerefPackage@@YAXPEAU_ApPluginPkg@@@Z; DerefPackage(_ApPluginPkg *)
0x18000ecda  mov     rcx, rsi; struct _LOGON_SESSION *
0x18000ecdd  call    ?ReleaseLogonSession@@YAXPEAU_LOGON_SESSION@@@Z; ReleaseLogonSession(_LOGON_SESSION *)
0x18000ece2  mov     rcx, r15; hMem
0x18000ece5  call    ?FreeCloudAPCache@@YAXPEAU_CloudAPCache@@@Z; FreeCloudAPCache(_CloudAPCache *)
0x18000ecea  mov     eax, ebx
0x18000ecec  add     rsp, 78h
0x18000ecf0  pop     r15
0x18000ecf2  pop     r14
0x18000ecf4  pop     r13
0x18000ecf6  pop     r12
0x18000ecf8  pop     rdi
0x18000ecf9  pop     rsi
0x18000ecfa  pop     rbx
0x18000ecfb  pop     rbp
0x18000ecfc  retn
```
