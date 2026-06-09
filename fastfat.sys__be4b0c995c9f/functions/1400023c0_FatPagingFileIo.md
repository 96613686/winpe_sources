# FatPagingFileIo

- ea: `0x1400023c0`
- end: `0x1400028fa`
- name: `FatPagingFileIo`
- size: `1338`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140006030`
- `0x140006290`
- `0x140007530`

## callees

- `0x1400023c0`
- `0x140005c80`
- `0x14003f50c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140002756`
- `ntoskrnl!KeInitializeEvent` at `0x140002756`
- `ntoskrnl!IofCallDriver` at `0x140002544`
- `ntoskrnl!IofCallDriver` at `0x1400027cd`
- `ntoskrnl!IofCallDriver` at `0x140002544`
- `ntoskrnl!IofCallDriver` at `0x1400027cd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000265f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000281b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000265f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000281b`
- `ntoskrnl!IofCompleteRequest` at `0x1400028d9`
- `ntoskrnl!IofCompleteRequest` at `0x1400028d9`
- `ntoskrnl!IoAllocateMdl` at `0x140002636`
- `ntoskrnl!IoAllocateMdl` at `0x140002636`
- `ntoskrnl!PsUpdateDiskCounters` at `0x1400024e6`
- `ntoskrnl!PsUpdateDiskCounters` at `0x1400024e6`
- `ntoskrnl!PsGetThreadProcess` at `0x1400024c2`
- `ntoskrnl!PsGetThreadProcess` at `0x1400024c2`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x140002572`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x1400027f4`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x140002572`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x1400027f4`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400026a7`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400026a7`
- `ntoskrnl!IoMakeAssociatedIrp` at `0x1400026d4`
- `ntoskrnl!IoMakeAssociatedIrp` at `0x1400026d4`
- `ntoskrnl!KeDelayExecutionThread` at `0x140002729`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400028c3`
- `ntoskrnl!KeDelayExecutionThread` at `0x140002729`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400028c3`
- `ntoskrnl!KeBugCheckEx` at `0x140002478`
- `ntoskrnl!KeBugCheckEx` at `0x1400025ce`
- `ntoskrnl!KeBugCheckEx` at `0x140002478`
- `ntoskrnl!KeBugCheckEx` at `0x1400025ce`

## pseudocode

```c
void __fastcall FatPagingFileIo(PIRP Irp, __int64 a2)
{
  __int64 v2; // r13
  __int64 v4; // rcx
  __int64 v5; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  DWORD LowPart; // ebx
  ULONG_PTR Length; // r14
  struct _KTHREAD *CurrentThread; // rdx
  int v10; // r15d
  unsigned int v11; // r12d
  unsigned int v12; // eax
  unsigned int v13; // ecx
  unsigned int v14; // edi
  unsigned int v15; // ebx
  PEPROCESS ThreadProcess; // rax
  unsigned int v17; // edi
  struct _IO_STACK_LOCATION *v18; // rdx
  UCHAR v19; // al
  struct _IO_STACK_LOCATION *v20; // rax
  struct _DEVICE_OBJECT *v21; // rcx
  unsigned int v22; // eax
  unsigned int v23; // ebx
  unsigned int v24; // r13d
  ULONG v25; // edx
  LONG v26; // ebx
  char *v27; // rcx
  ULONG v28; // r15d
  ULONG v29; // edi
  PIRP AssociatedIrp; // rax
  PIRP v31; // rdi
  struct _IO_STACK_LOCATION *v32; // rdx
  LARGE_INTEGER v33; // rax
  bool v34; // zf
  struct _IO_STACK_LOCATION *v35; // rax
  char v36; // r8
  struct _KEVENT *v37; // r9
  __int64 (__fastcall *v38)(); // r10
  struct _IO_STACK_LOCATION *v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rcx
  unsigned int v42; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v43; // [rsp+34h] [rbp-55h] BYREF
  DWORD v44; // [rsp+38h] [rbp-51h]
  unsigned int v45; // [rsp+3Ch] [rbp-4Dh]
  unsigned int v46; // [rsp+40h] [rbp-49h] BYREF
  LARGE_INTEGER v47; // [rsp+48h] [rbp-41h] BYREF
  unsigned int v48; // [rsp+50h] [rbp-39h] BYREF
  PMDL TargetMdl; // [rsp+58h] [rbp-31h] BYREF
  LARGE_INTEGER v50; // [rsp+60h] [rbp-29h]
  PDEVICE_OBJECT DeviceObject; // [rsp+68h] [rbp-21h]
  __int64 v52; // [rsp+70h] [rbp-19h]
  struct _KEVENT Event[4]; // [rsp+78h] [rbp-11h] BYREF
  int v54; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v55; // [rsp+F8h] [rbp+6Fh]
  struct _IO_STACK_LOCATION *v56; // [rsp+100h] [rbp+77h]
  UCHAR MajorFunction; // [rsp+108h] [rbp+7Fh]

  v55 = a2;
  v2 = a2 + 288;
  v48 = 0;
  v43 = 0;
  v4 = *(_QWORD *)(a2 + 184);
  memset(Event, 0, 32);
  v5 = a2;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  DeviceObject = *(PDEVICE_OBJECT *)(v4 + 136);
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  Length = CurrentStackLocation->Parameters.Read.Length;
  MajorFunction = CurrentStackLocation->MajorFunction;
  v47.QuadPart = 0;
  v42 = 0;
  TargetMdl = 0;
  v54 = 0;
  v56 = CurrentStackLocation;
  v44 = LowPart;
  v52 = a2 + 288;
  if ( !(unsigned __int8)FatLookupMcbEntry(v4, a2 + 288, LowPart, &v47, &v42, &v48) )
    KeBugCheckEx(0x23u, 0x80183u, LowPart, (unsigned int)Length, 0);
  if ( FatDiskAccountingEnabled )
  {
    CurrentThread = KeGetCurrentThread();
    if ( CurrentStackLocation->MajorFunction == 4 )
    {
      v10 = 1;
      v11 = 0;
      v12 = Length;
      v13 = 0;
    }
    else
    {
      v10 = 0;
      v11 = 1;
      v12 = 0;
      v13 = Length;
    }
    v14 = v13;
    v15 = v12;
    ThreadProcess = PsGetThreadProcess(CurrentThread);
    PsUpdateDiskCounters(ThreadProcess, v14, v15, v11, v10, 0);
    CurrentStackLocation = v56;
    LowPart = v44;
    v5 = v55;
  }
  v17 = v42;
  if ( v42 >= (unsigned int)Length )
  {
    v18 = Irp->Tail.Overlay.CurrentStackLocation;
    v19 = CurrentStackLocation->MajorFunction;
    v18[-1].Flags |= 2u;
    v18[-1].MajorFunction = v19;
    v18[-1].Parameters.Read.ByteOffset = v47;
    v18[-1].Parameters.Read.Length = Length;
    v20 = Irp->Tail.Overlay.CurrentStackLocation;
    v20[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)FatPagingFileCompletionRoutine;
    v21 = DeviceObject;
    v20[-1].Context = Irp;
    v20[-1].Control = -96;
    IofCallDriver(v21, Irp);
    if ( FatDiskAccountingEnabled )
    {
      if ( MajorFunction == 4 )
      {
        v22 = Length;
        LODWORD(Length) = 0;
      }
      else
      {
        v22 = 0;
      }
      FsRtlUpdateDiskCounters((unsigned int)Length, v22);
    }
    return;
  }
  v23 = Length + LowPart - 1;
  if ( !(unsigned __int8)FatLookupMcbEntry(*(_QWORD *)(v5 + 184), v2, v23, &TargetMdl, &v54, &v43) )
    KeBugCheckEx(0x23u, 0x801EEu, v23, 1u, 0);
  v24 = v48;
  v25 = 0;
  LOBYTE(v56) = 0;
  v26 = v43 - v48 + 1;
  LOBYTE(v54) = 0;
  v45 = 0;
  Irp->IoStatus.Status = 0;
  Irp->IoStatus.Information = Length;
  Irp->AssociatedIrp.IrpCount = v26;
  if ( v24 <= v43 )
  {
    v50 = v47;
    while ( 1 )
    {
      if ( v17 > (unsigned int)Length )
        v17 = Length;
      v27 = (char *)Irp->UserBuffer + v25;
      v28 = v17;
      v42 = v17;
      v29 = 0;
      v46 = 0;
      TargetMdl = IoAllocateMdl(v27, v28, 0, 0, 0);
      if ( !TargetMdl )
      {
        KeWaitForSingleObject(&FatReserveEvent, Executive, 0, 0, 0);
        TargetMdl = (PMDL)FatReserveMdl;
        LOBYTE(v56) = 1;
        if ( v28 > 0x10000 )
        {
          v29 = v28 - 0x10000;
          v42 = 0x10000;
          v46 = v28 - 0x10000;
          v28 = 0x10000;
        }
      }
      IoBuildPartialMdl(Irp->MdlAddress, TargetMdl, (char *)Irp->UserBuffer + v45, v28);
      if ( (_BYTE)v56 || v26 == 1 && (v24 != v43 || v29) )
        break;
      AssociatedIrp = IoMakeAssociatedIrp(Irp, DeviceObject->StackSize + 1);
      v31 = AssociatedIrp;
      if ( !AssociatedIrp )
        break;
      --v26;
      if ( (_BYTE)v54 )
        goto LABEL_34;
      --AssociatedIrp->CurrentLocation;
      v32 = --AssociatedIrp->Tail.Overlay.CurrentStackLocation;
      v33.QuadPart = v44;
      v32->MajorFunction = CurrentStackLocation->MajorFunction;
      v32->Parameters.Read.Length = v28;
      v32->Parameters.Read.ByteOffset = v33;
      v32->DeviceObject = CurrentStackLocation->DeviceObject;
LABEL_35:
      v34 = (_BYTE)v54 == 0;
      v31->MdlAddress = TargetMdl;
      v35 = v31->Tail.Overlay.CurrentStackLocation;
      if ( v34 )
      {
        v36 = -96;
        v38 = FatPagingFileCompletionRoutine;
        v37 = (struct _KEVENT *)Irp;
      }
      else
      {
        v36 = -32;
        v37 = Event;
        v38 = (__int64 (__fastcall *)())&FatPagingFileCompletionRoutineCatch;
      }
      v35[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)v38;
      v35[-1].Context = v37;
      v35[-1].Control = v36;
      v39 = v31->Tail.Overlay.CurrentStackLocation;
      v39[-1].Flags |= 2u;
      v39[-1].MajorFunction = CurrentStackLocation->MajorFunction;
      v39[-1].Parameters.Read.ByteOffset = v50;
      v39[-1].Parameters.Read.Length = v28;
      IofCallDriver(DeviceObject, v31);
      if ( FatDiskAccountingEnabled )
      {
        if ( MajorFunction == 4 )
        {
          v40 = v28;
          v41 = 0;
        }
        else
        {
          v40 = 0;
          v41 = v28;
        }
        FsRtlUpdateDiskCounters(v41, v40);
      }
      if ( (_BYTE)v54 )
      {
        KeWaitForSingleObject(Event, Executive, 0, 0, 0);
        if ( Irp->IoStatus.Status < 0 )
          goto LABEL_51;
        LOBYTE(v56) = 0;
        LOBYTE(v54) = 0;
      }
      LODWORD(Length) = Length - v28;
      v44 += v28;
      v25 = v28 + v45;
      v17 = v46;
      v45 += v28;
      if ( v46 )
      {
        v50.QuadPart += v28;
        v47 = v50;
      }
      else
      {
        if ( ++v24 > v43 )
          goto LABEL_51;
        FatGetNextMcbEntry(*(_QWORD *)(v55 + 184), v52, v24, &v46, &v47, &v42);
        v17 = v42;
        v25 = v45;
        v50 = v47;
      }
      if ( v24 > v43 )
        goto LABEL_51;
    }
    while ( Irp->AssociatedIrp.IrpCount != v26 )
      KeDelayExecutionThread(0, 0, &Fat30Milliseconds);
    if ( Irp->IoStatus.Status < 0 )
      goto LABEL_51;
    v31 = Irp;
    LOBYTE(v54) = 1;
LABEL_34:
    KeInitializeEvent(Event, SynchronizationEvent, 0);
    *(_QWORD *)&Event[1].Header.Lock = Irp->MdlAddress;
    goto LABEL_35;
  }
LABEL_51:
  if ( v26 )
  {
    while ( Irp->AssociatedIrp.IrpCount != v26 )
      KeDelayExecutionThread(0, 0, &Fat30Milliseconds);
    IofCompleteRequest(Irp, 1);
  }
}

```

## disassembly

```asm
0x1400023c0  mov     [rsp-8+arg_8], rdx
0x1400023c5  push    rbp
0x1400023c6  push    rbx
0x1400023c7  push    rsi
0x1400023c8  push    rdi
0x1400023c9  push    r12
0x1400023cb  push    r13
0x1400023cd  push    r14
0x1400023cf  push    r15
0x1400023d1  lea     rbp, [rsp-1Fh]
0x1400023d6  sub     rsp, 0A8h
0x1400023dd  xor     edi, edi
0x1400023df  lea     r13, [rdx+120h]
0x1400023e6  mov     [rbp+57h+var_90], edi
0x1400023e9  lea     r9, [rbp+57h+var_98]
0x1400023ed  mov     [rbp+57h+var_AC], edi
0x1400023f0  mov     rsi, rcx
0x1400023f3  mov     rcx, [rdx+0B8h]
0x1400023fa  xorps   xmm0, xmm0
0x1400023fd  movups  xmmword ptr [rbp+57h+Event], xmm0
0x140002401  mov     r15, rdx
0x140002404  mov     rdx, r13
0x140002407  mov     r12, [rsi+0B8h]
0x14000240e  movups  xmmword ptr [rbp+57h+Event+10h], xmm0
0x140002412  mov     rax, [rcx+88h]
0x140002419  mov     [rbp+57h+DeviceObject], rax
0x14000241d  mov     al, [r12]
0x140002421  mov     ebx, [r12+18h]
0x140002426  mov     r14d, [r12+8]
0x14000242b  mov     r8d, ebx
0x14000242e  mov     [rbp+57h+arg_18], al
0x140002431  lea     rax, [rbp+57h+var_90]
0x140002435  mov     [rsp+0E0h+var_B8], rax
0x14000243a  lea     rax, [rbp+57h+var_B0]
0x14000243e  mov     [rsp+0E0h+BugCheckParameter4], rax
0x140002443  mov     [rbp+57h+var_98], rdi
0x140002447  mov     [rbp+57h+var_B0], edi
0x14000244a  mov     [rbp+57h+TargetMdl], rdi
0x14000244e  mov     [rbp+57h+arg_0], edi
0x140002451  mov     [rbp+57h+arg_10], r12
0x140002455  mov     [rbp+57h+var_A8], ebx
0x140002458  mov     [rbp+57h+var_70], r13
0x14000245c  call    FatLookupMcbEntry
0x140002461  test    al, al
0x140002463  jnz     short loc_140002485
0x140002465  mov     r9d, r14d; BugCheckParameter3
0x140002468  mov     [rsp+0E0h+BugCheckParameter4], rdi; BugCheckParameter4
0x14000246d  mov     r8d, ebx; BugCheckParameter2
0x140002470  lea     ecx, [rdi+23h]; BugCheckCode
0x140002473  mov     edx, 80183h; BugCheckParameter1
0x140002478  call    cs:__imp_KeBugCheckEx
0x140002485  cmp     cs:FatDiskAccountingEnabled, edi
0x14000248b  jz      short loc_1400024FD
0x14000248d  mov     rdx, gs:188h
0x140002496  cmp     byte ptr [r12], 4
0x14000249b  jnz     short loc_1400024AD
0x14000249d  mov     r15d, 1
0x1400024a3  mov     r12d, edi
0x1400024a6  mov     eax, r14d
0x1400024a9  mov     ecx, edi
0x1400024ab  jmp     short loc_1400024BB
0x1400024ad  mov     r15d, edi
0x1400024b0  mov     r12d, 1
0x1400024b6  mov     eax, edi
0x1400024b8  mov     ecx, r14d
0x1400024bb  mov     edi, ecx
0x1400024bd  mov     rcx, rdx; Thread
0x1400024c0  mov     ebx, eax
0x1400024c2  call    cs:__imp_PsGetThreadProcess
0x1400024c9  nop     dword ptr [rax+rax+00h]
0x1400024ce  mov     dword ptr [rsp+0E0h+var_B8], 0
0x1400024d6  mov     r9d, r12d
0x1400024d9  mov     rcx, rax
0x1400024dc  mov     dword ptr [rsp+0E0h+BugCheckParameter4], r15d
0x1400024e1  mov     r8d, ebx
0x1400024e4  mov     edx, edi
0x1400024e6  call    cs:__imp_PsUpdateDiskCounters
0x1400024ed  nop     dword ptr [rax+rax+00h]
0x1400024f2  mov     r12, [rbp+57h+arg_10]
0x1400024f6  mov     ebx, [rbp+57h+var_A8]
0x1400024f9  mov     r15, [rbp+57h+arg_8]
0x1400024fd  mov     edi, [rbp+57h+var_B0]
0x140002500  cmp     edi, r14d
0x140002503  jb      short loc_140002583
0x140002505  mov     rdx, [rsi+0B8h]
0x14000250c  lea     rcx, FatPagingFileCompletionRoutine
0x140002513  mov     al, [r12]
0x140002517  or      byte ptr [rdx-46h], 2
0x14000251b  mov     [rdx-48h], al
0x14000251e  mov     rax, [rbp+57h+var_98]
0x140002522  mov     [rdx-30h], rax
0x140002526  mov     [rdx-40h], r14d
0x14000252a  mov     rdx, rsi; Irp
0x14000252d  mov     rax, [rsi+0B8h]
0x140002534  mov     [rax-10h], rcx
0x140002538  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x14000253c  mov     [rax-8], rsi
0x140002540  mov     byte ptr [rax-45h], 0A0h
0x140002544  call    cs:__imp_IofCallDriver
0x14000254b  nop     dword ptr [rax+rax+00h]
0x140002550  cmp     cs:FatDiskAccountingEnabled, 0
0x140002557  jz      loc_1400028E5
0x14000255d  cmp     [rbp+57h+arg_18], 4
0x140002561  jnz     short loc_14000256B
0x140002563  mov     eax, r14d
0x140002566  xor     r14d, r14d
0x140002569  jmp     short loc_14000256D
0x14000256b  xor     eax, eax
0x14000256d  mov     edx, eax
0x14000256f  mov     ecx, r14d
0x140002572  call    cs:__imp_FsRtlUpdateDiskCounters
0x140002579  nop     dword ptr [rax+rax+00h]
0x14000257e  jmp     loc_1400028E5
0x140002583  mov     rcx, [r15+0B8h]
0x14000258a  lea     rax, [rbp+57h+var_AC]
0x14000258e  mov     [rsp+0E0h+var_B8], rax
0x140002593  lea     r9, [rbp+57h+TargetMdl]
0x140002597  lea     rax, [rbp+57h+arg_0]
0x14000259b  dec     ebx
0x14000259d  add     ebx, r14d
0x1400025a0  mov     [rsp+0E0h+BugCheckParameter4], rax
0x1400025a5  mov     r8d, ebx
0x1400025a8  mov     rdx, r13
0x1400025ab  call    FatLookupMcbEntry
0x1400025b0  test    al, al
0x1400025b2  jnz     short loc_1400025DB
0x1400025b4  mov     ecx, 23h ; '#'; BugCheckCode
0x1400025b9  mov     r8d, ebx; BugCheckParameter2
0x1400025bc  mov     edx, 801EEh; BugCheckParameter1
0x1400025c1  mov     [rsp+0E0h+BugCheckParameter4], 0; BugCheckParameter4
0x1400025ca  lea     r9d, [rcx-22h]; BugCheckParameter3
0x1400025ce  call    cs:__imp_KeBugCheckEx
0x1400025db  mov     r13d, [rbp+57h+var_90]
0x1400025df  xor     edx, edx
0x1400025e1  mov     ebx, [rbp+57h+var_AC]
0x1400025e4  sub     ebx, r13d
0x1400025e7  mov     byte ptr [rbp+57h+arg_10], 0
0x1400025eb  inc     ebx
0x1400025ed  mov     byte ptr [rbp+57h+arg_0], 0
0x1400025f1  mov     [rbp+57h+var_A4], edx
0x1400025f4  mov     [rsi+30h], edx
0x1400025f7  mov     [rsi+38h], r14
0x1400025fb  mov     [rsi+18h], ebx
0x1400025fe  cmp     r13d, [rbp+57h+var_AC]
0x140002602  ja      loc_1400028B2
0x140002608  mov     rax, [rbp+57h+var_98]
0x14000260c  mov     [rbp+57h+var_80], rax
0x140002610  mov     ecx, edx
0x140002612  cmp     edi, r14d
0x140002615  cmova   edi, r14d
0x140002619  add     rcx, [rsi+70h]; VirtualAddress
0x14000261d  mov     r15d, edi
0x140002620  mov     [rbp+57h+var_B0], edi
0x140002623  xor     edi, edi
0x140002625  mov     edx, r15d; Length
0x140002628  xor     r9d, r9d; ChargeQuota
0x14000262b  mov     [rbp+57h+var_A0], edi
0x14000262e  xor     r8d, r8d; SecondaryBuffer
0x140002631  mov     [rsp+0E0h+BugCheckParameter4], rdi; Irp
0x140002636  call    cs:__imp_IoAllocateMdl
0x14000263d  nop     dword ptr [rax+rax+00h]
0x140002642  mov     [rbp+57h+TargetMdl], rax
0x140002646  test    rax, rax
0x140002649  jnz     short loc_140002694
0x14000264b  xor     r9d, r9d; Alertable
0x14000264e  mov     [rsp+0E0h+BugCheckParameter4], rdi; Timeout
0x140002653  xor     r8d, r8d; WaitMode
0x140002656  lea     rcx, FatReserveEvent; Object
0x14000265d  xor     edx, edx; WaitReason
0x14000265f  call    cs:__imp_KeWaitForSingleObject
0x140002666  nop     dword ptr [rax+rax+00h]
0x14000266b  mov     rax, cs:FatReserveMdl
0x140002672  mov     [rbp+57h+TargetMdl], rax
0x140002676  mov     eax, 10000h
0x14000267b  mov     byte ptr [rbp+57h+arg_10], 1
0x14000267f  cmp     r15d, eax
0x140002682  jbe     short loc_140002694
0x140002684  lea     edi, [r15-10000h]
0x14000268b  mov     [rbp+57h+var_B0], eax
0x14000268e  mov     [rbp+57h+var_A0], edi
0x140002691  mov     r15d, eax
0x140002694  mov     r8d, [rbp+57h+var_A4]
0x140002698  mov     r9d, r15d; Length
0x14000269b  add     r8, [rsi+70h]; VirtualAddress
0x14000269f  mov     rdx, [rbp+57h+TargetMdl]; TargetMdl
0x1400026a3  mov     rcx, [rsi+8]; SourceMdl
0x1400026a7  call    cs:__imp_IoBuildPartialMdl
0x1400026ae  nop     dword ptr [rax+rax+00h]
0x1400026b3  cmp     byte ptr [rbp+57h+arg_10], 0
0x1400026b7  jnz     short loc_140002735
0x1400026b9  cmp     ebx, 1
0x1400026bc  jnz     short loc_1400026C8
0x1400026be  cmp     r13d, [rbp+57h+var_AC]
0x1400026c2  jnz     short loc_140002735
0x1400026c4  test    edi, edi
0x1400026c6  jnz     short loc_140002735
0x1400026c8  mov     rax, [rbp+57h+DeviceObject]
0x1400026cc  mov     rcx, rsi; Irp
0x1400026cf  mov     dl, [rax+4Ch]
0x1400026d2  inc     dl; StackSize
0x1400026d4  call    cs:__imp_IoMakeAssociatedIrp
0x1400026db  nop     dword ptr [rax+rax+00h]
0x1400026e0  mov     rdi, rax
0x1400026e3  test    rax, rax
0x1400026e6  jz      short loc_140002735
0x1400026e8  dec     ebx
0x1400026ea  cmp     byte ptr [rbp+57h+arg_0], 0
0x1400026ee  jnz     short loc_14000274B
0x1400026f0  dec     byte ptr [rax+43h]
0x1400026f3  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400026fb  mov     rdx, [rax+0B8h]
0x140002702  mov     cl, [r12]
0x140002706  mov     eax, [rbp+57h+var_A8]
0x140002709  mov     [rdx], cl
0x14000270b  mov     [rdx+8], r15d
0x14000270f  mov     [rdx+18h], rax
0x140002713  mov     rax, [r12+28h]
0x140002718  mov     [rdx+28h], rax
0x14000271c  jmp     short loc_14000276A
0x14000271e  lea     r8, Fat30Milliseconds; Interval
0x140002725  xor     edx, edx; Alertable
0x140002727  xor     ecx, ecx; WaitMode
0x140002729  call    cs:__imp_KeDelayExecutionThread
0x140002730  nop     dword ptr [rax+rax+00h]
0x140002735  cmp     [rsi+18h], ebx
0x140002738  jnz     short loc_14000271E
0x14000273a  cmp     dword ptr [rsi+30h], 0
0x14000273e  jl      loc_1400028B2
0x140002744  mov     rdi, rsi
0x140002747  mov     byte ptr [rbp+57h+arg_0], 1
0x14000274b  xor     r8d, r8d; State
0x14000274e  lea     rcx, [rbp+57h+Event]; Event
0x140002752  lea     edx, [r8+1]; Type
0x140002756  call    cs:__imp_KeInitializeEvent
0x14000275d  nop     dword ptr [rax+rax+00h]
0x140002762  mov     rax, [rsi+8]
0x140002766  mov     qword ptr [rbp+57h+Event+18h], rax
0x14000276a  cmp     byte ptr [rbp+57h+arg_0], 0
0x14000276e  mov     rax, [rbp+57h+TargetMdl]
0x140002772  mov     [rdi+8], rax
0x140002776  mov     rax, [rdi+0B8h]
0x14000277d  jz      short loc_14000278F
0x14000277f  mov     r8b, 0E0h
0x140002782  lea     r9, [rbp+57h+Event]
0x140002786  lea     r10, FatPagingFileCompletionRoutineCatch
0x14000278d  jmp     short loc_14000279C
0x14000278f  mov     r8b, 0A0h
0x140002792  lea     r10, FatPagingFileCompletionRoutine
0x140002799  mov     r9, rsi
0x14000279c  mov     [rax-10h], r10
0x1400027a0  mov     rdx, rdi; Irp
0x1400027a3  mov     [rax-8], r9
0x1400027a7  mov     [rax-45h], r8b
0x1400027ab  mov     rcx, [rdi+0B8h]
0x1400027b2  or      byte ptr [rcx-46h], 2
0x1400027b6  mov     al, [r12]
0x1400027ba  mov     [rcx-48h], al
0x1400027bd  mov     rax, [rbp+57h+var_80]
0x1400027c1  mov     [rcx-30h], rax
0x1400027c5  mov     [rcx-40h], r15d
0x1400027c9  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x1400027cd  call    cs:__imp_IofCallDriver
0x1400027d4  nop     dword ptr [rax+rax+00h]
0x1400027d9  cmp     cs:FatDiskAccountingEnabled, 0
0x1400027e0  jz      short loc_140002800
0x1400027e2  cmp     [rbp+57h+arg_18], 4
0x1400027e6  jnz     short loc_1400027EF
0x1400027e8  mov     edx, r15d
0x1400027eb  xor     ecx, ecx
0x1400027ed  jmp     short loc_1400027F4
0x1400027ef  xor     edx, edx
0x1400027f1  mov     ecx, r15d
0x1400027f4  call    cs:__imp_FsRtlUpdateDiskCounters
0x1400027fb  nop     dword ptr [rax+rax+00h]
0x140002800  cmp     byte ptr [rbp+57h+arg_0], 0
0x140002804  jz      short loc_140002839
0x140002806  xor     r9d, r9d; Alertable
0x140002809  mov     [rsp+0E0h+BugCheckParameter4], 0; Timeout
0x140002812  xor     r8d, r8d; WaitMode
0x140002815  lea     rcx, [rbp+57h+Event]; Object
0x140002819  xor     edx, edx; WaitReason
0x14000281b  call    cs:__imp_KeWaitForSingleObject
0x140002822  nop     dword ptr [rax+rax+00h]
0x140002827  cmp     dword ptr [rsi+30h], 0
0x14000282b  jl      loc_1400028B2
0x140002831  mov     byte ptr [rbp+57h+arg_10], 0
0x140002835  mov     byte ptr [rbp+57h+arg_0], 0
0x140002839  mov     edx, [rbp+57h+var_A4]
0x14000283c  sub     r14d, r15d
0x14000283f  add     [rbp+57h+var_A8], r15d
0x140002843  add     edx, r15d
0x140002846  mov     edi, [rbp+57h+var_A0]
0x140002849  mov     [rbp+57h+var_A4], edx
0x14000284c  test    edi, edi
0x14000284e  jz      short loc_140002864
0x140002850  mov     rcx, [rbp+57h+var_80]
0x140002854  mov     eax, r15d
0x140002857  add     rcx, rax
0x14000285a  mov     [rbp+57h+var_80], rcx
0x14000285e  mov     [rbp+57h+var_98], rcx
  ... truncated ...
```
