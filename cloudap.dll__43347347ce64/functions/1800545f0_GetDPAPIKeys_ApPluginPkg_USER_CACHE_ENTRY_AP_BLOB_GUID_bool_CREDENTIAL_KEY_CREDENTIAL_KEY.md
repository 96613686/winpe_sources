# GetDPAPIKeys(_ApPluginPkg *,_USER_CACHE_ENTRY *,_AP_BLOB *,_GUID *,bool,_CREDENTIAL_KEY * *,_CREDENTIAL_KEY * *)

- ea: `0x1800545f0`
- end: `0x180054e27`
- name: `?GetDPAPIKeys@@YAJPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@PEAU_AP_BLOB@@PEAU_GUID@@_NPEAPEAU_CREDENTIAL_KEY@@5@Z`
- size: `2103`
- prototype: `__int64 __fastcall(struct _ApPluginPkg *, struct _USER_CACHE_ENTRY *, struct _AP_BLOB *, struct _GUID *, bool, struct _CREDENTIAL_KEY **, struct _CREDENTIAL_KEY **)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180037240`

## callees

- `0x180007ef0`
- `0x180007fc0`
- `0x18000a600`
- `0x18000e7e0`
- `0x18002b6dc`
- `0x18002ce50`
- `0x1800335f4`
- `0x180034d5c`
- `0x18003bfdc`
- `0x18003c07c`
- `0x180042410`
- `0x1800511c8`
- `0x1800545f0`
- `0x18005dfa0`
- `0x180081010`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x1800547c5`
- `bcrypt!BCryptGenRandom` at `0x1800547c5`
- `RPCRT4!UuidCreate` at `0x1800546b0`
- `RPCRT4!UuidCreate` at `0x1800546b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005495d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005495d`

## string_xrefs

- `0x1800546bd`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005474f`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800547d5`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180054812`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180054855`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180054ce5`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180054832`: `Plugin doesn't support cached logon`
- `0x1800546db`: `UuidCreate`
- `0x180054c91`: `Plugin should return back a key Blob`

## pseudocode

```c
__int64 __fastcall GetDPAPIKeys(
        struct _ApPluginPkg *a1,
        struct _USER_CACHE_ENTRY *a2,
        struct _AP_BLOB *a3,
        struct _GUID *a4,
        bool a5,
        struct _CREDENTIAL_KEY **a6,
        struct _CREDENTIAL_KEY **a7)
{
  int v8; // ecx
  bool v10; // r15
  __int64 v11; // rdx
  const char *v12; // rax
  __int64 v13; // r8
  int KeyBlobForUser; // ebx
  const char *v15; // rax
  __int64 v16; // r8
  const char *v17; // r9
  unsigned int *v18; // rax
  int v19; // ecx
  const char *v20; // rax
  __int64 v21; // rax
  __int128 *v22; // r9
  unsigned int **v23; // rdx
  const char *v24; // rax
  int v25; // r11d
  unsigned int v26; // r10d
  __int64 v27; // r8
  __int64 v28; // rax
  const char *v29; // r9
  __int64 v30; // r8
  struct _CREDENTIAL_KEY *v31; // rax
  __int64 v32; // rcx
  _BYTE *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rax
  _BYTE *v37; // rdx
  struct _AP_BLOB *v39; // [rsp+20h] [rbp-E0h]
  const char *v40; // [rsp+28h] [rbp-D8h]
  char v41; // [rsp+50h] [rbp-B0h]
  unsigned int *v42; // [rsp+58h] [rbp-A8h] BYREF
  struct _CREDENTIAL_KEY *v43; // [rsp+60h] [rbp-A0h] BYREF
  int v44; // [rsp+68h] [rbp-98h] BYREF
  __int128 v45; // [rsp+70h] [rbp-90h] BYREF
  __int128 *v46; // [rsp+80h] [rbp-80h]
  __int64 v47; // [rsp+88h] [rbp-78h] BYREF
  __int64 v48; // [rsp+90h] [rbp-70h]
  int v49; // [rsp+98h] [rbp-68h]
  struct _ApPluginPkg *v50; // [rsp+A0h] [rbp-60h]
  struct _FILETIME v51; // [rsp+A8h] [rbp-58h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v53; // [rsp+B8h] [rbp-48h]
  struct _AP_BLOB *v54; // [rsp+C0h] [rbp-40h]
  __int128 v55; // [rsp+C8h] [rbp-38h] BYREF
  struct _CREDENTIAL_KEY **v56; // [rsp+D8h] [rbp-28h]
  __int128 v57; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v58; // [rsp+F0h] [rbp-10h] BYREF
  UUID Uuid; // [rsp+100h] [rbp+0h] BYREF

  v50 = a1;
  v53 = (unsigned __int64)a4;
  v54 = a3;
  v8 = *((_DWORD *)a1 + 40);
  v56 = a6;
  v51 = 0;
  SystemTimeAsFileTime = 0;
  v44 = 0;
  v43 = 0;
  v42 = 0;
  Uuid = 0;
  v57 = 0;
  v45 = 0;
  v55 = 0;
  v58 = 0;
  if ( a6 )
    *a6 = 0;
  v10 = a5;
  if ( a7 )
  {
    *a7 = 0;
  }
  else if ( a5 || (v8 & 0x20) != 0 )
  {
    KeyBlobForUser = -1073741595;
    v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v40 = "bGetLatestKey/bSurrogateKeys is TRUE and ppLatestCredKey is NULL";
    LODWORD(v39) = 3245;
    goto LABEL_68;
  }
  if ( (v8 & 0x20) == 0 )
  {
    if ( !*((_QWORD *)a1 + 33) )
    {
      KeyBlobForUser = -2146893039;
      v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      v40 = "Plugin doesn't support cached logon";
      LODWORD(v39) = 3284;
      goto LABEL_13;
    }
    v19 = v8 & 2;
    v46 = 0;
    v49 = v19;
    if ( a4 )
    {
      v41 = 1;
      if ( !v19 )
      {
        if ( !a7 )
        {
          KeyBlobForUser = -1073741595;
          v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          v40 = "GetKeyBlobForUser";
          LODWORD(v39) = 3297;
          goto LABEL_10;
        }
        KeyBlobForUser = GetKeyBlobForUser(
                           *((const unsigned __int16 **)a1 + 43),
                           (const unsigned __int16 *)a2 + 52,
                           *((const unsigned __int16 **)a2 + 11),
                           a4,
                           (struct _AP_BLOB *)&v57,
                           &v51);
        if ( KeyBlobForUser >= 0 )
        {
          v46 = &v57;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          if ( (unsigned int)I_CryptSubtractFileTimes(&SystemTimeAsFileTime, &v51) < 0x76A700 )
            goto LABEL_33;
          CloudAPProvider::CloudAPLogonUserKeyExpired<_GUID &>(v53);
        }
        else
        {
          v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v39) = 3310;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)KeyBlobForUser, v20, v39, "GetKeyBlobForUser", &Class);
          if ( (unsigned int)(KeyBlobForUser + 1073283070) > 1 && KeyBlobForUser != -1073281904 )
          {
            v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            v40 = "GetKeyBlobForUser";
            LODWORD(v39) = 3315;
            goto LABEL_26;
          }
          v41 = 0;
        }
LABEL_32:
        v10 = 1;
LABEL_33:
        KeyBlobForUser = DuplicateCredentialData(a2, (struct _AP_BLOB *)&v55, (struct _tagCacheNodeIdentifier *)&v58);
        if ( KeyBlobForUser )
        {
          v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          v40 = "DuplicateCredentialData";
          LODWORD(v39) = 3357;
          goto LABEL_26;
        }
        v47 = *((_QWORD *)a2 + 45);
        v21 = *((_QWORD *)a2 + 46);
        v48 = v21;
        if ( v21 )
          _InterlockedIncrement((volatile signed __int32 *)(v21 + 8));
        IncrementSharedPtrAtomicCounter(&v47);
        UnlockAndProtectUserCacheEntry(a2);
        if ( v41 )
        {
          v22 = v46;
          v23 = (unsigned int **)&v43;
        }
        else
        {
          v22 = 0;
          v23 = 0;
        }
        KeyBlobForUser = (*((__int64 (__fastcall **)(_QWORD, struct _AP_BLOB *, unsigned __int64, __int128 *, bool, unsigned int **, int *, unsigned __int64, unsigned __int64))v50
                          + 33))(
                           *((_QWORD *)v50 + 1),
                           v54,
                           v53 & -(__int64)(v41 != 0),
                           v22,
                           v10,
                           v23,
                           &v44,
                           (unsigned __int64)&v42 & -(__int64)v10,
                           (unsigned __int64)&v45 & -(__int64)v10);
        if ( KeyBlobForUser >= 0 )
        {
          if ( !v41 || !v44 || v10 )
            goto LABEL_50;
          if ( !a7 )
          {
            KeyBlobForUser = -1073741275;
LABEL_49:
            v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(v39) = v25;
            WPPTraceLogA(v26, "0x%08x %s:%u : %s:%ws", (unsigned int)KeyBlobForUser, v24, v39, v27, &Class);
            LockAndUnProtectUserCacheEntry(a2, 1);
            goto LABEL_69;
          }
          v10 = 1;
          KeyBlobForUser = (*((__int64 (__fastcall **)(_QWORD, struct _AP_BLOB *, _QWORD, _QWORD, int, _QWORD, _QWORD, unsigned int **, __int128 *))v50
                            + 33))(
                             *((_QWORD *)v50 + 1),
                             v54,
                             0,
                             0,
                             1,
                             0,
                             0,
                             &v42,
                             &v45);
          if ( KeyBlobForUser >= 0 )
          {
LABEL_50:
            LockAndUnProtectUserCacheEntry(a2, 1);
            v47 = *((_QWORD *)a2 + 45);
            v28 = *((_QWORD *)a2 + 46);
            v48 = v28;
            if ( v28 )
              _InterlockedIncrement((volatile signed __int32 *)(v28 + 8));
            DecrementSharedPtrAtomicCounter(&v47);
            if ( (unsigned int)IsCredentialDataSame(a2, (struct _AP_BLOB *)&v55, (struct _tagCacheNodeIdentifier *)&v58) )
            {
              if ( !v10 || v49 )
                goto LABEL_62;
              if ( !(_DWORD)v45 || !*((_QWORD *)&v45 + 1) || !v42 )
              {
                KeyBlobForUser = -1073741595;
                v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(v39) = 3453;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v30, v29, v39, "Plugin should return back a key Blob", &Class);
                goto LABEL_69;
              }
              KeyBlobForUser = SaveKeyBlobForUser(
                                 *((const unsigned __int16 **)v50 + 43),
                                 (const unsigned __int16 *)a2 + 52,
                                 (UUID *)v42 + 1,
                                 (LPCVOID *)&v45,
                                 0);
              if ( !KeyBlobForUser )
                goto LABEL_62;
              v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
              v40 = "SaveKeyBlobForUser";
              LODWORD(v39) = 3462;
            }
            else
            {
              KeyBlobForUser = -1073741564;
              v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
              v40 = "InteractiveLogon:Bailing out of network logon as state has changed";
              LODWORD(v39) = 3441;
            }
LABEL_26:
            v16 = (unsigned int)KeyBlobForUser;
            goto LABEL_68;
          }
        }
        else
        {
          v43 = 0;
        }
        *((_QWORD *)&v45 + 1) = 0;
        LODWORD(v45) = 0;
        v42 = 0;
        goto LABEL_49;
      }
    }
    else
    {
      v41 = 0;
      if ( !v19 )
        goto LABEL_33;
    }
    if ( !a7 )
      goto LABEL_33;
    goto LABEL_32;
  }
  if ( UuidCreate(&Uuid) )
  {
    v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v12, 3254, "UuidCreate", &Class);
    KeyBlobForUser = -1073741595;
    v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v40 = "UuidCreate";
    LODWORD(v39) = 3256;
LABEL_10:
    v17 = v15;
LABEL_68:
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v16, v17, v39, v40, &Class);
    goto LABEL_69;
  }
  v18 = (unsigned int *)((__int64 (__fastcall *)(__int64, __int64, _QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(
                          96,
                          v11,
                          0);
  v42 = v18;
  if ( !v18 )
  {
    KeyBlobForUser = -1073741801;
    v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v40 = "AllocateLsaHeap";
    LODWORD(v39) = 3264;
LABEL_13:
    v16 = (unsigned int)KeyBlobForUser;
    goto LABEL_68;
  }
  *v18 = 96;
  v42[2] = 32;
  v42[3] = 64;
  *((UUID *)v42 + 1) = Uuid;
  KeyBlobForUser = BCryptGenRandom(0, (PUCHAR)v42 + 32, 0x40u, 2u);
  if ( KeyBlobForUser )
  {
    v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v40 = "BCryptGenRandom";
    LODWORD(v39) = 3277;
    goto LABEL_13;
  }
LABEL_62:
  if ( v56 )
  {
    *v56 = v43;
    v43 = 0;
  }
  if ( a7 )
  {
    *a7 = (struct _CREDENTIAL_KEY *)v42;
    v42 = 0;
  }
  KeyBlobForUser = 0;
LABEL_69:
  if ( *((_QWORD *)&v57 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( *((_QWORD *)&v45 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v31 = v43;
  if ( v43 )
  {
    v32 = *(unsigned int *)v43;
    if ( *(_DWORD *)v43 )
    {
      do
      {
        *(_BYTE *)v31 = 0;
        v31 = (struct _CREDENTIAL_KEY *)((char *)v31 + 1);
        --v32;
      }
      while ( v32 );
    }
    ((void (__fastcall *)(struct _CREDENTIAL_KEY *))g_pLsaFunctionTable->FreeLsaHeap)(v43);
  }
  v33 = v42;
  if ( v42 )
  {
    v34 = *v42;
    if ( *v42 )
    {
      do
      {
        *v33++ = 0;
        --v34;
      }
      while ( v34 );
    }
    ((void (__fastcall *)(unsigned int *))g_pLsaFunctionTable->FreeLsaHeap)(v42);
  }
  v35 = *((_QWORD *)&v55 + 1);
  if ( *((_QWORD *)&v55 + 1) )
  {
    v36 = (unsigned int)v55;
    v37 = (_BYTE *)*((_QWORD *)&v55 + 1);
    if ( (_DWORD)v55 )
    {
      do
      {
        *v37++ = 0;
        --v36;
      }
      while ( v36 );
    }
    ((void (__fastcall *)(__int64, _BYTE *))g_pLsaFunctionTable->FreeLsaHeap)(v35, v37);
  }
  if ( *((_QWORD *)&v58 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  return (unsigned int)KeyBlobForUser;
}

```

## disassembly

```asm
0x1800545f0  push    rbp
0x1800545f2  push    rbx
0x1800545f3  push    rsi
0x1800545f4  push    rdi
0x1800545f5  push    r12
0x1800545f7  push    r13
0x1800545f9  push    r14
0x1800545fb  push    r15
0x1800545fd  lea     rbp, [rsp-28h]
0x180054602  sub     rsp, 128h
0x180054609  mov     rax, cs:__security_cookie
0x180054610  xor     rax, rsp
0x180054613  mov     [rbp+60h+var_50], rax
0x180054617  mov     r12, [rbp+60h+arg_30]
0x18005461e  xor     ebx, ebx
0x180054620  xorps   xmm0, xmm0
0x180054623  mov     [rbp+60h+var_C0], rcx
0x180054627  xorps   xmm1, xmm1
0x18005462a  mov     [rbp+60h+var_A8], r9
0x18005462e  mov     r10, rcx
0x180054631  mov     [rbp+60h+var_A0], r8
0x180054635  mov     ecx, [rcx+0A0h]
0x18005463b  mov     r13, rdx
0x18005463e  mov     rdx, [rbp+60h+arg_28]
0x180054645  mov     eax, ecx
0x180054647  and     eax, 20h
0x18005464a  mov     [rbp+60h+var_88], rdx
0x18005464e  mov     qword ptr [rbp+60h+var_B8.dwLowDateTime], rbx
0x180054652  mov     qword ptr [rbp+60h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180054656  mov     [rsp+160h+var_F8], ebx
0x18005465a  mov     [rsp+160h+var_100], rbx
0x18005465f  mov     [rsp+160h+var_108], rbx
0x180054664  movups  xmmword ptr [rbp+60h+Uuid.Data1], xmm0
0x180054668  movups  [rbp+60h+var_80], xmm1
0x18005466c  movups  [rsp+160h+var_F0], xmm0
0x180054671  movups  [rbp+60h+var_98], xmm0
0x180054675  movups  [rbp+60h+var_70], xmm1
0x180054679  test    rdx, rdx
0x18005467c  jz      short loc_180054681
0x18005467e  mov     [rdx], rbx
0x180054681  mov     r15b, [rbp+60h+arg_20]
0x180054688  test    r12, r12
0x18005468b  jz      short loc_180054693
0x18005468d  mov     [r12], rbx
0x180054691  jmp     short loc_1800546A4
0x180054693  test    r15b, r15b
0x180054696  jnz     loc_180054CDF
0x18005469c  test    eax, eax
0x18005469e  jnz     loc_180054CDF
0x1800546a4  test    eax, eax
0x1800546a6  jz      loc_180054809
0x1800546ac  lea     rcx, [rbp+60h+Uuid]; Uuid
0x1800546b0  call    cs:__imp_UuidCreate
0x1800546b6  mov     r8d, eax
0x1800546b9  test    eax, eax
0x1800546bb  jz      short loc_18005472E
0x1800546bd  lea     r14, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800546c4  mov     rcx, r14; char *
0x1800546c7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800546cc  lea     rsi, Class
0x1800546d3  mov     r9, rax
0x1800546d6  mov     [rsp+160h+var_130], rsi
0x1800546db  lea     r15, aUuidcreate; "UuidCreate"
0x1800546e2  lea     rdi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800546e9  mov     [rsp+160h+var_138], r15
0x1800546ee  mov     rdx, rdi
0x1800546f1  mov     dword ptr [rsp+160h+var_140], 0CB6h
0x1800546f9  xor     ecx, ecx
0x1800546fb  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180054700  mov     r8d, 0C00000E5h
0x180054706  mov     rcx, r14; char *
0x180054709  mov     ebx, r8d
0x18005470c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180054711  mov     [rsp+160h+var_130], rsi
0x180054716  mov     [rsp+160h+var_138], r15
0x18005471b  mov     dword ptr [rsp+160h+var_140], 0CB8h
0x180054723  mov     r9, rax
0x180054726  mov     rdx, rdi
0x180054729  jmp     loc_180054D1E
0x18005472e  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180054735  mov     edi, 60h ; '`'
0x18005473a  mov     ecx, edi
0x18005473c  mov     rax, [rax+28h]
0x180054740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054745  mov     [rsp+160h+var_108], rax
0x18005474a  test    rax, rax
0x18005474d  jnz     short loc_18005478B
0x18005474f  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180054756  mov     ebx, 0C0000017h
0x18005475b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180054760  mov     r9, rax
0x180054763  lea     rsi, Class
0x18005476a  mov     [rsp+160h+var_130], rsi
0x18005476f  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x180054776  mov     [rsp+160h+var_138], rax
0x18005477b  mov     dword ptr [rsp+160h+var_140], 0CC0h
0x180054783  mov     r8d, ebx
0x180054786  jmp     loc_180054D17
0x18005478b  mov     [rax], edi
0x18005478d  mov     r8d, 40h ; '@'; cbBuffer
0x180054793  mov     rax, [rsp+160h+var_108]
0x180054798  xor     ecx, ecx; hAlgorithm
0x18005479a  lea     r9d, [r8-3Eh]; dwFlags
0x18005479e  mov     dword ptr [rax+8], 20h ; ' '
0x1800547a5  mov     rax, [rsp+160h+var_108]
0x1800547aa  mov     [rax+0Ch], r8d
0x1800547ae  mov     rax, [rsp+160h+var_108]
0x1800547b3  movups  xmm0, xmmword ptr [rbp+60h+Uuid.Data1]
0x1800547b7  movdqu  xmmword ptr [rax+10h], xmm0
0x1800547bc  mov     rdx, [rsp+160h+var_108]
0x1800547c1  add     rdx, 20h ; ' '; pbBuffer
0x1800547c5  call    cs:__imp_BCryptGenRandom
0x1800547cb  mov     ebx, eax
0x1800547cd  test    eax, eax
0x1800547cf  jz      loc_180054CAA
0x1800547d5  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800547dc  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800547e1  mov     r9, rax
0x1800547e4  lea     rsi, Class
0x1800547eb  mov     [rsp+160h+var_130], rsi
0x1800547f0  lea     rax, aBcryptgenrando; "BCryptGenRandom"
0x1800547f7  mov     [rsp+160h+var_138], rax
0x1800547fc  mov     dword ptr [rsp+160h+var_140], 0CCDh
0x180054804  jmp     loc_180054783
0x180054809  cmp     [r10+108h], rbx
0x180054810  jnz     short loc_18005484B
0x180054812  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180054819  mov     ebx, 80090311h
0x18005481e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180054823  mov     r9, rax
0x180054826  lea     rsi, Class
0x18005482d  mov     [rsp+160h+var_130], rsi
0x180054832  lea     rax, aPluginDoesnTSu; "Plugin doesn't support cached logon"
0x180054839  mov     [rsp+160h+var_138], rax
0x18005483e  mov     dword ptr [rsp+160h+var_140], 0CD4h
0x180054846  jmp     loc_180054783
0x18005484b  and     ecx, 2
0x18005484e  mov     [rbp+60h+var_E0], rbx
0x180054852  mov     [rbp+60h+var_C8], ecx
0x180054855  lea     r14, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18005485c  lea     rsi, Class
0x180054863  lea     rdi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005486a  test    r9, r9
0x18005486d  jz      loc_180054982
0x180054873  mov     [rsp+160h+var_110], 1
0x180054878  test    ecx, ecx
0x18005487a  jnz     loc_18005498A
0x180054880  test    r12, r12
0x180054883  jnz     short loc_1800548B4
0x180054885  mov     r8d, 0C00000E5h
0x18005488b  mov     rcx, r14; char *
0x18005488e  mov     ebx, r8d
0x180054891  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180054896  mov     [rsp+160h+var_130], rsi
0x18005489b  lea     r15, aGetkeyblobforu_0; "GetKeyBlobForUser"
0x1800548a2  mov     [rsp+160h+var_138], r15
0x1800548a7  mov     dword ptr [rsp+160h+var_140], 0CE1h
0x1800548af  jmp     loc_180054723
0x1800548b4  mov     r8, [r13+58h]; Src
0x1800548b8  lea     rax, [rbp+60h+var_B8]
0x1800548bc  mov     rcx, [r10+158h]; unsigned __int16 *
0x1800548c3  lea     rdx, [r13+68h]; unsigned __int16 *
0x1800548c7  mov     [rsp+160h+var_138], rax; struct _FILETIME *
0x1800548cc  lea     rax, [rbp+60h+var_80]
0x1800548d0  mov     [rsp+160h+var_140], rax; struct _AP_BLOB *
0x1800548d5  call    ?GetKeyBlobForUser@@YAJPEBG00PEAU_GUID@@PEAU_AP_BLOB@@PEAU_FILETIME@@@Z; GetKeyBlobForUser(ushort const *,ushort const *,ushort const *,_GUID *,_AP_BLOB *,_FILETIME *)
0x1800548da  mov     ebx, eax
0x1800548dc  test    eax, eax
0x1800548de  jns     short loc_180054951
0x1800548e0  mov     rcx, r14; char *
0x1800548e3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800548e8  mov     [rsp+160h+var_130], rsi
0x1800548ed  lea     r15, aGetkeyblobforu_0; "GetKeyBlobForUser"
0x1800548f4  mov     [rsp+160h+var_138], r15
0x1800548f9  mov     r9, rax
0x1800548fc  mov     r8d, ebx
0x1800548ff  mov     dword ptr [rsp+160h+var_140], 0CEEh
0x180054907  mov     rdx, rdi
0x18005490a  xor     ecx, ecx
0x18005490c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180054911  lea     eax, [rbx+3FF8FFFEh]
0x180054917  cmp     eax, 1
0x18005491a  jbe     short loc_180054949
0x18005491c  cmp     ebx, 0C0070490h
0x180054922  jz      short loc_180054949
0x180054924  mov     rcx, r14; char *
0x180054927  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005492c  mov     [rsp+160h+var_130], rsi
0x180054931  mov     r9, rax
0x180054934  mov     [rsp+160h+var_138], r15
0x180054939  mov     dword ptr [rsp+160h+var_140], 0CF3h
0x180054941  mov     r8d, ebx
0x180054944  jmp     loc_180054726
0x180054949  xor     al, al
0x18005494b  mov     [rsp+160h+var_110], al
0x18005494f  jmp     short loc_18005498F
0x180054951  lea     rax, [rbp+60h+var_80]
0x180054955  lea     rcx, [rbp+60h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180054959  mov     [rbp+60h+var_E0], rax
0x18005495d  call    cs:__imp_GetSystemTimeAsFileTime
0x180054963  lea     rdx, [rbp+60h+var_B8]
0x180054967  lea     rcx, [rbp+60h+SystemTimeAsFileTime]
0x18005496b  call    I_CryptSubtractFileTimes
0x180054970  cmp     eax, 76A700h
0x180054975  jb      short loc_180054992
0x180054977  mov     rcx, [rbp+60h+var_A8]
0x18005497b  call    ??$CloudAPLogonUserKeyExpired@AEAU_GUID@@@CloudAPProvider@@SAXAEAU_GUID@@@Z; CloudAPProvider::CloudAPLogonUserKeyExpired<_GUID &>(_GUID &)
0x180054980  jmp     short loc_18005498F
0x180054982  mov     [rsp+160h+var_110], bl
0x180054986  test    ecx, ecx
0x180054988  jz      short loc_180054992
0x18005498a  test    r12, r12
0x18005498d  jz      short loc_180054992
0x18005498f  mov     r15b, 1
0x180054992  lea     r8, [rbp+60h+var_70]; struct _tagCacheNodeIdentifier *
0x180054996  mov     rcx, r13; struct _USER_CACHE_ENTRY *
0x180054999  lea     rdx, [rbp+60h+var_98]; struct _AP_BLOB *
0x18005499d  call    ?DuplicateCredentialData@@YAJPEAU_USER_CACHE_ENTRY@@PEAU_AP_BLOB@@PEAU_tagCacheNodeIdentifier@@@Z; DuplicateCredentialData(_USER_CACHE_ENTRY *,_AP_BLOB *,_tagCacheNodeIdentifier *)
0x1800549a2  mov     ebx, eax
0x1800549a4  test    eax, eax
0x1800549a6  jz      short loc_1800549D1
0x1800549a8  mov     rcx, r14; char *
0x1800549ab  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800549b0  mov     [rsp+160h+var_130], rsi
0x1800549b5  mov     r9, rax
0x1800549b8  lea     rax, aDuplicatecrede; "DuplicateCredentialData"
0x1800549bf  mov     [rsp+160h+var_138], rax
0x1800549c4  mov     dword ptr [rsp+160h+var_140], 0D1Dh
0x1800549cc  jmp     loc_180054941
0x1800549d1  mov     rax, [r13+168h]
0x1800549d8  mov     [rbp+60h+var_D8], rax
0x1800549dc  mov     rax, [r13+170h]
0x1800549e3  mov     [rbp+60h+var_D0], rax
0x1800549e7  test    rax, rax
0x1800549ea  jz      short loc_1800549F0
0x1800549ec  lock inc dword ptr [rax+8]
0x1800549f0  lea     rcx, [rbp+60h+var_D8]
0x1800549f4  call    ?IncrementSharedPtrAtomicCounter@@YAXV?$shared_ptr@U?$atomic@K@utl@@@utl@@@Z; IncrementSharedPtrAtomicCounter(utl::shared_ptr<utl::atomic<ulong>>)
0x1800549f9  mov     rcx, r13; struct _USER_CACHE_ENTRY *
0x1800549fc  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x180054a01  mov     r10, [rbp+60h+var_C0]
0x180054a05  mov     al, r15b
0x180054a08  neg     al
0x180054a0a  lea     rax, [rsp+160h+var_F0]
0x180054a0f  sbb     r11, r11
0x180054a12  and     r11, rax
0x180054a15  mov     al, r15b
0x180054a18  neg     al
0x180054a1a  lea     rax, [rsp+160h+var_108]
0x180054a1f  sbb     rbx, rbx
0x180054a22  and     rbx, rax
0x180054a25  mov     al, [rsp+160h+var_110]
0x180054a29  test    al, al
0x180054a2b  jz      short loc_180054A38
0x180054a2d  mov     r9, [rbp+60h+var_E0]
0x180054a31  lea     rdx, [rsp+160h+var_100]
0x180054a36  jmp     short loc_180054A3D
0x180054a38  xor     r9d, r9d
0x180054a3b  xor     edx, edx
0x180054a3d  mov     [rsp+160h+var_120], r11
0x180054a42  neg     al
0x180054a44  mov     [rsp+160h+var_128], rbx
0x180054a49  lea     rax, [rsp+160h+var_F8]
0x180054a4e  mov     [rsp+160h+var_130], rax
0x180054a53  sbb     r8, r8
0x180054a56  and     r8, [rbp+60h+var_A8]
0x180054a5a  mov     rax, [r10+108h]
0x180054a61  mov     [rsp+160h+var_138], rdx
0x180054a66  mov     rdx, [rbp+60h+var_A0]
0x180054a6a  movzx   ecx, r15b
0x180054a6e  mov     dword ptr [rsp+160h+var_140], ecx
0x180054a72  mov     rcx, [r10+8]
0x180054a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a7b  mov     ebx, eax
0x180054a7d  test    eax, eax
0x180054a7f  jns     short loc_180054A95
0x180054a81  mov     [rsp+160h+var_100], 0
0x180054a8a  mov     r11d, 0D36h
0x180054a90  jmp     loc_180054B28
0x180054a95  cmp     [rsp+160h+var_110], 0
0x180054a9a  jz      loc_180054B83
0x180054aa0  cmp     [rsp+160h+var_F8], 0
0x180054aa5  jz      loc_180054B83
0x180054aab  test    r15b, r15b
0x180054aae  jnz     loc_180054B83
0x180054ab4  test    r12, r12
0x180054ab7  jnz     short loc_180054ACD
0x180054ab9  mov     ebx, 0C0000225h
0x180054abe  lea     r8, aCurrentKeyNotR; "Current Key not recoverable from the se"...
0x180054ac5  mov     r11d, 0D46h
0x180054acb  jmp     short loc_180054B49
0x180054acd  mov     rdx, [rbp+60h+var_A0]
0x180054ad1  lea     rax, [rsp+160h+var_F0]
0x180054ad6  mov     [rsp+160h+var_120], rax
0x180054adb  xor     r9d, r9d
0x180054ade  lea     rax, [rsp+160h+var_108]
0x180054ae3  xor     r8d, r8d
0x180054ae6  mov     [rsp+160h+var_128], rax
0x180054aeb  mov     r15b, 1
0x180054aee  mov     rax, [rbp+60h+var_C0]
  ... truncated ...
```
