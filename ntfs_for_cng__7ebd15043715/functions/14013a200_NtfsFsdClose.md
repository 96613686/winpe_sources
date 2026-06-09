# NtfsFsdClose

- ea: `0x14013a200`
- end: `0x14013ad79`
- name: `NtfsFsdClose`
- size: `2937`
- prototype: `__int64 __fastcall(__int64, IRP *)`
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
- `0x1400596c0`
- `0x140139ed0`
- `0x14013a200`
- `0x14013ad80`
- `0x14013b870`
- `0x1401879b0`
- `0x1401e7c70`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14013a2fa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14013a2fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14013a7ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14013a7ba`
- `ntoskrnl!IofCompleteRequest` at `0x14013acad`
- `ntoskrnl!IofCompleteRequest` at `0x14013acad`
- `ntoskrnl!KeQueryPriorityThread` at `0x14013a44b`
- `ntoskrnl!KeQueryPriorityThread` at `0x14013a44b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14013abb2`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14013abb2`
- `ntoskrnl!IoGetCurrentProcess` at `0x14013a42d`
- `ntoskrnl!IoGetCurrentProcess` at `0x14013a42d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14013aa0b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14013aa0b`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14013ac2f`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14013ac2f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013a689`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013a915`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013a689`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013a915`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013a584`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013a976`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013a584`
- `ntoskrnl!ExReleaseFastMutex` at `0x14013a976`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14013a418`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14013ab95`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14013a418`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14013ab95`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14013a4f0`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14013a4f0`
- `HAL!KeQueryPerformanceCounter` at `0x14013a316`
- `HAL!KeQueryPerformanceCounter` at `0x14013a316`

## pseudocode

```c
__int64 __fastcall NtfsFsdClose(__int64 a1, IRP *a2)
{
  IRP *v2; // r14
  __int64 v3; // r13
  PFILE_OBJECT FileObject; // rdx
  __int64 FsContext; // r12
  unsigned __int8 *FsContext2; // rax
  __int64 v7; // rbx
  int v8; // eax
  struct _FILE_OBJECT *v9; // rcx
  int v10; // esi
  LARGE_INTEGER *v11; // rdx
  LARGE_INTEGER v12; // rbx
  int v13; // eax
  PFILE_OBJECT v14; // rcx
  unsigned __int8 *v15; // rax
  __int64 v16; // rdx
  unsigned __int8 **v17; // rcx
  __int64 v18; // rax
  LARGE_INTEGER *v19; // r13
  PFILE_OBJECT v21; // rax
  __int64 v22; // r13
  __int64 QuadPart; // r12
  HANDLE OriginatingProcessId; // rax
  LARGE_INTEGER *v25; // r10
  int v26; // eax
  int v27; // eax
  char v28; // r12
  PFILE_OBJECT v29; // rsi
  __int64 v30; // r9
  PIRP TopLevelIrp; // rax
  __int64 v32; // r9
  _DWORD *v33; // rax
  PFILE_OBJECT v34; // rax
  unsigned __int8 *v35; // [rsp+50h] [rbp-F8h] BYREF
  int v36; // [rsp+58h] [rbp-F0h]
  int v37; // [rsp+5Ch] [rbp-ECh]
  LARGE_INTEGER *v38; // [rsp+60h] [rbp-E8h]
  PFILE_OBJECT v39; // [rsp+68h] [rbp-E0h]
  __int64 v40; // [rsp+70h] [rbp-D8h]
  __int64 v41; // [rsp+78h] [rbp-D0h] BYREF
  int v42; // [rsp+80h] [rbp-C8h]
  LARGE_INTEGER PerformanceCounter; // [rsp+88h] [rbp-C0h]
  LARGE_INTEGER v44; // [rsp+90h] [rbp-B8h]
  __int64 v45; // [rsp+98h] [rbp-B0h]
  LARGE_INTEGER *v46; // [rsp+A0h] [rbp-A8h]
  __int64 v47; // [rsp+A8h] [rbp-A0h]
  PVOID *p_FsContext; // [rsp+B0h] [rbp-98h]
  __int64 v49; // [rsp+B8h] [rbp-90h]
  ULONG_PTR v50; // [rsp+C0h] [rbp-88h]
  PFILE_OBJECT v51; // [rsp+C8h] [rbp-80h]
  __int64 v52; // [rsp+D0h] [rbp-78h]
  BOOLEAN *p_WriteAccess; // [rsp+D8h] [rbp-70h]
  BOOLEAN *p_DeleteAccess; // [rsp+E0h] [rbp-68h]
  _BYTE v55[32]; // [rsp+E8h] [rbp-60h] BYREF
  __int64 v56; // [rsp+108h] [rbp-40h]
  unsigned __int8 v57; // [rsp+150h] [rbp+8h]
  char v58; // [rsp+150h] [rbp+8h]
  _QWORD *v59; // [rsp+150h] [rbp+8h]
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // [rsp+160h] [rbp+18h]
  int v61; // [rsp+168h] [rbp+20h]

  v2 = a2;
  memset(v55, 0, sizeof(v55));
  v56 = 0;
  v3 = 0;
  v41 = 0;
  v35 = 0;
  if ( *(_WORD *)(a1 + 2) == 336 )
  {
    a2->IoStatus.Status = 0;
    a2->IoStatus.Information = 1;
    IofCompleteRequest(a2, 1);
    return 0;
  }
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  v39 = FileObject;
  v51 = FileObject;
  p_FsContext = &FileObject->FsContext;
  FsContext = (__int64)FileObject->FsContext;
  v47 = FsContext;
  if ( FsContext )
  {
    FsContext2 = (unsigned __int8 *)FileObject->FsContext2;
    v7 = *(_QWORD *)(FsContext + 192);
    v40 = v7;
    v35 = FsContext2;
    v45 = v7;
    v38 = *(LARGE_INTEGER **)(FsContext + 184);
    v46 = v38;
    if ( !FsContext2 )
    {
      v8 = 5;
      v61 = 5;
      goto LABEL_6;
    }
    v8 = FsContext2[88];
  }
  else
  {
    v7 = 0;
    v40 = 0;
    v45 = 0;
    v38 = 0;
    v46 = 0;
    v8 = 1;
  }
  v61 = v8;
  if ( v8 == 1 )
  {
LABEL_117:
    NtfsExtendedCompleteRequestInternal(0, v2, 0, v2 != 0, 1);
    return 0;
  }
LABEL_6:
  v9 = *(struct _FILE_OBJECT **)(v7 + 216);
  if ( FileObject == v9 )
  {
    v33 = v9->FsContext;
    if ( v33 && (v33[50] & 0x4000) == 0 )
    {
      v9->FileName.MaximumLength = 0;
      *(_WORD *)(*(_QWORD *)(v7 + 216) + 88LL) = 0;
      *(_QWORD *)(*(_QWORD *)(v7 + 216) + 96LL) = 0;
    }
    *(_QWORD *)(v7 + 216) = 0;
    goto LABEL_117;
  }
  v10 = 0;
  v52 = FsContext;
  v42 = v8;
  KeEnterCriticalRegion();
  if ( *(_BYTE *)(v7 + 10496) )
  {
    PerformanceCounter = KeQueryPerformanceCounter(0);
    v11 = v38;
    v12 = v38[1];
  }
  else
  {
    PerformanceCounter.QuadPart = 0;
    v12.QuadPart = 0;
    v11 = v38;
  }
  v44 = v12;
  p_DeleteAccess = &v39->DeleteAccess;
  v13 = (_DWORD)v39 + 75;
  p_WriteAccess = &v39->WriteAccess;
  LOBYTE(v13) = *(_WORD *)&v39->WriteAccess == 0;
  v57 = v13;
  if ( v35 )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(v11[13].QuadPart + 8));
    if ( (*((_DWORD *)v35 + 1) & 0x80000) == 0 )
      _InterlockedOr((volatile signed __int32 *)v35 + 1, 0x80000u);
    v25 = v38;
    v26 = v57;
    if ( (v38->HighPart & 0x40000000) != 0 )
      v26 = 0;
    v37 = v26;
    if ( (*((_DWORD *)v35 + 1) & 0x10000000) != 0 )
    {
      SetFlagInterlocked((unsigned int *)v35 + 1, 0x4000u);
      v34 = v39;
      v39->FileName.Buffer = 0;
      *(_DWORD *)&v34->FileName.Length = 0;
    }
    ExReleaseFastMutex((PFAST_MUTEX)(v25[13].QuadPart + 8));
  }
  else
  {
    v37 = v13;
  }
  v50 = NtfsInitializeTopLevelIrp((__int64)v55, 0, v40);
  v58 = (v38->HighPart & 4) != 0
     || v61 == 5
     || v35 && ((*((_DWORD *)v35 + 2) & 4) != 0 || (v38->HighPart & 0x40000000) != 0);
  v14 = v39;
  if ( v39->FileName.Buffer && !v39->FileName.Length )
    v39->FileName.Length = 1;
  if ( (v14->Flags & 0x4000) == 0 )
  {
    if ( (v27 = *(_DWORD *)(FsContext + 256), v27 == 128) && *(_WORD *)FsContext == 1797
      || v27 == 160
      && *(_WORD *)(FsContext + 264) == 8
      && **(_QWORD **)(FsContext + 272) == 0x30003300490024LL
      && (unsigned __int16)(*(_WORD *)FsContext - 1795) <= 1u )
    {
      FsRtlCheckOplockEx((POPLOCK)(FsContext + 88), v2, 0, 0, 0, 0);
    }
  }
  while ( 1 )
  {
    if ( v3 )
    {
      if ( v10 == -1073741432 )
        NtfsCheckpointForLogFileFull(v3);
      goto LABEL_23;
    }
    v10 = NtfsInitializeIrpContextInternal(v2, 0, 0, &v41);
    v36 = v10;
    if ( v10 >= 0 )
      break;
    _InterlockedAdd(&NtfsFailedCloseIrpContextAllocations, 1u);
    TxfCheckForFloaterDelete(v39->SectionObjectPointer, FsContext, v35);
    if ( v35 )
    {
      v49 = *((_QWORD *)v35 + 9);
      v19 = v38;
      ExAcquireFastMutex((PFAST_MUTEX)(v38[13].QuadPart + 8));
      if ( *((_QWORD *)v35 + 9) )
      {
        v15 = v35 + 56;
        v16 = *((_QWORD *)v35 + 7);
        if ( *(unsigned __int8 **)(*(_QWORD *)v15 + 8LL) != v15
          || (v17 = (unsigned __int8 **)*((_QWORD *)v35 + 8), *v17 != v15) )
        {
          __fastfail(3u);
        }
        *v17 = (unsigned __int8 *)v16;
        *(_QWORD *)(v16 + 8) = v17;
        *((_QWORD *)v35 + 9) = 0;
      }
      ExReleaseFastMutex((PFAST_MUTEX)(v19[13].QuadPart + 8));
      NtfsDeleteCcb(v19, &v35);
      v18 = v49;
    }
    else
    {
      v18 = 0;
    }
    NtfsDecrementCloseCounts(0, FsContext, v18, v58, v37, 1, 0);
    if ( NtfsStatusDebugFlags
      && (unsigned int)v10 < 0xFFFFFFED
      && v10 != -1073741802
      && v10 != -1073741807
      && (unsigned int)(v10 + 2147483643) > 1
      && v10 != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(0, v10, 0x80180u);
    }
    NtfsExtendedCompleteRequestInternal(0, v2, v10, v2 != 0, v10 >= 0);
    v2 = 0;
    v3 = v41;
    if ( v10 != -1073741608 && v10 != -1073741432 )
      goto LABEL_50;
  }
  v3 = v41;
  NtfsUpdateIrpContextWithTopLevel(v41, v50);
  if ( v3 == *(_QWORD *)(v3 + 144) && LOBYTE(IoGetTopLevelIrp()->Type) )
  {
    if ( IoGetCurrentProcess() == (PEPROCESS)qword_140095530 )
    {
      if ( KeQueryPriorityThread(KeGetCurrentThread()) >= 16 )
      {
        v10 = 259;
        v36 = 259;
        goto LABEL_50;
      }
    }
    else
    {
      *(_DWORD *)(v3 + 12) |= 1u;
    }
  }
  else if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(FsContext + 184) + 104LL) + 64LL))
         || *(_DWORD *)(*(_QWORD *)(v3 + 144) + 24LL) )
  {
    v10 = 259;
    v36 = 259;
    goto LABEL_50;
  }
LABEL_23:
  NtfsPreRequestProcessingExtend(v3, v10);
  if ( (*(_DWORD *)(FsContext + 200) & 0x200000) == 0 || *(_DWORD *)(*(_QWORD *)(FsContext + 184) + 268LL) )
  {
    v10 = NtfsCommonClose(
            v3,
            FsContext,
            (_DWORD)v38,
            v40,
            (__int64)&v35,
            (__int64)v39->SectionObjectPointer,
            v61,
            v37,
            0);
    v36 = v10;
  }
  else
  {
    v10 = 259;
    v36 = 259;
  }
LABEL_50:
  if ( v10 != 259 )
    goto LABEL_127;
  v59 = ExAllocateFromLookasideListEx(&NtfsCloseEntryLookasideList);
  if ( !v59 )
  {
    _InterlockedAdd(&NtfsFailedCloseEntryAllocations, 1u);
    v10 = -1073741670;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC000009A, 0x80205u);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 0xC000009A, 0x80206u);
    NtfsExtendedCompleteRequestInternal(v3, 0, -1073741670, 1u, 1);
  }
  if ( v10 == 259 )
  {
    v28 = 0;
    v29 = v39;
    SectionObjectPointer = v39->SectionObjectPointer;
    if ( (*(_DWORD *)(v3 + 12) & 0x100000) != 0 )
    {
      TopLevelIrp = IoGetTopLevelIrp();
      TopLevelIrp->ThreadListEntry.Flink = 0;
      if ( !LOBYTE(TopLevelIrp->Size) )
      {
        *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
        IoSetTopLevelIrp(TopLevelIrp->AssociatedIrp.MasterIrp);
      }
      *(_DWORD *)(v3 + 12) &= ~0x100000u;
    }
    *p_FsContext = 0;
    v29->FsContext2 = 0;
    v29->SectionObjectPointer = 0;
    *(_DWORD *)(v3 + 4) |= 0x400u;
    if ( *(_BYTE *)(*(_QWORD *)(v3 + 104) + 10496LL) )
    {
      *(LARGE_INTEGER *)(v3 + 496) = PerformanceCounter;
      *(_DWORD *)(v3 + 504) = 24;
      v2->Tail.Overlay.CurrentStackLocation[-1].Parameters.Read.ByteOffset = v12;
    }
    NtfsExtendedCompleteRequestInternal(v3, v2, 0, v2 != 0, 1);
    v10 = 0;
    memset(v59, 0, 0x58u);
    v59[1] = v59;
    *v59 = v59;
    v59[3] = v59 + 2;
    v59[2] = v59 + 2;
    v30 = v47;
    v59[4] = v47;
    v59[5] = v35;
    v59[6] = SectionObjectPointer;
    *((_BYTE *)v59 + 56) = v61;
    if ( v35 )
    {
      if ( !(_BYTE)v37 )
      {
        *p_WriteAccess = 0;
        *p_DeleteAccess = 0;
        _InterlockedAdd((volatile signed __int32 *)(v40 + 264), 1u);
      }
      *((_BYTE *)v59 + 57) = 1;
    }
    if ( (*(_DWORD *)(v30 + 200) & 0x200000) != 0 )
    {
      ClearFlagInterlocked((unsigned int *)(v30 + 200), 0x200000);
      if ( !*(_DWORD *)(*(_QWORD *)(v32 + 184) + 268LL) )
      {
        v28 = 1;
        if ( (*(_WORD *)(v32 + 460) & 0x80FF) != 0 )
          v28 = (*(_BYTE *)(v32 + 4) & 0x20) == 0;
      }
    }
    NtfsQueueClose(v3, (__int64)v59, v28);
    NtfsExtendedCompleteRequestInternal(v3, 0, 0, 1u, 1);
  }
  else
  {
LABEL_127:
    if ( !v10 )
    {
      *p_FsContext = 0;
      v21 = v39;
      v39->FsContext2 = 0;
      v21->SectionObjectPointer = 0;
      if ( v2 )
      {
        v22 = v40;
        if ( *(_BYTE *)(v40 + 10496) )
        {
          QuadPart = PerformanceCounter.QuadPart;
          if ( PerformanceCounter.QuadPart > 23 )
          {
            v2->Tail.Overlay.CurrentStackLocation[-1].Parameters.Read.ByteOffset = v12;
            OriginatingProcessId = FsLibGetOriginatingProcessId(v2);
            NtfsIoPerfCollectBasicData(v22, (__int64)v2, (__int64)OriginatingProcessId, 24, QuadPart);
          }
        }
      }
    }
    if ( NtfsStatusDebugFlags
      && v10
      && v10 != 294
      && (unsigned int)(v10 - 298) > 1
      && (unsigned int)v10 < 0xFFFFFFED
      && v10 != -1073741802
      && v10 != -1073741807
      && (unsigned int)(v10 + 2147483643) > 1
      && v10 != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(0, v10, 0x802D3u);
    }
    NtfsExtendedCompleteRequestInternal(0, v2, v10, v2 != 0, v10 >= 0);
  }
  KeLeaveCriticalRegion();
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14013a200  mov     r11, rsp
0x14013a203  mov     [r11+10h], rdx
0x14013a207  push    rbx
0x14013a208  push    rsi
0x14013a209  push    rdi
0x14013a20a  push    r12
0x14013a20c  push    r13
0x14013a20e  push    r14
0x14013a210  push    r15
0x14013a212  sub     rsp, 110h
0x14013a219  mov     r14, rdx
0x14013a21c  xorps   xmm0, xmm0
0x14013a21f  xor     eax, eax
0x14013a221  movups  xmmword ptr [r11-60h], xmm0
0x14013a226  movups  xmmword ptr [r11-50h], xmm0
0x14013a22b  mov     [r11-40h], rax
0x14013a22f  xor     edi, edi
0x14013a231  mov     r13d, edi
0x14013a234  mov     [rsp+148h+var_D0], rdi
0x14013a239  mov     [rsp+148h+var_F8], rdi
0x14013a23e  mov     eax, 150h
0x14013a243  lea     r15d, [rdi+1]
0x14013a247  cmp     [rcx+2], ax
0x14013a24b  jz      loc_14013ACA0
0x14013a251  mov     rax, [rdx+0B8h]
0x14013a258  mov     rdx, [rax+30h]
0x14013a25c  mov     [rsp+148h+var_E0], rdx
0x14013a261  mov     [rsp+148h+var_80], rdx
0x14013a269  lea     rax, [rdx+18h]
0x14013a26d  mov     [rsp+148h+var_98], rax
0x14013a275  mov     r12, [rax]
0x14013a278  mov     [rsp+148h+var_A0], r12
0x14013a280  test    r12, r12
0x14013a283  jz      loc_14013AC78
0x14013a289  mov     rax, [rdx+20h]
0x14013a28d  mov     rbx, [r12+0C0h]
0x14013a295  mov     [rsp+148h+var_D8], rbx
0x14013a29a  mov     [rsp+148h+var_F8], rax
0x14013a29f  mov     [rsp+148h+var_B0], rbx
0x14013a2a7  mov     rcx, [r12+0B8h]
0x14013a2af  mov     [rsp+148h+var_E8], rcx
0x14013a2b4  mov     [rsp+148h+var_A8], rcx
0x14013a2bc  test    rax, rax
0x14013a2bf  jz      loc_14013A987
0x14013a2c5  movzx   eax, byte ptr [rax+58h]
0x14013a2c9  mov     [rsp+148h+arg_18], eax
0x14013a2d0  cmp     eax, r15d
0x14013a2d3  jz      loc_14013ACDC
0x14013a2d9  mov     rcx, [rbx+0D8h]
0x14013a2e0  cmp     rdx, rcx
0x14013a2e3  jz      loc_14013AD02
0x14013a2e9  mov     esi, edi
0x14013a2eb  mov     [rsp+148h+var_78], r12
0x14013a2f3  mov     [rsp+148h+var_C8], eax
0x14013a2fa  call    cs:__imp_KeEnterCriticalRegion
0x14013a301  nop     dword ptr [rax+rax+00h]
0x14013a306  mov     al, [rbx+2900h]
0x14013a30c  test    al, al
0x14013a30e  jz      loc_14013A82F
0x14013a314  xor     ecx, ecx; PerformanceFrequency
0x14013a316  call    cs:__imp_KeQueryPerformanceCounter
0x14013a31d  nop     dword ptr [rax+rax+00h]
0x14013a322  mov     [rsp+148h+var_C0], rax
0x14013a32a  mov     rdx, [rsp+148h+var_E8]
0x14013a32f  mov     rbx, [rdx+8]
0x14013a333  mov     [rsp+148h+var_B8], rbx
0x14013a33b  mov     rax, [rsp+148h+var_E0]
0x14013a340  lea     rcx, [rax+4Ch]
0x14013a344  mov     [rsp+148h+var_68], rcx
0x14013a34c  add     rax, 4Bh ; 'K'
0x14013a350  mov     [rsp+148h+var_70], rax
0x14013a358  mov     al, [rax]
0x14013a35a  or      al, [rcx]
0x14013a35c  setz    al
0x14013a35f  mov     byte ptr [rsp+148h+arg_0], al
0x14013a366  cmp     [rsp+148h+var_F8], rdi
0x14013a36b  jnz     loc_14013A90D
0x14013a371  mov     [rsp+148h+var_EC], eax
0x14013a375  mov     byte ptr [rsp+148h+arg_10], al
0x14013a37c  mov     r8, [rsp+148h+var_D8]
0x14013a381  xor     edx, edx
0x14013a383  lea     rcx, [rsp+148h+var_60]
0x14013a38b  call    NtfsInitializeTopLevelIrp
0x14013a390  mov     [rsp+148h+var_88], rax
0x14013a398  mov     rdx, [rsp+148h+var_E8]
0x14013a39d  mov     ecx, [rdx+4]
0x14013a3a0  test    cl, 4
0x14013a3a3  jz      loc_14013A8D0
0x14013a3a9  mov     byte ptr [rsp+148h+arg_0], r15b
0x14013a3b1  mov     rcx, [rsp+148h+var_E0]
0x14013a3b6  cmp     [rcx+60h], rdi
0x14013a3ba  jnz     loc_14013A8BC
0x14013a3c0  test    dword ptr [rcx+50h], 4000h
0x14013a3c7  jz      loc_14013A998
0x14013a3cd  test    r13, r13
0x14013a3d0  jnz     loc_14013A6B1
0x14013a3d6  lea     r9, [rsp+148h+var_D0]
0x14013a3db  xor     r8d, r8d
0x14013a3de  xor     edx, edx
0x14013a3e0  mov     rcx, r14; Irp
0x14013a3e3  call    NtfsInitializeIrpContextInternal
0x14013a3e8  mov     esi, eax
0x14013a3ea  mov     [rsp+148h+var_F0], eax
0x14013a3ee  test    eax, eax
0x14013a3f0  js      loc_14013A648
0x14013a3f6  mov     rdx, [rsp+148h+var_88]
0x14013a3fe  mov     r13, [rsp+148h+var_D0]
0x14013a403  mov     rcx, r13
0x14013a406  call    NtfsUpdateIrpContextWithTopLevel
0x14013a40b  cmp     r13, [r13+90h]
0x14013a412  jnz     loc_14013A4E0
0x14013a418  call    cs:__imp_IoGetTopLevelIrp
0x14013a41f  nop     dword ptr [rax+rax+00h]
0x14013a424  cmp     [rax], dil
0x14013a427  jz      loc_14013A4E0
0x14013a42d  call    cs:__imp_IoGetCurrentProcess
0x14013a434  nop     dword ptr [rax+rax+00h]
0x14013a439  cmp     rax, cs:qword_140095530
0x14013a440  jnz     short loc_14013A470
0x14013a442  mov     rcx, gs:188h; Thread
0x14013a44b  call    cs:__imp_KeQueryPriorityThread
0x14013a452  nop     dword ptr [rax+rax+00h]
0x14013a457  cmp     eax, 10h
0x14013a45a  jl      short loc_14013A474
0x14013a45c  mov     al, cs:NtfsStatusDebugFlags
0x14013a462  mov     esi, 103h
0x14013a467  mov     [rsp+148h+var_F0], esi
0x14013a46b  jmp     loc_14013A775
0x14013a470  or      [r13+0Ch], r15d
0x14013a474  mov     edx, esi
0x14013a476  mov     rcx, r13
0x14013a479  call    NtfsPreRequestProcessingExtend
0x14013a47e  test    dword ptr [r12+0C8h], 200000h
0x14013a48a  jnz     loc_14013A514
0x14013a490  mov     [rsp+148h+var_108], dil
0x14013a495  mov     eax, [rsp+148h+var_EC]
0x14013a499  mov     [rsp+148h+var_110], al
0x14013a49d  mov     eax, [rsp+148h+arg_18]
0x14013a4a4  mov     dword ptr [rsp+148h+var_118], eax
0x14013a4a8  mov     rax, [rsp+148h+var_E0]
0x14013a4ad  mov     rax, [rax+28h]
0x14013a4b1  mov     [rsp+148h+PostIrpRoutine], rax
0x14013a4b6  lea     rax, [rsp+148h+var_F8]
0x14013a4bb  mov     [rsp+148h+CompletionRoutine], rax
0x14013a4c0  mov     r9, [rsp+148h+var_D8]
0x14013a4c5  mov     r8, [rsp+148h+var_E8]
0x14013a4ca  mov     rdx, r12
0x14013a4cd  mov     rcx, r13
0x14013a4d0  call    NtfsCommonClose
0x14013a4d5  mov     esi, eax
0x14013a4d7  mov     [rsp+148h+var_F0], eax
0x14013a4db  jmp     loc_14013A6CA
0x14013a4e0  mov     rax, [r12+0B8h]
0x14013a4e8  mov     rcx, [rax+68h]
0x14013a4ec  add     rcx, 40h ; '@'; Resource
0x14013a4f0  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14013a4f7  nop     dword ptr [rax+rax+00h]
0x14013a4fc  test    al, al
0x14013a4fe  jnz     short loc_14013A53C
0x14013a500  mov     al, cs:NtfsStatusDebugFlags
0x14013a506  mov     esi, 103h
0x14013a50b  mov     [rsp+148h+var_F0], esi
0x14013a50f  jmp     loc_14013A775
0x14013a514  mov     rax, [r12+0B8h]
0x14013a51c  cmp     [rax+10Ch], edi
0x14013a522  jnz     loc_14013A490
0x14013a528  mov     al, cs:NtfsStatusDebugFlags
0x14013a52e  mov     esi, 103h
0x14013a533  mov     [rsp+148h+var_F0], esi
0x14013a537  jmp     loc_14013A6CA
0x14013a53c  mov     rax, [r13+90h]
0x14013a543  cmp     [rax+18h], edi
0x14013a546  jz      loc_14013A474
0x14013a54c  jmp     short loc_14013A500
0x14013a54e  add     rax, 38h ; '8'
0x14013a552  mov     rdx, [rax]
0x14013a555  cmp     [rdx+8], rax
0x14013a559  jnz     loc_14013A641
0x14013a55f  mov     rcx, [rax+8]
0x14013a563  cmp     [rcx], rax
0x14013a566  jnz     loc_14013A641
0x14013a56c  mov     [rcx], rdx
0x14013a56f  mov     [rdx+8], rcx
0x14013a573  mov     rax, [rsp+148h+var_F8]
0x14013a578  mov     [rax+48h], rdi
0x14013a57c  mov     rcx, [r13+68h]
0x14013a580  add     rcx, 8; FastMutex
0x14013a584  call    cs:__imp_ExReleaseFastMutex
0x14013a58b  nop     dword ptr [rax+rax+00h]
0x14013a590  lea     rdx, [rsp+148h+var_F8]
0x14013a595  mov     rcx, r13
0x14013a598  call    NtfsDeleteCcb
0x14013a59d  mov     rax, [rsp+148h+var_90]
0x14013a5a5  mov     [rsp+148h+var_118], rdi
0x14013a5aa  mov     byte ptr [rsp+148h+PostIrpRoutine], r15b
0x14013a5af  mov     ecx, [rsp+148h+var_EC]
0x14013a5b3  mov     byte ptr [rsp+148h+CompletionRoutine], cl
0x14013a5b7  mov     r9b, byte ptr [rsp+148h+arg_0]
0x14013a5bf  mov     r8, rax
0x14013a5c2  mov     rdx, r12
0x14013a5c5  xor     ecx, ecx
0x14013a5c7  call    NtfsDecrementCloseCounts
0x14013a5cc  mov     al, cs:NtfsStatusDebugFlags
0x14013a5d2  test    al, al
0x14013a5d4  jz      short loc_14013A60D
0x14013a5d6  cmp     esi, 0FFFFFFEDh
0x14013a5d9  jnb     short loc_14013A60D
0x14013a5db  cmp     esi, 0C0000016h
0x14013a5e1  jz      short loc_14013A60D
0x14013a5e3  cmp     esi, 0C0000011h
0x14013a5e9  jz      short loc_14013A60D
0x14013a5eb  lea     eax, [rsi+7FFFFFFBh]
0x14013a5f1  cmp     eax, r15d
0x14013a5f4  jbe     short loc_14013A60D
0x14013a5f6  cmp     esi, 0C00000D8h
0x14013a5fc  jz      short loc_14013A60D
0x14013a5fe  mov     r8d, 80180h
0x14013a604  mov     edx, esi
0x14013a606  xor     ecx, ecx
0x14013a608  call    NtfsStatusTraceAndDebugInternal
0x14013a60d  mov     eax, esi
0x14013a60f  not     eax
0x14013a611  shr     eax, 1Fh
0x14013a614  test    r14, r14
0x14013a617  setnz   r9b
0x14013a61b  mov     dword ptr [rsp+148h+CompletionRoutine], eax
0x14013a61f  mov     r8d, esi
0x14013a622  mov     rdx, r14
0x14013a625  xor     ecx, ecx
0x14013a627  call    NtfsExtendedCompleteRequestInternal
0x14013a62c  mov     r14, rdi
0x14013a62f  mov     [rsp+148h+arg_8], rdi
0x14013a637  mov     r13, [rsp+148h+var_D0]
0x14013a63c  jmp     loc_14013AD34
0x14013a641  mov     ecx, 3
0x14013a646  int     29h; Win8: RtlFailFast(ecx)
0x14013a648  lock add cs:NtfsFailedCloseIrpContextAllocations, r15d
0x14013a650  mov     r8, [rsp+148h+var_F8]
0x14013a655  mov     rdx, r12
0x14013a658  mov     rax, [rsp+148h+var_E0]
0x14013a65d  mov     rcx, [rax+28h]
0x14013a661  call    TxfCheckForFloaterDelete
0x14013a666  mov     rax, [rsp+148h+var_F8]
0x14013a66b  test    rax, rax
0x14013a66e  jz      short loc_14013A6A9
0x14013a670  mov     rcx, [rax+48h]
0x14013a674  mov     [rsp+148h+var_90], rcx
0x14013a67c  mov     r13, [rsp+148h+var_E8]
0x14013a681  mov     rcx, [r13+68h]
0x14013a685  add     rcx, 8; FastMutex
0x14013a689  call    cs:__imp_ExAcquireFastMutex
0x14013a690  nop     dword ptr [rax+rax+00h]
0x14013a695  mov     rax, [rsp+148h+var_F8]
0x14013a69a  cmp     [rax+48h], rdi
0x14013a69e  jz      loc_14013A57C
0x14013a6a4  jmp     loc_14013A54E
0x14013a6a9  mov     rax, rdi
0x14013a6ac  jmp     loc_14013A5A5
0x14013a6b1  cmp     esi, 0C0000188h
0x14013a6b7  jnz     loc_14013A474
0x14013a6bd  mov     rcx, r13
0x14013a6c0  call    NtfsCheckpointForLogFileFull
0x14013a6c5  jmp     loc_14013A474
0x14013a6ca  jmp     loc_14013A775
0x14013a6cf  mov     r8d, eax
0x14013a6d2  mov     r14, [rsp+148h+arg_8]
0x14013a6da  mov     rdx, r14
0x14013a6dd  mov     r13, [rsp+148h+var_D0]
0x14013a6e2  mov     rcx, r13
0x14013a6e5  call    NtfsProcessException
0x14013a6ea  mov     esi, eax
0x14013a6ec  mov     [rsp+148h+var_F0], eax
0x14013a6f0  cmp     eax, 0C00000D8h
0x14013a6f5  jz      short loc_14013A712
0x14013a6f7  cmp     eax, 103h
0x14013a6fc  jz      short loc_14013A712
0x14013a6fe  xor     eax, eax
0x14013a700  cmp     esi, 0C0000188h
0x14013a706  cmovnz  r14, rax
0x14013a70a  mov     [rsp+148h+arg_8], r14
0x14013a712  xor     edi, edi
0x14013a714  lea     r15d, [rdi+1]
0x14013a718  mov     rbx, [rsp+148h+var_B8]
0x14013a720  mov     rax, [rsp+148h+var_80]
0x14013a728  mov     [rsp+148h+var_E0], rax
0x14013a72d  mov     eax, [rsp+148h+var_C8]
0x14013a734  mov     [rsp+148h+arg_18], eax
0x14013a73b  mov     al, byte ptr [rsp+148h+arg_10]
0x14013a742  mov     [rsp+148h+var_EC], eax
0x14013a746  mov     rax, [rsp+148h+var_B0]
0x14013a74e  mov     [rsp+148h+var_D8], rax
0x14013a753  mov     rax, [rsp+148h+var_A8]
0x14013a75b  mov     [rsp+148h+var_E8], rax
0x14013a760  mov     r12, [rsp+148h+var_78]
0x14013a768  mov     [rsp+148h+var_A0], r12
0x14013a770  jmp     loc_14013AD34
0x14013a775  mov     [rsp+148h+arg_0], rdi
0x14013a77d  cmp     esi, 103h
0x14013a783  jz      loc_14013AA04
0x14013a789  test    esi, esi
  ... truncated ...
```
