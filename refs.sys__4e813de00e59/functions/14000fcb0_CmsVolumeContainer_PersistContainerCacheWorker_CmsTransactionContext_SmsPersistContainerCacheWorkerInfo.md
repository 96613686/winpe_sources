# CmsVolumeContainer::PersistContainerCacheWorker(CmsTransactionContext *,SmsPersistContainerCacheWorkerInfo *)

- ea: `0x14000fcb0`
- end: `0x1400103a4`
- name: `?PersistContainerCacheWorker@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@PEAUSmsPersistContainerCacheWorkerInfo@@@Z`
- size: `1780`
- prototype: `__int64 __fastcall(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, struct SmsPersistContainerCacheWorkerInfo *)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002ff00`
- `0x14005af00`

## callees

- `0x14000fcb0`
- `0x1400103b0`
- `0x140088db0`
- `0x1400a0dc4`
- `0x1400a0fb0`
- `0x1400a990c`
- `0x1400acde4`
- `0x1400ad170`
- `0x1400b0e8c`
- `0x1400d3578`
- `0x14013af8c`
- `0x1401695f4`
- `0x14017c5f8`
- `0x1401f4100`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x14000fee7`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x14000fee7`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14000ff0c`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401f8a82`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14000ff0c`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401f8a82`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1401f8a6d`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1401f8a6d`
- `ntoskrnl!RtlIsZeroMemory` at `0x1401f8ba2`
- `ntoskrnl!RtlIsZeroMemory` at `0x1401f8ba2`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000fe4e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140010098`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000fe4e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140010098`
- `ntoskrnl!ExReleasePushLockEx` at `0x14000fe26`
- `ntoskrnl!ExReleasePushLockEx` at `0x140010070`
- `ntoskrnl!ExReleasePushLockEx` at `0x14000fe26`
- `ntoskrnl!ExReleasePushLockEx` at `0x140010070`

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
  BOOL v12; // r9d
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
  __int64 v26; // rcx
  unsigned int j; // eax
  __int64 v28; // rbx
  int v29; // r8d
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // r8d
  int v33; // edx
  int v34; // eax
  unsigned int v35; // ecx
  int v36; // eax
  unsigned int v37; // ecx
  __int64 *n; // rcx
  char v39; // al
  char v40; // cl
  __int64 *k; // rcx
  char v42; // al
  unsigned int v43; // ecx
  unsigned int v44; // eax
  __int64 v45; // rdx
  __int64 v46; // r8
  char *v47; // rcx
  int v48; // eax
  __int64 v49; // rcx
  CmsAllocator *v50; // rcx
  __int64 v51; // rax
  CmsAllocator *v52; // rcx
  SmsAllocationRegionEx *v53; // r12
  CmsAllocator *v54; // rcx
  SmsAllocationRegionEx *v55; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v56[2]; // [rsp+38h] [rbp-28h] BYREF
  struct _RANGE *v57; // [rsp+40h] [rbp-20h] BYREF
  SmsAllocationRegionEx ***v58; // [rsp+48h] [rbp-18h] BYREF
  char *v59; // [rsp+50h] [rbp-10h]
  void *v60; // [rsp+58h] [rbp-8h]
  char v61; // [rsp+A0h] [rbp+40h]
  SmsAllocationRegionEx **v62; // [rsp+B0h] [rbp+50h] BYREF
  int v63; // [rsp+B8h] [rbp+58h]

  v3 = *((_BYTE *)a3 + 88);
  v4 = 0;
  v5 = *((_DWORD *)a3 + 20);
  v7 = *((_DWORD *)a3 + 21);
  LODWORD(v62) = 0;
  LOBYTE(v63) = 0;
  v61 = v3;
  while ( 1 )
  {
LABEL_2:
    for ( i = 0; v5 < v7; i = *(_QWORD *)(*((_QWORD *)this + 64) + 8 * v10) )
    {
      if ( i )
        break;
      v10 = v5++;
    }
    v55 = (SmsAllocationRegionEx *)i;
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
      || (v39 = *(_BYTE *)(i + 24), (v39 & 0x48) != 0)
      || *(_DWORD *)(i + 112)
      || *(_DWORD *)(i + 116)
      || (v39 & 0x25) != 0
      || (v40 = *(_BYTE *)(i + 25), (v40 & 8) != 0)
      || (*(_DWORD *)(i + 612) & 0x201) != 0
      || (v40 & 0x10) != 0 )
    {
      ExReleaseAutoExpandPushLockExclusive((char *)this + 56, 2);
      v3 = v61;
LABEL_7:
      *(_QWORD *)a2 |= 0x400000000uLL;
      v4 = CmsVolumeContainer::PinContainer(this, a2, v11, &v55, 0, 1);
      LODWORD(v62) = v4;
      *(_QWORD *)a2 &= ~0x400000000uLL;
      if ( v4 < 0 )
        break;
      v13 = v55;
      if ( v3 )
      {
        v14 = *((_BYTE *)v55 + 25) & 0x10;
        if ( v14 )
        {
          LODWORD(v55) = 0;
          if ( (*((_DWORD *)v13 + 153) & 8) != 0 || (*((_DWORD *)this + 30) & 8) == 0 )
          {
            v32 = *((_DWORD *)v13 + 156);
            v4 = 0;
            LODWORD(v62) = 0;
            v12 = 0;
            LODWORD(v55) = v32;
          }
          else
          {
            v29 = *((_DWORD *)this + 97);
            v30 = *((_QWORD *)this + 1);
            v62 = &v55;
            v58 = &v62;
            v31 = *(_QWORD *)(v30 + 3264);
            v60 = v56;
            *(_QWORD *)v56 = 0;
            v59 = (char *)v13 + (unsigned int)(16 * v29) + 672;
            LODWORD(v62) = CmsAllocator::WalkAllocator__CmsAllocator::QueryContainerRangeAllocatedCount_::_2_::_lambda_1___(
                             v31,
                             (_DWORD)a2,
                             (_DWORD)v59,
                             v12,
                             (__int64)&v58);
            v4 = (int)v62;
            v12 = (int)v62;
            if ( (int)v62 < 0 )
              goto LABEL_67;
            v32 = (int)v55;
          }
          v33 = *((_DWORD *)v13 + 153);
          v34 = 0;
          if ( !v32 )
            v34 = 0x2000;
          v35 = v34 | *((_DWORD *)v13 + 153) & 0xFFFFDFFF;
          v36 = 0;
          if ( v32 == *((_DWORD *)v13 + 154) )
            v36 = 0x4000;
          v37 = v36 | v35 & 0xFFFFBFFF;
          *((_DWORD *)v13 + 153) = v37;
          *((_BYTE *)v13 + 25) &= ~0x10u;
          if ( (((unsigned __int16)v37 ^ (unsigned __int16)v33) & 0x2000) == 0
            && (((unsigned __int16)v37 ^ (unsigned __int16)v33) & 0x4000) == 0 )
          {
LABEL_67:
            if ( v4 < 0 )
            {
              CmsVolumeContainer::UnpinContainer(this, a2, v11, 0);
              v4 = (int)v62;
              goto LABEL_43;
            }
            goto LABEL_10;
          }
          *((_BYTE *)v13 + 24) |= 1u;
          v4 = v12;
          LODWORD(v62) = v12;
        }
LABEL_10:
        v15 = *((_DWORD *)v13 + 153);
        if ( ((v15 & 0x2000) != 0 || (*((_BYTE *)v13 + 24) & 4) != 0) && (v15 & 8) != 0 )
        {
          v22 = (unsigned __int8)v63;
          if ( !*((_DWORD *)v13 + 22) )
            v22 = 1;
          v63 = v22;
        }
        if ( (v15 & 0x2100) == 0x2100 )
        {
          v42 = v63;
          if ( (v15 & 8) == 0 )
            v42 = 1;
          LOBYTE(v63) = v42;
        }
        if ( (*((_BYTE *)v13 + 24) & 0x40) != 0 && *((_QWORD *)v13 + 5) <= *(_QWORD *)(*((_QWORD *)this + 1) + 2064LL) )
        {
          *((_DWORD *)v13 + 163) = 0;
          *((_BYTE *)v13 + 24) = *((_BYTE *)v13 + 24) & 0xBE | 1;
          v46 = *(_QWORD *)(*((_QWORD *)this + 1) + 2064LL);
          v47 = (char *)v13
              + 24 * (((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)v13 + 44, 1u) + 1) & 0xF);
          *((_DWORD *)v47 + 46) = 12;
          *((_QWORD *)v47 + 24) = v46;
          *((_QWORD *)v47 + 25) = 0;
          _InterlockedDecrement((volatile signed __int32 *)this + 114);
          _InterlockedAdd64(
            (volatile signed __int64 *)(*((_QWORD *)this + 1) + 3824LL),
            *(unsigned int *)(*((_QWORD *)this + 1) + 84LL));
          _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)this + 1) + 3840LL));
          _InterlockedAdd64(
            (volatile signed __int64 *)(*((_QWORD *)this + 1) + 3848LL),
            -*(_DWORD *)(*((_QWORD *)this + 1) + 84LL));
        }
        if ( (*((_BYTE *)v13 + 24) & 1) != 0 )
        {
          if ( v14 && (*((_BYTE *)this + 760) & 0x40) == 0 )
          {
            LODWORD(v55) = 0;
            v56[0] = 0;
            if ( (*((_DWORD *)v13 + 153) & 8) != 0
              || (v23 = (_DWORD *)((char *)this + 120), (*((_DWORD *)this + 30) & 8) == 0) )
            {
              v43 = *((_DWORD *)v13 + 156);
              v23 = (_DWORD *)((char *)this + 120);
              LODWORD(v55) = v43;
              v44 = *((_DWORD *)v13 + 158);
              v56[0] = v44;
            }
            else
            {
              v24 = *((_DWORD *)this + 97);
              v25 = *((_QWORD *)this + 1);
              v57 = (struct _RANGE *)v56;
              v62 = &v55;
              v58 = &v62;
              v26 = *(_QWORD *)(v25 + 3264);
              v60 = &v57;
              v59 = (char *)v13 + (unsigned int)(16 * v24) + 672;
              LODWORD(v62) = CmsAllocator::WalkAllocator__CmsAllocator::QueryContainerRangeAllocatedCount_::_2_::_lambda_1___(
                               v26,
                               (_DWORD)a2,
                               (_DWORD)v59,
                               v12,
                               (__int64)&v58);
              v4 = (int)v62;
              if ( (int)v62 < 0 )
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
                IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)this + 15, 0, 0x20u);
                --*((_DWORD *)a2 + 88);
                v4 = (int)v62;
                goto LABEL_43;
              }
              v43 = (unsigned int)v55;
              v44 = v56[0];
            }
            if ( v43 < v44
              && ((*((_DWORD *)v13 + 153) & 8) != 0 || (*v23 & 8) == 0)
              && (*((_DWORD *)v13 + 153) & 8) == 0 )
            {
              *((_DWORD *)v13 + 158) = v43;
            }
          }
          if ( (*((_DWORD *)v13 + 153) & 0x2008) == 0x2000
            && *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 1) + 3280LL) + 16LL)
            && !(unsigned __int8)RtlIsZeroMemory((char *)v13 + 672, (unsigned int)(16 * *((_DWORD *)this + 97))) )
          {
            *((_DWORD *)v13 + 153) |= 0x100u;
            LOBYTE(v63) = 1;
          }
          if ( (*((_BYTE *)v13 + 24) & 2) != 0 )
          {
            LODWORD(v62) = CmsVolumeContainer::PersistNewContainer(this, a2, v13);
            CmsVolumeContainer::UnpinContainer(this, a2, v11, 0);
            v4 = (int)v62;
          }
          else
          {
            CmsVolumeContainer::UnpinContainer(this, a2, v11, 0);
            LODWORD(v62) = CmsVolumeContainer::PersistContainer(this, a2, v11);
            v4 = (int)v62;
            if ( (int)v62 < 0 )
              goto LABEL_43;
          }
          v3 = v61;
          if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 1) + 3280LL) + 16LL) && (*((_DWORD *)v13 + 153) & 8) == 0 )
          {
            memmove(*((void **)v13 + 71), (char *)v13 + 672, (unsigned int)(16 * *((_DWORD *)this + 97)));
            v4 = (int)v62;
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
                    v3 = v61;
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
          v3 = v61;
          if ( !v18 )
            continue;
          *((_QWORD *)a2 + (unsigned int)m + 37) = 0;
LABEL_21:
          ExReleasePushLockEx(v17 + 120, 2);
          --*((_DWORD *)a2 + 89);
          _InterlockedDecrement((volatile signed __int32 *)(v17 + 92));
          IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)this + 15, 0, 0x20u);
          --*((_DWORD *)a2 + 88);
          v4 = (int)v62;
          v3 = v61;
        }
      }
      else
      {
        v56[0] = 0;
        LODWORD(v62) = CmsVolumeContainer::GetNumAllocatedForContainerEntry(
                         this,
                         a2,
                         (SmsAllocationRegionEx *)((char *)v55 + 592),
                         v12,
                         v56,
                         0);
        if ( (int)v62 < 0 )
        {
          CmsVolumeContainer::UnpinContainer(this, a2, v11, 0);
          return (unsigned int)v62;
        }
        if ( v56[0] && (*((_BYTE *)v13 + 24) & 4) == 0
          || (*((_DWORD *)v13 + 153) & 8) == 0
          || *((_DWORD *)v13 + 22)
          || (*(_DWORD *)(*((_QWORD *)this + 1) + 3396LL) & 0x8000) != 0 )
        {
          v48 = *((_DWORD *)v13 + 153);
          if ( (v48 & 0x100) != 0 && !v56[0] && (v48 & 8) == 0 )
          {
            v49 = *((_QWORD *)this + 1);
            if ( *(_BYTE *)(*(_QWORD *)(v49 + 3280) + 16LL) )
            {
              v50 = *(CmsAllocator **)(v49 + 3264);
              v51 = (unsigned int)(16 * *((_DWORD *)this + 97)) + 672LL;
              v55 = 0;
              v57 = (SmsAllocationRegionEx *)((char *)v13 + v51);
              if ( (int)CmsAllocator::PinBitmapRegion(v50, a2, (SmsAllocationRegionEx *)((char *)v13 + v51), &v55) >= 0 )
              {
                v53 = v55;
                if ( CmsAllocator::TryProtectRegion(v52, v55, 1) >= 0 )
                {
                  if ( !SmsAllocationRegionEx::GetTotalAllocated(v53)
                    && (int)CmsIntegrityState::ResetIntegrityState(
                              *(CmsIntegrityState **)(*((_QWORD *)this + 1) + 3280LL),
                              a2,
                              v57) >= 0 )
                  {
                    memset((char *)v13 + 672, 0, (unsigned int)(16 * *((_DWORD *)this + 97)));
                    *((_DWORD *)v13 + 153) &= ~0x100u;
                    *((_BYTE *)v13 + 24) |= 1u;
                  }
                  CmsAllocator::TryProtectRegion(v54, v53, 0);
                }
                v3 = v61;
              }
            }
          }
          CmsVolumeContainer::UnpinContainer(this, a2, v11, 0);
          v4 = (int)v62;
        }
        else
        {
          CmsVolumeContainer::UnpinContainer(this, a2, v11, 0);
          CmsVolumeContainer::DeleteContainer(this, a2, v11);
          v4 = (int)v62;
        }
      }
    }
    else
    {
      RtlRemoveEntryHashTable(*((PRTL_DYNAMIC_HASH_TABLE *)this + 6), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)i, 0);
      ExReleaseAutoExpandPushLockExclusive((char *)this + 56, 2);
      v45 = v5 - 1;
      *(_QWORD *)(*((_QWORD *)this + 64) + 8 * v45) = 0;
      SmsContainer::`scalar deleting destructor'((PVOID)i, v45);
      v4 = (int)v62;
      v3 = v61;
    }
  }
  if ( !v3 )
    return (unsigned int)v4;
LABEL_43:
  result = (unsigned int)v4;
  if ( (_BYTE)v63 )
    *((_BYTE *)this + 281) = 1;
  return result;
}

```

## disassembly

```asm
0x14000fcb0  mov     [rsp-38h+arg_8], rbx
0x14000fcb5  push    rbp
0x14000fcb6  push    rsi
0x14000fcb7  push    rdi
0x14000fcb8  push    r12
0x14000fcba  push    r13
0x14000fcbc  push    r14
0x14000fcbe  push    r15
0x14000fcc0  mov     rbp, rsp
0x14000fcc3  sub     rsp, 60h
0x14000fcc7  movzx   r12d, byte ptr [r8+58h]
0x14000fccc  xor     r10d, r10d
0x14000fccf  mov     ebx, [r8+50h]
0x14000fcd3  mov     r14, rdx
0x14000fcd6  mov     r15d, [r8+54h]
0x14000fcda  mov     rsi, rcx
0x14000fcdd  mov     dword ptr [rbp+arg_10], r10d
0x14000fce1  mov     byte ptr [rbp+arg_18], r10b
0x14000fce5  mov     [rbp+arg_0], r12b
0x14000fce9  nop     dword ptr [rax+00000000h]
0x14000fcf0  xor     edi, edi
0x14000fcf2  cmp     ebx, r15d
0x14000fcf5  jnb     short loc_14000FD10
0x14000fcf7  test    rdi, rdi
0x14000fcfa  jnz     short loc_14000FD10
0x14000fcfc  mov     rax, [rsi+200h]
0x14000fd03  mov     ecx, ebx
0x14000fd05  inc     ebx
0x14000fd07  mov     rdi, [rax+rcx*8]
0x14000fd0b  cmp     ebx, r15d
0x14000fd0e  jb      short loc_14000FCF7
0x14000fd10  mov     [rbp+var_30], rdi
0x14000fd14  test    rdi, rdi
0x14000fd17  jz      loc_14000FF22
0x14000fd1d  mov     r13, [rdi+250h]
0x14000fd24  test    r12b, r12b
0x14000fd27  jnz     loc_14000FE6F
0x14000fd2d  mov     rax, 400000000h
0x14000fd37  mov     byte ptr [rsp+60h+var_38], 1; char
0x14000fd3c  or      [r14], rax
0x14000fd3f  lea     r9, [rbp+var_30]; struct SmsContainer **
0x14000fd43  mov     r8, r13; unsigned __int64
0x14000fd46  mov     [rsp+60h+var_40], 0; struct _SmsContainerOverflowPinList *
0x14000fd4f  mov     rdx, r14; struct CmsTransactionContext *
0x14000fd52  mov     rcx, rsi; this
0x14000fd55  call    ?PinContainer@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@PEAU_SmsContainerOverflowPinList@@E@Z; CmsVolumeContainer::PinContainer(CmsTransactionContext *,unsigned __int64,SmsContainer * *,_SmsContainerOverflowPinList *,uchar)
0x14000fd5a  mov     r10d, eax
0x14000fd5d  mov     dword ptr [rbp+arg_10], eax
0x14000fd60  mov     rax, 0FFFFFFFBFFFFFFFFh
0x14000fd6a  and     [r14], rax
0x14000fd6d  test    r10d, r10d
0x14000fd70  js      loc_14000FF22
0x14000fd76  mov     rdi, [rbp+var_30]
0x14000fd7a  test    r12b, r12b
0x14000fd7d  jz      loc_14001035A
0x14000fd83  movzx   r12d, byte ptr [rdi+19h]
0x14000fd88  and     r12b, 10h
0x14000fd8c  jnz     loc_1400100B4
0x14000fd92  mov     ecx, [rdi+264h]
0x14000fd98  bt      ecx, 0Dh
0x14000fd9c  jb      loc_14000FF43
0x14000fda2  test    byte ptr [rdi+18h], 4
0x14000fda6  jnz     loc_14000FF43
0x14000fdac  mov     eax, ecx
0x14000fdae  and     eax, 2100h
0x14000fdb3  cmp     eax, 2100h
0x14000fdb8  jz      loc_14001031D
0x14000fdbe  test    byte ptr [rdi+18h], 40h
0x14000fdc2  jnz     loc_1401F8AB6
0x14000fdc8  test    byte ptr [rdi+18h], 1
0x14000fdcc  jnz     loc_14000FF7F
0x14000fdd2  xor     eax, eax
0x14000fdd4  cmp     eax, 4
0x14000fdd7  jnb     loc_1400101F3
0x14000fddd  mov     rdi, [r14+rax*8+128h]
0x14000fde5  mov     ecx, eax
0x14000fde7  test    rdi, rdi
0x14000fdea  jz      loc_14000FF66
0x14000fdf0  cmp     [rdi+250h], r13
0x14000fdf7  jnz     loc_14000FF66
0x14000fdfd  add     dword ptr [r14+rax*4+150h], 0FFFFFFFFh
0x14000fe06  movzx   r12d, [rbp+arg_0]
0x14000fe0b  jnz     loc_14000FCF0
0x14000fe11  mov     qword ptr [r14+rcx*8+128h], 0
0x14000fe1d  lea     rcx, [rdi+78h]
0x14000fe21  mov     edx, 2
0x14000fe26  call    cs:__imp_ExReleasePushLockEx
0x14000fe2d  nop     dword ptr [rax+rax+00h]
0x14000fe32  dec     dword ptr [r14+164h]
0x14000fe39  lea     rcx, [rsi+1E0h]; RemoveLock
0x14000fe40  nop
0x14000fe41  xor     edx, edx; Tag
0x14000fe43  lock dec dword ptr [rdi+5Ch]
0x14000fe47  mov     r8d, 20h ; ' '; RemlockSize
0x14000fe4d  nop
0x14000fe4e  call    cs:__imp_IoReleaseRemoveLockEx
0x14000fe55  nop     dword ptr [rax+rax+00h]
0x14000fe5a  dec     dword ptr [r14+160h]
0x14000fe61  mov     r10d, dword ptr [rbp+arg_10]
0x14000fe65  movzx   r12d, [rbp+arg_0]
0x14000fe6a  jmp     loc_14000FCF0
0x14000fe6f  cmp     dword ptr [rdi+5Ch], 0
0x14000fe73  jnz     loc_14000FD2D
0x14000fe79  cmp     dword ptr [rdi+58h], 0
0x14000fe7d  jnz     loc_14000FD2D
0x14000fe83  movzx   eax, byte ptr [rdi+18h]
0x14000fe87  test    al, 48h
0x14000fe89  jnz     loc_14000FD2D
0x14000fe8f  cmp     dword ptr [rdi+70h], 0
0x14000fe93  jnz     loc_14000FD2D
0x14000fe99  cmp     dword ptr [rdi+74h], 0
0x14000fe9d  jnz     loc_14000FD2D
0x14000fea3  test    al, 25h
0x14000fea5  jnz     loc_14000FD2D
0x14000feab  movzx   ecx, byte ptr [rdi+19h]
0x14000feaf  test    cl, 8
0x14000feb2  jnz     loc_14000FD2D
0x14000feb8  test    dword ptr [rdi+264h], 201h
0x14000fec2  jnz     loc_14000FD2D
0x14000fec8  test    cl, 10h
0x14000fecb  jnz     loc_14000FD2D
0x14000fed1  inc     dword ptr [rdi+60h]
0x14000fed4  cmp     dword ptr [rdi+60h], 0Ah
0x14000fed8  jl      loc_14000FD2D
0x14000fede  mov     edx, 2
0x14000fee3  lea     rcx, [rsi+38h]
0x14000fee7  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x14000feee  nop     dword ptr [rax+rax+00h]
0x14000fef3  cmp     dword ptr [rdi+5Ch], 0
0x14000fef7  jnz     short loc_14000FF03
0x14000fef9  cmp     dword ptr [rdi+58h], 0
0x14000fefd  jz      loc_140010246
0x14000ff03  mov     edx, 2
0x14000ff08  lea     rcx, [rsi+38h]
0x14000ff0c  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x14000ff13  nop     dword ptr [rax+rax+00h]
0x14000ff18  movzx   r12d, [rbp+arg_0]
0x14000ff1d  jmp     loc_14000FD2D
0x14000ff22  test    r12b, r12b
0x14000ff25  jnz     short loc_14000FF6D
0x14000ff27  mov     eax, r10d
0x14000ff2a  mov     rbx, [rsp+60h+arg_8]
0x14000ff32  add     rsp, 60h
0x14000ff36  pop     r15
0x14000ff38  pop     r14
0x14000ff3a  pop     r13
0x14000ff3c  pop     r12
0x14000ff3e  pop     rdi
0x14000ff3f  pop     rsi
0x14000ff40  pop     rbp
0x14000ff41  retn
0x14000ff43  test    cl, 8
0x14000ff46  jz      loc_14000FDAC
0x14000ff4c  mov     eax, [rbp+arg_18]
0x14000ff4f  mov     edx, 1
0x14000ff54  cmp     dword ptr [rdi+58h], 0
0x14000ff58  movzx   eax, al
0x14000ff5b  cmovz   eax, edx
0x14000ff5e  mov     [rbp+arg_18], eax
0x14000ff61  jmp     loc_14000FDAC
0x14000ff66  inc     eax
0x14000ff68  jmp     loc_14000FDD4
0x14000ff6d  cmp     byte ptr [rbp+arg_18], 0
0x14000ff71  mov     eax, r10d
0x14000ff74  jz      short loc_14000FF2A
0x14000ff76  mov     byte ptr [rsi+119h], 1
0x14000ff7d  jmp     short loc_14000FF2A
0x14000ff7f  test    r12b, r12b
0x14000ff82  jz      loc_1401F8B6F
0x14000ff88  test    byte ptr [rsi+2F8h], 40h
0x14000ff8f  jnz     loc_1401F8B6F
0x14000ff95  mov     dword ptr [rbp+var_30], 0
0x14000ff9c  mov     [rbp+var_28], 0
0x14000ffa3  mov     eax, [rdi+264h]
0x14000ffa9  test    al, 8
0x14000ffab  jnz     loc_14001033F
0x14000ffb1  mov     eax, [rsi+78h]
0x14000ffb4  lea     r12, [rsi+78h]
0x14000ffb8  test    al, 8
0x14000ffba  jz      loc_14001033F
0x14000ffc0  mov     r8d, [rsi+184h]
0x14000ffc7  lea     rax, [rbp+var_28]
0x14000ffcb  mov     rcx, [rsi+8]
0x14000ffcf  mov     rdx, r14
0x14000ffd2  mov     [rbp+var_20], rax
0x14000ffd6  lea     rax, [rbp+var_30]
0x14000ffda  mov     [rbp+arg_10], rax
0x14000ffde  lea     rax, [rbp+arg_10]
0x14000ffe2  mov     [rbp+var_18], rax
0x14000ffe6  lea     rax, [rbp+var_20]
0x14000ffea  mov     rcx, [rcx+0CC0h]
0x14000fff1  shl     r8d, 4
0x14000fff5  add     r8, 2A0h
0x14000fffc  mov     [rbp+var_8], rax
0x140010000  lea     rax, [rbp+var_18]
0x140010004  add     r8, rdi
0x140010007  mov     [rsp+60h+var_40], rax
0x14001000c  mov     [rbp+var_10], r8
0x140010010  call    CmsAllocator__WalkAllocator__CmsAllocator__QueryContainerRangeAllocatedCount____2____lambda_1___
0x140010015  mov     dword ptr [rbp+arg_10], eax
0x140010018  mov     r10d, eax
0x14001001b  test    eax, eax
0x14001001d  jns     loc_140010334
0x140010023  xor     edx, edx
0x140010025  mov     eax, edx
0x140010027  cmp     eax, 4
0x14001002a  jnb     loc_140010290
0x140010030  mov     ecx, eax
0x140010032  mov     rbx, [r14+rcx*8+128h]
0x14001003a  test    rbx, rbx
0x14001003d  jz      loc_1400101C7
0x140010043  cmp     [rbx+250h], r13
0x14001004a  jnz     loc_1400101C7
0x140010050  add     dword ptr [r14+rcx*4+150h], 0FFFFFFFFh
0x140010059  jnz     loc_14000FF6D
0x14001005f  mov     [r14+rcx*8+128h], rdx
0x140010067  lea     rcx, [rbx+78h]
0x14001006b  mov     edx, 2
0x140010070  call    cs:__imp_ExReleasePushLockEx
0x140010077  nop     dword ptr [rax+rax+00h]
0x14001007c  dec     dword ptr [r14+164h]
0x140010083  lea     rcx, [rsi+1E0h]; RemoveLock
0x14001008a  nop
0x14001008b  xor     edx, edx; Tag
0x14001008d  lock dec dword ptr [rbx+5Ch]
0x140010091  mov     r8d, 20h ; ' '; RemlockSize
0x140010097  nop
0x140010098  call    cs:__imp_IoReleaseRemoveLockEx
0x14001009f  nop     dword ptr [rax+rax+00h]
0x1400100a4  dec     dword ptr [r14+160h]
0x1400100ab  mov     r10d, dword ptr [rbp+arg_10]
0x1400100af  jmp     loc_14000FF6D
0x1400100b4  test    byte ptr [rdi+19h], 10h
0x1400100b8  mov     dword ptr [rbp+var_30], 0
0x1400100bf  jz      loc_1400101CE
0x1400100c5  mov     eax, [rdi+264h]
0x1400100cb  test    al, 8
0x1400100cd  jnz     loc_140010303
0x1400100d3  mov     eax, [rsi+78h]
0x1400100d6  test    al, 8
0x1400100d8  jz      loc_140010303
0x1400100de  mov     r8d, [rsi+184h]
0x1400100e5  lea     rax, [rbp+var_30]
0x1400100e9  mov     rcx, [rsi+8]
0x1400100ed  mov     rdx, r14
0x1400100f0  mov     [rbp+arg_10], rax
0x1400100f4  lea     rax, [rbp+arg_10]
0x1400100f8  mov     [rbp+var_18], rax
0x1400100fc  lea     rax, [rbp+var_28]
0x140010100  shl     r8d, 4
0x140010104  mov     rcx, [rcx+0CC0h]
0x14001010b  add     r8, 2A0h
0x140010112  mov     [rbp+var_8], rax
0x140010116  add     r8, rdi
0x140010119  lea     rax, [rbp+var_18]
0x14001011d  mov     qword ptr [rbp+var_28], 0
0x140010125  mov     [rsp+60h+var_40], rax
0x14001012a  mov     [rbp+var_10], r8
0x14001012e  call    CmsAllocator__WalkAllocator__CmsAllocator__QueryContainerRangeAllocatedCount____2____lambda_1___
0x140010133  mov     dword ptr [rbp+arg_10], eax
0x140010136  mov     r10d, eax
0x140010139  mov     r9d, eax
0x14001013c  test    eax, eax
0x14001013e  js      short loc_140010194
0x140010140  mov     r8d, dword ptr [rbp+var_30]
0x140010144  mov     edx, [rdi+264h]
0x14001014a  xor     eax, eax
0x14001014c  test    r8d, r8d
0x14001014f  mov     r11d, 2000h
0x140010155  mov     ecx, edx
0x140010157  cmovz   eax, r11d
0x14001015b  btr     ecx, 0Dh
0x14001015f  or      ecx, eax
0x140010161  xor     eax, eax
0x140010163  cmp     r8d, [rdi+268h]
0x14001016a  mov     r8d, 4000h
0x140010170  cmovz   eax, r8d
0x140010174  btr     ecx, 0Eh
0x140010178  or      ecx, eax
0x14001017a  mov     eax, edx
0x14001017c  mov     [rdi+264h], ecx
0x140010182  xor     eax, ecx
0x140010184  and     byte ptr [rdi+19h], 0EFh
0x140010188  test    r11d, eax
0x14001018b  jnz     short loc_1400101B7
0x14001018d  xor     edx, ecx
0x14001018f  test    r8d, edx
0x140010192  jnz     short loc_1400101B7
0x140010194  test    r10d, r10d
0x140010197  jns     loc_14000FD92
0x14001019d  xor     r9d, r9d; struct _SmsContainerOverflowPinList *
0x1400101a0  mov     r8, r13; unsigned __int64
0x1400101a3  mov     rdx, r14; struct CmsTransactionContext *
0x1400101a6  mov     rcx, rsi; this
0x1400101a9  call    ?UnpinContainer@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@_KPEAU_SmsContainerOverflowPinList@@@Z; CmsVolumeContainer::UnpinContainer(CmsTransactionContext *,unsigned __int64,_SmsContainerOverflowPinList *)
0x1400101ae  mov     r10d, dword ptr [rbp+arg_10]
0x1400101b2  jmp     loc_14000FF6D
0x1400101b7  or      byte ptr [rdi+18h], 1
0x1400101bb  mov     r10d, r9d
0x1400101be  mov     dword ptr [rbp+arg_10], r9d
  ... truncated ...
```
