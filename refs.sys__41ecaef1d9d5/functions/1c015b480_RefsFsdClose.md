# RefsFsdClose

- ea: `0x1c015b480`
- end: `0x1c015be02`
- name: `RefsFsdClose`
- size: `2434`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1c0003788`
- `0x1c00046d4`
- `0x1c00049a0`
- `0x1c0005564`
- `0x1c0005650`
- `0x1c000f480`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c00588cc`
- `0x1c0062ce0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c00689d4`
- `0x1c015b480`
- `0x1c015de7c`
- `0x1c015e574`
- `0x1c01cd29c`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1c015ba69`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1c015ba69`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c015b5ef`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c015b832`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c015b5ef`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c015b832`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c015b62f`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c015b876`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c015b62f`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c015b876`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1c015b7d4`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1c015b7d4`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c015b94b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c015bc64`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c015b94b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c015bc64`
- `ntoskrnl!IofCompleteRequest` at `0x1c015b514`
- `ntoskrnl!IofCompleteRequest` at `0x1c015b514`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c015b921`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c015bc7b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c015b921`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c015bc7b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c015b5a4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c015b5a4`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c015b5c3`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c015b5c3`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c015bdb8`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c015bdb8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c015bdc4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c015bdc4`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c015b960`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c015b960`
- `ntoskrnl!KeQueryPriorityThread` at `0x1c015b99e`
- `ntoskrnl!KeQueryPriorityThread` at `0x1c015b99e`

## pseudocode

```c
__int64 __fastcall RefsFsdClose(__int64 a1, IRP *a2)
{
  IRP *v2; // rsi
  int v3; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  PFILE_OBJECT FileObject; // r14
  int v7; // r13d
  __int64 v8; // r15
  int v9; // eax
  bool v10; // zf
  int v11; // ecx
  int v12; // eax
  int v13; // r9d
  __int64 v14; // rsi
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  PIRP v19; // rcx
  struct _LIST_ENTRY *Flink; // rax
  __int64 v21; // rbx
  __int64 v22; // rbx
  unsigned int v23; // edx
  bool v24; // si
  __int64 v25; // r15
  PIRP TopLevelIrp; // rax
  __int64 v27; // rbx
  __int64 v28; // rdx
  bool v29; // [rsp+40h] [rbp-D8h]
  char v30; // [rsp+41h] [rbp-D7h]
  unsigned int Status; // [rsp+44h] [rbp-D4h]
  __int64 v32; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v33; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v34; // [rsp+58h] [rbp-C0h] BYREF
  IRP *v35; // [rsp+60h] [rbp-B8h]
  int v36; // [rsp+68h] [rbp-B0h]
  BOOL v37; // [rsp+6Ch] [rbp-ACh]
  __int64 v38; // [rsp+70h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+78h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+80h] [rbp-98h] BYREF
  PIRP Irp; // [rsp+88h] [rbp-90h]
  IRP *v42; // [rsp+90h] [rbp-88h]
  PFILE_OBJECT v43; // [rsp+98h] [rbp-80h]
  PKTHREAD CurrentThread; // [rsp+A0h] [rbp-78h]
  _BYTE v45[32]; // [rsp+B0h] [rbp-68h] BYREF
  __int64 v46; // [rsp+D0h] [rbp-48h]
  __int128 v47; // [rsp+D8h] [rbp-40h] BYREF

  v2 = a2;
  v35 = a2;
  memset(v45, 0, sizeof(v45));
  v46 = 0;
  v3 = 0;
  v33 = 0;
  v39 = 0;
  v38 = 0;
  v32 = 0;
  v34 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v47 = 0;
  v40 = 0;
  if ( *(_WORD *)(a1 + 2) == 336 )
  {
    a2->IoStatus.Status = 0;
    a2->IoStatus.Information = 1;
    IofCompleteRequest(a2, 1);
    return 0;
  }
  FileObject = CurrentStackLocation->FileObject;
  v43 = FileObject;
  v7 = RefsDecodeFileObject(
         0,
         (_DWORD)FileObject,
         (unsigned int)&v39,
         (unsigned int)&v38,
         (__int64)&v32,
         (__int64)&v34,
         0);
  v36 = v7;
  if ( v7 == 1 )
  {
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(0);
    RefsExtendedCompleteRequestInternal(0, v35, 0);
    return 0;
  }
  KeEnterCriticalRegion();
  v37 = (int)IoPropagateActivityIdToThread(v2, &v47, &v40) >= 0;
  if ( v34 )
  {
    v8 = v38;
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v38 + 96) + 8LL));
    *(_DWORD *)(v34 + 4) |= 0x80000u;
    v9 = *(_DWORD *)(v34 + 4);
    if ( (v9 & 0x10000000) != 0 )
    {
      *(_DWORD *)(v34 + 4) = v9 | 0x4000;
      FileObject->FileName.Buffer = 0;
      *(_DWORD *)&FileObject->FileName.Length = 0;
    }
    ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(v8 + 96) + 8LL));
  }
  v42 = (IRP *)RefsInitializeTopLevelIrp(v45, 0, 0);
  Irp = v42;
  v29 = (*(_DWORD *)(v38 + 4) & 4) != 0 || v7 == 5 || v34 && (*(_DWORD *)(v34 + 4) & 0x20000000) != 0;
  v30 = *(_WORD *)&FileObject->WriteAccess == 0;
  if ( FileObject->FileName.Buffer && !FileObject->FileName.Length )
    FileObject->FileName.Length = 1;
  if ( (FileObject->Flags & 0x4000) == 0 )
  {
    v10 = (unsigned int)Feature_Servicing_REFSDisallowDASDOplock__private_IsEnabledDeviceUsage() == 0;
    v11 = *(_DWORD *)(v32 + 200);
    if ( v10 )
    {
      if ( (v11 != 128 && v11 != 176 || *(_WORD *)v32 != 2053)
        && (v11 != 160
         || *(_WORD *)(v32 + 208) != 8
         || **(_QWORD **)(v32 + 216) != 0x30003300490024LL
         || (unsigned __int16)(*(_WORD *)v32 - 2051) > 1u) )
      {
        goto LABEL_42;
      }
    }
    else if ( (v11 != 128 && v11 != 176 || *(_WORD *)v32 != 2053 || *(_QWORD *)(*(_QWORD *)(v32 + 128) + 72LL) == v32)
           && (v11 != 160
            || *(_WORD *)(v32 + 208) != 8
            || **(_QWORD **)(v32 + 216) != 0x30003300490024LL
            || (unsigned __int16)(*(_WORD *)v32 - 2051) > 1u) )
    {
      v12 = 0;
      goto LABEL_40;
    }
    v12 = 1;
LABEL_40:
    if ( v12 )
      FsRtlCheckOplockEx((POPLOCK)(v32 + 88), v2, 0, 0, 0, 0);
    goto LABEL_42;
  }
  while ( 1 )
  {
LABEL_42:
    if ( v33 )
    {
      if ( v3 == -1073741432 )
        RefsCheckpointForLogFileFull(v33);
      goto LABEL_83;
    }
    Status = RefsInitializeIrpContext(v2, 0, 0, &v33);
    if ( (Status & 0x80000000) == 0 )
      break;
    _InterlockedAdd(&RefsFailedCloseIrpContextAllocations, 1u);
    if ( v34 )
    {
      v14 = *(_QWORD *)(v34 + 72);
      v15 = v38;
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v38 + 96) + 8LL));
      if ( *(_QWORD *)(v34 + 72) )
      {
        v16 = v34 + 56;
        v17 = *(_QWORD *)(v34 + 56);
        v18 = *(_QWORD **)(v34 + 64);
        if ( *(_QWORD *)(*(_QWORD *)v16 + 8LL) != v16 || *v18 != v16 )
          __fastfail(3u);
        *v18 = v17;
        *(_QWORD *)(v17 + 8) = v18;
        *(_QWORD *)(v34 + 72) = 0;
      }
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(v15 + 96) + 8LL));
      RefsDeleteCcb(v15, &v34);
    }
    else
    {
      LODWORD(v14) = 0;
    }
    LOBYTE(v13) = v29;
    RefsDecrementCloseCounts(0, v32, v14, v13, v30, 1, 0);
    v3 = Status;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    RefsExtendedCompleteRequestInternal(0, v35, Status);
    v2 = 0;
    v35 = 0;
    if ( Status != -1073741608 && Status != -1073741400 && Status != -1073741432 )
      goto LABEL_96;
  }
  v19 = Irp;
  Flink = Irp->ThreadListEntry.Flink;
  if ( !Flink )
  {
    *(_DWORD *)(&Irp->Size + 1) = 1397140410;
    v21 = v33;
    v19->ThreadListEntry.Flink = (struct _LIST_ENTRY *)v33;
    *(_DWORD *)(v21 + 8) |= 0x100000u;
    IoSetTopLevelIrp(v19);
    Flink = v42->ThreadListEntry.Flink;
  }
  v22 = v33;
  *(_QWORD *)(v33 + 104) = Flink;
  if ( (struct _LIST_ENTRY *)v22 != Flink || !LOBYTE(IoGetTopLevelIrp()->Type) )
  {
    if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v32 + 120) + 96LL) + 64LL))
      || *(_DWORD *)(*(_QWORD *)(v22 + 104) + 16LL) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_6104780b72913034addf9c8b337aee53_Traceguids, 259);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(259);
      v3 = 259;
      Status = 259;
      goto LABEL_96;
    }
LABEL_83:
    RefsPreRequestProcessingExtend(v33);
    if ( (*(_DWORD *)(v32 + 136) & 0x200000) == 0 || *(_DWORD *)(*(_QWORD *)(v32 + 120) + 192LL) )
    {
      v3 = RefsCommonClose(v33, v32, v38, v39, (__int64)&v34, v36, v30, 0);
      Status = v3;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_6104780b72913034addf9c8b337aee53_Traceguids, 259);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(259);
      v3 = 259;
      Status = 259;
    }
    goto LABEL_96;
  }
  if ( IoGetCurrentProcess() != (PEPROCESS)qword_1C012DEF0 )
  {
    *(_DWORD *)(v22 + 8) |= 1u;
    goto LABEL_83;
  }
  ++RefsAsyncPassCount;
  CurrentThread = KeGetCurrentThread();
  if ( KeQueryPriorityThread(CurrentThread) < 16 )
  {
    if ( (RefsAsyncPassCount & 3) == 0 )
      goto LABEL_83;
    v23 = *(_DWORD *)(v39 + 220);
    if ( 4 * *(_DWORD *)(v39 + 216) >= v23
      || v23 - *(_DWORD *)(v39 + 216) <= RefsAsyncPostThreshold + RefsMaxDelayedCloseCount )
    {
      goto LABEL_83;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_6104780b72913034addf9c8b337aee53_Traceguids, 259);
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(259);
  v3 = 259;
  Status = 259;
LABEL_96:
  if ( v3 == 259 )
  {
    v24 = 0;
    v25 = v33;
    if ( (*(_DWORD *)(v33 + 8) & 0x100000) != 0 )
    {
      TopLevelIrp = IoGetTopLevelIrp();
      *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
      TopLevelIrp->ThreadListEntry.Flink = 0;
      IoSetTopLevelIrp(TopLevelIrp->AssociatedIrp.MasterIrp);
      *(_DWORD *)(v25 + 8) &= ~0x100000u;
    }
    FileObject->FsContext = 0;
    FileObject->FsContext2 = 0;
    FileObject->SectionObjectPointer = 0;
    *(_DWORD *)(v33 + 4) |= 0x400u;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(0);
    v27 = v33;
    RefsExtendedCompleteRequestInternal(v33, v35, 0);
    Status = 0;
    v28 = v32;
    *(_QWORD *)(v27 + 72) = v32;
    *(_QWORD *)(v27 + 144) = v34;
    *(_DWORD *)(v27 + 24) = v36;
    if ( v34 )
    {
      if ( *(_WORD *)&FileObject->WriteAccess )
      {
        *(_WORD *)&FileObject->WriteAccess = 0;
        _InterlockedAdd((volatile signed __int32 *)(v39 + 224), 1u);
        v28 = v32;
      }
      *(_DWORD *)(v25 + 8) |= 0x4000u;
    }
    if ( (*(_DWORD *)(v28 + 136) & 0x200000) != 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)(v28 + 136), 0xFFDFFFFF);
      if ( !*(_DWORD *)(*(_QWORD *)(v32 + 120) + 192LL) )
      {
        v24 = 1;
        v28 = 33023;
        if ( (*(_WORD *)(v32 + 252) & 0x80FF) != 0 )
          v24 = (*(_BYTE *)(v32 + 4) & 0x20) == 0;
      }
    }
    LOBYTE(v28) = v24;
    RefsQueueClose(v33, v28);
  }
  else
  {
    FileObject->FsContext = 0;
    FileObject->FsContext2 = 0;
    FileObject->SectionObjectPointer = 0;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    RefsExtendedCompleteRequestInternal(0, v35, Status);
  }
  if ( v37 )
    IoClearActivityIdThread(v40);
  KeLeaveCriticalRegion();
  return Status;
}

```

## disassembly

```asm
0x1c015b480  mov     r11, rsp
0x1c015b483  mov     [r11+8], rbx
0x1c015b487  mov     [r11+18h], rsi
0x1c015b48b  push    rdi
0x1c015b48c  push    r12
0x1c015b48e  push    r13
0x1c015b490  push    r14
0x1c015b492  push    r15
0x1c015b494  sub     rsp, 0F0h
0x1c015b49b  mov     rax, cs:__security_cookie
0x1c015b4a2  xor     rax, rsp
0x1c015b4a5  mov     [rsp+118h+var_30], rax
0x1c015b4ad  mov     rsi, rdx
0x1c015b4b0  mov     [rsp+118h+var_B8], rdx
0x1c015b4b5  xorps   xmm0, xmm0
0x1c015b4b8  xor     eax, eax
0x1c015b4ba  movups  xmmword ptr [r11-68h], xmm0
0x1c015b4bf  movups  xmmword ptr [r11-58h], xmm0
0x1c015b4c4  mov     [r11-48h], rax
0x1c015b4c8  xor     edi, edi
0x1c015b4ca  mov     ebx, edi
0x1c015b4cc  mov     [rsp+118h+var_C8], rdi
0x1c015b4d1  mov     [rsp+118h+var_A0], rdi
0x1c015b4d6  mov     [rsp+118h+var_A8], rdi
0x1c015b4db  mov     [rsp+118h+var_D0], rdi
0x1c015b4e0  mov     [rsp+118h+var_C0], rdi
0x1c015b4e5  mov     r14, [rdx+0B8h]
0x1c015b4ec  movups  xmmword ptr [r11-40h], xmm0
0x1c015b4f1  mov     [r11-98h], rdi
0x1c015b4f8  mov     eax, 150h
0x1c015b4fd  cmp     [rcx+2], ax
0x1c015b501  jnz     short loc_1C015B527
0x1c015b503  mov     [rdx+30h], edi
0x1c015b506  lea     r12d, [rdi+1]
0x1c015b50a  mov     [rdx+38h], r12
0x1c015b50e  mov     dl, r12b; PriorityBoost
0x1c015b511  mov     rcx, rsi; Irp
0x1c015b514  call    cs:__imp_IofCompleteRequest
0x1c015b51b  nop     dword ptr [rax+rax+00h]
0x1c015b520  xor     eax, eax
0x1c015b522  jmp     loc_1C015BDD4
0x1c015b527  mov     r14, [r14+30h]
0x1c015b52b  mov     [rsp+118h+var_80], r14
0x1c015b533  mov     byte ptr [rsp+118h+var_E8], dil
0x1c015b538  lea     rax, [rsp+118h+var_C0]
0x1c015b53d  mov     [rsp+118h+PostIrpRoutine], rax
0x1c015b542  lea     rax, [rsp+118h+var_D0]
0x1c015b547  mov     [rsp+118h+CompletionRoutine], rax
0x1c015b54c  lea     r9, [rsp+118h+var_A8]
0x1c015b551  lea     r8, [rsp+118h+var_A0]
0x1c015b556  mov     rdx, r14
0x1c015b559  xor     ecx, ecx
0x1c015b55b  call    RefsDecodeFileObject
0x1c015b560  mov     r13d, eax
0x1c015b563  mov     [rsp+118h+var_B0], eax
0x1c015b567  mov     r12d, 1
0x1c015b56d  cmp     eax, r12d
0x1c015b570  jnz     short loc_1C015B5A4
0x1c015b572  mov     al, cs:RefsStatusDebugEnabled
0x1c015b578  test    al, al
0x1c015b57a  jz      short loc_1C015B590
0x1c015b57c  mov     r8d, 0A9h
0x1c015b582  lea     rdx, aCloseC; "Close.c"
0x1c015b589  xor     ecx, ecx; Status
0x1c015b58b  call    RefsStatusDebug
0x1c015b590  xor     r8d, r8d
0x1c015b593  mov     rdx, [rsp+118h+var_B8]
0x1c015b598  xor     ecx, ecx
0x1c015b59a  call    RefsExtendedCompleteRequestInternal
0x1c015b59f  jmp     loc_1C015B520
0x1c015b5a4  call    cs:__imp_KeEnterCriticalRegion
0x1c015b5ab  nop     dword ptr [rax+rax+00h]
0x1c015b5b0  lea     r8, [rsp+118h+var_98]
0x1c015b5b8  lea     rdx, [rsp+118h+var_40]
0x1c015b5c0  mov     rcx, rsi
0x1c015b5c3  call    cs:__imp_IoPropagateActivityIdToThread
0x1c015b5ca  nop     dword ptr [rax+rax+00h]
0x1c015b5cf  mov     ecx, edi
0x1c015b5d1  test    eax, eax
0x1c015b5d3  cmovns  ecx, r12d
0x1c015b5d7  mov     [rsp+118h+var_AC], ecx
0x1c015b5db  cmp     [rsp+118h+var_C0], rdi
0x1c015b5e0  jz      short loc_1C015B63D
0x1c015b5e2  mov     r15, [rsp+118h+var_A8]
0x1c015b5e7  mov     rcx, [r15+60h]
0x1c015b5eb  add     rcx, 8; FastMutex
0x1c015b5ef  call    cs:__imp_ExAcquireFastMutex
0x1c015b5f6  nop     dword ptr [rax+rax+00h]
0x1c015b5fb  mov     rax, [rsp+118h+var_C0]
0x1c015b600  bts     dword ptr [rax+4], 13h
0x1c015b605  mov     rcx, [rsp+118h+var_C0]
0x1c015b60a  mov     eax, [rcx+4]
0x1c015b60d  bt      eax, 1Ch
0x1c015b611  jnb     short loc_1C015B622
0x1c015b613  bts     eax, 0Eh
0x1c015b617  mov     [rcx+4], eax
0x1c015b61a  mov     [r14+60h], rdi
0x1c015b61e  mov     [r14+58h], edi
0x1c015b622  mov     rcx, [r15+60h]
0x1c015b626  mov     r15d, 8
0x1c015b62c  add     rcx, r15; FastMutex
0x1c015b62f  call    cs:__imp_ExReleaseFastMutex
0x1c015b636  nop     dword ptr [rax+rax+00h]
0x1c015b63b  jmp     short loc_1C015B643
0x1c015b63d  mov     r15d, 8
0x1c015b643  xor     r8d, r8d
0x1c015b646  xor     edx, edx
0x1c015b648  lea     rcx, [rsp+118h+var_68]
0x1c015b650  call    RefsInitializeTopLevelIrp
0x1c015b655  mov     [rsp+118h+var_88], rax
0x1c015b65d  mov     [rsp+118h+Irp], rax
0x1c015b665  mov     rax, [rsp+118h+var_A8]
0x1c015b66a  mov     ecx, [rax+4]
0x1c015b66d  test    cl, 4
0x1c015b670  jnz     short loc_1C015B692
0x1c015b672  cmp     r13d, 5
0x1c015b676  jz      short loc_1C015B692
0x1c015b678  mov     rax, [rsp+118h+var_C0]
0x1c015b67d  test    rax, rax
0x1c015b680  jz      short loc_1C015B68B
0x1c015b682  mov     eax, [rax+4]
0x1c015b685  bt      eax, 1Dh
0x1c015b689  jb      short loc_1C015B692
0x1c015b68b  mov     [rsp+118h+var_D8], dil
0x1c015b690  jmp     short loc_1C015B697
0x1c015b692  mov     [rsp+118h+var_D8], r12b
0x1c015b697  mov     al, [r14+4Ch]
0x1c015b69b  or      al, [r14+4Bh]
0x1c015b69f  setz    [rsp+118h+var_D7]
0x1c015b6a4  cmp     [r14+60h], rdi
0x1c015b6a8  jz      short loc_1C015B6B6
0x1c015b6aa  cmp     [r14+58h], di
0x1c015b6af  jnz     short loc_1C015B6B6
0x1c015b6b1  mov     [r14+58h], r12w
0x1c015b6b6  test    dword ptr [r14+50h], 4000h
0x1c015b6be  jnz     loc_1C015B7E0
0x1c015b6c4  call    Feature_Servicing_REFSDisallowDASDOplock__private_IsEnabledDeviceUsage
0x1c015b6c9  test    eax, eax
0x1c015b6cb  mov     rax, [rsp+118h+var_D0]
0x1c015b6d0  mov     ecx, [rax+0C8h]
0x1c015b6d6  jz      short loc_1C015B74F
0x1c015b6d8  cmp     ecx, 80h
0x1c015b6de  jz      short loc_1C015B6E8
0x1c015b6e0  cmp     ecx, 0B0h
0x1c015b6e6  jnz     short loc_1C015B70A
0x1c015b6e8  mov     r8d, 805h
0x1c015b6ee  mov     rdx, [rsp+118h+var_D0]
0x1c015b6f3  cmp     [rdx], r8w
0x1c015b6f7  jnz     short loc_1C015B70A
0x1c015b6f9  mov     rax, [rdx+80h]
0x1c015b700  cmp     [rax+48h], rdx
0x1c015b704  jnz     loc_1C015B7B1
0x1c015b70a  cmp     ecx, 0A0h
0x1c015b710  jnz     short loc_1C015B74B
0x1c015b712  mov     rdx, [rsp+118h+var_D0]
0x1c015b717  cmp     [rdx+0D0h], r15w
0x1c015b71f  jnz     short loc_1C015B74B
0x1c015b721  mov     rax, [rdx+0D8h]
0x1c015b728  mov     rcx, [rax]
0x1c015b72b  mov     rax, 30003300490024h
0x1c015b735  cmp     rcx, rax
0x1c015b738  jnz     short loc_1C015B74B
0x1c015b73a  mov     ecx, 803h
0x1c015b73f  movzx   eax, word ptr [rdx]
0x1c015b742  sub     ax, cx
0x1c015b745  cmp     ax, r12w
0x1c015b749  jbe     short loc_1C015B7B1
0x1c015b74b  mov     eax, edi
0x1c015b74d  jmp     short loc_1C015B7B4
0x1c015b74f  cmp     ecx, 80h
0x1c015b755  jz      short loc_1C015B75F
0x1c015b757  cmp     ecx, 0B0h
0x1c015b75d  jnz     short loc_1C015B770
0x1c015b75f  mov     r8d, 805h
0x1c015b765  mov     rax, [rsp+118h+var_D0]
0x1c015b76a  cmp     [rax], r8w
0x1c015b76e  jz      short loc_1C015B7B1
0x1c015b770  cmp     ecx, 0A0h
0x1c015b776  jnz     short loc_1C015B7E0
0x1c015b778  mov     rdx, [rsp+118h+var_D0]
0x1c015b77d  cmp     [rdx+0D0h], r15w
0x1c015b785  jnz     short loc_1C015B7E0
0x1c015b787  mov     rax, [rdx+0D8h]
0x1c015b78e  mov     rcx, [rax]
0x1c015b791  mov     rax, 30003300490024h
0x1c015b79b  cmp     rcx, rax
0x1c015b79e  jnz     short loc_1C015B7E0
0x1c015b7a0  mov     ecx, 803h
0x1c015b7a5  movzx   eax, word ptr [rdx]
0x1c015b7a8  sub     ax, cx
0x1c015b7ab  cmp     ax, r12w
0x1c015b7af  ja      short loc_1C015B7E0
0x1c015b7b1  mov     eax, r12d
0x1c015b7b4  test    eax, eax
0x1c015b7b6  jz      short loc_1C015B7E0
0x1c015b7b8  mov     rcx, [rsp+118h+var_D0]
0x1c015b7bd  add     rcx, 58h ; 'X'; Oplock
0x1c015b7c1  mov     [rsp+118h+PostIrpRoutine], rdi; PostIrpRoutine
0x1c015b7c6  mov     [rsp+118h+CompletionRoutine], rdi; CompletionRoutine
0x1c015b7cb  xor     r9d, r9d; Context
0x1c015b7ce  xor     r8d, r8d; Flags
0x1c015b7d1  mov     rdx, rsi; Irp
0x1c015b7d4  call    cs:__imp_FsRtlCheckOplockEx
0x1c015b7db  nop     dword ptr [rax+rax+00h]
0x1c015b7e0  lea     r13, aCloseC; "Close.c"
0x1c015b7e7  cmp     [rsp+118h+var_C8], rdi
0x1c015b7ec  jnz     loc_1C015BAEA
0x1c015b7f2  lea     r9, [rsp+118h+var_C8]
0x1c015b7f7  xor     r8d, r8d
0x1c015b7fa  xor     edx, edx
0x1c015b7fc  mov     rcx, rsi
0x1c015b7ff  call    RefsInitializeIrpContext
0x1c015b804  mov     [rsp+118h+Status], eax
0x1c015b808  test    eax, eax
0x1c015b80a  jns     loc_1C015B8FB
0x1c015b810  lock add cs:RefsFailedCloseIrpContextAllocations, r12d
0x1c015b818  mov     rax, [rsp+118h+var_C0]
0x1c015b81d  test    rax, rax
0x1c015b820  jz      short loc_1C015B898
0x1c015b822  mov     rsi, [rax+48h]
0x1c015b826  mov     rbx, [rsp+118h+var_A8]
0x1c015b82b  mov     rcx, [rbx+60h]
0x1c015b82f  add     rcx, r15; FastMutex
0x1c015b832  call    cs:__imp_ExAcquireFastMutex
0x1c015b839  nop     dword ptr [rax+rax+00h]
0x1c015b83e  mov     rax, [rsp+118h+var_C0]
0x1c015b843  cmp     [rax+48h], rdi
0x1c015b847  jz      short loc_1C015B86F
0x1c015b849  add     rax, 38h ; '8'
0x1c015b84d  mov     rdx, [rax]
0x1c015b850  mov     rcx, [rax+8]
0x1c015b854  cmp     [rdx+8], rax
0x1c015b858  jnz     short loc_1C015B891
0x1c015b85a  cmp     [rcx], rax
0x1c015b85d  jnz     short loc_1C015B891
0x1c015b85f  mov     [rcx], rdx
0x1c015b862  mov     [rdx+8], rcx
0x1c015b866  mov     rax, [rsp+118h+var_C0]
0x1c015b86b  mov     [rax+48h], rdi
0x1c015b86f  mov     rcx, [rbx+60h]
0x1c015b873  add     rcx, r15; FastMutex
0x1c015b876  call    cs:__imp_ExReleaseFastMutex
0x1c015b87d  nop     dword ptr [rax+rax+00h]
0x1c015b882  lea     rdx, [rsp+118h+var_C0]
0x1c015b887  mov     rcx, rbx
0x1c015b88a  call    RefsDeleteCcb
0x1c015b88f  jmp     short loc_1C015B89B
0x1c015b891  mov     ecx, 3
0x1c015b896  int     29h; Win8: RtlFailFast(ecx)
0x1c015b898  mov     rsi, rdi
0x1c015b89b  mov     [rsp+118h+var_E8], rdi
0x1c015b8a0  mov     byte ptr [rsp+118h+PostIrpRoutine], r12b
0x1c015b8a5  mov     al, [rsp+118h+var_D7]
0x1c015b8a9  mov     byte ptr [rsp+118h+CompletionRoutine], al
0x1c015b8ad  mov     r9b, [rsp+118h+var_D8]
0x1c015b8b2  mov     r8, rsi
0x1c015b8b5  mov     rdx, [rsp+118h+var_D0]
0x1c015b8ba  xor     ecx, ecx
0x1c015b8bc  call    RefsDecrementCloseCounts
0x1c015b8c1  mov     al, cs:RefsStatusDebugEnabled
0x1c015b8c7  mov     ebx, [rsp+118h+Status]
0x1c015b8cb  test    al, al
0x1c015b8cd  jz      short loc_1C015B8DF
0x1c015b8cf  mov     r8d, 14Fh
0x1c015b8d5  mov     rdx, r13
0x1c015b8d8  mov     ecx, ebx; Status
0x1c015b8da  call    RefsStatusDebug
0x1c015b8df  mov     r8d, ebx
0x1c015b8e2  mov     rdx, [rsp+118h+var_B8]
0x1c015b8e7  xor     ecx, ecx
0x1c015b8e9  call    RefsExtendedCompleteRequestInternal
0x1c015b8ee  mov     rsi, rdi
0x1c015b8f1  mov     [rsp+118h+var_B8], rdi
0x1c015b8f6  jmp     loc_1C015BC22
0x1c015b8fb  mov     rcx, [rsp+118h+Irp]; Irp
0x1c015b903  mov     rax, [rcx+20h]
0x1c015b907  test    rax, rax
0x1c015b90a  jnz     short loc_1C015B939
0x1c015b90c  mov     dword ptr [rcx+4], 5346ABBAh
0x1c015b913  mov     rbx, [rsp+118h+var_C8]
0x1c015b918  mov     [rcx+20h], rbx
0x1c015b91c  bts     dword ptr [rbx+8], 14h
0x1c015b921  call    cs:__imp_IoSetTopLevelIrp
0x1c015b928  nop     dword ptr [rax+rax+00h]
0x1c015b92d  mov     rcx, [rsp+118h+var_88]
0x1c015b935  mov     rax, [rcx+20h]
0x1c015b939  mov     rbx, [rsp+118h+var_C8]
0x1c015b93e  mov     [rbx+68h], rax
0x1c015b942  cmp     rbx, rax
0x1c015b945  jnz     loc_1C015BA58
0x1c015b94b  call    cs:__imp_IoGetTopLevelIrp
0x1c015b952  nop     dword ptr [rax+rax+00h]
0x1c015b957  cmp     [rax], dil
0x1c015b95a  jz      loc_1C015BA58
0x1c015b960  call    cs:__imp_IoGetCurrentProcess
0x1c015b967  nop     dword ptr [rax+rax+00h]
0x1c015b96c  cmp     rax, cs:qword_1C012DEF0
0x1c015b973  jz      short loc_1C015B97E
0x1c015b975  or      [rbx+8], r12d
0x1c015b979  jmp     loc_1C015BAFC
  ... truncated ...
```
