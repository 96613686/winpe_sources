# LsaDbpForestTrustCacheInsert(_UNICODE_STRING *,void *,_LSA_FOREST_TRUST_INFORMATION2 *,uchar)

- ea: `0x180025ba8`
- end: `0x1800262b4`
- name: `?LsaDbpForestTrustCacheInsert@@YAJPEAU_UNICODE_STRING@@PEAXPEAU_LSA_FOREST_TRUST_INFORMATION2@@E@Z`
- size: `1804`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, void *, struct _LSA_FOREST_TRUST_INFORMATION2 *, unsigned __int8)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000b990`
- `0x1800262bc`
- `0x1800266b0`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x18000bf70`
- `0x18000c0e0`
- `0x18000fd18`
- `0x18000fd40`
- `0x1800215a4`
- `0x180022580`
- `0x180025ba8`
- `0x180026c5c`
- `0x180027738`
- `0x180028c84`
- `0x180029e14`
- `0x18002a320`
- `0x18002ae5c`
- `0x18002b5a4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025eff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025f45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025f7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800260ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026104`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002616e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800261e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026246`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026284`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025eff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025f45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025f7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800260ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026104`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002616e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800261e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026246`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026284`
- `LSASRV!LsapIsSamOpened` at `0x180025d41`
- `LSASRV!LsapIsSamOpened` at `0x180025d41`
- `LSASRV!LsapDbWriteAttributesObject` at `0x1800260d1`
- `LSASRV!LsapDbWriteAttributesObject` at `0x1800260d1`
- `LSASRV!LsapDbOpenObject` at `0x180026040`
- `LSASRV!LsapDbOpenObject` at `0x180026040`
- `LSASRV!LsapDbDereferenceObject` at `0x18002612c`
- `LSASRV!LsapDbDereferenceObject` at `0x18002612c`
- `LSASRV!LsapGetAccountDomainHandle` at `0x180025c18`
- `LSASRV!LsapGetAccountDomainHandle` at `0x180025c18`
- `LSASRV!LsapDbInitializeAttribute` at `0x1800260a3`
- `LSASRV!LsapDbInitializeAttribute` at `0x1800260a3`
- `LSASRV!LsapDbReferenceObject` at `0x180025ec7`
- `LSASRV!LsapDbReferenceObject` at `0x180025ec7`
- `LSASRV!LsapDbCloseHandle` at `0x1800260e6`
- `LSASRV!LsapDbCloseHandle` at `0x1800261f1`
- `LSASRV!LsapDbCloseHandle` at `0x180026251`
- `LSASRV!LsapDbCloseHandle` at `0x1800260e6`
- `LSASRV!LsapDbCloseHandle` at `0x1800261f1`
- `LSASRV!LsapDbCloseHandle` at `0x180026251`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002605f`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002605f`
- `ntdll!RtlEqualUnicodeString` at `0x180025e26`
- `ntdll!RtlEqualUnicodeString` at `0x180025e6c`
- `ntdll!RtlEqualUnicodeString` at `0x180025e26`
- `ntdll!RtlEqualUnicodeString` at `0x180025e6c`
- `SAMSRV!SamIQueryServerRole` at `0x180025d57`
- `SAMSRV!SamIQueryServerRole` at `0x180025d57`

## pseudocode

```c
__int64 __fastcall LsaDbpForestTrustCacheInsert(
        struct _UNICODE_STRING *a1,
        void *a2,
        struct _LSA_FOREST_TRUST_INFORMATION2 *a3,
        char a4)
{
  __int64 v8; // rcx
  __int64 AccountDomainHandle; // rsi
  char v11; // r12
  FTCache *v12; // rcx
  int v13; // ebx
  int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // r8d
  PCUNICODE_STRING *v17; // rdi
  __int64 v18; // rsi
  __int64 v19; // r12
  __int64 v20; // r14
  int v21; // eax
  __int64 v22; // r15
  __int64 v23; // rbx
  __int64 v24; // rbx
  int v25; // eax
  __int64 v26; // r14
  struct _LSAPR_UNICODE_STRING *v27; // rcx
  int v28; // eax
  int v29; // r8d
  int v30; // eax
  struct FTCache::TDO_ENTRY *v31; // rax
  int v32; // eax
  HLOCAL v33; // r15
  int v34; // eax
  PCUNICODE_STRING *v35; // rcx
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r9
  int v39; // [rsp+20h] [rbp-E0h]
  unsigned int v40; // [rsp+54h] [rbp-ACh] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  int v42; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL v44; // [rsp+70h] [rbp-90h] BYREF
  struct FTCache::TDO_ENTRY *v45; // [rsp+78h] [rbp-88h] BYREF
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v46; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v47; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v48[8]; // [rsp+90h] [rbp-70h] BYREF
  int v49; // [rsp+D0h] [rbp-30h]
  int v50; // [rsp+D4h] [rbp-2Ch]
  __int16 v51; // [rsp+E0h] [rbp-20h] BYREF
  char v52[86]; // [rsp+E2h] [rbp-1Eh] BYREF
  int v53; // [rsp+138h] [rbp+38h]
  _BYTE v54[32]; // [rsp+140h] [rbp+40h] BYREF
  int v55; // [rsp+160h] [rbp+60h]
  int v56; // [rsp+164h] [rbp+64h]

  v51 = 0;
  memset_0(v52, 0, 0x5Eu);
  v45 = 0;
  v44 = 0;
  v40 = 0;
  v42 = 2;
  AccountDomainHandle = LsapGetAccountDomainHandle(v8);
  if ( !LsaDbpNoMoreWin2KForest() && !a4 )
    return 0;
  v11 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
  if ( !LsaDbpValidateForestTrustInfo2(a3) )
  {
    v12 = (FTCache *)WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    v13 = -1073741811;
    goto LABEL_57;
  }
  v14 = FTCache::Insert(
          g_FTCache,
          a1,
          a2,
          a3,
          a4,
          (struct FTCache::TDO_ENTRY *)&v51,
          &v45,
          (struct FTCache::CONFLICT_PAIR **)&v44,
          &v40);
  v13 = v14;
  if ( v14 < 0 )
  {
    v12 = (FTCache *)WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_57;
    v15 = 46;
    goto LABEL_13;
  }
  if ( !v44 )
    goto LABEL_79;
  FTCache::ReconcileConflictPairs(0, (struct FTCache::CONFLICT_PAIR *)v44, v40);
  if ( !v44 || !DcInRootDomain || !(unsigned __int8)LsapIsSamOpened() )
    goto LABEL_79;
  v14 = SamIQueryServerRole(AccountDomainHandle, &v42);
  v13 = v14;
  if ( v14 < 0 )
  {
    v12 = (FTCache *)WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_57;
    v15 = 47;
LABEL_13:
    WPP_SF_d(*((_QWORD *)v12 + 2), v15, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, (unsigned int)v14);
    goto LABEL_57;
  }
  if ( v42 != 3 )
    goto LABEL_79;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  hMem = 0;
  while ( (unsigned int)v19 < v40 )
  {
    if ( *((_DWORD *)v44 + 10 * v19) )
    {
      v20 = 0;
      if ( *((_DWORD *)v44 + 10 * v19) != 2 )
        goto LABEL_29;
      v20 = *(_QWORD *)(*((_QWORD *)v44 + 5 * v19 + 1) + 88LL);
    }
    else
    {
      v20 = *(_QWORD *)(*((_QWORD *)v44 + 5 * v19 + 1) + 48LL);
    }
    if ( *(_BYTE *)(v20 + 92) )
      v20 = 0;
LABEL_29:
    v21 = *((_DWORD *)v44 + 10 * v19 + 5);
    if ( !v21 )
    {
      v22 = *(_QWORD *)(*((_QWORD *)v44 + 5 * v19 + 3) + 48LL);
LABEL_33:
      if ( *(_BYTE *)(v22 + 92) )
        v22 = 0;
      goto LABEL_35;
    }
    v22 = 0;
    if ( v21 == 2 )
    {
      v22 = *(_QWORD *)(*((_QWORD *)v44 + 5 * v19 + 3) + 88LL);
      goto LABEL_33;
    }
LABEL_35:
    if ( v20 || v22 )
    {
      v23 = 0;
      if ( v20 )
      {
        while ( (unsigned int)v23 < (unsigned int)v18 )
        {
          if ( RtlEqualUnicodeString((PCUNICODE_STRING)v20, v17[v23], 1u) )
            goto LABEL_44;
          v23 = (unsigned int)(v23 + 1);
        }
        if ( (_DWORD)v23 == (_DWORD)v18 )
        {
          v13 = LsaDbpLocalAllocateOneMoreEntry(&hMem, v18, v16);
          if ( v13 < 0 )
          {
            if ( hMem )
              LocalFree(hMem);
            v12 = (FTCache *)WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_DZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, v16, v13, v20);
            goto LABEL_56;
          }
          v17 = (PCUNICODE_STRING *)hMem;
          *((_QWORD *)hMem + v18) = v20;
          v18 = (unsigned int)(v18 + 1);
        }
      }
LABEL_44:
      v24 = 0;
      if ( v22 )
      {
        while ( (unsigned int)v24 < (unsigned int)v18 )
        {
          if ( RtlEqualUnicodeString((PCUNICODE_STRING)v22, v17[v24], 1u) )
            goto LABEL_51;
          v24 = (unsigned int)(v24 + 1);
        }
        if ( (_DWORD)v24 == (_DWORD)v18 )
        {
          v13 = LsaDbpLocalAllocateOneMoreEntry(&hMem, v18, v16);
          if ( v13 < 0 )
          {
            if ( hMem )
              LocalFree(hMem);
            v12 = (FTCache *)WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_DZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, v16, v13, v22);
            goto LABEL_56;
          }
          v17 = (PCUNICODE_STRING *)hMem;
          *((_QWORD *)hMem + v18) = v22;
          v18 = (unsigned int)(v18 + 1);
        }
      }
    }
LABEL_51:
    v19 = (unsigned int)(v19 + 1);
  }
  v39 = 0x2000000;
  v25 = LsapDbReferenceObject(LsaDbpPolicyHandle, 0, 1, 2);
  v13 = v25;
  if ( v25 < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
        (unsigned int)v25);
    LocalFree(v17);
LABEL_56:
    v11 = 0;
    goto LABEL_57;
  }
  v26 = 0;
  v11 = 1;
  if ( !(_DWORD)v18 )
  {
LABEL_76:
    LocalFree(v17);
    goto LABEL_77;
  }
  while ( 1 )
  {
    memset_0(v48, 0, 0x48u);
    v43 = 0;
    v46 = 0;
    v27 = (struct _LSAPR_UNICODE_STRING *)v17[v26];
    LODWORD(hMem) = 0;
    v47 = 0;
    v28 = LsaDbpLookupNameTrustedDomainListEx(v27, &v46);
    v13 = v28;
    if ( v28 < 0 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_DZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, v29, v28, (__int64)a1);
      goto LABEL_98;
    }
    v48[2] = LsaDbpPolicyHandle;
    memset(&v48[4], 0, 32);
    v49 = 0;
    v48[3] = (char *)v46 + 16;
    v48[1] = 48;
    v48[0] = 2;
    v50 = 32;
    v30 = LsapDbOpenObject(v48, 32, 0, &v43, v39);
    v13 = v30;
    if ( v30 < 0 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
          (unsigned int)v30);
LABEL_98:
      v35 = v17;
      goto LABEL_99;
    }
    v31 = (struct FTCache::TDO_ENTRY *)RtlLookupElementGenericTableAvl(
                                         (PRTL_AVL_TABLE)((char *)g_FTCache + 8),
                                         (PVOID)v17[v26]);
    if ( !v31 )
    {
      v13 = -1073741275;
      v36 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v37 = 53;
        v38 = 3221226021LL;
        goto LABEL_94;
      }
LABEL_95:
      LocalFree(v17);
      LsapDbCloseHandle(v43);
      goto LABEL_57;
    }
    v32 = FTCache::MarshalBlob(v31, (unsigned int *)&hMem, (unsigned __int8 **)&v47);
    v13 = v32;
    if ( v32 < 0 )
    {
      v36 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v37 = 54;
        v38 = (unsigned int)v32;
LABEL_94:
        WPP_SF_d(v36[2], v37, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, v38);
        goto LABEL_95;
      }
      goto LABEL_95;
    }
    v33 = v47;
    LOBYTE(v39) = 0;
    LsapDbInitializeAttribute(v54, 45, v47);
    v55 = *((_DWORD *)LsaDbpDsAttInfo + 135);
    v56 = *((_DWORD *)LsaDbpDsAttInfo + 136);
    v34 = LsapDbWriteAttributesObject(v43, v54);
    v13 = v34;
    if ( v34 < 0 )
      break;
    LsapDbCloseHandle(v43);
    LocalFree(v33);
    v26 = (unsigned int)(v26 + 1);
    if ( (unsigned int)v26 >= (unsigned int)v18 )
      goto LABEL_76;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
      (unsigned int)v34);
  LocalFree(v17);
  LsapDbCloseHandle(v43);
  v35 = (PCUNICODE_STRING *)v33;
LABEL_99:
  LocalFree(v35);
LABEL_57:
  if ( v45 )
  {
    FTCache::RollbackChanges(g_FTCache, v45, (struct FTCache::TDO_ENTRY *)&v51);
    v45 = 0;
  }
  if ( v11 )
LABEL_77:
    v13 = LsapDbDereferenceObject(&LsaDbpPolicyHandle, 1, 2, 33570816, 0, v13);
  if ( v13 >= 0 )
  {
LABEL_79:
    if ( v44 && v42 == 3 )
      FTCache::AuditCollisions(v12, (struct FTCache::CONFLICT_PAIR *)v44, v40);
  }
  if ( v53 )
    FTCache::PurgeTdoEntry(g_FTCache, (struct FTCache::TDO_ENTRY *)&v51);
  LocalFree(v44);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
      (unsigned int)v13);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180025ba8  push    rbp
0x180025baa  push    rbx
0x180025bab  push    rsi
0x180025bac  push    rdi
0x180025bad  push    r12
0x180025baf  push    r13
0x180025bb1  push    r14
0x180025bb3  push    r15
0x180025bb5  lea     rbp, [rsp-2D8h]
0x180025bbd  sub     rsp, 3D8h
0x180025bc4  mov     rax, cs:__security_cookie
0x180025bcb  xor     rax, rsp
0x180025bce  mov     [rbp+310h+var_50], rax
0x180025bd5  xor     eax, eax
0x180025bd7  mov     rdi, r8
0x180025bda  mov     r14, rdx
0x180025bdd  mov     [rbp+310h+var_330], ax
0x180025be1  mov     r13, rcx
0x180025be4  xor     edx, edx; Val
0x180025be6  lea     rcx, [rbp+310h+var_32E]; void *
0x180025bea  mov     bl, r9b
0x180025bed  lea     r8d, [rax+5Eh]; Size
0x180025bf1  call    memset_0
0x180025bf6  mov     [rsp+410h+var_398], 0
0x180025bff  mov     [rsp+410h+var_3A0], 0
0x180025c08  mov     [rsp+410h+var_3BC], 0
0x180025c10  mov     [rsp+410h+var_3B0], 2
0x180025c18  call    cs:__imp_LsapGetAccountDomainHandle
0x180025c1e  mov     rsi, rax
0x180025c21  call    ?LsaDbpNoMoreWin2KForest@@YAEXZ; LsaDbpNoMoreWin2KForest(void)
0x180025c26  test    al, al
0x180025c28  jnz     short loc_180025C35
0x180025c2a  test    bl, bl
0x180025c2c  jnz     short loc_180025C35
0x180025c2e  xor     eax, eax
0x180025c30  jmp     loc_18002619B
0x180025c35  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c3c  xor     r12b, r12b
0x180025c3f  mov     r15b, 8
0x180025c42  mov     [rsp+410h+var_3C0], r12b
0x180025c47  test    [rcx+1Ch], r15b
0x180025c4b  jz      short loc_180025C62
0x180025c4d  mov     rcx, [rcx+10h]
0x180025c51  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180025c58  mov     edx, 2Ch ; ','
0x180025c5d  call    WPP_SF_
0x180025c62  mov     rcx, rdi; struct _LSA_FOREST_TRUST_INFORMATION2 *
0x180025c65  call    ?LsaDbpValidateForestTrustInfo2@@YAEPEAU_LSA_FOREST_TRUST_INFORMATION2@@@Z; LsaDbpValidateForestTrustInfo2(_LSA_FOREST_TRUST_INFORMATION2 *)
0x180025c6a  test    al, al
0x180025c6c  jnz     short loc_180025C9A
0x180025c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c75  test    [rcx+1Ch], r15b
0x180025c79  jz      short loc_180025C90
0x180025c7b  mov     rcx, [rcx+10h]
0x180025c7f  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180025c86  mov     edx, 2Dh ; '-'
0x180025c8b  call    WPP_SF_
0x180025c90  mov     ebx, 0C000000Dh
0x180025c95  jmp     loc_180025F0A
0x180025c9a  mov     rcx, cs:?g_FTCache@@3PEAVFTCache@@EA; this
0x180025ca1  lea     rax, [rsp+410h+var_3BC]
0x180025ca6  mov     [rsp+410h+var_3D0], rax; unsigned int *
0x180025cab  mov     r9, rdi; struct _LSA_FOREST_TRUST_INFORMATION2 *
0x180025cae  lea     rax, [rsp+410h+var_3A0]
0x180025cb3  mov     r8, r14; void *
0x180025cb6  mov     [rsp+410h+var_3D8], rax; struct FTCache::CONFLICT_PAIR **
0x180025cbb  mov     rdx, r13; struct _UNICODE_STRING *
0x180025cbe  lea     rax, [rsp+410h+var_398]
0x180025cc3  mov     [rsp+410h+var_3E0], rax; struct FTCache::TDO_ENTRY **
0x180025cc8  lea     rax, [rbp+310h+var_330]
0x180025ccc  mov     [rsp+410h+var_3E8], rax; struct FTCache::TDO_ENTRY *
0x180025cd1  mov     [rsp+410h+var_3F0], bl; unsigned __int8
0x180025cd5  call    ?Insert@FTCache@@AEAAJPEAU_UNICODE_STRING@@PEAXPEAU_LSA_FOREST_TRUST_INFORMATION2@@EPEAUTDO_ENTRY@1@PEAPEAU41@PEAPEAUCONFLICT_PAIR@1@PEAK@Z; FTCache::Insert(_UNICODE_STRING *,void *,_LSA_FOREST_TRUST_INFORMATION2 *,uchar,FTCache::TDO_ENTRY *,FTCache::TDO_ENTRY * *,FTCache::CONFLICT_PAIR * *,ulong *)
0x180025cda  mov     ebx, eax
0x180025cdc  test    eax, eax
0x180025cde  jns     short loc_180025D0E
0x180025ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ce7  test    [rcx+1Ch], r15b
0x180025ceb  jz      loc_180025F0A
0x180025cf1  mov     edx, 2Eh ; '.'
0x180025cf6  mov     rcx, [rcx+10h]
0x180025cfa  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180025d01  mov     r9d, eax
0x180025d04  call    WPP_SF_d
0x180025d09  jmp     loc_180025F0A
0x180025d0e  mov     rdx, [rsp+410h+var_3A0]; struct FTCache::CONFLICT_PAIR *
0x180025d13  test    rdx, rdx
0x180025d16  jz      loc_180026138
0x180025d1c  mov     r8d, [rsp+410h+var_3BC]; unsigned int
0x180025d21  xor     ecx, ecx; struct FTCache::TDO_ENTRY *
0x180025d23  call    ?ReconcileConflictPairs@FTCache@@CAXPEBUTDO_ENTRY@1@PEAUCONFLICT_PAIR@1@K@Z; FTCache::ReconcileConflictPairs(FTCache::TDO_ENTRY const *,FTCache::CONFLICT_PAIR *,ulong)
0x180025d28  cmp     [rsp+410h+var_3A0], 0
0x180025d2e  jz      loc_180026138
0x180025d34  cmp     cs:?DcInRootDomain@@3EA, r12b; uchar DcInRootDomain
0x180025d3b  jz      loc_180026138
0x180025d41  call    cs:__imp_LsapIsSamOpened
0x180025d47  test    al, al
0x180025d49  jz      loc_180026138
0x180025d4f  lea     rdx, [rsp+410h+var_3B0]
0x180025d54  mov     rcx, rsi
0x180025d57  call    cs:__imp_SamIQueryServerRole
0x180025d5d  mov     ebx, eax
0x180025d5f  test    eax, eax
0x180025d61  jns     short loc_180025D7E
0x180025d63  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d6a  test    [rcx+1Ch], r15b
0x180025d6e  jz      loc_180025F0A
0x180025d74  mov     edx, 2Fh ; '/'
0x180025d79  jmp     loc_180025CF6
0x180025d7e  cmp     [rsp+410h+var_3B0], 3
0x180025d83  jnz     loc_180026138
0x180025d89  xor     edi, edi
0x180025d8b  xor     esi, esi
0x180025d8d  xor     r12d, r12d
0x180025d90  mov     [rsp+410h+hMem], rdi
0x180025d95  cmp     [rsp+410h+var_3BC], esi
0x180025d99  jbe     loc_180025EAE
0x180025d9f  mov     rdx, [rsp+410h+var_3A0]
0x180025da4  lea     rcx, [r12+r12*4]
0x180025da8  cmp     dword ptr [rdx+rcx*8], 0
0x180025dac  jz      short loc_180025DC2
0x180025dae  xor     r14d, r14d
0x180025db1  cmp     dword ptr [rdx+rcx*8], 2
0x180025db5  jnz     short loc_180025DD5
0x180025db7  mov     rax, [rdx+rcx*8+8]
0x180025dbc  mov     r14, [rax+58h]
0x180025dc0  jmp     short loc_180025DCB
0x180025dc2  mov     rax, [rdx+rcx*8+8]
0x180025dc7  mov     r14, [rax+30h]
0x180025dcb  xor     eax, eax
0x180025dcd  cmp     [r14+5Ch], al
0x180025dd1  cmovnz  r14, rax
0x180025dd5  mov     eax, [rdx+rcx*8+14h]
0x180025dd9  test    eax, eax
0x180025ddb  jz      short loc_180025DF0
0x180025ddd  xor     r15d, r15d
0x180025de0  cmp     eax, 2
0x180025de3  jnz     short loc_180025E03
0x180025de5  mov     rax, [rdx+rcx*8+18h]
0x180025dea  mov     r15, [rax+58h]
0x180025dee  jmp     short loc_180025DF9
0x180025df0  mov     rax, [rdx+rcx*8+18h]
0x180025df5  mov     r15, [rax+30h]
0x180025df9  xor     eax, eax
0x180025dfb  cmp     [r15+5Ch], al
0x180025dff  cmovnz  r15, rax
0x180025e03  test    r14, r14
0x180025e06  jnz     short loc_180025E11
0x180025e08  test    r15, r15
0x180025e0b  jz      loc_180025E9D
0x180025e11  xor     ebx, ebx
0x180025e13  test    r14, r14
0x180025e16  jz      short loc_180025E57
0x180025e18  cmp     ebx, esi
0x180025e1a  jnb     short loc_180025E34
0x180025e1c  mov     rdx, [rdi+rbx*8]; String2
0x180025e20  mov     r8b, 1; CaseInsensitive
0x180025e23  mov     rcx, r14; String1
0x180025e26  call    cs:__imp_RtlEqualUnicodeString
0x180025e2c  test    al, al
0x180025e2e  jnz     short loc_180025E57
0x180025e30  inc     ebx
0x180025e32  jmp     short loc_180025E18
0x180025e34  jnz     short loc_180025E57
0x180025e36  mov     edx, esi; unsigned int
0x180025e38  lea     rcx, [rsp+410h+hMem]; void **
0x180025e3d  call    ?LsaDbpLocalAllocateOneMoreEntry@@YAJPEAPEAXKK@Z; LsaDbpLocalAllocateOneMoreEntry(void * *,ulong,ulong)
0x180025e42  mov     ebx, eax
0x180025e44  test    eax, eax
0x180025e46  js      loc_180025F3B
0x180025e4c  mov     rdi, [rsp+410h+hMem]
0x180025e51  mov     [rdi+rsi*8], r14
0x180025e55  inc     esi
0x180025e57  xor     ebx, ebx
0x180025e59  test    r15, r15
0x180025e5c  jz      short loc_180025E9D
0x180025e5e  cmp     ebx, esi
0x180025e60  jnb     short loc_180025E7A
0x180025e62  mov     rdx, [rdi+rbx*8]; String2
0x180025e66  mov     r8b, 1; CaseInsensitive
0x180025e69  mov     rcx, r15; String1
0x180025e6c  call    cs:__imp_RtlEqualUnicodeString
0x180025e72  test    al, al
0x180025e74  jnz     short loc_180025E9D
0x180025e76  inc     ebx
0x180025e78  jmp     short loc_180025E5E
0x180025e7a  jnz     short loc_180025E9D
0x180025e7c  mov     edx, esi; unsigned int
0x180025e7e  lea     rcx, [rsp+410h+hMem]; void **
0x180025e83  call    ?LsaDbpLocalAllocateOneMoreEntry@@YAJPEAPEAXKK@Z; LsaDbpLocalAllocateOneMoreEntry(void * *,ulong,ulong)
0x180025e88  mov     ebx, eax
0x180025e8a  test    eax, eax
0x180025e8c  js      loc_180025F70
0x180025e92  mov     rdi, [rsp+410h+hMem]
0x180025e97  mov     [rdi+rsi*8], r15
0x180025e9b  inc     esi
0x180025e9d  inc     r12d
0x180025ea0  cmp     r12d, [rsp+410h+var_3BC]
0x180025ea5  jb      loc_180025D9F
0x180025eab  mov     r15b, 8
0x180025eae  mov     rcx, cs:?LsaDbpPolicyHandle@@3PEAXEA; void * LsaDbpPolicyHandle
0x180025eb5  xor     edx, edx
0x180025eb7  mov     dword ptr [rsp+410h+var_3F0], 2000000h
0x180025ebf  lea     r9d, [rdx+2]
0x180025ec3  lea     r8d, [rdx+1]
0x180025ec7  call    cs:__imp_LsapDbReferenceObject
0x180025ecd  mov     ebx, eax
0x180025ecf  test    eax, eax
0x180025ed1  jns     loc_180025F9D
0x180025ed7  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ede  test    [rcx+1Ch], r15b
0x180025ee2  jz      short loc_180025EFC
0x180025ee4  mov     rcx, [rcx+10h]
0x180025ee8  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180025eef  mov     edx, 32h ; '2'
0x180025ef4  mov     r9d, eax
0x180025ef7  call    WPP_SF_d
0x180025efc  mov     rcx, rdi; hMem
0x180025eff  call    cs:__imp_LocalFree
0x180025f05  mov     r12b, [rsp+410h+var_3C0]
0x180025f0a  mov     rdx, [rsp+410h+var_398]; struct FTCache::TDO_ENTRY *
0x180025f0f  test    rdx, rdx
0x180025f12  jz      short loc_180025F2D
0x180025f14  mov     rcx, cs:?g_FTCache@@3PEAVFTCache@@EA; this
0x180025f1b  lea     r8, [rbp+310h+var_330]; struct FTCache::TDO_ENTRY *
0x180025f1f  call    ?RollbackChanges@FTCache@@AEAAXPEAUTDO_ENTRY@1@0@Z; FTCache::RollbackChanges(FTCache::TDO_ENTRY *,FTCache::TDO_ENTRY *)
0x180025f24  mov     [rsp+410h+var_398], 0
0x180025f2d  test    r12b, r12b
0x180025f30  jz      loc_180026134
0x180025f36  jmp     loc_18002610A
0x180025f3b  mov     rcx, [rsp+410h+hMem]; hMem
0x180025f40  test    rcx, rcx
0x180025f43  jz      short loc_180025F4B
0x180025f45  call    cs:__imp_LocalFree
0x180025f4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f52  test    byte ptr [rcx+1Ch], 8
0x180025f56  jz      short loc_180025F05
0x180025f58  mov     edx, 30h ; '0'
0x180025f5d  mov     qword ptr [rsp+410h+var_3F0], r14
0x180025f62  mov     rcx, [rcx+10h]
0x180025f66  mov     r9d, ebx
0x180025f69  call    WPP_SF_DZ
0x180025f6e  jmp     short loc_180025F05
0x180025f70  mov     rcx, [rsp+410h+hMem]; hMem
0x180025f75  test    rcx, rcx
0x180025f78  jz      short loc_180025F80
0x180025f7a  call    cs:__imp_LocalFree
0x180025f80  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f87  test    byte ptr [rcx+1Ch], 8
0x180025f8b  jz      loc_180025F05
0x180025f91  mov     edx, 31h ; '1'
0x180025f96  mov     qword ptr [rsp+410h+var_3F0], r15
0x180025f9b  jmp     short loc_180025F62
0x180025f9d  xor     r14d, r14d
0x180025fa0  mov     r12b, 1
0x180025fa3  test    esi, esi
0x180025fa5  jz      loc_180026101
0x180025fab  xor     edx, edx; Val
0x180025fad  lea     rcx, [rbp+310h+var_380]; void *
0x180025fb1  lea     r8d, [rdx+48h]; Size
0x180025fb5  call    memset_0
0x180025fba  mov     [rsp+410h+var_3A8], 0
0x180025fc3  lea     rdx, [rbp+310h+var_390]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x180025fc7  mov     [rbp+310h+var_390], 0
0x180025fcf  mov     rcx, [rdi+r14*8]; struct _LSAPR_UNICODE_STRING *
0x180025fd3  mov     dword ptr [rsp+410h+hMem], 0
0x180025fdb  mov     [rbp+310h+var_388], 0
0x180025fe3  call    ?LsaDbpLookupNameTrustedDomainListEx@@YAJPEAU_LSAPR_UNICODE_STRING@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupNameTrustedDomainListEx(_LSAPR_UNICODE_STRING *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x180025fe8  xor     ecx, ecx
0x180025fea  mov     ebx, eax
0x180025fec  test    eax, eax
0x180025fee  js      loc_18002628F
0x180025ff4  mov     rax, cs:?LsaDbpPolicyHandle@@3PEAXEA; void * LsaDbpPolicyHandle
0x180025ffb  lea     edx, [rcx+20h]
0x180025ffe  mov     [rbp+310h+var_370], rax
0x180026002  lea     r9, [rsp+410h+var_3A8]
0x180026007  mov     rax, [rbp+310h+var_390]
0x18002600b  xor     r8d, r8d
0x18002600e  add     rax, 10h
0x180026012  mov     [rbp+310h+var_360], rcx
0x180026016  mov     [rbp+310h+var_340], ecx
0x180026019  mov     [rbp+310h+var_348], rcx
0x18002601d  mov     [rbp+310h+var_358], rcx
0x180026021  mov     [rbp+310h+var_350], rcx
0x180026025  lea     rcx, [rbp+310h+var_380]
0x180026029  mov     [rbp+310h+var_368], rax
0x18002602d  mov     [rbp+310h+var_378], 30h ; '0'
0x180026035  mov     [rbp+310h+var_380], 2
0x18002603d  mov     [rbp+310h+var_33C], edx
0x180026040  call    cs:__imp_LsapDbOpenObject
0x180026046  mov     ebx, eax
0x180026048  test    eax, eax
0x18002604a  js      loc_18002625C
0x180026050  mov     rcx, cs:?g_FTCache@@3PEAVFTCache@@EA; FTCache * g_FTCache
0x180026057  mov     rdx, [rdi+r14*8]; Buffer
0x18002605b  add     rcx, 8; Table
0x18002605f  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180026065  test    rax, rax
0x180026068  jz      loc_180026216
0x18002606e  lea     r8, [rbp+310h+var_388]; unsigned __int8 **
  ... truncated ...
```
