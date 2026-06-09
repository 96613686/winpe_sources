# RefsSpecialDispatch(void *)

- ea: `0x140040b20`
- end: `0x140041278`
- name: `?RefsSpecialDispatch@@YAXPEAX@Z`
- size: `1880`
- prototype: `void __fastcall(struct _IRP_CONTEXT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14003a520`
- `0x14003ec10`
- `0x140040410`
- `0x140040b20`
- `0x140041b40`
- `0x1400a648c`
- `0x1400b2d58`
- `0x1401e9ce0`
- `0x1401e9dc0`
- `0x140286ebc`
- `0x14031ac80`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140040be4`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140040f9b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140040be4`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140040f9b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140040c55`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140040fb3`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140040c55`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140040fb3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140040b6f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140040b6f`
- `ntoskrnl!IoClearActivityIdThread` at `0x140040ec9`
- `ntoskrnl!IoClearActivityIdThread` at `0x140040ec9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140040f23`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140040f23`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140040eb8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004110e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140040eb8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004110e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14004123b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14004123b`
- `ntoskrnl!IoSetActivityIdThread` at `0x140040bc5`
- `ntoskrnl!IoSetActivityIdThread` at `0x140040bc5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040edc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040edc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040f0e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040f0e`
- `ntoskrnl!IoWithinStackLimits` at `0x140040bfb`
- `ntoskrnl!IoWithinStackLimits` at `0x140040bfb`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140041057`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140041057`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140041066`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140041066`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401eaf0b`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401eaf0b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400410a2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400410a2`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400410ae`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400410ae`
- `ntoskrnl!ExReleaseFastResource` at `0x140040d47`
- `ntoskrnl!ExReleaseFastResource` at `0x140040d64`
- `ntoskrnl!ExReleaseFastResource` at `0x140040d47`
- `ntoskrnl!ExReleaseFastResource` at `0x140040d64`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040f8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004121a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004124d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041260`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040f8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004121a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004124d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041260`

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
0x140040b20  mov     r11, rsp
0x140040b23  mov     [r11+10h], rbx
0x140040b27  mov     [r11+18h], rsi
0x140040b2b  push    rdi
0x140040b2c  push    r12
0x140040b2e  push    r13
0x140040b30  push    r14
0x140040b32  push    r15
0x140040b34  sub     rsp, 0A0h
0x140040b3b  mov     rax, cs:__security_cookie
0x140040b42  xor     rax, rsp
0x140040b45  mov     [rsp+0C8h+var_30], rax
0x140040b4d  mov     rbx, rcx
0x140040b50  mov     [rsp+0C8h+var_98], rcx
0x140040b55  xorps   xmm0, xmm0
0x140040b58  xor     eax, eax
0x140040b5a  movups  [rsp+0C8h+var_90], xmm0
0x140040b5f  mov     [r11-80h], rax
0x140040b63  xorps   xmm1, xmm1
0x140040b66  movups  xmmword ptr [r11-48h], xmm1
0x140040b6b  mov     [r11-38h], rax
0x140040b6f  call    cs:__imp_KeEnterCriticalRegion
0x140040b76  nop     dword ptr [rax+rax+00h]
0x140040b7b  xor     r12d, r12d
0x140040b7e  mov     rax, [rbx+40h]
0x140040b82  mov     [rsp+0C8h+var_60], rax
0x140040b87  lea     r13, [rbx+90h]
0x140040b8e  mov     [rsp+0C8h+var_70], r13
0x140040b93  mov     r14, [r13+0]
0x140040b97  mov     [rsp+0C8h+var_78], r14
0x140040b9c  mov     r15, [rbx+48h]
0x140040ba0  mov     [rsp+0C8h+var_68], r15
0x140040ba5  mov     [r13+0], r12
0x140040ba9  mov     [rbx+48h], r12
0x140040bad  mov     rcx, [rbx+50h]
0x140040bb1  test    rcx, rcx
0x140040bb4  jnz     loc_1400411DF
0x140040bba  mov     rcx, r12
0x140040bbd  mov     [rsp+0C8h+var_48], rcx
0x140040bc5  call    cs:__imp_IoSetActivityIdThread
0x140040bcc  nop     dword ptr [rax+rax+00h]
0x140040bd1  mov     [rsp+0C8h+var_50], rax
0x140040bd6  lea     rax, [rbx+70h]
0x140040bda  mov     [rbx+78h], rax
0x140040bde  mov     [rax], rax
0x140040be1  xor     sil, sil
0x140040be4  call    cs:__imp_IoGetTopLevelIrp
0x140040beb  nop     dword ptr [rax+rax+00h]
0x140040bf0  mov     rdi, rax
0x140040bf3  mov     edx, 18h; RegionSize
0x140040bf8  mov     rcx, rax; RegionStart
0x140040bfb  call    cs:__imp_IoWithinStackLimits
0x140040c02  nop     dword ptr [rax+rax+00h]
0x140040c07  test    eax, eax
0x140040c09  jnz     loc_14004117B
0x140040c0f  mov     dword ptr [rsp+0C8h+var_90+4], r12d
0x140040c14  mov     qword ptr [rsp+0C8h+var_90+8], rdi
0x140040c19  mov     [rsp+0C8h+var_80], r12
0x140040c1e  mov     byte ptr [rsp+0C8h+var_90], 1
0x140040c23  test    sil, sil
0x140040c26  jnz     loc_1400411C5
0x140040c2c  mov     word ptr [rsp+0C8h+var_90+1], 0
0x140040c33  mov     dword ptr [rsp+0C8h+var_90+4], 5346ABBAh
0x140040c3b  mov     [rsp+0C8h+var_80], rbx
0x140040c40  lea     rsi, [rbx+8]
0x140040c44  mov     [rsp+0C8h+var_A0], rsi
0x140040c49  or      qword ptr [rsi], 100000h
0x140040c50  lea     rcx, [rsp+0C8h+var_90]; Irp
0x140040c55  call    cs:__imp_IoSetTopLevelIrp
0x140040c5c  nop     dword ptr [rax+rax+00h]
0x140040c61  lea     rcx, [rbx+68h]
0x140040c65  mov     [rsp+0C8h+var_58], rcx
0x140040c6a  mov     rax, [rsp+0C8h+var_80]
0x140040c6f  mov     [rcx], rax
0x140040c72  or      qword ptr [rsi], 10000h
0x140040c79  xor     dil, dil
0x140040c7c  mov     [rsp+0C8h+var_A8], dil
0x140040c81  test    rbx, rbx
0x140040c84  jz      short loc_140040C8E
0x140040c86  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140040c89  call    ?RefsPreRequestProcessingExtend@@YAXPEAU_IRP_CONTEXT@@J@Z; RefsPreRequestProcessingExtend(_IRP_CONTEXT *,long)
0x140040c8e  mov     rdx, r15
0x140040c91  mov     rcx, rbx
0x140040c94  mov     rax, r14
0x140040c97  call    _guard_dispatch_icall
0x140040c9c  xor     r8d, r8d; Status
0x140040c9f  xor     edx, edx; Irp
0x140040ca1  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140040ca4  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x140040ca9  jmp     short loc_140040CEC
0x140040cab  mov     r8d, eax; int
0x140040cae  xor     edx, edx; struct _IRP *
0x140040cb0  mov     rbx, [rsp+0C8h+var_98]
0x140040cb5  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140040cb8  call    ?RefsProcessException@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsProcessException(_IRP_CONTEXT *,_IRP *,long)
0x140040cbd  cmp     eax, 0C00000D8h
0x140040cc2  jz      short loc_140040CD7
0x140040cc4  cmp     eax, 0C00001A8h
0x140040cc9  jz      short loc_140040CD7
0x140040ccb  cmp     eax, 0C0000188h
0x140040cd0  movzx   edi, [rsp+0C8h+var_A8]
0x140040cd5  jnz     short loc_140040CDA
0x140040cd7  mov     dil, 1
0x140040cda  xor     r12d, r12d
0x140040cdd  mov     r14, [rsp+0C8h+var_78]
0x140040ce2  mov     r15, [rsp+0C8h+var_68]
0x140040ce7  mov     rsi, [rsp+0C8h+var_A0]
0x140040cec  test    dil, dil
0x140040cef  jnz     short loc_140040C79
0x140040cf1  mov     rdi, [rsp+0C8h+var_60]
0x140040cf6  and     qword ptr [rsi], 0FFFFFFFFFFFEFFFFh
0x140040cfd  mov     r8b, 1; unsigned __int8
0x140040d00  mov     rdx, rdi; struct _VCB *
0x140040d03  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140040d06  cmp     dword ptr [rbx+4], 0
0x140040d0a  jge     short loc_140040D72
0x140040d0c  call    ?RefsAcquireSharedVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireSharedVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x140040d11  lock dec dword ptr [rdi+0E4h]
0x140040d18  lock dec dword ptr [rdi+0DCh]
0x140040d1f  cmp     dword ptr [rbx+4], 0
0x140040d23  jge     short loc_140040D55
0x140040d25  mov     rax, [rsp+0C8h+var_58]
0x140040d2a  mov     rdx, [rax]
0x140040d2d  lea     rcx, [rdi+520h]
0x140040d34  add     rdx, 0A0h
0x140040d3b  jz      short loc_140040D62
0x140040d3d  add     dword ptr [rdx+48h], 0FFFFFFFFh
0x140040d41  jnz     short loc_140040D79
0x140040d43  and     dword ptr [rdx+4Ch], 0FFFFFFFDh
0x140040d47  call    cs:__imp_ExReleaseFastResource
0x140040d4e  nop     dword ptr [rax+rax+00h]
0x140040d53  jmp     short loc_140040D79
0x140040d55  mov     rdx, rdi; struct _VCB *
0x140040d58  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140040d5b  call    ?RefsReleaseVcbCheckDelete@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@@Z; RefsReleaseVcbCheckDelete(_IRP_CONTEXT *,_VCB *)
0x140040d60  jmp     short loc_140040D79
0x140040d62  xor     edx, edx
0x140040d64  call    cs:__imp_ExReleaseFastResource
0x140040d6b  nop     dword ptr [rax+rax+00h]
0x140040d70  jmp     short loc_140040D79
0x140040d72  call    ?RefsAcquireExclusiveVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireExclusiveVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x140040d77  jmp     short loc_140040D11
0x140040d79  jmp     short loc_140040D88
0x140040d7b  xor     r12d, r12d
0x140040d7e  mov     rbx, [rsp+0C8h+var_98]
0x140040d83  mov     rsi, [rsp+0C8h+var_A0]
0x140040d88  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140040d8b  call    ?RefsReleaseAllResources@@YAXPEAU_IRP_CONTEXT@@@Z; RefsReleaseAllResources(_IRP_CONTEXT *)
0x140040d90  lea     r14, [rbx+280h]
0x140040d97  mov     rax, [r14]
0x140040d9a  mov     r15, r12
0x140040d9d  cmp     rax, r14
0x140040da0  jz      short loc_140040DBA
0x140040da2  cmp     rax, r14
0x140040da5  jz      short loc_140040DBA
0x140040da7  mov     edx, 827h
0x140040dac  cmp     [rax-8], dx
0x140040db0  jnz     loc_14004116C
0x140040db6  lea     r15, [rax-8]
0x140040dba  test    r15, r15
0x140040dbd  jnz     loc_140041010
0x140040dc3  mov     rcx, [rbx+258h]; P
0x140040dca  test    rcx, rcx
0x140040dcd  jnz     loc_14004120E
0x140040dd3  mov     ecx, [rbx+4]
0x140040dd6  bt      ecx, 0Ah
0x140040dda  jb      loc_140040FCB
0x140040de0  mov     rax, [rsi]
0x140040de3  bt      rax, 10h
0x140040de8  jb      loc_140040FCB
0x140040dee  bt      rax, 29h ; ')'
0x140040df3  jnb     short loc_140040E0C
0x140040df5  and     dword ptr [rbx+0ECh], 0FFFFFFFEh
0x140040dfc  mov     rcx, 0FFFFFDFFFFFFFFFFh
0x140040e06  and     rax, rcx
0x140040e09  mov     [rsi], rax
0x140040e0c  cmp     qword ptr [rbx+150h], 0
0x140040e14  jz      short loc_140040E24
0x140040e16  and     dword ptr [rbx+144h], 0FFFFFFFEh
0x140040e1d  mov     [rbx+150h], r12
0x140040e24  lea     rdi, [rbx+240h]
0x140040e2b  mov     rcx, [rdi]
0x140040e2e  cmp     rcx, rdi
0x140040e31  jnz     loc_140040F66
0x140040e37  mov     [rbx+160h], r12
0x140040e3e  mov     [rbx+1D0h], r12
0x140040e45  mov     [rbx+250h], r12d
0x140040e4c  mov     r13, [rsp+0C8h+var_70]
0x140040e51  test    byte ptr [rsi], 20h
0x140040e54  jnz     loc_140041237
0x140040e5a  mov     [r13+0], r12
0x140040e5e  mov     eax, [rsi]
0x140040e60  bt      rax, 14h
0x140040e65  jb      loc_140040F9B
0x140040e6b  mov     rcx, [rbx+2C8h]; P
0x140040e72  test    rcx, rcx
0x140040e75  jnz     loc_14004125E
0x140040e7b  mov     eax, [rsi]
0x140040e7d  bt      rax, 13h
0x140040e82  jnb     short loc_140040EC4
0x140040e84  mov     eax, [rbx-8]
0x140040e87  mov     ecx, 680h
0x140040e8c  cmp     [rbx+2], cx
0x140040e90  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x140040e96  jz      loc_140040FEE
0x140040e9c  mov     r9, cs:?RefsIrpContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsIrpContextLookasideList
0x140040ea3  cmp     eax, ecx
0x140040ea5  jnb     loc_140040FFD
0x140040eab  mov     ecx, eax
0x140040ead  shl     rcx, 7
0x140040eb1  add     rcx, r9; Lookaside
0x140040eb4  lea     rdx, [rbx-8]; Entry
0x140040eb8  call    cs:__imp_ExFreeToNPagedLookasideList
0x140040ebf  nop     dword ptr [rax+rax+00h]
0x140040ec4  mov     rcx, [rsp+0C8h+var_50]
0x140040ec9  call    cs:__imp_IoClearActivityIdThread
0x140040ed0  nop     dword ptr [rax+rax+00h]
0x140040ed5  lea     rcx, ?RefsScavengerLock@@3_KA; SpinLock
0x140040edc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140040ee3  nop     dword ptr [rax+rax+00h]
0x140040ee8  mov     rbx, cs:?RefsScavengerWorkList@@3PEAU_IRP_CONTEXT@@EA; _IRP_CONTEXT * RefsScavengerWorkList
0x140040eef  mov     [rsp+0C8h+var_98], rbx
0x140040ef4  test    rbx, rbx
0x140040ef7  jz      short loc_140040F5D
0x140040ef9  mov     rcx, [rbx+70h]
0x140040efd  mov     cs:?RefsScavengerWorkList@@3PEAU_IRP_CONTEXT@@EA, rcx; _IRP_CONTEXT * RefsScavengerWorkList
0x140040f04  movzx   edx, al; NewIrql
0x140040f07  lea     rcx, ?RefsScavengerLock@@3_KA; SpinLock
0x140040f0e  call    cs:__imp_KeReleaseSpinLock
0x140040f15  nop     dword ptr [rax+rax+00h]
0x140040f1a  test    rbx, rbx
0x140040f1d  jnz     loc_140040B7E
0x140040f23  call    cs:__imp_KeLeaveCriticalRegion
0x140040f2a  nop     dword ptr [rax+rax+00h]
0x140040f2f  mov     rcx, [rsp+0C8h+var_30]
0x140040f37  xor     rcx, rsp; StackCookie
0x140040f3a  call    __security_check_cookie
0x140040f3f  lea     r11, [rsp+0C8h+var_28]
0x140040f47  mov     rbx, [r11+38h]
0x140040f4b  mov     rsi, [r11+40h]
0x140040f4f  mov     rsp, r11
0x140040f52  pop     r15
0x140040f54  pop     r14
0x140040f56  pop     r13
0x140040f58  pop     r12
0x140040f5a  pop     rdi
0x140040f5b  retn
0x140040f5d  mov     cs:?RefsScavengerRunning@@3EA, 0; uchar RefsScavengerRunning
0x140040f64  jmp     short loc_140040F04
0x140040f66  cmp     [rcx+8], rdi
0x140040f6a  jnz     loc_140041174
0x140040f70  mov     rax, [rcx]
0x140040f73  cmp     [rax+8], rcx
0x140040f77  jnz     loc_140041174
0x140040f7d  mov     [rdi], rax
0x140040f80  mov     [rax+8], rdi
0x140040f84  add     rcx, 0FFFFFFFFFFFFFFA0h; P
0x140040f88  xor     edx, edx; Tag
0x140040f8a  call    cs:__imp_ExFreePoolWithTag
0x140040f91  nop     dword ptr [rax+rax+00h]
0x140040f96  jmp     loc_140040E2B
0x140040f9b  call    cs:__imp_IoGetTopLevelIrp
0x140040fa2  nop     dword ptr [rax+rax+00h]
0x140040fa7  mov     [rax+4], r12d
0x140040fab  mov     [rax+10h], r12
0x140040faf  mov     rcx, [rax+8]; Irp
0x140040fb3  call    cs:__imp_IoSetTopLevelIrp
0x140040fba  nop     dword ptr [rax+rax+00h]
0x140040fbf  and     qword ptr [rsi], 0FFFFFFFFFFEFFFFFh
0x140040fc6  jmp     loc_140040E6B
0x140040fcb  bt      ecx, 12h
0x140040fcf  jb      loc_14004115E
0x140040fd5  and     ecx, 0BFF9C0C5h
0x140040fdb  mov     [rbx+4], ecx
0x140040fde  and     qword ptr [rsi], 0FFFFFFFFFFFFFBFFh
0x140040fe5  mov     [rbx+10h], r12d
0x140040fe9  jmp     loc_140040EC4
0x140040fee  mov     r9, cs:?RefsIrpAndIoContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsIrpAndIoContextLookasideList
0x140040ff5  cmp     eax, ecx
0x140040ff7  jb      loc_140040EAB
0x140040ffd  xor     edx, edx
0x140040fff  div     ecx
0x140041001  mov     eax, edx
0x140041003  jmp     loc_140040EAB
0x140041010  mov     [rsp+0C8h+var_A0], r12
0x140041015  lea     r13, [r15+8]
0x140041019  cmp     [r14], r14
0x14004101c  jnz     loc_14004112D
0x140041022  mov     rcx, [r15+30h]
0x140041026  test    rcx, rcx
0x140041029  jz      loc_1400410BA
0x14004102f  mov     edx, [rcx+98h]
0x140041035  and     edx, 2000h
0x14004103b  jnz     loc_14004119D
0x140041041  mov     eax, [rcx+12Ch]
0x140041047  test    al, 40h
0x140041049  jnz     loc_14004119D
0x14004104f  mov     rax, [r15+30h]
0x140041053  mov     rdi, [rax+30h]
0x140041057  call    cs:__imp_KeEnterGuardedRegion
  ... truncated ...
```
