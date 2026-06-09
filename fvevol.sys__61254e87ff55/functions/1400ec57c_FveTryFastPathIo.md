# FveTryFastPathIo

- ea: `0x1400ec57c`
- end: `0x1400eccda`
- name: `FveTryFastPathIo`
- size: `1886`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400ebc00`

## callees

- `0x1400089c4`
- `0x140009cb4`
- `0x14000b998`
- `0x140023040`
- `0x14002a2a0`
- `0x14002d140`
- `0x1400bbaf0`
- `0x1400bd8e0`
- `0x1400e07fc`
- `0x1400e228c`
- `0x1400ec57c`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400eccc9`
- `ntoskrnl!IofCallDriver` at `0x1400eccc9`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400eca86`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400eca86`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400ec917`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400eca99`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400ec917`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400eca99`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400ec998`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400ec998`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400ec6b1`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400ec6b1`
- `ntoskrnl!MmSizeOfMdl` at `0x1400ec9b9`
- `ntoskrnl!MmSizeOfMdl` at `0x1400ec9b9`
- `ntoskrnl!MmAreMdlPagesCached` at `0x1400ec8dc`
- `ntoskrnl!MmAreMdlPagesCached` at `0x1400ec8dc`
- `ntoskrnl!KeBugCheckEx` at `0x1400ecc40`
- `ntoskrnl!KeBugCheckEx` at `0x1400ecc40`
- `ntoskrnl!ExAllocatePool2` at `0x1400ec9d6`
- `ntoskrnl!ExAllocatePool2` at `0x1400ec9d6`

## pseudocode

```c
char __fastcall FveTryFastPathIo(__int64 a1, IRP *a2, char a3, unsigned __int64 a4, unsigned int Length)
{
  __int64 v5; // r12
  struct _LIST_ENTRY *Flink; // rbx
  __int64 v11; // r9
  char v12; // si
  bool v13; // r14
  unsigned int Flink_low_high; // ecx
  _QWORD *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned __int64 v21; // rdx
  int v22; // eax
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  unsigned __int64 v29; // r8
  __int64 v30; // rax
  unsigned __int64 v31; // r8
  __int64 v32; // rcx
  unsigned __int64 v33; // rdx
  __int64 v34; // rax
  unsigned int v36; // edx
  int v37; // eax
  __int64 v38; // rdx
  __int64 ByteOffset; // r8
  __int64 v40; // r9
  char *v41; // r15
  unsigned int v42; // ecx
  bool v43; // zf
  __int64 v44; // rcx
  char *Pool2; // rax
  __int64 v46; // r15
  int v47; // eax
  unsigned __int64 v48; // r13
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  __int64 v50; // rdx
  char v51; // dl
  int v52; // eax
  __int64 v53; // rdx
  __int64 v54; // rdx
  ULONG v55; // eax
  struct _IO_STACK_LOCATION *v56; // rdx
  DWORD LowPart; // edx
  struct _IO_STACK_LOCATION *v58; // rax
  __int64 (__fastcall *v59)(); // rax
  struct _IO_STACK_LOCATION *v60; // rcx
  int LockArray_high; // [rsp+30h] [rbp-48h]
  unsigned int v62; // [rsp+34h] [rbp-44h]
  PMDL MemoryDescriptorList; // [rsp+38h] [rbp-40h]
  char v64; // [rsp+80h] [rbp+8h]
  struct _LIST_ENTRY *v65; // [rsp+80h] [rbp+8h]
  struct _LIST_ENTRY *v66; // [rsp+80h] [rbp+8h]
  unsigned int v67; // [rsp+88h] [rbp+10h]

  v5 = *(_QWORD *)(a1 + 8);
  Flink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  v12 = 1;
  v13 = (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline()
     && *(_QWORD *)(a1 + 5144)
     && *(_DWORD *)(a1 + 836) == 3
     && (*(_DWORD *)(a1 + 808) & 1) != 0;
  if ( *(_BYTE *)(a1 + 1477) )
    Flink_low_high = (unsigned __int8)HIBYTE(LODWORD(a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink));
  else
    Flink_low_high = GetPriorityFromIrpEx(a1, a2, 8, v11);
  v67 = Flink_low_high;
  if ( *(_DWORD *)(a1 + 840) )
    return 0;
  if ( *(_QWORD *)(a1 + 4752) )
    return 0;
  if ( v13 )
    return 0;
  if ( !*(_QWORD *)(v5 + 664) )
    return 0;
  if ( (*(_DWORD *)(a1 + 808) & 0x100) != 0 )
  {
    v15 = *(_QWORD **)(a1 + 736);
    if ( v15 )
    {
      if ( *v15 )
        return 0;
    }
  }
  v16 = *(unsigned int *)(v5 + 884);
  if ( *(_DWORD *)(v5 + 4 * v16 + 1372) != -1
    || *(_DWORD *)(v5 + 4 * v16 + 1384) != -1
    || !*(_DWORD *)(v5 + 4 * v16 + 1128)
    || Flink_low_high - 8 > 6
    || (a2->Flags & 0x42) != 0
    || IoGetIoPriorityHint(a2) != IoPriorityNormal )
  {
    return 0;
  }
  if ( *(_QWORD *)(a1 + 976) )
  {
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v18, v17)
      && (*(_BYTE *)(a1 + 4419) & 8) != 0
      || (v19 = *(_QWORD *)(a1 + 976), *(_WORD *)(v19 + 10) == 1) )
    {
      v20 = 0;
    }
    else
    {
      v20 = *(unsigned int *)(v19 + 28);
      if ( !(_DWORD)v20 )
        v20 = 1;
    }
    v18 = v20 * *(unsigned int *)(a1 + 1308);
    if ( a4 < v18 )
    {
      v18 = a4 + Length;
      if ( v18 )
        return 0;
    }
  }
  v21 = *(_QWORD *)(a1 + 976);
  if ( v21 )
  {
    v22 = *(_DWORD *)(a1 + 808);
    if ( (v22 & 0x17F) != 0 && (v22 & 0x40) == 0 )
    {
      v23 = *(_QWORD *)(a1 + 1056);
      if ( a4 < v23 + *(unsigned int *)(a1 + 1064) )
      {
        v18 = a4 + Length;
        if ( v18 > v23 )
          return 0;
      }
      v24 = *(_QWORD *)(a1 + 1080);
      if ( a4 < v24 + *(unsigned int *)(a1 + 1088) )
      {
        v18 = a4 + Length;
        if ( v18 > v24 )
          return 0;
      }
      v21 = *(_QWORD *)(a1 + 1104);
      if ( a4 < v21 + *(unsigned int *)(a1 + 1112) )
      {
        v18 = a4 + Length;
        if ( v18 > v21 )
          return 0;
      }
    }
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v18, v21) )
    {
      if ( (*(_BYTE *)(a1 + 4419) & 8) != 0 || (v25 = *(_QWORD *)(a1 + 976), *(_WORD *)(v25 + 10) == 1) )
      {
        v26 = 0;
      }
      else
      {
        v26 = *(unsigned int *)(v25 + 28);
        if ( !(_DWORD)v26 )
          v26 = 1;
      }
      v27 = *(_QWORD *)(a1 + 976);
      v28 = v27;
    }
    else
    {
      v28 = *(_QWORD *)(a1 + 976);
      if ( *(_WORD *)(v28 + 10) == 1 )
      {
        v26 = 0;
      }
      else
      {
        v26 = *(unsigned int *)(v28 + 28);
        if ( !(_DWORD)v26 )
          v26 = 1;
      }
      v27 = *(_QWORD *)(a1 + 976);
    }
    v29 = *(_QWORD *)(v27 + 56);
    if ( a4 < v29 + v26 * *(unsigned int *)(a1 + 1308) && a4 + Length > v29 )
      return 0;
    if ( v28 )
    {
      if ( *(_WORD *)(v28 + 12) == 2 )
      {
        v30 = *(unsigned int *)(v28 + 24);
        if ( (_DWORD)v30 )
        {
          v31 = *(_QWORD *)(v28 + 16);
          if ( a4 < v31 + v30 && a4 + Length > v31 )
            return 0;
        }
      }
    }
  }
  if ( *(_DWORD *)(a1 + 1492) )
  {
    v32 = *(_QWORD *)(*(_QWORD *)(a1 + 1392) + 304LL);
    v33 = *(_QWORD *)(v32 + 96);
    if ( a4 < v33 + *(unsigned int *)(v32 + 92) && a4 + Length > v33 )
      return 0;
  }
  v34 = *(unsigned int *)(v5 + 884);
  if ( a3 )
  {
    if ( Length > *(_DWORD *)(a1 + 4 * v34 + 1868) )
      return 0;
  }
  else if ( Length > *(_DWORD *)(a1 + 4 * v34 + 1856) )
  {
    return 0;
  }
  v36 = 33 * *(_DWORD *)(a1 + 4 * v34 + 1604);
  if ( v36 <= *(_DWORD *)(a1 + 4 * v34 + 1592) )
    v36 = *(_DWORD *)(a1 + 4 * v34 + 1592);
  if ( Length > v36 || *(_QWORD *)(a1 + 4584) != a1 + 4584 )
    return 0;
  v37 = MmAreMdlPagesCached(a2->MdlAddress);
  if ( a3
    || *(_DWORD *)(a1 + 4LL * *(unsigned int *)(v5 + 884) + 1700)
    || !v37
    || (v41 = 0, MemoryDescriptorList = 0, !(unsigned int)MmMdlPageContentsState(a2->MdlAddress, 2))
    && ((v42 = *(_DWORD *)(a1 + 1308), ByteOffset = a2->MdlAddress->ByteOffset, ((v42 - 1) & v42) != 0) || !v42
      ? (v38 = (unsigned int)ByteOffset % v42, v43 = (unsigned int)ByteOffset % v42 == 0)
      : (v43 = ((unsigned int)ByteOffset & (v42 - 1)) == 0),
        !v43) )
  {
    LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
    if ( Length > *(_DWORD *)(a1 + 4LL * *(unsigned int *)(v5 + 884) + 1592) )
    {
      v64 = 2;
      v46 = Length;
      v47 = MmSizeOfMdl(0, Length);
      Pool2 = (char *)ExAllocatePool2(74, v47 + Length + 64, 1883592262);
    }
    else
    {
      v44 = *(_QWORD *)(a1 + 2024);
      v64 = 1;
      if ( v44 )
        Pool2 = (char *)PplAllocateFromLookasideList(v44, v38, ByteOffset, v40);
      else
        Pool2 = (char *)ExAllocateFromNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 2016));
      v46 = Length;
    }
    v48 = (unsigned __int64)Pool2;
    if ( !Pool2 )
      return 0;
    v41 = &Pool2[v46];
    MemoryDescriptorList = (PMDL)(v41 + 64);
    memset(v41, 0, 0x40u);
    *((_DWORD *)v41 + 10) = (unsigned __int8)BYTE1(LODWORD(a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink));
    v41[44] = v64;
    *((_QWORD *)v41 + 7) = a2->MdlAddress;
    *((_DWORD *)v41 + 12) = LockArray_high;
    *((_QWORD *)v41 + 8) = 0;
    *((_QWORD *)v41 + 12) = v48 & 0xFFFFFFFFFFFFF000uLL;
    *((_WORD *)v41 + 37) = 0;
    *((_WORD *)v41 + 36) = 8 * ((((v48 & 0xFFF) + Length + 4095LL) >> 12) + 6);
    *((_DWORD *)v41 + 27) = v48 & 0xFFF;
    *((_DWORD *)v41 + 26) = Length;
    MmBuildMdlForNonPagedPool((PMDL)(v41 + 64));
    MmMdlPageContentsState(v41 + 64, 1);
  }
  LOBYTE(ByteOffset) = a3;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v65 = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  FvePerfReportIoSplitSize(a1, Length, ByteOffset);
  LOBYTE(v50) = a3;
  FvePerfReportSubRequest(a1, v50);
  v52 = *(_DWORD *)(a1 + 2344);
  if ( !v51 )
  {
    if ( v52 == 1 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 2352) + 288LL));
      goto LABEL_97;
    }
    v54 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
    ++*(_DWORD *)(v54 + *(_QWORD *)(a1 + 2352) + 288);
LABEL_96:
    v51 = a3;
    goto LABEL_97;
  }
  if ( v52 != 1 )
  {
    v53 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
    ++*(_DWORD *)(v53 + *(_QWORD *)(a1 + 2352) + 292);
    goto LABEL_96;
  }
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 2352) + 292LL));
LABEL_97:
  v55 = MEMORY[0xFFFFF78000000008];
  v62 = MEMORY[0xFFFFF7800000000C];
  if ( v41 )
    *(_QWORD *)v41 = MEMORY[0xFFFFF78000000008];
  if ( v51 )
  {
    v66 = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
    BYTE2(v66) = 1;
    a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = v66;
    a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = (struct _LIST_ENTRY *)v41;
    if ( (unsigned __int8)Flink >= 2u || Length > *(_DWORD *)(a1 + 4LL * *(unsigned int *)(v5 + 884) + 1880) )
      FveQueueIoWork(a1, a2, v67);
    else
      FastWriteEncrypt(a1, a2, v41);
  }
  else
  {
    if ( MemoryDescriptorList )
      a2->MdlAddress = MemoryDescriptorList;
    v56 = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v56[-1].MajorFunction = *(_OWORD *)&v56->MajorFunction;
    *(_OWORD *)&v56[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v56->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v56[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v56->Parameters.SetQuota + 6);
    v56[-1].FileObject = v56->FileObject;
    v56[-1].Control = 0;
    if ( *(_BYTE *)(a1 + 1477) )
    {
      LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
      if ( (LowPart & 0xF) != 0 )
        KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
      CurrentStackLocation->Parameters.Read.ByteOffset.LowPart = LowPart + v67;
    }
    if ( v41 )
    {
      v58 = a2->Tail.Overlay.CurrentStackLocation;
      v58[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)FastReadCompletionRoutineControl;
      v58[-1].Context = v41;
      v58[-1].Control = -32;
    }
    else
    {
      CurrentStackLocation->Parameters.Create.Options = v55;
      v59 = FastReadCompletionRoutineRdpLevel1;
      v60 = a2->Tail.Overlay.CurrentStackLocation;
      if ( BYTE1(v65) != 1 )
        v59 = FastReadCompletionRoutineRdpLevel2;
      v60[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)v59;
      v60[-1].Context = (PVOID)v62;
      v60[-1].Control = -32;
    }
    FvePerfTraceDevPtr(a1, FVE_PERF_READ_SUBREQUEST_START, a2);
    IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 112), a2);
  }
  return v12;
}

```

## disassembly

```asm
0x1400ec57c  mov     [rsp+arg_18], rbx
0x1400ec581  mov     [rsp+arg_10], r8b
0x1400ec586  push    rbp
0x1400ec587  push    rsi
0x1400ec588  push    rdi
0x1400ec589  push    r12
0x1400ec58b  push    r13
0x1400ec58d  push    r14
0x1400ec58f  push    r15
0x1400ec591  sub     rsp, 40h
0x1400ec595  mov     r12, [rcx+8]
0x1400ec599  mov     r15, r9
0x1400ec59c  mov     rbx, [rdx+78h]
0x1400ec5a0  mov     r13b, r8b
0x1400ec5a3  mov     rbp, rdx
0x1400ec5a6  mov     rdi, rcx
0x1400ec5a9  call    Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline
0x1400ec5ae  mov     esi, 1
0x1400ec5b3  test    eax, eax
0x1400ec5b5  jz      short loc_1400EC5DA
0x1400ec5b7  cmp     qword ptr [rdi+1418h], 0
0x1400ec5bf  jz      short loc_1400EC5DA
0x1400ec5c1  cmp     dword ptr [rdi+344h], 3
0x1400ec5c8  jnz     short loc_1400EC5DA
0x1400ec5ca  mov     eax, [rdi+328h]
0x1400ec5d0  test    sil, al
0x1400ec5d3  jz      short loc_1400EC5DA
0x1400ec5d5  mov     r14b, sil
0x1400ec5d8  jmp     short loc_1400EC5DD
0x1400ec5da  xor     r14b, r14b
0x1400ec5dd  cmp     byte ptr [rdi+5C5h], 0
0x1400ec5e4  jz      short loc_1400EC5F2
0x1400ec5e6  mov     eax, [rbp+78h]
0x1400ec5e9  shr     rax, 18h
0x1400ec5ed  movzx   ecx, al
0x1400ec5f0  jmp     short loc_1400EC605
0x1400ec5f2  mov     r8d, 8
0x1400ec5f8  mov     rdx, rbp
0x1400ec5fb  mov     rcx, rdi
0x1400ec5fe  call    GetPriorityFromIrpEx
0x1400ec603  mov     ecx, eax
0x1400ec605  cmp     dword ptr [rdi+348h], 0
0x1400ec60c  mov     [rsp+78h+arg_8], ecx
0x1400ec613  jnz     loc_1400EC88A
0x1400ec619  cmp     qword ptr [rdi+1290h], 0
0x1400ec621  jnz     loc_1400EC88A
0x1400ec627  test    r14b, r14b
0x1400ec62a  jnz     loc_1400EC88A
0x1400ec630  cmp     qword ptr [r12+298h], 0
0x1400ec639  jz      loc_1400EC88A
0x1400ec63f  test    dword ptr [rdi+328h], 100h
0x1400ec649  jz      short loc_1400EC661
0x1400ec64b  mov     rax, [rdi+2E0h]
0x1400ec652  test    rax, rax
0x1400ec655  jz      short loc_1400EC661
0x1400ec657  cmp     qword ptr [rax], 0
0x1400ec65b  jnz     loc_1400EC88A
0x1400ec661  mov     eax, [r12+374h]
0x1400ec669  or      edx, 0FFFFFFFFh
0x1400ec66c  cmp     [r12+rax*4+55Ch], edx
0x1400ec674  jnz     loc_1400EC88A
0x1400ec67a  cmp     [r12+rax*4+568h], edx
0x1400ec682  jnz     loc_1400EC88A
0x1400ec688  cmp     dword ptr [r12+rax*4+468h], 0
0x1400ec691  jz      loc_1400EC88A
0x1400ec697  lea     eax, [rcx-8]
0x1400ec69a  cmp     eax, 6
0x1400ec69d  ja      loc_1400EC88A
0x1400ec6a3  mov     eax, [rbp+10h]
0x1400ec6a6  test    al, 42h
0x1400ec6a8  jnz     loc_1400EC88A
0x1400ec6ae  mov     rcx, rbp; Irp
0x1400ec6b1  call    cs:__imp_IoGetIoPriorityHint
0x1400ec6b8  nop     dword ptr [rax+rax+00h]
0x1400ec6bd  cmp     eax, 2
0x1400ec6c0  jnz     loc_1400EC88A
0x1400ec6c6  cmp     qword ptr [rdi+3D0h], 0
0x1400ec6ce  mov     r14d, dword ptr [rsp+78h+Length]
0x1400ec6d6  jz      short loc_1400EC71E
0x1400ec6d8  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400ec6dd  test    eax, eax
0x1400ec6df  jz      short loc_1400EC6EA
0x1400ec6e1  test    byte ptr [rdi+1143h], 8
0x1400ec6e8  jnz     short loc_1400EC6F7
0x1400ec6ea  mov     rax, [rdi+3D0h]
0x1400ec6f1  cmp     [rax+0Ah], si
0x1400ec6f5  jnz     short loc_1400EC6FB
0x1400ec6f7  xor     eax, eax
0x1400ec6f9  jmp     short loc_1400EC703
0x1400ec6fb  mov     eax, [rax+1Ch]
0x1400ec6fe  test    eax, eax
0x1400ec700  cmovz   eax, esi
0x1400ec703  mov     ecx, [rdi+51Ch]
0x1400ec709  imul    rcx, rax
0x1400ec70d  cmp     r15, rcx
0x1400ec710  jnb     short loc_1400EC71E
0x1400ec712  mov     rcx, r14
0x1400ec715  add     rcx, r15
0x1400ec718  jnz     loc_1400EC88A
0x1400ec71e  mov     rdx, [rdi+3D0h]
0x1400ec725  test    rdx, rdx
0x1400ec728  jz      loc_1400EC844
0x1400ec72e  mov     eax, [rdi+328h]
0x1400ec734  test    eax, 17Fh
0x1400ec739  jz      short loc_1400EC7A5
0x1400ec73b  test    al, 40h
0x1400ec73d  jnz     short loc_1400EC7A5
0x1400ec73f  mov     rdx, [rdi+420h]
0x1400ec746  mov     eax, [rdi+428h]
0x1400ec74c  add     rax, rdx
0x1400ec74f  cmp     r15, rax
0x1400ec752  jnb     short loc_1400EC761
0x1400ec754  lea     rcx, [r15+r14]
0x1400ec758  cmp     rcx, rdx
0x1400ec75b  ja      loc_1400EC88A
0x1400ec761  mov     rdx, [rdi+438h]
0x1400ec768  mov     eax, [rdi+440h]
0x1400ec76e  add     rax, rdx
0x1400ec771  cmp     r15, rax
0x1400ec774  jnb     short loc_1400EC783
0x1400ec776  lea     rcx, [r15+r14]
0x1400ec77a  cmp     rcx, rdx
0x1400ec77d  ja      loc_1400EC88A
0x1400ec783  mov     rdx, [rdi+450h]
0x1400ec78a  mov     eax, [rdi+458h]
0x1400ec790  add     rax, rdx
0x1400ec793  cmp     r15, rax
0x1400ec796  jnb     short loc_1400EC7A5
0x1400ec798  lea     rcx, [r15+r14]
0x1400ec79c  cmp     rcx, rdx
0x1400ec79f  ja      loc_1400EC88A
0x1400ec7a5  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400ec7aa  test    eax, eax
0x1400ec7ac  jz      short loc_1400EC7DC
0x1400ec7ae  test    byte ptr [rdi+1143h], 8
0x1400ec7b5  jnz     short loc_1400EC7C4
0x1400ec7b7  mov     rax, [rdi+3D0h]
0x1400ec7be  cmp     [rax+0Ah], si
0x1400ec7c2  jnz     short loc_1400EC7C8
0x1400ec7c4  xor     eax, eax
0x1400ec7c6  jmp     short loc_1400EC7D0
0x1400ec7c8  mov     eax, [rax+1Ch]
0x1400ec7cb  test    eax, eax
0x1400ec7cd  cmovz   eax, esi
0x1400ec7d0  mov     rcx, [rdi+3D0h]
0x1400ec7d7  mov     rdx, rcx
0x1400ec7da  jmp     short loc_1400EC7F9
0x1400ec7dc  mov     rdx, [rdi+3D0h]
0x1400ec7e3  cmp     [rdx+0Ah], si
0x1400ec7e7  jnz     short loc_1400EC7ED
0x1400ec7e9  xor     eax, eax
0x1400ec7eb  jmp     short loc_1400EC7F6
0x1400ec7ed  mov     eax, [rdx+1Ch]
0x1400ec7f0  test    eax, eax
0x1400ec7f2  jnz     short loc_1400EC7F6
0x1400ec7f4  mov     eax, esi
0x1400ec7f6  mov     rcx, rdx
0x1400ec7f9  mov     r8, [rcx+38h]
0x1400ec7fd  mov     ecx, [rdi+51Ch]
0x1400ec803  imul    rcx, rax
0x1400ec807  add     rcx, r8
0x1400ec80a  cmp     r15, rcx
0x1400ec80d  jnb     short loc_1400EC818
0x1400ec80f  lea     rax, [r15+r14]
0x1400ec813  cmp     rax, r8
0x1400ec816  ja      short loc_1400EC88A
0x1400ec818  test    rdx, rdx
0x1400ec81b  jz      short loc_1400EC844
0x1400ec81d  mov     eax, 2
0x1400ec822  cmp     [rdx+0Ch], ax
0x1400ec826  jnz     short loc_1400EC844
0x1400ec828  mov     eax, [rdx+18h]
0x1400ec82b  test    eax, eax
0x1400ec82d  jz      short loc_1400EC844
0x1400ec82f  mov     r8, [rdx+10h]
0x1400ec833  add     rax, r8
0x1400ec836  cmp     r15, rax
0x1400ec839  jnb     short loc_1400EC844
0x1400ec83b  lea     rcx, [r15+r14]
0x1400ec83f  cmp     rcx, r8
0x1400ec842  ja      short loc_1400EC88A
0x1400ec844  cmp     dword ptr [rdi+5D4h], 0
0x1400ec84b  jz      short loc_1400EC873
0x1400ec84d  mov     rax, [rdi+570h]
0x1400ec854  mov     rcx, [rax+130h]
0x1400ec85b  mov     rdx, [rcx+60h]
0x1400ec85f  mov     eax, [rcx+5Ch]
0x1400ec862  add     rax, rdx
0x1400ec865  cmp     r15, rax
0x1400ec868  jnb     short loc_1400EC873
0x1400ec86a  lea     rcx, [r15+r14]
0x1400ec86e  cmp     rcx, rdx
0x1400ec871  ja      short loc_1400EC88A
0x1400ec873  mov     eax, [r12+374h]
0x1400ec87b  test    r13b, r13b
0x1400ec87e  jz      short loc_1400EC8A9
0x1400ec880  cmp     r14d, [rdi+rax*4+74Ch]
0x1400ec888  jbe     short loc_1400EC8B3
0x1400ec88a  xor     sil, sil
0x1400ec88d  mov     rbx, [rsp+78h+arg_18]
0x1400ec895  mov     al, sil
0x1400ec898  add     rsp, 40h
0x1400ec89c  pop     r15
0x1400ec89e  pop     r14
0x1400ec8a0  pop     r13
0x1400ec8a2  pop     r12
0x1400ec8a4  pop     rdi
0x1400ec8a5  pop     rsi
0x1400ec8a6  pop     rbp
0x1400ec8a7  retn
0x1400ec8a9  cmp     r14d, [rdi+rax*4+740h]
0x1400ec8b1  ja      short loc_1400EC88A
0x1400ec8b3  imul    edx, [rdi+rax*4+644h], 21h ; '!'
0x1400ec8bb  mov     ecx, [rdi+rax*4+638h]
0x1400ec8c2  cmp     edx, ecx
0x1400ec8c4  cmovbe  edx, ecx
0x1400ec8c7  cmp     r14d, edx
0x1400ec8ca  ja      short loc_1400EC88A
0x1400ec8cc  lea     rax, [rdi+11E8h]
0x1400ec8d3  cmp     [rax], rax
0x1400ec8d6  jnz     short loc_1400EC88A
0x1400ec8d8  mov     rcx, [rbp+8]
0x1400ec8dc  call    cs:__imp_MmAreMdlPagesCached
0x1400ec8e3  nop     dword ptr [rax+rax+00h]
0x1400ec8e8  test    r13b, r13b
0x1400ec8eb  jnz     short loc_1400EC958
0x1400ec8ed  mov     ecx, [r12+374h]
0x1400ec8f5  cmp     dword ptr [rdi+rcx*4+6A4h], 0
0x1400ec8fd  jnz     short loc_1400EC958
0x1400ec8ff  test    eax, eax
0x1400ec901  jz      short loc_1400EC958
0x1400ec903  mov     rcx, [rbp+8]
0x1400ec907  xor     r15d, r15d
0x1400ec90a  mov     [rsp+78h+MemoryDescriptorList], 0
0x1400ec913  lea     edx, [r15+2]
0x1400ec917  call    cs:__imp_MmMdlPageContentsState
0x1400ec91e  nop     dword ptr [rax+rax+00h]
0x1400ec923  test    eax, eax
0x1400ec925  jnz     loc_1400ECAA5
0x1400ec92b  mov     rax, [rbp+8]
0x1400ec92f  mov     ecx, [rdi+51Ch]
0x1400ec935  mov     r8d, [rax+2Ch]
0x1400ec939  lea     eax, [rcx-1]
0x1400ec93c  test    ecx, eax
0x1400ec93e  jnz     short loc_1400EC949
0x1400ec940  test    ecx, ecx
0x1400ec942  jz      short loc_1400EC949
0x1400ec944  and     eax, r8d
0x1400ec947  jmp     short loc_1400EC952
0x1400ec949  xor     edx, edx
0x1400ec94b  mov     eax, r8d
0x1400ec94e  div     ecx
0x1400ec950  test    edx, edx
0x1400ec952  jz      loc_1400ECAA5
0x1400ec958  mov     eax, gs:1A4h
0x1400ec960  mov     dword ptr [rsp+78h+var_48], eax
0x1400ec964  mov     eax, [r12+374h]
0x1400ec96c  cmp     r14d, [rdi+rax*4+638h]
0x1400ec974  ja      short loc_1400EC9A9
0x1400ec976  mov     rcx, [rdi+7E8h]
0x1400ec97d  mov     byte ptr [rsp+78h+arg_0], sil
0x1400ec985  test    rcx, rcx
0x1400ec988  jz      short loc_1400EC991
0x1400ec98a  call    PplAllocateFromLookasideList
0x1400ec98f  jmp     short loc_1400EC9A4
0x1400ec991  mov     rcx, [rdi+7E0h]; Lookaside
0x1400ec998  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400ec99f  nop     dword ptr [rax+rax+00h]
0x1400ec9a4  mov     r15, r14
0x1400ec9a7  jmp     short loc_1400EC9E2
0x1400ec9a9  mov     rdx, r14; Length
0x1400ec9ac  mov     byte ptr [rsp+78h+arg_0], 2
0x1400ec9b4  xor     ecx, ecx; Base
0x1400ec9b6  mov     r15, r14
0x1400ec9b9  call    cs:__imp_MmSizeOfMdl
0x1400ec9c0  nop     dword ptr [rax+rax+00h]
0x1400ec9c5  lea     edx, [r14+40h]
0x1400ec9c9  mov     ecx, 4Ah ; 'J'
0x1400ec9ce  add     edx, eax
0x1400ec9d0  mov     r8d, 70455646h
0x1400ec9d6  call    cs:__imp_ExAllocatePool2
0x1400ec9dd  nop     dword ptr [rax+rax+00h]
0x1400ec9e2  mov     r13, rax
0x1400ec9e5  test    rax, rax
0x1400ec9e8  jz      loc_1400EC88A
0x1400ec9ee  add     r15, rax
0x1400ec9f1  xor     edx, edx; Val
0x1400ec9f3  mov     rcx, r15; void *
0x1400ec9f6  lea     rax, [r15+40h]
0x1400ec9fa  lea     r8d, [rdx+40h]; Size
0x1400ec9fe  mov     [rsp+78h+MemoryDescriptorList], rax
0x1400eca03  call    memset
0x1400eca08  mov     eax, [rbp+78h]
0x1400eca0b  lea     rcx, [r14+0FFFh]
0x1400eca12  mov     r8, [rsp+78h+MemoryDescriptorList]
0x1400eca17  mov     edx, r13d
0x1400eca1a  shr     rax, 8
0x1400eca1e  mov     r10d, 0FFFh
0x1400eca24  movzx   eax, al
0x1400eca27  and     r13, 0FFFFFFFFFFFFF000h
  ... truncated ...
```
