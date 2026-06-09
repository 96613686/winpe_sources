# TmsAllocatorEngine<MsAllocator::ThinProvisioningStrategy<MsAllocator::RangeArrayStrategy>>::Allocate(CmsTransactionContext *,MsAllocator::ThinProvisioningStrategy<MsAllocator::RangeArrayStrategy>::State *,SmsAllocationContext *,_RANGE const *,_RANGE *,_RANGE *)

- ea: `0x1c00e9410`
- end: `0x1c00e9b2c`
- name: `?Allocate@?$TmsAllocatorEngine@V?$ThinProvisioningStrategy@VRangeArrayStrategy@MsAllocator@@@MsAllocator@@@@SAJPEAVCmsTransactionContext@@PEAUState@?$ThinProvisioningStrategy@VRangeArrayStrategy@MsAllocator@@@MsAllocator@@PEAUSmsAllocationContext@@PEBU_RANGE@@PEAU7@4@Z`
- size: `1820`
- prototype: `__int64 __usercall@<rax>(struct CmsTransactionContext *@<rcx>, struct _RANGE *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c0023ee4`

## callees

- `0x1c00247f0`
- `0x1c00254d0`
- `0x1c0025f98`
- `0x1c0026628`
- `0x1c0026868`
- `0x1c00268d4`
- `0x1c005a9d8`
- `0x1c005ac78`
- `0x1c0068960`
- `0x1c00bcc28`
- `0x1c00e9410`
- `0x1c00eb9f0`
- `0x1c00ebf68`

## import_xrefs

- `ntoskrnl!ExReleasePushLockEx` at `0x1c00e9597`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00e9ab8`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00e9af6`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00e9597`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00e9ab8`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00e9af6`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00e994a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00e9a84`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00e994a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00e9a84`

## pseudocode

```c
__int64 __fastcall TmsAllocatorEngine<MsAllocator::ThinProvisioningStrategy<MsAllocator::RangeArrayStrategy>>::Allocate(
        struct CmsTransactionContext *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        struct _RANGE *a5,
        struct _RANGE *a6)
{
  __int64 v6; // r14
  unsigned __int64 v8; // rcx
  CmsVolume *v10; // rsi
  int v11; // eax
  int v12; // eax
  unsigned __int64 v13; // r13
  int v14; // ecx
  int Space; // eax
  int v16; // ebx
  SmsAllocationRegionEx *v17; // rcx
  int Candidate; // eax
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  __int16 v21; // bx
  unsigned __int64 TotalFree; // rax
  int v23; // r8d
  int v24; // r9d
  unsigned int v25; // r11d
  bool v26; // r9
  __int16 v27; // bx
  int v28; // edx
  bool v29; // r8
  bool v30; // si
  unsigned __int64 v31; // rax
  struct SmsAllocationContext *v32; // r8
  char v33; // r9
  int v34; // r10d
  __int64 v35; // rcx
  int v36; // eax
  unsigned __int64 v37; // rax
  unsigned __int64 v38; // rax
  char v39; // r9
  int v40; // r10d
  bool v41; // zf
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  int v44; // eax
  int v45; // edx
  int v46; // eax
  struct _IO_REMOVE_LOCK *v47; // rcx
  struct _RANGE *v48; // rcx
  char v49; // al
  struct SmsContainer *v50; // rsi
  __int64 v51; // rcx
  SmsAllocationRegionEx *v52; // rcx
  SmsAllocationRegionEx *v53; // rcx
  signed __int32 v55[8]; // [rsp+0h] [rbp-100h] BYREF
  struct _RANGE *v56; // [rsp+20h] [rbp-E0h]
  char v57; // [rsp+40h] [rbp-C0h]
  CmsVolume *v58; // [rsp+48h] [rbp-B8h]
  int v59; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v60; // [rsp+58h] [rbp-A8h]
  struct SmsContainer *v61; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v62; // [rsp+68h] [rbp-98h]
  __int64 v63; // [rsp+78h] [rbp-88h]
  struct _RANGE *v64; // [rsp+80h] [rbp-80h]
  _OWORD v65[4]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v66; // [rsp+C8h] [rbp-38h]
  __int64 v67; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v68; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v69; // [rsp+E8h] [rbp-18h]
  __int64 v70; // [rsp+F0h] [rbp-10h]
  __int128 v71; // [rsp+F8h] [rbp-8h]
  int v72; // [rsp+108h] [rbp+8h]
  __int16 v73; // [rsp+10Ch] [rbp+Ch]
  char v74; // [rsp+10Eh] [rbp+Eh]
  __int128 v75; // [rsp+110h] [rbp+10h]
  __int64 v76; // [rsp+120h] [rbp+20h]
  __int64 *v77; // [rsp+128h] [rbp+28h]
  __int128 v78; // [rsp+130h] [rbp+30h] BYREF
  SmsAllocationRegionEx *v79; // [rsp+140h] [rbp+40h]
  __int64 v80; // [rsp+148h] [rbp+48h]
  int v81; // [rsp+150h] [rbp+50h]

  v6 = *(_QWORD *)(a3 + 16);
  v8 = *(_QWORD *)(a4 + 8);
  v10 = *(CmsVolume **)(v6 + 48);
  v64 = a6;
  v77 = &v67;
  v11 = *(_DWORD *)(a3 + 68) & 8;
  v67 = a2;
  v59 = v11;
  v12 = *(_DWORD *)(a3 + 104);
  v69 = 0;
  v70 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v76 = a3;
  v79 = 0;
  v81 = 0;
  v80 = 0;
  v63 = a2;
  v58 = v10;
  v61 = 0;
  v60 = v8;
  v57 = 0;
  v68 = MsZeroRange;
  v71 = MsZeroRange;
  v75 = MsZeroRange;
  v78 = MsZeroRange;
  v13 = *(int *)(v6 + 60);
  v65[0] = 0;
  if ( v8 > 0x20 || (v14 = 4, (v12 & 2) == 0) )
    v14 = 0;
  *(_DWORD *)(a3 + 104) = v14 | v12 & 0xFFFFFFFB;
  do
  {
    while ( 1 )
    {
      do
      {
        v75 = MsZeroRange;
        v68 = MsZeroRange;
LABEL_6:
        *(_OWORD *)(a3 + 80) = 0;
        v79 = 0;
        *(_QWORD *)(a3 + 96) = 0;
        v81 = 0;
        v80 = 0;
        v78 = MsZeroRange;
        Space = MsAllocator::ThinProvisioningStrategy<MsAllocator::RangeArrayStrategy>::NextSpace(a1);
        v16 = Space;
      }
      while ( Space == -1073741267 );
      if ( Space != -1073741197 )
        break;
      if ( (*(_DWORD *)(a3 + 104) & 0x200) == 0 || v57 )
      {
        v16 = -1073741697;
        break;
      }
      v57 = 1;
    }
    if ( v16 < 0 )
      break;
    do
    {
      while ( 1 )
      {
        if ( (v81 & 4) != 0 )
        {
          v17 = v79;
          _InterlockedDecrement((volatile signed __int32 *)v79 + 10);
          ExReleasePushLockEx((char *)v17 + 32, 0);
          LOBYTE(v81) = v81 & 0xFB;
        }
        Candidate = MsAllocator::ThinProvisioningStrategy<MsAllocator::RangeArrayStrategy>::NextCandidate(
                      a1,
                      (struct MsAllocator::AllocationCandidate *)&v78);
        v16 = Candidate;
        if ( Candidate < 0 )
          break;
        if ( v59 )
        {
          v19 = -(int)v13 & (unsigned __int64)(v78 + (int)v13 - 1);
          *((_QWORD *)&v62 + 1) = *(&MsZeroRange + 1);
          *(_QWORD *)&v62 = v19;
          if ( *((_QWORD *)&v78 + 1) + (_QWORD)v78 <= v19 )
          {
            v20 = *((_QWORD *)&v62 + 1);
          }
          else
          {
            v20 = v78 + *((_QWORD *)&v78 + 1) - v19;
            *((_QWORD *)&v62 + 1) = v20;
          }
          if ( v20 >= v13 )
          {
            v78 = v62;
            goto LABEL_23;
          }
        }
        else
        {
LABEL_23:
          v21 = *((_WORD *)v79 + 12);
          TotalFree = SmsAllocationRegionEx::GetTotalFree(v79);
          if ( TotalFree >= *((_QWORD *)&v78 + 1) )
            TotalFree = *((_QWORD *)&v78 + 1);
          if ( !TotalFree || TotalFree < v60 && v23 || (v21 & 0x64) != 0 || !v24 && (v21 & 8) != 0 )
            goto LABEL_13;
          if ( (v81 & 2) != 0 || (v26 = v25, v57 != (_BYTE)v25) )
            v26 = 1;
          v27 = v21 & 2;
          _InterlockedOr(v55, v25);
          v28 = *(_DWORD *)(a3 + 104);
          if ( (v81 & 1) == 0 && ((v28 & 4) != 0 || v27) )
            v29 = v25;
          else
            v29 = 1;
          if ( v27 || *((_QWORD *)v79 + 1) != *(_DWORD *)(v6 + 60) || v26 || v29 || (v30 = 1, (v28 & 0x200) != 0) )
            v30 = v25;
          if ( !CmsAllocator::TryLockCandidateForAllocation(
                  (CmsAllocator *)v6,
                  a1,
                  (struct SmsAllocationContext *)a3,
                  (const struct MsAllocator::AllocationCandidate *)&v78,
                  v26,
                  v29,
                  v30) )
            goto LABEL_57;
          LOBYTE(v81) = v81 | 4;
          v31 = SmsAllocationRegionEx::GetTotalFree(v79);
          v35 = *((_QWORD *)&v78 + 1);
          if ( v31 >= *((_QWORD *)&v78 + 1) )
            v31 = *((_QWORD *)&v78 + 1);
          if ( !v31 || v31 < v60 && (_DWORD)v32 || (v33 & 0x64) != 0 || !v34 && (v33 & 8) != 0 )
            goto LABEL_13;
          if ( !v27 )
            goto LABEL_68;
          v36 = CmsAllocator::PrepareRangeOnlyCandidateForAllocation(
                  (CmsAllocator *)v6,
                  a1,
                  (struct SmsAllocationContext *)a3,
                  (struct MsAllocator::AllocationCandidate *)&v78);
          v16 = v36;
          if ( v36 < 0 )
          {
            if ( v36 != -1073741267 )
              goto LABEL_110;
LABEL_57:
            v37 = v13;
            if ( *((_QWORD *)&v78 + 1) < v13 )
              v37 = *((_QWORD *)&v78 + 1);
            *((_QWORD *)&v78 + 1) = v37;
            goto LABEL_13;
          }
          v38 = SmsAllocationRegionEx::GetTotalFree(v79);
          v35 = *((_QWORD *)&v78 + 1);
          if ( v38 >= *((_QWORD *)&v78 + 1) )
            v38 = *((_QWORD *)&v78 + 1);
          if ( !v38 || v38 < v60 && (_DWORD)v32 || (v39 & 0x64) != 0 || !v40 && (v39 & 8) != 0 )
          {
LABEL_13:
            v10 = v58;
          }
          else
          {
LABEL_68:
            if ( (*(_DWORD *)(a3 + 104) & 1) != 0 )
            {
              CmsAllocator::UnlockCache((CmsAllocator *)v6, a1, (struct SmsPushLockContext *)(a3 + 40));
              *(_DWORD *)(a3 + 104) &= ~1u;
              v35 = *((_QWORD *)&v78 + 1);
            }
            v41 = *(_BYTE *)(v6 + 84) == 2;
            v42 = *((_OWORD *)v79 + 1);
            v65[1] = *(_OWORD *)v79;
            v43 = *((_OWORD *)v79 + 2);
            v65[2] = v42;
            *(_QWORD *)&v42 = *((_QWORD *)v79 + 6);
            v65[3] = v43;
            v66 = v42;
            if ( !v41 )
            {
              v44 = CmsAllocator::PopulateContainersForCandidate(
                      (CmsAllocator *)v6,
                      a1,
                      v32,
                      (const struct MsAllocator::AllocationCandidate *)&v78,
                      (struct _RANGE *)v65,
                      &v61);
              v16 = v44;
              if ( v44 < 0 )
              {
                if ( v44 != -1073741267 )
                  goto LABEL_110;
                goto LABEL_13;
              }
              v35 = *((_QWORD *)&v78 + 1);
            }
            if ( (*(_BYTE *)(v6 + 84) == 4 || !byte_1C0136921) && (v45 = *(_DWORD *)(a3 + 104), (v45 & 4) != 0) )
            {
              v41 = !v30;
              v10 = v58;
              if ( !v41
                && v35 == *((_QWORD *)v79 + 1)
                && ((*(_DWORD *)(a3 + 68) & 0x400) != 0 || byte_1C0114F74[12 * *((int *)v58 + 871)]) )
              {
                v46 = 128;
                goto LABEL_85;
              }
            }
            else
            {
              v10 = v58;
            }
            v45 = *(_DWORD *)(a3 + 104);
            v46 = 0;
LABEL_85:
            v56 = a5;
            *(_DWORD *)(a3 + 104) = v46 | v45 & 0xFFFFFF7F;
            v16 = CmsAllocator::AllocateFromCandidate(
                    (CmsAllocator *)v6,
                    a1,
                    (struct SmsAllocationContext *)a3,
                    (struct MsAllocator::AllocationCandidate *)&v78,
                    v56);
            if ( v16 >= 0 )
            {
              if ( (*(_DWORD *)(a3 + 104) & 0x100) != 0 && (*(_DWORD *)(a3 + 104) & 0x20) == 0 )
                MsAllocator::RangeArrayStrategy::State::SetHint(
                  *(MsAllocator::RangeArrayStrategy::State **)(v63 + 8),
                  (struct SmsAllocationContext *)a3,
                  (const struct MsAllocator::RangeArrayStrategy::Context *)&v68,
                  a5);
              v48 = v64;
              *(_OWORD *)v64 = *(_OWORD *)a5;
              v49 = *(_BYTE *)(v6 + 84);
              if ( v49 != 2 )
              {
                v50 = v61;
                if ( v49 == 4 )
                  CmsAllocator::UpdateVolumeContainerForCompletedAllocation(
                    (CmsAllocator *)v6,
                    a1,
                    (struct SmsAllocationContext *)a3,
                    v61,
                    v48);
                v51 = *((_QWORD *)v58 + 381);
                _InterlockedDecrement((volatile signed __int32 *)v50 + 22);
                IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v51 + 328), 0, 0x20u);
                --*((_DWORD *)a1 + 706);
                *(_QWORD *)a5 = *(_QWORD *)&v65[0] + (*(_QWORD *)a5 & ((int)v13 - 1));
              }
              v52 = v79;
              _InterlockedDecrement((volatile signed __int32 *)v79 + 10);
              ExReleasePushLockEx((char *)v52 + 32, 0);
              LOBYTE(v81) = v81 & 0xFB;
              goto LABEL_110;
            }
            if ( *(_BYTE *)(v6 + 84) != 2 )
            {
              v47 = (struct _IO_REMOVE_LOCK *)(*((_QWORD *)v10 + 381) + 328LL);
              _InterlockedDecrement((volatile signed __int32 *)v61 + 22);
              IoReleaseRemoveLockEx(v47, 0, 0x20u);
              --*((_DWORD *)a1 + 706);
            }
            if ( v16 != -1073741267 && v16 != -1073741197 && v16 != -1073741431 )
              goto LABEL_110;
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
    v16 = CmsVolume::TriageAllocator(v10, a1);
  }
  while ( v16 >= 0 );
LABEL_110:
  if ( (*(_DWORD *)(a3 + 104) & 1) != 0 )
  {
    CmsAllocator::UnlockCache((CmsAllocator *)v6, a1, (struct SmsPushLockContext *)(a3 + 40));
    *(_DWORD *)(a3 + 104) &= ~1u;
  }
  if ( (v81 & 4) != 0 )
  {
    v53 = v79;
    _InterlockedDecrement((volatile signed __int32 *)v79 + 10);
    ExReleasePushLockEx((char *)v53 + 32, 0);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1c00e9410  mov     [rsp-8+arg_18], rbx
0x1c00e9415  push    rbp
0x1c00e9416  push    rsi
0x1c00e9417  push    rdi
0x1c00e9418  push    r12
0x1c00e941a  push    r13
0x1c00e941c  push    r14
0x1c00e941e  push    r15
0x1c00e9420  lea     rbp, [rsp-70h]
0x1c00e9425  sub     rsp, 170h
0x1c00e942c  mov     rax, cs:__security_cookie
0x1c00e9433  xor     rax, rsp
0x1c00e9436  mov     [rbp+0A0h+var_40], rax
0x1c00e943a  movups  xmm0, cs:?MsZeroRange@@3U_RANGE@@B; _RANGE const MsZeroRange
0x1c00e9441  mov     r14, [r8+10h]
0x1c00e9445  xor     r11d, r11d
0x1c00e9448  mov     rax, [rbp+0A0h+arg_28]
0x1c00e944f  mov     r15, rcx
0x1c00e9452  mov     rcx, [r9+8]
0x1c00e9456  mov     rdi, r8
0x1c00e9459  mov     r12, [rbp+0A0h+arg_20]
0x1c00e9460  mov     rsi, [r14+30h]
0x1c00e9464  mov     [rbp+0A0h+var_120], rax
0x1c00e9468  lea     rax, [rbp+0A0h+var_D0]
0x1c00e946c  mov     [rbp+0A0h+var_78], rax
0x1c00e9470  mov     eax, [r8+44h]
0x1c00e9474  and     eax, 8
0x1c00e9477  mov     [rbp+0A0h+var_D0], rdx
0x1c00e947b  mov     [rsp+1A0h+var_150], eax
0x1c00e947f  mov     eax, [r8+68h]
0x1c00e9483  mov     [rbp+0A0h+var_B8], r11
0x1c00e9487  mov     [rbp+0A0h+var_B0], r11
0x1c00e948b  mov     [rbp+0A0h+var_98], r11d
0x1c00e948f  mov     [rbp+0A0h+var_94], r11w
0x1c00e9494  mov     [rbp+0A0h+var_92], r11b
0x1c00e9498  mov     [rbp+0A0h+var_80], r8
0x1c00e949c  mov     [rbp+0A0h+var_60], r11
0x1c00e94a0  mov     [rbp+0A0h+var_50], r11d
0x1c00e94a4  mov     [rbp+0A0h+var_58], r11
0x1c00e94a8  mov     [rsp+1A0h+var_128], rdx
0x1c00e94ad  mov     [rsp+1A0h+var_158], rsi
0x1c00e94b2  mov     [rsp+1A0h+var_140], r11
0x1c00e94b7  mov     [rsp+1A0h+var_148], rcx
0x1c00e94bc  mov     [rsp+1A0h+var_160], r11b
0x1c00e94c1  movdqu  [rbp+0A0h+var_C8], xmm0
0x1c00e94c6  movdqu  [rbp+0A0h+var_A8], xmm0
0x1c00e94cb  movdqu  [rbp+0A0h+var_90], xmm0
0x1c00e94d0  movdqu  [rbp+0A0h+var_70], xmm0
0x1c00e94d5  movsxd  r13, dword ptr [r14+3Ch]
0x1c00e94d9  xorps   xmm0, xmm0
0x1c00e94dc  movups  [rbp+0A0h+var_118], xmm0
0x1c00e94e0  cmp     rcx, 20h ; ' '
0x1c00e94e4  ja      short loc_1C00E94EE
0x1c00e94e6  lea     ecx, [r11+4]
0x1c00e94ea  test    al, 2
0x1c00e94ec  jnz     short loc_1C00E94F1
0x1c00e94ee  mov     ecx, r11d
0x1c00e94f1  and     eax, 0FFFFFFFBh
0x1c00e94f4  or      eax, ecx
0x1c00e94f6  mov     [r8+68h], eax
0x1c00e94fa  movups  xmm0, cs:?MsZeroRange@@3U_RANGE@@B; _RANGE const MsZeroRange
0x1c00e9501  movdqu  [rbp+0A0h+var_90], xmm0
0x1c00e9506  movdqu  [rbp+0A0h+var_C8], xmm0
0x1c00e950b  mov     r8, [rbp+0A0h+var_80]
0x1c00e950f  lea     r9, [rbp+0A0h+var_C8]
0x1c00e9513  mov     rdx, [rbp+0A0h+var_D0]
0x1c00e9517  xorps   xmm0, xmm0
0x1c00e951a  movups  xmmword ptr [rdi+50h], xmm0
0x1c00e951e  xor     eax, eax
0x1c00e9520  mov     [rbp+0A0h+var_60], r11
0x1c00e9524  mov     [rdi+60h], rax
0x1c00e9528  mov     rcx, r15; struct CmsTransactionContext *
0x1c00e952b  movups  xmm0, cs:?MsZeroRange@@3U_RANGE@@B; _RANGE const MsZeroRange
0x1c00e9532  mov     [rbp+0A0h+var_50], r11d
0x1c00e9536  mov     [rbp+0A0h+var_58], r11
0x1c00e953a  movdqu  [rbp+0A0h+var_70], xmm0
0x1c00e953f  call    ?NextSpace@?$ThinProvisioningStrategy@VRangeArrayStrategy@MsAllocator@@@MsAllocator@@CAJPEAVCmsTransactionContext@@PEAUState@12@PEAUSmsAllocationContext@@AEAUContext@12@@Z; MsAllocator::ThinProvisioningStrategy<MsAllocator::RangeArrayStrategy>::NextSpace(CmsTransactionContext *,MsAllocator::ThinProvisioningStrategy<MsAllocator::RangeArrayStrategy>::State *,SmsAllocationContext *,MsAllocator::ThinProvisioningStrategy<MsAllocator::RangeArrayStrategy>::Context &)
0x1c00e9544  mov     ebx, eax
0x1c00e9546  cmp     eax, 0C000022Dh
0x1c00e954b  jz      loc_1C00E99F6
0x1c00e9551  cmp     eax, 0C0000273h
0x1c00e9556  jnz     short loc_1C00E9574
0x1c00e9558  test    dword ptr [rdi+68h], 200h
0x1c00e955f  jz      short loc_1C00E956F
0x1c00e9561  xor     r11d, r11d
0x1c00e9564  cmp     [rsp+1A0h+var_160], r11b
0x1c00e9569  jz      loc_1C00E99FE
0x1c00e956f  mov     ebx, 0C000007Fh
0x1c00e9574  test    ebx, ebx
0x1c00e9576  js      loc_1C00E9AC8
0x1c00e957c  jmp     short loc_1C00E9583
0x1c00e957e  mov     rsi, [rsp+1A0h+var_158]
0x1c00e9583  test    byte ptr [rbp+0A0h+var_50], 4
0x1c00e9587  jz      short loc_1C00E95A7
0x1c00e9589  mov     rcx, [rbp+0A0h+var_60]
0x1c00e958d  xor     edx, edx
0x1c00e958f  lock dec dword ptr [rcx+28h]
0x1c00e9593  add     rcx, 20h ; ' '
0x1c00e9597  call    cs:__imp_ExReleasePushLockEx
0x1c00e959e  nop     dword ptr [rax+rax+00h]
0x1c00e95a3  and     byte ptr [rbp+0A0h+var_50], 0FBh
0x1c00e95a7  mov     rdx, [rbp+0A0h+var_78]
0x1c00e95ab  lea     rax, [rbp+0A0h+var_70]
0x1c00e95af  mov     rcx, r15; struct CmsTransactionContext *
0x1c00e95b2  mov     [rsp+1A0h+var_180], rax; struct MsAllocator::AllocationCandidate *
0x1c00e95b7  mov     r8, [rdx+50h]
0x1c00e95bb  lea     r9, [rdx+8]
0x1c00e95bf  mov     rdx, [rdx]
0x1c00e95c2  call    ?NextCandidate@?$ThinProvisioningStrategy@VRangeArrayStrategy@MsAllocator@@@MsAllocator@@CAJPEAVCmsTransactionContext@@PEAUState@12@PEAUSmsAllocationContext@@AEAUContext@12@AEAUAllocationCandidate@2@@Z; MsAllocator::ThinProvisioningStrategy<MsAllocator::RangeArrayStrategy>::NextCandidate(CmsTransactionContext *,MsAllocator::ThinProvisioningStrategy<MsAllocator::RangeArrayStrategy>::State *,SmsAllocationContext *,MsAllocator::ThinProvisioningStrategy<MsAllocator::RangeArrayStrategy>::Context &,MsAllocator::AllocationCandidate &)
0x1c00e95c7  xor     r11d, r11d
0x1c00e95ca  mov     ebx, eax
0x1c00e95cc  test    eax, eax
0x1c00e95ce  js      loc_1C00E9986
0x1c00e95d4  cmp     [rsp+1A0h+var_150], r11d
0x1c00e95d9  jz      short loc_1C00E9638
0x1c00e95db  mov     r8, qword ptr [rbp+0A0h+var_70]
0x1c00e95df  lea     eax, [r13-1]
0x1c00e95e3  movups  xmm0, cs:?MsZeroRange@@3U_RANGE@@B; _RANGE const MsZeroRange
0x1c00e95ea  movsxd  rdx, eax
0x1c00e95ed  mov     eax, r13d
0x1c00e95f0  neg     eax
0x1c00e95f2  add     rdx, r8
0x1c00e95f5  movsxd  rcx, eax
0x1c00e95f8  and     rdx, rcx
0x1c00e95fb  mov     rcx, qword ptr [rbp+0A0h+var_70+8]
0x1c00e95ff  movdqu  [rsp+1A0h+var_138], xmm0
0x1c00e9605  mov     qword ptr [rsp+1A0h+var_138], rdx
0x1c00e960a  lea     rax, [rcx+r8]
0x1c00e960e  cmp     rax, rdx
0x1c00e9611  jbe     short loc_1C00E9620
0x1c00e9613  sub     rcx, rdx
0x1c00e9616  add     rcx, r8
0x1c00e9619  mov     qword ptr [rsp+1A0h+var_138+8], rcx
0x1c00e961e  jmp     short loc_1C00E9625
0x1c00e9620  mov     rcx, qword ptr [rsp+1A0h+var_138+8]
0x1c00e9625  cmp     rcx, r13
0x1c00e9628  jb      loc_1C00E9583
0x1c00e962e  movups  xmm0, [rsp+1A0h+var_138]
0x1c00e9633  movdqu  [rbp+0A0h+var_70], xmm0
0x1c00e9638  mov     rcx, [rbp+0A0h+var_60]; this
0x1c00e963c  mov     r8d, [rdi+44h]
0x1c00e9640  mov     r9d, r8d
0x1c00e9643  and     r9d, 40h
0x1c00e9647  and     r8d, 8
0x1c00e964b  movzx   ebx, word ptr [rcx+18h]
0x1c00e964f  call    ?GetTotalFree@SmsAllocationRegionEx@@QEBA?B_KXZ; SmsAllocationRegionEx::GetTotalFree(void)
0x1c00e9654  cmp     rax, qword ptr [rbp+0A0h+var_70+8]
0x1c00e9658  cmovnb  rax, qword ptr [rbp+0A0h+var_70+8]
0x1c00e965d  test    rax, rax
0x1c00e9660  jz      loc_1C00E957E
0x1c00e9666  cmp     rax, [rsp+1A0h+var_148]
0x1c00e966b  jnb     short loc_1C00E9676
0x1c00e966d  test    r8d, r8d
0x1c00e9670  jnz     loc_1C00E957E
0x1c00e9676  test    bl, 64h
0x1c00e9679  jnz     loc_1C00E957E
0x1c00e967f  test    r9d, r9d
0x1c00e9682  jnz     short loc_1C00E968D
0x1c00e9684  test    bl, 8
0x1c00e9687  jnz     loc_1C00E957E
0x1c00e968d  test    byte ptr [rbp+0A0h+var_50], 2
0x1c00e9691  jnz     short loc_1C00E969D
0x1c00e9693  mov     r9b, r11b
0x1c00e9696  cmp     [rsp+1A0h+var_160], r11b
0x1c00e969b  jz      short loc_1C00E96A0
0x1c00e969d  mov     r9b, 1
0x1c00e96a0  and     bx, 2
0x1c00e96a4  lock or [rsp+1A0h+var_1A0], r11d
0x1c00e96a9  test    byte ptr [rbp+0A0h+var_50], 1
0x1c00e96ad  mov     edx, [rdi+68h]
0x1c00e96b0  jnz     short loc_1C00E96C1
0x1c00e96b2  test    dl, 4
0x1c00e96b5  jnz     short loc_1C00E96BC
0x1c00e96b7  test    bx, bx
0x1c00e96ba  jz      short loc_1C00E96C1
0x1c00e96bc  mov     r8b, r11b
0x1c00e96bf  jmp     short loc_1C00E96C4
0x1c00e96c1  mov     r8b, 1
0x1c00e96c4  test    bx, bx
0x1c00e96c7  jnz     short loc_1C00E96EA
0x1c00e96c9  mov     rax, [rbp+0A0h+var_60]
0x1c00e96cd  movsxd  rcx, dword ptr [r14+3Ch]
0x1c00e96d1  cmp     [rax+8], rcx
0x1c00e96d5  jnz     short loc_1C00E96EA
0x1c00e96d7  test    r9b, r9b
0x1c00e96da  jnz     short loc_1C00E96EA
0x1c00e96dc  test    r8b, r8b
0x1c00e96df  jnz     short loc_1C00E96EA
0x1c00e96e1  mov     sil, 1
0x1c00e96e4  bt      edx, 9
0x1c00e96e8  jnb     short loc_1C00E96ED
0x1c00e96ea  mov     sil, r11b
0x1c00e96ed  mov     [rsp+1A0h+var_170], sil; bool
0x1c00e96f2  mov     rdx, r15; struct CmsTransactionContext *
0x1c00e96f5  mov     byte ptr [rsp+1A0h+var_178], r8b; bool
0x1c00e96fa  mov     rcx, r14; this
0x1c00e96fd  mov     byte ptr [rsp+1A0h+var_180], r9b; bool
0x1c00e9702  mov     r8, rdi; struct SmsAllocationContext *
0x1c00e9705  lea     r9, [rbp+0A0h+var_70]; struct MsAllocator::AllocationCandidate *
0x1c00e9709  call    ?TryLockCandidateForAllocation@CmsAllocator@@AEAA_NPEAVCmsTransactionContext@@PEAUSmsAllocationContext@@AEBUAllocationCandidate@MsAllocator@@_N33@Z; CmsAllocator::TryLockCandidateForAllocation(CmsTransactionContext *,SmsAllocationContext *,MsAllocator::AllocationCandidate const &,bool,bool,bool)
0x1c00e970e  test    al, al
0x1c00e9710  jz      loc_1C00E97A0
0x1c00e9716  mov     rcx, [rbp+0A0h+var_60]; this
0x1c00e971a  mov     r8d, [rdi+44h]
0x1c00e971e  mov     r10d, r8d
0x1c00e9721  or      byte ptr [rbp+0A0h+var_50], 4
0x1c00e9725  and     r10d, 40h
0x1c00e9729  and     r8d, 8
0x1c00e972d  movzx   r9d, word ptr [rcx+18h]
0x1c00e9732  call    ?GetTotalFree@SmsAllocationRegionEx@@QEBA?B_KXZ; SmsAllocationRegionEx::GetTotalFree(void)
0x1c00e9737  mov     rcx, qword ptr [rbp+0A0h+var_70+8]
0x1c00e973b  cmp     rax, rcx
0x1c00e973e  cmovnb  rax, rcx
0x1c00e9742  test    rax, rax
0x1c00e9745  jz      loc_1C00E957E
0x1c00e974b  cmp     rax, [rsp+1A0h+var_148]
0x1c00e9750  jnb     short loc_1C00E975B
0x1c00e9752  test    r8d, r8d
0x1c00e9755  jnz     loc_1C00E957E
0x1c00e975b  test    r9b, 64h
0x1c00e975f  jnz     loc_1C00E957E
0x1c00e9765  test    r10d, r10d
0x1c00e9768  jnz     short loc_1C00E9774
0x1c00e976a  test    r9b, 8
0x1c00e976e  jnz     loc_1C00E957E
0x1c00e9774  test    bx, bx
0x1c00e9777  jz      loc_1C00E980F
0x1c00e977d  lea     r9, [rbp+0A0h+var_70]; struct MsAllocator::AllocationCandidate *
0x1c00e9781  mov     r8, rdi; struct SmsAllocationContext *
0x1c00e9784  mov     rdx, r15; struct CmsTransactionContext *
0x1c00e9787  mov     rcx, r14; this
0x1c00e978a  call    ?PrepareRangeOnlyCandidateForAllocation@CmsAllocator@@AEAAJPEAVCmsTransactionContext@@PEAUSmsAllocationContext@@AEAUAllocationCandidate@MsAllocator@@@Z; CmsAllocator::PrepareRangeOnlyCandidateForAllocation(CmsTransactionContext *,SmsAllocationContext *,MsAllocator::AllocationCandidate &)
0x1c00e978f  mov     ebx, eax
0x1c00e9791  test    eax, eax
0x1c00e9793  jns     short loc_1C00E97B5
0x1c00e9795  cmp     eax, 0C000022Dh
0x1c00e979a  jnz     loc_1C00E9AC8
0x1c00e97a0  cmp     qword ptr [rbp+0A0h+var_70+8], r13
0x1c00e97a4  mov     rax, r13
0x1c00e97a7  cmovb   rax, qword ptr [rbp+0A0h+var_70+8]
0x1c00e97ac  mov     qword ptr [rbp+0A0h+var_70+8], rax
0x1c00e97b0  jmp     loc_1C00E957E
0x1c00e97b5  mov     rcx, [rbp+0A0h+var_60]; this
0x1c00e97b9  mov     r8d, [rdi+44h]
0x1c00e97bd  mov     r10d, r8d
0x1c00e97c0  and     r10d, 40h
0x1c00e97c4  and     r8d, 8
0x1c00e97c8  movzx   r9d, word ptr [rcx+18h]
0x1c00e97cd  call    ?GetTotalFree@SmsAllocationRegionEx@@QEBA?B_KXZ; SmsAllocationRegionEx::GetTotalFree(void)
0x1c00e97d2  mov     rcx, qword ptr [rbp+0A0h+var_70+8]
0x1c00e97d6  cmp     rax, rcx
0x1c00e97d9  cmovnb  rax, rcx
0x1c00e97dd  test    rax, rax
0x1c00e97e0  jz      loc_1C00E957E
0x1c00e97e6  cmp     rax, [rsp+1A0h+var_148]
0x1c00e97eb  jnb     short loc_1C00E97F6
0x1c00e97ed  test    r8d, r8d
0x1c00e97f0  jnz     loc_1C00E957E
0x1c00e97f6  test    r9b, 64h
0x1c00e97fa  jnz     loc_1C00E957E
0x1c00e9800  test    r10d, r10d
0x1c00e9803  jnz     short loc_1C00E980F
0x1c00e9805  test    r9b, 8
0x1c00e9809  jnz     loc_1C00E957E
0x1c00e980f  mov     eax, [rdi+68h]
0x1c00e9812  test    al, 1
0x1c00e9814  jz      short loc_1C00E982D
0x1c00e9816  lea     r8, [rdi+28h]; struct SmsPushLockContext *
0x1c00e981a  mov     rdx, r15; struct CmsTransactionContext *
0x1c00e981d  mov     rcx, r14; this
0x1c00e9820  call    ?UnlockCache@CmsAllocator@@AEAAXPEAVCmsTransactionContext@@PEAUSmsPushLockContext@@@Z; CmsAllocator::UnlockCache(CmsTransactionContext *,SmsPushLockContext *)
0x1c00e9825  and     dword ptr [rdi+68h], 0FFFFFFFEh
0x1c00e9829  mov     rcx, qword ptr [rbp+0A0h+var_70+8]
0x1c00e982d  cmp     byte ptr [r14+54h], 2
0x1c00e9832  mov     rax, [rbp+0A0h+var_60]
0x1c00e9836  movups  xmm0, xmmword ptr [rax]
0x1c00e9839  movups  xmm1, xmmword ptr [rax+10h]
0x1c00e983d  movups  [rbp+0A0h+var_108], xmm0
0x1c00e9841  movups  xmm0, xmmword ptr [rax+20h]
0x1c00e9845  movups  [rbp+0A0h+var_F8], xmm1
0x1c00e9849  movsd   xmm1, qword ptr [rax+30h]
0x1c00e984e  movups  [rbp+0A0h+var_E8], xmm0
0x1c00e9852  movsd   [rbp+0A0h+var_D8], xmm1
0x1c00e9857  jz      short loc_1C00E989A
0x1c00e9859  lea     rax, [rsp+1A0h+var_140]
0x1c00e985e  mov     rdx, r15; struct CmsTransactionContext *
0x1c00e9861  mov     [rsp+1A0h+var_178], rax; struct SmsContainer **
0x1c00e9866  lea     r9, [rbp+0A0h+var_70]; struct MsAllocator::AllocationCandidate *
0x1c00e986a  lea     rax, [rbp+0A0h+var_118]
0x1c00e986e  mov     rcx, r14; this
0x1c00e9871  mov     [rsp+1A0h+var_180], rax; struct _RANGE *
0x1c00e9876  call    ?PopulateContainersForCandidate@CmsAllocator@@AEAAJPEAVCmsTransactionContext@@PEAUSmsAllocationContext@@AEBUAllocationCandidate@MsAllocator@@PEAU_RANGE@@PEAPEAUSmsContainer@@@Z; CmsAllocator::PopulateContainersForCandidate(CmsTransactionContext *,SmsAllocationContext *,MsAllocator::AllocationCandidate const &,_RANGE *,SmsContainer * *)
0x1c00e987b  xor     r11d, r11d
0x1c00e987e  mov     ebx, eax
0x1c00e9880  test    eax, eax
0x1c00e9882  jns     short loc_1C00E9894
0x1c00e9884  cmp     eax, 0C000022Dh
0x1c00e9889  jnz     loc_1C00E9AC8
0x1c00e988f  jmp     loc_1C00E957E
0x1c00e9894  mov     rcx, qword ptr [rbp+0A0h+var_70+8]
  ... truncated ...
```
