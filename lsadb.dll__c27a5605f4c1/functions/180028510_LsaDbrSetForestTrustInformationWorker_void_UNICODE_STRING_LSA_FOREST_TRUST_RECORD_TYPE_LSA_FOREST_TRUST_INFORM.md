# LsaDbrSetForestTrustInformationWorker(void *,_UNICODE_STRING *,LSA_FOREST_TRUST_RECORD_TYPE,_LSA_FOREST_TRUST_INFORMATION2 *,uchar,_LSA_FOREST_TRUST_COLLISION_INFORMATION * *)

- ea: `0x180028510`
- end: `0x180028c7c`
- name: `?LsaDbrSetForestTrustInformationWorker@@YAJPEAXPEAU_UNICODE_STRING@@W4LSA_FOREST_TRUST_RECORD_TYPE@@PEAU_LSA_FOREST_TRUST_INFORMATION2@@EPEAPEAU_LSA_FOREST_TRUST_COLLISION_INFORMATION@@@Z`
- size: `1900`
- prototype: `__int64 __fastcall(void *, struct _UNICODE_STRING *, int, struct _LSA_FOREST_TRUST_INFORMATION2 *, unsigned __int8, struct _LSA_FOREST_TRUST_COLLISION_INFORMATION **)`
- caller_count: `4`
- callee_count: `20`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18000a2bc`
- `0x180028290`
- `0x1800283d0`
- `0x180031abc`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x18000bf70`
- `0x18000c0e0`
- `0x18000fd18`
- `0x18000fd40`
- `0x180012fa4`
- `0x180020bc8`
- `0x180022350`
- `0x180022580`
- `0x1800268c0`
- `0x180027738`
- `0x180028510`
- `0x180028c84`
- `0x180029e14`
- `0x18002a320`
- `0x18002a7f8`
- `0x18002ae5c`
- `0x18002bd48`
- `0x180036e6c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028bc5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028bcf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028bc5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028bcf`
- `LSASRV!LsapDbCloseObject` at `0x180028bbb`
- `LSASRV!LsapDbCloseObject` at `0x180028bbb`
- `LSASRV!LsapDbWriteAttributesObject` at `0x180028a03`
- `LSASRV!LsapDbWriteAttributesObject` at `0x180028a03`
- `LSASRV!LsapDbOpenObject` at `0x18002882b`
- `LSASRV!LsapDbOpenObject` at `0x18002882b`
- `LSASRV!LsapTraceEvent` at `0x1800285d8`
- `LSASRV!LsapTraceEvent` at `0x180028c2e`
- `LSASRV!LsapTraceEvent` at `0x1800285d8`
- `LSASRV!LsapTraceEvent` at `0x180028c2e`
- `LSASRV!LsapDbDereferenceObject` at `0x180028c1e`
- `LSASRV!LsapDbDereferenceObject` at `0x180028c1e`
- `LSASRV!LsapGetAccountDomainHandle` at `0x1800285a5`
- `LSASRV!LsapGetAccountDomainHandle` at `0x1800285a5`
- `LSASRV!LsapDbInitializeAttribute` at `0x1800289d6`
- `LSASRV!LsapDbInitializeAttribute` at `0x1800289d6`
- `LSASRV!LsapDbReferenceObject` at `0x180028740`
- `LSASRV!LsapDbReferenceObject` at `0x180028740`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x18002876e`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x18002876e`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180028bf2`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180028bf2`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180028b78`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180028b78`
- `SAMSRV!SamIQueryServerRole` at `0x180028679`
- `SAMSRV!SamIQueryServerRole` at `0x180028679`

## pseudocode

```c
__int64 __fastcall LsaDbrSetForestTrustInformationWorker(
        void *a1,
        struct _UNICODE_STRING *a2,
        int a3,
        struct _LSA_FOREST_TRUST_INFORMATION2 *a4,
        unsigned __int8 a5,
        struct _LSA_FOREST_TRUST_COLLISION_INFORMATION **a6)
{
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v8; // r13
  __int64 v9; // rcx
  __int64 AccountDomainHandle; // rbx
  unsigned __int8 v11; // dl
  unsigned __int8 v12; // r8
  unsigned __int8 v13; // r9
  unsigned int v14; // ebx
  bool v15; // zf
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  struct _UNICODE_STRING *v25; // rdi
  struct _LSA_FOREST_TRUST_INFORMATION2 *v26; // rsi
  int v27; // ebx
  int ConflictInfo; // eax
  struct FTCache::TDO_ENTRY *v29; // r8
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  struct FTCache::CONFLICT_PAIR *v32; // rax
  struct _LSA_FOREST_TRUST_COLLISION_INFORMATION *v33; // rax
  _QWORD *v34; // rcx
  __int64 v35; // rbx
  TRACEHANDLE v36; // rcx
  const wchar_t *v37; // rdx
  _DWORD *p_Index; // r8
  struct FTCache::TDO_ENTRY *v39; // rcx
  const struct FTCache::TDO_ENTRY *v40; // rdx
  const struct FTCache::TDO_ENTRY *v41; // rax
  FTCache *v42; // rcx
  __int64 v43; // rcx
  unsigned __int16 v45; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v46; // [rsp+28h] [rbp-D8h]
  char v47; // [rsp+50h] [rbp-B0h]
  char v48; // [rsp+51h] [rbp-AFh]
  struct FTCache::TDO_ENTRY *v50; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v51; // [rsp+68h] [rbp-98h] BYREF
  int v52; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v53; // [rsp+70h] [rbp-90h] BYREF
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v54; // [rsp+78h] [rbp-88h] BYREF
  __int64 v55; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v56; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp-70h] BYREF
  void *v58; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v59[8]; // [rsp+A0h] [rbp-60h] BYREF
  int v60; // [rsp+E0h] [rbp-20h]
  int v61; // [rsp+E4h] [rbp-1Ch]
  __int16 v62; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v63[86]; // [rsp+F2h] [rbp-Eh] BYREF
  int v64; // [rsp+148h] [rbp+48h]
  _BYTE v65[32]; // [rsp+150h] [rbp+50h] BYREF
  int v66; // [rsp+170h] [rbp+70h]
  int v67; // [rsp+174h] [rbp+74h]

  v58 = a1;
  memset_0(v59, 0, 0x48u);
  v55 = 0;
  v48 = 0;
  v8 = 0;
  v47 = 0;
  v54 = 0;
  v53 = 0;
  hMem = 0;
  v62 = 0;
  memset_0(v63, 0, 0x5Eu);
  v50 = 0;
  v56 = 0;
  v51 = 0;
  v52 = 0;
  AccountDomainHandle = LsapGetAccountDomainHandle(v9);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 299, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
  LsapTraceEvent(1, 19);
  if ( *(_DWORD *)a4 > 0xFA0u )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 300, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    v14 = -1073740784;
    goto LABEL_82;
  }
  if ( !LsapValidateUnicodeStringWorker(a2, v11, v12, v13, v45, v46) || !LsaDbpValidateForestTrustInfo2(a4) )
  {
    v21 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v22 = 301;
      goto LABEL_80;
    }
LABEL_81:
    v14 = -1073741811;
    goto LABEL_82;
  }
  v15 = DcInRootDomain == 0;
  *a6 = 0;
  if ( v15 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    {
LABEL_13:
      v14 = -1073741603;
LABEL_82:
      v26 = a4;
      goto LABEL_83;
    }
    v17 = 302;
LABEL_12:
    WPP_SF_(v16[2], v17, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    goto LABEL_13;
  }
  v18 = SamIQueryServerRole(AccountDomainHandle, &v52);
  v14 = v18;
  if ( v18 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_82;
    v20 = 303;
LABEL_17:
    WPP_SF_d(v19[2], v20, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, (unsigned int)v18);
    goto LABEL_82;
  }
  if ( v52 != 3 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 304, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    v14 = -1073741602;
    goto LABEL_82;
  }
  if ( !LsaDbpNoMoreWin2KForest() )
  {
    v16 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_13;
    v17 = 305;
    goto LABEL_12;
  }
  if ( a3 > 4 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v22 = 306;
LABEL_80:
      WPP_SF_(v21[2], v22, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
      goto LABEL_81;
    }
    goto LABEL_81;
  }
  v18 = LsapDbReferenceObject(v58, 0, 1, 2);
  v14 = v18;
  if ( v18 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_82;
    v20 = 307;
    goto LABEL_17;
  }
  v48 = 1;
  v18 = LsapDbExpAcquireWriteLockTrustedDomainList(v23);
  v14 = v18;
  if ( v18 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_82;
    v20 = 308;
    goto LABEL_17;
  }
  v47 = 1;
  v24 = LsaDbpLookupNameTrustedDomainListEx((struct _LSAPR_UNICODE_STRING *)a2, &v54);
  v14 = v24;
  if ( v24 < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_ZD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        309,
        (unsigned int)&WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
        (_DWORD)a2,
        v24);
    v8 = v54;
    goto LABEL_82;
  }
  v8 = v54;
  v59[1] = 48;
  memset(&v59[4], 0, 32);
  v60 = 0;
  v25 = (struct _UNICODE_STRING *)((char *)v54 + 16);
  v59[0] = 2;
  v59[3] = (char *)v54 + 16;
  v61 = 32;
  v59[2] = v58;
  v18 = LsapDbOpenObject(v59, 32, 0, &v55, 1);
  v14 = v18;
  if ( v18 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_82;
    v20 = 310;
    goto LABEL_17;
  }
  v26 = a4;
  if ( !*(_DWORD *)a4 )
  {
    if ( a5 )
      goto LABEL_84;
LABEL_64:
    LsapDbInitializeAttribute(v65, 45, hMem);
    v66 = *((_DWORD *)LsaDbpDsAttInfo + 135);
    v67 = *((_DWORD *)LsaDbpDsAttInfo + 136);
    ConflictInfo = LsapDbWriteAttributesObject(v55, v65);
    v14 = ConflictInfo;
    if ( ConflictInfo >= 0 )
    {
      if ( *a6 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 316, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
          v33 = *a6;
          if ( (*a6)->RecordCount )
          {
            v34 = WPP_GLOBAL_Control;
            v35 = 0;
            do
            {
              if ( (*((_BYTE *)v34 + 28) & 8) != 0 )
              {
                v36 = v34[2];
                v37 = L"TDO";
                p_Index = &v33->Entries[v35]->Index;
                if ( p_Index[1] )
                  v37 = (const wchar_t *)L"XRef";
                WPP_SF_ddSdZ(v36, *p_Index, (__int64)v37, p_Index[2], (__int64)(p_Index + 4));
                v34 = WPP_GLOBAL_Control;
              }
              v33 = *a6;
              v35 = (unsigned int)(v35 + 1);
            }
            while ( (unsigned int)v35 < (*a6)->RecordCount );
          }
        }
      }
      v39 = v50;
      v14 = 0;
      goto LABEL_88;
    }
    v30 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_83;
    v31 = 315;
    goto LABEL_47;
  }
  v27 = *((_DWORD *)v8 + 16);
  if ( !LsaDbpNoMoreWin2KForest() || (v27 & 8) == 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 311, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    v14 = -1073741811;
    goto LABEL_83;
  }
  ConflictInfo = FTCache::Insert(
                   g_FTCache,
                   v25,
                   *((void **)v8 + 6),
                   a4,
                   0,
                   (struct FTCache::TDO_ENTRY *)&v62,
                   &v50,
                   (struct FTCache::CONFLICT_PAIR **)&v56,
                   &v51);
  v14 = ConflictInfo;
  if ( ConflictInfo >= 0 )
  {
    v32 = (struct FTCache::CONFLICT_PAIR *)v56;
    if ( v56 )
    {
      ConflictInfo = FTCache::GenerateConflictInfo((struct FTCache::CONFLICT_PAIR *)v56, v51, v29, a6);
      v14 = ConflictInfo;
      if ( ConflictInfo < 0 )
      {
        v30 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_83;
        v31 = 313;
        goto LABEL_47;
      }
      v32 = (struct FTCache::CONFLICT_PAIR *)v56;
    }
    if ( a5 )
      goto LABEL_84;
    if ( v32 )
      FTCache::ReconcileConflictPairs(v50, v32, v51);
    ConflictInfo = FTCache::MarshalBlob(v50, &v53, (unsigned __int8 **)&hMem);
    v14 = ConflictInfo;
    if ( ConflictInfo < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_83;
      v31 = 314;
      goto LABEL_47;
    }
    goto LABEL_64;
  }
  v30 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v31 = 312;
LABEL_47:
    WPP_SF_d(v30[2], v31, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, (unsigned int)ConflictInfo);
  }
LABEL_83:
  LsaDbpFreeCollisionInfo(a6);
LABEL_84:
  v39 = v50;
  if ( v50 )
  {
    FTCache::RollbackChanges(g_FTCache, v50, (struct FTCache::TDO_ENTRY *)&v62);
    v39 = 0;
    v50 = 0;
  }
  if ( (v14 & 0x80000000) == 0 && !a5 )
  {
LABEL_88:
    if ( v39 )
    {
      v40 = (const struct FTCache::TDO_ENTRY *)&v62;
      if ( !v64 )
        v40 = 0;
      FTCache::AuditChanges(g_FTCache, v40, v39);
    }
    else if ( !*(_DWORD *)v26 )
    {
      v41 = (const struct FTCache::TDO_ENTRY *)RtlLookupElementGenericTableAvl(
                                                 (PRTL_AVL_TABLE)((char *)g_FTCache + 8),
                                                 (char *)v8 + 16);
      if ( v41 )
        FTCache::AuditChanges(g_FTCache, v41, 0);
      v14 = FTCache::Remove(v42, (struct _UNICODE_STRING *)v8 + 1);
      if ( v14 == -1073741275 )
        v14 = 0;
    }
  }
  if ( v55 )
    LsapDbCloseObject(&v55, 0, v14);
  LocalFree(hMem);
  LocalFree(v56);
  if ( v64 )
    FTCache::PurgeTdoEntry(g_FTCache, (struct FTCache::TDO_ENTRY *)&v62);
  if ( v47 )
    LsapDbExpReleaseLockTrustedDomainList(v43);
  if ( v48 )
    v14 = LsapDbDereferenceObject(&v58, 1, 2, 16385, 0, v14);
  LsapTraceEvent(2, 19);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 318, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x180028510  push    rbp
0x180028512  push    rbx
0x180028513  push    rsi
0x180028514  push    rdi
0x180028515  push    r13
0x180028517  push    r14
0x180028519  push    r15
0x18002851b  lea     rbp, [rsp-2E0h]
0x180028523  sub     rsp, 3E0h
0x18002852a  mov     rax, cs:__security_cookie
0x180028531  xor     rax, rsp
0x180028534  mov     [rbp+310h+var_40], rax
0x18002853b  mov     r15, [rbp+310h+arg_28]
0x180028542  mov     rdi, rdx
0x180028545  xor     edx, edx; Val
0x180028547  mov     [rbp+310h+var_378], rcx
0x18002854b  mov     esi, r8d
0x18002854e  mov     [rsp+410h+var_3B8], r9
0x180028553  lea     rcx, [rbp+310h+var_370]; void *
0x180028557  lea     r8d, [rdx+48h]; Size
0x18002855b  call    memset_0
0x180028560  xor     ebx, ebx
0x180028562  lea     rcx, [rbp+310h+var_31E]; void *
0x180028566  xor     edx, edx; Val
0x180028568  mov     [rbp+310h+var_390], rbx
0x18002856c  mov     [rsp+410h+var_3BF], bl
0x180028570  mov     r13d, ebx
0x180028573  mov     [rsp+410h+var_3C0], bl
0x180028577  mov     r14d, ebx
0x18002857a  lea     r8d, [rbx+5Eh]; Size
0x18002857e  mov     [rsp+410h+var_398], rbx
0x180028583  mov     [rsp+410h+var_3A0], ebx
0x180028587  mov     [rbp+310h+hMem], rbx
0x18002858b  mov     [rbp+310h+var_320], bx
0x18002858f  call    memset_0
0x180028594  mov     [rsp+410h+var_3B0], rbx
0x180028599  mov     [rbp+310h+var_388], rbx
0x18002859d  mov     [rsp+410h+var_3A8], ebx
0x1800285a1  mov     [rsp+410h+var_3A4], ebx
0x1800285a5  call    cs:__imp_LsapGetAccountDomainHandle
0x1800285ab  mov     rbx, rax
0x1800285ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285b5  test    byte ptr [rcx+1Ch], 8
0x1800285b9  jz      short loc_1800285D0
0x1800285bb  mov     rcx, [rcx+10h]
0x1800285bf  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800285c6  mov     edx, 12Bh
0x1800285cb  call    WPP_SF_
0x1800285d0  mov     edx, 13h
0x1800285d5  lea     ecx, [rdx-12h]
0x1800285d8  call    cs:__imp_LsapTraceEvent
0x1800285de  mov     rax, [rsp+410h+var_3B8]
0x1800285e3  cmp     dword ptr [rax], 0FA0h
0x1800285e9  jbe     short loc_180028617
0x1800285eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285f2  test    byte ptr [rcx+1Ch], 8
0x1800285f6  jz      short loc_18002860D
0x1800285f8  mov     rcx, [rcx+10h]
0x1800285fc  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180028603  mov     edx, 12Ch
0x180028608  call    WPP_SF_
0x18002860d  mov     ebx, 0C0000410h
0x180028612  jmp     loc_180028B03
0x180028617  mov     rcx, rdi; SearchString
0x18002861a  call    ?LsapValidateUnicodeStringWorker@@YAEPEAU_UNICODE_STRING@@EEEGPEAG@Z; LsapValidateUnicodeStringWorker(_UNICODE_STRING *,uchar,uchar,uchar,ushort,ushort *)
0x18002861f  test    al, al
0x180028621  jz      loc_180028ADC
0x180028627  mov     rcx, [rsp+410h+var_3B8]; struct _LSA_FOREST_TRUST_INFORMATION2 *
0x18002862c  call    ?LsaDbpValidateForestTrustInfo2@@YAEPEAU_LSA_FOREST_TRUST_INFORMATION2@@@Z; LsaDbpValidateForestTrustInfo2(_LSA_FOREST_TRUST_INFORMATION2 *)
0x180028631  test    al, al
0x180028633  jz      loc_180028ADC
0x180028639  cmp     cs:?DcInRootDomain@@3EA, r13b; uchar DcInRootDomain
0x180028640  mov     [r15], r13
0x180028643  jnz     short loc_180028671
0x180028645  mov     rcx, cs:WPP_GLOBAL_Control
0x18002864c  test    byte ptr [rcx+1Ch], 8
0x180028650  jz      short loc_180028667
0x180028652  mov     edx, 12Eh
0x180028657  mov     rcx, [rcx+10h]
0x18002865b  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180028662  call    WPP_SF_
0x180028667  mov     ebx, 0C00000DDh
0x18002866c  jmp     loc_180028B03
0x180028671  lea     rdx, [rsp+410h+var_3A4]
0x180028676  mov     rcx, rbx
0x180028679  call    cs:__imp_SamIQueryServerRole
0x18002867f  mov     ebx, eax
0x180028681  test    eax, eax
0x180028683  jns     short loc_1800286B3
0x180028685  mov     rcx, cs:WPP_GLOBAL_Control
0x18002868c  test    byte ptr [rcx+1Ch], 8
0x180028690  jz      loc_180028B03
0x180028696  mov     edx, 12Fh
0x18002869b  mov     rcx, [rcx+10h]
0x18002869f  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800286a6  mov     r9d, eax
0x1800286a9  call    WPP_SF_d
0x1800286ae  jmp     loc_180028B03
0x1800286b3  cmp     [rsp+410h+var_3A4], 3
0x1800286b8  jz      short loc_1800286E6
0x1800286ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800286c1  test    byte ptr [rcx+1Ch], 8
0x1800286c5  jz      short loc_1800286DC
0x1800286c7  mov     rcx, [rcx+10h]
0x1800286cb  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800286d2  mov     edx, 130h
0x1800286d7  call    WPP_SF_
0x1800286dc  mov     ebx, 0C00000DEh
0x1800286e1  jmp     loc_180028B03
0x1800286e6  call    ?LsaDbpNoMoreWin2KForest@@YAEXZ; LsaDbpNoMoreWin2KForest(void)
0x1800286eb  test    al, al
0x1800286ed  jnz     short loc_18002870A
0x1800286ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800286f6  test    byte ptr [rcx+1Ch], 8
0x1800286fa  jz      loc_180028667
0x180028700  mov     edx, 131h
0x180028705  jmp     loc_180028657
0x18002870a  cmp     esi, 4
0x18002870d  jle     short loc_18002872A
0x18002870f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028716  test    byte ptr [rcx+1Ch], 8
0x18002871a  jz      loc_180028AFE
0x180028720  mov     edx, 132h
0x180028725  jmp     loc_180028AEE
0x18002872a  mov     rcx, [rbp+310h+var_378]
0x18002872e  mov     eax, 1
0x180028733  mov     r8d, eax
0x180028736  mov     dword ptr [rsp+410h+var_3F0], eax
0x18002873a  xor     edx, edx
0x18002873c  lea     r9d, [rax+1]
0x180028740  call    cs:__imp_LsapDbReferenceObject
0x180028746  xor     esi, esi
0x180028748  mov     ebx, eax
0x18002874a  test    eax, eax
0x18002874c  jns     short loc_180028769
0x18002874e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028755  test    byte ptr [rcx+1Ch], 8
0x180028759  jz      loc_180028B03
0x18002875f  mov     edx, 133h
0x180028764  jmp     loc_18002869B
0x180028769  mov     [rsp+410h+var_3BF], 1
0x18002876e  call    cs:__imp_LsapDbExpAcquireWriteLockTrustedDomainList
0x180028774  mov     ebx, eax
0x180028776  test    eax, eax
0x180028778  jns     short loc_180028795
0x18002877a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028781  test    byte ptr [rcx+1Ch], 8
0x180028785  jz      loc_180028B03
0x18002878b  mov     edx, 134h
0x180028790  jmp     loc_18002869B
0x180028795  lea     rdx, [rsp+410h+var_398]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18002879a  mov     [rsp+410h+var_3C0], 1
0x18002879f  mov     rcx, rdi; struct _LSAPR_UNICODE_STRING *
0x1800287a2  call    ?LsaDbpLookupNameTrustedDomainListEx@@YAJPEAU_LSAPR_UNICODE_STRING@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupNameTrustedDomainListEx(_LSAPR_UNICODE_STRING *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x1800287a7  mov     ebx, eax
0x1800287a9  test    eax, eax
0x1800287ab  jns     short loc_1800287E0
0x1800287ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287b4  test    byte ptr [rcx+1Ch], 8
0x1800287b8  jz      short loc_1800287D6
0x1800287ba  mov     rcx, [rcx+10h]
0x1800287be  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800287c5  mov     edx, 135h
0x1800287ca  mov     dword ptr [rsp+410h+var_3F0], eax
0x1800287ce  mov     r9, rdi
0x1800287d1  call    WPP_SF_ZD
0x1800287d6  mov     r13, [rsp+410h+var_398]
0x1800287db  jmp     loc_180028B03
0x1800287e0  mov     rax, [rbp+310h+var_378]
0x1800287e4  lea     r9, [rbp+310h+var_390]
0x1800287e8  mov     r13, [rsp+410h+var_398]
0x1800287ed  lea     rcx, [rbp+310h+var_370]
0x1800287f1  mov     edx, 20h ; ' '
0x1800287f6  mov     [rbp+310h+var_368], 30h ; '0'
0x1800287fe  xor     r8d, r8d
0x180028801  mov     [rbp+310h+var_350], rsi
0x180028805  mov     [rbp+310h+var_330], esi
0x180028808  lea     rdi, [r13+10h]
0x18002880c  mov     [rbp+310h+var_370], 2
0x180028814  mov     [rbp+310h+var_358], rdi
0x180028818  mov     [rbp+310h+var_338], rsi
0x18002881c  mov     [rbp+310h+var_32C], edx
0x18002881f  mov     [rbp+310h+var_360], rax
0x180028823  mov     [rbp+310h+var_348], rsi
0x180028827  mov     [rbp+310h+var_340], rsi
0x18002882b  call    cs:__imp_LsapDbOpenObject
0x180028831  mov     ebx, eax
0x180028833  test    eax, eax
0x180028835  jns     short loc_180028852
0x180028837  mov     rcx, cs:WPP_GLOBAL_Control
0x18002883e  test    byte ptr [rcx+1Ch], 8
0x180028842  jz      loc_180028B03
0x180028848  mov     edx, 136h
0x18002884d  jmp     loc_18002869B
0x180028852  mov     rsi, [rsp+410h+var_3B8]
0x180028857  cmp     [rsi], r14d
0x18002885a  jbe     loc_1800289B4
0x180028860  mov     ebx, [r13+40h]
0x180028864  call    ?LsaDbpNoMoreWin2KForest@@YAEXZ; LsaDbpNoMoreWin2KForest(void)
0x180028869  test    al, al
0x18002886b  jz      loc_180028988
0x180028871  test    bl, 8
0x180028874  jz      loc_180028988
0x18002887a  mov     r8, [r13+30h]; void *
0x18002887e  lea     rax, [rsp+410h+var_3A8]
0x180028883  mov     rcx, cs:?g_FTCache@@3PEAVFTCache@@EA; this
0x18002888a  mov     r9, rsi; struct _LSA_FOREST_TRUST_INFORMATION2 *
0x18002888d  mov     [rsp+410h+var_3D0], rax; unsigned int *
0x180028892  mov     rdx, rdi; struct _UNICODE_STRING *
0x180028895  lea     rax, [rbp+310h+var_388]
0x180028899  mov     [rsp+410h+var_3D8], rax; struct FTCache::CONFLICT_PAIR **
0x18002889e  lea     rax, [rsp+410h+var_3B0]
0x1800288a3  mov     [rsp+410h+var_3E0], rax; struct FTCache::TDO_ENTRY **
0x1800288a8  lea     rax, [rbp+310h+var_320]
0x1800288ac  mov     [rsp+410h+var_3E8], rax; struct FTCache::TDO_ENTRY *
0x1800288b1  mov     byte ptr [rsp+410h+var_3F0], r14b; unsigned __int8
0x1800288b6  call    ?Insert@FTCache@@AEAAJPEAU_UNICODE_STRING@@PEAXPEAU_LSA_FOREST_TRUST_INFORMATION2@@EPEAUTDO_ENTRY@1@PEAPEAU41@PEAPEAUCONFLICT_PAIR@1@PEAK@Z; FTCache::Insert(_UNICODE_STRING *,void *,_LSA_FOREST_TRUST_INFORMATION2 *,uchar,FTCache::TDO_ENTRY *,FTCache::TDO_ENTRY * *,FTCache::CONFLICT_PAIR * *,ulong *)
0x1800288bb  mov     ebx, eax
0x1800288bd  test    eax, eax
0x1800288bf  jns     short loc_1800288EF
0x1800288c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800288c8  test    byte ptr [rcx+1Ch], 8
0x1800288cc  jz      loc_180028B08
0x1800288d2  mov     edx, 138h
0x1800288d7  mov     rcx, [rcx+10h]
0x1800288db  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800288e2  mov     r9d, eax
0x1800288e5  call    WPP_SF_d
0x1800288ea  jmp     loc_180028B08
0x1800288ef  mov     rax, [rbp+310h+var_388]
0x1800288f3  test    rax, rax
0x1800288f6  jz      short loc_180028929
0x1800288f8  mov     edx, [rsp+410h+var_3A8]; unsigned int
0x1800288fc  mov     r9, r15; struct _LSA_FOREST_TRUST_COLLISION_INFORMATION **
0x1800288ff  mov     rcx, rax; struct FTCache::CONFLICT_PAIR *
0x180028902  call    ?GenerateConflictInfo@FTCache@@CAJPEAUCONFLICT_PAIR@1@KPEAUTDO_ENTRY@1@PEAPEAU_LSA_FOREST_TRUST_COLLISION_INFORMATION@@@Z; FTCache::GenerateConflictInfo(FTCache::CONFLICT_PAIR *,ulong,FTCache::TDO_ENTRY *,_LSA_FOREST_TRUST_COLLISION_INFORMATION * *)
0x180028907  mov     ebx, eax
0x180028909  test    eax, eax
0x18002890b  jns     short loc_180028925
0x18002890d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028914  test    byte ptr [rcx+1Ch], 8
0x180028918  jz      loc_180028B08
0x18002891e  mov     edx, 139h
0x180028923  jmp     short loc_1800288D7
0x180028925  mov     rax, [rbp+310h+var_388]
0x180028929  cmp     [rbp+310h+arg_20], r14b
0x180028930  jnz     loc_180028B10
0x180028936  test    rax, rax
0x180028939  jz      short loc_18002894D
0x18002893b  mov     r8d, [rsp+410h+var_3A8]; unsigned int
0x180028940  mov     rdx, rax; struct FTCache::CONFLICT_PAIR *
0x180028943  mov     rcx, [rsp+410h+var_3B0]; struct FTCache::TDO_ENTRY *
0x180028948  call    ?ReconcileConflictPairs@FTCache@@CAXPEBUTDO_ENTRY@1@PEAUCONFLICT_PAIR@1@K@Z; FTCache::ReconcileConflictPairs(FTCache::TDO_ENTRY const *,FTCache::CONFLICT_PAIR *,ulong)
0x18002894d  mov     rcx, [rsp+410h+var_3B0]; struct FTCache::TDO_ENTRY *
0x180028952  lea     r8, [rbp+310h+hMem]; unsigned __int8 **
0x180028956  lea     rdx, [rsp+410h+var_3A0]; unsigned int *
0x18002895b  call    ?MarshalBlob@FTCache@@CAJPEAUTDO_ENTRY@1@PEAKPEAPEAE@Z; FTCache::MarshalBlob(FTCache::TDO_ENTRY *,ulong *,uchar * *)
0x180028960  mov     ebx, eax
0x180028962  test    eax, eax
0x180028964  jns     short loc_180028981
0x180028966  mov     rcx, cs:WPP_GLOBAL_Control
0x18002896d  test    byte ptr [rcx+1Ch], 8
0x180028971  jz      loc_180028B08
0x180028977  mov     edx, 13Ah
0x18002897c  jmp     loc_1800288D7
0x180028981  mov     r14d, [rsp+410h+var_3A0]
0x180028986  jmp     short loc_1800289C1
0x180028988  mov     rcx, cs:WPP_GLOBAL_Control
0x18002898f  test    byte ptr [rcx+1Ch], 8
0x180028993  jz      short loc_1800289AA
0x180028995  mov     rcx, [rcx+10h]
0x180028999  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800289a0  mov     edx, 137h
0x1800289a5  call    WPP_SF_
0x1800289aa  mov     ebx, 0C000000Dh
0x1800289af  jmp     loc_180028B08
0x1800289b4  cmp     [rbp+310h+arg_20], r14b
0x1800289bb  jnz     loc_180028B10
0x1800289c1  mov     r8, [rbp+310h+hMem]
0x1800289c5  lea     rcx, [rbp+310h+var_2C0]
0x1800289c9  mov     r9d, r14d
0x1800289cc  mov     byte ptr [rsp+410h+var_3F0], 0
0x1800289d1  mov     edx, 2Dh ; '-'
0x1800289d6  call    cs:__imp_LsapDbInitializeAttribute
0x1800289dc  mov     rcx, cs:?LsaDbpDsAttInfo@@3PEAU_LSAP_DB_DS_INFO@@EA; _LSAP_DB_DS_INFO * LsaDbpDsAttInfo
0x1800289e3  lea     rdx, [rbp+310h+var_2C0]
0x1800289e7  mov     r8d, 1
0x1800289ed  mov     eax, [rcx+21Ch]
0x1800289f3  mov     [rbp+310h+var_2A0], eax
0x1800289f6  mov     eax, [rcx+220h]
0x1800289fc  mov     rcx, [rbp+310h+var_390]
0x180028a00  mov     [rbp+310h+var_29C], eax
0x180028a03  call    cs:__imp_LsapDbWriteAttributesObject
0x180028a09  mov     ebx, eax
0x180028a0b  test    eax, eax
0x180028a0d  jns     short loc_180028A2A
0x180028a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a16  test    byte ptr [rcx+1Ch], 8
0x180028a1a  jz      loc_180028B08
0x180028a20  mov     edx, 13Bh
  ... truncated ...
```
