# RefsMinstoreRead

- ea: `0x140041280`
- end: `0x140041a2f`
- name: `RefsMinstoreRead`
- size: `1967`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, struct REFS_IO_CONTEXT *@<rdx>, struct _IRP *@<r8>, unsigned __int64 LowLimit)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x14003b3f0`

## callees

- `0x140012b18`
- `0x140041280`
- `0x140041b40`
- `0x140042af0`
- `0x140042e50`
- `0x1400531a0`
- `0x140054950`
- `0x140054b90`
- `0x140081670`
- `0x14008dbd0`
- `0x1400ca788`
- `0x1400e2e8c`
- `0x1400e39dc`
- `0x1400ec738`
- `0x1401154f0`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400417b8`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400417b8`
- `ntoskrnl!IofCompleteRequest` at `0x14004177c`
- `ntoskrnl!IofCompleteRequest` at `0x14004177c`
- `ntoskrnl!IoGetStackLimits` at `0x140041434`
- `ntoskrnl!IoGetStackLimits` at `0x140041434`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400416a0`
- `ntoskrnl!IoGetCurrentProcess` at `0x1401f2374`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400416a0`
- `ntoskrnl!IoGetCurrentProcess` at `0x1401f2374`
- `ntoskrnl!DbgPrintEx` at `0x1400419cb`
- `ntoskrnl!DbgPrintEx` at `0x1400419cb`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400416bc`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400416bc`
- `ntoskrnl!_strnicmp` at `0x1401f239f`
- `ntoskrnl!_strnicmp` at `0x1401f239f`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401f2383`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401f2383`
- `ntoskrnl!IofCallDriver` at `0x14004145a`
- `ntoskrnl!IofCallDriver` at `0x14004145a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140041721`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140041721`
- `ntoskrnl!KeWaitForSingleObject` at `0x140041489`
- `ntoskrnl!KeWaitForSingleObject` at `0x140041489`
- `ntoskrnl!KeInitializeEvent` at `0x1400413ac`
- `ntoskrnl!KeInitializeEvent` at `0x1400413ac`

## string_xrefs

- `0x1400412c4`: `Read.c`
- `0x14004159c`: `Read.c`
- `0x14004187b`: `Read.c`
- `0x1401f23cf`: `Read.c`

## pseudocode

```c
__int64 __fastcall RefsMinstoreRead(
        struct _IRP_CONTEXT *a1,
        struct REFS_IO_CONTEXT *a2,
        struct _IRP *a3,
        int a4,
        char *LowLimit)
{
  int v8; // eax
  unsigned __int64 v9; // rsi
  struct _VCB **v10; // r15
  __int64 v11; // rcx
  __int64 v12; // r13
  __int64 v13; // r8
  int Status; // ebx
  unsigned int v15; // r8d
  ULONG_PTR v16; // r13
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *p_CurrentStackLocation; // rdx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  UCHAR MajorFunction; // al
  bool v20; // zf
  struct _IO_STACK_LOCATION *v21; // rax
  NTSTATUS v22; // eax
  unsigned int v23; // ecx
  __int64 v24; // rax
  volatile unsigned int v25; // edi
  __int64 v27; // rcx
  struct _KPROCESS *v28; // rdi
  ULONG Priority; // r8d
  struct CmsTransactionContext *v30; // r10
  PMDL MdlAddress; // rcx
  PVOID v32; // rax
  PVOID MappedSystemVa; // rbx
  __int64 v34; // rdx
  NTSTATUS v35; // eax
  int TransactionContext; // eax
  unsigned int v37; // eax
  int v38; // ecx
  int CompressedContainerRange; // eax
  PEPROCESS CurrentProcess; // rax
  const char *ProcessImageFileName; // rax
  unsigned __int64 v42; // [rsp+30h] [rbp-A1h]
  char v43; // [rsp+50h] [rbp-81h] BYREF
  unsigned int v44; // [rsp+54h] [rbp-7Dh] BYREF
  int *v45; // [rsp+58h] [rbp-79h]
  unsigned int v46; // [rsp+60h] [rbp-71h]
  PVOID Context; // [rsp+68h] [rbp-69h] BYREF
  struct CmsTransactionContext *v48; // [rsp+70h] [rbp-61h] BYREF
  struct _FCB *v49; // [rsp+78h] [rbp-59h]
  LARGE_INTEGER v50; // [rsp+80h] [rbp-51h] BYREF
  __int64 v51; // [rsp+88h] [rbp-49h] BYREF
  union SmsBigIdentifier *v52; // [rsp+90h] [rbp-41h] BYREF
  __int64 v53; // [rsp+98h] [rbp-39h]
  unsigned __int64 HighLimit; // [rsp+A0h] [rbp-31h] BYREF
  __int64 v55; // [rsp+A8h] [rbp-29h]
  struct _KEVENT Event; // [rsp+B0h] [rbp-21h] BYREF
  __int128 Parameter; // [rsp+C8h] [rbp-9h] BYREF
  __int128 v58; // [rsp+D8h] [rbp+7h]
  char v59; // [rsp+130h] [rbp+5Fh]

  v51 = 0;
  v8 = a4;
  v52 = 0;
  v50.QuadPart = 0;
  v44 = 0;
  memset(&Event, 0, sizeof(Event));
  v43 = 0;
  v48 = 0;
  if ( *((_QWORD *)a1 + 84) )
  {
    v9 = (unsigned __int64)LowLimit;
    v10 = (struct _VCB **)((char *)a1 + 64);
    v11 = *((_QWORD *)a1 + 8);
    v49 = 0;
    v46 = 0;
    v12 = *(_QWORD *)LowLimit;
    v59 = 0;
    v13 = *(_QWORD *)LowLimit;
    v55 = *(_QWORD *)LowLimit;
    v53 = v11;
    while ( 1 )
    {
      Status = MsConvertVboToLboPagingRead(
                 *((_QWORD *)a1 + 84),
                 v8,
                 v13,
                 *(_DWORD *)(v9 + 16),
                 (__int64)&v50,
                 (__int64)&v44,
                 (__int64)&v43,
                 (__int64)&v51,
                 (__int64)&v52,
                 (__int64)&v48);
      if ( Status < 0 )
        break;
      if ( !v59 )
      {
        if ( v51 )
        {
          v49 = (struct _FCB *)v51;
          if ( *(_WORD *)v51 != 2050 )
            v49 = *(struct _FCB **)(v51 + 136);
        }
        if ( (*(_DWORD *)(v53 + 28) & 2) != 0 )
          RefsInsertDebugInfoIrpImplementation(0, a3, 0, v49, v52, 0x6174654Du, v42);
        v59 = 1;
      }
      if ( *(_QWORD *)v9 != v12 )
      {
        Status = RefsAdvanceMdl(a1, a2, a3->MdlAddress, (unsigned int)*(_QWORD *)v9 - (unsigned int)v12);
        if ( Status < 0 )
          break;
      }
      KeInitializeEvent(&Event, SynchronizationEvent, 0);
      v16 = v44;
      p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&a3->Tail.Overlay.CurrentStackLocation;
      CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
      MajorFunction = CurrentStackLocation->MajorFunction;
      CurrentStackLocation[-1].Flags |= 2u;
      v20 = v43 == 0;
      CurrentStackLocation[-1].MajorFunction = MajorFunction;
      CurrentStackLocation[-1].Parameters.Read.ByteOffset = v50;
      CurrentStackLocation[-1].Parameters.Read.Length = v16;
      v21 = a3->Tail.Overlay.CurrentStackLocation;
      v21[-1].CompletionRoutine = RefsVerifyReadCompletionRoutine;
      v21[-1].Context = &Event;
      v21[-1].Control = -32;
      if ( v20 )
      {
        Context = RefsReserveStackStorage;
        Parameter = 0;
        v58 = 0;
        v16 = *(_QWORD *)(v53 + 192);
        HighLimit = 0;
        LowLimit = 0;
        IoGetStackLimits((PULONG_PTR)&LowLimit, &HighLimit);
        if ( (unsigned __int64)((char *)&HighLimit - LowLimit) <= 0x4800 )
        {
          *(_QWORD *)&Parameter = v16;
          *((_QWORD *)&Parameter + 1) = a3;
          v35 = KeExpandKernelStackAndCalloutEx(RefsStorageDriverCallout, &Parameter, 0x6000u, 0, Context);
          LODWORD(v16) = v44;
          if ( v35 >= 0 )
            Status = DWORD2(v58);
        }
        else
        {
          v22 = IofCallDriver((PDEVICE_OBJECT)v16, a3);
          LODWORD(v16) = v44;
          Status = v22;
        }
      }
      else
      {
        Priority = 1073741856;
        v30 = v48;
        MdlAddress = a3->MdlAddress;
        if ( (a3->Flags & 2) == 0 )
          Priority = 1073741840;
        v45 = (int *)v48;
        Context = v48;
        if ( MdlAddress )
        {
          if ( (MdlAddress->MdlFlags & 5) != 0 )
          {
            MappedSystemVa = MdlAddress->MappedSystemVa;
          }
          else
          {
            v32 = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, Priority);
            v30 = (struct CmsTransactionContext *)v45;
            MappedSystemVa = v32;
          }
          p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&a3->Tail.Overlay.CurrentStackLocation;
        }
        else
        {
          MappedSystemVa = a3->UserBuffer;
        }
        if ( MappedSystemVa )
        {
          if ( v48
            || (TransactionContext = MsCreateTransactionContext(
                                       (PSLIST_ENTRY *)&Context,
                                       *(_QWORD *)(MEMORY[0x90] + 112LL)),
                v30 = (struct CmsTransactionContext *)Context,
                v45 = (int *)Context,
                LODWORD(LowLimit) = TransactionContext,
                TransactionContext >= 0) )
          {
            CompressedContainerRange = MsReadCompressedContainerRange(v30);
            v30 = (struct CmsTransactionContext *)v45;
            LODWORD(LowLimit) = CompressedContainerRange;
          }
          p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&a3->Tail.Overlay.CurrentStackLocation;
        }
        else
        {
          LODWORD(LowLimit) = -1073741670;
        }
        --p_CurrentStackLocation->CurrentStackLocation;
        --a3->CurrentLocation;
        v20 = v48 == 0;
        v34 = (unsigned int)LowLimit;
        a3->IoStatus.Status = (int)LowLimit;
        if ( v20 && v30 )
        {
          if ( (int)v34 < 0 )
            MsAbortTransaction(v30);
          else
            MsCommitTransaction(v30, v34, 0);
          MsDeleteTransactionContext(v45);
          LODWORD(v34) = (_DWORD)LowLimit;
          v45 = (int *)&a3->IoStatus.0;
        }
        else
        {
          v45 = (int *)&a3->IoStatus.0;
        }
        if ( (int)v34 >= 0 )
          a3->IoStatus.Information = v16;
        else
          v45 = (int *)&a3->IoStatus.0;
        IofCompleteRequest(a3, 1);
        Status = *v45;
      }
      if ( Status == 259 )
      {
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        Status = a3->IoStatus.Status;
      }
      if ( *(_QWORD *)v9 == v55 )
      {
        if ( Status < 0 )
          break;
      }
      else
      {
        Status = RefsRestoreMdl(a1, a2, a3->MdlAddress, *(_QWORD *)v9 - v55);
        if ( Status < 0 )
          break;
      }
      v23 = v16 + v46;
      *(_QWORD *)v9 += (unsigned int)v16;
      v20 = *(_DWORD *)(v9 + 16) == (_DWORD)v16;
      *(_DWORD *)(v9 + 16) -= v16;
      v13 = *(_QWORD *)v9;
      v46 = v23;
      if ( v20 )
      {
        a3->IoStatus.Information = v23;
        goto LABEL_22;
      }
      v12 = v55;
      v8 = a4;
    }
    if ( Status == -1073741608 || Status == -1073741400 || Status == -1073741432 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
          (unsigned int)Status);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(Status, a1, "Read.c", 0x275u);
      RefsRaiseStatusInternal(a1, Status, v15);
      JUMPOUT(0x1401F23EALL);
    }
  }
  else
  {
    Status = -1073741808;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids, 3221225488LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741808, 0, "Read.c", 0x1E2u);
    v10 = (struct _VCB **)((char *)a1 + 64);
  }
LABEL_22:
  v24 = *((_QWORD *)a1 + 1);
  if ( (v24 & 0x100000000LL) != 0 )
  {
    *((_QWORD *)a1 + 1) = v24 | 0x200000000LL;
  }
  else
  {
    if ( Status >= 0 && *((_BYTE *)*v10 + 10496) && *((__int64 *)a1 + 86) > 23 )
    {
      RefsIoPerfCollectReadWriteData(*v10, a3, a1, a2);
      *((_QWORD *)a1 + 1) |= 0x8000uLL;
    }
    else
    {
      *((_QWORD *)a1 + 1) |= 0x8000uLL;
      if ( Status < 0 )
      {
        v37 = *((unsigned __int8 *)a1 + 40);
        if ( (unsigned __int8)v37 <= 0x12u )
        {
          v38 = 262685;
          if ( _bittest(&v38, v37) )
          {
            if ( *v10
              && *((_BYTE *)*v10 + 10496)
              && (*((_DWORD *)a1 + 1) & 0x400) == 0
              && (*((_DWORD *)a1 + 2) & 0x10000) == 0 )
            {
              *((_QWORD *)a1 + 86) = 7;
            }
          }
        }
      }
    }
    *((_DWORD *)a2 + 199) &= ~1u;
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, a3, Status);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
  {
    if ( Status < 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
LABEL_111:
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
          (unsigned int)Status);
    }
    else if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      goto LABEL_111;
    }
  }
  if ( (_BYTE)RefsStatusDebugEnabled && Status != 259 && Status != -1073741802 )
  {
    if ( RefsStatusDisplayStatus && RefsStatusDisplayStatus == Status )
      DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), Status, "Read.c", 633);
    v25 = RefsStatusBreakOnWin32Error;
    if ( RefsStatusBreakOnStatus && RefsStatusBreakOnStatus == Status
      || RefsStatusBreakOnWin32Error && v25 == RtlNtStatusToDosErrorNoTeb(Status) )
    {
      v28 = RefsStatusBreakForProcess;
      if ( !RefsStatusBreakForThread
        || RefsStatusBreakForThread == KeGetCurrentThread()
        && (!RefsStatusBreakForProcess || v28 == IoGetCurrentProcess())
        && (!RefsStatusBreakForImage
         || (CurrentProcess = IoGetCurrentProcess(),
             ProcessImageFileName = (const char *)PsGetProcessImageFileName(CurrentProcess),
             !_strnicmp(&RefsStatusBreakForImage, ProcessImageFileName, 0xFu))) )
      {
        __int2c();
      }
    }
    if ( Status && Status != -2147483643 )
    {
      v27 = 32LL
          * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
           & 0xFFF);
      *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v27) = KeGetCurrentThread();
      *(_DWORD *)((char *)&RefsStatusQueue + v27 + 8) = Status;
      *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v27 + 16) = (struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near *)"Read.c";
      *(_DWORD *)((char *)&RefsStatusQueue + v27 + 24) = 633;
    }
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140041280  mov     [rsp-8+arg_8], rbx
0x140041285  mov     [rsp-8+arg_18], r9
0x14004128a  push    rbp
0x14004128b  push    rsi
0x14004128c  push    rdi
0x14004128d  push    r12
0x14004128f  push    r13
0x140041291  push    r14
0x140041293  push    r15
0x140041295  lea     rbp, [rsp-1Fh]
0x14004129a  sub     rsp, 0F0h
0x1400412a1  mov     rdi, rcx
0x1400412a4  lea     r13, WPP_GLOBAL_Control
0x1400412ab  xor     ecx, ecx
0x1400412ad  mov     r14, r8
0x1400412b0  xor     r8d, r8d
0x1400412b3  mov     [rbp+4Fh+Event.Header.WaitListHead.Blink], rcx
0x1400412b7  xorps   xmm0, xmm0
0x1400412ba  mov     [rbp+4Fh+var_98], r8
0x1400412be  mov     r12, rdx
0x1400412c1  mov     rax, r9
0x1400412c4  lea     rdx, aReadC; "Read.c"
0x1400412cb  mov     [rbp+4Fh+var_90], r8
0x1400412cf  mov     esi, 1
0x1400412d4  mov     [rbp+4Fh+var_A0], r8
0x1400412d8  mov     dword ptr [rbp+4Fh+var_D0+4], r8d
0x1400412dc  movups  xmmword ptr [rbp+4Fh+Event.Header], xmm0
0x1400412e0  mov     byte ptr [rsp+120h+var_D0], cl
0x1400412e4  mov     [rbp+4Fh+var_B0], r8
0x1400412e8  cmp     [rdi+2A0h], rcx
0x1400412ef  jz      loc_140041837
0x1400412f5  mov     rsi, [rbp+4Fh+LowLimit]
0x1400412f9  lea     r15, [rdi+40h]
0x1400412fd  mov     rcx, [r15]
0x140041300  mov     [rbp+4Fh+var_A8], r8
0x140041304  mov     [rbp+4Fh+var_C0], r8d
0x140041308  mov     r13, [rsi]
0x14004130b  mov     [rbp+4Fh+arg_0], r8b
0x14004130f  mov     r8, r13
0x140041312  mov     [rbp+4Fh+var_78], r13
0x140041316  mov     [rbp+4Fh+var_88], rcx
0x14004131a  mov     r9d, [rsi+10h]
0x14004131e  lea     rcx, [rbp+4Fh+var_B0]
0x140041322  mov     [rsp+120h+var_D8], rcx
0x140041327  mov     rdx, rax
0x14004132a  lea     rcx, [rbp+4Fh+var_90]
0x14004132e  mov     [rsp+120h+var_E0], rcx
0x140041333  lea     rcx, [rbp+4Fh+var_98]
0x140041337  mov     [rsp+120h+var_E8], rcx
0x14004133c  lea     rcx, [rsp+120h+var_D0]
0x140041341  mov     [rsp+120h+var_F0], rcx; unsigned __int64
0x140041346  lea     rcx, [rbp+4Fh+var_D0+4]
0x14004134a  mov     qword ptr [rsp+120h+Priority], rcx
0x14004134f  lea     rcx, [rbp+4Fh+var_A0]
0x140041353  mov     [rsp+120h+Timeout], rcx
0x140041358  mov     rcx, [rdi+2A0h]
0x14004135f  call    MsConvertVboToLboPagingRead
0x140041364  mov     ebx, eax
0x140041366  test    eax, eax
0x140041368  js      loc_1400414D1
0x14004136e  cmp     [rbp+4Fh+arg_0], 0
0x140041372  jnz     short loc_140041394
0x140041374  mov     rax, [rbp+4Fh+var_98]
0x140041378  test    rax, rax
0x14004137b  jnz     loc_1400417F7
0x140041381  mov     rax, [rbp+4Fh+var_88]
0x140041385  mov     eax, [rax+1Ch]
0x140041388  test    al, 2
0x14004138a  jnz     loc_140041887
0x140041390  mov     [rbp+4Fh+arg_0], 1
0x140041394  mov     r9, [rsi]
0x140041397  cmp     r9, r13
0x14004139a  jnz     loc_1400418AF
0x1400413a0  xor     r8d, r8d; State
0x1400413a3  lea     rcx, [rbp+4Fh+Event]; Event
0x1400413a7  mov     edx, 1; Type
0x1400413ac  call    cs:__imp_KeInitializeEvent
0x1400413b3  nop     dword ptr [rax+rax+00h]
0x1400413b8  mov     r13d, dword ptr [rbp+4Fh+var_D0+4]
0x1400413bc  lea     rdx, [r14+0B8h]
0x1400413c3  mov     rcx, [rdx]
0x1400413c6  movzx   eax, byte ptr [rcx]
0x1400413c9  or      byte ptr [rcx-46h], 2
0x1400413cd  cmp     byte ptr [rsp+120h+var_D0], 0
0x1400413d2  mov     [rcx-48h], al
0x1400413d5  mov     rax, [rbp+4Fh+var_A0]
0x1400413d9  mov     [rcx-30h], rax
0x1400413dd  mov     [rcx-40h], r13d
0x1400413e1  lea     rcx, ?RefsVerifyReadCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; RefsVerifyReadCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x1400413e8  mov     rax, [rdx]
0x1400413eb  mov     [rax-10h], rcx
0x1400413ef  lea     rcx, [rbp+4Fh+Event]
0x1400413f3  mov     [rax-8], rcx
0x1400413f7  mov     byte ptr [rax-45h], 0E0h
0x1400413fb  jnz     loc_1400416D1
0x140041401  mov     rax, cs:?RefsReserveStackStorage@@3PEAXEA; void * RefsReserveStackStorage
0x140041408  lea     rdx, [rbp+4Fh+HighLimit]; HighLimit
0x14004140c  mov     [rbp+4Fh+Context], rax
0x140041410  lea     rcx, [rbp+4Fh+LowLimit]; LowLimit
0x140041414  mov     rax, [rbp+4Fh+var_88]
0x140041418  xorps   xmm0, xmm0
0x14004141b  movups  [rbp+4Fh+Parameter], xmm0
0x14004141f  movups  [rbp+4Fh+var_48], xmm0
0x140041423  mov     r13, [rax+0C0h]
0x14004142a  xor     eax, eax
0x14004142c  mov     [rbp+4Fh+HighLimit], rax
0x140041430  mov     [rbp+4Fh+LowLimit], rax
0x140041434  call    cs:__imp_IoGetStackLimits
0x14004143b  nop     dword ptr [rax+rax+00h]
0x140041440  lea     rax, [rbp+4Fh+HighLimit]
0x140041444  sub     rax, [rbp+4Fh+LowLimit]
0x140041448  cmp     rax, 4800h
0x14004144e  jbe     loc_140041793
0x140041454  mov     rdx, r14; Irp
0x140041457  mov     rcx, r13; DeviceObject
0x14004145a  call    cs:__imp_IofCallDriver
0x140041461  nop     dword ptr [rax+rax+00h]
0x140041466  mov     r13d, dword ptr [rbp+4Fh+var_D0+4]
0x14004146a  mov     ebx, eax
0x14004146c  cmp     ebx, 103h
0x140041472  jnz     short loc_140041499
0x140041474  xor     r9d, r9d; Alertable
0x140041477  mov     [rsp+120h+Timeout], 0; Timeout
0x140041480  xor     r8d, r8d; WaitMode
0x140041483  lea     rcx, [rbp+4Fh+Event]; Object
0x140041487  xor     edx, edx; WaitReason
0x140041489  call    cs:__imp_KeWaitForSingleObject
0x140041490  nop     dword ptr [rax+rax+00h]
0x140041495  mov     ebx, [r14+30h]
0x140041499  mov     r9, [rsi]
0x14004149c  mov     rax, [rbp+4Fh+var_78]
0x1400414a0  cmp     r9, rax
0x1400414a3  jnz     loc_140041933
0x1400414a9  test    ebx, ebx
0x1400414ab  js      short loc_1400414D1
0x1400414ad  mov     ecx, [rbp+4Fh+var_C0]
0x1400414b0  add     ecx, r13d
0x1400414b3  mov     eax, r13d
0x1400414b6  add     [rsi], rax
0x1400414b9  sub     [rsi+10h], r13d
0x1400414bd  mov     r8, [rsi]
0x1400414c0  mov     [rbp+4Fh+var_C0], ecx
0x1400414c3  jnz     loc_1400417D8
0x1400414c9  mov     eax, ecx
0x1400414cb  mov     [r14+38h], rax
0x1400414cf  jmp     short loc_1400414F6
0x1400414d1  cmp     ebx, 0C00000D8h
0x1400414d7  jz      loc_1400419E3
0x1400414dd  mov     eax, ebx
0x1400414df  cmp     ebx, 0C00001A8h
0x1400414e5  jz      loc_1400419E3
0x1400414eb  cmp     eax, 0C0000188h
0x1400414f0  jz      loc_1400419E3
0x1400414f6  lea     r13, WPP_GLOBAL_Control
0x1400414fd  mov     esi, 1
0x140041502  mov     rax, [rdi+8]
0x140041506  bt      rax, 20h ; ' '
0x14004150b  jb      loc_140041650
0x140041511  test    ebx, ebx
0x140041513  js      short loc_140041548
0x140041515  mov     rax, [r15]
0x140041518  movzx   edx, byte ptr [rax+2900h]
0x14004151f  test    dl, dl
0x140041521  jz      short loc_140041548
0x140041523  cmp     qword ptr [rdi+2B0h], 17h
0x14004152b  jle     short loc_140041548
0x14004152d  mov     rcx, [r15]; struct _VCB *
0x140041530  mov     r9, r12; struct REFS_IO_CONTEXT *
0x140041533  mov     r8, rdi; struct _IRP_CONTEXT *
0x140041536  mov     rdx, r14; struct _IRP *
0x140041539  call    ?RefsIoPerfCollectReadWriteData@@YAXPEAU_VCB@@PEAU_IRP@@PEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@@Z; RefsIoPerfCollectReadWriteData(_VCB *,_IRP *,_IRP_CONTEXT *,REFS_IO_CONTEXT *)
0x14004153e  or      qword ptr [rdi+8], 8000h
0x140041546  jmp     short loc_140041558
0x140041548  or      qword ptr [rdi+8], 8000h
0x140041550  test    ebx, ebx
0x140041552  js      loc_140041954
0x140041558  and     dword ptr [r12+31Ch], 0FFFFFFFEh
0x140041561  mov     r8d, ebx; Status
0x140041564  mov     rdx, r14; Irp
0x140041567  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14004156a  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x14004156f  mov     rcx, cs:WPP_GLOBAL_Control
0x140041576  cmp     rcx, r13
0x140041579  jnz     short loc_1400415E9
0x14004157b  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140041582  test    al, al
0x140041584  jz      short loc_1400415CB
0x140041586  cmp     ebx, 103h
0x14004158c  jz      short loc_1400415CB
0x14004158e  cmp     ebx, 0C0000016h
0x140041594  jz      short loc_1400415CB
0x140041596  mov     eax, cs:?RefsStatusDisplayStatus@@3JC; long volatile RefsStatusDisplayStatus
0x14004159c  lea     r14, aReadC; "Read.c"
0x1400415a3  test    eax, eax
0x1400415a5  jnz     loc_14004199B
0x1400415ab  mov     eax, cs:?RefsStatusBreakOnStatus@@3JC; long volatile RefsStatusBreakOnStatus
0x1400415b1  mov     edi, cs:?RefsStatusBreakOnWin32Error@@3KC; ulong volatile RefsStatusBreakOnWin32Error
0x1400415b7  test    eax, eax
0x1400415b9  jnz     loc_140041666
0x1400415bf  test    edi, edi
0x1400415c1  jnz     loc_1400416BA
0x1400415c7  test    ebx, ebx
0x1400415c9  jnz     short loc_140041609
0x1400415cb  mov     eax, ebx
0x1400415cd  mov     rbx, [rsp+120h+arg_8]
0x1400415d5  add     rsp, 0F0h
0x1400415dc  pop     r15
0x1400415de  pop     r14
0x1400415e0  pop     r13
0x1400415e2  pop     r12
0x1400415e4  pop     rdi
0x1400415e5  pop     rsi
0x1400415e6  pop     rbp
0x1400415e7  retn
0x1400415e9  test    dword ptr [rcx+2Ch], 100h
0x1400415f0  jz      short loc_14004157B
0x1400415f2  test    ebx, ebx
0x1400415f4  js      loc_1401F2343
0x1400415fa  cmp     byte ptr [rcx+29h], 5
0x1400415fe  jb      loc_14004157B
0x140041604  jmp     loc_1401F234D
0x140041609  cmp     ebx, 80000005h
0x14004160f  jz      short loc_1400415CB
0x140041611  lock xadd cs:?RefsStatusNextQueueEntry@@3KA, esi; ulong RefsStatusNextQueueEntry
0x140041619  mov     rax, gs:188h
0x140041622  lea     rdx, ?RefsStatusQueue@@3PAU_REFS_STATUS_DEBUG_QUEUE_ENTRY@@A; _REFS_STATUS_DEBUG_QUEUE_ENTRY near * RefsStatusQueue
0x140041629  lea     ecx, [rsi+1]
0x14004162c  and     ecx, 0FFFh
0x140041632  shl     rcx, 5
0x140041636  mov     [rcx+rdx], rax
0x14004163a  mov     [rcx+rdx+8], ebx
0x14004163e  mov     [rcx+rdx+10h], r14
0x140041643  mov     dword ptr [rcx+rdx+18h], 279h
0x14004164b  jmp     loc_1400415CB
0x140041650  mov     rcx, 200000000h
0x14004165a  or      rax, rcx
0x14004165d  mov     [rdi+8], rax
0x140041661  jmp     loc_14004156F
0x140041666  cmp     eax, ebx
0x140041668  jnz     loc_1400415BF
0x14004166e  mov     rcx, cs:?RefsStatusBreakForThread@@3REAU_KTHREAD@@EA; _KTHREAD * RefsStatusBreakForThread
0x140041675  mov     rdi, cs:?RefsStatusBreakForProcess@@3REAU_KPROCESS@@EA; _KPROCESS * RefsStatusBreakForProcess
0x14004167c  test    rcx, rcx
0x14004167f  jz      loc_1400419DC
0x140041685  mov     rax, gs:188h
0x14004168e  cmp     rcx, rax
0x140041691  jnz     loc_1400415C7
0x140041697  test    rdi, rdi
0x14004169a  jz      loc_1401F236B
0x1400416a0  call    cs:__imp_IoGetCurrentProcess
0x1400416a7  nop     dword ptr [rax+rax+00h]
0x1400416ac  cmp     rdi, rax
0x1400416af  jnz     loc_1400415C7
0x1400416b5  jmp     loc_1401F236B
0x1400416ba  mov     ecx, ebx; Status
0x1400416bc  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1400416c3  nop     dword ptr [rax+rax+00h]
0x1400416c8  cmp     edi, eax
0x1400416ca  jz      short loc_14004166E
0x1400416cc  jmp     loc_1400415C7
0x1400416d1  mov     eax, [r14+10h]
0x1400416d5  mov     r8d, 40000020h
0x1400416db  mov     r10, [rbp+4Fh+var_B0]
0x1400416df  test    al, 2
0x1400416e1  mov     rcx, [r14+8]; MemoryDescriptorList
0x1400416e5  mov     eax, 40000010h
0x1400416ea  cmovz   r8d, eax
0x1400416ee  mov     [rbp+4Fh+var_C8], r10
0x1400416f2  mov     [rbp+4Fh+Context], r10
0x1400416f6  test    rcx, rcx
0x1400416f9  jz      loc_1400417E5
0x1400416ff  test    byte ptr [rcx+0Ah], 5
0x140041703  jnz     loc_1400417EE
0x140041709  mov     [rsp+120h+Priority], r8d; Priority
0x14004170e  xor     r9d, r9d; RequestedAddress
0x140041711  mov     r8d, 1; CacheType
0x140041717  mov     dword ptr [rsp+120h+Timeout], 0; BugCheckOnFailure
0x14004171f  xor     edx, edx; AccessMode
0x140041721  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140041728  nop     dword ptr [rax+rax+00h]
0x14004172d  mov     r10, [rbp+4Fh+var_C8]
0x140041731  mov     rbx, rax
0x140041734  lea     rdx, [r14+0B8h]
0x14004173b  test    rbx, rbx
0x14004173e  jnz     loc_1400418D0
0x140041744  mov     dword ptr [rbp+4Fh+LowLimit], 0C000009Ah
0x14004174b  add     qword ptr [rdx], 0FFFFFFFFFFFFFFB8h
0x14004174f  lea     rbx, [r14+30h]
0x140041753  dec     byte ptr [r14+43h]
0x140041757  cmp     [rbp+4Fh+var_B0], 0
0x14004175c  mov     edx, dword ptr [rbp+4Fh+LowLimit]
0x14004175f  mov     [rbx], edx
0x140041761  jz      loc_140041908
0x140041767  mov     [rbp+4Fh+var_C8], rbx
0x14004176b  test    edx, edx
0x14004176d  jns     loc_14004192A
0x140041773  mov     [rbp+4Fh+var_C8], rbx
0x140041777  mov     dl, 1; PriorityBoost
0x140041779  mov     rcx, r14; Irp
0x14004177c  call    cs:__imp_IofCompleteRequest
  ... truncated ...
```
