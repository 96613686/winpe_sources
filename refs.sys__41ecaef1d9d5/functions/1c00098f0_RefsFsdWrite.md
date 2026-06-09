# RefsFsdWrite

- ea: `0x1c00098f0`
- end: `0x1c000a18a`
- name: `RefsFsdWrite`
- size: `2202`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1c000444c`
- `0x1c00098f0`
- `0x1c000a190`
- `0x1c000f480`
- `0x1c000f770`
- `0x1c00133b0`
- `0x1c0013f90`
- `0x1c003aa60`
- `0x1c004d164`
- `0x1c00588cc`
- `0x1c005bb10`
- `0x1c0062ce0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c006af80`
- `0x1c00a7c98`
- `0x1c00aad24`
- `0x1c00ab2a8`
- `0x1c00b3dc8`
- `0x1c01635d0`
- `0x1c018f524`
- `0x1c01cd29c`
- `0x1c01d3c80`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1c0009bf6`
- `ntoskrnl!KeInitializeEvent` at `0x1c0009bf6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c0009e2a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c0009e2a`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c00099af`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c0009cb8`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c0009cf3`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c00099af`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c0009cb8`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c0009cf3`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0009a9b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0009a9b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0009a71`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c007054a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0009a71`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c007054a`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c0009abd`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c0009abd`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c007057e`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c007057e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c000a0e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c000a0e2`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c0009a1c`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c0009a33`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c0009a1c`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c0009a33`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0009b73`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0009b73`
- `ntoskrnl!CcCanIWrite` at `0x1c0009f8e`
- `ntoskrnl!CcCanIWrite` at `0x1c0009f8e`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1c0009f00`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1c0009f00`
- `ntoskrnl!IoWithinStackLimits` at `0x1c00099c6`
- `ntoskrnl!IoWithinStackLimits` at `0x1c00099c6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c0009b41`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c0009b41`

## string_xrefs

- `0x1c0009eb8`: `write.c`
- `0x1c000a164`: `write.c`
- `0x1c007046c`: `write.c`
- `0x1c00704c0`: `write.c`
- `0x1c007052f`: `write.c`

## pseudocode

```c
__int64 __fastcall RefsFsdWrite(__int64 a1, IRP *a2)
{
  unsigned int v3; // esi
  LARGE_INTEGER *v4; // rdi
  bool v5; // r15
  PFILE_OBJECT FileObject; // r14
  _DWORD *FsContext; // r14
  bool v8; // r12
  ULONG_PTR TopLevelIrp; // rbx
  char v10; // al
  BOOLEAN IsOperationSynchronous; // al
  NTSTATUS v12; // eax
  char v13; // al
  LARGE_INTEGER v14; // rax
  int v15; // eax
  int v16; // r12d
  char v17; // r14
  unsigned int LowPart; // r9d
  struct _SLIST_ENTRY *QuadPart; // r10
  PSLIST_ENTRY v20; // rcx
  unsigned int v21; // edx
  ULONG CurrentProcessorNumber; // eax
  struct _SLIST_ENTRY *v23; // r12
  unsigned __int64 v24; // r14
  unsigned int v25; // edx
  LARGE_INTEGER v26; // rax
  LARGE_INTEGER v27; // rax
  _QWORD *v28; // rax
  LARGE_INTEGER v29; // rsi
  LARGE_INTEGER v30; // rax
  char v31; // cl
  LONG HighPart; // eax
  NTSTATUS v33; // eax
  bool v34; // r14
  LARGE_INTEGER v35; // rdx
  __int64 v36; // r8
  LARGE_INTEGER v37; // rax
  __int64 v38; // rax
  unsigned int v39; // ecx
  __int64 v41; // rax
  void *v42; // rsp
  unsigned int v43; // ebx
  _BYTE v44[288]; // [rsp+0h] [rbp-150h] BYREF
  char v45; // [rsp+150h] [rbp+0h]
  char v46; // [rsp+151h] [rbp+1h]
  char v47; // [rsp+152h] [rbp+2h]
  NTSTATUS Status; // [rsp+154h] [rbp+4h]
  int v49; // [rsp+158h] [rbp+8h]
  PVOID Context1; // [rsp+160h] [rbp+10h] BYREF
  ULONG_PTR v51; // [rsp+168h] [rbp+18h]
  ULONG v52; // [rsp+170h] [rbp+20h]
  int v53; // [rsp+174h] [rbp+24h]
  PSLIST_ENTRY v54; // [rsp+178h] [rbp+28h]
  __int64 v55; // [rsp+180h] [rbp+30h] BYREF
  _QWORD Irp[45]; // [rsp+188h] [rbp+38h] BYREF
  __int128 v57; // [rsp+2F0h] [rbp+1A0h] BYREF

  Irp[6] = a2;
  memset(Irp, 0, 40);
  v3 = 0;
  v4 = 0;
  Context1 = 0;
  v53 = 0;
  memset(&Irp[7], 0, 0x130u);
  v5 = 0;
  v57 = 0;
  v55 = 0;
  v49 = 0;
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( (FileObject->Flags & 0x20000000) != 0 )
  {
    RefsCompleteWriteRequest(0, a2, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids, 0);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(0);
    return 0;
  }
  FsContext = FileObject->FsContext;
  if ( FsContext && (*(_DWORD *)(*((_QWORD *)FsContext + 15) + 4LL) & 4) != 0 )
    v5 = (FsContext[34] & 0x10) != 0;
  LOBYTE(v51) = 1;
  v8 = 0;
  TopLevelIrp = (ULONG_PTR)IoGetTopLevelIrp();
  if ( IoWithinStackLimits(TopLevelIrp, 0x28u) && (TopLevelIrp & 3) == 0 )
    v8 = *(_DWORD *)(TopLevelIrp + 4) == 1397140410;
  if ( !TopLevelIrp )
  {
    v10 = v51;
LABEL_8:
    Irp[3] = TopLevelIrp;
    Irp[4] = 0;
    LOBYTE(Irp[0]) = v10;
    if ( v8 )
    {
      Irp[1] = *(_QWORD *)(TopLevelIrp + 8);
      Irp[2] = *(_QWORD *)(TopLevelIrp + 16);
      BYTE1(Irp[0]) = 1;
      BYTE2(Irp[0]) = *(_BYTE *)(TopLevelIrp + 2);
    }
    else
    {
      *(_OWORD *)&Irp[1] = 0;
      *(_WORD *)((char *)Irp + 1) = 0;
    }
    TopLevelIrp = (ULONG_PTR)Irp;
    goto LABEL_11;
  }
  if ( TopLevelIrp <= 0xFFFF )
  {
    v10 = 0;
    goto LABEL_8;
  }
  if ( !v8 || (v41 = *(_QWORD *)(TopLevelIrp + 32)) != 0 && (*(_DWORD *)(v41 + 4) & 0x200) != 0 )
  {
    v10 = v51;
    if ( TopLevelIrp == 2147483650 )
      v10 = 0;
    goto LABEL_8;
  }
LABEL_11:
  v51 = TopLevelIrp;
  if ( v5 )
  {
    if ( (*(_DWORD *)(*((_QWORD *)FsContext + 15) + 4LL) & 1) != 0 )
    {
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741533);
      RefsExtendedCompleteRequestInternal(0, a2, 3221225763LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids, 3221225763LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741533);
      return 3221225763LL;
    }
    KeEnterCriticalRegion();
  }
  else
  {
    if ( IoIsOperationSynchronous(a2) && (a2->Flags & 2) != 0 )
    {
      v42 = alloca(336);
      v4 = (LARGE_INTEGER *)v44;
      Context1 = v44;
      v12 = RefsInitializeLocalIrpContext(a2, v44);
    }
    else
    {
      IsOperationSynchronous = IoIsOperationSynchronous(a2);
      v12 = RefsInitializeIrpContext(a2, IsOperationSynchronous, 0, &Context1);
      v4 = (LARGE_INTEGER *)Context1;
    }
    Status = v12;
    v3 = v12;
    if ( v12 < 0 )
    {
      v43 = Status;
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(Status);
      RefsExtendedCompleteRequestInternal(0, a2, v43);
      return v43;
    }
    v13 = BYTE1(v4[5].LowPart);
    if ( (v13 & 2) != 0 && (v13 & 4) == 0 )
      a2->MdlAddress = 0;
    KeEnterCriticalRegion();
    v14 = *(LARGE_INTEGER *)(TopLevelIrp + 32);
    if ( !v14.QuadPart )
    {
      *(_DWORD *)(TopLevelIrp + 4) = 1397140410;
      *(_QWORD *)(TopLevelIrp + 32) = v4;
      v4[1].LowPart |= 0x100000u;
      IoSetTopLevelIrp((PIRP)TopLevelIrp);
      v14 = *(LARGE_INTEGER *)(TopLevelIrp + 32);
    }
    v4[13] = v14;
  }
  if ( (int)IoPropagateActivityIdToThread(a2, &v57, &v55) >= 0 )
    v15 = 1;
  else
    v15 = v49;
  v49 = v15;
  v16 = 53;
  v17 = 0;
  while ( 1 )
  {
    if ( !v17 )
    {
      v34 = (a2->Flags & 2) != 0;
      v45 = v34;
      LowPart = v4[1].LowPart;
      QuadPart = (struct _SLIST_ENTRY *)v4[18].QuadPart;
      v20 = QuadPart;
      v21 = LowPart;
      if ( QuadPart && (LowPart & 0x8010) == 0x8000 && QuadPart != (struct _SLIST_ENTRY *)&Irp[7] )
      {
        v4[18].QuadPart = 0;
        v21 = LowPart & 0xFFFF7FFF;
        v4[1].LowPart = LowPart & 0xFFFF7FFF;
        v20 = 0;
      }
      if ( !v20 || (v21 & 0x10) == 0 )
      {
        if ( (LowPart & 1) != 0 && v34 )
        {
          v4[18].QuadPart = (LONGLONG)&Irp[7];
          v25 = v21 & 0xFFFFFFEF;
          v4[1].LowPart = v25;
          v20 = (PSLIST_ENTRY)&Irp[7];
        }
        else
        {
          Irp[5] = RefsIoContextLookasideList;
          v54 = 0;
          v52 = 0;
          CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
          v52 = CurrentProcessorNumber;
          if ( CurrentProcessorNumber >= RefsNumberProcessors )
          {
            CurrentProcessorNumber %= (unsigned int)RefsNumberProcessors;
            v52 = CurrentProcessorNumber;
          }
          v23 = (struct _SLIST_ENTRY *)CurrentProcessorNumber;
          v24 = Irp[5] + ((unsigned __int64)CurrentProcessorNumber << 7);
          ++*(_DWORD *)(v24 + 20);
          v20 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v24);
          if ( !v20 )
          {
            ++*(_DWORD *)(v24 + 24);
            v20 = (PSLIST_ENTRY)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v24 + 48))(
                                  *(unsigned int *)(v24 + 36),
                                  *(unsigned int *)(v24 + 44),
                                  *(unsigned int *)(v24 + 40));
          }
          v54 = v20;
          if ( v20 )
          {
            v20->Next = v23;
            v20 = (PSLIST_ENTRY)((char *)v20 + 8);
            v54 = v20;
          }
          v4[18].QuadPart = (LONGLONG)v20;
          v4[1].LowPart |= 0x10u;
          v25 = v4[1].LowPart;
          v34 = v45;
          v16 = 53;
        }
        v4[1].LowPart = v25 | 0x8000;
      }
      memset(v20, 0, 0x130u);
      if ( (v4[1].LowPart & 0x10) != 0 )
        *(_DWORD *)v4[18].QuadPart |= 1u;
      if ( v34 )
        *(_DWORD *)v4[18].QuadPart |= 2u;
      KeInitializeEvent((PRKEVENT)(v4[18].QuadPart + 8), NotificationEvent, 0);
      v26 = v4[18];
      *(_QWORD *)(v26.QuadPart + 152) = 0;
      *(_QWORD *)(v26.QuadPart + 160) = 0;
      *(_DWORD *)(v26.QuadPart + 156) = 1;
      v27 = v4[18];
      *(_OWORD *)(v27.QuadPart + 216) = 0;
      *(_OWORD *)(v27.QuadPart + 232) = 0;
      *(_OWORD *)(v27.QuadPart + 248) = 0;
      *(_OWORD *)(v27.QuadPart + 264) = 0;
      *(_QWORD *)(v27.QuadPart + 280) = 0;
      v28 = (_QWORD *)(v4[18].QuadPart + 224);
      v28[1] = v28;
      *v28 = v28;
      *(_DWORD *)(v4[18].QuadPart + 244) = 1;
      *(_DWORD *)(v4[18].QuadPart + 216) = 72;
      v45 = 1;
      v46 = 1;
      v17 = 1;
    }
    if ( v3 == -1073741432 )
    {
      RefsCheckpointForLogFileFull(v4);
      goto LABEL_41;
    }
    if ( v3 != 871 )
      goto LABEL_41;
    a2->Tail.Overlay.CurrentStackLocation->Control &= ~1u;
    Status = KeWaitForSingleObject((PVOID)(v4[18].QuadPart + 8), Executive, 0, 0, 0);
    v35 = v4[18];
    if ( v35.QuadPart )
    {
      MsFreeCacheContextResources(*(_QWORD *)(v4[8].QuadPart + 104), v35.QuadPart + 216);
      MsCleanupFastResourceOwnerEntry(v4[18].QuadPart + 80);
      if ( (v4[1].LowPart & 0x10) != 0 )
      {
        ((void (__fastcall *)(_QWORD, _QWORD))RefsFreeNPagedPerProcessorLookaside)(
          RefsIoContextLookasideList,
          (LARGE_INTEGER)v4[18].QuadPart);
        v4[1].LowPart &= ~0x10u;
      }
      v4[18].QuadPart = 0;
      v4[1].LowPart &= ~0x8000u;
    }
    v46 = 0;
    Status = a2->IoStatus.Status;
    if ( Status < 0 )
      break;
    v36 = a2->Flags >> 1;
    LOBYTE(v36) = (a2->Flags & 2) != 0;
    RefsInitializeIoContext(v4, &Irp[7], v36);
    v17 = 1;
    v46 = 1;
LABEL_41:
    if ( v4 )
    {
      v29 = v4[9];
      if ( v4 != (LARGE_INTEGER *)v4[13].QuadPart )
        goto LABEL_53;
      if ( LOBYTE(IoGetTopLevelIrp()->Type) )
      {
        v30 = v4[8];
        if ( v30.QuadPart )
        {
          if ( v29.QuadPart && *(_QWORD *)(v30.QuadPart + 104) && (unsigned __int8)MsVolumeHasReadCache() )
            ((void (__fastcall *)(_QWORD))IoClearFsTrackOffsetState)((LARGE_INTEGER)v29.QuadPart);
        }
      }
      if ( v4 != (LARGE_INTEGER *)v4[13].QuadPart )
        goto LABEL_53;
      if ( !LOBYTE(IoGetTopLevelIrp()->Type) )
        goto LABEL_53;
      v31 = v4[5].QuadPart;
      if ( v31 )
      {
        if ( v31 != 13 )
          goto LABEL_53;
      }
      v37 = v4[8];
      if ( !v37.QuadPart || (*(_DWORD *)(v37.QuadPart + 4) & 1) == 0 )
        goto LABEL_53;
      v47 = 0;
      v38 = *(_QWORD *)(v29.QuadPart + 184);
      if ( v31 )
      {
        if ( *(_DWORD *)(v38 + 24) != 589988 )
          goto LABEL_53;
      }
      else
      {
        v39 = *(unsigned __int8 *)(v38 + 19);
        if ( (*(_DWORD *)(v38 + 16) & 1) == 0
          || (v4[1].LowPart & 8) != 0
          || (unsigned __int8)v39 > 5u
          || !_bittest(&v16, v39) )
        {
LABEL_53:
          HighPart = v4->HighPart;
          if ( (HighPart & 0x200000) != 0 )
          {
            v4->HighPart = HighPart & 0xFFDFFFFF;
            ((void (__fastcall *)(_QWORD, _QWORD))RefsPerformVerify)(v4, (LARGE_INTEGER)v29.QuadPart);
          }
          goto LABEL_55;
        }
      }
      v47 = 1;
      CcCanIWrite(0, 0x80000u, 1u, 0);
      goto LABEL_53;
    }
LABEL_55:
    if ( (v4[5].LowPart & 0x400) != 0 )
    {
      v33 = RefsCompleteMdl(v4, a2);
    }
    else if ( (a2->Flags & 2) != 0 )
    {
      v33 = RefsCommonWriteOnNewStack(v4, a2);
    }
    else
    {
      v33 = RefsCommonWrite(v4, a2);
    }
    v3 = v33;
    Status = v33;
    ++v53;
    if ( v33 != -1073741608 && v33 != -1073741432 && v33 != -1073741400 && v33 != 871 || (_QWORD *)TopLevelIrp != Irp )
      goto LABEL_91;
  }
  v3 = Status;
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(Status);
  RefsExtendedCompleteRequestInternal(Context1, a2, v3);
LABEL_91:
  if ( v49 )
    IoClearActivityIdThread(v55);
  KeLeaveCriticalRegion();
  return v3;
}

```

## disassembly

```asm
0x1c00098f0  push    rbp
0x1c00098f2  push    r12
0x1c00098f4  push    r13
0x1c00098f6  push    r14
0x1c00098f8  push    r15
0x1c00098fa  sub     rsp, 1F0h
0x1c0009901  lea     rbp, [rsp+30h]
0x1c0009906  mov     [rbp+1E0h+arg_0], rbx
0x1c000990d  mov     [rbp+1E0h+arg_10], rsi
0x1c0009914  mov     [rbp+1E0h+arg_18], rdi
0x1c000991b  mov     rax, cs:__security_cookie
0x1c0009922  xor     rax, rbp
0x1c0009925  mov     [rbp+1E0h+var_30], rax
0x1c000992c  mov     r13, rdx
0x1c000992f  mov     qword ptr [rbp+1E0h+Irp+30h], rdx
0x1c0009933  xorps   xmm0, xmm0
0x1c0009936  xor     eax, eax
0x1c0009938  movups  xmmword ptr [rbp+1E0h+Irp], xmm0
0x1c000993c  movups  xmmword ptr [rbp+1E0h+Irp+10h], xmm0
0x1c0009940  mov     qword ptr [rbp+1E0h+Irp+20h], rax
0x1c0009944  xor     ebx, ebx
0x1c0009946  mov     esi, ebx
0x1c0009948  mov     edi, ebx
0x1c000994a  mov     [rbp+1E0h+Context1], rbx
0x1c000994e  mov     [rbp+1E0h+var_1BC], ebx
0x1c0009951  xor     edx, edx; Val
0x1c0009953  mov     r8d, 130h; Size
0x1c0009959  lea     rcx, [rbp+1E0h+Irp+38h]; void *
0x1c000995d  call    memset
0x1c0009962  xor     r15b, r15b
0x1c0009965  xorps   xmm0, xmm0
0x1c0009968  movups  [rbp+1E0h+var_40], xmm0
0x1c000996f  mov     [rbp+1E0h+var_1B0], rbx
0x1c0009973  mov     [rbp+1E0h+var_1D8], ebx
0x1c0009976  mov     rax, [r13+0B8h]
0x1c000997d  mov     r14, [rax+30h]
0x1c0009981  test    dword ptr [r14+50h], 20000000h
0x1c0009989  jnz     loc_1C000A126
0x1c000998f  mov     r14, [r14+18h]
0x1c0009993  test    r14, r14
0x1c0009996  jz      short loc_1C00099A8
0x1c0009998  mov     rax, [r14+78h]
0x1c000999c  mov     ecx, [rax+4]
0x1c000999f  test    cl, 4
0x1c00099a2  jnz     loc_1C0070390
0x1c00099a8  mov     byte ptr [rbp+1E0h+var_1C8], 1
0x1c00099ac  xor     r12b, r12b
0x1c00099af  call    cs:__imp_IoGetTopLevelIrp
0x1c00099b6  nop     dword ptr [rax+rax+00h]
0x1c00099bb  mov     rbx, rax
0x1c00099be  mov     edx, 28h ; '('; RegionSize
0x1c00099c3  mov     rcx, rax; RegionStart
0x1c00099c6  call    cs:__imp_IoWithinStackLimits
0x1c00099cd  nop     dword ptr [rax+rax+00h]
0x1c00099d2  test    eax, eax
0x1c00099d4  jnz     loc_1C00703A7
0x1c00099da  test    rbx, rbx
0x1c00099dd  jnz     loc_1C00703C9
0x1c00099e3  mov     eax, dword ptr [rbp+1E0h+var_1C8]
0x1c00099e6  xor     ecx, ecx
0x1c00099e8  mov     qword ptr [rbp+1E0h+Irp+18h], rbx
0x1c00099ec  mov     qword ptr [rbp+1E0h+Irp+20h], rcx
0x1c00099f0  mov     [rbp+1E0h+Irp], al
0x1c00099f3  test    r12b, r12b
0x1c00099f6  jnz     loc_1C0070411
0x1c00099fc  xorps   xmm0, xmm0
0x1c00099ff  movdqu  xmmword ptr [rbp+1E0h+Irp+8], xmm0
0x1c0009a04  mov     word ptr [rbp+1E0h+Irp+1], si
0x1c0009a08  lea     rbx, [rbp+1E0h+Irp]
0x1c0009a0c  mov     [rbp+1E0h+var_1C8], rbx
0x1c0009a10  test    r15b, r15b
0x1c0009a13  jnz     loc_1C007049F
0x1c0009a19  mov     rcx, r13; Irp
0x1c0009a1c  call    cs:__imp_IoIsOperationSynchronous
0x1c0009a23  nop     dword ptr [rax+rax+00h]
0x1c0009a28  test    al, al
0x1c0009a2a  jnz     loc_1C000A179
0x1c0009a30  mov     rcx, r13; Irp
0x1c0009a33  call    cs:__imp_IoIsOperationSynchronous
0x1c0009a3a  nop     dword ptr [rax+rax+00h]
0x1c0009a3f  movzx   edx, al
0x1c0009a42  lea     r9, [rbp+1E0h+Context1]
0x1c0009a46  xor     r8d, r8d
0x1c0009a49  mov     rcx, r13
0x1c0009a4c  call    RefsInitializeIrpContext
0x1c0009a51  mov     rdi, [rbp+1E0h+Context1]
0x1c0009a55  mov     [rbp+1E0h+Status], eax
0x1c0009a58  mov     esi, eax
0x1c0009a5a  test    eax, eax
0x1c0009a5c  js      loc_1C0070458
0x1c0009a62  movzx   eax, byte ptr [rdi+29h]
0x1c0009a66  xor     r15d, r15d
0x1c0009a69  test    al, 2
0x1c0009a6b  jnz     loc_1C007048E
0x1c0009a71  call    cs:__imp_KeEnterCriticalRegion
0x1c0009a78  nop     dword ptr [rax+rax+00h]
0x1c0009a7d  mov     rax, [rbx+20h]
0x1c0009a81  test    rax, rax
0x1c0009a84  jnz     short loc_1C0009AAB
0x1c0009a86  mov     dword ptr [rbx+4], 5346ABBAh
0x1c0009a8d  mov     [rbx+20h], rdi
0x1c0009a91  or      dword ptr [rdi+8], 100000h
0x1c0009a98  mov     rcx, rbx; Irp
0x1c0009a9b  call    cs:__imp_IoSetTopLevelIrp
0x1c0009aa2  nop     dword ptr [rax+rax+00h]
0x1c0009aa7  mov     rax, [rbx+20h]
0x1c0009aab  mov     [rdi+68h], rax
0x1c0009aaf  lea     r8, [rbp+1E0h+var_1B0]
0x1c0009ab3  lea     rdx, [rbp+1E0h+var_40]
0x1c0009aba  mov     rcx, r13
0x1c0009abd  call    cs:__imp_IoPropagateActivityIdToThread
0x1c0009ac4  nop     dword ptr [rax+rax+00h]
0x1c0009ac9  test    eax, eax
0x1c0009acb  jns     loc_1C007055E
0x1c0009ad1  mov     eax, [rbp+1E0h+var_1D8]
0x1c0009ad4  mov     [rbp+1E0h+var_1D8], eax
0x1c0009ad7  mov     r12d, 35h ; '5'
0x1c0009add  xor     r14b, r14b
0x1c0009ae0  test    r14b, r14b
0x1c0009ae3  jnz     loc_1C0009C91
0x1c0009ae9  mov     eax, [r13+10h]
0x1c0009aed  test    al, 2
0x1c0009aef  jnz     loc_1C0009D91
0x1c0009af5  mov     [rbp+1E0h+var_1E0], r14b
0x1c0009af9  mov     r9d, [rdi+8]
0x1c0009afd  mov     r8d, r9d
0x1c0009b00  and     r8d, 1
0x1c0009b04  mov     r10, [rdi+90h]
0x1c0009b0b  mov     rcx, r10
0x1c0009b0e  mov     edx, r9d
0x1c0009b11  test    r10, r10
0x1c0009b14  jnz     loc_1C0009D99
0x1c0009b1a  test    rcx, rcx
0x1c0009b1d  jnz     loc_1C0009DCF
0x1c0009b23  test    r8d, r8d
0x1c0009b26  jnz     loc_1C0009D6E
0x1c0009b2c  mov     rax, cs:RefsIoContextLookasideList
0x1c0009b33  mov     qword ptr [rbp+1E0h+Irp+28h], rax
0x1c0009b37  mov     [rbp+1E0h+var_1B8], r15
0x1c0009b3b  mov     [rbp+1E0h+var_1C0], r15d
0x1c0009b3f  xor     ecx, ecx; ProcNumber
0x1c0009b41  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1c0009b48  nop     dword ptr [rax+rax+00h]
0x1c0009b4d  mov     [rbp+1E0h+var_1C0], eax
0x1c0009b50  mov     ecx, cs:RefsNumberProcessors
0x1c0009b56  cmp     eax, ecx
0x1c0009b58  jnb     loc_1C0009DDD
0x1c0009b5e  mov     r12d, eax
0x1c0009b61  mov     r14d, eax
0x1c0009b64  shl     r14, 7
0x1c0009b68  add     r14, qword ptr [rbp+1E0h+Irp+28h]
0x1c0009b6c  inc     dword ptr [r14+14h]
0x1c0009b70  mov     rcx, r14; ListHead
0x1c0009b73  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0009b7a  nop     dword ptr [rax+rax+00h]
0x1c0009b7f  mov     rcx, rax
0x1c0009b82  test    rax, rax
0x1c0009b85  jz      loc_1C0009D4C
0x1c0009b8b  mov     [rbp+1E0h+var_1B8], rcx
0x1c0009b8f  test    rcx, rcx
0x1c0009b92  jz      short loc_1C0009B9F
0x1c0009b94  mov     [rcx], r12
0x1c0009b97  add     rcx, 8; void *
0x1c0009b9b  mov     [rbp+1E0h+var_1B8], rcx
0x1c0009b9f  mov     [rdi+90h], rcx
0x1c0009ba6  or      dword ptr [rdi+8], 10h
0x1c0009baa  mov     edx, [rdi+8]
0x1c0009bad  movzx   r14d, [rbp+1E0h+var_1E0]
0x1c0009bb2  mov     r12d, 35h ; '5'
0x1c0009bb8  bts     edx, 0Fh
0x1c0009bbc  mov     [rdi+8], edx
0x1c0009bbf  xor     edx, edx; Val
0x1c0009bc1  mov     r8d, 130h; Size
0x1c0009bc7  call    memset
0x1c0009bcc  mov     eax, [rdi+8]
0x1c0009bcf  test    al, 10h
0x1c0009bd1  jz      short loc_1C0009BDD
0x1c0009bd3  mov     rax, [rdi+90h]
0x1c0009bda  or      dword ptr [rax], 1
0x1c0009bdd  test    r14b, r14b
0x1c0009be0  jnz     loc_1C0009DEB
0x1c0009be6  mov     rcx, [rdi+90h]
0x1c0009bed  add     rcx, 8; Event
0x1c0009bf1  xor     r8d, r8d; State
0x1c0009bf4  xor     edx, edx; Type
0x1c0009bf6  call    cs:__imp_KeInitializeEvent
0x1c0009bfd  nop     dword ptr [rax+rax+00h]
0x1c0009c02  mov     rax, [rdi+90h]
0x1c0009c09  mov     qword ptr [rax+98h], 0
0x1c0009c14  mov     [rax+0A0h], r15
0x1c0009c1b  mov     ecx, 1
0x1c0009c20  mov     [rax+9Ch], ecx
0x1c0009c26  mov     rax, [rdi+90h]
0x1c0009c2d  xorps   xmm0, xmm0
0x1c0009c30  xor     edx, edx
0x1c0009c32  movups  xmmword ptr [rax+0D8h], xmm0
0x1c0009c39  movups  xmmword ptr [rax+0E8h], xmm0
0x1c0009c40  movups  xmmword ptr [rax+0F8h], xmm0
0x1c0009c47  movups  xmmword ptr [rax+108h], xmm0
0x1c0009c4e  mov     [rax+118h], rdx
0x1c0009c55  mov     rax, [rdi+90h]
0x1c0009c5c  add     rax, 0E0h
0x1c0009c62  mov     [rax+8], rax
0x1c0009c66  mov     [rax], rax
0x1c0009c69  mov     rax, [rdi+90h]
0x1c0009c70  mov     [rax+0F4h], ecx
0x1c0009c76  mov     rax, [rdi+90h]
0x1c0009c7d  mov     dword ptr [rax+0D8h], 48h ; 'H'
0x1c0009c87  mov     [rbp+1E0h+var_1E0], cl
0x1c0009c8a  mov     [rbp+1E0h+var_1DF], cl
0x1c0009c8d  movzx   r14d, cl
0x1c0009c91  cmp     esi, 0C0000188h
0x1c0009c97  jz      loc_1C0009DFA
0x1c0009c9d  cmp     esi, 367h
0x1c0009ca3  jz      loc_1C0009E07
0x1c0009ca9  test    rdi, rdi
0x1c0009cac  jz      short loc_1C0009D26
0x1c0009cae  mov     rsi, [rdi+48h]
0x1c0009cb2  cmp     rdi, [rdi+68h]
0x1c0009cb6  jnz     short loc_1C0009D19
0x1c0009cb8  call    cs:__imp_IoGetTopLevelIrp
0x1c0009cbf  nop     dword ptr [rax+rax+00h]
0x1c0009cc4  cmp     byte ptr [rax], 0
0x1c0009cc7  jz      short loc_1C0009CED
0x1c0009cc9  mov     rax, [rdi+40h]
0x1c0009ccd  test    rax, rax
0x1c0009cd0  jz      short loc_1C0009CED
0x1c0009cd2  test    rsi, rsi
0x1c0009cd5  jz      short loc_1C0009CED
0x1c0009cd7  mov     rcx, [rax+68h]
0x1c0009cdb  test    rcx, rcx
0x1c0009cde  jz      short loc_1C0009CED
0x1c0009ce0  call    MsVolumeHasReadCache
0x1c0009ce5  test    al, al
0x1c0009ce7  jnz     loc_1C0009EFD
0x1c0009ced  cmp     rdi, [rdi+68h]
0x1c0009cf1  jnz     short loc_1C0009D19
0x1c0009cf3  call    cs:__imp_IoGetTopLevelIrp
0x1c0009cfa  nop     dword ptr [rax+rax+00h]
0x1c0009cff  cmp     byte ptr [rax], 0
0x1c0009d02  jz      short loc_1C0009D19
0x1c0009d04  movzx   ecx, byte ptr [rdi+28h]
0x1c0009d08  test    cl, cl
0x1c0009d0a  jz      loc_1C0009F11
0x1c0009d10  cmp     cl, 0Dh
0x1c0009d13  jz      loc_1C0009F11
0x1c0009d19  mov     eax, [rdi+4]
0x1c0009d1c  bt      eax, 15h
0x1c0009d20  jb      loc_1C0009F9F
0x1c0009d26  mov     rdx, r13; Context2
0x1c0009d29  mov     rcx, rdi; Context1
0x1c0009d2c  test    byte ptr [rdi+29h], 4
0x1c0009d30  jnz     loc_1C0009FB6
0x1c0009d36  mov     eax, [r13+10h]
0x1c0009d3a  test    al, 2
0x1c0009d3c  jnz     loc_1C0009FBD
0x1c0009d42  call    RefsCommonWrite
0x1c0009d47  jmp     loc_1C0009FC2
0x1c0009d4c  inc     dword ptr [r14+18h]
0x1c0009d50  mov     edx, [r14+2Ch]
0x1c0009d54  mov     rax, [r14+30h]
0x1c0009d58  mov     r8d, [r14+28h]
0x1c0009d5c  mov     ecx, [r14+24h]
0x1c0009d60  call    cs:__guard_dispatch_icall_fptr
0x1c0009d66  mov     rcx, rax
0x1c0009d69  jmp     loc_1C0009B8B
0x1c0009d6e  test    r14b, r14b
0x1c0009d71  jz      loc_1C0009B2C
0x1c0009d77  lea     rax, [rbp+1E0h+Irp+38h]
0x1c0009d7b  mov     [rdi+90h], rax
0x1c0009d82  and     edx, 0FFFFFFEFh
0x1c0009d85  mov     [rdi+8], edx
0x1c0009d88  lea     rcx, [rbp+1E0h+Irp+38h]
0x1c0009d8c  jmp     loc_1C0009BB8
0x1c0009d91  mov     r14b, 1
0x1c0009d94  jmp     loc_1C0009AF5
0x1c0009d99  mov     eax, r9d
0x1c0009d9c  and     eax, 8010h
0x1c0009da1  cmp     eax, 8000h
0x1c0009da6  jnz     loc_1C0009B1A
0x1c0009dac  lea     rax, [rbp+1E0h+Irp+38h]
0x1c0009db0  cmp     r10, rax
0x1c0009db3  jz      loc_1C0009B1A
0x1c0009db9  mov     [rdi+90h], r15
0x1c0009dc0  btr     edx, 0Fh
0x1c0009dc4  mov     [rdi+8], edx
0x1c0009dc7  mov     rcx, r15
0x1c0009dca  jmp     loc_1C0009B1A
0x1c0009dcf  test    dl, 10h
0x1c0009dd2  jnz     loc_1C0009BBF
0x1c0009dd8  jmp     loc_1C0009B23
0x1c0009ddd  xor     edx, edx
0x1c0009ddf  div     ecx
0x1c0009de1  mov     eax, edx
0x1c0009de3  mov     [rbp+1E0h+var_1C0], edx
0x1c0009de6  jmp     loc_1C0009B5E
0x1c0009deb  mov     rax, [rdi+90h]
0x1c0009df2  or      dword ptr [rax], 2
0x1c0009df5  jmp     loc_1C0009BE6
0x1c0009dfa  mov     rcx, rdi
  ... truncated ...
```
