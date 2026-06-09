# FveTryFastPathIo

- ea: `0x1400e49ec`
- end: `0x1400e50f8`
- name: `FveTryFastPathIo`
- size: `1804`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400e8a30`

## callees

- `0x140008904`
- `0x140009bf4`
- `0x140021d00`
- `0x1400292a0`
- `0x14002c140`
- `0x1400b9a20`
- `0x1400ba1c0`
- `0x1400cf770`
- `0x1400d5f8c`
- `0x1400e49ec`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400e50e7`
- `ntoskrnl!IofCallDriver` at `0x1400e50e7`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400e4eac`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400e4eac`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400e4d47`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400e4ebd`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400e4d47`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400e4ebd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400e4dc8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400e4dc8`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400e4adf`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400e4adf`
- `ntoskrnl!MmSizeOfMdl` at `0x1400e4de9`
- `ntoskrnl!MmSizeOfMdl` at `0x1400e4de9`
- `ntoskrnl!MmAreMdlPagesCached` at `0x1400e4d15`
- `ntoskrnl!MmAreMdlPagesCached` at `0x1400e4d15`
- `ntoskrnl!KeBugCheckEx` at `0x1400e5060`
- `ntoskrnl!KeBugCheckEx` at `0x1400e5060`
- `ntoskrnl!ExAllocatePool2` at `0x1400e4e06`
- `ntoskrnl!ExAllocatePool2` at `0x1400e4e06`

## pseudocode

```c
char __fastcall FveTryFastPathIo(__int64 a1, IRP *a2, char a3, unsigned __int64 a4, unsigned int Length)
{
  struct _LIST_ENTRY *Flink; // rax
  struct _MDL *v6; // r13
  __int64 v8; // r12
  unsigned int PriorityFromIrp; // edx
  _QWORD *v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  char v16; // di
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rdx
  unsigned __int64 v26; // r8
  __int64 v27; // rax
  unsigned __int64 v28; // r8
  __int64 v29; // rcx
  unsigned __int64 v30; // rdx
  __int64 v31; // rax
  unsigned int v33; // edx
  int v34; // eax
  char *v35; // r15
  __int64 ByteOffset; // r8
  unsigned int v37; // ecx
  bool v38; // zf
  char *Pool2; // rax
  __int64 v40; // r15
  int v41; // eax
  unsigned __int64 v42; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  __int64 v44; // rdx
  char v45; // dl
  int v46; // eax
  __int64 v47; // rdx
  __int64 v48; // rdx
  ULONG v49; // eax
  struct _IO_STACK_LOCATION *v50; // rdx
  DWORD LowPart; // edx
  struct _IO_STACK_LOCATION *v52; // rax
  __int64 (__fastcall *v53)(); // rax
  struct _IO_STACK_LOCATION *v54; // rcx
  int LockArray_high; // [rsp+30h] [rbp-48h]
  unsigned int v56; // [rsp+34h] [rbp-44h]
  unsigned __int8 v57; // [rsp+38h] [rbp-40h]
  char v58; // [rsp+80h] [rbp+8h]
  struct _LIST_ENTRY *v59; // [rsp+80h] [rbp+8h]
  struct _LIST_ENTRY *v60; // [rsp+80h] [rbp+8h]
  unsigned int v61; // [rsp+88h] [rbp+10h]

  Flink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  v6 = 0;
  v8 = *(_QWORD *)(a1 + 8);
  v57 = (unsigned __int8)Flink;
  if ( *(_BYTE *)(a1 + 1477) )
    PriorityFromIrp = BYTE3(Flink);
  else
    PriorityFromIrp = GetPriorityFromIrpEx(a1, a2, 8);
  v61 = PriorityFromIrp;
  if ( *(_DWORD *)(a1 + 840) )
    return 0;
  if ( *(_QWORD *)(a1 + 4736) )
    return 0;
  if ( !*(_QWORD *)(v8 + 664) )
    return 0;
  if ( (*(_DWORD *)(a1 + 808) & 0x100) != 0 )
  {
    v13 = *(_QWORD **)(a1 + 736);
    if ( v13 )
    {
      if ( *v13 )
        return 0;
    }
  }
  v14 = *(unsigned int *)(v8 + 884);
  if ( *(_DWORD *)(v8 + 4 * v14 + 1372) != -1
    || *(_DWORD *)(v8 + 4 * v14 + 1384) != -1
    || !*(_DWORD *)(v8 + 4 * v14 + 1128)
    || PriorityFromIrp - 8 > 6
    || (a2->Flags & 0x42) != 0
    || IoGetIoPriorityHint(a2) != IoPriorityNormal )
  {
    return 0;
  }
  v16 = 1;
  if ( *(_QWORD *)(a1 + 976) )
  {
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v15)
      && (*(_BYTE *)(a1 + 4403) & 8) != 0
      || (v17 = *(_QWORD *)(a1 + 976), *(_WORD *)(v17 + 10) == 1) )
    {
      v18 = 0;
    }
    else
    {
      v18 = *(unsigned int *)(v17 + 28);
      if ( !(_DWORD)v18 )
        v18 = 1;
    }
    v15 = v18 * *(unsigned int *)(a1 + 1308);
    if ( a4 < v15 )
    {
      v15 = a4 + Length;
      if ( v15 )
        return 0;
    }
  }
  if ( *(_QWORD *)(a1 + 976) )
  {
    LOBYTE(v15) = (*(_DWORD *)(a1 + 808) & 0x17F) != 0;
    if ( ((unsigned __int8)v15 & ((*(_DWORD *)(a1 + 808) & 0x40) == 0)) != 0 )
    {
      v19 = *(_QWORD *)(a1 + 1056);
      if ( a4 < v19 + *(unsigned int *)(a1 + 1064) )
      {
        v15 = Length + a4;
        if ( v15 > v19 )
          return 0;
      }
      v20 = *(_QWORD *)(a1 + 1080);
      if ( a4 < v20 + *(unsigned int *)(a1 + 1088) )
      {
        v15 = Length + a4;
        if ( v15 > v20 )
          return 0;
      }
      v21 = *(_QWORD *)(a1 + 1104);
      if ( a4 < v21 + *(unsigned int *)(a1 + 1112) )
      {
        v15 = Length + a4;
        if ( v15 > v21 )
          return 0;
      }
    }
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v15) )
    {
      if ( (*(_BYTE *)(a1 + 4403) & 8) != 0 || (v22 = *(_QWORD *)(a1 + 976), *(_WORD *)(v22 + 10) == 1) )
      {
        v23 = 0;
      }
      else
      {
        v23 = *(unsigned int *)(v22 + 28);
        if ( !(_DWORD)v23 )
          v23 = 1;
      }
      v24 = *(_QWORD *)(a1 + 976);
      v25 = v24;
    }
    else
    {
      v25 = *(_QWORD *)(a1 + 976);
      if ( *(_WORD *)(v25 + 10) == 1 )
      {
        v23 = 0;
      }
      else
      {
        v23 = *(unsigned int *)(v25 + 28);
        if ( !(_DWORD)v23 )
          v23 = 1;
      }
      v24 = *(_QWORD *)(a1 + 976);
    }
    v26 = *(_QWORD *)(v24 + 56);
    if ( a4 < v26 + v23 * *(unsigned int *)(a1 + 1308) && Length + a4 > v26 )
      return 0;
    if ( v25 )
    {
      if ( *(_WORD *)(v25 + 12) == 2 )
      {
        v27 = *(unsigned int *)(v25 + 24);
        if ( (_DWORD)v27 )
        {
          v28 = *(_QWORD *)(v25 + 16);
          if ( a4 < v28 + v27 && Length + a4 > v28 )
            return 0;
        }
      }
    }
  }
  if ( *(_DWORD *)(a1 + 1492) )
  {
    v29 = *(_QWORD *)(*(_QWORD *)(a1 + 1392) + 304LL);
    v30 = *(_QWORD *)(v29 + 96);
    if ( a4 < v30 + *(unsigned int *)(v29 + 92) && Length + a4 > v30 )
      return 0;
  }
  v31 = *(unsigned int *)(v8 + 884);
  if ( a3 )
  {
    if ( Length > *(_DWORD *)(a1 + 4 * v31 + 1868) )
      return 0;
  }
  else if ( Length > *(_DWORD *)(a1 + 4 * v31 + 1856) )
  {
    return 0;
  }
  v33 = 33 * *(_DWORD *)(a1 + 4 * v31 + 1604);
  if ( v33 <= *(_DWORD *)(a1 + 4 * v31 + 1592) )
    v33 = *(_DWORD *)(a1 + 4 * v31 + 1592);
  if ( Length > v33 || *(_QWORD *)(a1 + 4568) != a1 + 4568 )
    return 0;
  v34 = MmAreMdlPagesCached(a2->MdlAddress);
  if ( a3
    || *(_DWORD *)(a1 + 4LL * *(unsigned int *)(v8 + 884) + 1700)
    || !v34
    || (v35 = 0, !(unsigned int)MmMdlPageContentsState(a2->MdlAddress, 2))
    && ((v37 = *(_DWORD *)(a1 + 1308), ByteOffset = a2->MdlAddress->ByteOffset, ((v37 - 1) & v37) != 0) || !v37
      ? (v38 = (unsigned int)ByteOffset % v37 == 0)
      : (v38 = ((unsigned int)ByteOffset & (v37 - 1)) == 0),
        !v38) )
  {
    LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
    if ( Length > *(_DWORD *)(a1 + 4LL * *(unsigned int *)(v8 + 884) + 1592) )
    {
      v58 = 2;
      v40 = Length;
      v41 = MmSizeOfMdl(0, Length);
      Pool2 = (char *)ExAllocatePool2(74, v41 + Length + 64, 1883592262);
    }
    else
    {
      v58 = 1;
      if ( *(_QWORD *)(a1 + 2024) )
        Pool2 = (char *)PplAllocateFromLookasideList();
      else
        Pool2 = (char *)ExAllocateFromNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 2016));
      v40 = Length;
    }
    v42 = (unsigned __int64)Pool2;
    if ( !Pool2 )
      return 0;
    v35 = &Pool2[v40];
    v6 = (struct _MDL *)(v35 + 64);
    memset(v35, 0, 0x40u);
    *((_DWORD *)v35 + 10) = (unsigned __int8)BYTE1(LODWORD(a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink));
    v35[44] = v58;
    *((_QWORD *)v35 + 7) = a2->MdlAddress;
    *((_DWORD *)v35 + 12) = LockArray_high;
    *((_QWORD *)v35 + 8) = 0;
    *((_QWORD *)v35 + 12) = v42 & 0xFFFFFFFFFFFFF000uLL;
    *((_WORD *)v35 + 37) = 0;
    *((_WORD *)v35 + 36) = 8 * ((((v42 & 0xFFF) + Length + 4095LL) >> 12) + 6);
    *((_DWORD *)v35 + 27) = v42 & 0xFFF;
    *((_DWORD *)v35 + 26) = Length;
    MmBuildMdlForNonPagedPool((PMDL)(v35 + 64));
    MmMdlPageContentsState(v35 + 64, 1);
  }
  LOBYTE(ByteOffset) = a3;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v59 = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  FvePerfReportIoSplitSize(a1, Length, ByteOffset);
  LOBYTE(v44) = a3;
  FvePerfReportSubRequest(a1, v44);
  v46 = *(_DWORD *)(a1 + 2328);
  if ( !v45 )
  {
    if ( v46 == 1 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 2336) + 288LL));
      goto LABEL_89;
    }
    v48 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
    ++*(_DWORD *)(v48 + *(_QWORD *)(a1 + 2336) + 288);
LABEL_88:
    v45 = a3;
    goto LABEL_89;
  }
  if ( v46 != 1 )
  {
    v47 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
    ++*(_DWORD *)(v47 + *(_QWORD *)(a1 + 2336) + 292);
    goto LABEL_88;
  }
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 2336) + 292LL));
LABEL_89:
  v49 = MEMORY[0xFFFFF78000000008];
  v56 = MEMORY[0xFFFFF7800000000C];
  if ( v35 )
    *(_QWORD *)v35 = MEMORY[0xFFFFF78000000008];
  if ( v45 )
  {
    v60 = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
    BYTE2(v60) = 1;
    a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = v60;
    a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = (struct _LIST_ENTRY *)v35;
    if ( v57 >= 2u || Length > *(_DWORD *)(a1 + 4LL * *(unsigned int *)(v8 + 884) + 1880) )
      FveQueueIoWork(a1, a2, v61);
    else
      FastWriteEncrypt(a1, a2, v35);
  }
  else
  {
    if ( v6 )
      a2->MdlAddress = v6;
    v50 = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v50[-1].MajorFunction = *(_OWORD *)&v50->MajorFunction;
    *(_OWORD *)&v50[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v50->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v50[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v50->Parameters.SetQuota + 6);
    v50[-1].FileObject = v50->FileObject;
    v50[-1].Control = 0;
    if ( *(_BYTE *)(a1 + 1477) )
    {
      LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
      if ( (LowPart & 0xF) != 0 )
        KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
      CurrentStackLocation->Parameters.Read.ByteOffset.LowPart = LowPart + v61;
    }
    if ( v35 )
    {
      v52 = a2->Tail.Overlay.CurrentStackLocation;
      v52[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)FastReadCompletionRoutineControl;
      v52[-1].Context = v35;
      v52[-1].Control = -32;
    }
    else
    {
      CurrentStackLocation->Parameters.Create.Options = v49;
      v53 = FastReadCompletionRoutineRdpLevel1;
      v54 = a2->Tail.Overlay.CurrentStackLocation;
      if ( BYTE1(v59) != 1 )
        v53 = FastReadCompletionRoutineRdpLevel2;
      v54[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)v53;
      v54[-1].Context = (PVOID)v56;
      v54[-1].Control = -32;
    }
    FvePerfTraceDevPtr(a1, FVE_PERF_READ_SUBREQUEST_START, a2);
    IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 112), a2);
  }
  return v16;
}

```

## disassembly

```asm
0x1400e49ec  mov     [rsp+arg_18], rbx
0x1400e49f1  mov     [rsp+arg_10], r8b
0x1400e49f6  push    rbp
0x1400e49f7  push    rsi
0x1400e49f8  push    rdi
0x1400e49f9  push    r12
0x1400e49fb  push    r13
0x1400e49fd  push    r14
0x1400e49ff  push    r15
0x1400e4a01  sub     rsp, 40h
0x1400e4a05  mov     rax, [rdx+78h]
0x1400e4a09  xor     r13d, r13d
0x1400e4a0c  mov     rbp, r9
0x1400e4a0f  mov     r12, [rcx+8]
0x1400e4a13  mov     r15b, r8b
0x1400e4a16  mov     rsi, rdx
0x1400e4a19  mov     rbx, rcx
0x1400e4a1c  mov     qword ptr [rsp+78h+var_40], rax
0x1400e4a21  cmp     [rcx+5C5h], r13b
0x1400e4a28  jz      short loc_1400E4A33
0x1400e4a2a  sar     rax, 18h
0x1400e4a2e  movzx   edx, al
0x1400e4a31  jmp     short loc_1400E4A40
0x1400e4a33  mov     r8d, 8
0x1400e4a39  call    GetPriorityFromIrpEx
0x1400e4a3e  mov     edx, eax
0x1400e4a40  mov     [rsp+78h+arg_8], edx
0x1400e4a47  cmp     [rbx+348h], r13d
0x1400e4a4e  jnz     loc_1400E4CC3
0x1400e4a54  cmp     [rbx+1280h], r13
0x1400e4a5b  jnz     loc_1400E4CC3
0x1400e4a61  cmp     [r12+298h], r13
0x1400e4a69  jz      loc_1400E4CC3
0x1400e4a6f  test    dword ptr [rbx+328h], 100h
0x1400e4a79  jz      short loc_1400E4A90
0x1400e4a7b  mov     rax, [rbx+2E0h]
0x1400e4a82  test    rax, rax
0x1400e4a85  jz      short loc_1400E4A90
0x1400e4a87  cmp     [rax], r13
0x1400e4a8a  jnz     loc_1400E4CC3
0x1400e4a90  mov     eax, [r12+374h]
0x1400e4a98  or      ecx, 0FFFFFFFFh
0x1400e4a9b  cmp     [r12+rax*4+55Ch], ecx
0x1400e4aa3  jnz     loc_1400E4CC3
0x1400e4aa9  cmp     [r12+rax*4+568h], ecx
0x1400e4ab1  jnz     loc_1400E4CC3
0x1400e4ab7  cmp     [r12+rax*4+468h], r13d
0x1400e4abf  jz      loc_1400E4CC3
0x1400e4ac5  lea     eax, [rdx-8]
0x1400e4ac8  cmp     eax, 6
0x1400e4acb  ja      loc_1400E4CC3
0x1400e4ad1  mov     eax, [rsi+10h]
0x1400e4ad4  test    al, 42h
0x1400e4ad6  jnz     loc_1400E4CC3
0x1400e4adc  mov     rcx, rsi; Irp
0x1400e4adf  call    cs:__imp_IoGetIoPriorityHint
0x1400e4ae6  nop     dword ptr [rax+rax+00h]
0x1400e4aeb  cmp     eax, 2
0x1400e4aee  jnz     loc_1400E4CC3
0x1400e4af4  lea     edi, [rax-1]
0x1400e4af7  mov     r14d, dword ptr [rsp+78h+Length]
0x1400e4aff  cmp     [rbx+3D0h], r13
0x1400e4b06  jz      short loc_1400E4B4F
0x1400e4b08  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400e4b0d  test    eax, eax
0x1400e4b0f  jz      short loc_1400E4B1A
0x1400e4b11  test    byte ptr [rbx+1133h], 8
0x1400e4b18  jnz     short loc_1400E4B27
0x1400e4b1a  mov     rax, [rbx+3D0h]
0x1400e4b21  cmp     [rax+0Ah], di
0x1400e4b25  jnz     short loc_1400E4B2C
0x1400e4b27  mov     eax, r13d
0x1400e4b2a  jmp     short loc_1400E4B34
0x1400e4b2c  mov     eax, [rax+1Ch]
0x1400e4b2f  test    eax, eax
0x1400e4b31  cmovz   eax, edi
0x1400e4b34  mov     ecx, [rbx+51Ch]
0x1400e4b3a  imul    rcx, rax
0x1400e4b3e  cmp     rbp, rcx
0x1400e4b41  jnb     short loc_1400E4B4F
0x1400e4b43  mov     rcx, r14
0x1400e4b46  add     rcx, rbp
0x1400e4b49  jnz     loc_1400E4CC3
0x1400e4b4f  mov     rdx, [rbx+3D0h]
0x1400e4b56  test    rdx, rdx
0x1400e4b59  jz      loc_1400E4C7D
0x1400e4b5f  mov     eax, [rbx+328h]
0x1400e4b65  test    eax, 17Fh
0x1400e4b6a  setnz   cl
0x1400e4b6d  test    al, 40h
0x1400e4b6f  setz    al
0x1400e4b72  test    al, cl
0x1400e4b74  jz      short loc_1400E4BDC
0x1400e4b76  mov     rdx, [rbx+420h]
0x1400e4b7d  mov     eax, [rbx+428h]
0x1400e4b83  add     rax, rdx
0x1400e4b86  cmp     rbp, rax
0x1400e4b89  jnb     short loc_1400E4B98
0x1400e4b8b  lea     rcx, [r14+rbp]
0x1400e4b8f  cmp     rcx, rdx
0x1400e4b92  ja      loc_1400E4CC3
0x1400e4b98  mov     rdx, [rbx+438h]
0x1400e4b9f  mov     eax, [rbx+440h]
0x1400e4ba5  add     rax, rdx
0x1400e4ba8  cmp     rbp, rax
0x1400e4bab  jnb     short loc_1400E4BBA
0x1400e4bad  lea     rcx, [r14+rbp]
0x1400e4bb1  cmp     rcx, rdx
0x1400e4bb4  ja      loc_1400E4CC3
0x1400e4bba  mov     rdx, [rbx+450h]
0x1400e4bc1  mov     eax, [rbx+458h]
0x1400e4bc7  add     rax, rdx
0x1400e4bca  cmp     rbp, rax
0x1400e4bcd  jnb     short loc_1400E4BDC
0x1400e4bcf  lea     rcx, [r14+rbp]
0x1400e4bd3  cmp     rcx, rdx
0x1400e4bd6  ja      loc_1400E4CC3
0x1400e4bdc  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400e4be1  test    eax, eax
0x1400e4be3  jz      short loc_1400E4C14
0x1400e4be5  test    byte ptr [rbx+1133h], 8
0x1400e4bec  jnz     short loc_1400E4BFB
0x1400e4bee  mov     rax, [rbx+3D0h]
0x1400e4bf5  cmp     [rax+0Ah], di
0x1400e4bf9  jnz     short loc_1400E4C00
0x1400e4bfb  mov     eax, r13d
0x1400e4bfe  jmp     short loc_1400E4C08
0x1400e4c00  mov     eax, [rax+1Ch]
0x1400e4c03  test    eax, eax
0x1400e4c05  cmovz   eax, edi
0x1400e4c08  mov     rcx, [rbx+3D0h]
0x1400e4c0f  mov     rdx, rcx
0x1400e4c12  jmp     short loc_1400E4C32
0x1400e4c14  mov     rdx, [rbx+3D0h]
0x1400e4c1b  cmp     [rdx+0Ah], di
0x1400e4c1f  jnz     short loc_1400E4C26
0x1400e4c21  mov     eax, r13d
0x1400e4c24  jmp     short loc_1400E4C2F
0x1400e4c26  mov     eax, [rdx+1Ch]
0x1400e4c29  test    eax, eax
0x1400e4c2b  jnz     short loc_1400E4C2F
0x1400e4c2d  mov     eax, edi
0x1400e4c2f  mov     rcx, rdx
0x1400e4c32  mov     r8, [rcx+38h]
0x1400e4c36  mov     ecx, [rbx+51Ch]
0x1400e4c3c  imul    rcx, rax
0x1400e4c40  add     rcx, r8
0x1400e4c43  cmp     rbp, rcx
0x1400e4c46  jnb     short loc_1400E4C51
0x1400e4c48  lea     rax, [r14+rbp]
0x1400e4c4c  cmp     rax, r8
0x1400e4c4f  ja      short loc_1400E4CC3
0x1400e4c51  test    rdx, rdx
0x1400e4c54  jz      short loc_1400E4C7D
0x1400e4c56  mov     eax, 2
0x1400e4c5b  cmp     [rdx+0Ch], ax
0x1400e4c5f  jnz     short loc_1400E4C7D
0x1400e4c61  mov     eax, [rdx+18h]
0x1400e4c64  test    eax, eax
0x1400e4c66  jz      short loc_1400E4C7D
0x1400e4c68  mov     r8, [rdx+10h]
0x1400e4c6c  add     rax, r8
0x1400e4c6f  cmp     rbp, rax
0x1400e4c72  jnb     short loc_1400E4C7D
0x1400e4c74  lea     rcx, [r14+rbp]
0x1400e4c78  cmp     rcx, r8
0x1400e4c7b  ja      short loc_1400E4CC3
0x1400e4c7d  cmp     [rbx+5D4h], r13d
0x1400e4c84  jz      short loc_1400E4CAC
0x1400e4c86  mov     rax, [rbx+570h]
0x1400e4c8d  mov     rcx, [rax+130h]
0x1400e4c94  mov     rdx, [rcx+60h]
0x1400e4c98  mov     eax, [rcx+5Ch]
0x1400e4c9b  add     rax, rdx
0x1400e4c9e  cmp     rbp, rax
0x1400e4ca1  jnb     short loc_1400E4CAC
0x1400e4ca3  lea     rcx, [r14+rbp]
0x1400e4ca7  cmp     rcx, rdx
0x1400e4caa  ja      short loc_1400E4CC3
0x1400e4cac  mov     eax, [r12+374h]
0x1400e4cb4  test    r15b, r15b
0x1400e4cb7  jz      short loc_1400E4CE2
0x1400e4cb9  cmp     r14d, [rbx+rax*4+74Ch]
0x1400e4cc1  jbe     short loc_1400E4CEC
0x1400e4cc3  mov     dil, r13b
0x1400e4cc6  mov     rbx, [rsp+78h+arg_18]
0x1400e4cce  mov     al, dil
0x1400e4cd1  add     rsp, 40h
0x1400e4cd5  pop     r15
0x1400e4cd7  pop     r14
0x1400e4cd9  pop     r13
0x1400e4cdb  pop     r12
0x1400e4cdd  pop     rdi
0x1400e4cde  pop     rsi
0x1400e4cdf  pop     rbp
0x1400e4ce0  retn
0x1400e4ce2  cmp     r14d, [rbx+rax*4+740h]
0x1400e4cea  ja      short loc_1400E4CC3
0x1400e4cec  imul    edx, [rbx+rax*4+644h], 21h ; '!'
0x1400e4cf4  mov     ecx, [rbx+rax*4+638h]
0x1400e4cfb  cmp     edx, ecx
0x1400e4cfd  cmovbe  edx, ecx
0x1400e4d00  cmp     r14d, edx
0x1400e4d03  ja      short loc_1400E4CC3
0x1400e4d05  lea     rax, [rbx+11D8h]
0x1400e4d0c  cmp     [rax], rax
0x1400e4d0f  jnz     short loc_1400E4CC3
0x1400e4d11  mov     rcx, [rsi+8]
0x1400e4d15  call    cs:__imp_MmAreMdlPagesCached
0x1400e4d1c  nop     dword ptr [rax+rax+00h]
0x1400e4d21  test    r15b, r15b
0x1400e4d24  jnz     short loc_1400E4D88
0x1400e4d26  mov     ecx, [r12+374h]
0x1400e4d2e  cmp     [rbx+rcx*4+6A4h], r13d
0x1400e4d36  jnz     short loc_1400E4D88
0x1400e4d38  test    eax, eax
0x1400e4d3a  jz      short loc_1400E4D88
0x1400e4d3c  mov     rcx, [rsi+8]
0x1400e4d40  xor     r15d, r15d
0x1400e4d43  lea     edx, [r15+2]
0x1400e4d47  call    cs:__imp_MmMdlPageContentsState
0x1400e4d4e  nop     dword ptr [rax+rax+00h]
0x1400e4d53  test    eax, eax
0x1400e4d55  jnz     loc_1400E4EC9
0x1400e4d5b  mov     rax, [rsi+8]
0x1400e4d5f  mov     ecx, [rbx+51Ch]
0x1400e4d65  mov     r8d, [rax+2Ch]
0x1400e4d69  lea     eax, [rcx-1]
0x1400e4d6c  test    ecx, eax
0x1400e4d6e  jnz     short loc_1400E4D79
0x1400e4d70  test    ecx, ecx
0x1400e4d72  jz      short loc_1400E4D79
0x1400e4d74  and     eax, r8d
0x1400e4d77  jmp     short loc_1400E4D82
0x1400e4d79  xor     edx, edx
0x1400e4d7b  mov     eax, r8d
0x1400e4d7e  div     ecx
0x1400e4d80  test    edx, edx
0x1400e4d82  jz      loc_1400E4EC9
0x1400e4d88  mov     eax, gs:1A4h
0x1400e4d90  mov     dword ptr [rsp+78h+var_48], eax
0x1400e4d94  mov     eax, [r12+374h]
0x1400e4d9c  cmp     r14d, [rbx+rax*4+638h]
0x1400e4da4  ja      short loc_1400E4DD9
0x1400e4da6  mov     rcx, [rbx+7E8h]
0x1400e4dad  mov     byte ptr [rsp+78h+arg_0], dil
0x1400e4db5  test    rcx, rcx
0x1400e4db8  jz      short loc_1400E4DC1
0x1400e4dba  call    PplAllocateFromLookasideList
0x1400e4dbf  jmp     short loc_1400E4DD4
0x1400e4dc1  mov     rcx, [rbx+7E0h]; Lookaside
0x1400e4dc8  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400e4dcf  nop     dword ptr [rax+rax+00h]
0x1400e4dd4  mov     r15, r14
0x1400e4dd7  jmp     short loc_1400E4E12
0x1400e4dd9  mov     rdx, r14; Length
0x1400e4ddc  mov     byte ptr [rsp+78h+arg_0], 2
0x1400e4de4  xor     ecx, ecx; Base
0x1400e4de6  mov     r15, r14
0x1400e4de9  call    cs:__imp_MmSizeOfMdl
0x1400e4df0  nop     dword ptr [rax+rax+00h]
0x1400e4df5  lea     edx, [r14+40h]
0x1400e4df9  mov     ecx, 4Ah ; 'J'
0x1400e4dfe  add     edx, eax
0x1400e4e00  mov     r8d, 70455646h
0x1400e4e06  call    cs:__imp_ExAllocatePool2
0x1400e4e0d  nop     dword ptr [rax+rax+00h]
0x1400e4e12  mov     rbp, rax
0x1400e4e15  test    rax, rax
0x1400e4e18  jz      loc_1400E4CC3
0x1400e4e1e  add     r15, rax
0x1400e4e21  xor     edx, edx; Val
0x1400e4e23  mov     rcx, r15; void *
0x1400e4e26  lea     r8d, [rdx+40h]; Size
0x1400e4e2a  lea     r13, [r15+40h]
0x1400e4e2e  call    memset
0x1400e4e33  mov     eax, [rsi+78h]
0x1400e4e36  lea     rcx, [r14+0FFFh]
0x1400e4e3d  shr     rax, 8
0x1400e4e41  mov     edx, ebp
0x1400e4e43  movzx   eax, al
0x1400e4e46  mov     r9d, 0FFFh
0x1400e4e4c  mov     [r15+28h], eax
0x1400e4e50  and     rbp, 0FFFFFFFFFFFFF000h
0x1400e4e57  mov     al, byte ptr [rsp+78h+arg_0]
0x1400e4e5e  mov     [r15+2Ch], al
0x1400e4e62  mov     rax, [rsi+8]
0x1400e4e66  mov     [r15+38h], rax
0x1400e4e6a  mov     eax, dword ptr [rsp+78h+var_48]
0x1400e4e6e  mov     [r15+30h], eax
0x1400e4e72  mov     eax, edx
0x1400e4e74  and     rax, r9
0x1400e4e77  mov     qword ptr [r13+0], 0
0x1400e4e7f  add     rcx, rax
0x1400e4e82  mov     [r13+20h], rbp
0x1400e4e86  shr     rcx, 0Ch
0x1400e4e8a  xor     eax, eax
0x1400e4e8c  add     cx, 6
0x1400e4e90  mov     [r13+0Ah], ax
0x1400e4e95  shl     cx, 3
  ... truncated ...
```
