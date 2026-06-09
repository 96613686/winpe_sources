# RefsFsdClose(_VOLUME_DEVICE_OBJECT *,_IRP *)

- ea: `0x1403391e0`
- end: `0x140339ae9`
- name: `?RefsFsdClose@@YAJPEAU_VOLUME_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `2313`
- prototype: `int(struct _VOLUME_DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x140039b60`
- `0x14003a520`
- `0x14003ec10`
- `0x140041b40`
- `0x14007dd30`
- `0x14008dbd0`
- `0x14008faf0`
- `0x1400a648c`
- `0x1400ca788`
- `0x1401e9ce0`
- `0x140301810`
- `0x14032c4c4`
- `0x140332c34`
- `0x1403389e4`
- `0x1403391e0`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x1403395a4`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140339907`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1403395a4`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140339907`
- `ntoskrnl!IofCompleteRequest` at `0x14033925d`
- `ntoskrnl!IofCompleteRequest` at `0x14033925d`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140339580`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14033991e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140339580`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14033991e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140339327`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140339327`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x140339346`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x140339346`
- `ntoskrnl!IoClearActivityIdThread` at `0x140339aa1`
- `ntoskrnl!IoClearActivityIdThread` at `0x140339aa1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140339aad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140339aad`
- `ntoskrnl!IoGetCurrentProcess` at `0x1403395b9`
- `ntoskrnl!IoGetCurrentProcess` at `0x1403395b9`
- `ntoskrnl!KeQueryPriorityThread` at `0x1403395e7`
- `ntoskrnl!KeQueryPriorityThread` at `0x1403395e7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140339a77`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140339a77`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140339361`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140339361`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140339371`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140339371`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1403394b4`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1403394b4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403393b3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403393b3`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403393bf`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403393bf`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1403396bf`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1403396bf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403399e2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140339a2f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403399e2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140339a2f`

## pseudocode

```c
__int64 __fastcall RefsFsdClose(struct _VOLUME_DEVICE_OBJECT *a1, struct _IRP *a2)
{
  PFILE_OBJECT FileObject; // rax
  _QWORD *FsContext; // rcx
  _QWORD *v6; // r15
  _BYTE *FsContext2; // rax
  __int64 v8; // r13
  char v9; // al
  __int64 v10; // rbx
  int v11; // eax
  PFILE_OBJECT v12; // rax
  struct _TOP_LEVEL_CONTEXT *v13; // rbx
  PFILE_OBJECT v14; // rdx
  __int16 v15; // cx
  unsigned int v16; // edi
  struct _IRP_CONTEXT *v17; // rsi
  struct _IRP_CONTEXT *v18; // rax
  unsigned int v19; // edx
  __int64 v20; // rbx
  PFILE_OBJECT v21; // rax
  PIRP TopLevelIrp; // rax
  unsigned __int8 v23; // si
  BOOLEAN *v24; // rdx
  __int64 v25; // rbx
  BOOLEAN *v26; // rbx
  _BYTE *v27; // r8
  __int64 v28; // r9
  int CompletionRoutine; // [rsp+20h] [rbp-108h]
  int PostIrpRoutine; // [rsp+28h] [rbp-100h]
  char v31; // [rsp+40h] [rbp-E8h]
  bool v32; // [rsp+41h] [rbp-E7h]
  __int64 v33; // [rsp+48h] [rbp-E0h]
  _BYTE *v34; // [rsp+50h] [rbp-D8h] BYREF
  struct _IRP_CONTEXT *v35; // [rsp+58h] [rbp-D0h] BYREF
  BOOLEAN *p_DeleteAccess; // [rsp+60h] [rbp-C8h] BYREF
  PFILE_OBJECT v37; // [rsp+68h] [rbp-C0h]
  int v38; // [rsp+70h] [rbp-B8h]
  struct _IRP *v39; // [rsp+78h] [rbp-B0h]
  __int64 v40; // [rsp+80h] [rbp-A8h]
  __int64 v41; // [rsp+88h] [rbp-A0h]
  _QWORD *v42; // [rsp+90h] [rbp-98h]
  _QWORD v43[5]; // [rsp+98h] [rbp-90h] BYREF
  PVOID *p_FsContext; // [rsp+C0h] [rbp-68h]
  BOOLEAN *p_WriteAccess; // [rsp+C8h] [rbp-60h]
  __int128 v46; // [rsp+D0h] [rbp-58h] BYREF
  __int64 v47; // [rsp+E0h] [rbp-48h]
  __int128 v48; // [rsp+E8h] [rbp-40h] BYREF

  v39 = a2;
  v46 = 0;
  v47 = 0;
  v35 = 0;
  v34 = 0;
  v48 = 0;
  v43[0] = 0;
  if ( *((_WORD *)a1 + 1) == 336 )
  {
    a2->IoStatus.Status = 0;
    a2->IoStatus.Information = 1;
    IofCompleteRequest(a2, 1);
    return 0;
  }
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  v37 = FileObject;
  v43[3] = FileObject;
  p_FsContext = &FileObject->FsContext;
  FsContext = FileObject->FsContext;
  v42 = FsContext;
  v6 = FsContext;
  v43[2] = FsContext;
  if ( FsContext )
  {
    v33 = FsContext[18];
    v40 = v33;
    FsContext2 = FileObject->FsContext2;
    v34 = FsContext2;
    v8 = FsContext[17];
    v41 = v8;
    if ( FsContext2 )
      v9 = FsContext2[80];
    else
      v9 = 5;
  }
  else
  {
    v33 = 0;
    v40 = 0;
    v8 = 0;
    v41 = 0;
    v9 = 1;
  }
  v31 = v9;
  if ( v9 == 1 )
  {
    RefsCompleteRequest(0, a2, 0);
    return 0;
  }
  KeEnterCriticalRegion();
  v38 = IoPropagateActivityIdToThread(a2, &v48, v43);
  if ( v34 )
  {
    v10 = *(_QWORD *)(v8 + 88);
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v10 + 8));
    *((_DWORD *)v34 + 1) |= 0x80000u;
    v11 = *((_DWORD *)v34 + 1);
    if ( (v11 & 0x10000000) != 0 )
    {
      *((_DWORD *)v34 + 1) = v11 | 0x4000;
      v12 = v37;
      v37->FileName.Buffer = 0;
      *(_DWORD *)&v12->FileName.Length = 0;
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v8 + 88) + 8LL));
    KeLeaveGuardedRegion();
  }
  v13 = RefsInitializeTopLevelIrp((struct _TOP_LEVEL_CONTEXT *)&v46, 0, 0);
  v43[1] = v13;
  v14 = v37;
  p_DeleteAccess = &v37->DeleteAccess;
  p_WriteAccess = &v37->WriteAccess;
  v32 = *(_WORD *)&v37->WriteAccess == 0;
  if ( v37->FileName.Buffer && !v37->FileName.Length )
    v37->FileName.Length = 1;
  if ( (v14->Flags & 0x4000) == 0 )
  {
    if ( ((v15 = *((_WORD *)v6 + 108), v15 == 128) || v15 == 176)
      && *(_WORD *)v6 == 2053
      && *(_QWORD **)(v6[18] + 72LL) != v6
      || v15 == 160
      && *((_WORD *)v6 + 112) == 8
      && *(_QWORD *)v6[29] == *(_QWORD *)RefsFileNameIndex.Buffer
      && (unsigned __int16)(*(_WORD *)v6 - 2051) <= 1u )
    {
      FsRtlCheckOplockEx((POPLOCK)v6 + 11, a2, 0, 0, 0, 0);
    }
  }
  if ( (int)RefsInitializeIrpContext(a2, 0, 0, &v35) >= 0 )
  {
    if ( *((_QWORD *)v13 + 2) )
    {
      v17 = v35;
    }
    else
    {
      *((_DWORD *)v13 + 1) = 1397140410;
      v17 = v35;
      *((_QWORD *)v13 + 2) = v35;
      *((_QWORD *)v17 + 1) |= 0x100000uLL;
      IoSetTopLevelIrp((PIRP)v13);
    }
    v18 = (struct _IRP_CONTEXT *)*((_QWORD *)v13 + 2);
    *((_QWORD *)v17 + 13) = v18;
    if ( v17 != v18 || !LOBYTE(IoGetTopLevelIrp()->Type) )
    {
      if ( !(unsigned __int8)ExIsFastResourceHeldExclusive(*(_QWORD *)(v6[17] + 88LL) + 64LL)
        || *(_DWORD *)(*((_QWORD *)v17 + 13) + 16LL) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_4391b888391630af3073df0a7ea07d8a_Traceguids, 259);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(259, 0, "Close.c", 0x16Eu);
        v16 = 259;
        goto LABEL_73;
      }
      goto LABEL_62;
    }
    if ( IoGetCurrentProcess() != (PEPROCESS)qword_140261128 )
    {
      *((_QWORD *)v17 + 1) |= 1uLL;
LABEL_62:
      v20 = v33;
      goto LABEL_63;
    }
    ++RefsAsyncPassCount;
    if ( KeQueryPriorityThread(KeGetCurrentThread()) < 16 )
    {
      if ( (RefsAsyncPassCount & 3) == 0 )
        goto LABEL_62;
      v20 = v33;
      if ( 4 * *(_DWORD *)(v33 + 216) >= *(_DWORD *)(v33 + 220)
        || (v19 = *(_DWORD *)(v33 + 220) - *(_DWORD *)(v33 + 216),
            v19 <= RefsMaxDelayedCloseCount + RefsAsyncPostThreshold) )
      {
LABEL_63:
        RefsPreRequestProcessingExtend(v17, v19);
        if ( (v6[19] & 0x200000) == 0 || *(_DWORD *)(v6[17] + 208LL) )
        {
          LOBYTE(PostIrpRoutine) = v31;
          v16 = RefsCommonClose(v17, v6, v8, v20, &v34, PostIrpRoutine, v32, 0);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_4391b888391630af3073df0a7ea07d8a_Traceguids, 259);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(259, 0, "Close.c", 0x189u);
          v16 = 259;
        }
        goto LABEL_73;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_4391b888391630af3073df0a7ea07d8a_Traceguids, 259);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(259, 0, "Close.c", 0x15Eu);
    v16 = 259;
    goto LABEL_73;
  }
  _InterlockedIncrement((volatile signed __int32 *)&RefsFailedCloseIrpContextAllocations);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_4391b888391630af3073df0a7ea07d8a_Traceguids, 259);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(259, 0, "Close.c", 0x12Eu);
  v16 = 259;
  v17 = v35;
LABEL_73:
  *p_FsContext = 0;
  v21 = v37;
  v37->FsContext2 = 0;
  v21->SectionObjectPointer = 0;
  if ( v16 == 259 )
  {
    if ( v17 && (*((_DWORD *)v17 + 2) & 0x100000) != 0 )
    {
      TopLevelIrp = IoGetTopLevelIrp();
      *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
      *(_QWORD *)&TopLevelIrp->Flags = 0;
      IoSetTopLevelIrp((PIRP)TopLevelIrp->MdlAddress);
      *((_QWORD *)v17 + 1) &= ~0x100000uLL;
    }
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v17, a2, 0);
    v16 = 0;
    v23 = 0;
    if ( (v6[19] & 0x200000) != 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)v6 + 38, 0xFFDFFFFF);
      if ( !*(_DWORD *)(v6[17] + 208LL)
        && (v6[19] & 0x100) == 0
        && (*((__int16 *)v6 + 128) >= 0 || (*((_BYTE *)v42 + 4) & 0x20) == 0) )
      {
        v23 = 1;
      }
    }
    if ( v34 )
    {
      v24 = p_DeleteAccess;
      if ( *p_WriteAccess | *p_DeleteAccess )
      {
        *p_WriteAccess = 0;
        *v24 = 0;
        v25 = v33;
        _InterlockedIncrement((volatile signed __int32 *)(v33 + 224));
      }
      else
      {
        v25 = v33;
      }
      v26 = (BOOLEAN *)(v25 + 3504);
      ExAcquirePushLockExclusiveEx(v26, 0);
      p_DeleteAccess = v26;
      v27 = v34;
      v34[96] = 0;
      v27[90] = v23;
      *((_QWORD *)v27 + 16) = v6;
      CLOSE_QUEUE::QueueInternal(&p_DeleteAccess, v6, v27 + 104, v23);
    }
    else
    {
      v26 = (BOOLEAN *)(v33 + 3504);
      ExAcquirePushLockExclusiveEx(v33 + 3504, 0);
      p_DeleteAccess = (BOOLEAN *)(v33 + 3504);
      if ( !(unsigned __int8)CLOSE_QUEUE::QueueScb(&p_DeleteAccess, v6, v23) )
      {
        LOBYTE(CompletionRoutine) = 0;
        LOBYTE(v28) = 1;
        RefsDecrementCloseCounts(0, v6, 0, v28, CompletionRoutine, 3);
      }
    }
    ExReleasePushLockExclusiveEx(v26, 0);
  }
  else
  {
    RefsCompleteRequest(0, a2, v16);
  }
  if ( v38 >= 0 )
    IoClearActivityIdThread(v43[0]);
  KeLeaveCriticalRegion();
  return v16;
}

```

## disassembly

```asm
0x1403391e0  mov     r11, rsp
0x1403391e3  mov     [r11+8], rbx
0x1403391e7  mov     [r11+18h], rsi
0x1403391eb  push    rdi
0x1403391ec  push    r12
0x1403391ee  push    r13
0x1403391f0  push    r14
0x1403391f2  push    r15
0x1403391f4  sub     rsp, 100h
0x1403391fb  mov     rax, cs:__security_cookie
0x140339202  xor     rax, rsp
0x140339205  mov     [rsp+128h+var_30], rax
0x14033920d  mov     r14, rdx
0x140339210  mov     [rsp+128h+var_B0], rdx
0x140339215  xorps   xmm0, xmm0
0x140339218  xor     eax, eax
0x14033921a  movups  xmmword ptr [r11-58h], xmm0
0x14033921f  mov     [r11-48h], rax
0x140339223  xor     r12d, r12d
0x140339226  mov     esi, r12d
0x140339229  mov     [rsp+128h+var_D0], r12
0x14033922e  mov     [rsp+128h+var_D8], r12
0x140339233  movups  xmmword ptr [r11-40h], xmm0
0x140339238  mov     [r11-90h], r12
0x14033923f  mov     eax, 150h
0x140339244  cmp     [rcx+2], ax
0x140339248  jnz     short loc_140339270
0x14033924a  mov     [rdx+30h], r12d
0x14033924e  mov     eax, 1
0x140339253  mov     [rdx+38h], rax
0x140339257  movzx   edx, al; PriorityBoost
0x14033925a  mov     rcx, r14; Irp
0x14033925d  call    cs:__imp_IofCompleteRequest
0x140339264  nop     dword ptr [rax+rax+00h]
0x140339269  xor     eax, eax
0x14033926b  jmp     loc_140339ABB
0x140339270  mov     rax, [rdx+0B8h]
0x140339277  mov     rax, [rax+30h]
0x14033927b  mov     [rsp+128h+var_C0], rax
0x140339280  mov     [rsp+128h+var_78], rax
0x140339288  lea     rcx, [rax+18h]
0x14033928c  mov     [rsp+128h+var_68], rcx
0x140339294  mov     rcx, [rcx]
0x140339297  mov     [rsp+128h+var_98], rcx
0x14033929f  mov     r15, rcx
0x1403392a2  mov     [rsp+128h+var_80], rcx
0x1403392aa  test    rcx, rcx
0x1403392ad  jz      short loc_1403392EA
0x1403392af  mov     rbx, [rcx+90h]
0x1403392b6  mov     [rsp+128h+var_E0], rbx
0x1403392bb  mov     [rsp+128h+var_A8], rbx
0x1403392c3  mov     rax, [rax+20h]
0x1403392c7  mov     [rsp+128h+var_D8], rax
0x1403392cc  mov     r13, [rcx+88h]
0x1403392d3  mov     [rsp+128h+var_A0], r13
0x1403392db  test    rax, rax
0x1403392de  jnz     short loc_1403392E4
0x1403392e0  mov     al, 5
0x1403392e2  jmp     short loc_140339307
0x1403392e4  movzx   eax, byte ptr [rax+50h]
0x1403392e8  jmp     short loc_140339307
0x1403392ea  mov     rbx, r12
0x1403392ed  mov     [rsp+128h+var_E0], rbx
0x1403392f2  mov     [rsp+128h+var_A8], rbx
0x1403392fa  mov     r13, r12
0x1403392fd  mov     [rsp+128h+var_A0], r12
0x140339305  mov     al, 1
0x140339307  mov     [rsp+128h+var_E8], al
0x14033930b  cmp     al, 1
0x14033930d  jnz     short loc_140339320
0x14033930f  xor     r8d, r8d; Status
0x140339312  xor     ecx, ecx; struct _IRP_CONTEXT *
0x140339314  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x140339319  xor     eax, eax
0x14033931b  jmp     loc_140339ABB
0x140339320  mov     [rsp+128h+var_E6], al
0x140339324  mov     edi, r12d
0x140339327  call    cs:__imp_KeEnterCriticalRegion
0x14033932e  nop     dword ptr [rax+rax+00h]
0x140339333  lea     r8, [rsp+128h+var_90]
0x14033933b  lea     rdx, [rsp+128h+var_40]
0x140339343  mov     rcx, r14
0x140339346  call    cs:__imp_IoPropagateActivityIdToThread
0x14033934d  nop     dword ptr [rax+rax+00h]
0x140339352  mov     [rsp+128h+var_B8], eax
0x140339356  cmp     [rsp+128h+var_D8], r12
0x14033935b  jz      short loc_1403393CB
0x14033935d  mov     rbx, [r13+58h]
0x140339361  call    cs:__imp_KeEnterGuardedRegion
0x140339368  nop     dword ptr [rax+rax+00h]
0x14033936d  lea     rcx, [rbx+8]; FastMutex
0x140339371  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140339378  nop     dword ptr [rax+rax+00h]
0x14033937d  mov     rax, [rsp+128h+var_D8]
0x140339382  or      dword ptr [rax+4], 80000h
0x140339389  mov     rcx, [rsp+128h+var_D8]
0x14033938e  mov     eax, [rcx+4]
0x140339391  bt      eax, 1Ch
0x140339395  jnb     short loc_1403393AB
0x140339397  bts     eax, 0Eh
0x14033939b  mov     [rcx+4], eax
0x14033939e  mov     rax, [rsp+128h+var_C0]
0x1403393a3  mov     [rax+60h], r12
0x1403393a7  mov     [rax+58h], r12d
0x1403393ab  mov     rcx, [r13+58h]
0x1403393af  add     rcx, 8; FastMutex
0x1403393b3  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1403393ba  nop     dword ptr [rax+rax+00h]
0x1403393bf  call    cs:__imp_KeLeaveGuardedRegion
0x1403393c6  nop     dword ptr [rax+rax+00h]
0x1403393cb  xor     r8d, r8d; unsigned __int8
0x1403393ce  xor     edx, edx; unsigned __int8
0x1403393d0  lea     rcx, [rsp+128h+var_58]; struct _TOP_LEVEL_CONTEXT *
0x1403393d8  call    ?RefsInitializeTopLevelIrp@@YAPEAU_TOP_LEVEL_CONTEXT@@PEAU1@EE@Z; RefsInitializeTopLevelIrp(_TOP_LEVEL_CONTEXT *,uchar,uchar)
0x1403393dd  mov     rbx, rax
0x1403393e0  mov     [rsp+128h+var_88], rax
0x1403393e8  mov     rdx, [rsp+128h+var_C0]
0x1403393ed  lea     rax, [rdx+4Ch]
0x1403393f1  mov     [rsp+128h+var_C8], rax
0x1403393f6  lea     rcx, [rdx+4Bh]
0x1403393fa  mov     [rsp+128h+var_60], rcx
0x140339402  movzx   eax, byte ptr [rax]
0x140339405  or      al, [rcx]
0x140339407  setz    [rsp+128h+var_E7]
0x14033940c  cmp     [rdx+60h], r12
0x140339410  jz      short loc_14033941F
0x140339412  cmp     [rdx+58h], r12w
0x140339417  jnz     short loc_14033941F
0x140339419  mov     word ptr [rdx+58h], 1
0x14033941f  mov     eax, [rdx+50h]
0x140339422  bt      eax, 0Eh
0x140339426  jb      loc_1403394C0
0x14033942c  movzx   ecx, word ptr [r15+0D8h]
0x140339434  mov     eax, 80h
0x140339439  cmp     cx, ax
0x14033943c  jz      short loc_140339448
0x14033943e  mov     eax, 0B0h
0x140339443  cmp     cx, ax
0x140339446  jnz     short loc_140339460
0x140339448  mov     eax, 805h
0x14033944d  cmp     [r15], ax
0x140339451  jnz     short loc_140339460
0x140339453  mov     rax, [r15+90h]
0x14033945a  cmp     [rax+48h], r15
0x14033945e  jnz     short loc_14033949D
0x140339460  mov     eax, 0A0h
0x140339465  cmp     cx, ax
0x140339468  jnz     short loc_1403394C0
0x14033946a  cmp     word ptr [r15+0E0h], 8
0x140339473  jnz     short loc_1403394C0
0x140339475  mov     rax, [r15+0E8h]
0x14033947c  mov     rcx, cs:?RefsFileNameIndex@@3U_UNICODE_STRING@@B.Buffer; _UNICODE_STRING const RefsFileNameIndex ...
0x140339483  mov     rax, [rax]
0x140339486  cmp     rax, [rcx]
0x140339489  jnz     short loc_1403394C0
0x14033948b  mov     ecx, 803h
0x140339490  movzx   eax, word ptr [r15]
0x140339494  sub     ax, cx
0x140339497  cmp     ax, 1
0x14033949b  ja      short loc_1403394C0
0x14033949d  lea     rcx, [r15+58h]; Oplock
0x1403394a1  mov     [rsp+128h+PostIrpRoutine], r12; PostIrpRoutine
0x1403394a6  mov     [rsp+128h+CompletionRoutine], r12; CompletionRoutine
0x1403394ab  xor     r9d, r9d; Context
0x1403394ae  xor     r8d, r8d; Flags
0x1403394b1  mov     rdx, r14; Irp
0x1403394b4  call    cs:__imp_FsRtlCheckOplockEx
0x1403394bb  nop     dword ptr [rax+rax+00h]
0x1403394c0  lea     r12, WPP_GLOBAL_Control
0x1403394c7  test    rsi, rsi
0x1403394ca  jnz     loc_140339741
0x1403394d0  lea     r9, [rsp+128h+var_D0]; struct _IRP_CONTEXT **
0x1403394d5  xor     r8d, r8d; unsigned __int8
0x1403394d8  xor     edx, edx; unsigned __int8
0x1403394da  mov     rcx, r14; Irp
0x1403394dd  call    ?RefsInitializeIrpContext@@YAJPEAU_IRP@@EEPEAPEAU_IRP_CONTEXT@@@Z; RefsInitializeIrpContext(_IRP *,uchar,uchar,_IRP_CONTEXT * *)
0x1403394e2  mov     [rsp+128h+var_E4], eax
0x1403394e6  test    eax, eax
0x1403394e8  jns     short loc_14033955E
0x1403394ea  lock inc cs:?RefsFailedCloseIrpContextAllocations@@3KA; ulong RefsFailedCloseIrpContextAllocations
0x1403394f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1403394f8  cmp     rcx, r12
0x1403394fb  jz      short loc_140339527
0x1403394fd  test    dword ptr [rcx+2Ch], 100h
0x140339504  jz      short loc_140339527
0x140339506  cmp     byte ptr [rcx+29h], 5
0x14033950a  jb      short loc_140339527
0x14033950c  mov     edx, 0Ah
0x140339511  mov     r9d, 103h
0x140339517  lea     r8, WPP_4391b888391630af3073df0a7ea07d8a_Traceguids
0x14033951e  mov     rcx, [rcx+18h]
0x140339522  call    WPP_SF_d
0x140339527  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14033952e  test    al, al
0x140339530  jz      short loc_14033954B
0x140339532  mov     r9d, 12Eh; unsigned int
0x140339538  lea     r8, aCloseC; "Close.c"
0x14033953f  xor     edx, edx; struct _IRP_CONTEXT *
0x140339541  mov     ecx, 103h; Status
0x140339546  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14033954b  mov     edi, 103h
0x140339550  mov     [rsp+128h+var_E4], edi
0x140339554  mov     rsi, [rsp+128h+var_D0]
0x140339559  jmp     loc_1403398AE
0x14033955e  cmp     qword ptr [rbx+10h], 0
0x140339563  jnz     short loc_14033958E
0x140339565  mov     dword ptr [rbx+4], 5346ABBAh
0x14033956c  mov     rsi, [rsp+128h+var_D0]
0x140339571  mov     [rbx+10h], rsi
0x140339575  or      qword ptr [rsi+8], 100000h
0x14033957d  mov     rcx, rbx; Irp
0x140339580  call    cs:__imp_IoSetTopLevelIrp
0x140339587  nop     dword ptr [rax+rax+00h]
0x14033958c  jmp     short loc_140339593
0x14033958e  mov     rsi, [rsp+128h+var_D0]
0x140339593  mov     rax, [rbx+10h]
0x140339597  mov     [rsi+68h], rax
0x14033959b  cmp     rsi, rax
0x14033959e  jnz     loc_1403396B0
0x1403395a4  call    cs:__imp_IoGetTopLevelIrp
0x1403395ab  nop     dword ptr [rax+rax+00h]
0x1403395b0  cmp     byte ptr [rax], 0
0x1403395b3  jz      loc_1403396B0
0x1403395b9  call    cs:__imp_IoGetCurrentProcess
0x1403395c0  nop     dword ptr [rax+rax+00h]
0x1403395c5  cmp     rax, cs:qword_140261128
0x1403395cc  jz      short loc_1403395D8
0x1403395ce  or      qword ptr [rsi+8], 1
0x1403395d3  jmp     loc_140339751
0x1403395d8  inc     cs:?RefsAsyncPassCount@@3KA; ulong RefsAsyncPassCount
0x1403395de  mov     rcx, gs:188h; Thread
0x1403395e7  call    cs:__imp_KeQueryPriorityThread
0x1403395ee  nop     dword ptr [rax+rax+00h]
0x1403395f3  cmp     eax, 10h
0x1403395f6  jge     short loc_140339648
0x1403395f8  mov     eax, cs:?RefsAsyncPassCount@@3KA; ulong RefsAsyncPassCount
0x1403395fe  test    al, 3
0x140339600  jz      loc_140339751
0x140339606  mov     rbx, [rsp+128h+var_E0]
0x14033960b  mov     eax, [rbx+0D8h]
0x140339611  mov     ecx, [rbx+0DCh]
0x140339617  lea     eax, ds:0[rax*4]
0x14033961e  cmp     eax, ecx
0x140339620  jge     loc_140339756
0x140339626  mov     edx, [rbx+0DCh]
0x14033962c  mov     eax, [rbx+0D8h]
0x140339632  sub     edx, eax
0x140339634  mov     ecx, cs:?RefsAsyncPostThreshold@@3KA; ulong RefsAsyncPostThreshold
0x14033963a  add     ecx, cs:?RefsMaxDelayedCloseCount@@3KA; ulong RefsMaxDelayedCloseCount
0x140339640  cmp     edx, ecx
0x140339642  jbe     loc_140339756
0x140339648  mov     rcx, cs:WPP_GLOBAL_Control
0x14033964f  cmp     rcx, r12
0x140339652  jz      short loc_14033967E
0x140339654  test    dword ptr [rcx+2Ch], 100h
0x14033965b  jz      short loc_14033967E
0x14033965d  cmp     byte ptr [rcx+29h], 5
0x140339661  jb      short loc_14033967E
0x140339663  mov     edx, 0Bh
0x140339668  mov     r9d, 103h
0x14033966e  lea     r8, WPP_4391b888391630af3073df0a7ea07d8a_Traceguids
0x140339675  mov     rcx, [rcx+18h]
0x140339679  call    WPP_SF_d
0x14033967e  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140339685  test    al, al
0x140339687  jz      short loc_1403396A2
0x140339689  mov     r9d, 15Eh; unsigned int
0x14033968f  lea     r8, aCloseC; "Close.c"
0x140339696  xor     edx, edx; struct _IRP_CONTEXT *
0x140339698  mov     ecx, 103h; Status
0x14033969d  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1403396a2  mov     edi, 103h
0x1403396a7  mov     [rsp+128h+var_E4], edi
0x1403396ab  jmp     loc_1403398D2
0x1403396b0  mov     rax, [r15+88h]
0x1403396b7  mov     rcx, [rax+58h]
0x1403396bb  add     rcx, 40h ; '@'
0x1403396bf  call    cs:__imp_ExIsFastResourceHeldExclusive
0x1403396c6  nop     dword ptr [rax+rax+00h]
0x1403396cb  test    al, al
0x1403396cd  jz      short loc_1403396D9
0x1403396cf  mov     rax, [rsi+68h]
0x1403396d3  cmp     dword ptr [rax+10h], 0
0x1403396d7  jz      short loc_140339751
0x1403396d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1403396e0  cmp     rcx, r12
0x1403396e3  jz      short loc_14033970F
0x1403396e5  test    dword ptr [rcx+2Ch], 100h
0x1403396ec  jz      short loc_14033970F
0x1403396ee  cmp     byte ptr [rcx+29h], 5
0x1403396f2  jb      short loc_14033970F
0x1403396f4  mov     edx, 0Ch
0x1403396f9  mov     r9d, 103h
0x1403396ff  lea     r8, WPP_4391b888391630af3073df0a7ea07d8a_Traceguids
0x140339706  mov     rcx, [rcx+18h]
0x14033970a  call    WPP_SF_d
0x14033970f  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140339716  test    al, al
0x140339718  jz      short loc_140339733
0x14033971a  mov     r9d, 16Eh; unsigned int
  ... truncated ...
```
