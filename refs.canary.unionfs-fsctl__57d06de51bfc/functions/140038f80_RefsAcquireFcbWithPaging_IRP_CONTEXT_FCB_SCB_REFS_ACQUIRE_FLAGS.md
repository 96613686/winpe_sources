# RefsAcquireFcbWithPaging(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)

- ea: `0x140038f80`
- end: `0x140039b12`
- name: `?RefsAcquireFcbWithPaging@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z`
- size: `2962`
- prototype: ``
- caller_count: `35`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140037c90`
- `0x1400a1490`
- `0x1400d6ee4`
- `0x1400e64e4`
- `0x1400eb1ac`
- `0x1400f1330`
- `0x1400f6f00`
- `0x140104a40`
- `0x140110650`
- `0x14028aa64`
- `0x1402915d4`
- `0x140295074`
- `0x14029b12c`
- `0x1402a5720`
- `0x1402a9d08`
- `0x1402ad9cc`
- `0x1402b3dac`
- `0x1402bd964`
- `0x1402c2478`
- `0x1402c2af4`
- `0x1402c3810`
- `0x1402cde48`
- `0x1402ce9cc`
- `0x1402cee8c`
- `0x1402fb270`
- `0x1402fc810`
- `0x140301810`
- `0x140304220`
- `0x14030a1a0`
- `0x140314de0`
- `0x140319a38`
- `0x14031c960`
- `0x140328060`
- `0x140336b00`
- `0x14033a130`

## callees

- `0x14000a370`
- `0x140038f80`
- `0x140081670`
- `0x14008dbd0`
- `0x1400c8644`
- `0x1400ca788`
- `0x1400cbbac`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140039528`
- `ntoskrnl!KeDelayExecutionThread` at `0x140039747`
- `ntoskrnl!KeDelayExecutionThread` at `0x140039528`
- `ntoskrnl!KeDelayExecutionThread` at `0x140039747`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140039378`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140039424`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140039378`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140039424`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003969a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003969a`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400390d9`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400390d9`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400395ce`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400395ce`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400395dd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400395dd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003961d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003961d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140039629`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140039629`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400392ad`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400394b5`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400392ad`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400394b5`
- `ntoskrnl!ExReleaseFastResource` at `0x1400392d4`
- `ntoskrnl!ExReleaseFastResource` at `0x1400394f1`
- `ntoskrnl!ExReleaseFastResource` at `0x140039ad3`
- `ntoskrnl!ExReleaseFastResource` at `0x1400392d4`
- `ntoskrnl!ExReleaseFastResource` at `0x1400394f1`
- `ntoskrnl!ExReleaseFastResource` at `0x140039ad3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140039a4f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140039af7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140039a4f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140039af7`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140039112`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140039112`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400397ea`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400397ea`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003971f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003971f`

## pseudocode

```c
__int64 __fastcall RefsAcquireFcbWithPaging(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned int v4; // edi
  __int64 v5; // r12
  unsigned __int8 v8; // dl
  __int64 v9; // rax
  __int64 v10; // r13
  __int64 v11; // r15
  __int64 *v12; // rbx
  struct _KTHREAD *CurrentThread; // r12
  unsigned int i; // edx
  __int64 v15; // rcx
  _QWORD *j; // rcx
  unsigned int k; // edx
  BOOLEAN v18; // al
  _QWORD *v19; // rcx
  unsigned int v20; // r8d
  unsigned __int8 v21; // bl
  __int64 v22; // rax
  _QWORD *v23; // rcx
  _QWORD *v24; // r12
  _QWORD *v25; // rax
  _QWORD *jj; // r15
  __int64 v27; // r15
  __int64 v28; // r8
  _QWORD *v29; // rbx
  struct _KTHREAD *v30; // r9
  unsigned int n; // edx
  __int64 v32; // rcx
  _QWORD *ii; // rcx
  unsigned int v34; // r15d
  int v35; // r12d
  unsigned __int8 v36; // bl
  __int64 v37; // rcx
  unsigned int v38; // r8d
  _QWORD *v39; // rax
  __int64 v40; // rdx
  unsigned int v41; // ebx
  __int64 v42; // rcx
  unsigned int v43; // r8d
  char IsFastResourceHeldExclusive; // al
  int v45; // ecx
  _QWORD *v46; // rbx
  _QWORD *v47; // r13
  __int64 v48; // rcx
  struct _FAST_MUTEX *v49; // rbx
  _QWORD *v50; // rcx
  _QWORD *v51; // rax
  unsigned int v52; // eax
  _QWORD *m; // rax
  char *PoolWithTag; // rax
  _QWORD *kk; // rax
  _QWORD *v56; // rdx
  _QWORD *v57; // rax
  bool v58; // zf
  unsigned int v59; // ebx
  __int64 v61; // rdx
  struct _ERESOURCE *v62; // rcx
  __int64 v63; // rdx
  BOOLEAN v64; // [rsp+20h] [rbp-B8h]
  unsigned __int8 v65; // [rsp+21h] [rbp-B7h]
  char v66; // [rsp+22h] [rbp-B6h]
  _QWORD *v67; // [rsp+60h] [rbp-78h]

  v4 = a4;
  v5 = a3;
  v66 = 0;
  if ( (a4 & 2) != 0 )
  {
    v8 = 0;
  }
  else if ( (a4 & 4) != 0 )
  {
    v8 = 1;
  }
  else
  {
    v8 = *(_BYTE *)(a1 + 8) & 1;
  }
  v65 = v8;
  if ( (*(_DWORD *)(a1 + 4) & 0x10000) != 0 )
    v4 = a4 | 0x10;
  v9 = *(_QWORD *)(a1 + 56);
  if ( v9 && (v4 & 0x20) == 0 )
  {
    if ( *(_WORD *)v9 != 2050 )
      v9 = *(_QWORD *)(v9 + 136);
    v61 = *(_QWORD *)(a1 + 104);
    v62 = *(struct _ERESOURCE **)(v9 + 96);
    if ( *(struct _ERESOURCE **)(v61 + 336) != v62 || (v63 = v61 + 248, !*(_DWORD *)(v63 + 72)) )
      v63 = 0;
    if ( v63 )
    {
      v58 = (*(_DWORD *)(v63 + 72))-- == 1;
      if ( v58 )
      {
        *(_DWORD *)(v63 + 76) &= ~2u;
        ExReleaseFastResource(v62, v63);
      }
    }
    else
    {
      ExReleaseResourceLite(v62);
    }
    *(_QWORD *)(a1 + 56) = 0;
    v8 = v65;
  }
  while ( 1 )
  {
    if ( (v4 & 0x10) != 0 && *(_QWORD *)(a2 + 96) )
    {
      if ( *(_WORD *)a2 == 2050 )
        v42 = a2;
      else
        v42 = *(_QWORD *)(a2 + 136);
      if ( !(unsigned __int8)ExAcquireFastResourceExclusive(*(_QWORD *)(v42 + 96), 0, v8) )
      {
        if ( (v4 & 2) != 0 )
          return 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            12,
            WPP_31376ab3b8073048edfb14e725e449b5_Traceguids,
            3221225688LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741608, (struct _IRP_CONTEXT *)a1, "ResrcSup.c", 0x34Bu);
        RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, -1073741608, v43);
        goto LABEL_188;
      }
      if ( (v4 & 0x20) == 0 )
        *(_QWORD *)(a1 + 56) = a2;
      v66 = 1;
    }
    if ( (v4 & 8) != 0 )
    {
      if ( (v4 & 2) != 0 )
      {
        v64 = 0;
      }
      else if ( (v4 & 4) != 0 )
      {
        v64 = 1;
      }
      else
      {
        v64 = *(_BYTE *)(a1 + 8) & 1;
      }
      if ( *(_WORD *)a2 == 2050 )
        v10 = a2;
      else
        v10 = *(_QWORD *)(a2 + 136);
      v11 = *(_QWORD *)(v10 + 88) + 64LL;
      v12 = 0;
      if ( a1 )
      {
        CurrentThread = KeGetCurrentThread();
        for ( i = 0; ; ++i )
        {
          if ( i >= 2 )
            goto LABEL_18;
          v15 = 112LL * i;
          if ( *(_QWORD *)(v15 + a1 + 352) == v11 && *(struct _KTHREAD **)(v15 + a1 + 360) == CurrentThread )
            break;
        }
        v12 = (__int64 *)(v15 + a1 + 352);
LABEL_18:
        if ( !v12 )
        {
          for ( j = *(_QWORD **)(a1 + 576); ; j = (_QWORD *)*j )
          {
            if ( j == (_QWORD *)(a1 + 576) )
              goto LABEL_21;
            if ( *(j - 12) == v11 && (struct _KTHREAD *)*(j - 11) == CurrentThread )
              break;
          }
          v12 = j - 12;
        }
LABEL_21:
        if ( !v12 )
        {
          for ( k = 0; ; ++k )
          {
            if ( k >= 2 )
              goto LABEL_26;
            if ( !*(_QWORD *)(a1 + 112LL * k + 352) )
              break;
          }
          v12 = (__int64 *)(a1 + 112LL * k + 352);
LABEL_26:
          if ( v12 )
            goto LABEL_27;
          for ( m = *(_QWORD **)(a1 + 576); ; m = (_QWORD *)*m )
          {
            if ( m == (_QWORD *)(a1 + 576) )
              goto LABEL_139;
            if ( !*(m - 12) )
              break;
          }
          v12 = m - 12;
LABEL_139:
          if ( v12 )
            goto LABEL_27;
          while ( 1 )
          {
            PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x70u, 0x73466552u);
            v12 = (__int64 *)PoolWithTag;
            if ( PoolWithTag )
              break;
            KeDelayExecutionThread(0, 0, (PLARGE_INTEGER)&Interval);
          }
          *((_DWORD *)PoolWithTag + 4) = 0;
          v56 = *(_QWORD **)(a1 + 584);
          if ( *v56 != a1 + 576 )
LABEL_83:
            __fastfail(3u);
          v57 = PoolWithTag + 96;
          *v57 = a1 + 576;
          v57[1] = v56;
          *v56 = v57;
          *(_QWORD *)(a1 + 584) = v57;
          ++*(_DWORD *)(a1 + 592);
          if ( v12 )
          {
LABEL_27:
            ExInitializeFastOwnerEntry(v12 + 3);
            *v12 = v11;
            v12[1] = (__int64)CurrentThread;
          }
        }
        v5 = a3;
      }
      if ( v12 )
      {
        ++*((_DWORD *)v12 + 4);
        v18 = ExAcquireFastResourceShared(*(_QWORD *)(v10 + 88) + 64LL, v12 + 3, v64);
        if ( v18 )
        {
LABEL_31:
          if ( (v4 & 1) != 0 || (*(_BYTE *)(a2 + 8) & 1) == 0 && (!v5 || (*(_DWORD *)(v5 + 300) & 0x40) == 0) )
          {
            if ( *(_QWORD *)(a2 + 64) )
              ++*(_WORD *)(a2 + 28);
            v21 = 1;
            goto LABEL_38;
          }
LABEL_188:
          RefsReleaseResource(a1, a2);
          v59 = -1073741533;
          goto LABEL_190;
        }
        v58 = (*((_DWORD *)v12 + 4))-- == 1;
        if ( v58 )
        {
          v19 = 0;
          *v12 = 0;
          v12[1] = 0;
        }
      }
      else
      {
        v18 = ExAcquireResourceSharedLite((PERESOURCE)(*(_QWORD *)(v10 + 88) + 64LL), v64);
      }
      if ( !v18 )
      {
        if ( (v4 & 2) != 0 )
          goto LABEL_157;
        v59 = -1073741608;
LABEL_190:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_31376ab3b8073048edfb14e725e449b5_Traceguids, v59);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(v59, (struct _IRP_CONTEXT *)a1, "ResrcSup.c", 0x546u);
        RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v59, v20);
        __debugbreak();
      }
      goto LABEL_31;
    }
    v34 = 1;
    v35 = 0;
    if ( (v4 & 2) != 0 )
    {
      v36 = 0;
    }
    else
    {
      if ( (v4 & 4) != 0 )
      {
        v36 = 1;
        goto LABEL_77;
      }
      v36 = *(_BYTE *)(a1 + 8) & 1;
      if ( v36 )
        goto LABEL_77;
    }
    if ( (v4 & 0x40) != 0 )
      v34 = 10;
    while ( 1 )
    {
LABEL_77:
      if ( *(_WORD *)a2 == 2050 )
        v37 = a2;
      else
        v37 = *(_QWORD *)(a2 + 136);
      if ( (unsigned __int8)ExAcquireFastResourceExclusive(*(_QWORD *)(v37 + 88) + 64LL, 0, v36) )
      {
        if ( (v4 & 1) == 0
          && ((*(_BYTE *)(a2 + 8) & 1) != 0 || a3 && (*(_DWORD *)(a3 + 300) & 0x40) != 0)
          && ((*(_BYTE *)(a1 + 40) - 2) & 0xEF) != 0 )
        {
          RefsReleaseResource(a1, a2);
          v41 = -1073741533;
LABEL_172:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_31376ab3b8073048edfb14e725e449b5_Traceguids, v41);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(v41, (struct _IRP_CONTEXT *)a1, "ResrcSup.c", 0x4C0u);
          RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v41, v38);
          __debugbreak();
        }
        v19 = (_QWORD *)(a2 + 64);
        if ( !*(_QWORD *)(a2 + 64) )
        {
          v39 = (_QWORD *)(a1 + 112);
          v40 = *(_QWORD *)(a1 + 112);
          if ( *(_QWORD *)(v40 + 8) != a1 + 112 )
            goto LABEL_83;
          *v19 = v40;
          *(_QWORD *)(a2 + 72) = v39;
          *(_QWORD *)(v40 + 8) = v19;
          *v39 = v19;
        }
        ++*(_WORD *)(a2 + 28);
        v21 = 1;
        goto LABEL_38;
      }
      if ( ++v35 >= v34 )
        break;
      KeDelayExecutionThread(0, 0, &RefsShortDelay);
    }
    if ( (v4 & 2) == 0 )
    {
      v41 = -1073741608;
      goto LABEL_172;
    }
LABEL_157:
    v21 = 0;
LABEL_38:
    if ( !v21 )
      break;
    if ( (v4 & 0x10) == 0 || v66 || !*(_QWORD *)(a2 + 96) )
      return 1;
    if ( !*(_QWORD *)(a2 + 64) )
      goto LABEL_55;
    if ( *(_WORD *)(a2 + 28) != 1 )
    {
LABEL_54:
      --*(_WORD *)(a2 + 28);
LABEL_55:
      if ( *(_WORD *)a2 == 2050 )
        v27 = a2;
      else
        v27 = *(_QWORD *)(a2 + 136);
      v28 = *(_QWORD *)(v27 + 88) + 64LL;
      v29 = 0;
      if ( !a1 )
        goto LABEL_69;
      v30 = KeGetCurrentThread();
      for ( n = 0; n < 2; ++n )
      {
        v32 = 112LL * n;
        if ( *(_QWORD *)(v32 + a1 + 352) == v28 && *(struct _KTHREAD **)(v32 + a1 + 360) == v30 )
        {
          v29 = (_QWORD *)(v32 + a1 + 352);
          break;
        }
      }
      if ( v29 )
        goto LABEL_106;
      for ( ii = *(_QWORD **)(a1 + 576); ii != (_QWORD *)(a1 + 576); ii = (_QWORD *)*ii )
      {
        if ( *(ii - 12) == v28 && (struct _KTHREAD *)*(ii - 11) == v30 )
        {
          v29 = ii - 12;
          break;
        }
      }
      if ( v29 )
      {
LABEL_106:
        IsFastResourceHeldExclusive = ExIsFastResourceHeldExclusive(*(_QWORD *)(v27 + 88) + 64LL);
        v45 = *((_DWORD *)v29 + 4);
        if ( !IsFastResourceHeldExclusive || v45 )
        {
          *((_DWORD *)v29 + 4) = v45 - 1;
          if ( v45 == 1 )
          {
            *v29 = 0;
            v29[1] = 0;
          }
        }
        ExReleaseFastResource(*(_QWORD *)(v27 + 88) + 64LL, v29 + 3);
      }
      else
      {
LABEL_69:
        if ( (unsigned __int8)ExIsFastResourceHeldExclusive(*(_QWORD *)(v27 + 88) + 64LL) && a1 )
          ExReleaseFastResource(*(_QWORD *)(v27 + 88) + 64LL, 0);
        else
          ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v27 + 88) + 64LL));
      }
      goto LABEL_71;
    }
    v22 = *(_QWORD *)(a1 + 24);
    if ( !v22 || !*(_QWORD *)(v22 + 144) || (*(_DWORD *)(a2 + 8) & 0x8000LL) != 0 && (*(_DWORD *)(a1 + 4) & 0x1000) == 0 )
    {
      ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(a2 + 64);
      *(_QWORD *)(a2 + 72) = 0;
      *v23 = 0;
      v24 = (_QWORD *)(a1 + 640);
      v25 = *(_QWORD **)(a1 + 640);
      jj = 0;
      if ( v25 == (_QWORD *)(a1 + 640) )
        goto LABEL_53;
      while ( 1 )
      {
        if ( v25 == v24 )
          goto LABEL_53;
        if ( *((_WORD *)v25 - 4) == 2087 )
          break;
        v25 = (_QWORD *)*v25;
      }
      for ( jj = v25 - 1; ; jj = v46 )
      {
LABEL_53:
        while ( 2 )
        {
          if ( !jj )
            goto LABEL_54;
          v46 = 0;
          v67 = 0;
          v47 = jj + 1;
          if ( (_QWORD *)*v24 != v24 )
          {
            for ( kk = (_QWORD *)*v47; ; kk = (_QWORD *)*kk )
            {
              v47 = jj + 1;
              if ( kk == v24 )
                break;
              if ( *((_WORD *)kk - 4) == 2087 )
              {
                v46 = kk - 1;
                v67 = kk - 1;
                break;
              }
            }
          }
          v48 = jj[6];
          if ( v48 )
          {
            if ( a2 && *(_QWORD *)(v48 + 136) != a2 )
            {
              jj = v46;
              continue;
            }
            if ( ((*(_DWORD *)(v48 + 152) & 0x2000) != 0 || (*(_DWORD *)(v48 + 300) & 0x40) != 0)
              && (*(_DWORD *)(v48 + 152) & 0x2000) != 0 )
            {
              _InterlockedAnd((volatile signed __int32 *)(v48 + 152), 0xFFFFDFFF);
            }
            v49 = *(struct _FAST_MUTEX **)(jj[6] + 48LL);
            KeEnterGuardedRegion();
            ExAcquireFastMutexUnsafe(v49);
            _InterlockedIncrement((volatile signed __int32 *)(jj[6] + 172LL));
            *(_QWORD *)(jj[6] + 280LL) = 0;
            ++*(_DWORD *)(jj[6] + 172LL);
            ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(jj[6] + 48LL));
            KeLeaveGuardedRegion();
            v46 = v67;
          }
          break;
        }
        v50 = (_QWORD *)*v47;
        if ( *(_QWORD **)(*v47 + 8LL) != v47 )
          goto LABEL_83;
        v51 = (_QWORD *)v47[1];
        if ( (_QWORD *)*v51 != v47 )
          goto LABEL_83;
        *v51 = v50;
        v50[1] = v51;
        if ( jj != (_QWORD *)(a1 + 728) )
        {
          v52 = *((_DWORD *)jj - 2);
          if ( v52 >= RefsNumberProcessors )
            v52 %= RefsNumberProcessors;
          ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v52], jj - 1);
        }
      }
    }
LABEL_71:
    v8 = v65;
    v5 = a3;
  }
  if ( v66 )
    RefsAcquireFcbWithPaging_::_2_::_lambda_1_::operator()(v19, a1, a2, v4);
  return v21;
}

```

## disassembly

```asm
0x140038f80  mov     [rsp+arg_18], r9d
0x140038f85  mov     [rsp+arg_10], r8
0x140038f8a  mov     [rsp+arg_8], rdx
0x140038f8f  mov     [rsp+arg_0], rcx
0x140038f94  push    rbx
0x140038f95  push    rsi
0x140038f96  push    rdi
0x140038f97  push    r12
0x140038f99  push    r13
0x140038f9b  push    r14
0x140038f9d  push    r15
0x140038f9f  sub     rsp, 0A0h
0x140038fa6  mov     edi, r9d
0x140038fa9  mov     r12, r8
0x140038fac  mov     r14, rdx
0x140038faf  mov     rsi, rcx
0x140038fb2  mov     [rsp+0D8h+var_B6], 0
0x140038fb7  test    r9b, 2
0x140038fbb  jz      loc_140039A77
0x140038fc1  xor     dl, dl
0x140038fc3  mov     [rsp+0D8h+var_B7], dl
0x140038fc7  test    dword ptr [rcx+4], 10000h
0x140038fce  jz      short loc_140038FDA
0x140038fd0  or      edi, 10h
0x140038fd3  mov     [rsp+0D8h+arg_18], edi
0x140038fda  mov     rax, [rcx+38h]
0x140038fde  test    rax, rax
0x140038fe1  jnz     loc_140039A90
0x140038fe7  mov     r8d, 802h
0x140038fed  jmp     loc_1400392F3
0x140038ff2  test    r13d, r13d
0x140038ff5  jz      loc_14003916F
0x140038ffb  mov     [rsp+0D8h+var_B8], 0
0x140039000  mov     [rsp+0D8h+var_50], r14
0x140039008  cmp     [r14], r8w
0x14003900c  jnz     loc_140039491
0x140039012  mov     r13, r14
0x140039015  mov     r15, [r13+58h]
0x140039019  add     r15, 40h ; '@'
0x14003901d  mov     [rsp+0D8h+var_B0], 0
0x140039026  xor     ebx, ebx
0x140039028  test    rsi, rsi
0x14003902b  jz      loc_1400390F4
0x140039031  mov     r12, gs:188h
0x14003903a  mov     [rsp+0D8h+var_80], rbx
0x14003903f  mov     r8, gs:188h
0x140039048  xor     edx, edx
0x14003904a  mov     [rsp+0D8h+var_A8], edx
0x14003904e  cmp     edx, 2
0x140039051  jnb     short loc_14003907E
0x140039053  mov     eax, edx
0x140039055  imul    rcx, rax, 70h ; 'p'
0x140039059  lea     rax, [rsi+160h]
0x140039060  add     rax, rcx
0x140039063  cmp     [rax], r15
0x140039066  jz      short loc_14003906C
0x140039068  inc     edx
0x14003906a  jmp     short loc_14003904A
0x14003906c  cmp     [rcx+rsi+168h], r8
0x140039074  jnz     short loc_140039068
0x140039076  mov     rbx, rax
0x140039079  mov     [rsp+0D8h+var_80], rax
0x14003907e  test    rbx, rbx
0x140039081  jnz     short loc_140039096
0x140039083  lea     rax, [rsi+240h]
0x14003908a  mov     rcx, [rax]
0x14003908d  cmp     rcx, rax
0x140039090  jnz     loc_1400397A7
0x140039096  mov     [rsp+0D8h+var_B0], rbx
0x14003909b  test    rbx, rbx
0x14003909e  jnz     short loc_1400390EC
0x1400390a0  xor     edx, edx
0x1400390a2  mov     [rsp+0D8h+var_A4], edx
0x1400390a6  cmp     edx, 2
0x1400390a9  jnb     short loc_1400390CC
0x1400390ab  mov     eax, edx
0x1400390ad  imul    rax, 70h ; 'p'
0x1400390b1  add     rax, 160h
0x1400390b7  add     rax, rsi
0x1400390ba  cmp     qword ptr [rax], 0
0x1400390be  jnz     loc_1400394A6
0x1400390c4  mov     rbx, rax
0x1400390c7  mov     [rsp+0D8h+var_B0], rax
0x1400390cc  test    rbx, rbx
0x1400390cf  jz      loc_1400396E0
0x1400390d5  lea     rcx, [rbx+18h]
0x1400390d9  call    cs:__imp_ExInitializeFastOwnerEntry
0x1400390e0  nop     dword ptr [rax+rax+00h]
0x1400390e5  mov     [rbx], r15
0x1400390e8  mov     [rbx+8], r12
0x1400390ec  mov     r12, [rsp+0D8h+arg_10]
0x1400390f4  test    rbx, rbx
0x1400390f7  jz      loc_1400397DD
0x1400390fd  inc     dword ptr [rbx+10h]
0x140039100  lea     rdx, [rbx+18h]
0x140039104  mov     rcx, [r13+58h]
0x140039108  add     rcx, 40h ; '@'
0x14003910c  movzx   r8d, [rsp+0D8h+var_B8]
0x140039112  call    cs:__imp_ExAcquireFastResourceShared
0x140039119  nop     dword ptr [rax+rax+00h]
0x14003911e  test    al, al
0x140039120  jz      loc_14003992F
0x140039126  test    dil, 1
0x14003912a  jnz     short loc_14003914C
0x14003912c  test    byte ptr [r14+8], 1
0x140039131  jnz     loc_1400399AD
0x140039137  test    r12, r12
0x14003913a  jz      short loc_14003914C
0x14003913c  mov     eax, [r12+12Ch]
0x140039144  test    al, 40h
0x140039146  jnz     loc_1400399AD
0x14003914c  cmp     qword ptr [r14+40h], 0
0x140039151  jnz     loc_140039502
0x140039157  mov     bl, 1
0x140039159  test    bl, bl
0x14003915b  jz      loc_140039789
0x140039161  cmp     dword ptr [rsp+0D8h+var_90], 0
0x140039166  jnz     short loc_140039188
0x140039168  mov     bl, 1
0x14003916a  jmp     loc_140039A60
0x14003916f  test    dil, 4
0x140039173  jnz     loc_1400397D3
0x140039179  movzx   eax, byte ptr [rsi+8]
0x14003917d  and     al, 1
0x14003917f  mov     [rsp+0D8h+var_B8], al
0x140039183  jmp     loc_140039000
0x140039188  cmp     [rsp+0D8h+var_B6], 0
0x14003918d  jnz     short loc_140039168
0x14003918f  cmp     qword ptr [r14+60h], 0
0x140039194  jz      short loc_140039168
0x140039196  lea     rcx, [r14+40h]
0x14003919a  cmp     qword ptr [rcx], 0
0x14003919e  jz      short loc_140039213
0x1400391a0  cmp     word ptr [r14+1Ch], 1
0x1400391a6  jnz     short loc_140039209
0x1400391a8  mov     rax, [rsi+18h]
0x1400391ac  test    rax, rax
0x1400391af  jnz     loc_1400396B1
0x1400391b5  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x1400391ba  xor     r9d, r9d
0x1400391bd  mov     [r14+48h], r9
0x1400391c1  mov     [rcx], r9
0x1400391c4  lea     r12, [rsi+280h]
0x1400391cb  mov     rax, [r12]
0x1400391cf  mov     r15d, r9d
0x1400391d2  cmp     rax, r12
0x1400391d5  jz      short loc_140039200
0x1400391d7  mov     [rsp+0D8h+var_60], r9
0x1400391dc  mov     edx, 827h
0x1400391e1  cmp     rax, r12
0x1400391e4  jz      short loc_140039200
0x1400391e6  lea     rcx, [rax-8]
0x1400391ea  cmp     [rcx], dx
0x1400391ed  jnz     loc_1400397B8
0x1400391f3  mov     r15, rcx
0x1400391f6  mov     [rsp+0D8h+var_60], rcx
0x1400391fb  nop     dword ptr [rax+rax+00h]
0x140039200  test    r15, r15
0x140039203  jnz     loc_140039568
0x140039209  mov     eax, 0FFFFh
0x14003920e  add     [r14+1Ch], ax
0x140039213  mov     [rsp+0D8h+var_40], r14
0x14003921b  mov     eax, 802h
0x140039220  cmp     [r14], ax
0x140039224  jnz     loc_14003953F
0x14003922a  mov     r15, r14
0x14003922d  mov     r8, [r15+58h]
0x140039231  add     r8, 40h ; '@'
0x140039235  xor     ebx, ebx
0x140039237  mov     [rsp+0D8h+var_70], rbx
0x14003923c  test    rsi, rsi
0x14003923f  jz      short loc_1400392A5
0x140039241  mov     r9, gs:188h
0x14003924a  xor     edx, edx
0x14003924c  mov     [rsp+0D8h+var_88], edx
0x140039250  cmp     edx, 2
0x140039253  jnb     short loc_140039280
0x140039255  mov     eax, edx
0x140039257  imul    rcx, rax, 70h ; 'p'
0x14003925b  lea     rax, [rsi+160h]
0x140039262  add     rax, rcx
0x140039265  cmp     [rax], r8
0x140039268  jz      short loc_14003926E
0x14003926a  inc     edx
0x14003926c  jmp     short loc_14003924C
0x14003926e  cmp     [rcx+rsi+168h], r9
0x140039276  jnz     short loc_14003926A
0x140039278  mov     rbx, rax
0x14003927b  mov     [rsp+0D8h+var_70], rax
0x140039280  test    rbx, rbx
0x140039283  jnz     loc_1400394AD
0x140039289  lea     rax, [rsi+240h]
0x140039290  mov     rcx, [rax]
0x140039293  cmp     rcx, rax
0x140039296  jnz     loc_14003985E
0x14003929c  test    rbx, rbx
0x14003929f  jnz     loc_1400394AD
0x1400392a5  mov     rcx, [r15+58h]
0x1400392a9  add     rcx, 40h ; '@'
0x1400392ad  call    cs:__imp_ExIsFastResourceHeldExclusive
0x1400392b4  nop     dword ptr [rax+rax+00h]
0x1400392b9  test    al, al
0x1400392bb  jz      loc_140039A47
0x1400392c1  test    rsi, rsi
0x1400392c4  jz      loc_140039A47
0x1400392ca  mov     rcx, [r15+58h]
0x1400392ce  add     rcx, 40h ; '@'
0x1400392d2  xor     edx, edx
0x1400392d4  call    cs:__imp_ExReleaseFastResource
0x1400392db  nop     dword ptr [rax+rax+00h]
0x1400392e0  movzx   edx, [rsp+0D8h+var_B7]
0x1400392e5  mov     r8d, 802h
0x1400392eb  mov     r12, [rsp+0D8h+arg_10]
0x1400392f3  mov     ecx, 0Ah
0x1400392f8  mov     ebx, 0C00000D8h
0x1400392fd  mov     eax, edi
0x1400392ff  and     eax, 10h
0x140039302  mov     dword ptr [rsp+0D8h+var_90], eax
0x140039306  jnz     loc_1400393FA
0x14003930c  mov     r13d, edi
0x14003930f  and     r13d, 2
0x140039313  mov     [rsp+0D8h+var_A0], r13d
0x140039318  test    dil, 8
0x14003931c  jnz     loc_140038FF2
0x140039322  mov     r15d, 1
0x140039328  mov     [rsp+0D8h+var_9C], r15d
0x14003932d  xor     r12d, r12d
0x140039330  mov     [rsp+0D8h+var_98], r12d
0x140039335  test    r13d, r13d
0x140039338  jnz     loc_14003947D
0x14003933e  test    dil, 4
0x140039342  jnz     loc_14003949D
0x140039348  movzx   ebx, byte ptr [rsi+8]
0x14003934c  and     bl, r15b
0x14003934f  jz      loc_14003947F
0x140039355  mov     [rsp+0D8h+var_48], r14
0x14003935d  cmp     [r14], r8w
0x140039361  jnz     loc_140039471
0x140039367  mov     rcx, r14
0x14003936a  mov     rcx, [rcx+58h]
0x14003936e  add     rcx, 40h ; '@'
0x140039372  movzx   r8d, bl
0x140039376  xor     edx, edx
0x140039378  call    cs:__imp_ExAcquireFastResourceExclusive
0x14003937f  nop     dword ptr [rax+rax+00h]
0x140039384  test    al, al
0x140039386  jz      loc_14003950C
0x14003938c  test    dil, 1
0x140039390  jz      short loc_1400393B8
0x140039392  lea     rcx, [r14+40h]
0x140039396  cmp     qword ptr [rcx], 0
0x14003939a  jnz     loc_140039465
0x1400393a0  lea     rax, [rsi+70h]
0x1400393a4  mov     rdx, [rax]
0x1400393a7  cmp     [rdx+8], rax
0x1400393ab  jz      loc_140039457
0x1400393b1  mov     ecx, 3
0x1400393b6  int     29h; Win8: RtlFailFast(ecx)
0x1400393b8  test    byte ptr [r14+8], 1
0x1400393bd  jnz     short loc_1400393D6
0x1400393bf  mov     rax, [rsp+0D8h+arg_10]
0x1400393c7  test    rax, rax
0x1400393ca  jz      short loc_140039392
0x1400393cc  mov     eax, [rax+12Ch]
0x1400393d2  test    al, 40h
0x1400393d4  jz      short loc_140039392
0x1400393d6  movzx   eax, byte ptr [rsi+28h]
0x1400393da  sub     al, 2
0x1400393dc  test    al, 0EFh
0x1400393de  jz      short loc_140039392
0x1400393e0  mov     [rsp+0D8h+var_90], r14
0x1400393e5  mov     rdx, r14
0x1400393e8  mov     rcx, rsi
0x1400393eb  call    ?RefsReleaseResource@@YAXPEAU_IRP_CONTEXT@@UPFCBOrSCB@@@Z; RefsReleaseResource(_IRP_CONTEXT *,PFCBOrSCB)
0x1400393f0  mov     ebx, 0C0000123h
0x1400393f5  jmp     loc_1400398C8
0x1400393fa  cmp     qword ptr [r14+60h], 0
0x1400393ff  jz      loc_14003930C
0x140039405  mov     [rsp+0D8h+var_58], r14
0x14003940d  cmp     [r14], r8w
0x140039411  jnz     loc_14003954B
0x140039417  mov     rcx, r14
0x14003941a  movzx   r8d, dl
0x14003941e  xor     edx, edx
0x140039420  mov     rcx, [rcx+60h]
0x140039424  call    cs:__imp_ExAcquireFastResourceExclusive
0x14003942b  nop     dword ptr [rax+rax+00h]
0x140039430  test    al, al
0x140039432  jz      loc_140039557
0x140039438  test    dil, 20h
0x14003943c  jnz     short loc_140039442
0x14003943e  mov     [rsi+38h], r14
0x140039442  mov     [rsp+0D8h+var_B6], 1
0x140039447  mov     ecx, 0Ah
0x14003944c  mov     r8d, 802h
0x140039452  jmp     loc_14003930C
0x140039457  mov     [rcx], rdx
0x14003945a  mov     [rcx+8], rax
0x14003945e  mov     [rdx+8], rcx
0x140039462  mov     [rax], rcx
  ... truncated ...
```
