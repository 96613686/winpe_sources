# RefsSpecialDispatch(void *)

- ea: `0x14000d0c0`
- end: `0x14000d818`
- name: `?RefsSpecialDispatch@@YAXPEAX@Z`
- size: `1880`
- prototype: `void __fastcall(struct _IRP_CONTEXT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14000b1b0`
- `0x14000c9b0`
- `0x14000d0c0`
- `0x14000e0e0`
- `0x14009a130`
- `0x1400a069c`
- `0x1400aecd8`
- `0x1401f3fb0`
- `0x1401f4090`
- `0x14028debc`
- `0x14031def0`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14000d184`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000d53b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000d184`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000d53b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000d1f5`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000d553`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000d1f5`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000d553`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d10f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d10f`
- `ntoskrnl!IoClearActivityIdThread` at `0x14000d469`
- `ntoskrnl!IoClearActivityIdThread` at `0x14000d469`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d4c3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d4c3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000d458`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000d6ae`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000d458`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000d6ae`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000d7db`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000d7db`
- `ntoskrnl!IoSetActivityIdThread` at `0x14000d165`
- `ntoskrnl!IoSetActivityIdThread` at `0x14000d165`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d47c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d47c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d4ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d4ae`
- `ntoskrnl!IoWithinStackLimits` at `0x14000d19b`
- `ntoskrnl!IoWithinStackLimits` at `0x14000d19b`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000d5f7`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000d5f7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000d606`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000d606`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401f4afb`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401f4afb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000d642`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000d642`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000d64e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000d64e`
- `ntoskrnl!ExReleaseFastResource` at `0x14000d2e7`
- `ntoskrnl!ExReleaseFastResource` at `0x14000d304`
- `ntoskrnl!ExReleaseFastResource` at `0x14000d2e7`
- `ntoskrnl!ExReleaseFastResource` at `0x14000d304`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d52a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d800`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d52a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d800`

## pseudocode

```c
void __fastcall RefsSpecialDispatch(struct _IRP_CONTEXT *a1)
{
  void (__fastcall *v2)(_QWORD, _QWORD); // r14
  __int64 v3; // r15
  _QWORD *v4; // rcx
  char *v5; // rcx
  bool v6; // si
  ULONG_PTR TopLevelIrp; // rdi
  unsigned __int64 *v8; // rsi
  int v9; // edx
  volatile signed __int32 *v10; // rdi
  volatile signed __int32 *v11; // rcx
  __int64 v12; // rdx
  struct _IRP_CONTEXT *v14; // r14
  struct _IRP_CONTEXT *v15; // rax
  _QWORD *v16; // r15
  _QWORD *j; // rcx
  int v18; // ecx
  unsigned __int64 v19; // rax
  _QWORD **v20; // rdi
  _QWORD *v21; // rcx
  PVOID *v22; // r13
  void *v23; // rcx
  unsigned int v24; // eax
  struct _NPAGED_LOOKASIDE_LIST *v25; // r9
  KIRQL v26; // al
  _QWORD *v27; // rax
  PIRP v28; // rax
  struct _IRP_CONTEXT **v29; // r13
  __int64 v30; // rcx
  struct _FAST_MUTEX *v31; // rdi
  struct _IRP_CONTEXT *v32; // rcx
  struct _IRP_CONTEXT **v33; // rax
  unsigned int v34; // eax
  struct _IRP_CONTEXT *i; // rcx
  _QWORD *v36; // [rsp+28h] [rbp-A0h]
  __int128 v37; // [rsp+38h] [rbp-90h] BYREF
  struct _IRP_CONTEXT *v38; // [rsp+48h] [rbp-80h]
  void (__fastcall *v39)(_QWORD, _QWORD); // [rsp+50h] [rbp-78h]
  PSECURITY_SUBJECT_CONTEXT *v40; // [rsp+58h] [rbp-70h]
  __int64 v41; // [rsp+60h] [rbp-68h]
  struct _VCB *v42; // [rsp+68h] [rbp-60h]
  char *v43; // [rsp+70h] [rbp-58h]
  __int64 v44; // [rsp+78h] [rbp-50h]
  __int128 v45; // [rsp+80h] [rbp-48h] BYREF
  __int64 v46; // [rsp+90h] [rbp-38h]

  v37 = 0;
  v38 = 0;
  v45 = 0;
  v46 = 0;
  KeEnterCriticalRegion();
  do
  {
    v42 = (struct _VCB *)*((_QWORD *)a1 + 8);
    v40 = (PSECURITY_SUBJECT_CONTEXT *)((char *)a1 + 144);
    v2 = (void (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)a1 + 18);
    v39 = v2;
    v3 = *((_QWORD *)a1 + 9);
    v41 = v3;
    *((_QWORD *)a1 + 18) = 0;
    *((_QWORD *)a1 + 9) = 0;
    v4 = (_QWORD *)*((_QWORD *)a1 + 10);
    if ( v4 )
    {
      *((_QWORD *)&v45 + 1) = *v4;
      v46 = v4[1];
      v5 = (char *)&v45 + 8;
    }
    else
    {
      v5 = 0;
    }
    *(_QWORD *)&v45 = v5;
    v44 = IoSetActivityIdThread(v5);
    *((_QWORD *)a1 + 15) = (char *)a1 + 112;
    *((_QWORD *)a1 + 14) = (char *)a1 + 112;
    v6 = 0;
    TopLevelIrp = (ULONG_PTR)IoGetTopLevelIrp();
    if ( IoWithinStackLimits(TopLevelIrp, 0x18u) && (TopLevelIrp & 3) == 0 )
      v6 = *(_DWORD *)(TopLevelIrp + 4) == 1397140410;
    DWORD1(v37) = 0;
    *((_QWORD *)&v37 + 1) = TopLevelIrp;
    v38 = 0;
    LOBYTE(v37) = 1;
    if ( v6 )
    {
      BYTE1(v37) = 1;
      BYTE2(v37) = *(_BYTE *)(TopLevelIrp + 2);
    }
    else
    {
      *(_WORD *)((char *)&v37 + 1) = 0;
    }
    DWORD1(v37) = 1397140410;
    v38 = a1;
    v8 = (unsigned __int64 *)((char *)a1 + 8);
    *((_QWORD *)a1 + 1) |= 0x100000uLL;
    IoSetTopLevelIrp((PIRP)&v37);
    v43 = (char *)a1 + 104;
    *((_QWORD *)a1 + 13) = v38;
    *((_QWORD *)a1 + 1) |= 0x10000uLL;
    if ( a1 )
      RefsPreRequestProcessingExtend(a1, v9);
    v2(a1, v3);
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, 0, 0);
    v10 = (volatile signed __int32 *)v42;
    *v8 &= ~0x10000uLL;
    if ( *((int *)a1 + 1) >= 0 )
      RefsAcquireExclusiveVcb(a1, (struct _VCB *)v10, 1u);
    else
      RefsAcquireSharedVcb(a1, (struct _VCB *)v10, 1u);
    _InterlockedDecrement(v10 + 57);
    _InterlockedDecrement(v10 + 55);
    if ( *((int *)a1 + 1) >= 0 )
    {
      RefsReleaseVcbCheckDelete(a1, (struct _VCB *)v10);
    }
    else
    {
      v11 = v10 + 328;
      v12 = *(_QWORD *)v43 + 160LL;
      if ( *(_QWORD *)v43 == -160 )
      {
        ExReleaseFastResource(v11, 0);
      }
      else if ( (*(_DWORD *)(*(_QWORD *)v43 + 232LL))-- == 1 )
      {
        *(_DWORD *)(v12 + 76) &= ~2u;
        ExReleaseFastResource(v11, v12);
      }
    }
    RefsReleaseAllResources(a1);
    v14 = (struct _IRP_CONTEXT *)((char *)a1 + 640);
    v15 = (struct _IRP_CONTEXT *)*((_QWORD *)a1 + 80);
    v16 = 0;
    if ( v15 != (struct _IRP_CONTEXT *)((char *)a1 + 640) )
    {
      while ( v15 != v14 )
      {
        if ( *((_WORD *)v15 - 4) == 2087 )
        {
          v16 = (_QWORD *)((char *)v15 - 8);
          break;
        }
        v15 = *(struct _IRP_CONTEXT **)v15;
      }
    }
    if ( v16 )
    {
      do
      {
        v36 = 0;
        v29 = (struct _IRP_CONTEXT **)(v16 + 1);
        if ( *(struct _IRP_CONTEXT **)v14 != v14 )
        {
          for ( i = *v29; ; i = *(struct _IRP_CONTEXT **)i )
          {
            v29 = (struct _IRP_CONTEXT **)(v16 + 1);
            if ( i == v14 )
              break;
            if ( *((_WORD *)i - 4) == 2087 )
            {
              v36 = (_QWORD *)((char *)i - 8);
              break;
            }
          }
        }
        v30 = v16[6];
        if ( v30 )
        {
          if ( ((*(_DWORD *)(v30 + 152) & 0x2000) != 0 || (*(_DWORD *)(v30 + 300) & 0x40) != 0)
            && (*(_DWORD *)(v30 + 152) & 0x2000) != 0 )
          {
            _InterlockedAnd((volatile signed __int32 *)(v30 + 152), 0xFFFFDFFF);
          }
          v31 = *(struct _FAST_MUTEX **)(v16[6] + 48LL);
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(v31);
          _InterlockedIncrement((volatile signed __int32 *)(v16[6] + 172LL));
          *(_QWORD *)(v16[6] + 280LL) = 0;
          ++*(_DWORD *)(v16[6] + 172LL);
          ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(v16[6] + 48LL));
          KeLeaveGuardedRegion();
        }
        v32 = *v29;
        if ( *((struct _IRP_CONTEXT ***)*v29 + 1) != v29
          || (v33 = (struct _IRP_CONTEXT **)v16[2], *v33 != (struct _IRP_CONTEXT *)v29) )
        {
LABEL_74:
          __fastfail(3u);
        }
        *v33 = v32;
        *((_QWORD *)v32 + 1) = v33;
        if ( v16 != (_QWORD *)((char *)a1 + 728) )
        {
          v34 = *((_DWORD *)v16 - 2);
          if ( v34 >= RefsNumberProcessors )
            v34 %= RefsNumberProcessors;
          ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v34], v16 - 1);
        }
        v16 = v36;
      }
      while ( v36 );
    }
    for ( j = (_QWORD *)*((_QWORD *)a1 + 75); j; j = (_QWORD *)*((_QWORD *)a1 + 75) )
    {
      *((_QWORD *)a1 + 75) = *j;
      ExFreePoolWithTag(j, 0);
    }
    v18 = *((_DWORD *)a1 + 1);
    if ( (v18 & 0x400) != 0 || (v19 = *v8, (*v8 & 0x10000) != 0) )
    {
      if ( (v18 & 0x40000) != 0 )
      {
        *((_DWORD *)a1 + 1) = v18 & 0xFFFBFBFF;
      }
      else
      {
        *((_DWORD *)a1 + 1) = v18 & 0xBFF9C0C5;
        *v8 &= ~0x400uLL;
      }
      *((_DWORD *)a1 + 4) = 0;
    }
    else
    {
      if ( (v19 & 0x20000000000LL) != 0 )
      {
        *((_DWORD *)a1 + 59) &= ~1u;
        *v8 = v19 & 0xFFFFFDFFFFFFFFFFuLL;
      }
      if ( *((_QWORD *)a1 + 42) )
      {
        *((_DWORD *)a1 + 81) &= ~1u;
        *((_QWORD *)a1 + 42) = 0;
      }
      v20 = (_QWORD **)((char *)a1 + 576);
      while ( 1 )
      {
        v21 = *v20;
        if ( *v20 == v20 )
          break;
        if ( (_QWORD **)v21[1] != v20 )
          goto LABEL_74;
        v27 = (_QWORD *)*v21;
        if ( *(_QWORD **)(*v21 + 8LL) != v21 )
          goto LABEL_74;
        *v20 = v27;
        v27[1] = v20;
        ExFreePoolWithTag(v21 - 12, 0);
      }
      *((_QWORD *)a1 + 44) = 0;
      *((_QWORD *)a1 + 58) = 0;
      *((_DWORD *)a1 + 148) = 0;
      v22 = (PVOID *)v40;
      if ( (*(_BYTE *)v8 & 0x20) != 0 )
      {
        SeReleaseSubjectContext(*v40);
        ExFreePoolWithTag(*v22, 0);
      }
      *v22 = 0;
      if ( (*(_DWORD *)v8 & 0x100000) != 0 )
      {
        v28 = IoGetTopLevelIrp();
        *(_DWORD *)(&v28->Size + 1) = 0;
        *(_QWORD *)&v28->Flags = 0;
        IoSetTopLevelIrp((PIRP)v28->MdlAddress);
        *v8 &= ~0x100000uLL;
      }
      v23 = (void *)*((_QWORD *)a1 + 89);
      if ( v23 )
      {
        ExFreePoolWithTag(v23, 0);
        *((_QWORD *)a1 + 89) = 0;
      }
      if ( (*(_DWORD *)v8 & 0x80000) != 0 )
      {
        v24 = *((_DWORD *)a1 - 2);
        if ( *((_WORD *)a1 + 1) == 1664 )
        {
          v25 = RefsIrpAndIoContextLookasideList;
          if ( v24 < RefsNumberProcessors )
            goto LABEL_41;
        }
        else
        {
          v25 = RefsIrpContextLookasideList;
          if ( v24 < RefsNumberProcessors )
          {
LABEL_41:
            ExFreeToNPagedLookasideList(&v25[(unsigned __int64)v24], (char *)a1 - 8);
            goto LABEL_42;
          }
        }
        v24 %= RefsNumberProcessors;
        goto LABEL_41;
      }
    }
LABEL_42:
    IoClearActivityIdThread(v44);
    v26 = KeAcquireSpinLockRaiseToDpc(&RefsScavengerLock);
    a1 = RefsScavengerWorkList;
    if ( RefsScavengerWorkList )
      RefsScavengerWorkList = (struct _IRP_CONTEXT *)*((_QWORD *)RefsScavengerWorkList + 14);
    else
      RefsScavengerRunning = 0;
    KeReleaseSpinLock(&RefsScavengerLock, v26);
  }
  while ( a1 );
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14000d0c0  mov     r11, rsp
0x14000d0c3  mov     [r11+10h], rbx
0x14000d0c7  mov     [r11+18h], rsi
0x14000d0cb  push    rdi
0x14000d0cc  push    r12
0x14000d0ce  push    r13
0x14000d0d0  push    r14
0x14000d0d2  push    r15
0x14000d0d4  sub     rsp, 0A0h
0x14000d0db  mov     rax, cs:__security_cookie
0x14000d0e2  xor     rax, rsp
0x14000d0e5  mov     [rsp+0C8h+var_30], rax
0x14000d0ed  mov     rbx, rcx
0x14000d0f0  mov     [rsp+0C8h+var_98], rcx
0x14000d0f5  xorps   xmm0, xmm0
0x14000d0f8  xor     eax, eax
0x14000d0fa  movups  [rsp+0C8h+var_90], xmm0
0x14000d0ff  mov     [r11-80h], rax
0x14000d103  xorps   xmm1, xmm1
0x14000d106  movups  xmmword ptr [r11-48h], xmm1
0x14000d10b  mov     [r11-38h], rax
0x14000d10f  call    cs:__imp_KeEnterCriticalRegion
0x14000d116  nop     dword ptr [rax+rax+00h]
0x14000d11b  xor     r12d, r12d
0x14000d11e  mov     rax, [rbx+40h]
0x14000d122  mov     [rsp+0C8h+var_60], rax
0x14000d127  lea     r13, [rbx+90h]
0x14000d12e  mov     [rsp+0C8h+var_70], r13
0x14000d133  mov     r14, [r13+0]
0x14000d137  mov     [rsp+0C8h+var_78], r14
0x14000d13c  mov     r15, [rbx+48h]
0x14000d140  mov     [rsp+0C8h+var_68], r15
0x14000d145  mov     [r13+0], r12
0x14000d149  mov     [rbx+48h], r12
0x14000d14d  mov     rcx, [rbx+50h]
0x14000d151  test    rcx, rcx
0x14000d154  jnz     loc_14000D77F
0x14000d15a  mov     rcx, r12
0x14000d15d  mov     [rsp+0C8h+var_48], rcx
0x14000d165  call    cs:__imp_IoSetActivityIdThread
0x14000d16c  nop     dword ptr [rax+rax+00h]
0x14000d171  mov     [rsp+0C8h+var_50], rax
0x14000d176  lea     rax, [rbx+70h]
0x14000d17a  mov     [rbx+78h], rax
0x14000d17e  mov     [rax], rax
0x14000d181  xor     sil, sil
0x14000d184  call    cs:__imp_IoGetTopLevelIrp
0x14000d18b  nop     dword ptr [rax+rax+00h]
0x14000d190  mov     rdi, rax
0x14000d193  mov     edx, 18h; RegionSize
0x14000d198  mov     rcx, rax; RegionStart
0x14000d19b  call    cs:__imp_IoWithinStackLimits
0x14000d1a2  nop     dword ptr [rax+rax+00h]
0x14000d1a7  test    eax, eax
0x14000d1a9  jnz     loc_14000D71B
0x14000d1af  mov     dword ptr [rsp+0C8h+var_90+4], r12d
0x14000d1b4  mov     qword ptr [rsp+0C8h+var_90+8], rdi
0x14000d1b9  mov     [rsp+0C8h+var_80], r12
0x14000d1be  mov     byte ptr [rsp+0C8h+var_90], 1
0x14000d1c3  test    sil, sil
0x14000d1c6  jnz     loc_14000D765
0x14000d1cc  mov     word ptr [rsp+0C8h+var_90+1], 0
0x14000d1d3  mov     dword ptr [rsp+0C8h+var_90+4], 5346ABBAh
0x14000d1db  mov     [rsp+0C8h+var_80], rbx
0x14000d1e0  lea     rsi, [rbx+8]
0x14000d1e4  mov     [rsp+0C8h+var_A0], rsi
0x14000d1e9  or      qword ptr [rsi], 100000h
0x14000d1f0  lea     rcx, [rsp+0C8h+var_90]; Irp
0x14000d1f5  call    cs:__imp_IoSetTopLevelIrp
0x14000d1fc  nop     dword ptr [rax+rax+00h]
0x14000d201  lea     rcx, [rbx+68h]
0x14000d205  mov     [rsp+0C8h+var_58], rcx
0x14000d20a  mov     rax, [rsp+0C8h+var_80]
0x14000d20f  mov     [rcx], rax
0x14000d212  or      qword ptr [rsi], 10000h
0x14000d219  xor     dil, dil
0x14000d21c  mov     [rsp+0C8h+var_A8], dil
0x14000d221  test    rbx, rbx
0x14000d224  jz      short loc_14000D22E
0x14000d226  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14000d229  call    ?RefsPreRequestProcessingExtend@@YAXPEAU_IRP_CONTEXT@@J@Z; RefsPreRequestProcessingExtend(_IRP_CONTEXT *,long)
0x14000d22e  mov     rdx, r15
0x14000d231  mov     rcx, rbx
0x14000d234  mov     rax, r14
0x14000d237  call    _guard_dispatch_icall
0x14000d23c  xor     r8d, r8d; Status
0x14000d23f  xor     edx, edx; Irp
0x14000d241  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14000d244  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x14000d249  jmp     short loc_14000D28C
0x14000d24b  mov     r8d, eax; int
0x14000d24e  xor     edx, edx; struct _IRP *
0x14000d250  mov     rbx, [rsp+0C8h+var_98]
0x14000d255  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14000d258  call    ?RefsProcessException@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsProcessException(_IRP_CONTEXT *,_IRP *,long)
0x14000d25d  cmp     eax, 0C00000D8h
0x14000d262  jz      short loc_14000D277
0x14000d264  cmp     eax, 0C00001A8h
0x14000d269  jz      short loc_14000D277
0x14000d26b  cmp     eax, 0C0000188h
0x14000d270  movzx   edi, [rsp+0C8h+var_A8]
0x14000d275  jnz     short loc_14000D27A
0x14000d277  mov     dil, 1
0x14000d27a  xor     r12d, r12d
0x14000d27d  mov     r14, [rsp+0C8h+var_78]
0x14000d282  mov     r15, [rsp+0C8h+var_68]
0x14000d287  mov     rsi, [rsp+0C8h+var_A0]
0x14000d28c  test    dil, dil
0x14000d28f  jnz     short loc_14000D219
0x14000d291  mov     rdi, [rsp+0C8h+var_60]
0x14000d296  and     qword ptr [rsi], 0FFFFFFFFFFFEFFFFh
0x14000d29d  mov     r8b, 1; unsigned __int8
0x14000d2a0  mov     rdx, rdi; struct _VCB *
0x14000d2a3  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14000d2a6  cmp     dword ptr [rbx+4], 0
0x14000d2aa  jge     short loc_14000D312
0x14000d2ac  call    ?RefsAcquireSharedVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireSharedVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x14000d2b1  lock dec dword ptr [rdi+0E4h]
0x14000d2b8  lock dec dword ptr [rdi+0DCh]
0x14000d2bf  cmp     dword ptr [rbx+4], 0
0x14000d2c3  jge     short loc_14000D2F5
0x14000d2c5  mov     rax, [rsp+0C8h+var_58]
0x14000d2ca  mov     rdx, [rax]
0x14000d2cd  lea     rcx, [rdi+520h]
0x14000d2d4  add     rdx, 0A0h
0x14000d2db  jz      short loc_14000D302
0x14000d2dd  add     dword ptr [rdx+48h], 0FFFFFFFFh
0x14000d2e1  jnz     short loc_14000D319
0x14000d2e3  and     dword ptr [rdx+4Ch], 0FFFFFFFDh
0x14000d2e7  call    cs:__imp_ExReleaseFastResource
0x14000d2ee  nop     dword ptr [rax+rax+00h]
0x14000d2f3  jmp     short loc_14000D319
0x14000d2f5  mov     rdx, rdi; struct _VCB *
0x14000d2f8  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14000d2fb  call    ?RefsReleaseVcbCheckDelete@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@@Z; RefsReleaseVcbCheckDelete(_IRP_CONTEXT *,_VCB *)
0x14000d300  jmp     short loc_14000D319
0x14000d302  xor     edx, edx
0x14000d304  call    cs:__imp_ExReleaseFastResource
0x14000d30b  nop     dword ptr [rax+rax+00h]
0x14000d310  jmp     short loc_14000D319
0x14000d312  call    ?RefsAcquireExclusiveVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireExclusiveVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x14000d317  jmp     short loc_14000D2B1
0x14000d319  jmp     short loc_14000D328
0x14000d31b  xor     r12d, r12d
0x14000d31e  mov     rbx, [rsp+0C8h+var_98]
0x14000d323  mov     rsi, [rsp+0C8h+var_A0]
0x14000d328  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14000d32b  call    ?RefsReleaseAllResources@@YAXPEAU_IRP_CONTEXT@@@Z; RefsReleaseAllResources(_IRP_CONTEXT *)
0x14000d330  lea     r14, [rbx+280h]
0x14000d337  mov     rax, [r14]
0x14000d33a  mov     r15, r12
0x14000d33d  cmp     rax, r14
0x14000d340  jz      short loc_14000D35A
0x14000d342  cmp     rax, r14
0x14000d345  jz      short loc_14000D35A
0x14000d347  mov     edx, 827h
0x14000d34c  cmp     [rax-8], dx
0x14000d350  jnz     loc_14000D70C
0x14000d356  lea     r15, [rax-8]
0x14000d35a  test    r15, r15
0x14000d35d  jnz     loc_14000D5B0
0x14000d363  mov     rcx, [rbx+258h]; P
0x14000d36a  test    rcx, rcx
0x14000d36d  jnz     loc_14000D7AE
0x14000d373  mov     ecx, [rbx+4]
0x14000d376  bt      ecx, 0Ah
0x14000d37a  jb      loc_14000D56B
0x14000d380  mov     rax, [rsi]
0x14000d383  bt      rax, 10h
0x14000d388  jb      loc_14000D56B
0x14000d38e  bt      rax, 29h ; ')'
0x14000d393  jnb     short loc_14000D3AC
0x14000d395  and     dword ptr [rbx+0ECh], 0FFFFFFFEh
0x14000d39c  mov     rcx, 0FFFFFDFFFFFFFFFFh
0x14000d3a6  and     rax, rcx
0x14000d3a9  mov     [rsi], rax
0x14000d3ac  cmp     qword ptr [rbx+150h], 0
0x14000d3b4  jz      short loc_14000D3C4
0x14000d3b6  and     dword ptr [rbx+144h], 0FFFFFFFEh
0x14000d3bd  mov     [rbx+150h], r12
0x14000d3c4  lea     rdi, [rbx+240h]
0x14000d3cb  mov     rcx, [rdi]
0x14000d3ce  cmp     rcx, rdi
0x14000d3d1  jnz     loc_14000D506
0x14000d3d7  mov     [rbx+160h], r12
0x14000d3de  mov     [rbx+1D0h], r12
0x14000d3e5  mov     [rbx+250h], r12d
0x14000d3ec  mov     r13, [rsp+0C8h+var_70]
0x14000d3f1  test    byte ptr [rsi], 20h
0x14000d3f4  jnz     loc_14000D7D7
0x14000d3fa  mov     [r13+0], r12
0x14000d3fe  mov     eax, [rsi]
0x14000d400  bt      rax, 14h
0x14000d405  jb      loc_14000D53B
0x14000d40b  mov     rcx, [rbx+2C8h]; P
0x14000d412  test    rcx, rcx
0x14000d415  jnz     loc_14000D7FE
0x14000d41b  mov     eax, [rsi]
0x14000d41d  bt      rax, 13h
0x14000d422  jnb     short loc_14000D464
0x14000d424  mov     eax, [rbx-8]
0x14000d427  mov     ecx, 680h
0x14000d42c  cmp     [rbx+2], cx
0x14000d430  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x14000d436  jz      loc_14000D58E
0x14000d43c  mov     r9, cs:?RefsIrpContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsIrpContextLookasideList
0x14000d443  cmp     eax, ecx
0x14000d445  jnb     loc_14000D59D
0x14000d44b  mov     ecx, eax
0x14000d44d  shl     rcx, 7
0x14000d451  add     rcx, r9; Lookaside
0x14000d454  lea     rdx, [rbx-8]; Entry
0x14000d458  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000d45f  nop     dword ptr [rax+rax+00h]
0x14000d464  mov     rcx, [rsp+0C8h+var_50]
0x14000d469  call    cs:__imp_IoClearActivityIdThread
0x14000d470  nop     dword ptr [rax+rax+00h]
0x14000d475  lea     rcx, ?RefsScavengerLock@@3_KA; SpinLock
0x14000d47c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d483  nop     dword ptr [rax+rax+00h]
0x14000d488  mov     rbx, cs:?RefsScavengerWorkList@@3PEAU_IRP_CONTEXT@@EA; _IRP_CONTEXT * RefsScavengerWorkList
0x14000d48f  mov     [rsp+0C8h+var_98], rbx
0x14000d494  test    rbx, rbx
0x14000d497  jz      short loc_14000D4FD
0x14000d499  mov     rcx, [rbx+70h]
0x14000d49d  mov     cs:?RefsScavengerWorkList@@3PEAU_IRP_CONTEXT@@EA, rcx; _IRP_CONTEXT * RefsScavengerWorkList
0x14000d4a4  movzx   edx, al; NewIrql
0x14000d4a7  lea     rcx, ?RefsScavengerLock@@3_KA; SpinLock
0x14000d4ae  call    cs:__imp_KeReleaseSpinLock
0x14000d4b5  nop     dword ptr [rax+rax+00h]
0x14000d4ba  test    rbx, rbx
0x14000d4bd  jnz     loc_14000D11E
0x14000d4c3  call    cs:__imp_KeLeaveCriticalRegion
0x14000d4ca  nop     dword ptr [rax+rax+00h]
0x14000d4cf  mov     rcx, [rsp+0C8h+var_30]
0x14000d4d7  xor     rcx, rsp; StackCookie
0x14000d4da  call    __security_check_cookie
0x14000d4df  lea     r11, [rsp+0C8h+var_28]
0x14000d4e7  mov     rbx, [r11+38h]
0x14000d4eb  mov     rsi, [r11+40h]
0x14000d4ef  mov     rsp, r11
0x14000d4f2  pop     r15
0x14000d4f4  pop     r14
0x14000d4f6  pop     r13
0x14000d4f8  pop     r12
0x14000d4fa  pop     rdi
0x14000d4fb  retn
0x14000d4fd  mov     cs:?RefsScavengerRunning@@3EA, 0; uchar RefsScavengerRunning
0x14000d504  jmp     short loc_14000D4A4
0x14000d506  cmp     [rcx+8], rdi
0x14000d50a  jnz     loc_14000D714
0x14000d510  mov     rax, [rcx]
0x14000d513  cmp     [rax+8], rcx
0x14000d517  jnz     loc_14000D714
0x14000d51d  mov     [rdi], rax
0x14000d520  mov     [rax+8], rdi
0x14000d524  add     rcx, 0FFFFFFFFFFFFFFA0h; P
0x14000d528  xor     edx, edx; Tag
0x14000d52a  call    cs:__imp_ExFreePoolWithTag
0x14000d531  nop     dword ptr [rax+rax+00h]
0x14000d536  jmp     loc_14000D3CB
0x14000d53b  call    cs:__imp_IoGetTopLevelIrp
0x14000d542  nop     dword ptr [rax+rax+00h]
0x14000d547  mov     [rax+4], r12d
0x14000d54b  mov     [rax+10h], r12
0x14000d54f  mov     rcx, [rax+8]; Irp
0x14000d553  call    cs:__imp_IoSetTopLevelIrp
0x14000d55a  nop     dword ptr [rax+rax+00h]
0x14000d55f  and     qword ptr [rsi], 0FFFFFFFFFFEFFFFFh
0x14000d566  jmp     loc_14000D40B
0x14000d56b  bt      ecx, 12h
0x14000d56f  jb      loc_14000D6FE
0x14000d575  and     ecx, 0BFF9C0C5h
0x14000d57b  mov     [rbx+4], ecx
0x14000d57e  and     qword ptr [rsi], 0FFFFFFFFFFFFFBFFh
0x14000d585  mov     [rbx+10h], r12d
0x14000d589  jmp     loc_14000D464
0x14000d58e  mov     r9, cs:?RefsIrpAndIoContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsIrpAndIoContextLookasideList
0x14000d595  cmp     eax, ecx
0x14000d597  jb      loc_14000D44B
0x14000d59d  xor     edx, edx
0x14000d59f  div     ecx
0x14000d5a1  mov     eax, edx
0x14000d5a3  jmp     loc_14000D44B
0x14000d5b0  mov     [rsp+0C8h+var_A0], r12
0x14000d5b5  lea     r13, [r15+8]
0x14000d5b9  cmp     [r14], r14
0x14000d5bc  jnz     loc_14000D6CD
0x14000d5c2  mov     rcx, [r15+30h]
0x14000d5c6  test    rcx, rcx
0x14000d5c9  jz      loc_14000D65A
0x14000d5cf  mov     edx, [rcx+98h]
0x14000d5d5  and     edx, 2000h
0x14000d5db  jnz     loc_14000D73D
0x14000d5e1  mov     eax, [rcx+12Ch]
0x14000d5e7  test    al, 40h
0x14000d5e9  jnz     loc_14000D73D
0x14000d5ef  mov     rax, [r15+30h]
0x14000d5f3  mov     rdi, [rax+30h]
0x14000d5f7  call    cs:__imp_KeEnterGuardedRegion
  ... truncated ...
```
