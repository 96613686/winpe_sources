# TmsAllocatorEngine<MsAllocator::CompactionStrategy>::Allocate(CmsTransactionContext *,MsAllocator::CompactionStrategy::State *,SmsAllocationContext *,_RANGE const *,_RANGE *,_RANGE *)

- ea: `0x1c00e9b34`
- end: `0x1c00ea169`
- name: `?Allocate@?$TmsAllocatorEngine@VCompactionStrategy@MsAllocator@@@@SAJPEAVCmsTransactionContext@@PEAUState@CompactionStrategy@MsAllocator@@PEAUSmsAllocationContext@@PEBU_RANGE@@PEAU7@4@Z`
- size: `1589`
- prototype: `__int64 __usercall@<rax>(struct CmsTransactionContext *@<rcx>, struct _RANGE *, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c0023ee4`

## callees

- `0x1c00247f0`
- `0x1c00254d0`
- `0x1c0025f98`
- `0x1c0026868`
- `0x1c00268d4`
- `0x1c005a9d8`
- `0x1c005ac78`
- `0x1c0068960`
- `0x1c00bcc28`
- `0x1c00e933c`
- `0x1c00e9b34`
- `0x1c00ec038`

## import_xrefs

- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ea0f5`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ea133`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ea0f5`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ea133`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00e9f96`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00ea0c1`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00e9f96`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00ea0c1`

## pseudocode

```c
__int64 __fastcall TmsAllocatorEngine<MsAllocator::CompactionStrategy>::Allocate(
        struct CmsTransactionContext *a1,
        struct MsAllocator::CompactionStrategy::State *a2,
        __int64 a3,
        __int64 a4,
        struct _RANGE *a5,
        struct _RANGE *a6)
{
  __int64 v6; // r15
  unsigned __int64 v8; // rcx
  char v10; // si
  int v11; // eax
  int v12; // eax
  unsigned __int64 v13; // r13
  int v14; // ecx
  struct SmsAllocationContext *v15; // r8
  struct MsAllocator::CompactionStrategy::State *v16; // rdx
  int Space; // eax
  int v18; // ebx
  int v19; // eax
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rcx
  __int16 v22; // bx
  unsigned __int64 TotalFree; // rax
  int v24; // r8d
  int v25; // r9d
  unsigned int v26; // r10d
  bool v27; // r9
  __int16 v28; // bx
  int v29; // edx
  bool v30; // r8
  bool v31; // al
  unsigned __int64 v32; // rax
  SmsAllocationRegionEx *v33; // rcx
  struct SmsAllocationContext *v34; // r8
  char v35; // r9
  int v36; // r10d
  int v37; // eax
  unsigned __int64 v38; // rax
  unsigned __int64 v39; // rax
  char v40; // r9
  int v41; // r10d
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  int v44; // eax
  bool v45; // zf
  struct _IO_REMOVE_LOCK *v46; // rcx
  struct _RANGE *v47; // rcx
  char v48; // al
  struct SmsContainer *v49; // rsi
  __int64 v50; // rcx
  SmsAllocationRegionEx *v51; // rcx
  SmsAllocationRegionEx *v52; // rcx
  signed __int32 v54[8]; // [rsp+0h] [rbp-100h] BYREF
  int v55; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v56; // [rsp+48h] [rbp-B8h]
  struct SmsContainer *v57; // [rsp+50h] [rbp-B0h] BYREF
  CmsVolume *v58; // [rsp+58h] [rbp-A8h]
  __int128 v59; // [rsp+60h] [rbp-A0h]
  struct MsAllocator::CompactionStrategy::State *v60; // [rsp+70h] [rbp-90h]
  struct _RANGE *v61; // [rsp+78h] [rbp-88h]
  _OWORD v62[4]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v63; // [rsp+C0h] [rbp-40h]
  struct MsAllocator::CompactionStrategy::State *v64; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v65; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v66; // [rsp+E8h] [rbp-18h]
  struct SmsAllocationContext *v67; // [rsp+F0h] [rbp-10h]
  struct MsAllocator::CompactionStrategy::State **v68; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v69; // [rsp+100h] [rbp+0h] BYREF
  SmsAllocationRegionEx *v70; // [rsp+110h] [rbp+10h]
  __int64 v71; // [rsp+118h] [rbp+18h]
  int v72; // [rsp+120h] [rbp+20h]

  v6 = *(_QWORD *)(a3 + 16);
  v8 = *(_QWORD *)(a4 + 8);
  v10 = 0;
  v61 = a6;
  v58 = *(CmsVolume **)(v6 + 48);
  v68 = &v64;
  v11 = *(_DWORD *)(a3 + 68) & 8;
  v64 = a2;
  v55 = v11;
  v12 = *(_DWORD *)(a3 + 104);
  v66 = 0;
  v67 = (struct SmsAllocationContext *)a3;
  v70 = 0;
  v72 = 0;
  v71 = 0;
  v60 = a2;
  v57 = 0;
  v56 = v8;
  v65 = MsZeroRange;
  v69 = MsZeroRange;
  v13 = *(int *)(v6 + 60);
  v62[0] = 0;
  if ( v8 > 0x20 || (v14 = 4, (v12 & 2) == 0) )
    v14 = 0;
  *(_DWORD *)(a3 + 104) = v14 | v12 & 0xFFFFFFFB;
  do
  {
    while ( 1 )
    {
      do
      {
        v66 = 0;
        v65 = MsZeroRange;
LABEL_6:
        v15 = v67;
        v16 = v64;
        *(_OWORD *)(a3 + 80) = 0;
        v70 = 0;
        *(_QWORD *)(a3 + 96) = 0;
        v72 = 0;
        v71 = 0;
        v69 = MsZeroRange;
        Space = MsAllocator::CompactionStrategy::NextSpace(
                  a1,
                  v16,
                  v15,
                  (struct MsAllocator::CompactionStrategy::Context *)&v65);
        v18 = Space;
      }
      while ( Space == -1073741267 );
      if ( Space != -1073741197 )
        break;
      if ( (*(_DWORD *)(a3 + 104) & 0x200) == 0 || v10 )
      {
        v18 = -1073741697;
        break;
      }
      v10 = 1;
    }
    if ( v18 < 0 )
      break;
    do
    {
      while ( 1 )
      {
        v19 = MsAllocator::CandidateIterator<MsAllocator::CompactionStrategy>::Advance(&v68, a1);
        v18 = v19;
        if ( v19 < 0 )
          break;
        if ( !v55 )
          goto LABEL_19;
        v20 = -(int)v13 & (unsigned __int64)(v69 + (int)v13 - 1);
        *((_QWORD *)&v59 + 1) = *(&MsZeroRange + 1);
        *(_QWORD *)&v59 = v20;
        if ( *((_QWORD *)&v69 + 1) + (_QWORD)v69 <= v20 )
        {
          v21 = *((_QWORD *)&v59 + 1);
        }
        else
        {
          v21 = v69 + *((_QWORD *)&v69 + 1) - v20;
          *((_QWORD *)&v59 + 1) = v21;
        }
        if ( v21 >= v13 )
        {
          v69 = v59;
LABEL_19:
          v22 = *((_WORD *)v70 + 12);
          TotalFree = SmsAllocationRegionEx::GetTotalFree(v70);
          if ( TotalFree >= *((_QWORD *)&v69 + 1) )
            TotalFree = *((_QWORD *)&v69 + 1);
          if ( TotalFree && (TotalFree >= v56 || !v24) && (v22 & 0x64) == 0 && (v25 || (v22 & 8) == 0) )
          {
            if ( (v72 & 2) != 0 || (v27 = v26, v10) )
              v27 = 1;
            v28 = v22 & 2;
            _InterlockedOr(v54, v26);
            v29 = *(_DWORD *)(a3 + 104);
            if ( (v72 & 1) == 0 && ((v29 & 4) != 0 || v28) )
              v30 = v26;
            else
              v30 = 1;
            if ( v28 || *((_QWORD *)v70 + 1) != *(_DWORD *)(v6 + 60) || v27 || v30 || (v31 = 1, (v29 & 0x200) != 0) )
              v31 = v26;
            if ( !CmsAllocator::TryLockCandidateForAllocation(
                    (CmsAllocator *)v6,
                    a1,
                    (struct SmsAllocationContext *)a3,
                    (const struct MsAllocator::AllocationCandidate *)&v69,
                    v27,
                    v30,
                    v31) )
              goto LABEL_53;
            LOBYTE(v72) = v72 | 4;
            v32 = SmsAllocationRegionEx::GetTotalFree(v70);
            if ( v32 >= *((_QWORD *)&v69 + 1) )
              v32 = *((_QWORD *)&v69 + 1);
            if ( v32 && (v32 >= v56 || !(_DWORD)v34) && (v35 & 0x64) == 0 && (v36 || (v35 & 8) == 0) )
            {
              if ( v28 )
              {
                v37 = CmsAllocator::PrepareRangeOnlyCandidateForAllocation(
                        (CmsAllocator *)v6,
                        a1,
                        (struct SmsAllocationContext *)a3,
                        (struct MsAllocator::AllocationCandidate *)&v69);
                v18 = v37;
                if ( v37 >= 0 )
                {
                  v39 = SmsAllocationRegionEx::GetTotalFree(v70);
                  if ( v39 >= *((_QWORD *)&v69 + 1) )
                    v39 = *((_QWORD *)&v69 + 1);
                  if ( v39 && (v39 >= v56 || !(_DWORD)v34) && (v40 & 0x64) == 0 && (v41 || (v40 & 8) == 0) )
                    goto LABEL_64;
                }
                else
                {
                  if ( v37 != -1073741267 )
                    goto LABEL_95;
LABEL_53:
                  v38 = v13;
                  if ( *((_QWORD *)&v69 + 1) < v13 )
                    v38 = *((_QWORD *)&v69 + 1);
                  *((_QWORD *)&v69 + 1) = v38;
                }
              }
              else
              {
LABEL_64:
                if ( (*(_DWORD *)(a3 + 104) & 1) != 0 )
                {
                  CmsAllocator::UnlockCache((CmsAllocator *)v6, a1, (struct SmsPushLockContext *)(a3 + 40));
                  *(_DWORD *)(a3 + 104) &= ~1u;
                  v33 = v70;
                }
                v45 = *(_BYTE *)(v6 + 84) == 2;
                v42 = *((_OWORD *)v33 + 1);
                v62[1] = *(_OWORD *)v33;
                v43 = *((_OWORD *)v33 + 2);
                v62[2] = v42;
                *(_QWORD *)&v42 = *((_QWORD *)v33 + 6);
                v62[3] = v43;
                v63 = v42;
                if ( v45
                  || (v44 = CmsAllocator::PopulateContainersForCandidate(
                              (CmsAllocator *)v6,
                              a1,
                              v34,
                              (const struct MsAllocator::AllocationCandidate *)&v69,
                              (struct _RANGE *)v62,
                              &v57),
                      v18 = v44,
                      v44 >= 0) )
                {
                  *(_DWORD *)(a3 + 104) &= ~0x80u;
                  v18 = CmsAllocator::AllocateFromCandidate(
                          (CmsAllocator *)v6,
                          a1,
                          (struct SmsAllocationContext *)a3,
                          (struct MsAllocator::AllocationCandidate *)&v69,
                          a5);
                  if ( v18 >= 0 )
                  {
                    if ( (*(_DWORD *)(a3 + 104) & 0x120) == 0x100 )
                      *((_QWORD *)v60 + 1) = *(_QWORD *)a5 + *((_QWORD *)a5 + 1);
                    v47 = v61;
                    *(_OWORD *)v61 = *(_OWORD *)a5;
                    v48 = *(_BYTE *)(v6 + 84);
                    if ( v48 != 2 )
                    {
                      v49 = v57;
                      if ( v48 == 4 )
                        CmsAllocator::UpdateVolumeContainerForCompletedAllocation(
                          (CmsAllocator *)v6,
                          a1,
                          (struct SmsAllocationContext *)a3,
                          v57,
                          v47);
                      v50 = *((_QWORD *)v58 + 381);
                      _InterlockedDecrement((volatile signed __int32 *)v49 + 22);
                      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v50 + 328), 0, 0x20u);
                      --*((_DWORD *)a1 + 706);
                      *(_QWORD *)a5 = *(_QWORD *)&v62[0] + (*(_QWORD *)a5 & ((int)v13 - 1));
                    }
                    v51 = v70;
                    _InterlockedDecrement((volatile signed __int32 *)v70 + 10);
                    ExReleasePushLockEx((char *)v51 + 32, 0);
                    LOBYTE(v72) = v72 & 0xFB;
                    goto LABEL_95;
                  }
                  if ( *(_BYTE *)(v6 + 84) != 2 )
                  {
                    v46 = (struct _IO_REMOVE_LOCK *)(*((_QWORD *)v58 + 381) + 328LL);
                    _InterlockedDecrement((volatile signed __int32 *)v57 + 22);
                    IoReleaseRemoveLockEx(v46, 0, 0x20u);
                    --*((_DWORD *)a1 + 706);
                  }
                  if ( v18 != -1073741267 && v18 != -1073741197 )
                  {
                    v45 = v18 == -1073741431;
                    goto LABEL_69;
                  }
                }
                else
                {
                  v45 = v44 == -1073741267;
LABEL_69:
                  if ( !v45 )
                    goto LABEL_95;
                }
              }
            }
          }
        }
      }
      if ( v19 == -1073741197 || v19 == -1073741172 )
        goto LABEL_6;
    }
    while ( v19 == -1073741198 );
    if ( v19 != -1073741400 || (*(_DWORD *)(a3 + 68) & 0x800) != 0 )
      break;
    if ( (*(_DWORD *)(a3 + 104) & 1) != 0 )
    {
      CmsAllocator::UnlockCache((CmsAllocator *)v6, a1, (struct SmsPushLockContext *)(a3 + 40));
      *(_DWORD *)(a3 + 104) &= ~1u;
    }
    v18 = CmsVolume::TriageAllocator(v58, a1);
  }
  while ( v18 >= 0 );
LABEL_95:
  if ( (*(_DWORD *)(a3 + 104) & 1) != 0 )
  {
    CmsAllocator::UnlockCache((CmsAllocator *)v6, a1, (struct SmsPushLockContext *)(a3 + 40));
    *(_DWORD *)(a3 + 104) &= ~1u;
  }
  if ( (v72 & 4) != 0 )
  {
    v52 = v70;
    _InterlockedDecrement((volatile signed __int32 *)v70 + 10);
    ExReleasePushLockEx((char *)v52 + 32, 0);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1c00e9b34  mov     [rsp-8+arg_18], rbx
0x1c00e9b39  push    rbp
0x1c00e9b3a  push    rsi
0x1c00e9b3b  push    rdi
0x1c00e9b3c  push    r12
0x1c00e9b3e  push    r13
0x1c00e9b40  push    r14
0x1c00e9b42  push    r15
0x1c00e9b44  lea     rbp, [rsp-40h]
0x1c00e9b49  sub     rsp, 140h
0x1c00e9b50  mov     rax, cs:__security_cookie
0x1c00e9b57  xor     rax, rsp
0x1c00e9b5a  mov     [rbp+70h+var_40], rax
0x1c00e9b5e  movups  xmm0, cs:?MsZeroRange@@3U_RANGE@@B; _RANGE const MsZeroRange
0x1c00e9b65  mov     r15, [r8+10h]
0x1c00e9b69  xor     r10d, r10d
0x1c00e9b6c  mov     rax, [rbp+70h+arg_28]
0x1c00e9b73  mov     r14, rcx
0x1c00e9b76  mov     rcx, [r9+8]
0x1c00e9b7a  mov     rdi, r8
0x1c00e9b7d  mov     r12, [rbp+70h+arg_20]
0x1c00e9b84  mov     sil, r10b
0x1c00e9b87  mov     [rsp+170h+var_F8], rax
0x1c00e9b8c  mov     rax, [r15+30h]
0x1c00e9b90  mov     [rsp+170h+var_118], rax
0x1c00e9b95  lea     rax, [rbp+70h+var_A0]
0x1c00e9b99  mov     [rbp+70h+var_78], rax
0x1c00e9b9d  mov     eax, [r8+44h]
0x1c00e9ba1  and     eax, 8
0x1c00e9ba4  mov     [rbp+70h+var_A0], rdx
0x1c00e9ba8  mov     [rsp+170h+var_130], eax
0x1c00e9bac  mov     eax, [r8+68h]
0x1c00e9bb0  mov     [rbp+70h+var_88], r10
0x1c00e9bb4  mov     [rbp+70h+var_80], r8
0x1c00e9bb8  mov     [rbp+70h+var_60], r10
0x1c00e9bbc  mov     [rbp+70h+var_50], r10d
0x1c00e9bc0  mov     [rbp+70h+var_58], r10
0x1c00e9bc4  mov     [rsp+170h+var_100], rdx
0x1c00e9bc9  mov     [rsp+170h+var_120], r10
0x1c00e9bce  mov     [rsp+170h+var_128], rcx
0x1c00e9bd3  movdqu  [rbp+70h+var_98], xmm0
0x1c00e9bd8  movdqu  [rbp+70h+var_70], xmm0
0x1c00e9bdd  movsxd  r13, dword ptr [r15+3Ch]
0x1c00e9be1  xorps   xmm0, xmm0
0x1c00e9be4  movups  [rbp+70h+var_F0], xmm0
0x1c00e9be8  cmp     rcx, 20h ; ' '
0x1c00e9bec  ja      short loc_1C00E9BF6
0x1c00e9bee  lea     ecx, [r10+4]
0x1c00e9bf2  test    al, 2
0x1c00e9bf4  jnz     short loc_1C00E9BF9
0x1c00e9bf6  mov     ecx, r10d
0x1c00e9bf9  and     eax, 0FFFFFFFBh
0x1c00e9bfc  or      eax, ecx
0x1c00e9bfe  mov     [r8+68h], eax
0x1c00e9c02  movups  xmm0, cs:?MsZeroRange@@3U_RANGE@@B; _RANGE const MsZeroRange
0x1c00e9c09  mov     [rbp+70h+var_88], r10
0x1c00e9c0d  movdqu  [rbp+70h+var_98], xmm0
0x1c00e9c12  mov     r8, [rbp+70h+var_80]; struct SmsAllocationContext *
0x1c00e9c16  lea     r9, [rbp+70h+var_98]; struct MsAllocator::CompactionStrategy::Context *
0x1c00e9c1a  mov     rdx, [rbp+70h+var_A0]; struct MsAllocator::CompactionStrategy::State *
0x1c00e9c1e  xorps   xmm0, xmm0
0x1c00e9c21  movups  xmmword ptr [rdi+50h], xmm0
0x1c00e9c25  xor     eax, eax
0x1c00e9c27  mov     [rbp+70h+var_60], r10
0x1c00e9c2b  mov     [rdi+60h], rax
0x1c00e9c2f  mov     rcx, r14; struct CmsTransactionContext *
0x1c00e9c32  movups  xmm0, cs:?MsZeroRange@@3U_RANGE@@B; _RANGE const MsZeroRange
0x1c00e9c39  mov     [rbp+70h+var_50], r10d
0x1c00e9c3d  mov     [rbp+70h+var_58], r10
0x1c00e9c41  movdqu  [rbp+70h+var_70], xmm0
0x1c00e9c46  call    ?NextSpace@CompactionStrategy@MsAllocator@@CAJPEAVCmsTransactionContext@@PEAUState@12@PEAUSmsAllocationContext@@AEAUContext@12@@Z; MsAllocator::CompactionStrategy::NextSpace(CmsTransactionContext *,MsAllocator::CompactionStrategy::State *,SmsAllocationContext *,MsAllocator::CompactionStrategy::Context &)
0x1c00e9c4b  mov     ebx, eax
0x1c00e9c4d  cmp     eax, 0C000022Dh
0x1c00e9c52  jz      loc_1C00EA03E
0x1c00e9c58  cmp     eax, 0C0000273h
0x1c00e9c5d  jnz     short loc_1C00E9C79
0x1c00e9c5f  test    dword ptr [rdi+68h], 200h
0x1c00e9c66  jz      short loc_1C00E9C74
0x1c00e9c68  xor     r10d, r10d
0x1c00e9c6b  test    sil, sil
0x1c00e9c6e  jz      loc_1C00EA046
0x1c00e9c74  mov     ebx, 0C000007Fh
0x1c00e9c79  test    ebx, ebx
0x1c00e9c7b  js      loc_1C00EA105
0x1c00e9c81  mov     rdx, r14
0x1c00e9c84  lea     rcx, [rbp+70h+var_78]
0x1c00e9c88  call    ?Advance@?$CandidateIterator@VCompactionStrategy@MsAllocator@@@MsAllocator@@QEAAJPEAVCmsTransactionContext@@@Z; MsAllocator::CandidateIterator<MsAllocator::CompactionStrategy>::Advance(CmsTransactionContext *)
0x1c00e9c8d  xor     r10d, r10d
0x1c00e9c90  mov     ebx, eax
0x1c00e9c92  test    eax, eax
0x1c00e9c94  js      loc_1C00E9FCC
0x1c00e9c9a  cmp     [rsp+170h+var_130], r10d
0x1c00e9c9f  jz      short loc_1C00E9CFA
0x1c00e9ca1  mov     r8, qword ptr [rbp+70h+var_70]
0x1c00e9ca5  lea     eax, [r13-1]
0x1c00e9ca9  movups  xmm0, cs:?MsZeroRange@@3U_RANGE@@B; _RANGE const MsZeroRange
0x1c00e9cb0  movsxd  rdx, eax
0x1c00e9cb3  mov     eax, r13d
0x1c00e9cb6  neg     eax
0x1c00e9cb8  add     rdx, r8
0x1c00e9cbb  movsxd  rcx, eax
0x1c00e9cbe  and     rdx, rcx
0x1c00e9cc1  mov     rcx, qword ptr [rbp+70h+var_70+8]
0x1c00e9cc5  movdqu  [rsp+170h+var_110], xmm0
0x1c00e9ccb  mov     qword ptr [rsp+170h+var_110], rdx
0x1c00e9cd0  lea     rax, [rcx+r8]
0x1c00e9cd4  cmp     rax, rdx
0x1c00e9cd7  jbe     short loc_1C00E9CE6
0x1c00e9cd9  sub     rcx, rdx
0x1c00e9cdc  add     rcx, r8
0x1c00e9cdf  mov     qword ptr [rsp+170h+var_110+8], rcx
0x1c00e9ce4  jmp     short loc_1C00E9CEB
0x1c00e9ce6  mov     rcx, qword ptr [rsp+170h+var_110+8]
0x1c00e9ceb  cmp     rcx, r13
0x1c00e9cee  jb      short loc_1C00E9C81
0x1c00e9cf0  movups  xmm0, [rsp+170h+var_110]
0x1c00e9cf5  movdqu  [rbp+70h+var_70], xmm0
0x1c00e9cfa  mov     rcx, [rbp+70h+var_60]; this
0x1c00e9cfe  mov     r8d, [rdi+44h]
0x1c00e9d02  mov     r9d, r8d
0x1c00e9d05  and     r9d, 40h
0x1c00e9d09  and     r8d, 8
0x1c00e9d0d  movzx   ebx, word ptr [rcx+18h]
0x1c00e9d11  call    ?GetTotalFree@SmsAllocationRegionEx@@QEBA?B_KXZ; SmsAllocationRegionEx::GetTotalFree(void)
0x1c00e9d16  cmp     rax, qword ptr [rbp+70h+var_70+8]
0x1c00e9d1a  cmovnb  rax, qword ptr [rbp+70h+var_70+8]
0x1c00e9d1f  test    rax, rax
0x1c00e9d22  jz      loc_1C00E9C81
0x1c00e9d28  cmp     rax, [rsp+170h+var_128]
0x1c00e9d2d  jnb     short loc_1C00E9D38
0x1c00e9d2f  test    r8d, r8d
0x1c00e9d32  jnz     loc_1C00E9C81
0x1c00e9d38  test    bl, 64h
0x1c00e9d3b  jnz     loc_1C00E9C81
0x1c00e9d41  test    r9d, r9d
0x1c00e9d44  jnz     short loc_1C00E9D4F
0x1c00e9d46  test    bl, 8
0x1c00e9d49  jnz     loc_1C00E9C81
0x1c00e9d4f  test    byte ptr [rbp+70h+var_50], 2
0x1c00e9d53  jnz     short loc_1C00E9D5D
0x1c00e9d55  mov     r9b, r10b
0x1c00e9d58  test    sil, sil
0x1c00e9d5b  jz      short loc_1C00E9D60
0x1c00e9d5d  mov     r9b, 1
0x1c00e9d60  and     bx, 2
0x1c00e9d64  lock or [rsp+170h+var_170], r10d
0x1c00e9d69  test    byte ptr [rbp+70h+var_50], 1
0x1c00e9d6d  mov     edx, [rdi+68h]
0x1c00e9d70  jnz     short loc_1C00E9D81
0x1c00e9d72  test    dl, 4
0x1c00e9d75  jnz     short loc_1C00E9D7C
0x1c00e9d77  test    bx, bx
0x1c00e9d7a  jz      short loc_1C00E9D81
0x1c00e9d7c  mov     r8b, r10b
0x1c00e9d7f  jmp     short loc_1C00E9D84
0x1c00e9d81  mov     r8b, 1
0x1c00e9d84  test    bx, bx
0x1c00e9d87  jnz     short loc_1C00E9DA9
0x1c00e9d89  mov     rax, [rbp+70h+var_60]
0x1c00e9d8d  movsxd  rcx, dword ptr [r15+3Ch]
0x1c00e9d91  cmp     [rax+8], rcx
0x1c00e9d95  jnz     short loc_1C00E9DA9
0x1c00e9d97  test    r9b, r9b
0x1c00e9d9a  jnz     short loc_1C00E9DA9
0x1c00e9d9c  test    r8b, r8b
0x1c00e9d9f  jnz     short loc_1C00E9DA9
0x1c00e9da1  mov     al, 1
0x1c00e9da3  bt      edx, 9
0x1c00e9da7  jnb     short loc_1C00E9DAC
0x1c00e9da9  mov     al, r10b
0x1c00e9dac  mov     [rsp+170h+var_140], al; bool
0x1c00e9db0  mov     rdx, r14; struct CmsTransactionContext *
0x1c00e9db3  mov     byte ptr [rsp+170h+var_148], r8b; bool
0x1c00e9db8  mov     rcx, r15; this
0x1c00e9dbb  mov     byte ptr [rsp+170h+var_150], r9b; bool
0x1c00e9dc0  mov     r8, rdi; struct SmsAllocationContext *
0x1c00e9dc3  lea     r9, [rbp+70h+var_70]; struct MsAllocator::AllocationCandidate *
0x1c00e9dc7  call    ?TryLockCandidateForAllocation@CmsAllocator@@AEAA_NPEAVCmsTransactionContext@@PEAUSmsAllocationContext@@AEBUAllocationCandidate@MsAllocator@@_N33@Z; CmsAllocator::TryLockCandidateForAllocation(CmsTransactionContext *,SmsAllocationContext *,MsAllocator::AllocationCandidate const &,bool,bool,bool)
0x1c00e9dcc  test    al, al
0x1c00e9dce  jz      loc_1C00E9E5C
0x1c00e9dd4  mov     rcx, [rbp+70h+var_60]; this
0x1c00e9dd8  mov     r8d, [rdi+44h]
0x1c00e9ddc  mov     r10d, r8d
0x1c00e9ddf  or      byte ptr [rbp+70h+var_50], 4
0x1c00e9de3  and     r10d, 40h
0x1c00e9de7  and     r8d, 8
0x1c00e9deb  movzx   r9d, word ptr [rcx+18h]
0x1c00e9df0  call    ?GetTotalFree@SmsAllocationRegionEx@@QEBA?B_KXZ; SmsAllocationRegionEx::GetTotalFree(void)
0x1c00e9df5  cmp     rax, qword ptr [rbp+70h+var_70+8]
0x1c00e9df9  cmovnb  rax, qword ptr [rbp+70h+var_70+8]
0x1c00e9dfe  test    rax, rax
0x1c00e9e01  jz      loc_1C00E9C81
0x1c00e9e07  cmp     rax, [rsp+170h+var_128]
0x1c00e9e0c  jnb     short loc_1C00E9E17
0x1c00e9e0e  test    r8d, r8d
0x1c00e9e11  jnz     loc_1C00E9C81
0x1c00e9e17  test    r9b, 64h
0x1c00e9e1b  jnz     loc_1C00E9C81
0x1c00e9e21  test    r10d, r10d
0x1c00e9e24  jnz     short loc_1C00E9E30
0x1c00e9e26  test    r9b, 8
0x1c00e9e2a  jnz     loc_1C00E9C81
0x1c00e9e30  test    bx, bx
0x1c00e9e33  jz      loc_1C00E9EC9
0x1c00e9e39  lea     r9, [rbp+70h+var_70]; struct MsAllocator::AllocationCandidate *
0x1c00e9e3d  mov     r8, rdi; struct SmsAllocationContext *
0x1c00e9e40  mov     rdx, r14; struct CmsTransactionContext *
0x1c00e9e43  mov     rcx, r15; this
0x1c00e9e46  call    ?PrepareRangeOnlyCandidateForAllocation@CmsAllocator@@AEAAJPEAVCmsTransactionContext@@PEAUSmsAllocationContext@@AEAUAllocationCandidate@MsAllocator@@@Z; CmsAllocator::PrepareRangeOnlyCandidateForAllocation(CmsTransactionContext *,SmsAllocationContext *,MsAllocator::AllocationCandidate &)
0x1c00e9e4b  mov     ebx, eax
0x1c00e9e4d  test    eax, eax
0x1c00e9e4f  jns     short loc_1C00E9E71
0x1c00e9e51  cmp     eax, 0C000022Dh
0x1c00e9e56  jnz     loc_1C00EA105
0x1c00e9e5c  cmp     qword ptr [rbp+70h+var_70+8], r13
0x1c00e9e60  mov     rax, r13
0x1c00e9e63  cmovb   rax, qword ptr [rbp+70h+var_70+8]
0x1c00e9e68  mov     qword ptr [rbp+70h+var_70+8], rax
0x1c00e9e6c  jmp     loc_1C00E9C81
0x1c00e9e71  mov     rcx, [rbp+70h+var_60]; this
0x1c00e9e75  mov     r8d, [rdi+44h]
0x1c00e9e79  mov     r10d, r8d
0x1c00e9e7c  and     r10d, 40h
0x1c00e9e80  and     r8d, 8
0x1c00e9e84  movzx   r9d, word ptr [rcx+18h]
0x1c00e9e89  call    ?GetTotalFree@SmsAllocationRegionEx@@QEBA?B_KXZ; SmsAllocationRegionEx::GetTotalFree(void)
0x1c00e9e8e  cmp     rax, qword ptr [rbp+70h+var_70+8]
0x1c00e9e92  cmovnb  rax, qword ptr [rbp+70h+var_70+8]
0x1c00e9e97  test    rax, rax
0x1c00e9e9a  jz      loc_1C00E9C81
0x1c00e9ea0  cmp     rax, [rsp+170h+var_128]
0x1c00e9ea5  jnb     short loc_1C00E9EB0
0x1c00e9ea7  test    r8d, r8d
0x1c00e9eaa  jnz     loc_1C00E9C81
0x1c00e9eb0  test    r9b, 64h
0x1c00e9eb4  jnz     loc_1C00E9C81
0x1c00e9eba  test    r10d, r10d
0x1c00e9ebd  jnz     short loc_1C00E9EC9
0x1c00e9ebf  test    r9b, 8
0x1c00e9ec3  jnz     loc_1C00E9C81
0x1c00e9ec9  mov     eax, [rdi+68h]
0x1c00e9ecc  test    al, 1
0x1c00e9ece  jz      short loc_1C00E9EE7
0x1c00e9ed0  lea     r8, [rdi+28h]; struct SmsPushLockContext *
0x1c00e9ed4  mov     rdx, r14; struct CmsTransactionContext *
0x1c00e9ed7  mov     rcx, r15; this
0x1c00e9eda  call    ?UnlockCache@CmsAllocator@@AEAAXPEAVCmsTransactionContext@@PEAUSmsPushLockContext@@@Z; CmsAllocator::UnlockCache(CmsTransactionContext *,SmsPushLockContext *)
0x1c00e9edf  and     dword ptr [rdi+68h], 0FFFFFFFEh
0x1c00e9ee3  mov     rcx, [rbp+70h+var_60]
0x1c00e9ee7  cmp     byte ptr [r15+54h], 2
0x1c00e9eec  movups  xmm0, xmmword ptr [rcx]
0x1c00e9eef  movups  xmm1, xmmword ptr [rcx+10h]
0x1c00e9ef3  movups  [rbp+70h+var_E0], xmm0
0x1c00e9ef7  movups  xmm0, xmmword ptr [rcx+20h]
0x1c00e9efb  movups  [rbp+70h+var_D0], xmm1
0x1c00e9eff  movsd   xmm1, qword ptr [rcx+30h]
0x1c00e9f04  movups  [rbp+70h+var_C0], xmm0
0x1c00e9f08  movsd   [rbp+70h+var_B0], xmm1
0x1c00e9f0d  jz      short loc_1C00E9F47
0x1c00e9f0f  lea     rax, [rsp+170h+var_120]
0x1c00e9f14  mov     rdx, r14; struct CmsTransactionContext *
0x1c00e9f17  mov     [rsp+170h+var_148], rax; struct SmsContainer **
0x1c00e9f1c  lea     r9, [rbp+70h+var_70]; struct MsAllocator::AllocationCandidate *
0x1c00e9f20  lea     rax, [rbp+70h+var_F0]
0x1c00e9f24  mov     rcx, r15; this
0x1c00e9f27  mov     [rsp+170h+var_150], rax; struct _RANGE *
0x1c00e9f2c  call    ?PopulateContainersForCandidate@CmsAllocator@@AEAAJPEAVCmsTransactionContext@@PEAUSmsAllocationContext@@AEBUAllocationCandidate@MsAllocator@@PEAU_RANGE@@PEAPEAUSmsContainer@@@Z; CmsAllocator::PopulateContainersForCandidate(CmsTransactionContext *,SmsAllocationContext *,MsAllocator::AllocationCandidate const &,_RANGE *,SmsContainer * *)
0x1c00e9f31  mov     ebx, eax
0x1c00e9f33  test    eax, eax
0x1c00e9f35  jns     short loc_1C00E9F47
0x1c00e9f37  cmp     eax, 0C000022Dh
0x1c00e9f3c  jz      loc_1C00E9C81
0x1c00e9f42  jmp     loc_1C00EA105
0x1c00e9f47  btr     dword ptr [rdi+68h], 7
0x1c00e9f4c  lea     r9, [rbp+70h+var_70]; struct MsAllocator::AllocationCandidate *
0x1c00e9f50  mov     r8, rdi; struct SmsAllocationContext *
0x1c00e9f53  mov     [rsp+170h+var_150], r12; struct _RANGE *
0x1c00e9f58  mov     rdx, r14; struct CmsTransactionContext *
0x1c00e9f5b  mov     rcx, r15; this
0x1c00e9f5e  call    ?AllocateFromCandidate@CmsAllocator@@AEAAJPEAVCmsTransactionContext@@PEAUSmsAllocationContext@@AEAUAllocationCandidate@MsAllocator@@PEAU_RANGE@@@Z; CmsAllocator::AllocateFromCandidate(CmsTransactionContext *,SmsAllocationContext *,MsAllocator::AllocationCandidate &,_RANGE *)
0x1c00e9f63  mov     ebx, eax
0x1c00e9f65  test    eax, eax
0x1c00e9f67  jns     loc_1C00EA04E
0x1c00e9f6d  cmp     byte ptr [r15+54h], 2
0x1c00e9f72  jz      short loc_1C00E9FA9
0x1c00e9f74  mov     rax, [rsp+170h+var_118]
0x1c00e9f79  xor     edx, edx; Tag
0x1c00e9f7b  mov     rcx, [rax+0BE8h]
0x1c00e9f82  lea     r8d, [rdx+20h]; RemlockSize
0x1c00e9f86  mov     rax, [rsp+170h+var_120]
0x1c00e9f8b  add     rcx, 148h; RemoveLock
0x1c00e9f92  lock dec dword ptr [rax+58h]
0x1c00e9f96  call    cs:__imp_IoReleaseRemoveLockEx
0x1c00e9f9d  nop     dword ptr [rax+rax+00h]
0x1c00e9fa2  dec     dword ptr [r14+0B08h]
0x1c00e9fa9  cmp     ebx, 0C000022Dh
0x1c00e9faf  jz      loc_1C00E9C81
0x1c00e9fb5  cmp     ebx, 0C0000273h
0x1c00e9fbb  jz      loc_1C00E9C81
0x1c00e9fc1  cmp     ebx, 0C0000189h
  ... truncated ...
```
