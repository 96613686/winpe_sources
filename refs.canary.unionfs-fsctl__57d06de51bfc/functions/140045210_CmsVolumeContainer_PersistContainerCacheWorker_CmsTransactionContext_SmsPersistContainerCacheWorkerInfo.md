# CmsVolumeContainer::PersistContainerCacheWorker(CmsTransactionContext *,SmsPersistContainerCacheWorkerInfo *)

- ea: `0x140045210`
- end: `0x140045904`
- name: `?PersistContainerCacheWorker@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@PEAUSmsPersistContainerCacheWorkerInfo@@@Z`
- size: `1780`
- prototype: `__int64 __fastcall(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, struct SmsPersistContainerCacheWorkerInfo *)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140064250`
- `0x1400ac0c0`

## callees

- `0x140045210`
- `0x140045910`
- `0x140048ab4`
- `0x140049438`
- `0x140049620`
- `0x14005a1e0`
- `0x14008e900`
- `0x1400ae360`
- `0x1400b1190`
- `0x1400cdb78`
- `0x1401356e8`
- `0x14015f8dc`
- `0x140172278`
- `0x1401e9e40`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x140045447`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x140045447`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14004546c`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401f2fe2`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14004546c`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401f2fe2`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1401f2fcd`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1401f2fcd`
- `ntoskrnl!RtlIsZeroMemory` at `0x1401f3102`
- `ntoskrnl!RtlIsZeroMemory` at `0x1401f3102`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400453ae`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400455f8`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400453ae`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400455f8`
- `ntoskrnl!ExReleasePushLockEx` at `0x140045386`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400455d0`
- `ntoskrnl!ExReleasePushLockEx` at `0x140045386`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400455d0`

## pseudocode

```c
__int64 __fastcall CmsVolumeContainer::PersistContainerCacheWorker(
        CmsVolumeContainer *this,
        struct CmsTransactionContext *a2,
        struct SmsPersistContainerCacheWorkerInfo *a3)
{
  char v3; // r12
  int v4; // r10d
  unsigned int v5; // ebx
  unsigned int v7; // r15d
  __int64 i; // rdi
  __int64 v10; // rcx
  unsigned __int64 v11; // r13
  bool v12; // r9
  SmsAllocationRegionEx *v13; // rdi
  char v14; // r12
  int v15; // ecx
  __int64 m; // rax
  __int64 v17; // rdi
  bool v18; // zf
  char v19; // al
  char v20; // cl
  __int64 result; // rax
  int v22; // eax
  _DWORD *v23; // r12
  int v24; // r8d
  __int64 v25; // rcx
  CmsAllocator *v26; // rcx
  unsigned int j; // eax
  __int64 v28; // rbx
  int v29; // r8d
  __int64 v30; // rcx
  CmsAllocator *v31; // rcx
  int v32; // r9d
  int v33; // r8d
  int v34; // edx
  int v35; // eax
  unsigned int v36; // ecx
  int v37; // eax
  unsigned int v38; // ecx
  __int64 *n; // rcx
  char v40; // al
  char v41; // cl
  __int64 *k; // rcx
  char v43; // al
  unsigned int v44; // ecx
  unsigned int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // r8
  char *v48; // rcx
  int v49; // eax
  __int64 v50; // rcx
  CmsAllocator *v51; // rcx
  __int64 v52; // rax
  CmsAllocator *v53; // rcx
  SmsAllocationRegionEx *v54; // r12
  CmsAllocator *v55; // rcx
  SmsAllocationRegionEx *v56; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v57[2]; // [rsp+38h] [rbp-28h] BYREF
  struct _RANGE *v58; // [rsp+40h] [rbp-20h] BYREF
  SmsAllocationRegionEx ***v59; // [rsp+48h] [rbp-18h] BYREF
  char *v60; // [rsp+50h] [rbp-10h]
  void *v61; // [rsp+58h] [rbp-8h]
  char v62; // [rsp+A0h] [rbp+40h]
  SmsAllocationRegionEx **v63; // [rsp+B0h] [rbp+50h] BYREF
  int v64; // [rsp+B8h] [rbp+58h]

  v3 = *((_BYTE *)a3 + 88);
  v4 = 0;
  v5 = *((_DWORD *)a3 + 20);
  v7 = *((_DWORD *)a3 + 21);
  LODWORD(v63) = 0;
  LOBYTE(v64) = 0;
  v62 = v3;
  while ( 1 )
  {
LABEL_2:
    for ( i = 0; v5 < v7; i = *(_QWORD *)(*((_QWORD *)this + 65) + 8 * v10) )
    {
      if ( i )
        break;
      v10 = v5++;
    }
    v56 = (SmsAllocationRegionEx *)i;
    if ( !i )
      break;
    v11 = *(_QWORD *)(i + 592);
    if ( !v3 )
      goto LABEL_7;
    if ( *(_DWORD *)(i + 92) )
      goto LABEL_7;
    if ( *(_DWORD *)(i + 88) )
      goto LABEL_7;
    v19 = *(_BYTE *)(i + 24);
    if ( (v19 & 0x48) != 0 )
      goto LABEL_7;
    if ( *(_DWORD *)(i + 112) )
      goto LABEL_7;
    if ( *(_DWORD *)(i + 116) )
      goto LABEL_7;
    if ( (v19 & 0x25) != 0 )
      goto LABEL_7;
    v20 = *(_BYTE *)(i + 25);
    if ( (v20 & 8) != 0 )
      goto LABEL_7;
    if ( (*(_DWORD *)(i + 612) & 0x201) != 0 )
      goto LABEL_7;
    if ( (v20 & 0x10) != 0 )
      goto LABEL_7;
    if ( (int)++*(_DWORD *)(i + 96) < 10 )
      goto LABEL_7;
    ExAcquireAutoExpandPushLockExclusive((char *)this + 56, 2);
    if ( *(_DWORD *)(i + 92)
      || *(_DWORD *)(i + 88)
      || (v40 = *(_BYTE *)(i + 24), (v40 & 0x48) != 0)
      || *(_DWORD *)(i + 112)
      || *(_DWORD *)(i + 116)
      || (v40 & 0x25) != 0
      || (v41 = *(_BYTE *)(i + 25), (v41 & 8) != 0)
      || (*(_DWORD *)(i + 612) & 0x201) != 0
      || (v41 & 0x10) != 0 )
    {
      ExReleaseAutoExpandPushLockExclusive((char *)this + 56, 2);
      v3 = v62;
LABEL_7:
      *(_QWORD *)a2 |= 0x400000000uLL;
      v4 = CmsVolumeContainer::PinContainer(this, a2, v11, &v56, 0, 1);
      LODWORD(v63) = v4;
      *(_QWORD *)a2 &= ~0x400000000uLL;
      if ( v4 < 0 )
        break;
      v13 = v56;
      if ( v3 )
      {
        v14 = *((_BYTE *)v56 + 25) & 0x10;
        if ( v14 )
        {
          LODWORD(v56) = 0;
          if ( (*((_DWORD *)v13 + 153) & 8) != 0 || (*((_DWORD *)this + 30) & 8) == 0 )
          {
            v33 = *((_DWORD *)v13 + 156);
            v4 = 0;
            LODWORD(v63) = 0;
            v32 = 0;
            LODWORD(v56) = v33;
          }
          else
          {
            v29 = *((_DWORD *)this + 99);
            v30 = *((_QWORD *)this + 1);
            v63 = &v56;
            v59 = &v63;
            v31 = *(CmsAllocator **)(v30 + 3328);
            v61 = v57;
            *(_QWORD *)v57 = 0;
            v60 = (char *)v13 + (unsigned int)(16 * v29) + 672;
            LODWORD(v63) = CmsAllocator::WalkAllocator__CmsAllocator::QueryContainerRangeAllocatedCount_::_2_::_lambda_1___(
                             v31,
                             (__int64)&v59);
            v4 = (int)v63;
            v32 = (int)v63;
            if ( (int)v63 < 0 )
              goto LABEL_67;
            v33 = (int)v56;
          }
          v34 = *((_DWORD *)v13 + 153);
          v35 = 0;
          if ( !v33 )
            v35 = 0x2000;
          v36 = v35 | *((_DWORD *)v13 + 153) & 0xFFFFDFFF;
          v37 = 0;
          if ( v33 == *((_DWORD *)v13 + 154) )
            v37 = 0x4000;
          v38 = v37 | v36 & 0xFFFFBFFF;
          *((_DWORD *)v13 + 153) = v38;
          *((_BYTE *)v13 + 25) &= ~0x10u;
          if ( (((unsigned __int16)v38 ^ (unsigned __int16)v34) & 0x2000) == 0
            && (((unsigned __int16)v38 ^ (unsigned __int16)v34) & 0x4000) == 0 )
          {
LABEL_67:
            if ( v4 < 0 )
            {
              CmsVolumeContainer::UnpinContainer(this, a2, v11, 0);
              v4 = (int)v63;
              goto LABEL_43;
            }
            goto LABEL_10;
          }
          *((_BYTE *)v13 + 24) |= 1u;
          v4 = v32;
          LODWORD(v63) = v32;
        }
LABEL_10:
        v15 = *((_DWORD *)v13 + 153);
        if ( ((v15 & 0x2000) != 0 || (*((_BYTE *)v13 + 24) & 4) != 0) && (v15 & 8) != 0 )
        {
          v22 = (unsigned __int8)v64;
          if ( !*((_DWORD *)v13 + 22) )
            v22 = 1;
          v64 = v22;
        }
        if ( (v15 & 0x2100) == 0x2100 )
        {
          v43 = v64;
          if ( (v15 & 8) == 0 )
            v43 = 1;
          LOBYTE(v64) = v43;
        }
        if ( (*((_BYTE *)v13 + 24) & 0x40) != 0 && *((_QWORD *)v13 + 5) <= *(_QWORD *)(*((_QWORD *)this + 1) + 2112LL) )
        {
          *((_DWORD *)v13 + 163) = 0;
          *((_BYTE *)v13 + 24) = *((_BYTE *)v13 + 24) & 0xBE | 1;
          v47 = *(_QWORD *)(*((_QWORD *)this + 1) + 2112LL);
          v48 = (char *)v13
              + 24 * (((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)v13 + 44, 1u) + 1) & 0xF);
          *((_DWORD *)v48 + 46) = 12;
          *((_QWORD *)v48 + 24) = v47;
          *((_QWORD *)v48 + 25) = 0;
          _InterlockedDecrement((volatile signed __int32 *)this + 116);
          _InterlockedAdd64(
            (volatile signed __int64 *)(*((_QWORD *)this + 1) + 3896LL),
            *(unsigned int *)(*((_QWORD *)this + 1) + 84LL));
          _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)this + 1) + 3912LL));
          _InterlockedAdd64(
            (volatile signed __int64 *)(*((_QWORD *)this + 1) + 3920LL),
            -*(_DWORD *)(*((_QWORD *)this + 1) + 84LL));
        }
        if ( (*((_BYTE *)v13 + 24) & 1) != 0 )
        {
          if ( v14 && (*((_BYTE *)this + 768) & 0x40) == 0 )
          {
            LODWORD(v56) = 0;
            v57[0] = 0;
            if ( (*((_DWORD *)v13 + 153) & 8) != 0
              || (v23 = (_DWORD *)((char *)this + 120), (*((_DWORD *)this + 30) & 8) == 0) )
            {
              v44 = *((_DWORD *)v13 + 156);
              v23 = (_DWORD *)((char *)this + 120);
              LODWORD(v56) = v44;
              v45 = *((_DWORD *)v13 + 158);
              v57[0] = v45;
            }
            else
            {
              v24 = *((_DWORD *)this + 99);
              v25 = *((_QWORD *)this + 1);
              v58 = (struct _RANGE *)v57;
              v63 = &v56;
              v59 = &v63;
              v26 = *(CmsAllocator **)(v25 + 3328);
              v61 = &v58;
              v60 = (char *)v13 + (unsigned int)(16 * v24) + 672;
              LODWORD(v63) = CmsAllocator::WalkAllocator__CmsAllocator::QueryContainerRangeAllocatedCount_::_2_::_lambda_1___(
                               v26,
                               (__int64)&v59);
              v4 = (int)v63;
              if ( (int)v63 < 0 )
              {
                for ( j = 0; ; ++j )
                {
                  if ( j >= 4 )
                  {
                    v28 = 0;
                    if ( j == 4 )
                    {
                      for ( k = (__int64 *)*((_QWORD *)a2 + 41); ; k = (__int64 *)*k )
                      {
                        v28 = 0;
                        if ( !k )
                          break;
                        v28 = k[1];
                        if ( v28 && *(_QWORD *)(v28 + 592) == v11 )
                        {
                          v18 = (*((_DWORD *)k + 4))-- == 1;
                          if ( !v18 )
                            goto LABEL_43;
                          k[1] = 0;
                          goto LABEL_56;
                        }
                      }
                    }
                    goto LABEL_56;
                  }
                  v28 = *((_QWORD *)a2 + j + 37);
                  if ( v28 )
                  {
                    if ( *(_QWORD *)(v28 + 592) == v11 )
                      break;
                  }
                }
                v18 = (*((_DWORD *)a2 + j + 84))-- == 1;
                if ( !v18 )
                  goto LABEL_43;
                *((_QWORD *)a2 + j + 37) = 0;
LABEL_56:
                ExReleasePushLockEx(v28 + 120, 2);
                --*((_DWORD *)a2 + 89);
                _InterlockedDecrement((volatile signed __int32 *)(v28 + 92));
                IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)this + 488), 0, 0x20u);
                --*((_DWORD *)a2 + 88);
                v4 = (int)v63;
                goto LABEL_43;
              }
              v44 = (unsigned int)v56;
              v45 = v57[0];
            }
            if ( v44 < v45
              && ((*((_DWORD *)v13 + 153) & 8) != 0 || (*v23 & 8) == 0)
              && (*((_DWORD *)v13 + 153) & 8) == 0 )
            {
              *((_DWORD *)v13 + 158) = v44;
            }
          }
          if ( (*((_DWORD *)v13 + 153) & 0x2008) == 0x2000
            && *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 1) + 3344LL) + 16LL)
            && !(unsigned __int8)RtlIsZeroMemory((char *)v13 + 672, (unsigned int)(16 * *((_DWORD *)this + 99))) )
          {
            *((_DWORD *)v13 + 153) |= 0x100u;
            LOBYTE(v64) = 1;
          }
          if ( (*((_BYTE *)v13 + 24) & 2) != 0 )
          {
            LODWORD(v63) = CmsVolumeContainer::PersistNewContainer(this, a2, v13);
            CmsVolumeContainer::UnpinContainer(this, a2, v11, 0);
            v4 = (int)v63;
          }
          else
          {
            CmsVolumeContainer::UnpinContainer(this, a2, v11, 0);
            LODWORD(v63) = CmsVolumeContainer::PersistContainer(this, a2, v11);
            v4 = (int)v63;
            if ( (int)v63 < 0 )
              goto LABEL_43;
          }
          v3 = v62;
          if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 1) + 3344LL) + 16LL) && (*((_DWORD *)v13 + 153) & 8) == 0 )
          {
            memmove(*((void **)v13 + 71), (char *)v13 + 672, (unsigned int)(16 * *((_DWORD *)this + 99)));
            v4 = (int)v63;
          }
        }
        else
        {
          for ( m = 0; ; m = (unsigned int)(m + 1) )
          {
            if ( (unsigned int)m >= 4 )
            {
              v17 = 0;
              if ( (_DWORD)m == 4 )
              {
                for ( n = (__int64 *)*((_QWORD *)a2 + 41); ; n = (__int64 *)*n )
                {
                  v17 = 0;
                  if ( !n )
                    break;
                  v17 = n[1];
                  if ( v17 && *(_QWORD *)(v17 + 592) == v11 )
                  {
                    v18 = (*((_DWORD *)n + 4))-- == 1;
                    v3 = v62;
                    if ( !v18 )
                      goto LABEL_2;
                    n[1] = 0;
                    goto LABEL_21;
                  }
                }
              }
              goto LABEL_21;
            }
            v17 = *((_QWORD *)a2 + m + 37);
            if ( v17 )
            {
              if ( *(_QWORD *)(v17 + 592) == v11 )
                break;
            }
          }
          v18 = (*((_DWORD *)a2 + m + 84))-- == 1;
          v3 = v62;
          if ( !v18 )
            continue;
          *((_QWORD *)a2 + (unsigned int)m + 37) = 0;
LABEL_21:
          ExReleasePushLockEx(v17 + 120, 2);
          --*((_DWORD *)a2 + 89);
          _InterlockedDecrement((volatile signed __int32 *)(v17 + 92));
          IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)this + 488), 0, 0x20u);
          --*((_DWORD *)a2 + 88);
          v4 = (int)v63;
          v3 = v62;
        }
      }
      else
      {
        v57[0] = 0;
        LODWORD(v63) = CmsVolumeContainer::GetNumAllocatedForContainerEntry(
                         this,
                         a2,
                         (SmsAllocationRegionEx *)((char *)v56 + 592),
                         v12,
                         v57,
                         0);
        if ( (int)v63 < 0 )
        {
          CmsVolumeContainer::UnpinContainer(this, a2, v11, 0);
          return (unsigned int)v63;
        }
        if ( v57[0] && (*((_BYTE *)v13 + 24) & 4) == 0
          || (*((_DWORD *)v13 + 153) & 8) == 0
          || *((_DWORD *)v13 + 22)
          || (*(_DWORD *)(*((_QWORD *)this + 1) + 3460LL) & 0x8000) != 0 )
        {
          v49 = *((_DWORD *)v13 + 153);
          if ( (v49 & 0x100) != 0 && !v57[0] && (v49 & 8) == 0 )
          {
            v50 = *((_QWORD *)this + 1);
            if ( *(_BYTE *)(*(_QWORD *)(v50 + 3344) + 16LL) )
            {
              v51 = *(CmsAllocator **)(v50 + 3328);
              v52 = (unsigned int)(16 * *((_DWORD *)this + 99)) + 672LL;
              v56 = 0;
              v58 = (SmsAllocationRegionEx *)((char *)v13 + v52);
              if ( (int)CmsAllocator::PinBitmapRegion(v51, a2, (SmsAllocationRegionEx *)((char *)v13 + v52), &v56) >= 0 )
              {
                v54 = v56;
                if ( CmsAllocator::TryProtectRegion(v53, v56, 1) >= 0 )
                {
                  if ( !SmsAllocationRegionEx::GetTotalAllocated(v54)
                    && (int)CmsIntegrityState::ResetIntegrityState(
                              *(CmsIntegrityState **)(*((_QWORD *)this + 1) + 3344LL),
                              a2,
                              v58) >= 0 )
                  {
                    memset((char *)v13 + 672, 0, (unsigned int)(16 * *((_DWORD *)this + 99)));
                    *((_DWORD *)v13 + 153) &= ~0x100u;
                    *((_BYTE *)v13 + 24) |= 1u;
                  }
                  CmsAllocator::TryProtectRegion(v55, v54, 0);
                }
                v3 = v62;
              }
            }
          }
          CmsVolumeContainer::UnpinContainer(this, a2, v11, 0);
          v4 = (int)v63;
        }
        else
        {
          CmsVolumeContainer::UnpinContainer(this, a2, v11, 0);
          CmsVolumeContainer::DeleteContainer(this, a2, v11);
          v4 = (int)v63;
        }
      }
    }
    else
    {
      RtlRemoveEntryHashTable(*((PRTL_DYNAMIC_HASH_TABLE *)this + 6), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)i, 0);
      ExReleaseAutoExpandPushLockExclusive((char *)this + 56, 2);
      v46 = v5 - 1;
      *(_QWORD *)(*((_QWORD *)this + 65) + 8 * v46) = 0;
      SmsContainer::`scalar deleting destructor'((PVOID)i, v46);
      v4 = (int)v63;
      v3 = v62;
    }
  }
  if ( !v3 )
    return (unsigned int)v4;
LABEL_43:
  result = (unsigned int)v4;
  if ( (_BYTE)v64 )
    *((_BYTE *)this + 281) = 1;
  return result;
}

```

## disassembly

```asm
0x140045210  mov     [rsp-38h+arg_8], rbx
0x140045215  push    rbp
0x140045216  push    rsi
0x140045217  push    rdi
0x140045218  push    r12
0x14004521a  push    r13
0x14004521c  push    r14
0x14004521e  push    r15
0x140045220  mov     rbp, rsp
0x140045223  sub     rsp, 60h
0x140045227  movzx   r12d, byte ptr [r8+58h]
0x14004522c  xor     r10d, r10d
0x14004522f  mov     ebx, [r8+50h]
0x140045233  mov     r14, rdx
0x140045236  mov     r15d, [r8+54h]
0x14004523a  mov     rsi, rcx
0x14004523d  mov     dword ptr [rbp+arg_10], r10d
0x140045241  mov     byte ptr [rbp+arg_18], r10b
0x140045245  mov     [rbp+arg_0], r12b
0x140045249  nop     dword ptr [rax+00000000h]
0x140045250  xor     edi, edi
0x140045252  cmp     ebx, r15d
0x140045255  jnb     short loc_140045270
0x140045257  test    rdi, rdi
0x14004525a  jnz     short loc_140045270
0x14004525c  mov     rax, [rsi+208h]
0x140045263  mov     ecx, ebx
0x140045265  inc     ebx
0x140045267  mov     rdi, [rax+rcx*8]
0x14004526b  cmp     ebx, r15d
0x14004526e  jb      short loc_140045257
0x140045270  mov     [rbp+var_30], rdi
0x140045274  test    rdi, rdi
0x140045277  jz      loc_140045482
0x14004527d  mov     r13, [rdi+250h]
0x140045284  test    r12b, r12b
0x140045287  jnz     loc_1400453CF
0x14004528d  mov     rax, 400000000h
0x140045297  mov     byte ptr [rsp+60h+var_38], 1; char
0x14004529c  or      [r14], rax
0x14004529f  lea     r9, [rbp+var_30]; struct SmsContainer **
0x1400452a3  mov     r8, r13; unsigned __int64
0x1400452a6  mov     [rsp+60h+var_40], 0; struct _SmsContainerOverflowPinList *
0x1400452af  mov     rdx, r14; struct CmsTransactionContext *
0x1400452b2  mov     rcx, rsi; this
0x1400452b5  call    ?PinContainer@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@PEAU_SmsContainerOverflowPinList@@E@Z; CmsVolumeContainer::PinContainer(CmsTransactionContext *,unsigned __int64,SmsContainer * *,_SmsContainerOverflowPinList *,uchar)
0x1400452ba  mov     r10d, eax
0x1400452bd  mov     dword ptr [rbp+arg_10], eax
0x1400452c0  mov     rax, 0FFFFFFFBFFFFFFFFh
0x1400452ca  and     [r14], rax
0x1400452cd  test    r10d, r10d
0x1400452d0  js      loc_140045482
0x1400452d6  mov     rdi, [rbp+var_30]
0x1400452da  test    r12b, r12b
0x1400452dd  jz      loc_1400458BA
0x1400452e3  movzx   r12d, byte ptr [rdi+19h]
0x1400452e8  and     r12b, 10h
0x1400452ec  jnz     loc_140045614
0x1400452f2  mov     ecx, [rdi+264h]
0x1400452f8  bt      ecx, 0Dh
0x1400452fc  jb      loc_1400454A3
0x140045302  test    byte ptr [rdi+18h], 4
0x140045306  jnz     loc_1400454A3
0x14004530c  mov     eax, ecx
0x14004530e  and     eax, 2100h
0x140045313  cmp     eax, 2100h
0x140045318  jz      loc_14004587D
0x14004531e  test    byte ptr [rdi+18h], 40h
0x140045322  jnz     loc_1401F3016
0x140045328  test    byte ptr [rdi+18h], 1
0x14004532c  jnz     loc_1400454DF
0x140045332  xor     eax, eax
0x140045334  cmp     eax, 4
0x140045337  jnb     loc_140045753
0x14004533d  mov     rdi, [r14+rax*8+128h]
0x140045345  mov     ecx, eax
0x140045347  test    rdi, rdi
0x14004534a  jz      loc_1400454C6
0x140045350  cmp     [rdi+250h], r13
0x140045357  jnz     loc_1400454C6
0x14004535d  add     dword ptr [r14+rax*4+150h], 0FFFFFFFFh
0x140045366  movzx   r12d, [rbp+arg_0]
0x14004536b  jnz     loc_140045250
0x140045371  mov     qword ptr [r14+rcx*8+128h], 0
0x14004537d  lea     rcx, [rdi+78h]
0x140045381  mov     edx, 2
0x140045386  call    cs:__imp_ExReleasePushLockEx
0x14004538d  nop     dword ptr [rax+rax+00h]
0x140045392  dec     dword ptr [r14+164h]
0x140045399  lea     rcx, [rsi+1E8h]; RemoveLock
0x1400453a0  nop
0x1400453a1  xor     edx, edx; Tag
0x1400453a3  lock dec dword ptr [rdi+5Ch]
0x1400453a7  mov     r8d, 20h ; ' '; RemlockSize
0x1400453ad  nop
0x1400453ae  call    cs:__imp_IoReleaseRemoveLockEx
0x1400453b5  nop     dword ptr [rax+rax+00h]
0x1400453ba  dec     dword ptr [r14+160h]
0x1400453c1  mov     r10d, dword ptr [rbp+arg_10]
0x1400453c5  movzx   r12d, [rbp+arg_0]
0x1400453ca  jmp     loc_140045250
0x1400453cf  cmp     dword ptr [rdi+5Ch], 0
0x1400453d3  jnz     loc_14004528D
0x1400453d9  cmp     dword ptr [rdi+58h], 0
0x1400453dd  jnz     loc_14004528D
0x1400453e3  movzx   eax, byte ptr [rdi+18h]
0x1400453e7  test    al, 48h
0x1400453e9  jnz     loc_14004528D
0x1400453ef  cmp     dword ptr [rdi+70h], 0
0x1400453f3  jnz     loc_14004528D
0x1400453f9  cmp     dword ptr [rdi+74h], 0
0x1400453fd  jnz     loc_14004528D
0x140045403  test    al, 25h
0x140045405  jnz     loc_14004528D
0x14004540b  movzx   ecx, byte ptr [rdi+19h]
0x14004540f  test    cl, 8
0x140045412  jnz     loc_14004528D
0x140045418  test    dword ptr [rdi+264h], 201h
0x140045422  jnz     loc_14004528D
0x140045428  test    cl, 10h
0x14004542b  jnz     loc_14004528D
0x140045431  inc     dword ptr [rdi+60h]
0x140045434  cmp     dword ptr [rdi+60h], 0Ah
0x140045438  jl      loc_14004528D
0x14004543e  mov     edx, 2
0x140045443  lea     rcx, [rsi+38h]
0x140045447  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x14004544e  nop     dword ptr [rax+rax+00h]
0x140045453  cmp     dword ptr [rdi+5Ch], 0
0x140045457  jnz     short loc_140045463
0x140045459  cmp     dword ptr [rdi+58h], 0
0x14004545d  jz      loc_1400457A6
0x140045463  mov     edx, 2
0x140045468  lea     rcx, [rsi+38h]
0x14004546c  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x140045473  nop     dword ptr [rax+rax+00h]
0x140045478  movzx   r12d, [rbp+arg_0]
0x14004547d  jmp     loc_14004528D
0x140045482  test    r12b, r12b
0x140045485  jnz     short loc_1400454CD
0x140045487  mov     eax, r10d
0x14004548a  mov     rbx, [rsp+60h+arg_8]
0x140045492  add     rsp, 60h
0x140045496  pop     r15
0x140045498  pop     r14
0x14004549a  pop     r13
0x14004549c  pop     r12
0x14004549e  pop     rdi
0x14004549f  pop     rsi
0x1400454a0  pop     rbp
0x1400454a1  retn
0x1400454a3  test    cl, 8
0x1400454a6  jz      loc_14004530C
0x1400454ac  mov     eax, [rbp+arg_18]
0x1400454af  mov     edx, 1
0x1400454b4  cmp     dword ptr [rdi+58h], 0
0x1400454b8  movzx   eax, al
0x1400454bb  cmovz   eax, edx
0x1400454be  mov     [rbp+arg_18], eax
0x1400454c1  jmp     loc_14004530C
0x1400454c6  inc     eax
0x1400454c8  jmp     loc_140045334
0x1400454cd  cmp     byte ptr [rbp+arg_18], 0
0x1400454d1  mov     eax, r10d
0x1400454d4  jz      short loc_14004548A
0x1400454d6  mov     byte ptr [rsi+119h], 1
0x1400454dd  jmp     short loc_14004548A
0x1400454df  test    r12b, r12b
0x1400454e2  jz      loc_1401F30CF
0x1400454e8  test    byte ptr [rsi+300h], 40h
0x1400454ef  jnz     loc_1401F30CF
0x1400454f5  mov     dword ptr [rbp+var_30], 0
0x1400454fc  mov     [rbp+var_28], 0
0x140045503  mov     eax, [rdi+264h]
0x140045509  test    al, 8
0x14004550b  jnz     loc_14004589F
0x140045511  mov     eax, [rsi+78h]
0x140045514  lea     r12, [rsi+78h]
0x140045518  test    al, 8
0x14004551a  jz      loc_14004589F
0x140045520  mov     r8d, [rsi+18Ch]
0x140045527  lea     rax, [rbp+var_28]
0x14004552b  mov     rcx, [rsi+8]
0x14004552f  mov     rdx, r14
0x140045532  mov     [rbp+var_20], rax
0x140045536  lea     rax, [rbp+var_30]
0x14004553a  mov     [rbp+arg_10], rax
0x14004553e  lea     rax, [rbp+arg_10]
0x140045542  mov     [rbp+var_18], rax
0x140045546  lea     rax, [rbp+var_20]
0x14004554a  mov     rcx, [rcx+0D00h]
0x140045551  shl     r8d, 4
0x140045555  add     r8, 2A0h
0x14004555c  mov     [rbp+var_8], rax
0x140045560  lea     rax, [rbp+var_18]
0x140045564  add     r8, rdi
0x140045567  mov     [rsp+60h+var_40], rax
0x14004556c  mov     [rbp+var_10], r8
0x140045570  call    CmsAllocator__WalkAllocator__CmsAllocator__QueryContainerRangeAllocatedCount____2____lambda_1___
0x140045575  mov     dword ptr [rbp+arg_10], eax
0x140045578  mov     r10d, eax
0x14004557b  test    eax, eax
0x14004557d  jns     loc_140045894
0x140045583  xor     edx, edx
0x140045585  mov     eax, edx
0x140045587  cmp     eax, 4
0x14004558a  jnb     loc_1400457F0
0x140045590  mov     ecx, eax
0x140045592  mov     rbx, [r14+rcx*8+128h]
0x14004559a  test    rbx, rbx
0x14004559d  jz      loc_140045727
0x1400455a3  cmp     [rbx+250h], r13
0x1400455aa  jnz     loc_140045727
0x1400455b0  add     dword ptr [r14+rcx*4+150h], 0FFFFFFFFh
0x1400455b9  jnz     loc_1400454CD
0x1400455bf  mov     [r14+rcx*8+128h], rdx
0x1400455c7  lea     rcx, [rbx+78h]
0x1400455cb  mov     edx, 2
0x1400455d0  call    cs:__imp_ExReleasePushLockEx
0x1400455d7  nop     dword ptr [rax+rax+00h]
0x1400455dc  dec     dword ptr [r14+164h]
0x1400455e3  lea     rcx, [rsi+1E8h]; RemoveLock
0x1400455ea  nop
0x1400455eb  xor     edx, edx; Tag
0x1400455ed  lock dec dword ptr [rbx+5Ch]
0x1400455f1  mov     r8d, 20h ; ' '; RemlockSize
0x1400455f7  nop
0x1400455f8  call    cs:__imp_IoReleaseRemoveLockEx
0x1400455ff  nop     dword ptr [rax+rax+00h]
0x140045604  dec     dword ptr [r14+160h]
0x14004560b  mov     r10d, dword ptr [rbp+arg_10]
0x14004560f  jmp     loc_1400454CD
0x140045614  test    byte ptr [rdi+19h], 10h
0x140045618  mov     dword ptr [rbp+var_30], 0
0x14004561f  jz      loc_14004572E
0x140045625  mov     eax, [rdi+264h]
0x14004562b  test    al, 8
0x14004562d  jnz     loc_140045863
0x140045633  mov     eax, [rsi+78h]
0x140045636  test    al, 8
0x140045638  jz      loc_140045863
0x14004563e  mov     r8d, [rsi+18Ch]
0x140045645  lea     rax, [rbp+var_30]
0x140045649  mov     rcx, [rsi+8]
0x14004564d  mov     rdx, r14
0x140045650  mov     [rbp+arg_10], rax
0x140045654  lea     rax, [rbp+arg_10]
0x140045658  mov     [rbp+var_18], rax
0x14004565c  lea     rax, [rbp+var_28]
0x140045660  shl     r8d, 4
0x140045664  mov     rcx, [rcx+0D00h]
0x14004566b  add     r8, 2A0h
0x140045672  mov     [rbp+var_8], rax
0x140045676  add     r8, rdi
0x140045679  lea     rax, [rbp+var_18]
0x14004567d  mov     qword ptr [rbp+var_28], 0
0x140045685  mov     [rsp+60h+var_40], rax
0x14004568a  mov     [rbp+var_10], r8
0x14004568e  call    CmsAllocator__WalkAllocator__CmsAllocator__QueryContainerRangeAllocatedCount____2____lambda_1___
0x140045693  mov     dword ptr [rbp+arg_10], eax
0x140045696  mov     r10d, eax
0x140045699  mov     r9d, eax
0x14004569c  test    eax, eax
0x14004569e  js      short loc_1400456F4
0x1400456a0  mov     r8d, dword ptr [rbp+var_30]
0x1400456a4  mov     edx, [rdi+264h]
0x1400456aa  xor     eax, eax
0x1400456ac  test    r8d, r8d
0x1400456af  mov     r11d, 2000h
0x1400456b5  mov     ecx, edx
0x1400456b7  cmovz   eax, r11d
0x1400456bb  btr     ecx, 0Dh
0x1400456bf  or      ecx, eax
0x1400456c1  xor     eax, eax
0x1400456c3  cmp     r8d, [rdi+268h]
0x1400456ca  mov     r8d, 4000h
0x1400456d0  cmovz   eax, r8d
0x1400456d4  btr     ecx, 0Eh
0x1400456d8  or      ecx, eax
0x1400456da  mov     eax, edx
0x1400456dc  mov     [rdi+264h], ecx
0x1400456e2  xor     eax, ecx
0x1400456e4  and     byte ptr [rdi+19h], 0EFh
0x1400456e8  test    r11d, eax
0x1400456eb  jnz     short loc_140045717
0x1400456ed  xor     edx, ecx
0x1400456ef  test    r8d, edx
0x1400456f2  jnz     short loc_140045717
0x1400456f4  test    r10d, r10d
0x1400456f7  jns     loc_1400452F2
0x1400456fd  xor     r9d, r9d; struct _SmsContainerOverflowPinList *
0x140045700  mov     r8, r13; unsigned __int64
0x140045703  mov     rdx, r14; struct CmsTransactionContext *
0x140045706  mov     rcx, rsi; this
0x140045709  call    ?UnpinContainer@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@_KPEAU_SmsContainerOverflowPinList@@@Z; CmsVolumeContainer::UnpinContainer(CmsTransactionContext *,unsigned __int64,_SmsContainerOverflowPinList *)
0x14004570e  mov     r10d, dword ptr [rbp+arg_10]
0x140045712  jmp     loc_1400454CD
0x140045717  or      byte ptr [rdi+18h], 1
0x14004571b  mov     r10d, r9d
0x14004571e  mov     dword ptr [rbp+arg_10], r9d
  ... truncated ...
```
