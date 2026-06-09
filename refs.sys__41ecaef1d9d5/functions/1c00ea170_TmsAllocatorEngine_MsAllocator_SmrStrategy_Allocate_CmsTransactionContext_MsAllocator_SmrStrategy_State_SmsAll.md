# TmsAllocatorEngine<MsAllocator::SmrStrategy>::Allocate(CmsTransactionContext *,MsAllocator::SmrStrategy::State *,SmsAllocationContext *,_RANGE const *,_RANGE *,_RANGE *)

- ea: `0x1c00ea170`
- end: `0x1c00ea8a0`
- name: `?Allocate@?$TmsAllocatorEngine@VSmrStrategy@MsAllocator@@@@SAJPEAVCmsTransactionContext@@PEAUState@SmrStrategy@MsAllocator@@PEAUSmsAllocationContext@@PEBU_RANGE@@PEAU7@4@Z`
- size: `1840`
- prototype: `__int64 __usercall@<rax>(struct CmsTransactionContext *@<rcx>, struct _RANGE *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c0023ee4`

## callees

- `0x1c00247f0`
- `0x1c0024964`
- `0x1c0024b68`
- `0x1c00254d0`
- `0x1c0025f98`
- `0x1c0026868`
- `0x1c00268d4`
- `0x1c005a9d8`
- `0x1c005ac78`
- `0x1c0068960`
- `0x1c00bcc28`
- `0x1c00ea170`
- `0x1c00ebe38`
- `0x1c00ec2f0`

## import_xrefs

- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ea2cf`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ea82c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ea86a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ea2cf`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ea82c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ea86a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00ea613`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00ea6ee`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00ea7fc`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00ea613`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00ea6ee`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00ea7fc`

## pseudocode

```c
__int64 __fastcall TmsAllocatorEngine<MsAllocator::SmrStrategy>::Allocate(
        struct CmsTransactionContext *a1,
        struct MsAllocator::SmrStrategy::State *a2,
        __int64 a3,
        __int64 a4,
        struct _RANGE *a5,
        struct _RANGE *a6)
{
  __int64 v6; // r15
  unsigned __int64 v8; // r12
  int v10; // eax
  int v11; // eax
  unsigned __int64 v12; // rsi
  int v13; // ecx
  struct SmsAllocationContext *v14; // r8
  struct MsAllocator::SmrStrategy::State *v15; // rdx
  int Space; // eax
  int v17; // ebx
  SmsAllocationRegionEx *v18; // rcx
  int Candidate; // eax
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rcx
  __int16 v22; // bx
  unsigned __int64 TotalFree; // rax
  int v24; // r8d
  int v25; // r9d
  unsigned int v26; // r11d
  bool v27; // r9
  __int16 v28; // bx
  int v29; // edx
  bool v30; // r8
  bool v31; // al
  unsigned __int64 v32; // rax
  int v33; // r8d
  int v34; // r9d
  char v35; // r10
  int v36; // eax
  unsigned __int64 v37; // rax
  unsigned __int64 v38; // rax
  int v39; // r8d
  int v40; // r9d
  char v41; // r10
  CmsVolume *v42; // rbx
  __int64 v43; // rcx
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  __int64 v46; // rbx
  __int64 v47; // rcx
  __int64 v48; // r12
  struct SmsAllocationContext *v49; // r8
  unsigned __int64 v50; // rcx
  int v51; // eax
  bool v52; // zf
  struct _IO_REMOVE_LOCK *v53; // rcx
  struct _RANGE *v54; // rcx
  char v55; // al
  struct SmsContainer *v56; // rsi
  __int64 v57; // rcx
  SmsAllocationRegionEx *v58; // rcx
  SmsAllocationRegionEx *v59; // rcx
  signed __int32 v61[8]; // [rsp+0h] [rbp-100h] BYREF
  struct _RANGE *v62; // [rsp+20h] [rbp-E0h]
  char v63; // [rsp+40h] [rbp-C0h]
  CmsVolume *v64; // [rsp+48h] [rbp-B8h]
  int v65; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v66; // [rsp+58h] [rbp-A8h]
  struct SmsContainer *v67; // [rsp+60h] [rbp-A0h] BYREF
  struct SmsContainer *v68; // [rsp+68h] [rbp-98h] BYREF
  __int128 v69; // [rsp+70h] [rbp-90h]
  struct _RANGE *v70; // [rsp+80h] [rbp-80h]
  __int128 v71; // [rsp+88h] [rbp-78h] BYREF
  __int128 v72; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v73[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v74; // [rsp+F0h] [rbp-10h]
  struct MsAllocator::SmrStrategy::State *v75; // [rsp+100h] [rbp+0h] BYREF
  __int128 v76; // [rsp+108h] [rbp+8h] BYREF
  __int64 v77; // [rsp+118h] [rbp+18h]
  struct SmsAllocationContext *v78; // [rsp+120h] [rbp+20h]
  struct MsAllocator::SmrStrategy::State **v79; // [rsp+128h] [rbp+28h]
  __int128 v80; // [rsp+130h] [rbp+30h] BYREF
  SmsAllocationRegionEx *v81; // [rsp+140h] [rbp+40h]
  __int64 v82; // [rsp+148h] [rbp+48h]
  int v83; // [rsp+150h] [rbp+50h]

  v6 = *(_QWORD *)(a3 + 16);
  v8 = *(_QWORD *)(a4 + 8);
  v70 = a6;
  v64 = *(CmsVolume **)(v6 + 48);
  v79 = &v75;
  v10 = *(_DWORD *)(a3 + 68) & 8;
  v75 = a2;
  v65 = v10;
  v11 = *(_DWORD *)(a3 + 104);
  v77 = 0;
  v78 = (struct SmsAllocationContext *)a3;
  v81 = 0;
  v83 = 0;
  v82 = 0;
  v67 = 0;
  v66 = v8;
  v63 = 0;
  v76 = MsZeroRange;
  v80 = MsZeroRange;
  v12 = *(int *)(v6 + 60);
  v72 = 0;
  if ( v8 > 0x20 || (v13 = 4, (v11 & 2) == 0) )
    v13 = 0;
  *(_DWORD *)(a3 + 104) = v13 | v11 & 0xFFFFFFFB;
  do
  {
    while ( 1 )
    {
      do
      {
        v77 = 0;
        v76 = MsZeroRange;
LABEL_6:
        v14 = v78;
        v15 = v75;
        *(_OWORD *)(a3 + 80) = 0;
        v81 = 0;
        *(_QWORD *)(a3 + 96) = 0;
        v83 = 0;
        v82 = 0;
        v80 = MsZeroRange;
        Space = MsAllocator::SmrStrategy::NextSpace(a1, v15, v14, (struct MsAllocator::SmrStrategy::Context *)&v76);
        v17 = Space;
      }
      while ( Space == -1073741267 );
      if ( Space != -1073741197 )
        break;
      if ( (*(_DWORD *)(a3 + 104) & 0x200) == 0 || v63 )
      {
        v17 = -1073741697;
        break;
      }
      v63 = 1;
    }
    if ( v17 < 0 )
      break;
    do
    {
      while ( 1 )
      {
        if ( (v83 & 4) != 0 )
        {
          v18 = v81;
          _InterlockedDecrement((volatile signed __int32 *)v81 + 10);
          ExReleasePushLockEx((char *)v18 + 32, 0);
          LOBYTE(v83) = v83 & 0xFB;
        }
        Candidate = MsAllocator::SmrStrategy::NextCandidate(
                      a1,
                      *v79,
                      v79[4],
                      (struct MsAllocator::SmrStrategy::Context *)(v79 + 1),
                      (struct MsAllocator::AllocationCandidate *)&v80);
        v17 = Candidate;
        if ( Candidate < 0 )
          break;
        if ( !v65 )
          goto LABEL_21;
        v20 = -(int)v12 & (unsigned __int64)(v80 + (int)v12 - 1);
        *((_QWORD *)&v69 + 1) = *(&MsZeroRange + 1);
        *(_QWORD *)&v69 = v20;
        if ( *((_QWORD *)&v80 + 1) + (_QWORD)v80 <= v20 )
        {
          v21 = *((_QWORD *)&v69 + 1);
        }
        else
        {
          v21 = v80 + *((_QWORD *)&v80 + 1) - v20;
          *((_QWORD *)&v69 + 1) = v21;
        }
        if ( v21 >= v12 )
        {
          v80 = v69;
LABEL_21:
          v22 = *((_WORD *)v81 + 12);
          TotalFree = SmsAllocationRegionEx::GetTotalFree(v81);
          if ( TotalFree >= *((_QWORD *)&v80 + 1) )
            TotalFree = *((_QWORD *)&v80 + 1);
          if ( TotalFree && (TotalFree >= v8 || !v24) && (v22 & 0x64) == 0 && (v25 || (v22 & 8) == 0) )
          {
            if ( (v83 & 2) != 0 || (v27 = v26, v63 != (_BYTE)v26) )
              v27 = 1;
            v28 = v22 & 2;
            _InterlockedOr(v61, v26);
            v29 = *(_DWORD *)(a3 + 104);
            if ( (v83 & 1) == 0 && ((v29 & 4) != 0 || v28) )
              v30 = v26;
            else
              v30 = 1;
            if ( v28 || *((_QWORD *)v81 + 1) != *(_DWORD *)(v6 + 60) || v27 || v30 || (v31 = 1, (v29 & 0x200) != 0) )
              v31 = v26;
            if ( !CmsAllocator::TryLockCandidateForAllocation(
                    (CmsAllocator *)v6,
                    a1,
                    (struct SmsAllocationContext *)a3,
                    (const struct MsAllocator::AllocationCandidate *)&v80,
                    v27,
                    v30,
                    v31) )
              goto LABEL_55;
            LOBYTE(v83) = v83 | 4;
            v32 = SmsAllocationRegionEx::GetTotalFree(v81);
            if ( v32 >= *((_QWORD *)&v80 + 1) )
              v32 = *((_QWORD *)&v80 + 1);
            if ( v32 && (v32 >= v8 || !v33) && (v35 & 0x64) == 0 && (v34 || (v35 & 8) == 0) )
            {
              if ( v28 )
              {
                v36 = CmsAllocator::PrepareRangeOnlyCandidateForAllocation(
                        (CmsAllocator *)v6,
                        a1,
                        (struct SmsAllocationContext *)a3,
                        (struct MsAllocator::AllocationCandidate *)&v80);
                v17 = v36;
                if ( v36 >= 0 )
                {
                  v38 = SmsAllocationRegionEx::GetTotalFree(v81);
                  if ( v38 >= *((_QWORD *)&v80 + 1) )
                    v38 = *((_QWORD *)&v80 + 1);
                  if ( v38 && (v38 >= v8 || !v39) && (v41 & 0x64) == 0 && (v40 || (v41 & 8) == 0) )
                    goto LABEL_66;
                }
                else
                {
                  if ( v36 != -1073741267 )
                    goto LABEL_96;
LABEL_55:
                  v37 = v12;
                  if ( *((_QWORD *)&v80 + 1) < v12 )
                    v37 = *((_QWORD *)&v80 + 1);
                  *((_QWORD *)&v80 + 1) = v37;
                }
              }
              else
              {
LABEL_66:
                if ( (*(_DWORD *)(a3 + 104) & 1) != 0 )
                {
                  CmsAllocator::UnlockCache((CmsAllocator *)v6, a1, (struct SmsPushLockContext *)(a3 + 40));
                  *(_DWORD *)(a3 + 104) &= ~1u;
                }
                v42 = v64;
                v43 = *((_QWORD *)v64 + 381);
                v44 = *((_OWORD *)v81 + 1);
                v73[1] = *(_OWORD *)v81;
                v45 = *((_OWORD *)v81 + 2);
                v73[2] = v44;
                *(_QWORD *)&v44 = *((_QWORD *)v81 + 6);
                v73[3] = v45;
                v74 = v44;
                v71 = 0;
                v68 = 0;
                v73[0] = v80;
                LOBYTE(v62) = 0;
                CmsVolumeContainer::RealRangeToContainerRange(v43, a1, v73, &v71, (_DWORD)v62, 0);
                CmsVolumeContainer::GetContainerReference(
                  *((CmsVolumeContainer **)v42 + 381),
                  a1,
                  (unsigned __int64)v71 >> ((unsigned __int8)*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v42 + 381) + 8LL) + 76LL)
                                          + 1),
                  &v68,
                  1u,
                  0,
                  0);
                v46 = *((int *)v68 + 153);
                v47 = *((_QWORD *)v64 + 381);
                _InterlockedDecrement((volatile signed __int32 *)v68 + 22);
                IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v47 + 328), 0, 0x20u);
                --*((_DWORD *)a1 + 706);
                if ( v46 != v12 )
                {
                  v48 = (int)v12 - 1;
                  v49 = (struct SmsAllocationContext *)-(int)v12;
                  v50 = ((unsigned __int64)v49 & (*((_QWORD *)&v80 + 1) + v80 + v48)) - (v80 & (unsigned __int64)v49);
                  *(_QWORD *)&v80 = (v80 & (unsigned __int64)v49) + v46;
                  *((_QWORD *)&v80 + 1) = v50 - v46;
                  if ( *(_BYTE *)(v6 + 84) != 2 )
                  {
                    v51 = CmsAllocator::PopulateContainersForCandidate(
                            (CmsAllocator *)v6,
                            a1,
                            v49,
                            (const struct MsAllocator::AllocationCandidate *)&v80,
                            (struct _RANGE *)&v72,
                            &v67);
                    v17 = v51;
                    if ( v51 < 0 )
                    {
                      v52 = v51 == -1073741267;
                      goto LABEL_78;
                    }
                  }
                  *(_DWORD *)(a3 + 104) &= ~0x80u;
                  v17 = CmsAllocator::AllocateFromCandidate(
                          (CmsAllocator *)v6,
                          a1,
                          (struct SmsAllocationContext *)a3,
                          (struct MsAllocator::AllocationCandidate *)&v80,
                          a5);
                  if ( v17 >= 0 )
                  {
                    v54 = v70;
                    *(_OWORD *)v70 = *(_OWORD *)a5;
                    v55 = *(_BYTE *)(v6 + 84);
                    if ( v55 != 2 )
                    {
                      v56 = v67;
                      if ( v55 == 4 )
                        CmsAllocator::UpdateVolumeContainerForCompletedAllocation(
                          (CmsAllocator *)v6,
                          a1,
                          (struct SmsAllocationContext *)a3,
                          v67,
                          v54);
                      v57 = *((_QWORD *)v64 + 381);
                      _InterlockedDecrement((volatile signed __int32 *)v56 + 22);
                      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v57 + 328), 0, 0x20u);
                      --*((_DWORD *)a1 + 706);
                      *(_QWORD *)a5 = v72 + (v48 & *(_QWORD *)a5);
                    }
                    v58 = v81;
                    _InterlockedDecrement((volatile signed __int32 *)v81 + 10);
                    ExReleasePushLockEx((char *)v58 + 32, 0);
                    LOBYTE(v83) = v83 & 0xFB;
                    goto LABEL_96;
                  }
                  if ( *(_BYTE *)(v6 + 84) != 2 )
                  {
                    v53 = (struct _IO_REMOVE_LOCK *)(*((_QWORD *)v64 + 381) + 328LL);
                    _InterlockedDecrement((volatile signed __int32 *)v67 + 22);
                    IoReleaseRemoveLockEx(v53, 0, 0x20u);
                    --*((_DWORD *)a1 + 706);
                  }
                  if ( v17 != -1073741267 && v17 != -1073741197 )
                  {
                    v52 = v17 == -1073741431;
LABEL_78:
                    if ( !v52 )
                      goto LABEL_96;
                  }
                  v8 = v66;
                }
              }
            }
          }
        }
      }
      if ( Candidate == -1073741197 || Candidate == -1073741172 )
        goto LABEL_6;
    }
    while ( Candidate == -1073741198 );
    if ( Candidate != -1073741400 || (*(_DWORD *)(a3 + 68) & 0x800) != 0 )
      break;
    if ( (*(_DWORD *)(a3 + 104) & 1) != 0 )
    {
      CmsAllocator::UnlockCache((CmsAllocator *)v6, a1, (struct SmsPushLockContext *)(a3 + 40));
      *(_DWORD *)(a3 + 104) &= ~1u;
    }
    v17 = CmsVolume::TriageAllocator(v64, a1);
  }
  while ( v17 >= 0 );
LABEL_96:
  if ( (*(_DWORD *)(a3 + 104) & 1) != 0 )
  {
    CmsAllocator::UnlockCache((CmsAllocator *)v6, a1, (struct SmsPushLockContext *)(a3 + 40));
    *(_DWORD *)(a3 + 104) &= ~1u;
  }
  if ( (v83 & 4) != 0 )
  {
    v59 = v81;
    _InterlockedDecrement((volatile signed __int32 *)v81 + 10);
    ExReleasePushLockEx((char *)v59 + 32, 0);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1c00ea170  mov     [rsp-8+arg_8], rbx
0x1c00ea175  push    rbp
0x1c00ea176  push    rsi
0x1c00ea177  push    rdi
0x1c00ea178  push    r12
0x1c00ea17a  push    r13
0x1c00ea17c  push    r14
0x1c00ea17e  push    r15
0x1c00ea180  lea     rbp, [rsp-70h]
0x1c00ea185  sub     rsp, 170h
0x1c00ea18c  mov     rax, cs:__security_cookie
0x1c00ea193  xor     rax, rsp
0x1c00ea196  mov     [rbp+0A0h+var_40], rax
0x1c00ea19a  movups  xmm0, cs:?MsZeroRange@@3U_RANGE@@B; _RANGE const MsZeroRange
0x1c00ea1a1  mov     r15, [r8+10h]
0x1c00ea1a5  xor     r11d, r11d
0x1c00ea1a8  mov     rax, [rbp+0A0h+arg_28]
0x1c00ea1af  mov     rdi, r8
0x1c00ea1b2  mov     r12, [r9+8]
0x1c00ea1b6  mov     r14, rcx
0x1c00ea1b9  mov     r13, [rbp+0A0h+arg_20]
0x1c00ea1c0  mov     [rbp+0A0h+var_120], rax
0x1c00ea1c4  mov     rax, [r15+30h]
0x1c00ea1c8  mov     [rsp+1A0h+var_158], rax
0x1c00ea1cd  lea     rax, [rbp+0A0h+var_A0]
0x1c00ea1d1  mov     [rbp+0A0h+var_78], rax
0x1c00ea1d5  mov     eax, [r8+44h]
0x1c00ea1d9  and     eax, 8
0x1c00ea1dc  mov     [rbp+0A0h+var_A0], rdx
0x1c00ea1e0  mov     [rsp+1A0h+var_150], eax
0x1c00ea1e4  mov     eax, [r8+68h]
0x1c00ea1e8  mov     [rbp+0A0h+var_88], r11
0x1c00ea1ec  mov     [rbp+0A0h+var_80], r8
0x1c00ea1f0  mov     [rbp+0A0h+var_60], r11
0x1c00ea1f4  mov     [rbp+0A0h+var_50], r11d
0x1c00ea1f8  mov     [rbp+0A0h+var_58], r11
0x1c00ea1fc  mov     [rsp+1A0h+var_140], r11
0x1c00ea201  mov     [rsp+1A0h+var_148], r12
0x1c00ea206  mov     [rsp+1A0h+var_160], r11b
0x1c00ea20b  movdqu  [rbp+0A0h+var_98], xmm0
0x1c00ea210  movdqu  [rbp+0A0h+var_70], xmm0
0x1c00ea215  movsxd  rsi, dword ptr [r15+3Ch]
0x1c00ea219  xorps   xmm0, xmm0
0x1c00ea21c  movups  [rbp+0A0h+var_108], xmm0
0x1c00ea220  cmp     r12, 20h ; ' '
0x1c00ea224  ja      short loc_1C00EA22E
0x1c00ea226  lea     ecx, [r11+4]
0x1c00ea22a  test    al, 2
0x1c00ea22c  jnz     short loc_1C00EA231
0x1c00ea22e  mov     ecx, r11d
0x1c00ea231  and     eax, 0FFFFFFFBh
0x1c00ea234  or      eax, ecx
0x1c00ea236  mov     [r8+68h], eax
0x1c00ea23a  movups  xmm0, cs:?MsZeroRange@@3U_RANGE@@B; _RANGE const MsZeroRange
0x1c00ea241  mov     [rbp+0A0h+var_88], r11
0x1c00ea245  movdqu  [rbp+0A0h+var_98], xmm0
0x1c00ea24a  mov     r8, [rbp+0A0h+var_80]; struct SmsAllocationContext *
0x1c00ea24e  lea     r9, [rbp+0A0h+var_98]; struct MsAllocator::SmrStrategy::Context *
0x1c00ea252  mov     rdx, [rbp+0A0h+var_A0]; struct MsAllocator::SmrStrategy::State *
0x1c00ea256  xorps   xmm0, xmm0
0x1c00ea259  movups  xmmword ptr [rdi+50h], xmm0
0x1c00ea25d  xor     eax, eax
0x1c00ea25f  mov     [rbp+0A0h+var_60], r11
0x1c00ea263  mov     [rdi+60h], rax
0x1c00ea267  mov     rcx, r14; struct CmsTransactionContext *
0x1c00ea26a  movups  xmm0, cs:?MsZeroRange@@3U_RANGE@@B; _RANGE const MsZeroRange
0x1c00ea271  mov     [rbp+0A0h+var_50], r11d
0x1c00ea275  mov     [rbp+0A0h+var_58], r11
0x1c00ea279  movdqu  [rbp+0A0h+var_70], xmm0
0x1c00ea27e  call    ?NextSpace@SmrStrategy@MsAllocator@@CAJPEAVCmsTransactionContext@@PEAUState@12@PEAUSmsAllocationContext@@AEAUContext@12@@Z; MsAllocator::SmrStrategy::NextSpace(CmsTransactionContext *,MsAllocator::SmrStrategy::State *,SmsAllocationContext *,MsAllocator::SmrStrategy::Context &)
0x1c00ea283  mov     ebx, eax
0x1c00ea285  cmp     eax, 0C000022Dh
0x1c00ea28a  jz      loc_1C00EA799
0x1c00ea290  cmp     eax, 0C0000273h
0x1c00ea295  jnz     short loc_1C00EA2B3
0x1c00ea297  test    dword ptr [rdi+68h], 200h
0x1c00ea29e  jz      short loc_1C00EA2AE
0x1c00ea2a0  xor     r11d, r11d
0x1c00ea2a3  cmp     [rsp+1A0h+var_160], r11b
0x1c00ea2a8  jz      loc_1C00EA7A1
0x1c00ea2ae  mov     ebx, 0C000007Fh
0x1c00ea2b3  test    ebx, ebx
0x1c00ea2b5  js      loc_1C00EA83C
0x1c00ea2bb  test    byte ptr [rbp+0A0h+var_50], 4
0x1c00ea2bf  jz      short loc_1C00EA2DF
0x1c00ea2c1  mov     rcx, [rbp+0A0h+var_60]
0x1c00ea2c5  xor     edx, edx
0x1c00ea2c7  lock dec dword ptr [rcx+28h]
0x1c00ea2cb  add     rcx, 20h ; ' '
0x1c00ea2cf  call    cs:__imp_ExReleasePushLockEx
0x1c00ea2d6  nop     dword ptr [rax+rax+00h]
0x1c00ea2db  and     byte ptr [rbp+0A0h+var_50], 0FBh
0x1c00ea2df  mov     rdx, [rbp+0A0h+var_78]
0x1c00ea2e3  lea     rax, [rbp+0A0h+var_70]
0x1c00ea2e7  mov     rcx, r14; struct CmsTransactionContext *
0x1c00ea2ea  mov     [rsp+1A0h+var_180], rax; struct MsAllocator::AllocationCandidate *
0x1c00ea2ef  mov     r8, [rdx+20h]; struct SmsAllocationContext *
0x1c00ea2f3  lea     r9, [rdx+8]; struct MsAllocator::SmrStrategy::Context *
0x1c00ea2f7  mov     rdx, [rdx]; struct MsAllocator::SmrStrategy::State *
0x1c00ea2fa  call    ?NextCandidate@SmrStrategy@MsAllocator@@CAJPEAVCmsTransactionContext@@PEAUState@12@PEAUSmsAllocationContext@@AEAUContext@12@AEAUAllocationCandidate@2@@Z; MsAllocator::SmrStrategy::NextCandidate(CmsTransactionContext *,MsAllocator::SmrStrategy::State *,SmsAllocationContext *,MsAllocator::SmrStrategy::Context &,MsAllocator::AllocationCandidate &)
0x1c00ea2ff  xor     r11d, r11d
0x1c00ea302  mov     ebx, eax
0x1c00ea304  test    eax, eax
0x1c00ea306  js      loc_1C00EA727
0x1c00ea30c  cmp     [rsp+1A0h+var_150], r11d
0x1c00ea311  jz      short loc_1C00EA36E
0x1c00ea313  mov     r8, qword ptr [rbp+0A0h+var_70]
0x1c00ea317  lea     eax, [rsi-1]
0x1c00ea31a  movups  xmm0, cs:?MsZeroRange@@3U_RANGE@@B; _RANGE const MsZeroRange
0x1c00ea321  movsxd  rdx, eax
0x1c00ea324  mov     eax, esi
0x1c00ea326  neg     eax
0x1c00ea328  add     rdx, r8
0x1c00ea32b  movsxd  rcx, eax
0x1c00ea32e  and     rdx, rcx
0x1c00ea331  mov     rcx, qword ptr [rbp+0A0h+var_70+8]
0x1c00ea335  movdqu  [rsp+1A0h+var_130], xmm0
0x1c00ea33b  mov     qword ptr [rsp+1A0h+var_130], rdx
0x1c00ea340  lea     rax, [rcx+r8]
0x1c00ea344  cmp     rax, rdx
0x1c00ea347  jbe     short loc_1C00EA356
0x1c00ea349  sub     rcx, rdx
0x1c00ea34c  add     rcx, r8
0x1c00ea34f  mov     qword ptr [rsp+1A0h+var_130+8], rcx
0x1c00ea354  jmp     short loc_1C00EA35B
0x1c00ea356  mov     rcx, qword ptr [rsp+1A0h+var_130+8]
0x1c00ea35b  cmp     rcx, rsi
0x1c00ea35e  jb      loc_1C00EA2BB
0x1c00ea364  movups  xmm0, [rsp+1A0h+var_130]
0x1c00ea369  movdqu  [rbp+0A0h+var_70], xmm0
0x1c00ea36e  mov     rcx, [rbp+0A0h+var_60]; this
0x1c00ea372  mov     r8d, [rdi+44h]
0x1c00ea376  mov     r9d, r8d
0x1c00ea379  and     r9d, 40h
0x1c00ea37d  and     r8d, 8
0x1c00ea381  movzx   ebx, word ptr [rcx+18h]
0x1c00ea385  call    ?GetTotalFree@SmsAllocationRegionEx@@QEBA?B_KXZ; SmsAllocationRegionEx::GetTotalFree(void)
0x1c00ea38a  cmp     rax, qword ptr [rbp+0A0h+var_70+8]
0x1c00ea38e  cmovnb  rax, qword ptr [rbp+0A0h+var_70+8]
0x1c00ea393  test    rax, rax
0x1c00ea396  jz      loc_1C00EA2BB
0x1c00ea39c  cmp     rax, r12
0x1c00ea39f  jnb     short loc_1C00EA3AA
0x1c00ea3a1  test    r8d, r8d
0x1c00ea3a4  jnz     loc_1C00EA2BB
0x1c00ea3aa  test    bl, 64h
0x1c00ea3ad  jnz     loc_1C00EA2BB
0x1c00ea3b3  test    r9d, r9d
0x1c00ea3b6  jnz     short loc_1C00EA3C1
0x1c00ea3b8  test    bl, 8
0x1c00ea3bb  jnz     loc_1C00EA2BB
0x1c00ea3c1  test    byte ptr [rbp+0A0h+var_50], 2
0x1c00ea3c5  jnz     short loc_1C00EA3D1
0x1c00ea3c7  mov     r9b, r11b
0x1c00ea3ca  cmp     [rsp+1A0h+var_160], r11b
0x1c00ea3cf  jz      short loc_1C00EA3D4
0x1c00ea3d1  mov     r9b, 1
0x1c00ea3d4  and     bx, 2
0x1c00ea3d8  lock or [rsp+1A0h+var_1A0], r11d
0x1c00ea3dd  test    byte ptr [rbp+0A0h+var_50], 1
0x1c00ea3e1  mov     edx, [rdi+68h]
0x1c00ea3e4  jnz     short loc_1C00EA3F5
0x1c00ea3e6  test    dl, 4
0x1c00ea3e9  jnz     short loc_1C00EA3F0
0x1c00ea3eb  test    bx, bx
0x1c00ea3ee  jz      short loc_1C00EA3F5
0x1c00ea3f0  mov     r8b, r11b
0x1c00ea3f3  jmp     short loc_1C00EA3F8
0x1c00ea3f5  mov     r8b, 1
0x1c00ea3f8  test    bx, bx
0x1c00ea3fb  jnz     short loc_1C00EA41D
0x1c00ea3fd  mov     rax, [rbp+0A0h+var_60]
0x1c00ea401  movsxd  rcx, dword ptr [r15+3Ch]
0x1c00ea405  cmp     [rax+8], rcx
0x1c00ea409  jnz     short loc_1C00EA41D
0x1c00ea40b  test    r9b, r9b
0x1c00ea40e  jnz     short loc_1C00EA41D
0x1c00ea410  test    r8b, r8b
0x1c00ea413  jnz     short loc_1C00EA41D
0x1c00ea415  mov     al, 1
0x1c00ea417  bt      edx, 9
0x1c00ea41b  jnb     short loc_1C00EA420
0x1c00ea41d  mov     al, r11b
0x1c00ea420  mov     [rsp+1A0h+var_170], al; bool
0x1c00ea424  mov     rdx, r14; struct CmsTransactionContext *
0x1c00ea427  mov     byte ptr [rsp+1A0h+var_178], r8b; bool
0x1c00ea42c  mov     rcx, r15; this
0x1c00ea42f  mov     byte ptr [rsp+1A0h+var_180], r9b; bool
0x1c00ea434  mov     r8, rdi; struct SmsAllocationContext *
0x1c00ea437  lea     r9, [rbp+0A0h+var_70]; struct MsAllocator::AllocationCandidate *
0x1c00ea43b  call    ?TryLockCandidateForAllocation@CmsAllocator@@AEAA_NPEAVCmsTransactionContext@@PEAUSmsAllocationContext@@AEBUAllocationCandidate@MsAllocator@@_N33@Z; CmsAllocator::TryLockCandidateForAllocation(CmsTransactionContext *,SmsAllocationContext *,MsAllocator::AllocationCandidate const &,bool,bool,bool)
0x1c00ea440  test    al, al
0x1c00ea442  jz      loc_1C00EA4CE
0x1c00ea448  mov     rcx, [rbp+0A0h+var_60]; this
0x1c00ea44c  mov     r8d, [rdi+44h]
0x1c00ea450  mov     r9d, r8d
0x1c00ea453  or      byte ptr [rbp+0A0h+var_50], 4
0x1c00ea457  and     r9d, 40h
0x1c00ea45b  and     r8d, 8
0x1c00ea45f  movzx   r10d, word ptr [rcx+18h]
0x1c00ea464  call    ?GetTotalFree@SmsAllocationRegionEx@@QEBA?B_KXZ; SmsAllocationRegionEx::GetTotalFree(void)
0x1c00ea469  cmp     rax, qword ptr [rbp+0A0h+var_70+8]
0x1c00ea46d  cmovnb  rax, qword ptr [rbp+0A0h+var_70+8]
0x1c00ea472  test    rax, rax
0x1c00ea475  jz      loc_1C00EA2BB
0x1c00ea47b  cmp     rax, r12
0x1c00ea47e  jnb     short loc_1C00EA489
0x1c00ea480  test    r8d, r8d
0x1c00ea483  jnz     loc_1C00EA2BB
0x1c00ea489  test    r10b, 64h
0x1c00ea48d  jnz     loc_1C00EA2BB
0x1c00ea493  test    r9d, r9d
0x1c00ea496  jnz     short loc_1C00EA4A2
0x1c00ea498  test    r10b, 8
0x1c00ea49c  jnz     loc_1C00EA2BB
0x1c00ea4a2  test    bx, bx
0x1c00ea4a5  jz      loc_1C00EA539
0x1c00ea4ab  lea     r9, [rbp+0A0h+var_70]; struct MsAllocator::AllocationCandidate *
0x1c00ea4af  mov     r8, rdi; struct SmsAllocationContext *
0x1c00ea4b2  mov     rdx, r14; struct CmsTransactionContext *
0x1c00ea4b5  mov     rcx, r15; this
0x1c00ea4b8  call    ?PrepareRangeOnlyCandidateForAllocation@CmsAllocator@@AEAAJPEAVCmsTransactionContext@@PEAUSmsAllocationContext@@AEAUAllocationCandidate@MsAllocator@@@Z; CmsAllocator::PrepareRangeOnlyCandidateForAllocation(CmsTransactionContext *,SmsAllocationContext *,MsAllocator::AllocationCandidate &)
0x1c00ea4bd  mov     ebx, eax
0x1c00ea4bf  test    eax, eax
0x1c00ea4c1  jns     short loc_1C00EA4E3
0x1c00ea4c3  cmp     eax, 0C000022Dh
0x1c00ea4c8  jnz     loc_1C00EA83C
0x1c00ea4ce  cmp     qword ptr [rbp+0A0h+var_70+8], rsi
0x1c00ea4d2  mov     rax, rsi
0x1c00ea4d5  cmovb   rax, qword ptr [rbp+0A0h+var_70+8]
0x1c00ea4da  mov     qword ptr [rbp+0A0h+var_70+8], rax
0x1c00ea4de  jmp     loc_1C00EA2BB
0x1c00ea4e3  mov     rcx, [rbp+0A0h+var_60]; this
0x1c00ea4e7  mov     r8d, [rdi+44h]
0x1c00ea4eb  mov     r9d, r8d
0x1c00ea4ee  and     r9d, 40h
0x1c00ea4f2  and     r8d, 8
0x1c00ea4f6  movzx   r10d, word ptr [rcx+18h]
0x1c00ea4fb  call    ?GetTotalFree@SmsAllocationRegionEx@@QEBA?B_KXZ; SmsAllocationRegionEx::GetTotalFree(void)
0x1c00ea500  cmp     rax, qword ptr [rbp+0A0h+var_70+8]
0x1c00ea504  cmovnb  rax, qword ptr [rbp+0A0h+var_70+8]
0x1c00ea509  test    rax, rax
0x1c00ea50c  jz      loc_1C00EA2BB
0x1c00ea512  cmp     rax, r12
0x1c00ea515  jnb     short loc_1C00EA520
0x1c00ea517  test    r8d, r8d
0x1c00ea51a  jnz     loc_1C00EA2BB
0x1c00ea520  test    r10b, 64h
0x1c00ea524  jnz     loc_1C00EA2BB
0x1c00ea52a  test    r9d, r9d
0x1c00ea52d  jnz     short loc_1C00EA539
0x1c00ea52f  test    r10b, 8
0x1c00ea533  jnz     loc_1C00EA2BB
0x1c00ea539  mov     eax, [rdi+68h]
0x1c00ea53c  test    al, 1
0x1c00ea53e  jz      short loc_1C00EA553
0x1c00ea540  lea     r8, [rdi+28h]; struct SmsPushLockContext *
0x1c00ea544  mov     rdx, r14; struct CmsTransactionContext *
0x1c00ea547  mov     rcx, r15; this
0x1c00ea54a  call    ?UnlockCache@CmsAllocator@@AEAAXPEAVCmsTransactionContext@@PEAUSmsPushLockContext@@@Z; CmsAllocator::UnlockCache(CmsTransactionContext *,SmsPushLockContext *)
0x1c00ea54f  and     dword ptr [rdi+68h], 0FFFFFFFEh
0x1c00ea553  mov     rax, [rbp+0A0h+var_60]
0x1c00ea557  lea     r9, [rbp+0A0h+var_118]
0x1c00ea55b  mov     rbx, [rsp+1A0h+var_158]
0x1c00ea560  lea     r8, [rbp+0A0h+var_F0]
0x1c00ea564  mov     rdx, r14
0x1c00ea567  movups  xmm0, xmmword ptr [rax]
0x1c00ea56a  mov     rcx, [rbx+0BE8h]
0x1c00ea571  movups  xmm1, xmmword ptr [rax+10h]
0x1c00ea575  movups  [rbp+0A0h+var_E0], xmm0
0x1c00ea579  movups  xmm0, xmmword ptr [rax+20h]
0x1c00ea57d  movups  [rbp+0A0h+var_D0], xmm1
0x1c00ea581  movsd   xmm1, qword ptr [rax+30h]
0x1c00ea586  xor     eax, eax
0x1c00ea588  movups  [rbp+0A0h+var_C0], xmm0
0x1c00ea58c  mov     [rsp+1A0h+var_178], rax
0x1c00ea591  movsd   [rbp+0A0h+var_B0], xmm1
0x1c00ea596  xorps   xmm0, xmm0
0x1c00ea599  movaps  xmm1, [rbp+0A0h+var_70]
0x1c00ea59d  movups  [rbp+0A0h+var_118], xmm0
0x1c00ea5a1  mov     [rsp+1A0h+var_138], rax
0x1c00ea5a6  movdqu  [rbp+0A0h+var_F0], xmm1
0x1c00ea5ab  mov     byte ptr [rsp+1A0h+var_180], al
0x1c00ea5af  call    ?RealRangeToContainerRange@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@U_RANGE@@PEAU3@EPEA_K@Z; CmsVolumeContainer::RealRangeToContainerRange(CmsTransactionContext *,_RANGE,_RANGE *,uchar,unsigned __int64 *)
0x1c00ea5b4  mov     r10, [rbx+0BE8h]
0x1c00ea5bb  lea     r9, [rsp+1A0h+var_138]; struct SmsContainer **
0x1c00ea5c0  mov     r8, qword ptr [rbp+0A0h+var_118]
0x1c00ea5c4  mov     rdx, r14; struct CmsTransactionContext *
0x1c00ea5c7  mov     [rsp+1A0h+var_170], 0; unsigned __int8
0x1c00ea5cc  mov     byte ptr [rsp+1A0h+var_178], 0; unsigned __int8
0x1c00ea5d1  mov     rax, [r10+8]
0x1c00ea5d5  mov     byte ptr [rsp+1A0h+var_180], 1; unsigned __int8
0x1c00ea5da  mov     ecx, [rax+4Ch]
0x1c00ea5dd  inc     ecx
0x1c00ea5df  shr     r8, cl; unsigned __int64
0x1c00ea5e2  mov     rcx, r10; this
0x1c00ea5e5  call    ?GetContainerReference@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@EEE@Z; CmsVolumeContainer::GetContainerReference(CmsTransactionContext *,unsigned __int64,SmsContainer * *,uchar,uchar,uchar)
0x1c00ea5ea  mov     rax, [rsp+1A0h+var_138]
0x1c00ea5ef  xor     edx, edx; Tag
0x1c00ea5f1  mov     rcx, [rsp+1A0h+var_158]
  ... truncated ...
```
