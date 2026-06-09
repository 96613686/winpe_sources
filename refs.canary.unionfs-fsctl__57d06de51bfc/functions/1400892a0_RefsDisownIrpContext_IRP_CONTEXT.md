# RefsDisownIrpContext(_IRP_CONTEXT *)

- ea: `0x1400892a0`
- end: `0x140089b3f`
- name: `?RefsDisownIrpContext@@YAXPEAU_IRP_CONTEXT@@@Z`
- size: `2207`
- prototype: `void __fastcall(struct _IRP_CONTEXT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140326920`
- `0x14032ae48`

## callees

- `0x1400892a0`
- `0x1400c8644`
- `0x140320020`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140089453`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140089473`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140089516`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140089453`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140089473`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140089516`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14008948c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14008948c`
- `ntoskrnl!KeSetEvent` at `0x14008978f`
- `ntoskrnl!KeSetEvent` at `0x14008978f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008970c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140089956`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008970c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140089956`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140089655`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140089744`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140089899`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140089655`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140089744`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140089899`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140089664`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140089753`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400898a8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140089664`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140089753`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400898a8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400896a2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14008979f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400898e6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400896a2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14008979f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400898e6`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400896ae`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400897ab`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400898f2`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400896ae`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400897ab`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400898f2`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140089550`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140089550`
- `ntoskrnl!ExReleaseFastResource` at `0x140089573`
- `ntoskrnl!ExReleaseFastResource` at `0x1400895d2`
- `ntoskrnl!ExReleaseFastResource` at `0x140089822`
- `ntoskrnl!ExReleaseFastResource` at `0x140089ad4`
- `ntoskrnl!ExReleaseFastResource` at `0x140089573`
- `ntoskrnl!ExReleaseFastResource` at `0x1400895d2`
- `ntoskrnl!ExReleaseFastResource` at `0x140089822`
- `ntoskrnl!ExReleaseFastResource` at `0x140089ad4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140089984`
- `ntoskrnl!ExReleaseResourceLite` at `0x140089af3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140089984`
- `ntoskrnl!ExReleaseResourceLite` at `0x140089af3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400894fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400894fd`

## pseudocode

```c
void __fastcall RefsDisownIrpContext(struct _IRP_CONTEXT *a1)
{
  __int64 v2; // rsi
  char *v3; // r10
  int v4; // eax
  struct _IRP_CONTEXT *v5; // rbx
  __int16 v6; // r13
  char *v7; // rbp
  struct _IRP_CONTEXT *v8; // r12
  __int64 v9; // rax
  __int16 v10; // r8
  struct _IRP_CONTEXT *v11; // r15
  struct _IRP_CONTEXT *v12; // rax
  char *v13; // r13
  char *v14; // r15
  char *v15; // rsi
  struct _KTHREAD *CurrentThread; // r9
  __int64 v17; // r8
  unsigned int i; // edx
  __int64 v19; // rcx
  _QWORD *v20; // rax
  struct _IRP_CONTEXT *v21; // rsi
  struct _IRP_CONTEXT *v22; // rax
  _QWORD *v23; // rbp
  __int64 v24; // rax
  _QWORD **v25; // rbx
  _QWORD *v26; // rcx
  unsigned __int64 v27; // rax
  PIRP TopLevelIrp; // rax
  IRP *MdlAddress; // rcx
  _QWORD *v30; // rax
  struct _IRP_CONTEXT *j; // rcx
  char IsFastResourceHeldExclusive; // al
  struct _ERESOURCE *v33; // rcx
  bool v34; // zf
  int v35; // ecx
  struct _IRP_CONTEXT **v36; // r15
  _QWORD *v37; // r12
  __int64 v38; // rcx
  struct _FAST_MUTEX *v39; // rbx
  struct _IRP_CONTEXT *v40; // rax
  struct _IRP_CONTEXT **v41; // rcx
  unsigned int v42; // eax
  struct _FAST_MUTEX *v43; // rbx
  _QWORD *v44; // rcx
  _QWORD *v45; // rcx
  __int64 v46; // rcx
  struct _IRP_CONTEXT *m; // rax
  __int64 v48; // rdx
  struct _ERESOURCE *v49; // rcx
  __int64 v50; // rdx
  struct _IRP_CONTEXT **v51; // rax
  __int64 v52; // rcx
  struct _FAST_MUTEX *v53; // rsi
  struct _IRP_CONTEXT *v54; // rdx
  struct _IRP_CONTEXT **v55; // rcx
  unsigned int v56; // eax
  struct _IRP_CONTEXT *k; // rcx
  __int16 v58; // [rsp+60h] [rbp+8h]
  struct _IRP_CONTEXT **v59; // [rsp+68h] [rbp+10h]
  char *v60; // [rsp+70h] [rbp+18h]

  if ( *((_QWORD *)a1 + 6) )
    RefsReleaseSharedResources(a1);
  v2 = *((_QWORD *)a1 + 7);
  v3 = 0;
  if ( !v2 )
    goto LABEL_4;
  if ( *(_WORD *)v2 == 2050 )
  {
    v48 = *((_QWORD *)a1 + 13);
    v49 = *(struct _ERESOURCE **)(v2 + 96);
    if ( *(struct _ERESOURCE **)(v48 + 336) != v49 || !*(_DWORD *)(v48 + 320) || (v50 = v48 + 248) == 0 )
    {
      ExReleaseResourceLite(v49);
      v3 = 0;
      *((_QWORD *)a1 + 7) = 0;
      goto LABEL_4;
    }
    v34 = (*(_DWORD *)(v50 + 72))-- == 1;
    if ( v34 )
    {
      *(_DWORD *)(v50 + 76) &= ~2u;
      ExReleaseFastResource(v49, v50);
      v3 = 0;
      *((_QWORD *)a1 + 7) = 0;
      goto LABEL_4;
    }
  }
  else
  {
    *((_QWORD *)a1 + 7) = 0;
    v43 = *(struct _FAST_MUTEX **)(v2 + 48);
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe(v43);
    v44 = (_QWORD *)(v2 + 448);
    if ( (_QWORD *)*v44 == v44 )
    {
      *(_QWORD *)(v2 + 440) = 0;
    }
    else
    {
      v45 = (_QWORD *)*v44;
      *(_QWORD *)(v2 + 440) |= 3uLL;
      ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(v45);
      *(_QWORD *)(v46 + 8) = 0;
      *(_QWORD *)v46 = 0;
      KeSetEvent((PRKEVENT)(v46 + 16), 0, 0);
    }
    ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(v2 + 48));
    KeLeaveGuardedRegion();
    v3 = 0;
  }
  *((_QWORD *)a1 + 7) = 0;
LABEL_4:
  v4 = *((_DWORD *)a1 + 1);
  if ( (v4 & 0x2000) != 0 )
  {
    *((_DWORD *)a1 + 1) = v4 & 0xFFFFCFFF;
    ExReleaseFastResource(*((_QWORD *)a1 + 8) + 1208LL, 0);
    v3 = 0;
  }
  v5 = (struct _IRP_CONTEXT *)*((_QWORD *)a1 + 14);
LABEL_7:
  if ( v5 != (struct _IRP_CONTEXT *)((char *)a1 + 112) )
  {
    v6 = *((_WORD *)v5 - 18);
    v7 = (char *)v5 - 64;
    v8 = v5;
    v58 = v6;
    v5 = *(struct _IRP_CONTEXT **)v5;
    while ( !*(_QWORD *)v8 )
    {
LABEL_20:
      if ( *(_WORD *)v7 == 2050 )
        v14 = v7;
      else
        v14 = (char *)*((_QWORD *)v7 + 17);
      v15 = v3;
      CurrentThread = KeGetCurrentThread();
      v17 = *((_QWORD *)v14 + 11) + 64LL;
      for ( i = (unsigned int)v3; i < 2; ++i )
      {
        v19 = 112LL * i;
        v20 = (_QWORD *)((char *)a1 + v19 + 352);
        if ( *v20 == v17 && *(struct _KTHREAD **)((char *)a1 + v19 + 360) == CurrentThread )
        {
          v15 = (char *)a1 + v19 + 352;
          if ( v20 )
            goto LABEL_50;
          break;
        }
      }
      for ( j = (struct _IRP_CONTEXT *)*((_QWORD *)a1 + 72);
            j != (struct _IRP_CONTEXT *)((char *)a1 + 576);
            j = *(struct _IRP_CONTEXT **)j )
      {
        if ( *((_QWORD *)j - 12) == v17 && *((struct _KTHREAD **)j - 11) == CurrentThread )
        {
          v15 = (char *)j - 96;
          break;
        }
      }
LABEL_50:
      IsFastResourceHeldExclusive = ExIsFastResourceHeldExclusive(v17);
      if ( !v15 )
      {
        v33 = (struct _ERESOURCE *)(*((_QWORD *)v14 + 11) + 64LL);
        if ( IsFastResourceHeldExclusive )
          ExReleaseFastResource(v33, 0);
        else
          ExReleaseResourceLite(v33);
        goto LABEL_53;
      }
      v35 = *((_DWORD *)v15 + 4);
      if ( IsFastResourceHeldExclusive )
      {
        if ( !v35 )
          goto LABEL_59;
        *((_DWORD *)v15 + 4) = v35 - 1;
        if ( v35 != 1 )
          goto LABEL_59;
LABEL_58:
        *(_QWORD *)v15 = 0;
        *((_QWORD *)v15 + 1) = 0;
        goto LABEL_59;
      }
      *((_DWORD *)v15 + 4) = v35 - 1;
      if ( v35 == 1 )
        goto LABEL_58;
LABEL_59:
      ExReleaseFastResource(*((_QWORD *)v14 + 11) + 64LL, v15 + 24);
LABEL_53:
      v3 = 0;
LABEL_54:
      v34 = v6-- == 1;
      v58 = v6;
      if ( v34 )
        goto LABEL_7;
    }
    if ( *((_WORD *)v7 + 14) != 1 )
      goto LABEL_19;
    v9 = *((_QWORD *)a1 + 3);
    if ( v9 && *(_QWORD *)(v9 + 144) && ((*((_DWORD *)v7 + 2) & 0x8000LL) == 0 || (*((_DWORD *)a1 + 1) & 0x1000) != 0) )
      goto LABEL_54;
    ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(v8);
    v11 = (struct _IRP_CONTEXT *)((char *)a1 + 640);
    *((_QWORD *)v8 + 1) = v3;
    *(_QWORD *)v8 = v3;
    v12 = (struct _IRP_CONTEXT *)*((_QWORD *)a1 + 80);
    if ( v12 == (struct _IRP_CONTEXT *)((char *)a1 + 640) )
    {
LABEL_19:
      --*((_WORD *)v7 + 14);
      goto LABEL_20;
    }
    v13 = v3;
    while ( v12 != v11 )
    {
      if ( *((_WORD *)v12 - 4) == v10 )
      {
        v13 = (char *)v12 - 8;
        break;
      }
      v12 = *(struct _IRP_CONTEXT **)v12;
    }
    if ( !v13 )
    {
LABEL_18:
      v6 = v58;
      goto LABEL_19;
    }
    while ( 1 )
    {
      v51 = (struct _IRP_CONTEXT **)(v13 + 8);
      v60 = v3;
      v59 = (struct _IRP_CONTEXT **)(v13 + 8);
      if ( *(struct _IRP_CONTEXT **)v11 != v11 )
      {
        for ( k = *v51; ; k = *(struct _IRP_CONTEXT **)k )
        {
          v59 = (struct _IRP_CONTEXT **)(v13 + 8);
          v51 = (struct _IRP_CONTEXT **)(v13 + 8);
          if ( k == v11 )
            break;
          if ( *((_WORD *)k - 4) == v10 )
          {
            v60 = (char *)k - 8;
            v51 = (struct _IRP_CONTEXT **)(v13 + 8);
            v59 = (struct _IRP_CONTEXT **)(v13 + 8);
            break;
          }
        }
      }
      v52 = *((_QWORD *)v13 + 6);
      if ( v52 )
      {
        if ( *(char **)(v52 + 136) != v7 )
          goto LABEL_103;
        if ( ((*(_DWORD *)(v52 + 152) & 0x2000) != 0 || (*(_DWORD *)(v52 + 300) & 0x40) != 0)
          && (*(_DWORD *)(v52 + 152) & 0x2000) != 0 )
        {
          _InterlockedAnd((volatile signed __int32 *)(v52 + 152), 0xFFFFDFFF);
        }
        v53 = *(struct _FAST_MUTEX **)(*((_QWORD *)v13 + 6) + 48LL);
        KeEnterGuardedRegion();
        ExAcquireFastMutexUnsafe(v53);
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v13 + 6) + 172LL));
        *(_QWORD *)(*((_QWORD *)v13 + 6) + 280LL) = 0;
        ++*(_DWORD *)(*((_QWORD *)v13 + 6) + 172LL);
        ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(*((_QWORD *)v13 + 6) + 48LL));
        KeLeaveGuardedRegion();
        v51 = v59;
      }
      v54 = *v51;
      if ( *((struct _IRP_CONTEXT ***)*v51 + 1) != v51 )
        goto LABEL_112;
      v55 = (struct _IRP_CONTEXT **)v51[1];
      if ( *v55 != (struct _IRP_CONTEXT *)v51 )
        goto LABEL_112;
      *v55 = v54;
      *((_QWORD *)v54 + 1) = v55;
      if ( v13 != (char *)a1 + 728 )
      {
        v56 = *((_DWORD *)v13 - 2);
        if ( v56 >= RefsNumberProcessors )
          v56 %= RefsNumberProcessors;
        ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v56], v13 - 8);
      }
LABEL_103:
      v3 = 0;
      v13 = v60;
      v10 = 2087;
      if ( !v60 )
        goto LABEL_18;
    }
  }
  v21 = (struct _IRP_CONTEXT *)((char *)a1 + 640);
  v22 = (struct _IRP_CONTEXT *)*((_QWORD *)a1 + 80);
  if ( v22 != (struct _IRP_CONTEXT *)((char *)a1 + 640) )
  {
    v23 = 0;
    while ( v22 != v21 )
    {
      if ( *((_WORD *)v22 - 4) == 2087 )
      {
        v23 = (_QWORD *)((char *)v22 - 8);
        break;
      }
      v22 = *(struct _IRP_CONTEXT **)v22;
    }
    if ( v23 )
    {
      while ( 1 )
      {
        v36 = (struct _IRP_CONTEXT **)(v23 + 1);
        v37 = 0;
        if ( *(struct _IRP_CONTEXT **)v21 != v21 )
        {
          for ( m = *v36; ; m = *(struct _IRP_CONTEXT **)m )
          {
            v36 = (struct _IRP_CONTEXT **)(v23 + 1);
            if ( m == v21 )
              break;
            if ( *((_WORD *)m - 4) == 2087 )
            {
              v37 = (_QWORD *)((char *)m - 8);
              break;
            }
          }
        }
        v38 = v23[6];
        if ( v38 )
        {
          if ( ((*(_DWORD *)(v38 + 152) & 0x2000) != 0 || (*(_DWORD *)(v38 + 300) & 0x40) != 0)
            && (*(_DWORD *)(v38 + 152) & 0x2000) != 0 )
          {
            _InterlockedAnd((volatile signed __int32 *)(v38 + 152), 0xFFFFDFFF);
          }
          v39 = *(struct _FAST_MUTEX **)(v23[6] + 48LL);
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(v39);
          _InterlockedIncrement((volatile signed __int32 *)(v23[6] + 172LL));
          *(_QWORD *)(v23[6] + 280LL) = 0;
          ++*(_DWORD *)(v23[6] + 172LL);
          ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(v23[6] + 48LL));
          KeLeaveGuardedRegion();
        }
        v40 = *v36;
        if ( *((struct _IRP_CONTEXT ***)*v36 + 1) != v36
          || (v41 = (struct _IRP_CONTEXT **)v36[1], *v41 != (struct _IRP_CONTEXT *)v36) )
        {
LABEL_112:
          __fastfail(3u);
        }
        *v41 = v40;
        *((_QWORD *)v40 + 1) = v41;
        if ( v23 != (_QWORD *)((char *)a1 + 728) )
        {
          v42 = *((_DWORD *)v23 - 2);
          if ( v42 >= RefsNumberProcessors )
            v42 %= RefsNumberProcessors;
          ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v42], v23 - 1);
        }
        if ( !v37 )
          break;
        v23 = v37;
      }
    }
  }
  v24 = *((_QWORD *)a1 + 1);
  if ( (v24 & 0x20000000000LL) != 0 )
  {
    *((_DWORD *)a1 + 59) &= ~1u;
    *((_QWORD *)a1 + 1) = v24 & 0xFFFFFDFFFFFFFFFFuLL;
  }
  if ( *((_QWORD *)a1 + 42) )
  {
    *((_DWORD *)a1 + 81) &= ~1u;
    *((_QWORD *)a1 + 42) = 0;
  }
  v25 = (_QWORD **)((char *)a1 + 576);
  while ( 1 )
  {
    v26 = *v25;
    if ( *v25 == v25 )
      break;
    if ( (_QWORD **)v26[1] != v25 )
      goto LABEL_112;
    v30 = (_QWORD *)*v26;
    if ( *(_QWORD **)(*v26 + 8LL) != v26 )
      goto LABEL_112;
    *v25 = v30;
    v30[1] = v25;
    ExFreePoolWithTag(v26 - 12, 0);
  }
  *((_QWORD *)a1 + 44) = 0;
  *((_QWORD *)a1 + 58) = 0;
  *((_DWORD *)a1 + 148) = 0;
  if ( a1 != *((struct _IRP_CONTEXT **)a1 + 13) || !LOBYTE(IoGetTopLevelIrp()->Type) )
  {
    *((_QWORD *)a1 + 1) |= 0x2000uLL;
    if ( IoGetTopLevelIrp()->MdlAddress == (PMDL)7 )
      *((_QWORD *)a1 + 1) |= 0x400000uLL;
  }
  v27 = *((_QWORD *)a1 + 1);
  if ( (v27 & 0x100000) != 0 )
  {
    TopLevelIrp = IoGetTopLevelIrp();
    MdlAddress = (IRP *)TopLevelIrp->MdlAddress;
    *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
    *(_QWORD *)&TopLevelIrp->Flags = 0;
    IoSetTopLevelIrp(MdlAddress);
    v27 = *((_QWORD *)a1 + 1) & 0xFFFFFFFFFFEFFFFFuLL;
  }
  *((_DWORD *)a1 + 1) &= ~0x40u;
  *((_QWORD *)a1 + 1) = v27 & 0xFFFFFBFEFFFFFFFFuLL | 0x40000000000LL;
}

```

## disassembly

```asm
0x1400892a0  mov     [rsp+arg_18], rbx
0x1400892a5  push    rbp
0x1400892a6  push    rsi
0x1400892a7  push    rdi
0x1400892a8  push    r12
0x1400892aa  push    r13
0x1400892ac  push    r14
0x1400892ae  push    r15
0x1400892b0  sub     rsp, 20h
0x1400892b4  cmp     qword ptr [rcx+30h], 0
0x1400892b9  mov     rdi, rcx
0x1400892bc  jz      short loc_1400892C3
0x1400892be  call    ?RefsReleaseSharedResources@@YAXPEAU_IRP_CONTEXT@@@Z; RefsReleaseSharedResources(_IRP_CONTEXT *)
0x1400892c3  mov     rsi, [rdi+38h]
0x1400892c7  xor     r10d, r10d
0x1400892ca  mov     r15d, 802h
0x1400892d0  test    rsi, rsi
0x1400892d3  jnz     loc_140089732
0x1400892d9  mov     eax, [rdi+4]
0x1400892dc  bt      eax, 0Dh
0x1400892e0  jb      loc_140089ABF
0x1400892e6  mov     rbx, [rdi+70h]
0x1400892ea  lea     r14, [rdi+70h]
0x1400892ee  mov     r8d, 827h
0x1400892f4  cmp     rbx, r14
0x1400892f7  jz      loc_1400893D2
0x1400892fd  movzx   r13d, word ptr [rbx-24h]
0x140089302  lea     rbp, [rbx-40h]
0x140089306  mov     r12, rbx
0x140089309  mov     [rsp+58h+arg_0], r13w
0x14008930f  mov     rbx, [rbx]
0x140089312  mov     eax, 0FFFFh
0x140089317  cmp     qword ptr [r12], 0
0x14008931c  jz      short loc_140089387
0x14008931e  cmp     word ptr [rbp+1Ch], 1
0x140089323  jnz     short loc_140089383
0x140089325  mov     rax, [rdi+18h]
0x140089329  test    rax, rax
0x14008932c  jnz     loc_1400899AA
0x140089332  mov     rcx, r12
0x140089335  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x14008933a  lea     r15, [rdi+280h]
0x140089341  mov     [r12+8], r10
0x140089346  mov     [r12], r10
0x14008934a  mov     rax, [r15]
0x14008934d  cmp     rax, r15
0x140089350  jz      short loc_140089378
0x140089352  mov     r13, r10
0x140089355  cmp     rax, r15
0x140089358  jz      short loc_140089369
0x14008935a  cmp     [rax-8], r8w
0x14008935f  jnz     loc_140089A1F
0x140089365  lea     r13, [rax-8]
0x140089369  test    r13, r13
0x14008936c  jnz     loc_140089840
0x140089372  movzx   r13d, [rsp+58h+arg_0]
0x140089378  mov     eax, 0FFFFh
0x14008937d  mov     r15d, 802h
0x140089383  add     [rbp+1Ch], ax
0x140089387  cmp     [rbp+0], r15w
0x14008938c  jnz     loc_1400895FF
0x140089392  mov     r15, rbp
0x140089395  mov     r8, [r15+58h]
0x140089399  mov     rsi, r10
0x14008939c  mov     r9, gs:188h
0x1400893a5  add     r8, 40h ; '@'
0x1400893a9  mov     edx, r10d
0x1400893ac  cmp     edx, 2
0x1400893af  jnb     loc_14008953A
0x1400893b5  mov     eax, edx
0x1400893b7  imul    rcx, rax, 70h ; 'p'
0x1400893bb  lea     rax, [rdi+160h]
0x1400893c2  add     rax, rcx
0x1400893c5  cmp     [rax], r8
0x1400893c8  jz      loc_1400895E0
0x1400893ce  inc     edx
0x1400893d0  jmp     short loc_1400893AC
0x1400893d2  lea     rsi, [rdi+280h]
0x1400893d9  mov     rax, [rsi]
0x1400893dc  cmp     rax, rsi
0x1400893df  jz      short loc_140089401
0x1400893e1  mov     rbp, r10
0x1400893e4  cmp     rax, rsi
0x1400893e7  jz      short loc_1400893F8
0x1400893e9  cmp     [rax-8], r8w
0x1400893ee  jnz     loc_1400899D8
0x1400893f4  lea     rbp, [rax-8]
0x1400893f8  test    rbp, rbp
0x1400893fb  jnz     loc_140089610
0x140089401  mov     rax, [rdi+8]
0x140089405  bt      rax, 29h ; ')'
0x14008940a  jb      loc_140089B0F
0x140089410  cmp     qword ptr [rdi+150h], 0
0x140089418  jnz     loc_140089B2C
0x14008941e  lea     rbx, [rdi+240h]
0x140089425  mov     rcx, [rbx]
0x140089428  cmp     rcx, rbx
0x14008942b  jnz     loc_1400894D9
0x140089431  xor     r10d, r10d
0x140089434  mov     [rdi+160h], r10
0x14008943b  mov     [r14+160h], r10
0x140089442  mov     [rdi+250h], r10d
0x140089449  cmp     rdi, [rdi+68h]
0x14008944d  jnz     loc_14008950E
0x140089453  call    cs:__imp_IoGetTopLevelIrp
0x14008945a  nop     dword ptr [rax+rax+00h]
0x14008945f  cmp     byte ptr [rax], 0
0x140089462  jz      loc_14008950E
0x140089468  mov     rax, [rdi+8]
0x14008946c  bt      rax, 14h
0x140089471  jnb     short loc_1400894A1
0x140089473  call    cs:__imp_IoGetTopLevelIrp
0x14008947a  nop     dword ptr [rax+rax+00h]
0x14008947f  xor     edx, edx
0x140089481  mov     rcx, [rax+8]; Irp
0x140089485  mov     [rax+4], edx
0x140089488  mov     [rax+10h], rdx
0x14008948c  call    cs:__imp_IoSetTopLevelIrp
0x140089493  nop     dword ptr [rax+rax+00h]
0x140089498  mov     rax, [rdi+8]
0x14008949c  btr     rax, 14h
0x1400894a1  and     dword ptr [rdi+4], 0FFFFFFBFh
0x1400894a5  mov     rcx, 0FFFFFFFEFFFFFFFFh
0x1400894af  mov     rbx, [rsp+58h+arg_18]
0x1400894b4  and     rax, rcx
0x1400894b7  mov     rcx, 40000000000h
0x1400894c1  or      rax, rcx
0x1400894c4  mov     [rdi+8], rax
0x1400894c8  add     rsp, 20h
0x1400894cc  pop     r15
0x1400894ce  pop     r14
0x1400894d0  pop     r13
0x1400894d2  pop     r12
0x1400894d4  pop     rdi
0x1400894d5  pop     rsi
0x1400894d6  pop     rbp
0x1400894d7  retn
0x1400894d9  cmp     [rcx+8], rbx
0x1400894dd  jnz     loc_1400899E0
0x1400894e3  mov     rax, [rcx]
0x1400894e6  cmp     [rax+8], rcx
0x1400894ea  jnz     loc_1400899E0
0x1400894f0  mov     [rbx], rax
0x1400894f3  add     rcx, 0FFFFFFFFFFFFFFA0h; P
0x1400894f7  xor     edx, edx; Tag
0x1400894f9  mov     [rax+8], rbx
0x1400894fd  call    cs:__imp_ExFreePoolWithTag
0x140089504  nop     dword ptr [rax+rax+00h]
0x140089509  jmp     loc_140089425
0x14008950e  or      qword ptr [rdi+8], 2000h
0x140089516  call    cs:__imp_IoGetTopLevelIrp
0x14008951d  nop     dword ptr [rax+rax+00h]
0x140089522  cmp     qword ptr [rax+8], 7
0x140089527  jnz     loc_140089468
0x14008952d  or      qword ptr [rdi+8], 400000h
0x140089535  jmp     loc_140089468
0x14008953a  lea     rax, [rdi+240h]
0x140089541  mov     rcx, [rax]
0x140089544  cmp     rcx, rax
0x140089547  jnz     loc_140089A72
0x14008954d  mov     rcx, r8
0x140089550  call    cs:__imp_ExIsFastResourceHeldExclusive
0x140089557  nop     dword ptr [rax+rax+00h]
0x14008955c  test    rsi, rsi
0x14008955f  jnz     short loc_1400895A8
0x140089561  mov     rcx, [r15+58h]
0x140089565  add     rcx, 40h ; '@'; Resource
0x140089569  test    al, al
0x14008956b  jz      loc_140089AF3
0x140089571  xor     edx, edx
0x140089573  call    cs:__imp_ExReleaseFastResource
0x14008957a  nop     dword ptr [rax+rax+00h]
0x14008957f  xor     r10d, r10d
0x140089582  mov     r15d, 802h
0x140089588  mov     r8d, 827h
0x14008958e  mov     eax, 0FFFFh
0x140089593  add     r13w, ax
0x140089597  mov     [rsp+58h+arg_0], r13w
0x14008959d  jz      loc_1400892F4
0x1400895a3  jmp     loc_140089317
0x1400895a8  mov     ecx, [rsi+10h]
0x1400895ab  test    al, al
0x1400895ad  jnz     loc_140089A4F
0x1400895b3  lea     eax, [rcx-1]
0x1400895b6  mov     [rsi+10h], eax
0x1400895b9  test    eax, eax
0x1400895bb  jnz     short loc_1400895C6
0x1400895bd  xor     edx, edx
0x1400895bf  mov     [rsi], rdx
0x1400895c2  mov     [rsi+8], rdx
0x1400895c6  mov     rcx, [r15+58h]
0x1400895ca  lea     rdx, [rsi+18h]
0x1400895ce  add     rcx, 40h ; '@'
0x1400895d2  call    cs:__imp_ExReleaseFastResource
0x1400895d9  nop     dword ptr [rax+rax+00h]
0x1400895de  jmp     short loc_14008957F
0x1400895e0  cmp     [rcx+rdi+168h], r9
0x1400895e8  jnz     loc_1400893CE
0x1400895ee  mov     rsi, rax
0x1400895f1  test    rax, rax
0x1400895f4  jnz     loc_14008954D
0x1400895fa  jmp     loc_14008953A
0x1400895ff  mov     r15, [rbp+88h]
0x140089606  jmp     loc_140089395
0x140089610  lea     r15, [rbp+8]
0x140089614  mov     r12, r10
0x140089617  cmp     [rsi], rsi
0x14008961a  jnz     loc_1400897C3
0x140089620  mov     rcx, [rbp+30h]
0x140089624  test    rcx, rcx
0x140089627  jz      loc_1400896BA
0x14008962d  mov     edx, [rcx+98h]
0x140089633  and     edx, 2000h
0x140089639  jnz     loc_140089A27
0x14008963f  mov     eax, [rcx+12Ch]
0x140089645  test    al, 40h
0x140089647  jnz     loc_140089A27
0x14008964d  mov     rax, [rbp+30h]
0x140089651  mov     rbx, [rax+30h]
0x140089655  call    cs:__imp_KeEnterGuardedRegion
0x14008965c  nop     dword ptr [rax+rax+00h]
0x140089661  mov     rcx, rbx; FastMutex
0x140089664  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14008966b  nop     dword ptr [rax+rax+00h]
0x140089670  mov     rax, [rbp+30h]
0x140089674  lock inc dword ptr [rax+0ACh]
0x14008967b  mov     rax, [rbp+30h]
0x14008967f  xor     edx, edx
0x140089681  mov     [rax+118h], rdx
0x140089688  mov     rcx, [rbp+30h]
0x14008968c  mov     eax, [rcx+0ACh]
0x140089692  inc     eax
0x140089694  mov     [rcx+0ACh], eax
0x14008969a  mov     rcx, [rbp+30h]
0x14008969e  mov     rcx, [rcx+30h]; FastMutex
0x1400896a2  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400896a9  nop     dword ptr [rax+rax+00h]
0x1400896ae  call    cs:__imp_KeLeaveGuardedRegion
0x1400896b5  nop     dword ptr [rax+rax+00h]
0x1400896ba  mov     rax, [r15]
0x1400896bd  cmp     [rax+8], r15
0x1400896c1  jnz     loc_1400899E0
0x1400896c7  mov     rcx, [r15+8]
0x1400896cb  cmp     [rcx], r15
0x1400896ce  jnz     loc_1400899E0
0x1400896d4  mov     [rcx], rax
0x1400896d7  mov     [rax+8], rcx
0x1400896db  lea     rax, [rdi+2D8h]
0x1400896e2  cmp     rbp, rax
0x1400896e5  jz      short loc_140089718
0x1400896e7  mov     eax, [rbp-8]
0x1400896ea  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x1400896f0  mov     r8, cs:?RefsScbSnapshotLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsScbSnapshotLookasideList
0x1400896f7  cmp     eax, ecx
0x1400896f9  jnb     loc_140089B04
0x1400896ff  mov     ecx, eax
0x140089701  lea     rdx, [rbp-8]; Entry
0x140089705  shl     rcx, 7
0x140089709  add     rcx, r8; Lookaside
0x14008970c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140089713  nop     dword ptr [rax+rax+00h]
0x140089718  xor     r10d, r10d
0x14008971b  test    r12, r12
0x14008971e  jz      loc_140089401
0x140089724  mov     rbp, r12
0x140089727  mov     r8d, 827h
0x14008972d  jmp     loc_140089610
0x140089732  cmp     [rsi], r15w
0x140089736  jz      loc_1400897E9
0x14008973c  mov     [rdi+38h], r10
0x140089740  mov     rbx, [rsi+30h]
0x140089744  call    cs:__imp_KeEnterGuardedRegion
0x14008974b  nop     dword ptr [rax+rax+00h]
0x140089750  mov     rcx, rbx; FastMutex
0x140089753  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14008975a  nop     dword ptr [rax+rax+00h]
0x14008975f  lea     rcx, [rsi+1C0h]
0x140089766  cmp     [rcx], rcx
0x140089769  jz      loc_14008999C
0x14008976f  mov     rcx, [rcx]
0x140089772  or      qword ptr [rsi+1B8h], 3
0x14008977a  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x14008977f  xor     edx, edx; Increment
0x140089781  xor     r8d, r8d; Wait
0x140089784  mov     [rcx+8], rdx
0x140089788  mov     [rcx], rdx
0x14008978b  add     rcx, 10h; Event
0x14008978f  call    cs:__imp_KeSetEvent
0x140089796  nop     dword ptr [rax+rax+00h]
0x14008979b  mov     rcx, [rsi+30h]; FastMutex
0x14008979f  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400897a6  nop     dword ptr [rax+rax+00h]
0x1400897ab  call    cs:__imp_KeLeaveGuardedRegion
0x1400897b2  nop     dword ptr [rax+rax+00h]
0x1400897b7  xor     r10d, r10d
0x1400897ba  mov     [rdi+38h], r10
0x1400897be  jmp     loc_1400892D9
0x1400897c3  mov     rax, [r15]
0x1400897c6  mov     rcx, r15
0x1400897c9  mov     r15, rcx
  ... truncated ...
```
