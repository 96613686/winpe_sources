# NtfsFsdClose

- ea: `0x14013a250`
- end: `0x14013adc9`
- name: `NtfsFsdClose`
- size: `2937`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000ea70`
- `0x140011fb0`
- `0x140012ab0`
- `0x140016ea0`
- `0x140017030`
- `0x140017480`
- `0x14001c9c0`
- `0x14001e810`
- `0x14001ebf0`
- `0x1400291f0`
- `0x140029d80`
- `0x140059740`
- `0x140139f20`
- `0x14013a250`
- `0x14013add0`
- `0x14013b8c0`
- `0x140187a00`
- `0x1401e7cc0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14013a34a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14013a34a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14013a80a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14013a80a`
- `ntoskrnl!IofCompleteRequest` at `0x14013acfd`
- `ntoskrnl!IofCompleteRequest` at `0x14013acfd`
- `ntoskrnl!KeQueryPriorityThread` at `0x14013a49b`
- `ntoskrnl!KeQueryPriorityThread` at `0x14013a49b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14013ac02`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14013ac02`
- `ntoskrnl!IoGetCurrentProcess` at `0x14013a47d`
- `ntoskrnl!IoGetCurrentProcess` at `0x14013a47d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14013aa5b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14013aa5b`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14013ac7f`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14013ac7f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013a6d9`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013a965`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013a6d9`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013a965`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013a5d4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013a9c6`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013a5d4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013a9c6`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14013a468`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14013abe5`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14013a468`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14013abe5`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14013a540`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14013a540`
- `HAL!KeQueryPerformanceCounter` at `0x14013a366`
- `HAL!KeQueryPerformanceCounter` at `0x14013a366`

## pseudocode

```c
__int64 __fastcall NtfsFsdClose(__int64 a1, IRP *a2, __int64 a3, __int64 a4)
{
  IRP *v4; // r14
  __int64 v5; // r13
  PFILE_OBJECT FileObject; // rdx
  _WORD *FsContext; // r12
  __int16 *FsContext2; // rax
  __int64 v9; // rbx
  int v10; // eax
  struct _FILE_OBJECT *v11; // rcx
  unsigned int v12; // esi
  __int64 v13; // rdx
  LARGE_INTEGER v14; // rbx
  int v15; // eax
  PFILE_OBJECT v16; // rcx
  __int64 v17; // r9
  __int16 *v18; // rax
  __int64 v19; // rdx
  __int16 **v20; // rcx
  __int64 v21; // r9
  __int64 v22; // r13
  PFILE_OBJECT v24; // rax
  __int64 v25; // r13
  LARGE_INTEGER v26; // r12
  __int64 OriginatingProcessId; // rax
  __int64 v28; // r10
  int v29; // eax
  int v30; // eax
  bool v31; // r12
  PFILE_OBJECT v32; // rsi
  __int64 v33; // r8
  _DWORD *v34; // r9
  __int64 v35; // r9
  PIRP TopLevelIrp; // rax
  __int64 v37; // r9
  _DWORD *v38; // rax
  PFILE_OBJECT v39; // rax
  __int16 *v40; // [rsp+50h] [rbp-F8h] BYREF
  int v41; // [rsp+58h] [rbp-F0h]
  int v42; // [rsp+5Ch] [rbp-ECh]
  __int64 v43; // [rsp+60h] [rbp-E8h]
  PFILE_OBJECT v44; // [rsp+68h] [rbp-E0h]
  __int64 v45; // [rsp+70h] [rbp-D8h]
  __int64 v46; // [rsp+78h] [rbp-D0h] BYREF
  int v47; // [rsp+80h] [rbp-C8h]
  LARGE_INTEGER PerformanceCounter; // [rsp+88h] [rbp-C0h]
  LARGE_INTEGER v49; // [rsp+90h] [rbp-B8h]
  __int64 v50; // [rsp+98h] [rbp-B0h]
  __int64 v51; // [rsp+A0h] [rbp-A8h]
  _DWORD *v52; // [rsp+A8h] [rbp-A0h]
  PVOID *p_FsContext; // [rsp+B0h] [rbp-98h]
  __int64 v54; // [rsp+B8h] [rbp-90h]
  __int64 v55; // [rsp+C0h] [rbp-88h]
  PFILE_OBJECT v56; // [rsp+C8h] [rbp-80h]
  PVOID v57; // [rsp+D0h] [rbp-78h]
  BOOLEAN *p_WriteAccess; // [rsp+D8h] [rbp-70h]
  BOOLEAN *p_DeleteAccess; // [rsp+E0h] [rbp-68h]
  _BYTE v60[32]; // [rsp+E8h] [rbp-60h] BYREF
  __int64 v61; // [rsp+108h] [rbp-40h]
  unsigned __int8 v62; // [rsp+150h] [rbp+8h]
  _QWORD *v63; // [rsp+150h] [rbp+8h]
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // [rsp+160h] [rbp+18h]
  int v65; // [rsp+168h] [rbp+20h]

  v4 = a2;
  memset(v60, 0, sizeof(v60));
  v61 = 0;
  v5 = 0;
  v46 = 0;
  v40 = 0;
  if ( *(_WORD *)(a1 + 2) == 336 )
  {
    a2->IoStatus.Status = 0;
    a2->IoStatus.Information = 1;
    IofCompleteRequest(a2, 1);
    return 0;
  }
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  v44 = FileObject;
  v56 = FileObject;
  p_FsContext = &FileObject->FsContext;
  FsContext = FileObject->FsContext;
  v52 = FsContext;
  if ( FsContext )
  {
    FsContext2 = (__int16 *)FileObject->FsContext2;
    v9 = *((_QWORD *)FsContext + 24);
    v45 = v9;
    v40 = FsContext2;
    v50 = v9;
    v43 = *((_QWORD *)FsContext + 23);
    v51 = v43;
    if ( !FsContext2 )
    {
      v10 = 5;
      v65 = 5;
      goto LABEL_6;
    }
    v10 = *((unsigned __int8 *)FsContext2 + 88);
  }
  else
  {
    v9 = 0;
    v45 = 0;
    v50 = 0;
    v43 = 0;
    v51 = 0;
    v10 = 1;
  }
  v65 = v10;
  if ( v10 == 1 )
  {
LABEL_110:
    LOBYTE(a4) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(0, v4, 0, a4, 1);
    return 0;
  }
LABEL_6:
  v11 = *(struct _FILE_OBJECT **)(v9 + 216);
  if ( FileObject == v11 )
  {
    v38 = v11->FsContext;
    if ( v38 && (v38[50] & 0x4000) == 0 )
    {
      v11->FileName.MaximumLength = 0;
      *(_WORD *)(*(_QWORD *)(v9 + 216) + 88LL) = 0;
      *(_QWORD *)(*(_QWORD *)(v9 + 216) + 96LL) = 0;
    }
    *(_QWORD *)(v9 + 216) = 0;
    goto LABEL_110;
  }
  v12 = 0;
  v57 = FsContext;
  v47 = v10;
  KeEnterCriticalRegion();
  if ( *(_BYTE *)(v9 + 10496) )
  {
    PerformanceCounter = KeQueryPerformanceCounter(0);
    v13 = v43;
    v14 = *(LARGE_INTEGER *)(v43 + 8);
  }
  else
  {
    PerformanceCounter.QuadPart = 0;
    v14.QuadPart = 0;
    v13 = v43;
  }
  v49 = v14;
  p_DeleteAccess = &v44->DeleteAccess;
  v15 = (_DWORD)v44 + 75;
  p_WriteAccess = &v44->WriteAccess;
  LOBYTE(v15) = *(_WORD *)&v44->WriteAccess == 0;
  v62 = v15;
  if ( v40 )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v13 + 104) + 8LL));
    if ( (*((_DWORD *)v40 + 1) & 0x80000) == 0 )
      _InterlockedOr((volatile signed __int32 *)v40 + 1, 0x80000u);
    v28 = v43;
    v29 = v62;
    if ( (*(_DWORD *)(v43 + 4) & 0x40000000) != 0 )
      v29 = 0;
    v42 = v29;
    if ( (*((_DWORD *)v40 + 1) & 0x10000000) != 0 )
    {
      SetFlagInterlocked(v40 + 2, 0x4000);
      v39 = v44;
      v44->FileName.Buffer = 0;
      *(_DWORD *)&v39->FileName.Length = 0;
    }
    ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(v28 + 104) + 8LL));
  }
  else
  {
    v42 = v15;
  }
  v55 = NtfsInitializeTopLevelIrp(v60, 0, v45);
  v16 = v44;
  if ( v44->FileName.Buffer && !v44->FileName.Length )
    v44->FileName.Length = 1;
  if ( (v16->Flags & 0x4000) == 0 )
  {
    if ( (v30 = *((_DWORD *)FsContext + 64), v30 == 128) && *FsContext == 1797
      || v30 == 160
      && FsContext[132] == 8
      && **((_QWORD **)FsContext + 34) == 0x30003300490024LL
      && (unsigned __int16)(*FsContext - 1795) <= 1u )
    {
      FsRtlCheckOplockEx((POPLOCK)FsContext + 11, v4, 0, 0, 0, 0);
    }
  }
  while ( 1 )
  {
    if ( v5 )
    {
      if ( v12 == -1073741432 )
        NtfsCheckpointForLogFileFull(v5);
      goto LABEL_21;
    }
    v12 = NtfsInitializeIrpContextInternal(v4, 0, 0, &v46);
    v41 = v12;
    if ( (v12 & 0x80000000) == 0 )
      break;
    _InterlockedAdd(&NtfsFailedCloseIrpContextAllocations, 1u);
    TxfCheckForFloaterDelete(v44->SectionObjectPointer, FsContext, v40);
    if ( v40 )
    {
      v54 = *((_QWORD *)v40 + 9);
      v22 = v43;
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v43 + 104) + 8LL));
      if ( *((_QWORD *)v40 + 9) )
      {
        v18 = v40 + 28;
        v19 = *((_QWORD *)v40 + 7);
        if ( *(__int16 **)(*(_QWORD *)v18 + 8LL) != v18 || (v20 = (__int16 **)*((_QWORD *)v40 + 8), *v20 != v18) )
          __fastfail(3u);
        *v20 = (__int16 *)v19;
        *(_QWORD *)(v19 + 8) = v20;
        *((_QWORD *)v40 + 9) = 0;
      }
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(v22 + 104) + 8LL));
      NtfsDeleteCcb(v22, &v40);
    }
    NtfsDecrementCloseCounts(0, (_DWORD)FsContext, v42, 1, 0);
    if ( NtfsStatusDebugFlags
      && v12 < 0xFFFFFFED
      && v12 != -1073741802
      && v12 != -1073741807
      && v12 + 2147483643 > 1
      && v12 != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(0, v12, 524672);
    }
    LOBYTE(v21) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(0, v4, v12, v21, (v12 & 0x80000000) == 0);
    v4 = 0;
    v5 = v46;
    if ( v12 != -1073741608 && v12 != -1073741432 )
      goto LABEL_48;
  }
  v5 = v46;
  NtfsUpdateIrpContextWithTopLevel(v46, v55);
  if ( v5 == *(_QWORD *)(v5 + 144) && LOBYTE(IoGetTopLevelIrp()->Type) )
  {
    if ( IoGetCurrentProcess() == (PEPROCESS)qword_140095530 )
    {
      if ( KeQueryPriorityThread(KeGetCurrentThread()) >= 16 )
      {
        v12 = 259;
        v41 = 259;
        goto LABEL_48;
      }
    }
    else
    {
      *(_DWORD *)(v5 + 12) |= 1u;
    }
  }
  else if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*((_QWORD *)FsContext + 23) + 104LL) + 64LL))
         || *(_DWORD *)(*(_QWORD *)(v5 + 144) + 24LL) )
  {
    v12 = 259;
    v41 = 259;
    goto LABEL_48;
  }
LABEL_21:
  NtfsPreRequestProcessingExtend(v5);
  if ( (*((_DWORD *)FsContext + 50) & 0x200000) == 0 || *(_DWORD *)(*((_QWORD *)FsContext + 23) + 268LL) )
  {
    v12 = NtfsCommonClose(
            v5,
            (_DWORD)FsContext,
            v43,
            v45,
            (__int64)&v40,
            (__int64)v44->SectionObjectPointer,
            v65,
            v42,
            0);
    v41 = v12;
  }
  else
  {
    v12 = 259;
    v41 = 259;
  }
LABEL_48:
  if ( v12 != 259 )
    goto LABEL_120;
  v63 = ExAllocateFromLookasideListEx(&NtfsCloseEntryLookasideList);
  if ( !v63 )
  {
    _InterlockedAdd(&NtfsFailedCloseEntryAllocations, 1u);
    v12 = -1073741670;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225626LL, 524805);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v5, 3221225626LL, 524806);
    LOBYTE(v17) = 1;
    NtfsExtendedCompleteRequestInternal(v5, 0, 3221225626LL, v17, 1);
  }
  if ( v12 == 259 )
  {
    v31 = 0;
    v32 = v44;
    SectionObjectPointer = v44->SectionObjectPointer;
    if ( (*(_DWORD *)(v5 + 12) & 0x100000) != 0 )
    {
      TopLevelIrp = IoGetTopLevelIrp();
      TopLevelIrp->ThreadListEntry.Flink = 0;
      if ( !LOBYTE(TopLevelIrp->Size) )
      {
        *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
        IoSetTopLevelIrp(TopLevelIrp->AssociatedIrp.MasterIrp);
      }
      *(_DWORD *)(v5 + 12) &= ~0x100000u;
    }
    *p_FsContext = 0;
    v32->FsContext2 = 0;
    v32->SectionObjectPointer = 0;
    *(_DWORD *)(v5 + 4) |= 0x400u;
    if ( *(_BYTE *)(*(_QWORD *)(v5 + 104) + 10496LL) )
    {
      *(LARGE_INTEGER *)(v5 + 496) = PerformanceCounter;
      *(_DWORD *)(v5 + 504) = 24;
      v4->Tail.Overlay.CurrentStackLocation[-1].Parameters.Read.ByteOffset = v14;
    }
    LOBYTE(v17) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(v5, v4, 0, v17, 1);
    v12 = 0;
    memset(v63, 0, 0x58u);
    v63[1] = v63;
    *v63 = v63;
    v63[3] = v63 + 2;
    v63[2] = v63 + 2;
    v34 = v52;
    v63[4] = v52;
    v63[5] = v40;
    v63[6] = SectionObjectPointer;
    *((_BYTE *)v63 + 56) = v65;
    if ( v40 )
    {
      if ( !(_BYTE)v42 )
      {
        *p_WriteAccess = 0;
        *p_DeleteAccess = 0;
        _InterlockedAdd((volatile signed __int32 *)(v45 + 264), 1u);
      }
      *((_BYTE *)v63 + 57) = 1;
    }
    if ( (v34[50] & 0x200000) != 0 )
    {
      ClearFlagInterlocked(v34 + 50, 0x200000);
      if ( !*(_DWORD *)(*(_QWORD *)(v37 + 184) + 268LL) )
      {
        v31 = 1;
        if ( (*(_WORD *)(v37 + 460) & 0x80FF) != 0 )
          v31 = (*(_BYTE *)(v37 + 4) & 0x20) == 0;
      }
    }
    LOBYTE(v33) = v31;
    NtfsQueueClose(v5, v63, v33);
    LOBYTE(v35) = 1;
    NtfsExtendedCompleteRequestInternal(v5, 0, 0, v35, 1);
  }
  else
  {
LABEL_120:
    if ( !v12 )
    {
      *p_FsContext = 0;
      v24 = v44;
      v44->FsContext2 = 0;
      v24->SectionObjectPointer = 0;
      if ( v4 )
      {
        v25 = v45;
        if ( *(_BYTE *)(v45 + 10496) )
        {
          v26 = PerformanceCounter;
          if ( PerformanceCounter.QuadPart > 23 )
          {
            v4->Tail.Overlay.CurrentStackLocation[-1].Parameters.Read.ByteOffset = v14;
            OriginatingProcessId = FsLibGetOriginatingProcessId(v4);
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))NtfsIoPerfCollectBasicData)(
              v25,
              v4,
              OriginatingProcessId,
              24,
              (LARGE_INTEGER)v26.QuadPart);
          }
        }
      }
    }
    if ( NtfsStatusDebugFlags
      && v12
      && v12 != 294
      && v12 - 298 > 1
      && v12 < 0xFFFFFFED
      && v12 != -1073741802
      && v12 != -1073741807
      && v12 + 2147483643 > 1
      && v12 != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(0, v12, 525011);
    }
    LOBYTE(v17) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(0, v4, v12, v17, (v12 & 0x80000000) == 0);
  }
  KeLeaveCriticalRegion();
  return v12;
}

```

## disassembly

```asm
0x14013a250  mov     r11, rsp
0x14013a253  mov     [r11+10h], rdx
0x14013a257  push    rbx
0x14013a258  push    rsi
0x14013a259  push    rdi
0x14013a25a  push    r12
0x14013a25c  push    r13
0x14013a25e  push    r14
0x14013a260  push    r15
0x14013a262  sub     rsp, 110h
0x14013a269  mov     r14, rdx
0x14013a26c  xorps   xmm0, xmm0
0x14013a26f  xor     eax, eax
0x14013a271  movups  xmmword ptr [r11-60h], xmm0
0x14013a276  movups  xmmword ptr [r11-50h], xmm0
0x14013a27b  mov     [r11-40h], rax
0x14013a27f  xor     edi, edi
0x14013a281  mov     r13d, edi
0x14013a284  mov     [rsp+148h+var_D0], rdi
0x14013a289  mov     [rsp+148h+var_F8], rdi
0x14013a28e  mov     eax, 150h
0x14013a293  lea     r15d, [rdi+1]
0x14013a297  cmp     [rcx+2], ax
0x14013a29b  jz      loc_14013ACF0
0x14013a2a1  mov     rax, [rdx+0B8h]
0x14013a2a8  mov     rdx, [rax+30h]
0x14013a2ac  mov     [rsp+148h+var_E0], rdx
0x14013a2b1  mov     [rsp+148h+var_80], rdx
0x14013a2b9  lea     rax, [rdx+18h]
0x14013a2bd  mov     [rsp+148h+var_98], rax
0x14013a2c5  mov     r12, [rax]
0x14013a2c8  mov     [rsp+148h+var_A0], r12
0x14013a2d0  test    r12, r12
0x14013a2d3  jz      loc_14013ACC8
0x14013a2d9  mov     rax, [rdx+20h]
0x14013a2dd  mov     rbx, [r12+0C0h]
0x14013a2e5  mov     [rsp+148h+var_D8], rbx
0x14013a2ea  mov     [rsp+148h+var_F8], rax
0x14013a2ef  mov     [rsp+148h+var_B0], rbx
0x14013a2f7  mov     rcx, [r12+0B8h]
0x14013a2ff  mov     [rsp+148h+var_E8], rcx
0x14013a304  mov     [rsp+148h+var_A8], rcx
0x14013a30c  test    rax, rax
0x14013a30f  jz      loc_14013A9D7
0x14013a315  movzx   eax, byte ptr [rax+58h]
0x14013a319  mov     [rsp+148h+arg_18], eax
0x14013a320  cmp     eax, r15d
0x14013a323  jz      loc_14013AD2C
0x14013a329  mov     rcx, [rbx+0D8h]
0x14013a330  cmp     rdx, rcx
0x14013a333  jz      loc_14013AD52
0x14013a339  mov     esi, edi
0x14013a33b  mov     [rsp+148h+var_78], r12
0x14013a343  mov     [rsp+148h+var_C8], eax
0x14013a34a  call    cs:__imp_KeEnterCriticalRegion
0x14013a351  nop     dword ptr [rax+rax+00h]
0x14013a356  mov     al, [rbx+2900h]
0x14013a35c  test    al, al
0x14013a35e  jz      loc_14013A87F
0x14013a364  xor     ecx, ecx; PerformanceFrequency
0x14013a366  call    cs:__imp_KeQueryPerformanceCounter
0x14013a36d  nop     dword ptr [rax+rax+00h]
0x14013a372  mov     [rsp+148h+var_C0], rax
0x14013a37a  mov     rdx, [rsp+148h+var_E8]
0x14013a37f  mov     rbx, [rdx+8]
0x14013a383  mov     [rsp+148h+var_B8], rbx
0x14013a38b  mov     rax, [rsp+148h+var_E0]
0x14013a390  lea     rcx, [rax+4Ch]
0x14013a394  mov     [rsp+148h+var_68], rcx
0x14013a39c  add     rax, 4Bh ; 'K'
0x14013a3a0  mov     [rsp+148h+var_70], rax
0x14013a3a8  mov     al, [rax]
0x14013a3aa  or      al, [rcx]
0x14013a3ac  setz    al
0x14013a3af  mov     byte ptr [rsp+148h+arg_0], al
0x14013a3b6  cmp     [rsp+148h+var_F8], rdi
0x14013a3bb  jnz     loc_14013A95D
0x14013a3c1  mov     [rsp+148h+var_EC], eax
0x14013a3c5  mov     byte ptr [rsp+148h+arg_10], al
0x14013a3cc  mov     r8, [rsp+148h+var_D8]
0x14013a3d1  xor     edx, edx
0x14013a3d3  lea     rcx, [rsp+148h+var_60]
0x14013a3db  call    NtfsInitializeTopLevelIrp
0x14013a3e0  mov     [rsp+148h+var_88], rax
0x14013a3e8  mov     rdx, [rsp+148h+var_E8]
0x14013a3ed  mov     ecx, [rdx+4]
0x14013a3f0  test    cl, 4
0x14013a3f3  jz      loc_14013A920
0x14013a3f9  mov     byte ptr [rsp+148h+arg_0], r15b
0x14013a401  mov     rcx, [rsp+148h+var_E0]
0x14013a406  cmp     [rcx+60h], rdi
0x14013a40a  jnz     loc_14013A90C
0x14013a410  test    dword ptr [rcx+50h], 4000h
0x14013a417  jz      loc_14013A9E8
0x14013a41d  test    r13, r13
0x14013a420  jnz     loc_14013A701
0x14013a426  lea     r9, [rsp+148h+var_D0]
0x14013a42b  xor     r8d, r8d
0x14013a42e  xor     edx, edx
0x14013a430  mov     rcx, r14; Irp
0x14013a433  call    NtfsInitializeIrpContextInternal
0x14013a438  mov     esi, eax
0x14013a43a  mov     [rsp+148h+var_F0], eax
0x14013a43e  test    eax, eax
0x14013a440  js      loc_14013A698
0x14013a446  mov     rdx, [rsp+148h+var_88]
0x14013a44e  mov     r13, [rsp+148h+var_D0]
0x14013a453  mov     rcx, r13
0x14013a456  call    NtfsUpdateIrpContextWithTopLevel
0x14013a45b  cmp     r13, [r13+90h]
0x14013a462  jnz     loc_14013A530
0x14013a468  call    cs:__imp_IoGetTopLevelIrp
0x14013a46f  nop     dword ptr [rax+rax+00h]
0x14013a474  cmp     [rax], dil
0x14013a477  jz      loc_14013A530
0x14013a47d  call    cs:__imp_IoGetCurrentProcess
0x14013a484  nop     dword ptr [rax+rax+00h]
0x14013a489  cmp     rax, cs:qword_140095530
0x14013a490  jnz     short loc_14013A4C0
0x14013a492  mov     rcx, gs:188h; Thread
0x14013a49b  call    cs:__imp_KeQueryPriorityThread
0x14013a4a2  nop     dword ptr [rax+rax+00h]
0x14013a4a7  cmp     eax, 10h
0x14013a4aa  jl      short loc_14013A4C4
0x14013a4ac  mov     al, cs:NtfsStatusDebugFlags
0x14013a4b2  mov     esi, 103h
0x14013a4b7  mov     [rsp+148h+var_F0], esi
0x14013a4bb  jmp     loc_14013A7C5
0x14013a4c0  or      [r13+0Ch], r15d
0x14013a4c4  mov     edx, esi
0x14013a4c6  mov     rcx, r13
0x14013a4c9  call    NtfsPreRequestProcessingExtend
0x14013a4ce  test    dword ptr [r12+0C8h], 200000h
0x14013a4da  jnz     loc_14013A564
0x14013a4e0  mov     [rsp+148h+var_108], dil
0x14013a4e5  mov     eax, [rsp+148h+var_EC]
0x14013a4e9  mov     [rsp+148h+var_110], al
0x14013a4ed  mov     eax, [rsp+148h+arg_18]
0x14013a4f4  mov     dword ptr [rsp+148h+var_118], eax
0x14013a4f8  mov     rax, [rsp+148h+var_E0]
0x14013a4fd  mov     rax, [rax+28h]
0x14013a501  mov     [rsp+148h+PostIrpRoutine], rax
0x14013a506  lea     rax, [rsp+148h+var_F8]
0x14013a50b  mov     [rsp+148h+CompletionRoutine], rax
0x14013a510  mov     r9, [rsp+148h+var_D8]
0x14013a515  mov     r8, [rsp+148h+var_E8]
0x14013a51a  mov     rdx, r12
0x14013a51d  mov     rcx, r13
0x14013a520  call    NtfsCommonClose
0x14013a525  mov     esi, eax
0x14013a527  mov     [rsp+148h+var_F0], eax
0x14013a52b  jmp     loc_14013A71A
0x14013a530  mov     rax, [r12+0B8h]
0x14013a538  mov     rcx, [rax+68h]
0x14013a53c  add     rcx, 40h ; '@'; Resource
0x14013a540  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14013a547  nop     dword ptr [rax+rax+00h]
0x14013a54c  test    al, al
0x14013a54e  jnz     short loc_14013A58C
0x14013a550  mov     al, cs:NtfsStatusDebugFlags
0x14013a556  mov     esi, 103h
0x14013a55b  mov     [rsp+148h+var_F0], esi
0x14013a55f  jmp     loc_14013A7C5
0x14013a564  mov     rax, [r12+0B8h]
0x14013a56c  cmp     [rax+10Ch], edi
0x14013a572  jnz     loc_14013A4E0
0x14013a578  mov     al, cs:NtfsStatusDebugFlags
0x14013a57e  mov     esi, 103h
0x14013a583  mov     [rsp+148h+var_F0], esi
0x14013a587  jmp     loc_14013A71A
0x14013a58c  mov     rax, [r13+90h]
0x14013a593  cmp     [rax+18h], edi
0x14013a596  jz      loc_14013A4C4
0x14013a59c  jmp     short loc_14013A550
0x14013a59e  add     rax, 38h ; '8'
0x14013a5a2  mov     rdx, [rax]
0x14013a5a5  cmp     [rdx+8], rax
0x14013a5a9  jnz     loc_14013A691
0x14013a5af  mov     rcx, [rax+8]
0x14013a5b3  cmp     [rcx], rax
0x14013a5b6  jnz     loc_14013A691
0x14013a5bc  mov     [rcx], rdx
0x14013a5bf  mov     [rdx+8], rcx
0x14013a5c3  mov     rax, [rsp+148h+var_F8]
0x14013a5c8  mov     [rax+48h], rdi
0x14013a5cc  mov     rcx, [r13+68h]
0x14013a5d0  add     rcx, 8; FastMutex
0x14013a5d4  call    cs:__imp_ExReleaseFastMutex
0x14013a5db  nop     dword ptr [rax+rax+00h]
0x14013a5e0  lea     rdx, [rsp+148h+var_F8]
0x14013a5e5  mov     rcx, r13
0x14013a5e8  call    NtfsDeleteCcb
0x14013a5ed  mov     rax, [rsp+148h+var_90]
0x14013a5f5  mov     [rsp+148h+var_118], rdi
0x14013a5fa  mov     byte ptr [rsp+148h+PostIrpRoutine], r15b
0x14013a5ff  mov     ecx, [rsp+148h+var_EC]
0x14013a603  mov     byte ptr [rsp+148h+CompletionRoutine], cl
0x14013a607  mov     r9b, byte ptr [rsp+148h+arg_0]
0x14013a60f  mov     r8, rax
0x14013a612  mov     rdx, r12
0x14013a615  xor     ecx, ecx
0x14013a617  call    NtfsDecrementCloseCounts
0x14013a61c  mov     al, cs:NtfsStatusDebugFlags
0x14013a622  test    al, al
0x14013a624  jz      short loc_14013A65D
0x14013a626  cmp     esi, 0FFFFFFEDh
0x14013a629  jnb     short loc_14013A65D
0x14013a62b  cmp     esi, 0C0000016h
0x14013a631  jz      short loc_14013A65D
0x14013a633  cmp     esi, 0C0000011h
0x14013a639  jz      short loc_14013A65D
0x14013a63b  lea     eax, [rsi+7FFFFFFBh]
0x14013a641  cmp     eax, r15d
0x14013a644  jbe     short loc_14013A65D
0x14013a646  cmp     esi, 0C00000D8h
0x14013a64c  jz      short loc_14013A65D
0x14013a64e  mov     r8d, 80180h
0x14013a654  mov     edx, esi
0x14013a656  xor     ecx, ecx
0x14013a658  call    NtfsStatusTraceAndDebugInternal
0x14013a65d  mov     eax, esi
0x14013a65f  not     eax
0x14013a661  shr     eax, 1Fh
0x14013a664  test    r14, r14
0x14013a667  setnz   r9b
0x14013a66b  mov     dword ptr [rsp+148h+CompletionRoutine], eax
0x14013a66f  mov     r8d, esi
0x14013a672  mov     rdx, r14
0x14013a675  xor     ecx, ecx
0x14013a677  call    NtfsExtendedCompleteRequestInternal
0x14013a67c  mov     r14, rdi
0x14013a67f  mov     [rsp+148h+arg_8], rdi
0x14013a687  mov     r13, [rsp+148h+var_D0]
0x14013a68c  jmp     loc_14013AD84
0x14013a691  mov     ecx, 3
0x14013a696  int     29h; Win8: RtlFailFast(ecx)
0x14013a698  lock add cs:NtfsFailedCloseIrpContextAllocations, r15d
0x14013a6a0  mov     r8, [rsp+148h+var_F8]
0x14013a6a5  mov     rdx, r12
0x14013a6a8  mov     rax, [rsp+148h+var_E0]
0x14013a6ad  mov     rcx, [rax+28h]
0x14013a6b1  call    TxfCheckForFloaterDelete
0x14013a6b6  mov     rax, [rsp+148h+var_F8]
0x14013a6bb  test    rax, rax
0x14013a6be  jz      short loc_14013A6F9
0x14013a6c0  mov     rcx, [rax+48h]
0x14013a6c4  mov     [rsp+148h+var_90], rcx
0x14013a6cc  mov     r13, [rsp+148h+var_E8]
0x14013a6d1  mov     rcx, [r13+68h]
0x14013a6d5  add     rcx, 8; FastMutex
0x14013a6d9  call    cs:__imp_ExAcquireFastMutex
0x14013a6e0  nop     dword ptr [rax+rax+00h]
0x14013a6e5  mov     rax, [rsp+148h+var_F8]
0x14013a6ea  cmp     [rax+48h], rdi
0x14013a6ee  jz      loc_14013A5CC
0x14013a6f4  jmp     loc_14013A59E
0x14013a6f9  mov     rax, rdi
0x14013a6fc  jmp     loc_14013A5F5
0x14013a701  cmp     esi, 0C0000188h
0x14013a707  jnz     loc_14013A4C4
0x14013a70d  mov     rcx, r13
0x14013a710  call    NtfsCheckpointForLogFileFull
0x14013a715  jmp     loc_14013A4C4
0x14013a71a  jmp     loc_14013A7C5
0x14013a71f  mov     r8d, eax
0x14013a722  mov     r14, [rsp+148h+arg_8]
0x14013a72a  mov     rdx, r14
0x14013a72d  mov     r13, [rsp+148h+var_D0]
0x14013a732  mov     rcx, r13
0x14013a735  call    NtfsProcessException
0x14013a73a  mov     esi, eax
0x14013a73c  mov     [rsp+148h+var_F0], eax
0x14013a740  cmp     eax, 0C00000D8h
0x14013a745  jz      short loc_14013A762
0x14013a747  cmp     eax, 103h
0x14013a74c  jz      short loc_14013A762
0x14013a74e  xor     eax, eax
0x14013a750  cmp     esi, 0C0000188h
0x14013a756  cmovnz  r14, rax
0x14013a75a  mov     [rsp+148h+arg_8], r14
0x14013a762  xor     edi, edi
0x14013a764  lea     r15d, [rdi+1]
0x14013a768  mov     rbx, [rsp+148h+var_B8]
0x14013a770  mov     rax, [rsp+148h+var_80]
0x14013a778  mov     [rsp+148h+var_E0], rax
0x14013a77d  mov     eax, [rsp+148h+var_C8]
0x14013a784  mov     [rsp+148h+arg_18], eax
0x14013a78b  mov     al, byte ptr [rsp+148h+arg_10]
0x14013a792  mov     [rsp+148h+var_EC], eax
0x14013a796  mov     rax, [rsp+148h+var_B0]
0x14013a79e  mov     [rsp+148h+var_D8], rax
0x14013a7a3  mov     rax, [rsp+148h+var_A8]
0x14013a7ab  mov     [rsp+148h+var_E8], rax
0x14013a7b0  mov     r12, [rsp+148h+var_78]
0x14013a7b8  mov     [rsp+148h+var_A0], r12
0x14013a7c0  jmp     loc_14013AD84
0x14013a7c5  mov     [rsp+148h+arg_0], rdi
0x14013a7cd  cmp     esi, 103h
0x14013a7d3  jz      loc_14013AA54
0x14013a7d9  test    esi, esi
  ... truncated ...
```
