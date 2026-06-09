# RxProcessBatchedRead

- ea: `0x14004aeb4`
- end: `0x14004b36a`
- name: `RxProcessBatchedRead`
- size: `1206`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP, PFCB Fcb)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140045410`

## callees

- `0x140008030`
- `0x140008190`
- `0x140009b80`
- `0x140017220`
- `0x140017280`
- `0x140017370`
- `0x14001810c`
- `0x14004adc0`
- `0x14004aeb4`
- `0x14004b9b0`
- `0x14004baf4`
- `0x14004bbf8`
- `0x14004bca0`
- `0x140057660`
- `0x140067ad0`
- `0x140069970`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004b2f8`
- `ntoskrnl!ExAllocatePool2` at `0x14004b2f8`
- `ntoskrnl!FsRtlCheckOplock` at `0x14004b111`
- `ntoskrnl!FsRtlCheckOplock` at `0x14004b111`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14004b1e7`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14004b1e7`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x14004b127`

## pseudocode

```c
__int64 __fastcall RxProcessBatchedRead(PRX_CONTEXT RxContext, PIRP a2, PFCB Fcb)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  struct _IRP *Parameters; // r15
  char v8; // r13
  int Status; // ebx
  unsigned int Options; // r8d
  PVOID *p_EaBuffer; // r12
  unsigned __int64 v13; // rax
  ULONG v14; // ecx
  ULONG Length; // eax
  NTSTATUS v16; // eax
  __int64 v17; // r8
  PDEVICE_OBJECT v18; // rcx
  const CHAR *v19; // r9
  PFILE_OBJECT v20; // r10
  char v21; // r12
  ULONG *v22; // rbx
  unsigned int i; // ebp
  __int64 v24; // rax
  __int64 Pool2; // rax
  NTSTATUS v26; // eax
  const CHAR *PostIrpRoutine; // [rsp+20h] [rbp-58h]
  ULONG PostIrpRoutinea; // [rsp+20h] [rbp-58h]
  ULONG v29; // [rsp+28h] [rbp-50h]
  unsigned int *p_Flags; // [rsp+30h] [rbp-48h]
  ULONG v31; // [rsp+80h] [rbp+8h]
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp+10h]
  LARGE_INTEGER FileOffset; // [rsp+98h] [rbp+20h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 1327699 )
  {
    Parameters = (struct _IRP *)CurrentStackLocation->Parameters.CreatePipe.Parameters;
    v8 = 1;
  }
  else
  {
    Parameters = a2->AssociatedIrp.MasterIrp;
    v8 = 0;
  }
  FileObject = CurrentStackLocation->FileObject;
  FileOffset.QuadPart = 0;
  if ( !v8 || !a2->RequestorMode )
  {
    Options = CurrentStackLocation->Parameters.Create.Options;
    *((_DWORD *)&RxContext->9 + 29) = 0;
    p_EaBuffer = &RxContext->Create.EaBuffer;
    *((_DWORD *)&RxContext->9 + 28) = 0;
    if ( Options < 0x38 )
    {
      Status = -1073741811;
      goto LABEL_9;
    }
    if ( *(_DWORD *)&Parameters->Type != 1 )
    {
      Status = -1073741736;
      goto LABEL_9;
    }
    p_Flags = &Parameters->Flags;
    Status = RxpValidateBatchedRequest(
               (_DWORD *)&RxContext->9 + 29,
               (_DWORD *)&RxContext->9 + 28,
               Options,
               (int *)&Parameters->Flags);
    if ( Status >= 0 )
    {
      if ( (int)RxpValidateBatchedRead(&Parameters->Flags, *((_DWORD *)&RxContext->9 + 29)) < 0 )
      {
        Status = -1073741811;
        goto LABEL_10;
      }
      v13 = 16LL * *(unsigned int *)p_EaBuffer;
      if ( v13 > 0xFFFFFFFF )
      {
        Status = -1073740685;
        goto LABEL_10;
      }
      v14 = v13 + 8;
      Length = CurrentStackLocation->Parameters.Read.Length;
      v31 = v14;
      if ( Length && Length < v14 )
      {
        Status = -1073741789;
        goto LABEL_10;
      }
      if ( Fcb->Header.NodeTypeCode != -5086 )
      {
        Status = -1073741808;
        goto LABEL_10;
      }
      v16 = _RxAcquireFcb(Fcb, RxContext, 1u, 0, PostIrpRoutine, v29);
      Status = v16;
      if ( v16 < 0 )
      {
        if ( v16 == -1073741739 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, &WPP_08739a57919f3523a69f175bfdb02181_Traceguids);
          }
          BYTE3(RxContext->RealDevice) = 1;
        }
        goto LABEL_10;
      }
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqq(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          &WPP_08739a57919f3523a69f175bfdb02181_Traceguids,
          RxContext,
          Fcb,
          FileObject);
      }
      if ( (*(_DWORD *)(&Parameters->Size + 1) & 1) == 0 )
      {
        Status = FsRtlCheckOplock((POPLOCK)&Fcb->pNetRoot, a2, RxContext, RxUpperOplockBreakCompleteAsync, RxPrePostIrp);
        if ( Status )
          goto LABEL_65;
        Status = RxCheckByteRangeLocks(a2, (__int64)FsRtlFastCheckLockForRead);
        if ( Status )
          goto LABEL_65;
      }
      v20 = FileObject;
      v21 = 0;
      if ( FileObject->SectionObjectPointer->DataSectionObject )
      {
        v21 = 1;
        LOBYTE(v17) = 1;
        RxAcquirePagingIoResource(RxContext, Fcb, v17);
        if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
          McTemplateK0p_EtwWriteTransfer(v18, &CcPurgeRequest, &RxContext->LowIoContext.Flags + 1, Fcb);
        v20 = FileObject;
      }
      v22 = &Parameters->Flags;
LABEL_46:
      if ( v22 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= v22[2] )
          {
            v24 = *v22;
            if ( (_DWORD)v24 )
              v22 = (ULONG *)((char *)v22 + v24);
            else
              v22 = 0;
            goto LABEL_46;
          }
          FileOffset = *(LARGE_INTEGER *)&v22[4 * i + 6];
          if ( v21 )
          {
            CcCoherencyFlushAndPurgeCache(v20->SectionObjectPointer, &FileOffset, v22[4 * i + 9], &a2->IoStatus, 3u);
            if ( a2->IoStatus.Status < 0 )
              break;
          }
          v20 = FileObject;
        }
        if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
          McTemplateK0p_EtwWriteTransfer(v18, &CcPurgeCompletion, &RxContext->LowIoContext.Flags + 1, Fcb);
        RxReleasePagingIoResource(RxContext, Fcb);
        Status = a2->IoStatus.Status;
        goto LABEL_65;
      }
      if ( v21 )
      {
        if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
          McTemplateK0p_EtwWriteTransfer(v18, &CcPurgeCompletion, &RxContext->LowIoContext.Flags + 1, Fcb);
        RxReleasePagingIoResource(RxContext, Fcb);
      }
      if ( ((__int64)RxContext->RdbssDbgExtension & 0x200) != 0 || v8 )
      {
        RxpAssertBatchedBuffersLocked((__int64)a2, p_Flags, *((_DWORD *)&RxContext->9 + 29), v8);
      }
      else
      {
        Status = RxpProbeAndLockBatchedBuffers(a2, p_Flags, *((_DWORD *)&RxContext->9 + 29), IoWriteAccess);
        if ( Status < 0 )
        {
LABEL_65:
          _RxReleaseFcb(RxContext, (PMRX_FCB)&Fcb->Header, v17, v19, PostIrpRoutinea);
          goto LABEL_9;
        }
      }
      _RxReleaseFcb(RxContext, (PMRX_FCB)&Fcb->Header, v17, v19, PostIrpRoutinea);
      RxInitializeLowIoContext(RxContext, 6u, (PLOWIO_CONTEXT)((char *)&RxContext->9 + 120));
      Pool2 = ExAllocatePool2(64, v31, 1916958802);
      *((_QWORD *)&RxContext->9 + 18) = Pool2;
      if ( !Pool2 )
      {
        Status = -1073741670;
        goto LABEL_10;
      }
      if ( !RxContext->LockManagerContext && (a2->Flags & 2) == 0 )
        *((_WORD *)&RxContext->9 + 61) |= 8u;
      v26 = RxLowIoSubmit(RxContext, a2, Fcb, RxLowIoFsCtlShellCompletion);
      Status = v26;
      if ( v26 != 259 )
      {
        if ( v26 >= 0 )
          return (unsigned int)Status;
        goto LABEL_10;
      }
    }
LABEL_9:
    if ( Status >= 0 )
      return (unsigned int)Status;
    goto LABEL_10;
  }
  __int2c();
  Status = -1073741790;
LABEL_10:
  if ( !BYTE3(RxContext->RealDevice)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 15, &WPP_08739a57919f3523a69f175bfdb02181_Traceguids);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14004aeb4  mov     [rsp+arg_10], rbx
0x14004aeb9  push    rbp
0x14004aeba  push    rsi
0x14004aebb  push    rdi
0x14004aebc  push    r12
0x14004aebe  push    r13
0x14004aec0  push    r14
0x14004aec2  push    r15
0x14004aec4  sub     rsp, 40h
0x14004aec8  mov     rbp, [rdx+0B8h]
0x14004aecf  mov     rdi, rcx
0x14004aed2  xor     ecx, ecx
0x14004aed4  mov     rsi, r8
0x14004aed7  mov     r14, rdx
0x14004aeda  cmp     dword ptr [rbp+18h], 144253h
0x14004aee1  jnz     short loc_14004AEEC
0x14004aee3  mov     r15, [rbp+20h]
0x14004aee7  mov     r13b, 1
0x14004aeea  jmp     short loc_14004AEF3
0x14004aeec  mov     r15, [rdx+18h]
0x14004aef0  mov     r13b, cl
0x14004aef3  mov     rax, [rbp+30h]
0x14004aef7  mov     [rsp+78h+arg_8], rax
0x14004aeff  lea     rax, WPP_GLOBAL_Control
0x14004af06  mov     qword ptr [rsp+78h+FileOffset], rcx
0x14004af0e  test    r13b, r13b
0x14004af11  jz      short loc_14004AF21
0x14004af13  cmp     [rdx+40h], cl
0x14004af16  jz      short loc_14004AF21
0x14004af18  int     2Ch; Windows NT - assertion failure
0x14004af1a  mov     ebx, 0C0000022h
0x14004af1f  jmp     short loc_14004AF4F
0x14004af21  mov     r8d, [rbp+10h]
0x14004af25  lea     rax, [rdi+204h]
0x14004af2c  mov     [rax], ecx
0x14004af2e  lea     r12, [rdi+200h]
0x14004af35  mov     [r12], ecx
0x14004af39  cmp     r8d, 38h ; '8'
0x14004af3d  jnb     short loc_14004AFA5
0x14004af3f  mov     ebx, 0C000000Dh
0x14004af44  test    ebx, ebx
0x14004af46  jns     short loc_14004AF8A
0x14004af48  lea     rax, WPP_GLOBAL_Control
0x14004af4f  cmp     byte ptr [rdi+23h], 0
0x14004af53  jnz     short loc_14004AF8A
0x14004af55  mov     rcx, cs:WPP_GLOBAL_Control
0x14004af5c  cmp     rcx, rax
0x14004af5f  jz      short loc_14004AF8A
0x14004af61  mov     eax, [rcx+2Ch]
0x14004af64  test    al, 1
0x14004af66  jz      short loc_14004AF8A
0x14004af68  cmp     byte ptr [rcx+29h], 1
0x14004af6c  jb      short loc_14004AF8A
0x14004af6e  mov     rcx, [rcx+18h]
0x14004af72  lea     r8, WPP_08739a57919f3523a69f175bfdb02181_Traceguids
0x14004af79  mov     edx, 0Fh
0x14004af7e  mov     dword ptr [rsp+78h+PostIrpRoutine], ebx
0x14004af82  mov     r9, rdi
0x14004af85  call    WPP_SF_qD
0x14004af8a  mov     eax, ebx
0x14004af8c  mov     rbx, [rsp+78h+arg_10]
0x14004af94  add     rsp, 40h
0x14004af98  pop     r15
0x14004af9a  pop     r14
0x14004af9c  pop     r13
0x14004af9e  pop     r12
0x14004afa0  pop     rdi
0x14004afa1  pop     rsi
0x14004afa2  pop     rbp
0x14004afa3  retn
0x14004afa5  cmp     dword ptr [r15], 1
0x14004afa9  jz      short loc_14004AFB2
0x14004afab  mov     ebx, 0C0000058h
0x14004afb0  jmp     short loc_14004AF44
0x14004afb2  lea     rcx, [r15+10h]
0x14004afb6  mov     rdx, r12
0x14004afb9  mov     [rsp+78h+var_48], rcx
0x14004afbe  mov     r9, rcx
0x14004afc1  mov     rcx, rax
0x14004afc4  call    RxpValidateBatchedRequest
0x14004afc9  mov     ebx, eax
0x14004afcb  test    eax, eax
0x14004afcd  js      loc_14004AF44
0x14004afd3  mov     edx, [rdi+204h]
0x14004afd9  lea     rcx, [r15+10h]
0x14004afdd  call    RxpValidateBatchedRead
0x14004afe2  test    eax, eax
0x14004afe4  jns     short loc_14004AFF0
0x14004afe6  mov     ebx, 0C000000Dh
0x14004afeb  jmp     loc_14004AF48
0x14004aff0  mov     eax, [r12]
0x14004aff4  mov     ecx, 0FFFFFFFFh
0x14004aff9  shl     rax, 4
0x14004affd  cmp     rax, rcx
0x14004b000  ja      loc_14004B360
0x14004b006  lea     ecx, [rax+8]
0x14004b009  mov     eax, [rbp+8]
0x14004b00c  mov     [rsp+78h+arg_0], ecx
0x14004b013  test    eax, eax
0x14004b015  jz      short loc_14004B025
0x14004b017  cmp     eax, ecx
0x14004b019  jnb     short loc_14004B025
0x14004b01b  mov     ebx, 0C0000023h
0x14004b020  jmp     loc_14004AF48
0x14004b025  mov     eax, 0EC22h
0x14004b02a  cmp     [rsi], ax
0x14004b02d  jz      short loc_14004B039
0x14004b02f  mov     ebx, 0C0000010h
0x14004b034  jmp     loc_14004AF48
0x14004b039  xor     r9d, r9d; LineNumber
0x14004b03c  mov     rdx, rdi; RxContext
0x14004b03f  mov     rcx, rsi; Fcb
0x14004b042  lea     r8d, [r9+1]; Mode
0x14004b046  call    __RxAcquireFcb
0x14004b04b  mov     ebx, eax
0x14004b04d  test    eax, eax
0x14004b04f  jns     short loc_14004B0A2
0x14004b051  cmp     eax, 0C0000055h
0x14004b056  jnz     loc_14004AF48
0x14004b05c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b063  lea     rax, WPP_GLOBAL_Control
0x14004b06a  cmp     rcx, rax
0x14004b06d  jz      short loc_14004B099
0x14004b06f  mov     edx, [rcx+2Ch]
0x14004b072  test    dl, 10h
0x14004b075  jz      short loc_14004B099
0x14004b077  cmp     byte ptr [rcx+29h], 4
0x14004b07b  jb      short loc_14004B099
0x14004b07d  mov     rcx, [rcx+18h]
0x14004b081  lea     r8, WPP_08739a57919f3523a69f175bfdb02181_Traceguids
0x14004b088  mov     edx, 0Dh
0x14004b08d  call    WPP_SF_
0x14004b092  lea     rax, WPP_GLOBAL_Control
0x14004b099  mov     byte ptr [rdi+23h], 1
0x14004b09d  jmp     loc_14004AF4F
0x14004b0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b0a9  lea     rax, WPP_GLOBAL_Control
0x14004b0b0  cmp     rcx, rax
0x14004b0b3  jz      short loc_14004B0EC
0x14004b0b5  mov     eax, [rcx+2Ch]
0x14004b0b8  test    al, 10h
0x14004b0ba  jz      short loc_14004B0EC
0x14004b0bc  cmp     byte ptr [rcx+29h], 2
0x14004b0c0  jb      short loc_14004B0EC
0x14004b0c2  mov     rax, [rsp+78h+arg_8]
0x14004b0ca  lea     r8, WPP_08739a57919f3523a69f175bfdb02181_Traceguids
0x14004b0d1  mov     rcx, [rcx+18h]
0x14004b0d5  mov     edx, 0Eh
0x14004b0da  mov     [rsp+78h+var_50], rax
0x14004b0df  mov     r9, rdi
0x14004b0e2  mov     [rsp+78h+PostIrpRoutine], rsi
0x14004b0e7  call    WPP_SF_qqq
0x14004b0ec  mov     eax, [r15+4]
0x14004b0f0  test    al, 1
0x14004b0f2  jnz     short loc_14004B14E
0x14004b0f4  lea     rax, RxPrePostIrp
0x14004b0fb  mov     r8, rdi; Context
0x14004b0fe  lea     rcx, [rsi+58h]; Oplock
0x14004b102  mov     [rsp+78h+PostIrpRoutine], rax; PostIrpRoutine
0x14004b107  lea     r9, RxUpperOplockBreakCompleteAsync; CompletionRoutine
0x14004b10e  mov     rdx, r14; Irp
0x14004b111  call    cs:__imp_FsRtlCheckOplock
0x14004b118  nop     dword ptr [rax+rax+00h]
0x14004b11d  mov     ebx, eax
0x14004b11f  test    eax, eax
0x14004b121  jnz     loc_14004B2A0
0x14004b127  mov     rax, cs:__imp_FsRtlFastCheckLockForRead
0x14004b12e  xor     r9d, r9d
0x14004b131  mov     r8, r15
0x14004b134  mov     [rsp+78h+PostIrpRoutine], rax; __int64
0x14004b139  mov     rdx, rsi
0x14004b13c  mov     rcx, r14; Irp
0x14004b13f  call    RxCheckByteRangeLocks
0x14004b144  mov     ebx, eax
0x14004b146  test    eax, eax
0x14004b148  jnz     loc_14004B2A0
0x14004b14e  mov     r10, [rsp+78h+arg_8]
0x14004b156  xor     r12b, r12b
0x14004b159  mov     rax, [r10+28h]
0x14004b15d  cmp     qword ptr [rax], 0
0x14004b161  jz      short loc_14004B19B
0x14004b163  mov     r12b, 1
0x14004b166  mov     rdx, rsi
0x14004b169  mov     r8b, r12b
0x14004b16c  mov     rcx, rdi
0x14004b16f  call    RxAcquirePagingIoResource
0x14004b174  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x14004b17b  jz      short loc_14004B193
0x14004b17d  lea     r8, [rdi+19Ch]
0x14004b184  mov     r9, rsi
0x14004b187  lea     rdx, CcPurgeRequest
0x14004b18e  call    McTemplateK0p_EtwWriteTransfer
0x14004b193  mov     r10, [rsp+78h+arg_8]
0x14004b19b  lea     rbx, [r15+10h]
0x14004b19f  test    rbx, rbx
0x14004b1a2  jz      loc_14004B243
0x14004b1a8  xor     ebp, ebp
0x14004b1aa  cmp     ebp, [rbx+8]
0x14004b1ad  jnb     short loc_14004B205
0x14004b1af  mov     r8d, ebp
0x14004b1b2  add     r8, r8
0x14004b1b5  mov     rax, [rbx+r8*8+18h]
0x14004b1ba  mov     qword ptr [rsp+78h+FileOffset], rax
0x14004b1c2  test    r12b, r12b
0x14004b1c5  jz      short loc_14004B1F9
0x14004b1c7  mov     r8d, [rbx+r8*8+24h]; Length
0x14004b1cc  lea     r15, [r14+30h]
0x14004b1d0  mov     rcx, [r10+28h]; SectionObjectPointer
0x14004b1d4  lea     rdx, [rsp+78h+FileOffset]; FileOffset
0x14004b1dc  mov     r9, r15; IoStatus
0x14004b1df  mov     dword ptr [rsp+78h+PostIrpRoutine], 3; Flags
0x14004b1e7  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x14004b1ee  nop     dword ptr [rax+rax+00h]
0x14004b1f3  cmp     dword ptr [r15], 0
0x14004b1f7  jl      short loc_14004B214
0x14004b1f9  mov     r10, [rsp+78h+arg_8]
0x14004b201  inc     ebp
0x14004b203  jmp     short loc_14004B1AA
0x14004b205  mov     eax, [rbx]
0x14004b207  test    eax, eax
0x14004b209  jz      short loc_14004B210
0x14004b20b  add     rbx, rax
0x14004b20e  jmp     short loc_14004B19F
0x14004b210  xor     ebx, ebx
0x14004b212  jmp     short loc_14004B19F
0x14004b214  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x14004b21b  jz      short loc_14004B233
0x14004b21d  lea     r8, [rdi+19Ch]
0x14004b224  mov     r9, rsi
0x14004b227  lea     rdx, CcPurgeCompletion
0x14004b22e  call    McTemplateK0p_EtwWriteTransfer
0x14004b233  mov     rdx, rsi
0x14004b236  mov     rcx, rdi
0x14004b239  call    RxReleasePagingIoResource
0x14004b23e  mov     ebx, [r15]
0x14004b241  jmp     short loc_14004B2A0
0x14004b243  test    r12b, r12b
0x14004b246  jz      short loc_14004B272
0x14004b248  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x14004b24f  jz      short loc_14004B267
0x14004b251  lea     r8, [rdi+19Ch]
0x14004b258  mov     r9, rsi
0x14004b25b  lea     rdx, CcPurgeCompletion
0x14004b262  call    McTemplateK0p_EtwWriteTransfer
0x14004b267  mov     rdx, rsi
0x14004b26a  mov     rcx, rdi
0x14004b26d  call    RxReleasePagingIoResource
0x14004b272  test    dword ptr [rdi+78h], 200h
0x14004b279  jnz     short loc_14004B2B0
0x14004b27b  test    r13b, r13b
0x14004b27e  jnz     short loc_14004B2B0
0x14004b280  mov     r8d, [rdi+204h]
0x14004b287  mov     r9d, 1
0x14004b28d  mov     rdx, [rsp+78h+var_48]
0x14004b292  mov     rcx, r14; PIRP
0x14004b295  call    RxpProbeAndLockBatchedBuffers
0x14004b29a  mov     ebx, eax
0x14004b29c  test    eax, eax
0x14004b29e  jns     short loc_14004B2C7
0x14004b2a0  mov     rdx, rsi; MrxFcb
0x14004b2a3  mov     rcx, rdi; RxContext
0x14004b2a6  call    __RxReleaseFcb
0x14004b2ab  jmp     loc_14004AF44
0x14004b2b0  mov     r8d, [rdi+204h]
0x14004b2b7  mov     r9b, r13b
0x14004b2ba  mov     rdx, [rsp+78h+var_48]
0x14004b2bf  mov     rcx, r14
0x14004b2c2  call    RxpAssertBatchedBuffersLocked
0x14004b2c7  mov     rdx, rsi; MrxFcb
0x14004b2ca  mov     rcx, rdi; RxContext
0x14004b2cd  call    __RxReleaseFcb
0x14004b2d2  lea     r8, [rdi+208h]; LowIoContext
0x14004b2d9  mov     edx, 6; Operation
0x14004b2de  mov     rcx, rdi; RxContext
0x14004b2e1  call    RxInitializeLowIoContext
0x14004b2e6  mov     edx, [rsp+78h+arg_0]
0x14004b2ed  mov     ecx, 40h ; '@'
0x14004b2f2  mov     r8d, 72427852h
0x14004b2f8  call    cs:__imp_ExAllocatePool2
0x14004b2ff  nop     dword ptr [rax+rax+00h]
0x14004b304  mov     [rdi+220h], rax
0x14004b30b  test    rax, rax
0x14004b30e  jnz     short loc_14004B31A
0x14004b310  mov     ebx, 0C000009Ah
0x14004b315  jmp     loc_14004AF48
0x14004b31a  cmp     qword ptr [rdi+70h], 0
0x14004b31f  jnz     short loc_14004B331
0x14004b321  mov     eax, [r14+10h]
0x14004b325  test    al, 2
0x14004b327  jnz     short loc_14004B331
0x14004b329  or      word ptr [rdi+20Ah], 8
0x14004b331  lea     r9, RxLowIoFsCtlShellCompletion; CompletionRoutine
0x14004b338  mov     r8, rsi; Fcb
0x14004b33b  mov     rdx, r14; Irp
0x14004b33e  mov     rcx, rdi; RxContext
0x14004b341  call    RxLowIoSubmit
0x14004b346  mov     ebx, eax
0x14004b348  cmp     eax, 103h
0x14004b34d  jz      loc_14004AF44
0x14004b353  test    eax, eax
  ... truncated ...
```
