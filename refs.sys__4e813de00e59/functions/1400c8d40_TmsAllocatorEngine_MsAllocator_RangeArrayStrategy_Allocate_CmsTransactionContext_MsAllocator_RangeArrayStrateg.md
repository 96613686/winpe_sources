# TmsAllocatorEngine<MsAllocator::RangeArrayStrategy>::Allocate(CmsTransactionContext *,MsAllocator::RangeArrayStrategy::State *,SmsAllocationContext *,_RANGE const *,_RANGE *,_RANGE *)

- ea: `0x1400c8d40`
- end: `0x1400c9612`
- name: `?Allocate@?$TmsAllocatorEngine@VRangeArrayStrategy@MsAllocator@@@@SAJPEAVCmsTransactionContext@@PEAUState@RangeArrayStrategy@MsAllocator@@PEAUSmsAllocationContext@@PEBU_RANGE@@PEAU7@4@Z`
- size: `2258`
- prototype: `__int64 __usercall@<rax>(struct CmsTransactionContext *@<rcx>, struct _RANGE *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14006e060`

## callees

- `0x140034360`
- `0x140035a7c`
- `0x14009df70`
- `0x1400a7828`
- `0x1400c8d40`
- `0x1400ca030`
- `0x1400ca6a0`
- `0x1400cae60`
- `0x14012c7f8`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x1400c94fe`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400c95dc`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400c9400`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400c9400`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400c91aa`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400c931f`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400c959e`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400c91aa`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400c931f`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400c959e`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1400c91bf`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1400c9373`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1400c95b3`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1400c91bf`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1400c9373`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1400c95b3`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400c8e9c`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400c9557`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400c8e9c`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400c9557`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c944d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c9511`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c95ef`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c944d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c9511`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c95ef`

## pseudocode

```c
__int64 __fastcall TmsAllocatorEngine<MsAllocator::RangeArrayStrategy>::Allocate(
        struct CmsTransactionContext *a1,
        struct MsAllocator::RangeArrayStrategy::State *a2,
        __int64 a3,
        __int64 a4,
        struct _RANGE *a5,
        struct _RANGE *a6)
{
  CmsAllocator *v6; // rsi
  unsigned __int64 v7; // r15
  __int64 v8; // r14
  struct CmsTransactionContext *v9; // r12
  __int64 v10; // r13
  int v11; // eax
  int v12; // edi
  int v13; // eax
  int v14; // ecx
  int Space; // ebx
  __int64 v16; // r8
  struct _IO_REMOVE_LOCK *v17; // rcx
  int v18; // eax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rdx
  __int128 *v21; // r8
  __int16 v22; // dx
  unsigned __int64 v23; // rax
  int v24; // ecx
  int v25; // eax
  bool v26; // r9
  __int16 v27; // bx
  bool v28; // dl
  bool v29; // di
  __int128 *v30; // r8
  __int16 v31; // dx
  unsigned __int64 v32; // rcx
  int v33; // eax
  int v34; // eax
  __int64 v35; // rcx
  __int16 v36; // dx
  unsigned __int64 v37; // rcx
  int v38; // eax
  char v39; // cl
  __int64 v40; // rcx
  bool v41; // zf
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  int v46; // ecx
  struct _RANGE *v47; // rdi
  unsigned int v48; // eax
  int v49; // eax
  __int64 v50; // rcx
  struct SmsAllocationContext *v51; // r15
  struct MsAllocator::RangeArrayStrategy::State *v52; // rsi
  __int64 v53; // r13
  __int64 v54; // rdi
  unsigned __int64 v55; // r14
  unsigned __int64 *v56; // rdx
  char v57; // al
  __int128 *v58; // rcx
  struct _IO_REMOVE_LOCK *v59; // rcx
  __int64 v60; // rcx
  __int128 *v61; // rcx
  signed __int32 v63[8]; // [rsp+0h] [rbp-100h] BYREF
  struct _RANGE *v64; // [rsp+20h] [rbp-E0h]
  struct SmsContainer *v65; // [rsp+40h] [rbp-C0h] BYREF
  struct MsAllocator::RangeArrayStrategy::State *v66; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v67; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v68; // [rsp+60h] [rbp-A0h]
  __int64 v69; // [rsp+68h] [rbp-98h]
  __int128 v70; // [rsp+70h] [rbp-90h]
  __int64 v71; // [rsp+80h] [rbp-80h]
  int v72; // [rsp+88h] [rbp-78h]
  __int16 v73; // [rsp+8Ch] [rbp-74h]
  char v74; // [rsp+8Eh] [rbp-72h]
  struct SmsAllocationContext *v75; // [rsp+90h] [rbp-70h]
  struct MsAllocator::RangeArrayStrategy::State **v76; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int128 v77; // [rsp+A0h] [rbp-60h] BYREF
  __int128 *v78; // [rsp+B0h] [rbp-50h]
  __int64 v79; // [rsp+B8h] [rbp-48h]
  int v80; // [rsp+C0h] [rbp-40h]
  int v81; // [rsp+D0h] [rbp-30h]
  CmsAllocator *v82; // [rsp+D8h] [rbp-28h]
  __int64 v83; // [rsp+E0h] [rbp-20h]
  _QWORD v84[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v85; // [rsp+F8h] [rbp-8h]
  __int128 v86; // [rsp+108h] [rbp+8h]
  __int128 v87; // [rsp+118h] [rbp+18h]
  __int128 v88; // [rsp+128h] [rbp+28h]
  __int128 v89; // [rsp+138h] [rbp+38h]
  __int64 v90; // [rsp+148h] [rbp+48h]
  char v92; // [rsp+1A8h] [rbp+A8h]
  int v94; // [rsp+1B8h] [rbp+B8h]

  v6 = *(CmsAllocator **)(a3 + 16);
  v7 = *(_QWORD *)(a4 + 8);
  v8 = a3;
  v82 = v6;
  v9 = a1;
  v10 = *((_QWORD *)v6 + 57);
  v76 = &v66;
  v11 = *(_DWORD *)(a3 + 68) & 8;
  v66 = a2;
  v70 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = (struct SmsAllocationContext *)a3;
  v77 = 0;
  v78 = 0;
  v80 = 0;
  v79 = 0;
  v65 = 0;
  v12 = *((_DWORD *)v6 + 117);
  v81 = v11;
  v13 = *(_DWORD *)(a3 + 84);
  v83 = v10;
  v84[0] = 0;
  v84[1] = 0;
  v94 = v12;
  v92 = 0;
  if ( v7 > 0x20 || (v14 = 4, (v13 & 2) == 0) )
    v14 = 0;
  *(_DWORD *)(a3 + 84) = v14 | v13 & 0xFFFFFFFB;
  while ( 1 )
  {
    while ( 1 )
    {
      do
      {
LABEL_5:
        v67 = 0;
        v68 = 0;
        v78 = 0;
        v80 = 0;
        v79 = 0;
        v77 = 0;
        Space = MsAllocator::RangeArrayStrategy::NextSpace(
                  v9,
                  v66,
                  v75,
                  (struct MsAllocator::RangeArrayStrategy::Context *)&v67);
      }
      while ( Space == -1073741267 );
LABEL_6:
      if ( Space == -1073741197 )
        break;
      if ( Space < 0 )
        goto LABEL_146;
      do
      {
        while ( 1 )
        {
          if ( v65 )
          {
            v17 = (struct _IO_REMOVE_LOCK *)(*(_QWORD *)(v10 + 3272) + 480LL);
            _InterlockedDecrement((volatile signed __int32 *)v65 + 23);
            IoReleaseRemoveLockEx(v17, 0, 0x20u);
            if ( v9 )
              --*((_DWORD *)v9 + 88);
            v65 = 0;
          }
          v18 = MsAllocator::CandidateIterator<MsAllocator::RangeArrayStrategy>::Advance(&v76, v9);
          Space = v18;
          if ( v18 < 0 )
            break;
          ++*(_DWORD *)(v8 + 80);
          if ( v81 )
          {
            v19 = 0;
            v20 = -(__int64)v12 & (v12 + v77 - 1);
            if ( (_QWORD)v77 + *((_QWORD *)&v77 + 1) > v20 )
              v19 = *((_QWORD *)&v77 + 1) + v77 - v20;
            if ( v19 < v12 )
              goto LABEL_9;
            v77 = __PAIR128__(v19, v20);
          }
          else
          {
            v19 = *((_QWORD *)&v77 + 1);
          }
          v21 = v78;
          v22 = *((_WORD *)v78 + 18);
          v23 = *((int *)v78 + 4);
          if ( (v22 & 2) != 0 && *((_DWORD *)v78 + 4) )
            v23 = *((_QWORD *)v78 + 1);
          if ( v23 >= v19 )
            v23 = v19;
          if ( !v23 )
            goto LABEL_9;
          v24 = *(_DWORD *)(v8 + 68);
          if ( v23 < v7 && (v24 & 8) != 0 )
            goto LABEL_9;
          if ( (v22 & 0x64) != 0 || (v24 & 0x40) == 0 && (v22 & 8) != 0 )
            goto LABEL_9;
          if ( *((_BYTE *)v6 + 492) == 2 )
            goto LABEL_37;
          v25 = CmsAllocator::PopulateContainersForCandidate(
                  v6,
                  v9,
                  (struct SmsAllocationContext *)v8,
                  (const struct MsAllocator::AllocationCandidate *)&v77,
                  (struct _RANGE *)v84,
                  &v65);
          Space = v25;
          if ( v25 >= 0 )
          {
            v21 = v78;
LABEL_37:
            v26 = (v80 & 2) != 0 || v92;
            v27 = *((_WORD *)v21 + 18) & 2;
            _InterlockedOr(v63, 0);
            v28 = (v80 & 1) != 0 || (*(_DWORD *)(v8 + 84) & 4) == 0 && !v27;
            v29 = !v27
               && *((_QWORD *)v78 + 1) == *((_DWORD *)v6 + 117)
               && !v26
               && !v28
               && (*(_DWORD *)(v8 + 84) & 0x200) == 0;
            if ( !CmsAllocator::TryLockCandidateForAllocation(
                    v6,
                    v9,
                    (struct SmsAllocationContext *)v8,
                    (const struct MsAllocator::AllocationCandidate *)&v77,
                    v26,
                    v28,
                    v29) )
              goto LABEL_68;
            LOBYTE(v80) = v80 | 4;
            v30 = v78;
            v31 = *((_WORD *)v78 + 18);
            v32 = *((int *)v78 + 4);
            if ( (v31 & 2) != 0 && *((_DWORD *)v78 + 4) )
              v32 = *((_QWORD *)v78 + 1);
            if ( v32 >= *((_QWORD *)&v77 + 1) )
              v32 = *((_QWORD *)&v77 + 1);
            if ( !v32
              || (v33 = *(_DWORD *)(v8 + 68), v32 < v7) && (v33 & 8) != 0
              || (v31 & 0x64) != 0
              || (v33 & 0x40) == 0 && (v31 & 8) != 0 )
            {
LABEL_9:
              v12 = v94;
            }
            else
            {
              if ( !v27 )
                goto LABEL_82;
              v34 = CmsAllocator::PrepareRangeOnlyCandidateForAllocation(
                      v6,
                      v9,
                      (struct SmsAllocationContext *)v8,
                      (struct MsAllocator::AllocationCandidate *)&v77);
              Space = v34;
              if ( v34 >= 0 )
              {
                v30 = v78;
                v36 = *((_WORD *)v78 + 18);
                v37 = *((int *)v78 + 4);
                if ( (v36 & 2) != 0 && *((_DWORD *)v78 + 4) )
                  v37 = *((_QWORD *)v78 + 1);
                if ( v37 >= *((_QWORD *)&v77 + 1) )
                  v37 = *((_QWORD *)&v77 + 1);
                if ( !v37 )
                  goto LABEL_9;
                v38 = *(_DWORD *)(v8 + 68);
                if ( v37 < v7 && (v38 & 8) != 0 )
                  goto LABEL_9;
                if ( (v36 & 0x64) != 0 || (v38 & 0x40) == 0 && (v36 & 8) != 0 )
                  goto LABEL_9;
LABEL_82:
                v39 = *((_BYTE *)v6 + 492);
                if ( v39 != 3
                  || (*(_DWORD *)(v8 + 68) & 0x10) != 0
                  || *(_QWORD *)v30 == *(_QWORD *)((char *)v65
                                                 + (unsigned int)(16 * *(_DWORD *)(*(_QWORD *)(v10 + 3272) + 388LL))
                                                 + 672) )
                {
                  if ( (*(_DWORD *)(v8 + 84) & 1) != 0 )
                  {
                    if ( ((unsigned __int8)(1 << v39) & *((_BYTE *)v9 + 220)) == 0 )
                    {
                      v40 = *(_QWORD *)(v8 + 40);
                      if ( v40 )
                        ExReleaseAutoExpandPushLockShared(v40, 2, v30);
                      else
                        ExReleaseAutoExpandPushLockExclusive((char *)v6 + 440, 2);
                      v30 = v78;
                    }
                    *(_DWORD *)(v8 + 84) &= ~1u;
                  }
                  v41 = *((_BYTE *)v6 + 492) == 3;
                  v42 = v30[1];
                  v85 = *v30;
                  v43 = v30[2];
                  v86 = v42;
                  v44 = v30[3];
                  v87 = v43;
                  v45 = v30[4];
                  v88 = v44;
                  *(_QWORD *)&v44 = *((_QWORD *)v30 + 10);
                  v89 = v45;
                  v90 = v44;
                  if ( (v41 || !byte_140269025)
                    && (*(_DWORD *)(v8 + 84) & 4) != 0
                    && v29
                    && *((_QWORD *)&v77 + 1) == *((_QWORD *)v30 + 1)
                    && ((*(_DWORD *)(v8 + 68) & 0x400) != 0 || byte_140209844[12 * *(int *)(v10 + 3900)]) )
                  {
                    v46 = 128;
                  }
                  else
                  {
                    v46 = 0;
                  }
                  v47 = a5;
                  v48 = v46 | *(_DWORD *)(v8 + 84) & 0xFFFFFF7F;
                  v64 = a5;
                  *(_DWORD *)(v8 + 84) = v48;
                  v49 = CmsAllocator::AllocateFromCandidate(
                          v6,
                          v9,
                          (struct SmsAllocationContext *)v8,
                          (struct MsAllocator::AllocationCandidate *)&v77,
                          v64);
                  Space = v49;
                  if ( v49 >= 0 )
                  {
                    v51 = v75;
                    v52 = v66;
                    v53 = *((_QWORD *)v9 + 1);
                    if ( (*((_DWORD *)v75 + 21) & 0x100) != 0 )
                    {
                      v54 = HIDWORD(v69);
                      v55 = *(_QWORD *)a5 + *((_QWORD *)a5 + 1);
                      ExAcquirePushLockSharedEx((char *)v66 + 64, 4);
                      v56 = (unsigned __int64 *)(*((_QWORD *)v52 + 2) + 56 * v54);
                      if ( v55 >= *v56 && v55 < v56[1] + *v56 )
                      {
                        if ( (*((_DWORD *)v51 + 17) & 0x2000) != 0 )
                        {
                          v56[4] = v55;
                        }
                        else if ( !(_BYTE)v73 && (*((_DWORD *)v51 + 21) & 0x40) == 0 )
                        {
                          v56[2] = v55;
                        }
                      }
                      ExReleasePushLockEx((char *)v52 + 64, 0);
                      v8 = a3;
                      v9 = a1;
                      v47 = a5;
                    }
                    if ( *((_DWORD *)v52 + 11)
                      && *(_QWORD *)(v53 + 2064) - *((_QWORD *)v52 + 7) > (unsigned __int64)*((unsigned int *)v52 + 12) )
                    {
                      *((_DWORD *)v52 + 11) = 0;
                    }
                    v6 = v82;
                    *(_OWORD *)a6 = *(_OWORD *)v47;
                    v57 = *((_BYTE *)v6 + 492);
                    if ( v57 != 2 )
                    {
                      if ( v57 == 3 )
                        CmsAllocator::UpdateVolumeContainerForCompletedAllocation(
                          v6,
                          v9,
                          (struct MsAllocator::AllocationCandidate *)&v77,
                          (struct SmsAllocationContext *)v8,
                          v65,
                          a6);
                      *(_QWORD *)v47 = v84[0] + (*(int *)v47 & (unsigned __int64)(v94 - 1));
                    }
                    v58 = v78;
                    if ( _InterlockedDecrement((volatile signed __int32 *)v78 + 12) < 0 && (_BYTE)KdDebuggerEnabled )
                      __debugbreak();
                    ExReleasePushLockEx((char *)v58 + 40, 0);
                    LOBYTE(v80) = v80 & 0xFB;
                    v10 = v83;
                    goto LABEL_146;
                  }
                  if ( v49 != -1073741267 && v49 != -1073741197 && v49 != -1073741431 )
                    goto LABEL_146;
                }
                goto LABEL_9;
              }
              if ( v34 != -1073741267 )
                goto LABEL_146;
LABEL_68:
              v35 = *((_QWORD *)&v77 + 1);
              v12 = v94;
              if ( *((_QWORD *)&v77 + 1) >= (unsigned __int64)v94 )
                v35 = v94;
              *((_QWORD *)&v77 + 1) = v35;
            }
          }
          else if ( v25 != -1073741267 )
          {
            goto LABEL_146;
          }
        }
        if ( v18 == -1073741197 || v18 == -1073741172 )
        {
          v78 = 0;
          v77 = 0;
          v80 = 0;
          v79 = 0;
          Space = MsAllocator::RangeArrayStrategy::NextSpace(
                    v9,
                    v66,
                    v75,
                    (struct MsAllocator::RangeArrayStrategy::Context *)&v67);
          if ( Space != -1073741267 )
            goto LABEL_6;
          goto LABEL_5;
        }
      }
      while ( v18 == -1073741198 );
      if ( v18 == -1073741400 && (*(_DWORD *)(v8 + 68) & 0x800) == 0 )
      {
        if ( (*(_DWORD *)(v8 + 84) & 1) != 0 )
        {
          if ( ((unsigned __int8)(1 << *((_BYTE *)v6 + 492)) & *((_BYTE *)v9 + 220)) == 0 )
          {
            v50 = *(_QWORD *)(v8 + 40);
            if ( v50 )
              ExReleaseAutoExpandPushLockShared(v50, 2, v16);
            else
              ExReleaseAutoExpandPushLockExclusive((char *)v6 + 440, 2);
          }
          *(_DWORD *)(v8 + 84) &= ~1u;
        }
        Space = CmsVolume::TriageAllocator((CmsVolume *)v10, v9);
        if ( Space >= 0 )
          continue;
      }
      goto LABEL_146;
    }
    if ( (*(_DWORD *)(v8 + 84) & 0x200) == 0 || v92 )
      break;
    v92 = 1;
  }
  Space = -1073741697;
LABEL_146:
  if ( v65 )
  {
    v59 = (struct _IO_REMOVE_LOCK *)(*(_QWORD *)(v10 + 3272) + 480LL);
    _InterlockedDecrement((volatile signed __int32 *)v65 + 23);
    IoReleaseRemoveLockEx(v59, 0, 0x20u);
    if ( v9 )
      --*((_DWORD *)v9 + 88);
  }
  if ( (*(_DWORD *)(v8 + 84) & 1) != 0 )
  {
    if ( ((unsigned __int8)(1 << *((_BYTE *)v6 + 492)) & *((_BYTE *)v9 + 220)) == 0 )
    {
      v60 = *(_QWORD *)(v8 + 40);
      if ( v60 )
        ExReleaseAutoExpandPushLockShared(v60, 2, v16);
      else
        ExReleaseAutoExpandPushLockExclusive((char *)v6 + 440, 2);
    }
    *(_DWORD *)(v8 + 84) &= ~1u;
  }
  if ( (v80 & 4) != 0 )
  {
    v61 = v78;
    if ( _InterlockedDecrement((volatile signed __int32 *)v78 + 12) < 0 && (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    ExReleasePushLockEx((char *)v61 + 40, 0);
  }
  return (unsigned int)Space;
}

```

## disassembly

```asm
0x1400c8d40  mov     [rsp-8+arg_10], r8
0x1400c8d45  mov     [rsp-8+arg_0], rcx
0x1400c8d4a  push    rbp
0x1400c8d4b  push    rbx
0x1400c8d4c  push    rsi
0x1400c8d4d  push    rdi
0x1400c8d4e  push    r12
0x1400c8d50  push    r13
0x1400c8d52  push    r14
0x1400c8d54  push    r15
0x1400c8d56  lea     rbp, [rsp-58h]
0x1400c8d5b  sub     rsp, 158h
0x1400c8d62  mov     rsi, [r8+10h]
0x1400c8d66  lea     rax, [rsp+190h+var_140]
0x1400c8d6b  mov     r15, [r9+8]
0x1400c8d6f  xorps   xmm0, xmm0
0x1400c8d72  mov     r14, r8
0x1400c8d75  mov     [rbp+90h+var_B8], rsi
0x1400c8d79  mov     r12, rcx
0x1400c8d7c  mov     r13, [rsi+1C8h]
0x1400c8d83  mov     [rbp+90h+var_F8], rax
0x1400c8d87  mov     eax, [r8+44h]
0x1400c8d8b  and     eax, 8
0x1400c8d8e  mov     [rsp+190h+var_140], rdx
0x1400c8d93  xor     edx, edx
0x1400c8d95  movdqa  [rsp+190h+var_120], xmm0
0x1400c8d9b  mov     [rsp+190h+var_138], rdx
0x1400c8da0  mov     [rsp+190h+var_130], rdx
0x1400c8da5  mov     [rsp+190h+var_128], rdx
0x1400c8daa  mov     [rbp+90h+var_110], rdx
0x1400c8dae  mov     [rbp+90h+var_108], edx
0x1400c8db1  mov     [rbp+90h+var_104], dx
0x1400c8db5  mov     [rbp+90h+var_102], dl
0x1400c8db8  mov     [rbp+90h+var_100], r8
0x1400c8dbc  movdqa  [rbp+90h+var_F0], xmm0
0x1400c8dc1  mov     [rbp+90h+var_E0], rdx
0x1400c8dc5  mov     [rbp+90h+var_D0], edx
0x1400c8dc8  mov     [rbp+90h+var_D8], rdx
0x1400c8dcc  mov     [rsp+190h+var_150], rdx
0x1400c8dd1  mov     edi, [rsi+1D4h]
0x1400c8dd7  mov     [rbp+90h+var_C0], eax
0x1400c8dda  mov     eax, [r8+54h]
0x1400c8dde  mov     [rbp+90h+var_B0], r13
0x1400c8de2  mov     [rbp+90h+var_A8], rdx
0x1400c8de6  mov     [rbp+90h+var_A0], rdx
0x1400c8dea  mov     [rbp+90h+arg_18], edi
0x1400c8df0  mov     [rbp+90h+arg_8], dl
0x1400c8df6  cmp     r15, 20h ; ' '
0x1400c8dfa  ja      short loc_1400C8E05
0x1400c8dfc  mov     ecx, 4
0x1400c8e01  test    al, 2
0x1400c8e03  jnz     short loc_1400C8E07
0x1400c8e05  mov     ecx, edx
0x1400c8e07  and     eax, 0FFFFFFFBh
0x1400c8e0a  or      eax, ecx
0x1400c8e0c  mov     [r8+54h], eax
0x1400c8e10  mov     r8, [rbp+90h+var_100]; struct SmsAllocationContext *
0x1400c8e14  lea     r9, [rsp+190h+var_138]; struct MsAllocator::RangeArrayStrategy::Context *
0x1400c8e19  mov     [rsp+190h+var_138], rdx
0x1400c8e1e  xorps   xmm0, xmm0
0x1400c8e21  mov     [rsp+190h+var_130], rdx
0x1400c8e26  mov     rcx, r12; struct CmsTransactionContext *
0x1400c8e29  mov     [rbp+90h+var_E0], rdx
0x1400c8e2d  mov     [rbp+90h+var_D0], edx
0x1400c8e30  mov     [rbp+90h+var_D8], rdx
0x1400c8e34  mov     rdx, [rsp+190h+var_140]; struct MsAllocator::RangeArrayStrategy::State *
0x1400c8e39  movdqa  [rbp+90h+var_F0], xmm0
0x1400c8e3e  call    ?NextSpace@RangeArrayStrategy@MsAllocator@@CAJPEAVCmsTransactionContext@@PEAUState@12@PEAUSmsAllocationContext@@AEAUContext@12@@Z; MsAllocator::RangeArrayStrategy::NextSpace(CmsTransactionContext *,MsAllocator::RangeArrayStrategy::State *,SmsAllocationContext *,MsAllocator::RangeArrayStrategy::Context &)
0x1400c8e43  mov     ebx, eax
0x1400c8e45  cmp     eax, 0C000022Dh
0x1400c8e4a  jz      loc_1400C93C2
0x1400c8e50  cmp     ebx, 0C0000273h
0x1400c8e56  jz      loc_1400C93A0
0x1400c8e5c  test    ebx, ebx
0x1400c8e5e  js      loc_1400C952C
0x1400c8e64  jmp     short loc_1400C8E76
0x1400c8e70  mov     edi, [rbp+90h+arg_18]
0x1400c8e76  mov     rax, [rsp+190h+var_150]
0x1400c8e7b  test    rax, rax
0x1400c8e7e  jz      short loc_1400C8EBE
0x1400c8e80  mov     rcx, [r13+0CC8h]
0x1400c8e87  xor     edx, edx; Tag
0x1400c8e89  nop
0x1400c8e8a  add     rcx, 1E0h; RemoveLock
0x1400c8e91  lock dec dword ptr [rax+5Ch]
0x1400c8e95  mov     r8d, 20h ; ' '; RemlockSize
0x1400c8e9b  nop
0x1400c8e9c  call    cs:__imp_IoReleaseRemoveLockEx
0x1400c8ea3  nop     dword ptr [rax+rax+00h]
0x1400c8ea8  test    r12, r12
0x1400c8eab  jz      short loc_1400C8EB5
0x1400c8ead  dec     dword ptr [r12+160h]
0x1400c8eb5  mov     [rsp+190h+var_150], 0
0x1400c8ebe  mov     rdx, r12
0x1400c8ec1  lea     rcx, [rbp+90h+var_F8]
0x1400c8ec5  call    ?Advance@?$CandidateIterator@VRangeArrayStrategy@MsAllocator@@@MsAllocator@@QEAAJPEAVCmsTransactionContext@@@Z; MsAllocator::CandidateIterator<MsAllocator::RangeArrayStrategy>::Advance(CmsTransactionContext *)
0x1400c8eca  mov     ebx, eax
0x1400c8ecc  test    eax, eax
0x1400c8ece  js      loc_1400C92BB
0x1400c8ed4  inc     dword ptr [r14+50h]
0x1400c8ed8  cmp     [rbp+90h+var_C0], 0
0x1400c8edc  jz      short loc_1400C8F20
0x1400c8ede  mov     r8, qword ptr [rbp+90h+var_F0]
0x1400c8ee2  xor     ecx, ecx
0x1400c8ee4  mov     r10, qword ptr [rbp+90h+var_F0+8]
0x1400c8ee8  movsxd  r9, edi
0x1400c8eeb  mov     rax, r9
0x1400c8eee  neg     rax
0x1400c8ef1  lea     rdx, [r8-1]
0x1400c8ef5  add     rdx, r9
0x1400c8ef8  and     rdx, rax
0x1400c8efb  lea     rax, [r8+r10]
0x1400c8eff  cmp     rax, rdx
0x1400c8f02  jbe     short loc_1400C8F0D
0x1400c8f04  mov     rcx, r8
0x1400c8f07  sub     rcx, rdx
0x1400c8f0a  add     rcx, r10
0x1400c8f0d  cmp     rcx, r9
0x1400c8f10  jb      loc_1400C8E70
0x1400c8f16  mov     qword ptr [rbp+90h+var_F0], rdx
0x1400c8f1a  mov     qword ptr [rbp+90h+var_F0+8], rcx
0x1400c8f1e  jmp     short loc_1400C8F24
0x1400c8f20  mov     rcx, qword ptr [rbp+90h+var_F0+8]
0x1400c8f24  mov     r8, [rbp+90h+var_E0]
0x1400c8f28  movzx   edx, word ptr [r8+24h]
0x1400c8f2d  movsxd  rax, dword ptr [r8+10h]
0x1400c8f31  test    dl, 2
0x1400c8f34  jz      short loc_1400C8F3F
0x1400c8f36  test    rax, rax
0x1400c8f39  jz      short loc_1400C8F3F
0x1400c8f3b  mov     rax, [r8+8]
0x1400c8f3f  cmp     rax, rcx
0x1400c8f42  cmovnb  rax, rcx
0x1400c8f46  test    rax, rax
0x1400c8f49  jz      loc_1400C8E70
0x1400c8f4f  mov     ecx, [r14+44h]
0x1400c8f53  cmp     rax, r15
0x1400c8f56  jnb     short loc_1400C8F61
0x1400c8f58  test    cl, 8
0x1400c8f5b  jnz     loc_1400C8E70
0x1400c8f61  test    dl, 64h
0x1400c8f64  jnz     loc_1400C8E70
0x1400c8f6a  test    cl, 40h
0x1400c8f6d  jnz     short loc_1400C8F78
0x1400c8f6f  test    dl, 8
0x1400c8f72  jnz     loc_1400C8E70
0x1400c8f78  cmp     byte ptr [rsi+1ECh], 2
0x1400c8f7f  jz      short loc_1400C8FC0
0x1400c8f81  lea     rax, [rsp+190h+var_150]
0x1400c8f86  mov     r8, r14; struct SmsAllocationContext *
0x1400c8f89  mov     [rsp+190h+var_168], rax; struct SmsContainer **
0x1400c8f8e  lea     r9, [rbp+90h+var_F0]; struct MsAllocator::AllocationCandidate *
0x1400c8f92  lea     rax, [rbp+90h+var_A8]
0x1400c8f96  mov     rdx, r12; struct CmsTransactionContext *
0x1400c8f99  mov     rcx, rsi; this
0x1400c8f9c  mov     [rsp+190h+var_170], rax; struct _RANGE *
0x1400c8fa1  call    ?PopulateContainersForCandidate@CmsAllocator@@AEAAJPEAVCmsTransactionContext@@PEAUSmsAllocationContext@@AEBUAllocationCandidate@MsAllocator@@PEAU_RANGE@@PEAPEAUSmsContainer@@@Z; CmsAllocator::PopulateContainersForCandidate(CmsTransactionContext *,SmsAllocationContext *,MsAllocator::AllocationCandidate const &,_RANGE *,SmsContainer * *)
0x1400c8fa6  mov     ebx, eax
0x1400c8fa8  test    eax, eax
0x1400c8faa  jns     short loc_1400C8FBC
0x1400c8fac  cmp     eax, 0C000022Dh
0x1400c8fb1  jz      loc_1400C8E76
0x1400c8fb7  jmp     loc_1400C952C
0x1400c8fbc  mov     r8, [rbp+90h+var_E0]
0x1400c8fc0  test    byte ptr [rbp+90h+var_D0], 2
0x1400c8fc4  jnz     short loc_1400C8FD4
0x1400c8fc6  cmp     [rbp+90h+arg_8], 0
0x1400c8fcd  jnz     short loc_1400C8FD4
0x1400c8fcf  xor     r9b, r9b
0x1400c8fd2  jmp     short loc_1400C8FD7
0x1400c8fd4  mov     r9b, 1
0x1400c8fd7  movzx   ebx, word ptr [r8+24h]
0x1400c8fdc  and     bx, 2
0x1400c8fe0  lock or [rsp+190h+var_190], 0
0x1400c8fe5  test    byte ptr [rbp+90h+var_D0], 1
0x1400c8fe9  jnz     short loc_1400C8FFC
0x1400c8feb  mov     eax, [r14+54h]
0x1400c8fef  test    al, 4
0x1400c8ff1  jnz     short loc_1400C8FF8
0x1400c8ff3  test    bx, bx
0x1400c8ff6  jz      short loc_1400C8FFC
0x1400c8ff8  xor     dl, dl
0x1400c8ffa  jmp     short loc_1400C8FFE
0x1400c8ffc  mov     dl, 1
0x1400c8ffe  test    bx, bx
0x1400c9001  jnz     short loc_1400C902B
0x1400c9003  mov     rax, [rbp+90h+var_E0]
0x1400c9007  mov     ecx, [rsi+1D4h]
0x1400c900d  cmp     [rax+8], rcx
0x1400c9011  jnz     short loc_1400C902B
0x1400c9013  test    r9b, r9b
0x1400c9016  jnz     short loc_1400C902B
0x1400c9018  test    dl, dl
0x1400c901a  jnz     short loc_1400C902B
0x1400c901c  test    dword ptr [r14+54h], 200h
0x1400c9024  jnz     short loc_1400C902B
0x1400c9026  mov     dil, 1
0x1400c9029  jmp     short loc_1400C902E
0x1400c902b  xor     dil, dil
0x1400c902e  mov     [rsp+190h+var_160], dil; bool
0x1400c9033  mov     r8, r14; struct SmsAllocationContext *
0x1400c9036  mov     byte ptr [rsp+190h+var_168], dl; bool
0x1400c903a  mov     rcx, rsi; this
0x1400c903d  mov     byte ptr [rsp+190h+var_170], r9b; bool
0x1400c9042  mov     rdx, r12; struct CmsTransactionContext *
0x1400c9045  lea     r9, [rbp+90h+var_F0]; struct MsAllocator::AllocationCandidate *
0x1400c9049  call    ?TryLockCandidateForAllocation@CmsAllocator@@AEAA_NPEAVCmsTransactionContext@@PEAUSmsAllocationContext@@AEBUAllocationCandidate@MsAllocator@@_N33@Z; CmsAllocator::TryLockCandidateForAllocation(CmsTransactionContext *,SmsAllocationContext *,MsAllocator::AllocationCandidate const &,bool,bool,bool)
0x1400c904e  test    al, al
0x1400c9050  jz      loc_1400C90DA
0x1400c9056  or      byte ptr [rbp+90h+var_D0], 4
0x1400c905a  mov     r8, [rbp+90h+var_E0]
0x1400c905e  movzx   edx, word ptr [r8+24h]
0x1400c9063  movsxd  rcx, dword ptr [r8+10h]
0x1400c9067  test    dl, 2
0x1400c906a  jz      short loc_1400C9075
0x1400c906c  test    rcx, rcx
0x1400c906f  jz      short loc_1400C9075
0x1400c9071  mov     rcx, [r8+8]
0x1400c9075  cmp     rcx, qword ptr [rbp+90h+var_F0+8]
0x1400c9079  cmovnb  rcx, qword ptr [rbp+90h+var_F0+8]
0x1400c907e  test    rcx, rcx
0x1400c9081  jz      loc_1400C8E70
0x1400c9087  mov     eax, [r14+44h]
0x1400c908b  cmp     rcx, r15
0x1400c908e  jnb     short loc_1400C9098
0x1400c9090  test    al, 8
0x1400c9092  jnz     loc_1400C8E70
0x1400c9098  test    dl, 64h
0x1400c909b  jnz     loc_1400C8E70
0x1400c90a1  test    al, 40h
0x1400c90a3  jnz     short loc_1400C90AE
0x1400c90a5  test    dl, 8
0x1400c90a8  jnz     loc_1400C8E70
0x1400c90ae  test    bx, bx
0x1400c90b1  jz      loc_1400C9149
0x1400c90b7  lea     r9, [rbp+90h+var_F0]; struct MsAllocator::AllocationCandidate *
0x1400c90bb  mov     r8, r14; struct SmsAllocationContext *
0x1400c90be  mov     rdx, r12; struct CmsTransactionContext *
0x1400c90c1  mov     rcx, rsi; this
0x1400c90c4  call    ?PrepareRangeOnlyCandidateForAllocation@CmsAllocator@@AEAAJPEAVCmsTransactionContext@@PEAUSmsAllocationContext@@AEAUAllocationCandidate@MsAllocator@@@Z; CmsAllocator::PrepareRangeOnlyCandidateForAllocation(CmsTransactionContext *,SmsAllocationContext *,MsAllocator::AllocationCandidate &)
0x1400c90c9  mov     ebx, eax
0x1400c90cb  test    eax, eax
0x1400c90cd  jns     short loc_1400C90F5
0x1400c90cf  cmp     eax, 0C000022Dh
0x1400c90d4  jnz     loc_1400C952C
0x1400c90da  mov     rcx, qword ptr [rbp+90h+var_F0+8]
0x1400c90de  movsxd  rdi, [rbp+90h+arg_18]
0x1400c90e5  cmp     rcx, rdi
0x1400c90e8  cmovnb  rcx, rdi
0x1400c90ec  mov     qword ptr [rbp+90h+var_F0+8], rcx
0x1400c90f0  jmp     loc_1400C8E76
0x1400c90f5  mov     r8, [rbp+90h+var_E0]
0x1400c90f9  movzx   edx, word ptr [r8+24h]
0x1400c90fe  movsxd  rcx, dword ptr [r8+10h]
0x1400c9102  test    dl, 2
0x1400c9105  jz      short loc_1400C9110
0x1400c9107  test    rcx, rcx
0x1400c910a  jz      short loc_1400C9110
0x1400c910c  mov     rcx, [r8+8]
0x1400c9110  cmp     rcx, qword ptr [rbp+90h+var_F0+8]
0x1400c9114  cmovnb  rcx, qword ptr [rbp+90h+var_F0+8]
0x1400c9119  test    rcx, rcx
0x1400c911c  jz      loc_1400C8E70
0x1400c9122  mov     eax, [r14+44h]
0x1400c9126  cmp     rcx, r15
0x1400c9129  jnb     short loc_1400C9133
0x1400c912b  test    al, 8
0x1400c912d  jnz     loc_1400C8E70
0x1400c9133  test    dl, 64h
0x1400c9136  jnz     loc_1400C8E70
0x1400c913c  test    al, 40h
0x1400c913e  jnz     short loc_1400C9149
0x1400c9140  test    dl, 8
0x1400c9143  jnz     loc_1400C8E70
0x1400c9149  movzx   ecx, byte ptr [rsi+1ECh]
0x1400c9150  cmp     cl, 3
0x1400c9153  jnz     short loc_1400C9183
0x1400c9155  mov     eax, [r14+44h]
0x1400c9159  test    al, 10h
0x1400c915b  jnz     short loc_1400C9183
0x1400c915d  mov     rax, [r13+0CC8h]
0x1400c9164  mov     edx, [rax+184h]
0x1400c916a  mov     rax, [rsp+190h+var_150]
0x1400c916f  shl     edx, 4
0x1400c9172  mov     rdx, [rdx+rax+2A0h]
0x1400c917a  cmp     [r8], rdx
0x1400c917d  jnz     loc_1400C8E70
0x1400c9183  mov     eax, [r14+54h]
0x1400c9187  test    al, 1
0x1400c9189  jz      short loc_1400C91D4
0x1400c918b  mov     edx, 1
0x1400c9190  shl     dl, cl
0x1400c9192  test    [r12+0DCh], dl
0x1400c919a  jnz     short loc_1400C91CF
0x1400c919c  mov     rcx, [r14+28h]
0x1400c91a0  mov     edx, 2
0x1400c91a5  test    rcx, rcx
0x1400c91a8  jz      short loc_1400C91B8
0x1400c91aa  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x1400c91b1  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
