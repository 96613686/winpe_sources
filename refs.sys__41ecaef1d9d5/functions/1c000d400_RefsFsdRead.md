# RefsFsdRead

- ea: `0x1c000d400`
- end: `0x1c000dc46`
- name: `RefsFsdRead`
- size: `2118`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1c000d380`
- `0x1c000d400`
- `0x1c000dc50`
- `0x1c000dc80`
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
- `0x1c00b3dc8`
- `0x1c018f524`
- `0x1c01cd29c`
- `0x1c01d3c80`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1c000d712`
- `ntoskrnl!KeInitializeEvent` at `0x1c000d712`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000d4ec`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000d7bc`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000d7f7`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000d4ec`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000d7bc`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000d7f7`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c000d5ad`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c000d5ad`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c000d5d9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c000d5d9`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c000d5f3`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c000d5f3`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c007141f`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c007141f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c000db7b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c000db7b`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c000d549`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c000d560`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c000d549`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c000d560`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c000d68e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c000d68e`
- `ntoskrnl!CcCanIWrite` at `0x1c000d999`
- `ntoskrnl!CcCanIWrite` at `0x1c000d999`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1c000d90b`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1c000d90b`
- `ntoskrnl!IoWithinStackLimits` at `0x1c000d503`
- `ntoskrnl!IoWithinStackLimits` at `0x1c000d503`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c000d65f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c000d65f`

## string_xrefs

- `0x1c000d9f5`: `Read.c`
- `0x1c000da5d`: `Read.c`
- `0x1c00712cd`: `Read.c`
- `0x1c007133c`: `Read.c`
- `0x1c00713a8`: `Read.c`
- `0x1c00713e3`: `Read.c`

## pseudocode

```c
__int64 __fastcall RefsFsdRead(__int64 a1, IRP *a2)
{
  int v3; // r12d
  PFILE_OBJECT FileObject; // rax
  __int64 v5; // rcx
  _QWORD *FsContext; // rdx
  unsigned __int8 *FsContext2; // rax
  __int64 v8; // rax
  __int64 v9; // r13
  bool v10; // si
  bool v11; // di
  ULONG_PTR TopLevelIrp; // rbx
  BOOLEAN IsOperationSynchronous; // al
  NTSTATUS v14; // esi
  __int64 v15; // rax
  __int64 v16; // rdi
  int v17; // r12d
  int v18; // ebx
  unsigned int v19; // r9d
  struct _SLIST_ENTRY *v20; // r10
  PSLIST_ENTRY v21; // rcx
  unsigned int v22; // edx
  __int64 v23; // r13
  ULONG CurrentProcessorNumber; // eax
  struct _SLIST_ENTRY *v25; // r12
  unsigned __int64 v26; // rbx
  unsigned int v27; // edx
  __int64 v28; // rax
  __int64 v29; // rax
  _QWORD *v30; // rax
  __int64 v31; // rbx
  __int64 v32; // rax
  char v33; // cl
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rax
  unsigned int v37; // ecx
  void *v39; // rsp
  __int64 v40; // rax
  unsigned int v41; // ebx
  char v42; // [rsp+0h] [rbp-100h] BYREF
  char v43; // [rsp+100h] [rbp+0h]
  NTSTATUS Status; // [rsp+104h] [rbp+4h]
  char *v45; // [rsp+108h] [rbp+8h] BYREF
  ULONG v46; // [rsp+110h] [rbp+10h]
  int v47; // [rsp+114h] [rbp+14h]
  int v48; // [rsp+118h] [rbp+18h]
  int v49; // [rsp+11Ch] [rbp+1Ch]
  PSLIST_ENTRY v50; // [rsp+120h] [rbp+20h]
  _QWORD *v51; // [rsp+128h] [rbp+28h]
  __int64 v52; // [rsp+130h] [rbp+30h]
  __int64 v53; // [rsp+138h] [rbp+38h] BYREF
  _QWORD Irp[46]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v55; // [rsp+2B0h] [rbp+1B0h] BYREF

  Irp[5] = a2;
  memset(Irp, 0, 40);
  v45 = 0;
  v47 = 0;
  memset(&Irp[8], 0, 0x130u);
  v55 = 0;
  v53 = 0;
  v3 = 0;
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  v5 = 1;
  FsContext = FileObject->FsContext;
  v51 = FsContext;
  if ( FsContext )
  {
    FsContext2 = (unsigned __int8 *)FileObject->FsContext2;
    if ( !FsContext2 )
      goto LABEL_6;
    v5 = FsContext2[80];
  }
  if ( (((_DWORD)v5 - 2) & 0xFFFFFFFC) != 0 || (_DWORD)v5 == 3 )
    goto LABEL_96;
LABEL_6:
  v8 = FsContext[15];
  if ( *(_QWORD *)(v8 + 16) == 1312 && *(_QWORD *)(v8 + 8) == 1024 )
  {
LABEL_96:
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741808);
    RefsExtendedCompleteRequestInternal(0, a2, 3221225488LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids, 3221225488LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741808);
    return 3221225488LL;
  }
  Irp[6] = FsContext;
  v9 = MsCaptureTopLevelContext(v5);
  v52 = v9;
  v10 = 1;
  v11 = 0;
  TopLevelIrp = (ULONG_PTR)IoGetTopLevelIrp();
  if ( IoWithinStackLimits(TopLevelIrp, 0x28u) && (TopLevelIrp & 3) == 0 )
    v11 = *(_DWORD *)(TopLevelIrp + 4) == 1397140410;
  if ( !TopLevelIrp )
    goto LABEL_9;
  if ( TopLevelIrp <= 0xFFFF )
  {
    v10 = 0;
LABEL_9:
    Irp[3] = TopLevelIrp;
    Irp[4] = 0;
    LOBYTE(Irp[0]) = v10;
    if ( v11 )
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
    goto LABEL_12;
  }
  if ( !v11 || (v40 = *(_QWORD *)(TopLevelIrp + 32)) != 0 && (*(_DWORD *)(v40 + 4) & 0x200) != 0 )
  {
    v10 = TopLevelIrp != 2147483650;
    goto LABEL_9;
  }
LABEL_12:
  if ( IoIsOperationSynchronous(a2) && (a2->Flags & 2) != 0 )
  {
    v39 = alloca(256);
    v45 = &v42;
  }
  IsOperationSynchronous = IoIsOperationSynchronous(a2);
  v14 = RefsInitializeIrpContext(a2, IsOperationSynchronous, 0, &v45);
  Status = v14;
  if ( v14 < 0 )
  {
    MsRestoreTopLevelContext(v9);
    v41 = Status;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    RefsExtendedCompleteRequestInternal(0, a2, v41);
    return v41;
  }
  v15 = *(_QWORD *)(TopLevelIrp + 32);
  v16 = (__int64)v45;
  if ( !v15 )
  {
    *(_DWORD *)(TopLevelIrp + 4) = 1397140410;
    *(_QWORD *)(TopLevelIrp + 32) = v16;
    *(_DWORD *)(v16 + 8) |= 0x100000u;
    IoSetTopLevelIrp((PIRP)TopLevelIrp);
    v15 = *(_QWORD *)(TopLevelIrp + 32);
  }
  *(_QWORD *)(v16 + 104) = v15;
  *(_QWORD *)(v16 + 232) = v9;
  if ( *(_QWORD *)(*(_QWORD *)(v16 + 104) + 160LL) )
  {
    MsRestoreTopLevelContext(v9);
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073739768);
    RefsExtendedCompleteRequestInternal(v45, a2, 3221227528LL);
    return 3221227528LL;
  }
  KeEnterCriticalRegion();
  if ( (int)IoPropagateActivityIdToThread(a2, &v55, &v53) >= 0 )
    v3 = 1;
  v49 = v3;
  v17 = 53;
  while ( 1 )
  {
    v18 = a2->Flags & 2;
    v48 = v18;
    v19 = *(_DWORD *)(v16 + 8);
    v20 = *(struct _SLIST_ENTRY **)(v16 + 144);
    v21 = v20;
    v22 = v19;
    if ( v20 && (v19 & 0x8010) == 0x8000 && v20 != (struct _SLIST_ENTRY *)&Irp[8] )
    {
      *(_QWORD *)(v16 + 144) = 0;
      v22 = v19 & 0xFFFF7FFF;
      *(_DWORD *)(v16 + 8) = v19 & 0xFFFF7FFF;
      v21 = 0;
    }
    if ( !v21 || (v22 & 0x10) == 0 )
    {
      if ( (v19 & 1) != 0 && v18 )
      {
        *(_QWORD *)(v16 + 144) = &Irp[8];
        v27 = v22 & 0xFFFFFFEF;
        *(_DWORD *)(v16 + 8) = v27;
        v21 = (PSLIST_ENTRY)&Irp[8];
      }
      else
      {
        v23 = RefsIoContextLookasideList;
        v50 = 0;
        v46 = 0;
        CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
        v46 = CurrentProcessorNumber;
        if ( CurrentProcessorNumber >= RefsNumberProcessors )
        {
          CurrentProcessorNumber %= (unsigned int)RefsNumberProcessors;
          v46 = CurrentProcessorNumber;
        }
        v25 = (struct _SLIST_ENTRY *)CurrentProcessorNumber;
        v26 = v23 + ((unsigned __int64)CurrentProcessorNumber << 7);
        ++*(_DWORD *)(v26 + 20);
        v21 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v26);
        if ( !v21 )
        {
          ++*(_DWORD *)(v26 + 24);
          v21 = (PSLIST_ENTRY)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v26 + 48))(
                                *(unsigned int *)(v26 + 36),
                                *(unsigned int *)(v26 + 44),
                                *(unsigned int *)(v26 + 40));
        }
        v50 = v21;
        if ( v21 )
        {
          v21->Next = v25;
          v21 = (PSLIST_ENTRY)((char *)v21 + 8);
          v50 = v21;
        }
        *(_QWORD *)(v16 + 144) = v21;
        *(_DWORD *)(v16 + 8) |= 0x10u;
        v27 = *(_DWORD *)(v16 + 8);
        v18 = v48;
        v9 = v52;
        v17 = 53;
      }
      *(_DWORD *)(v16 + 8) = v27 | 0x8000;
    }
    memset(v21, 0, 0x130u);
    if ( (*(_DWORD *)(v16 + 8) & 0x10) != 0 )
      **(_DWORD **)(v16 + 144) |= 1u;
    if ( v18 )
      **(_DWORD **)(v16 + 144) |= 2u;
    KeInitializeEvent((PRKEVENT)(*(_QWORD *)(v16 + 144) + 8LL), NotificationEvent, 0);
    v28 = *(_QWORD *)(v16 + 144);
    *(_QWORD *)(v28 + 152) = 0;
    *(_QWORD *)(v28 + 160) = 0;
    *(_DWORD *)(v28 + 156) = 1;
    v29 = *(_QWORD *)(v16 + 144);
    *(_OWORD *)(v29 + 216) = 0;
    *(_OWORD *)(v29 + 232) = 0;
    *(_OWORD *)(v29 + 248) = 0;
    *(_OWORD *)(v29 + 264) = 0;
    *(_QWORD *)(v29 + 280) = 0;
    v30 = (_QWORD *)(*(_QWORD *)(v16 + 144) + 224LL);
    v30[1] = v30;
    *v30 = v30;
    *(_DWORD *)(*(_QWORD *)(v16 + 144) + 244LL) = 1;
    *(_DWORD *)(*(_QWORD *)(v16 + 144) + 216LL) = 72;
    if ( v14 == -1073741432 )
      RefsCheckpointForLogFileFull(v16);
    v31 = *(_QWORD *)(v16 + 72);
    if ( v16 == *(_QWORD *)(v16 + 104) )
    {
      if ( LOBYTE(IoGetTopLevelIrp()->Type) )
      {
        v32 = *(_QWORD *)(v16 + 64);
        if ( v32 )
        {
          if ( v31 && *(_QWORD *)(v32 + 104) && (unsigned __int8)MsVolumeHasReadCache() )
            IoClearFsTrackOffsetState(v31);
        }
      }
      if ( v16 == *(_QWORD *)(v16 + 104) )
      {
        if ( LOBYTE(IoGetTopLevelIrp()->Type) )
        {
          v33 = *(_BYTE *)(v16 + 40);
          if ( !v33 || v33 == 13 )
          {
            v35 = *(_QWORD *)(v16 + 64);
            if ( v35 )
            {
              if ( (*(_DWORD *)(v35 + 4) & 1) != 0 )
              {
                v43 = 0;
                v36 = *(_QWORD *)(v31 + 184);
                if ( v33 )
                {
                  if ( *(_DWORD *)(v36 + 24) != 589988 )
                    goto LABEL_48;
LABEL_68:
                  v43 = 1;
                  CcCanIWrite(0, 0x80000u, 1u, 0);
                  goto LABEL_48;
                }
                v37 = *(unsigned __int8 *)(v36 + 19);
                if ( (*(_DWORD *)(v36 + 16) & 1) != 0
                  && (*(_DWORD *)(v16 + 8) & 8) == 0
                  && (unsigned __int8)v37 <= 5u
                  && _bittest(&v17, v37) )
                {
                  goto LABEL_68;
                }
              }
            }
          }
        }
      }
    }
LABEL_48:
    v34 = *(_DWORD *)(v16 + 4);
    if ( (v34 & 0x200000) != 0 )
    {
      *(_DWORD *)(v16 + 4) = v34 & 0xFFDFFFFF;
      RefsPerformVerify(v16, v31);
    }
    *(_QWORD *)(v16 + 232) = v9;
    if ( (*(_BYTE *)(v16 + 41) & 4) == 0 )
    {
      v14 = RefsCommonRead(v16, a2);
      Status = v14;
      goto LABEL_79;
    }
    v14 = RefsCompleteMdl(v16, a2);
    Status = v14;
    if ( (v51[38] & 0x1000000) != 0 )
      break;
LABEL_79:
    ++v47;
    if ( v14 != -1073741608 && v14 != -1073741400 && v14 != -1073741432 )
      goto LABEL_82;
  }
  v14 = -1073741816;
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741816);
  RefsExtendedCompleteRequestInternal(v45, a2, 3221225480LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids, 3221225480LL);
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741816);
  Status = -1073741816;
LABEL_82:
  if ( v49 )
    IoClearActivityIdThread(v53);
  KeLeaveCriticalRegion();
  MsRestoreTopLevelContext(v9);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1c000d400  push    rbp
0x1c000d402  push    r12
0x1c000d404  push    r13
0x1c000d406  push    r14
0x1c000d408  push    r15
0x1c000d40a  sub     rsp, 1F0h
0x1c000d411  lea     rbp, [rsp+20h]
0x1c000d416  mov     [rbp+1F0h+arg_0], rbx
0x1c000d41d  mov     [rbp+1F0h+arg_10], rsi
0x1c000d424  mov     [rbp+1F0h+arg_18], rdi
0x1c000d42b  mov     rax, cs:__security_cookie
0x1c000d432  xor     rax, rbp
0x1c000d435  mov     [rbp+1F0h+var_30], rax
0x1c000d43c  mov     r14, rdx
0x1c000d43f  mov     qword ptr [rbp+1F0h+Irp+28h], rdx
0x1c000d443  xorps   xmm0, xmm0
0x1c000d446  xor     eax, eax
0x1c000d448  movups  xmmword ptr [rbp+1F0h+Irp], xmm0
0x1c000d44c  movups  xmmword ptr [rbp+1F0h+Irp+10h], xmm0
0x1c000d450  mov     qword ptr [rbp+1F0h+Irp+20h], rax
0x1c000d454  xor     r15d, r15d
0x1c000d457  mov     [rbp+1F0h+var_1E8], r15
0x1c000d45b  mov     [rbp+1F0h+var_1DC], r15d
0x1c000d45f  xor     edx, edx; Val
0x1c000d461  mov     r8d, 130h; Size
0x1c000d467  lea     rcx, [rbp+1F0h+Irp+40h]; void *
0x1c000d46e  call    memset
0x1c000d473  xorps   xmm0, xmm0
0x1c000d476  movups  [rbp+1F0h+var_40], xmm0
0x1c000d47d  mov     [rbp+1F0h+var_1B8], r15
0x1c000d481  mov     r12d, r15d
0x1c000d484  mov     rax, [r14+0B8h]
0x1c000d48b  mov     rax, [rax+30h]
0x1c000d48f  lea     ecx, [r15+1]
0x1c000d493  mov     rdx, [rax+18h]
0x1c000d497  mov     [rbp+1F0h+var_1C8], rdx
0x1c000d49b  test    rdx, rdx
0x1c000d49e  jz      short loc_1C000D4AD
0x1c000d4a0  mov     rax, [rax+20h]
0x1c000d4a4  test    rax, rax
0x1c000d4a7  jz      short loc_1C000D4C4
0x1c000d4a9  movzx   ecx, byte ptr [rax+50h]
0x1c000d4ad  lea     eax, [rcx-2]
0x1c000d4b0  test    eax, 0FFFFFFFCh
0x1c000d4b5  jnz     loc_1C00712BC
0x1c000d4bb  cmp     ecx, 3
0x1c000d4be  jz      loc_1C00712BC
0x1c000d4c4  mov     rax, [rdx+78h]
0x1c000d4c8  cmp     qword ptr [rax+10h], 520h
0x1c000d4d0  jz      loc_1C00712AE
0x1c000d4d6  mov     qword ptr [rbp+1F0h+Irp+30h], rdx
0x1c000d4da  call    MsCaptureTopLevelContext
0x1c000d4df  mov     r13, rax
0x1c000d4e2  mov     [rbp+1F0h+var_1C0], rax
0x1c000d4e6  mov     sil, 1
0x1c000d4e9  xor     dil, dil
0x1c000d4ec  call    cs:__imp_IoGetTopLevelIrp
0x1c000d4f3  nop     dword ptr [rax+rax+00h]
0x1c000d4f8  mov     rbx, rax
0x1c000d4fb  mov     edx, 28h ; '('; RegionSize
0x1c000d500  mov     rcx, rax; RegionStart
0x1c000d503  call    cs:__imp_IoWithinStackLimits
0x1c000d50a  nop     dword ptr [rax+rax+00h]
0x1c000d50f  test    eax, eax
0x1c000d511  jnz     loc_1C000DBEE
0x1c000d517  test    rbx, rbx
0x1c000d51a  jnz     loc_1C000DC0D
0x1c000d520  mov     qword ptr [rbp+1F0h+Irp+18h], rbx
0x1c000d524  mov     qword ptr [rbp+1F0h+Irp+20h], r15
0x1c000d528  mov     [rbp+1F0h+Irp], sil
0x1c000d52c  test    dil, dil
0x1c000d52f  jnz     loc_1C007136C
0x1c000d535  xorps   xmm0, xmm0
0x1c000d538  movdqu  xmmword ptr [rbp+1F0h+Irp+8], xmm0
0x1c000d53d  mov     word ptr [rbp+1F0h+Irp+1], r12w
0x1c000d542  lea     rbx, [rbp+1F0h+Irp]
0x1c000d546  mov     rcx, r14; Irp
0x1c000d549  call    cs:__imp_IoIsOperationSynchronous
0x1c000d550  nop     dword ptr [rax+rax+00h]
0x1c000d555  test    al, al
0x1c000d557  jnz     loc_1C000DBC7
0x1c000d55d  mov     rcx, r14; Irp
0x1c000d560  call    cs:__imp_IoIsOperationSynchronous
0x1c000d567  nop     dword ptr [rax+rax+00h]
0x1c000d56c  movzx   edx, al
0x1c000d56f  lea     r9, [rbp+1F0h+var_1E8]
0x1c000d573  xor     r8d, r8d
0x1c000d576  mov     rcx, r14
0x1c000d579  call    RefsInitializeIrpContext
0x1c000d57e  mov     esi, eax
0x1c000d580  mov     [rbp+1F0h+Status], eax
0x1c000d583  test    eax, eax
0x1c000d585  js      loc_1C007138C
0x1c000d58b  mov     rax, [rbx+20h]
0x1c000d58f  mov     rdi, [rbp+1F0h+var_1E8]
0x1c000d593  test    rax, rax
0x1c000d596  jnz     short loc_1C000D5BD
0x1c000d598  mov     dword ptr [rbx+4], 5346ABBAh
0x1c000d59f  mov     [rbx+20h], rdi
0x1c000d5a3  or      dword ptr [rdi+8], 100000h
0x1c000d5aa  mov     rcx, rbx; Irp
0x1c000d5ad  call    cs:__imp_IoSetTopLevelIrp
0x1c000d5b4  nop     dword ptr [rax+rax+00h]
0x1c000d5b9  mov     rax, [rbx+20h]
0x1c000d5bd  mov     [rdi+68h], rax
0x1c000d5c1  mov     [rdi+0E8h], r13
0x1c000d5c8  mov     rax, [rdi+68h]
0x1c000d5cc  cmp     [rax+0A0h], r12
0x1c000d5d3  jnz     loc_1C00713CA
0x1c000d5d9  call    cs:__imp_KeEnterCriticalRegion
0x1c000d5e0  nop     dword ptr [rax+rax+00h]
0x1c000d5e5  lea     r8, [rbp+1F0h+var_1B8]
0x1c000d5e9  lea     rdx, [rbp+1F0h+var_40]
0x1c000d5f0  mov     rcx, r14
0x1c000d5f3  call    cs:__imp_IoPropagateActivityIdToThread
0x1c000d5fa  nop     dword ptr [rax+rax+00h]
0x1c000d5ff  test    eax, eax
0x1c000d601  jns     loc_1C0071410
0x1c000d607  mov     [rbp+1F0h+var_1D4], r12d
0x1c000d60b  mov     r12d, 35h ; '5'
0x1c000d611  mov     ebx, [r14+10h]
0x1c000d615  and     ebx, 2
0x1c000d618  mov     [rbp+1F0h+var_1D8], ebx
0x1c000d61b  mov     r9d, [rdi+8]
0x1c000d61f  mov     r8d, r9d
0x1c000d622  and     r8d, 1
0x1c000d626  mov     r10, [rdi+90h]
0x1c000d62d  mov     rcx, r10
0x1c000d630  mov     edx, r9d
0x1c000d633  test    r10, r10
0x1c000d636  jnz     loc_1C000D8A6
0x1c000d63c  test    rcx, rcx
0x1c000d63f  jnz     loc_1C000D8DF
0x1c000d645  test    r8d, r8d
0x1c000d648  jnz     loc_1C000D87E
0x1c000d64e  mov     r13, cs:RefsIoContextLookasideList
0x1c000d655  mov     [rbp+1F0h+var_1D0], r15
0x1c000d659  mov     [rbp+1F0h+var_1E0], r15d
0x1c000d65d  xor     ecx, ecx; ProcNumber
0x1c000d65f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1c000d666  nop     dword ptr [rax+rax+00h]
0x1c000d66b  mov     [rbp+1F0h+var_1E0], eax
0x1c000d66e  mov     ecx, cs:RefsNumberProcessors
0x1c000d674  cmp     eax, ecx
0x1c000d676  jnb     loc_1C000D8ED
0x1c000d67c  mov     r12d, eax
0x1c000d67f  mov     ebx, eax
0x1c000d681  shl     rbx, 7
0x1c000d685  add     rbx, r13
0x1c000d688  inc     dword ptr [rbx+14h]
0x1c000d68b  mov     rcx, rbx; ListHead
0x1c000d68e  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c000d695  nop     dword ptr [rax+rax+00h]
0x1c000d69a  mov     rcx, rax
0x1c000d69d  test    rax, rax
0x1c000d6a0  jz      loc_1C000D850
0x1c000d6a6  mov     [rbp+1F0h+var_1D0], rcx
0x1c000d6aa  test    rcx, rcx
0x1c000d6ad  jz      short loc_1C000D6BA
0x1c000d6af  mov     [rcx], r12
0x1c000d6b2  add     rcx, 8; void *
0x1c000d6b6  mov     [rbp+1F0h+var_1D0], rcx
0x1c000d6ba  mov     [rdi+90h], rcx
0x1c000d6c1  or      dword ptr [rdi+8], 10h
0x1c000d6c5  mov     edx, [rdi+8]
0x1c000d6c8  mov     ebx, [rbp+1F0h+var_1D8]
0x1c000d6cb  mov     r13, [rbp+1F0h+var_1C0]
0x1c000d6cf  mov     r12d, 35h ; '5'
0x1c000d6d5  bts     edx, 0Fh
0x1c000d6d9  mov     [rdi+8], edx
0x1c000d6dc  xor     edx, edx; Val
0x1c000d6de  mov     r8d, 130h; Size
0x1c000d6e4  call    memset
0x1c000d6e9  mov     eax, [rdi+8]
0x1c000d6ec  test    al, 10h
0x1c000d6ee  jz      short loc_1C000D6FA
0x1c000d6f0  mov     rax, [rdi+90h]
0x1c000d6f7  or      dword ptr [rax], 1
0x1c000d6fa  test    ebx, ebx
0x1c000d6fc  jnz     loc_1C000D86F
0x1c000d702  mov     rcx, [rdi+90h]
0x1c000d709  add     rcx, 8; Event
0x1c000d70d  xor     r8d, r8d; State
0x1c000d710  xor     edx, edx; Type
0x1c000d712  call    cs:__imp_KeInitializeEvent
0x1c000d719  nop     dword ptr [rax+rax+00h]
0x1c000d71e  mov     rax, [rdi+90h]
0x1c000d725  mov     qword ptr [rax+98h], 0
0x1c000d730  mov     [rax+0A0h], r15
0x1c000d737  mov     dword ptr [rax+9Ch], 1
0x1c000d741  mov     rax, [rdi+90h]
0x1c000d748  xorps   xmm0, xmm0
0x1c000d74b  xor     ecx, ecx
0x1c000d74d  movups  xmmword ptr [rax+0D8h], xmm0
0x1c000d754  movups  xmmword ptr [rax+0E8h], xmm0
0x1c000d75b  movups  xmmword ptr [rax+0F8h], xmm0
0x1c000d762  movups  xmmword ptr [rax+108h], xmm0
0x1c000d769  mov     [rax+118h], rcx
0x1c000d770  mov     rax, [rdi+90h]
0x1c000d777  add     rax, 0E0h
0x1c000d77d  mov     [rax+8], rax
0x1c000d781  mov     [rax], rax
0x1c000d784  mov     rax, [rdi+90h]
0x1c000d78b  mov     dword ptr [rax+0F4h], 1
0x1c000d795  mov     rax, [rdi+90h]
0x1c000d79c  mov     dword ptr [rax+0D8h], 48h ; 'H'
0x1c000d7a6  cmp     esi, 0C0000188h
0x1c000d7ac  jz      loc_1C000D8FB
0x1c000d7b2  mov     rbx, [rdi+48h]
0x1c000d7b6  cmp     rdi, [rdi+68h]
0x1c000d7ba  jnz     short loc_1C000D81D
0x1c000d7bc  call    cs:__imp_IoGetTopLevelIrp
0x1c000d7c3  nop     dword ptr [rax+rax+00h]
0x1c000d7c8  cmp     byte ptr [rax], 0
0x1c000d7cb  jz      short loc_1C000D7F1
0x1c000d7cd  mov     rax, [rdi+40h]
0x1c000d7d1  test    rax, rax
0x1c000d7d4  jz      short loc_1C000D7F1
0x1c000d7d6  test    rbx, rbx
0x1c000d7d9  jz      short loc_1C000D7F1
0x1c000d7db  mov     rcx, [rax+68h]
0x1c000d7df  test    rcx, rcx
0x1c000d7e2  jz      short loc_1C000D7F1
0x1c000d7e4  call    MsVolumeHasReadCache
0x1c000d7e9  test    al, al
0x1c000d7eb  jnz     loc_1C000D908
0x1c000d7f1  cmp     rdi, [rdi+68h]
0x1c000d7f5  jnz     short loc_1C000D81D
0x1c000d7f7  call    cs:__imp_IoGetTopLevelIrp
0x1c000d7fe  nop     dword ptr [rax+rax+00h]
0x1c000d803  cmp     byte ptr [rax], 0
0x1c000d806  jz      short loc_1C000D81D
0x1c000d808  movzx   ecx, byte ptr [rdi+28h]
0x1c000d80c  test    cl, cl
0x1c000d80e  jz      loc_1C000D91C
0x1c000d814  cmp     cl, 0Dh
0x1c000d817  jz      loc_1C000D91C
0x1c000d81d  mov     eax, [rdi+4]
0x1c000d820  bt      eax, 15h
0x1c000d824  jb      loc_1C000D9AA
0x1c000d82a  mov     [rdi+0E8h], r13
0x1c000d831  mov     rdx, r14
0x1c000d834  mov     rcx, rdi
0x1c000d837  test    byte ptr [rdi+29h], 4
0x1c000d83b  jnz     loc_1C000D9C1
0x1c000d841  call    RefsCommonRead
0x1c000d846  mov     esi, eax
0x1c000d848  mov     [rbp+1F0h+Status], eax
0x1c000d84b  jmp     loc_1C000DA73
0x1c000d850  inc     dword ptr [rbx+18h]
0x1c000d853  mov     edx, [rbx+2Ch]
0x1c000d856  mov     rax, [rbx+30h]
0x1c000d85a  mov     r8d, [rbx+28h]
0x1c000d85e  mov     ecx, [rbx+24h]
0x1c000d861  call    cs:__guard_dispatch_icall_fptr
0x1c000d867  mov     rcx, rax
0x1c000d86a  jmp     loc_1C000D6A6
0x1c000d86f  mov     rax, [rdi+90h]
0x1c000d876  or      dword ptr [rax], 2
0x1c000d879  jmp     loc_1C000D702
0x1c000d87e  test    ebx, ebx
0x1c000d880  jz      loc_1C000D64E
0x1c000d886  lea     rax, [rbp+1F0h+Irp+40h]
0x1c000d88d  mov     [rdi+90h], rax
0x1c000d894  and     edx, 0FFFFFFEFh
0x1c000d897  mov     [rdi+8], edx
0x1c000d89a  lea     rcx, [rbp+1F0h+Irp+40h]
0x1c000d8a1  jmp     loc_1C000D6D5
0x1c000d8a6  mov     eax, r9d
0x1c000d8a9  and     eax, 8010h
0x1c000d8ae  cmp     eax, 8000h
0x1c000d8b3  jnz     loc_1C000D63C
0x1c000d8b9  lea     rax, [rbp+1F0h+Irp+40h]
0x1c000d8c0  cmp     r10, rax
0x1c000d8c3  jz      loc_1C000D63C
0x1c000d8c9  mov     [rdi+90h], r15
0x1c000d8d0  btr     edx, 0Fh
0x1c000d8d4  mov     [rdi+8], edx
0x1c000d8d7  mov     rcx, r15
0x1c000d8da  jmp     loc_1C000D63C
0x1c000d8df  test    dl, 10h
0x1c000d8e2  jnz     loc_1C000D6DC
0x1c000d8e8  jmp     loc_1C000D645
0x1c000d8ed  xor     edx, edx
0x1c000d8ef  div     ecx
0x1c000d8f1  mov     eax, edx
0x1c000d8f3  mov     [rbp+1F0h+var_1E0], edx
0x1c000d8f6  jmp     loc_1C000D67C
0x1c000d8fb  mov     rcx, rdi
0x1c000d8fe  call    RefsCheckpointForLogFileFull
0x1c000d903  jmp     loc_1C000D7B2
0x1c000d908  mov     rcx, rbx
0x1c000d90b  call    cs:__imp_IoClearFsTrackOffsetState
0x1c000d912  nop     dword ptr [rax+rax+00h]
0x1c000d917  jmp     loc_1C000D7F1
0x1c000d91c  mov     rax, [rdi+40h]
0x1c000d920  test    rax, rax
0x1c000d923  jz      loc_1C000D81D
0x1c000d929  mov     eax, [rax+4]
0x1c000d92c  test    al, 1
  ... truncated ...
```
