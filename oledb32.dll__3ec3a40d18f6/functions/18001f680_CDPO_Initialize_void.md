# CDPO::Initialize(void)

- ea: `0x18001f680`
- end: `0x18001fd90`
- name: `?Initialize@CDPO@@UEAAJXZ`
- size: `1808`
- prototype: `__int64 __fastcall(CDPO *__hidden this)`
- caller_count: `0`
- callee_count: `25`
- tags: `broker_com_uri`

## callees

- `0x180013870`
- `0x18001adec`
- `0x18001f680`
- `0x180021310`
- `0x180029560`
- `0x180029b58`
- `0x180029c30`
- `0x18002b0f4`
- `0x18003c270`
- `0x18004a084`
- `0x18005b330`
- `0x18005b3a0`
- `0x18005bd4c`
- `0x18005de9c`
- `0x18005eab0`
- `0x180060ca0`
- `0x180066a5c`
- `0x180066d10`
- `0x18006c84c`
- `0x180073f4c`
- `0x1800771ac`
- `0x180078108`
- `0x18007e6be`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `MSDART!mpFree` at `0x18001f903`
- `MSDART!mpFree` at `0x18001f903`
- `KERNEL32!EnterCriticalSection` at `0x18001f6ff`
- `KERNEL32!EnterCriticalSection` at `0x18001fa93`
- `KERNEL32!EnterCriticalSection` at `0x18001f6ff`
- `KERNEL32!EnterCriticalSection` at `0x18001fa93`
- `KERNEL32!LeaveCriticalSection` at `0x18001fa41`
- `KERNEL32!LeaveCriticalSection` at `0x18001fafd`
- `KERNEL32!LeaveCriticalSection` at `0x18001fa41`
- `KERNEL32!LeaveCriticalSection` at `0x18001fafd`
- `OLEAUT32!__imp_VariantCopy` at `0x18001fc7a`
- `OLEAUT32!__imp_VariantCopy` at `0x18001fc7a`

## pseudocode

```c
__int64 __fastcall CDPO::Initialize(CDPO *this)
{
  CDPO *v1; // r14
  unsigned int BidID; // eax
  __int64 v3; // r9
  char *v4; // r15
  CDPO *v5; // rcx
  int DCM; // eax
  int v7; // edi
  int v8; // ebx
  int v9; // eax
  int v10; // eax
  CConnStrParsingManager *v11; // rcx
  __int64 v12; // rdx
  unsigned __int8 *v13; // r13
  int v14; // eax
  unsigned int v15; // r8d
  int v16; // ecx
  __int64 v17; // rax
  __int64 v18; // rdi
  int SHA256Hash; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  _BYTE *v23; // rcx
  __int64 v24; // rsi
  __int64 v25; // rbx
  int v26; // edi
  int v27; // eax
  int v28; // eax
  char v29; // cl
  unsigned int v30; // eax
  int v31; // r9d
  __int64 v32; // r10
  __int64 v33; // rcx
  int v34; // eax
  int v35; // edi
  int v36; // eax
  int v37; // eax
  __int64 v38; // rax
  int (__fastcall ***v39)(_QWORD, GUID *, __int64 *); // r10
  const struct tagVARIANT **v40; // rax
  struct tagDBPROPSET *v41; // rdi
  unsigned int v42; // esi
  unsigned int v43; // r12d
  const struct tagVARIANT **v44; // r14
  const struct tagVARIANT *v45; // r13
  DBPROP *rgProperties; // r15
  int v47; // ecx
  unsigned int v48; // eax
  struct tagDBPROPSET **v50; // [rsp+20h] [rbp-99h]
  int v51; // [rsp+28h] [rbp-91h]
  unsigned int v52[2]; // [rsp+30h] [rbp-89h]
  char v53; // [rsp+60h] [rbp-59h]
  _BYTE pbInput[15]; // [rsp+61h] [rbp-58h] BYREF
  unsigned int v55; // [rsp+70h] [rbp-49h]
  unsigned int v56; // [rsp+78h] [rbp-41h] BYREF
  struct tagDBPROPSET *v57; // [rsp+80h] [rbp-39h] BYREF
  __int64 v58; // [rsp+88h] [rbp-31h] BYREF
  __int64 v59; // [rsp+90h] [rbp-29h] BYREF
  CDPO *v60; // [rsp+98h] [rbp-21h]
  UCHAR pbOutput[32]; // [rsp+A0h] [rbp-19h] BYREF

  v60 = this;
  pbInput[0] = 0;
  v1 = this;
  v59 = -1;
  if ( (bidGblFlags & 4) != 0 && off_1800C95A0[0] )
  {
    BidID = CDPO::GetBidID((CDPO *)((char *)this - 8));
    bidScopeEnterW(&v59, off_1800C95A0[0], BidID, v3);
  }
  v4 = (char *)v1 - 8;
  if ( *((_QWORD *)v1 + 11) )
  {
    if ( *((_QWORD *)v1 + 13)
      || (*((_BYTE *)v1 + 224) & 2) != 0
      || !CDPO::ShouldDoEnlistment((CDPO *)((char *)v1 - 8))
      || (v8 = CDCMCreator::EnlistDataSource(v33, (char *)v1 - 8, (char *)v1 + 88), v8 >= 0) )
    {
      if ( (*((_BYTE *)v1 + 224) & 1) != 0 )
      {
        v8 = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)v1 + 1);
        if ( (v4[232] & 1) != 0 && (v34 = CDPO::CompleteSettingProps((CDPO *)((char *)v1 - 8)), v8 = v34, v34 < 0) )
        {
          if ( (bidGblFlags & 2) != 0 )
            OLEDBTraceErr(v34, L"<CDPO::Initialize|OLEDB|ERR> ", 0x138u);
          v35 = v8;
        }
        else
        {
          v36 = CDPO::UnlockedDCMInit((CDPO *)((char *)v1 - 8));
          v35 = v36;
          if ( (bidGblFlags & 2) != 0 )
            OLEDBTraceErr(v36, L"<CDPO::Initialize|OLEDB|ERR> ", 0x13Fu);
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)v1 + 1);
        if ( v35 )
          v8 = v35;
      }
      else
      {
        v37 = CDPO::UnlockedDCMInit((CDPO *)((char *)v1 - 8));
        v8 = v37;
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v37, L"<CDPO::Initialize|OLEDB|ERR> ", 0x14Eu);
      }
    }
    goto LABEL_71;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)v1 + 1);
  v5 = (CDPO *)((char *)v1 - 8);
  if ( *((_QWORD *)v1 + 11) )
  {
    v8 = CDPO::UnlockedDCMInit(v5);
    goto LABEL_53;
  }
  if ( !CDPO::ShouldPoolDCM(v5) )
  {
    v57 = 0;
    *(_QWORD *)&pbInput[7] = 0;
    CDPO::CleanUpOptimizedInfo((CDPO *)((char *)v1 - 8));
    DCM = CDPO::GetDCM((CDPO *)((char *)v1 - 8));
    v7 = DCM;
    if ( DCM >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(struct tagDBPROPSET *, GUID *, _BYTE *))v57->rgProperties->dwPropertyID)(
             v57,
             &IID_IDBInitialize,
             &pbInput[7]);
      v8 = v9;
      if ( v9 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&pbInput[7] + 24LL))(*(_QWORD *)&pbInput[7]);
        v8 = v10;
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v10, L"<CDPO::Initialize|OLEDB|ERR> ", 0x90u);
        if ( v8 >= 0 && *((_BYTE *)v1 + 265) )
          CConnStrParsingManager::InsertConnStrParsingCacheItem(v11, (CDPO *)((char *)v1 - 8));
        _InterlockedIncrement(&dword_1800BEF28);
      }
      else if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v9, L"<CDPO::Initialize|OLEDB|ERR> ", 0x8Bu);
      }
    }
    else
    {
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(DCM, L"<CDPO::Initialize|OLEDB|ERR> ", 0x84u);
      v8 = v7;
    }
    if ( *(_QWORD *)&pbInput[7] )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pbInput[7] + 16LL))(*(_QWORD *)&pbInput[7]);
    if ( !v8 )
      v8 = v7;
    goto LABEL_53;
  }
  v12 = *((_QWORD *)v4 + 31);
  v53 = 0;
  if ( !v12 )
  {
LABEL_30:
    *(_QWORD *)&pbInput[7] = 0;
    if ( !v12 )
      goto LABEL_32;
    goto LABEL_31;
  }
  if ( (*((_BYTE *)v1 + 264) & 4) != 0 && ((*((_BYTE *)v1 + 152) ^ *(_BYTE *)(*(_QWORD *)(v12 + 840) + 160LL)) & 1) == 0 )
  {
    v13 = *(unsigned __int8 **)(v12 + 568);
    if ( v13 )
    {
      v55 = *(_DWORD *)(v12 + 832);
LABEL_45:
      v24 = *((_QWORD *)v1 + 12);
      v25 = *((_QWORD *)v1 + 16);
      v26 = *((_DWORD *)v1 + 30);
      v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 48LL))((__int64)v1 - 8);
      v28 = CDCMPoolManager::DrawResource(
              v24,
              (unsigned int)*((_QWORD *)v1 + 14) + 32,
              v27,
              v26,
              v25,
              v13,
              v55,
              v53,
              (CDPO *)((char *)v1 - 8),
              (__int64)v1 + 104,
              (__int64)v1 + 88,
              (__int64)pbInput);
      v29 = bidGblFlags;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v28, L"<CDPO::Initialize|OLEDB|ERR> ", 0xF7u);
        v29 = bidGblFlags;
      }
      v8 = *((_DWORD *)v1 + 48);
      if ( v8 < 0 )
      {
        if ( (v29 & 2) != 0 && off_1800C9338[0] )
        {
          v30 = HashForTrace(v13, v55);
          bidTraceW(off_1800C8448[0], 273408, off_1800C9338[0], v30, (_DWORD)v1 - 8, v31, v32);
        }
      }
      else
      {
        *((_QWORD *)v1 + 26) = *(_QWORD *)(*((_QWORD *)v1 + 12) + 80LL);
      }
      goto LABEL_53;
    }
    goto LABEL_30;
  }
  *(_QWORD *)&pbInput[7] = 0;
LABEL_31:
  CDPO::CleanUpOptimizedInfo((CDPO *)((char *)v1 - 8));
  v53 = 1;
LABEL_32:
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v4 + 56LL))((__int64)v1 - 8, 1, &pbInput[7]);
  v8 = v14;
  if ( v14 >= 0 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)(*(_QWORD *)&pbInput[7] + 2 * v17) );
    v18 = 2 * v17;
    SHA256Hash = GetSHA256Hash(*(PUCHAR *)&pbInput[7], 2 * (int)v17, pbOutput);
    v23 = *(_BYTE **)&pbInput[7];
    v8 = SHA256Hash;
    if ( v18 )
    {
      do
      {
        *v23++ = 0;
        --v18;
      }
      while ( v18 );
      v23 = *(_BYTE **)&pbInput[7];
    }
    mpFree(v23, v20, v21, v22);
    if ( v8 >= 0 )
    {
      v13 = pbOutput;
      v55 = 32;
      goto LABEL_45;
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      v15 = 225;
      v16 = v8;
      goto LABEL_35;
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    v15 = 212;
    v16 = v14;
LABEL_35:
    OLEDBTraceErr(v16, L"<CDPO::Initialize|OLEDB|ERR> ", v15);
  }
LABEL_53:
  LeaveCriticalSection((LPCRITICAL_SECTION)v1 + 1);
LABEL_71:
  if ( !*((_QWORD *)v1 + 11) )
    goto LABEL_95;
  v38 = TDSLSetArray<CDSLPropertySet,CDSLProperty>::Find((char *)v1 + 136, &DBPROPSET_DBINIT, 64);
  if ( !v38 )
    goto LABEL_94;
  if ( *(_WORD *)(v38 + 48) != 2 )
    goto LABEL_94;
  if ( *(_WORD *)(v38 + 56) == 4 )
    goto LABEL_94;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  if ( (**v39)(v39, &IID_IDBProperties, &v58) < 0 )
    goto LABEL_94;
  v50 = &v57;
  if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v58 + 24LL))(
         v58,
         *(unsigned int *)(*((_QWORD *)v1 + 14) + 1224LL),
         *(_QWORD *)(*((_QWORD *)v1 + 14) + 1232LL),
         &v56) < 0 )
    goto LABEL_94;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
  v40 = (const struct tagVARIANT **)*((_QWORD *)v1 + 18);
  v41 = v57;
  *(_DWORD *)&pbInput[7] = 0;
  v42 = v56;
  if ( !v56 )
    goto LABEL_93;
  v43 = *(_DWORD *)&pbInput[7];
  v44 = v40;
  do
  {
    v45 = *v44;
    rgProperties = v41->rgProperties;
    v47 = memcmp_0((char *)v44 + 12, &DBPROPSET_DBINIT, 0x10u) == 0;
    v48 = 0;
    *(_DWORD *)&pbInput[7] = v47;
    v55 = 0;
    if ( !v41->cProperties )
      goto LABEL_91;
    while ( rgProperties->dwPropertyID == 248 )
    {
LABEL_89:
      ++v48;
      v45 += 3;
      ++rgProperties;
      v55 = v48;
      if ( v48 >= v41->cProperties )
        goto LABEL_90;
    }
    if ( !v47
      || rgProperties->dwPropertyID != 9 && rgProperties->dwPropertyID != 160
      || (int)CDSLComVariant::EncryptBSTRValue(&rgProperties->vValue) >= 0 )
    {
      if ( !VariantCompare(&rgProperties->vValue, v45 + 2) )
      {
        if ( VariantCopy((VARIANTARG *)&v45[2], &rgProperties->vValue) < 0 )
          goto LABEL_90;
        v45->decVal.Hi32 &= ~0x80000000;
      }
      v47 = *(_DWORD *)&pbInput[7];
      v48 = v55;
      goto LABEL_89;
    }
LABEL_90:
    v42 = v56;
LABEL_91:
    ++v43;
    v44 += 4;
    ++v41;
  }
  while ( v43 < v42 );
  v41 = v57;
  v1 = v60;
LABEL_93:
  FreePropSets(v42, v41);
LABEL_94:
  CDCM::RestoreErrorObject((CDCM *)(*((_QWORD *)v1 + 11) + 24LL));
LABEL_95:
  *((_DWORD *)v1 + 49) |= 1u;
  if ( (bidGblFlags & 2) != 0 && off_1800C9330[0] )
    bidTraceW(off_1800C8448[0], 430080, off_1800C9330[0], (unsigned int)v8, (_DWORD)v50, v51, *(_QWORD *)v52);
  if ( (bidGblFlags & 4) != 0 && v59 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v59);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C8448[0], 432137, L"<CDPO::Initialize|Trace|HR> ", (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001f680  push    rbp
0x18001f682  push    rbx
0x18001f683  push    rsi
0x18001f684  push    rdi
0x18001f685  push    r12
0x18001f687  push    r13
0x18001f689  push    r14
0x18001f68b  push    r15
0x18001f68d  lea     rbp, [rsp-1Fh]
0x18001f692  sub     rsp, 0D8h
0x18001f699  mov     rax, cs:__security_cookie
0x18001f6a0  xor     rax, rsp
0x18001f6a3  mov     [rbp+57h+var_50], rax
0x18001f6a7  xor     esi, esi
0x18001f6a9  mov     [rbp+57h+var_78], rcx
0x18001f6ad  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001f6b1  mov     [rbp+57h+pbInput], sil
0x18001f6b5  test    byte ptr cs:_bidGblFlags, 4
0x18001f6bc  mov     r14, rcx
0x18001f6bf  mov     [rbp+57h+var_80], rdi
0x18001f6c3  jz      short loc_18001F6ED
0x18001f6c5  mov     rax, cs:off_1800C95A0; "<IDBInitialize::Initialize|API|OLEDB> %"...
0x18001f6cc  test    rax, rax
0x18001f6cf  jz      short loc_18001F6ED
0x18001f6d1  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x18001f6d5  call    ?GetBidID@CDPO@@AEAAHXZ; CDPO::GetBidID(void)
0x18001f6da  mov     rdx, cs:off_1800C95A0; "<IDBInitialize::Initialize|API|OLEDB> %"...
0x18001f6e1  lea     rcx, [rbp+57h+var_80]
0x18001f6e5  mov     r8d, eax
0x18001f6e8  call    _bidScopeEnterW
0x18001f6ed  lea     r15, [r14-8]
0x18001f6f1  cmp     [r15+60h], rsi
0x18001f6f5  jnz     loc_18001FA4C
0x18001f6fb  lea     rcx, [r14+28h]; lpCriticalSection
0x18001f6ff  call    cs:__imp_EnterCriticalSection
0x18001f705  mov     r12d, 2
0x18001f70b  mov     rcx, r15; this
0x18001f70e  cmp     [r14+58h], rsi
0x18001f712  jnz     loc_18001FA36
0x18001f718  call    ?ShouldPoolDCM@CDPO@@AEAA_NXZ; CDPO::ShouldPoolDCM(void)
0x18001f71d  test    al, al
0x18001f71f  jnz     loc_18001F81C
0x18001f725  mov     rcx, r15; this
0x18001f728  mov     [rbp+57h+var_90], rsi
0x18001f72c  mov     qword ptr [rbp+57h+pbInput+7], rsi
0x18001f730  call    ?CleanUpOptimizedInfo@CDPO@@QEAAXXZ; CDPO::CleanUpOptimizedInfo(void)
0x18001f735  mov     r8d, r12d
0x18001f738  lea     rdx, [rbp+57h+var_90]
0x18001f73c  mov     rcx, r15; CDPO *
0x18001f73f  call    ?GetDCM@CDPO@@AEAAJPEAPEAV?$CACMComPolyObject@VCDCM@@@@W4DPOATTACHSTATE@1@@Z; CDPO::GetDCM(CACMComPolyObject<CDCM> * *,CDPO::DPOATTACHSTATE)
0x18001f744  mov     edi, eax
0x18001f746  test    eax, eax
0x18001f748  jns     short loc_18001F76E
0x18001f74a  test    byte ptr cs:_bidGblFlags, r12b
0x18001f751  jz      short loc_18001F767
0x18001f753  mov     r8d, 84h; unsigned int
0x18001f759  lea     rdx, aCdpoInitialize_3; "<CDPO::Initialize|OLEDB|ERR> "
0x18001f760  mov     ecx, eax; int
0x18001f762  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001f767  mov     ebx, edi
0x18001f769  jmp     loc_18001F7F8
0x18001f76e  mov     rcx, [rbp+57h+var_90]
0x18001f772  lea     r8, [rbp+57h+pbInput+7]
0x18001f776  lea     rdx, IID_IDBInitialize
0x18001f77d  mov     rax, [rcx]
0x18001f780  mov     rax, [rax]
0x18001f783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f788  mov     ebx, eax
0x18001f78a  test    eax, eax
0x18001f78c  jns     short loc_18001F7AD
0x18001f78e  test    byte ptr cs:_bidGblFlags, r12b
0x18001f795  jz      short loc_18001F7F8
0x18001f797  mov     r8d, 8Bh; unsigned int
0x18001f79d  lea     rdx, aCdpoInitialize_3; "<CDPO::Initialize|OLEDB|ERR> "
0x18001f7a4  mov     ecx, eax; int
0x18001f7a6  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001f7ab  jmp     short loc_18001F7F8
0x18001f7ad  mov     rcx, qword ptr [rbp+57h+pbInput+7]
0x18001f7b1  mov     rax, [rcx]
0x18001f7b4  mov     rax, [rax+18h]
0x18001f7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7bd  test    byte ptr cs:_bidGblFlags, r12b
0x18001f7c4  mov     ebx, eax
0x18001f7c6  jz      short loc_18001F7DC
0x18001f7c8  mov     r8d, 90h; unsigned int
0x18001f7ce  lea     rdx, aCdpoInitialize_3; "<CDPO::Initialize|OLEDB|ERR> "
0x18001f7d5  mov     ecx, eax; int
0x18001f7d7  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001f7dc  test    ebx, ebx
0x18001f7de  js      short loc_18001F7F1
0x18001f7e0  cmp     [r14+109h], sil
0x18001f7e7  jz      short loc_18001F7F1
0x18001f7e9  mov     rdx, r15; struct CDPO *
0x18001f7ec  call    ?InsertConnStrParsingCacheItem@CConnStrParsingManager@@QEAAJPEAVCDPO@@@Z; CConnStrParsingManager::InsertConnStrParsingCacheItem(CDPO *)
0x18001f7f1  lock inc cs:dword_1800BEF28
0x18001f7f8  mov     rcx, qword ptr [rbp+57h+pbInput+7]
0x18001f7fc  test    rcx, rcx
0x18001f7ff  jz      short loc_18001F80D
0x18001f801  mov     rax, [rcx]
0x18001f804  mov     rax, [rax+10h]
0x18001f808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f80d  test    ebx, ebx
0x18001f80f  jnz     loc_18001FA3D
0x18001f815  mov     ebx, edi
0x18001f817  jmp     loc_18001FA3D
0x18001f81c  mov     rdx, [r15+0F8h]
0x18001f823  mov     [rbp+57h+var_B0], sil
0x18001f827  test    rdx, rdx
0x18001f82a  jz      short loc_18001F86F
0x18001f82c  test    byte ptr [r14+108h], 4
0x18001f834  jz      short loc_18001F869
0x18001f836  mov     rax, [rdx+348h]
0x18001f83d  mov     cl, [rax+0A0h]
0x18001f843  xor     cl, [r14+98h]
0x18001f84a  test    cl, 1
0x18001f84d  jnz     short loc_18001F869
0x18001f84f  mov     r13, [rdx+238h]
0x18001f856  test    r13, r13
0x18001f859  jz      short loc_18001F86F
0x18001f85b  mov     eax, [rdx+340h]
0x18001f861  mov     [rbp+57h+var_A0], eax
0x18001f864  jmp     loc_18001F92F
0x18001f869  mov     qword ptr [rbp+57h+pbInput+7], rsi
0x18001f86d  jmp     short loc_18001F878
0x18001f86f  mov     qword ptr [rbp+57h+pbInput+7], rsi
0x18001f873  test    rdx, rdx
0x18001f876  jz      short loc_18001F884
0x18001f878  mov     rcx, r15; this
0x18001f87b  call    ?CleanUpOptimizedInfo@CDPO@@QEAAXXZ; CDPO::CleanUpOptimizedInfo(void)
0x18001f880  mov     [rbp+57h+var_B0], 1
0x18001f884  mov     rax, [r15]
0x18001f887  lea     r8, [rbp+57h+pbInput+7]
0x18001f88b  mov     edx, 1
0x18001f890  mov     rcx, r15
0x18001f893  mov     rax, [rax+38h]
0x18001f897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f89c  mov     ebx, eax
0x18001f89e  test    eax, eax
0x18001f8a0  jns     short loc_18001F8C8
0x18001f8a2  test    byte ptr cs:_bidGblFlags, r12b
0x18001f8a9  jz      loc_18001FA3D
0x18001f8af  mov     r8d, 0D4h; unsigned int
0x18001f8b5  mov     ecx, eax; int
0x18001f8b7  lea     rdx, aCdpoInitialize_3; "<CDPO::Initialize|OLEDB|ERR> "
0x18001f8be  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001f8c3  jmp     loc_18001FA3D
0x18001f8c8  mov     rcx, qword ptr [rbp+57h+pbInput+7]; pbInput
0x18001f8cc  mov     rax, rdi
0x18001f8cf  inc     rax
0x18001f8d2  cmp     [rcx+rax*2], si
0x18001f8d6  jnz     short loc_18001F8CF
0x18001f8d8  lea     rdi, [rax+rax]
0x18001f8dc  mov     rdx, rdi; cbInput
0x18001f8df  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x18001f8e3  call    ?GetSHA256Hash@@YAJPEBG_KPEAE@Z; GetSHA256Hash(ushort const *,unsigned __int64,uchar *)
0x18001f8e8  mov     rcx, qword ptr [rbp+57h+pbInput+7]
0x18001f8ec  mov     ebx, eax
0x18001f8ee  test    rdi, rdi
0x18001f8f1  jz      short loc_18001F903
0x18001f8f3  mov     [rcx], sil
0x18001f8f6  inc     rcx
0x18001f8f9  sub     rdi, 1
0x18001f8fd  jnz     short loc_18001F8F3
0x18001f8ff  mov     rcx, qword ptr [rbp+57h+pbInput+7]
0x18001f903  call    cs:__imp_mpFree
0x18001f909  test    ebx, ebx
0x18001f90b  jns     short loc_18001F924
0x18001f90d  test    byte ptr cs:_bidGblFlags, r12b
0x18001f914  jz      loc_18001FA3D
0x18001f91a  mov     r8d, 0E1h
0x18001f920  mov     ecx, ebx
0x18001f922  jmp     short loc_18001F8B7
0x18001f924  lea     r13, [rbp+57h+pbOutput]
0x18001f928  mov     [rbp+57h+var_A0], 20h ; ' '
0x18001f92f  mov     rax, [r15]
0x18001f932  mov     rcx, r15
0x18001f935  mov     rsi, [r14+60h]
0x18001f939  mov     rbx, [r14+80h]
0x18001f940  mov     edi, [r14+78h]
0x18001f944  mov     rax, [rax+30h]
0x18001f948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f94d  mov     rdx, [r14+70h]
0x18001f951  lea     rcx, [rbp+57h+pbInput]
0x18001f955  mov     [rsp+110h+var_B8], rcx; __int64
0x18001f95a  lea     r8, [r14+68h]
0x18001f95e  lea     rcx, [r14+58h]
0x18001f962  add     rdx, 20h ; ' '; int
0x18001f966  mov     [rsp+110h+var_C0], rcx; __int64
0x18001f96b  mov     r9d, edi; int
0x18001f96e  mov     cl, [rbp+57h+var_B0]
0x18001f971  mov     [rsp+110h+var_C8], r8; __int64
0x18001f976  mov     r8, rax; int
0x18001f979  mov     [rsp+110h+var_D0], r15; CDPO *
0x18001f97e  mov     [rsp+110h+var_D8], cl; char
0x18001f982  mov     ecx, [rbp+57h+var_A0]
0x18001f985  mov     [rsp+110h+var_E0], ecx; unsigned int
0x18001f989  mov     rcx, rsi; int
0x18001f98c  mov     [rsp+110h+var_E8], r13; unsigned __int8 *
0x18001f991  mov     [rsp+110h+var_F0], rbx; __int64
0x18001f996  call    ?DrawResource@CDCMPoolManager@@QEAAJAEBU_GUID@@PEAUIUnknown@@KPEAGPEBEK_NPEAVCDPO@@PEAPEAV?$CComObject@VCDCMPool@@@ATL@@PEAPEAV?$CACMComPolyObject@VCDCM@@@@PEA_N@Z; CDCMPoolManager::DrawResource(_GUID const &,IUnknown *,ulong,ushort *,uchar const *,ulong,bool,CDPO *,ATL::CComObject<CDCMPool> * *,CACMComPolyObject<CDCM> * *,bool *)
0x18001f99b  mov     ecx, cs:_bidGblFlags
0x18001f9a1  test    r12b, cl
0x18001f9a4  jz      short loc_18001F9C0
0x18001f9a6  mov     r8d, 0F7h; unsigned int
0x18001f9ac  lea     rdx, aCdpoInitialize_3; "<CDPO::Initialize|OLEDB|ERR> "
0x18001f9b3  mov     ecx, eax; int
0x18001f9b5  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001f9ba  mov     ecx, cs:_bidGblFlags
0x18001f9c0  mov     ebx, [r14+0C0h]
0x18001f9c7  xor     esi, esi
0x18001f9c9  test    ebx, ebx
0x18001f9cb  js      short loc_18001F9DE
0x18001f9cd  mov     rax, [r14+60h]
0x18001f9d1  mov     rcx, [rax+50h]
0x18001f9d5  mov     [r14+0D0h], rcx
0x18001f9dc  jmp     short loc_18001FA3D
0x18001f9de  test    r12b, cl
0x18001f9e1  jz      short loc_18001FA3D
0x18001f9e3  mov     rax, cs:off_1800C9338; "<CDPO::Initialize|ERR> Hash: 0x%08X, %p"...
0x18001f9ea  test    rax, rax
0x18001f9ed  jz      short loc_18001FA3D
0x18001f9ef  mov     r9, [r14+70h]
0x18001f9f3  mov     rcx, r13; unsigned __int8 *
0x18001f9f6  mov     edx, [rbp+57h+var_A0]; unsigned int
0x18001f9f9  add     r9, 20h ; ' '
0x18001f9fd  mov     r10, [r14+68h]
0x18001fa01  call    ?HashForTrace@@YAIPEBEK@Z; HashForTrace(uchar const *,ulong)
0x18001fa06  mov     r8, cs:off_1800C9338; "<CDPO::Initialize|ERR> Hash: 0x%08X, %p"...
0x18001fa0d  mov     edx, 42C00h
0x18001fa12  mov     rcx, cs:off_1800C8448; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001fa19  mov     dword ptr [rsp+110h+var_D8], ebx
0x18001fa1d  mov     qword ptr [rsp+110h+var_E0], r10
0x18001fa22  mov     [rsp+110h+var_E8], r9
0x18001fa27  mov     r9d, eax
0x18001fa2a  mov     [rsp+110h+var_F0], r15
0x18001fa2f  call    _bidTraceW
0x18001fa34  jmp     short loc_18001FA3D
0x18001fa36  call    ?UnlockedDCMInit@CDPO@@AEAAJXZ; CDPO::UnlockedDCMInit(void)
0x18001fa3b  mov     ebx, eax
0x18001fa3d  lea     rcx, [r14+28h]; lpCriticalSection
0x18001fa41  call    cs:__imp_LeaveCriticalSection
0x18001fa47  jmp     loc_18001FB31
0x18001fa4c  mov     r12d, 2
0x18001fa52  cmp     [r14+68h], rsi
0x18001fa56  jnz     short loc_18001FA83
0x18001fa58  test    [r14+0E0h], r12b
0x18001fa5f  jnz     short loc_18001FA83
0x18001fa61  mov     rcx, r15; this
0x18001fa64  call    ?ShouldDoEnlistment@CDPO@@QEAA_NXZ; CDPO::ShouldDoEnlistment(void)
0x18001fa69  test    al, al
0x18001fa6b  jz      short loc_18001FA83
0x18001fa6d  lea     r8, [r14+58h]
0x18001fa71  mov     rdx, r15
0x18001fa74  call    ?EnlistDataSource@CDCMCreator@@QEAAJPEAVCDPO@@PEAPEAV?$CACMComPolyObject@VCDCM@@@@@Z; CDCMCreator::EnlistDataSource(CDPO *,CACMComPolyObject<CDCM> * *)
0x18001fa79  mov     ebx, eax
0x18001fa7b  test    eax, eax
0x18001fa7d  js      loc_18001FB31
0x18001fa83  test    byte ptr [r14+0E0h], 1
0x18001fa8b  jz      short loc_18001FB0A
0x18001fa8d  lea     rcx, [r14+28h]; lpCriticalSection
0x18001fa91  mov     ebx, esi
0x18001fa93  call    cs:__imp_EnterCriticalSection
0x18001fa99  test    byte ptr [r15+0E8h], 1
0x18001faa1  jz      short loc_18001FAD2
0x18001faa3  mov     rcx, r15; this
0x18001faa6  call    ?CompleteSettingProps@CDPO@@QEAAJXZ; CDPO::CompleteSettingProps(void)
0x18001faab  mov     ebx, eax
0x18001faad  test    eax, eax
0x18001faaf  jns     short loc_18001FAD2
0x18001fab1  test    byte ptr cs:_bidGblFlags, r12b
0x18001fab8  jz      short loc_18001FACE
0x18001faba  mov     r8d, 138h; unsigned int
0x18001fac0  lea     rdx, aCdpoInitialize_3; "<CDPO::Initialize|OLEDB|ERR> "
0x18001fac7  mov     ecx, eax; int
0x18001fac9  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001face  mov     edi, ebx
0x18001fad0  jmp     short loc_18001FAF9
0x18001fad2  mov     rcx, r15; this
0x18001fad5  call    ?UnlockedDCMInit@CDPO@@AEAAJXZ; CDPO::UnlockedDCMInit(void)
0x18001fada  test    byte ptr cs:_bidGblFlags, r12b
0x18001fae1  mov     edi, eax
0x18001fae3  jz      short loc_18001FAF9
0x18001fae5  mov     r8d, 13Fh; unsigned int
0x18001faeb  lea     rdx, aCdpoInitialize_3; "<CDPO::Initialize|OLEDB|ERR> "
0x18001faf2  mov     ecx, eax; int
0x18001faf4  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001faf9  lea     rcx, [r14+28h]; lpCriticalSection
0x18001fafd  call    cs:__imp_LeaveCriticalSection
0x18001fb03  test    edi, edi
0x18001fb05  cmovnz  ebx, edi
0x18001fb08  jmp     short loc_18001FB31
0x18001fb0a  mov     rcx, r15; this
0x18001fb0d  call    ?UnlockedDCMInit@CDPO@@AEAAJXZ; CDPO::UnlockedDCMInit(void)
0x18001fb12  test    byte ptr cs:_bidGblFlags, r12b
0x18001fb19  mov     ebx, eax
0x18001fb1b  jz      short loc_18001FB31
0x18001fb1d  mov     r8d, 14Eh; unsigned int
0x18001fb23  lea     rdx, aCdpoInitialize_3; "<CDPO::Initialize|OLEDB|ERR> "
0x18001fb2a  mov     ecx, eax; int
0x18001fb2c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
  ... truncated ...
```
