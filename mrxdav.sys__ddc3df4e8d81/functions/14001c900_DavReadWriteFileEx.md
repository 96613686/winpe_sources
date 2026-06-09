# DavReadWriteFileEx

- ea: `0x14001c900`
- end: `0x14001ce20`
- name: `DavReadWriteFileEx`
- size: `1312`
- prototype: `__int64 __fastcall(unsigned __int16, int, int, struct _MDL *, PDEVICE_OBJECT DeviceObject, struct _FILE_OBJECT *, __int64, PVOID VirtualAddress, ULONG Length, char, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001d020`
- `0x1400241b0`

## callees

- `0x14000163c`
- `0x140001680`
- `0x14000360c`
- `0x14001c900`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c95c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c9af`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ca14`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ca89`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001cb6e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ccd3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001cd23`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001cde6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c95c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c9af`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ca14`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ca89`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001cb6e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ccd3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001cd23`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001cde6`
- `ntoskrnl!KeInitializeEvent` at `0x14001cc03`
- `ntoskrnl!KeInitializeEvent` at `0x14001cc03`
- `ntoskrnl!IoAllocateMdl` at `0x14001cb35`
- `ntoskrnl!IoAllocateMdl` at `0x14001cb35`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14001cc10`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14001cc10`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001cc26`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001cc4e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140029024`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001cc26`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001cc4e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140029024`
- `ntoskrnl!IofCallDriver` at `0x14001cc38`
- `ntoskrnl!IofCallDriver` at `0x14001cc38`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001cc75`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001cc75`
- `ntoskrnl!IoFreeMdl` at `0x14001cd57`
- `ntoskrnl!IoFreeMdl` at `0x14001cdaf`
- `ntoskrnl!IoFreeMdl` at `0x14001cd57`
- `ntoskrnl!IoFreeMdl` at `0x14001cdaf`
- `ntoskrnl!IoAllocateIrp` at `0x14001ca54`
- `ntoskrnl!IoAllocateIrp` at `0x14001ca54`
- `ntoskrnl!IoFreeIrp` at `0x14001cdbe`
- `ntoskrnl!IoFreeIrp` at `0x14001cdbe`
- `ntoskrnl!IoBuildPartialMdl` at `0x14001cbb2`
- `ntoskrnl!IoBuildPartialMdl` at `0x14001cbb2`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001cbca`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001cbca`
- `ntoskrnl!MmProbeAndLockPages` at `0x14001cbdd`
- `ntoskrnl!MmProbeAndLockPages` at `0x14001cbdd`
- `ntoskrnl!MmUnlockPages` at `0x14001cd9f`
- `ntoskrnl!MmUnlockPages` at `0x14001cd9f`

## pseudocode

```c
__int64 __fastcall DavReadWriteFileEx(
        unsigned __int16 a1,
        int a2,
        int a3,
        struct _MDL *a4,
        PDEVICE_OBJECT DeviceObject,
        struct _FILE_OBJECT *a6,
        __int64 a7,
        PVOID VirtualAddress,
        ULONG Length,
        char a10,
        __int64 a11)
{
  int v12; // r15d
  int v13; // r13d
  __int64 v14; // rdi
  HANDLE CurrentThreadId; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rbx
  HANDLE v19; // rax
  PIRP Irp; // rsi
  __int64 v21; // rbx
  HANDLE v22; // rax
  NTSTATUS Status; // r15d
  __int64 Information_low; // rdi
  __int64 v25; // rbx
  HANDLE v26; // rax
  __int64 v27; // rdx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IO_STACK_LOCATION *v29; // rax
  struct _MDL *Mdl; // rcx
  NTSTATUS *v31; // rbx
  __int64 v32; // rbx
  HANDLE v33; // rax
  struct _MDL *MdlAddress; // rcx
  __int64 v35; // rbx
  HANDLE v36; // rax
  IRP *TopLevelIrp; // [rsp+48h] [rbp-60h]
  struct _KEVENT Event; // [rsp+50h] [rbp-58h] BYREF

  v12 = a1;
  memset(&Event, 0, sizeof(Event));
  v13 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v14 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_qddqi(v14, v16, v17, CurrentThreadId, v12, a2, a6, a7, 0);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v19 = PsGetCurrentThreadId();
    WPP_SF_qD(v18, 50, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids, v19, Length);
  }
  *(_QWORD *)(a11 + 8) = 0;
  if ( (DeviceObject->Flags & 4) != 0 )
  {
    Irp = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v21 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v22 = PsGetCurrentThreadId();
      WPP_SF_q(v21, 51, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids, v22);
    }
    Status = -1073741808;
    goto LABEL_12;
  }
  Irp = IoAllocateIrp(DeviceObject->StackSize, 0);
  if ( !Irp )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
      goto LABEL_18;
    v25 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v26 = PsGetCurrentThreadId();
    v27 = 52;
LABEL_17:
    WPP_SF_q(v25, v27, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids, v26);
LABEL_18:
    Status = -1073741670;
LABEL_12:
    LODWORD(Information_low) = -1;
    goto LABEL_37;
  }
  Irp->Tail.Overlay.Thread = KeGetCurrentThread();
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].MajorFunction = ((_WORD)v12 != 0) + 3;
  CurrentStackLocation[-1].FileObject = a6;
  v29 = Irp->Tail.Overlay.CurrentStackLocation;
  v29[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&DavReadWriteIrpCompletionRoutine;
  v29[-1].Context = &Event;
  v29[-1].Control = -32;
  CurrentStackLocation[-1].Parameters.Read.Length = Length;
  CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart = a7;
  CurrentStackLocation[-1].Parameters.Create.Options = 0;
  Irp->RequestorMode = 0;
  Irp->UserBuffer = VirtualAddress;
  Mdl = IoAllocateMdl(VirtualAddress, Length, 0, 0, 0);
  Irp->MdlAddress = Mdl;
  if ( !Mdl )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
      goto LABEL_18;
    v25 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v26 = PsGetCurrentThreadId();
    v27 = 53;
    goto LABEL_17;
  }
  Irp->Flags |= a10 & 1;
  if ( a3 )
  {
    IoBuildPartialMdl(a4, Mdl, Irp->UserBuffer, Length);
  }
  else if ( a2 )
  {
    MmBuildMdlForNonPagedPool(Mdl);
  }
  else
  {
    MmProbeAndLockPages(Mdl, 0, (LOCK_OPERATION)((_WORD)v12 == 0));
    v13 = 1;
  }
  KeInitializeEvent(&Event, NotificationEvent, 0);
  TopLevelIrp = IoGetTopLevelIrp();
  IoSetTopLevelIrp(0);
  Status = IofCallDriver(DeviceObject, Irp);
  IoSetTopLevelIrp(TopLevelIrp);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = Irp->IoStatus.Status;
  }
  if ( !Status )
  {
    Information_low = LODWORD(Irp->IoStatus.Information);
    v31 = (NTSTATUS *)a11;
    *(_QWORD *)(a11 + 8) = Information_low;
    goto LABEL_38;
  }
  if ( Status == -1073741807 )
  {
    LODWORD(Information_low) = 0;
  }
  else
  {
    LODWORD(Information_low) = -1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v32 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v33 = PsGetCurrentThreadId();
      WPP_SF_qD(v32, 55, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids, v33, Status);
    }
  }
LABEL_37:
  v31 = (NTSTATUS *)a11;
LABEL_38:
  if ( Irp )
  {
    MdlAddress = Irp->MdlAddress;
    if ( MdlAddress )
    {
      if ( v13 )
        MmUnlockPages(MdlAddress);
      IoFreeMdl(Irp->MdlAddress);
    }
    IoFreeIrp(Irp);
  }
  *v31 = Status;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v35 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v36 = PsGetCurrentThreadId();
    WPP_SF_qD(v35, 56, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids, v36, Information_low);
  }
  return (unsigned int)Information_low;
}

```

## disassembly

```asm
0x14001c900  mov     r11, rsp
0x14001c903  mov     [r11+20h], r9
0x14001c907  mov     [r11+18h], r8d
0x14001c90b  mov     [rsp+arg_8], edx
0x14001c90f  push    rbx
0x14001c910  push    rsi
0x14001c911  push    rdi
0x14001c912  push    r12
0x14001c914  push    r13
0x14001c916  push    r14
0x14001c918  push    r15
0x14001c91a  sub     rsp, 70h
0x14001c91e  mov     esi, edx
0x14001c920  movzx   r15d, cx
0x14001c924  xorps   xmm0, xmm0
0x14001c927  xor     eax, eax
0x14001c929  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x14001c92e  mov     [r11-48h], rax
0x14001c932  xor     r14d, r14d
0x14001c935  mov     r13d, r14d
0x14001c938  mov     [r11-68h], r14d
0x14001c93c  lea     r12, WPP_GLOBAL_Control
0x14001c943  mov     rdi, cs:WPP_GLOBAL_Control
0x14001c94a  cmp     rdi, r12
0x14001c94d  jz      short loc_14001C996
0x14001c94f  test    dword ptr [rdi+2Ch], 4000h
0x14001c956  jz      short loc_14001C996
0x14001c958  mov     rdi, [rdi+18h]
0x14001c95c  call    cs:__imp_PsGetCurrentThreadId
0x14001c963  nop     dword ptr [rax+rax+00h]
0x14001c968  mov     r9, rax
0x14001c96b  mov     rax, [rsp+0A8h+arg_30]
0x14001c973  mov     [rsp+0A8h+var_70], rax
0x14001c978  mov     rax, [rsp+0A8h+arg_28]
0x14001c980  mov     [rsp+0A8h+var_78], rax
0x14001c985  mov     [rsp+0A8h+var_80], esi
0x14001c989  mov     dword ptr [rsp+0A8h+Irp], r15d
0x14001c98e  mov     rcx, rdi
0x14001c991  call    WPP_SF_qddqi
0x14001c996  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c99d  cmp     rbx, r12
0x14001c9a0  jz      short loc_14001C9DD
0x14001c9a2  test    dword ptr [rbx+2Ch], 4000h
0x14001c9a9  jz      short loc_14001C9DD
0x14001c9ab  mov     rbx, [rbx+18h]
0x14001c9af  call    cs:__imp_PsGetCurrentThreadId
0x14001c9b6  nop     dword ptr [rax+rax+00h]
0x14001c9bb  mov     r9, rax
0x14001c9be  mov     edx, 32h ; '2'
0x14001c9c3  mov     eax, [rsp+0A8h+Length]
0x14001c9ca  mov     dword ptr [rsp+0A8h+Irp], eax
0x14001c9ce  lea     r8, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids
0x14001c9d5  mov     rcx, rbx
0x14001c9d8  call    WPP_SF_qD
0x14001c9dd  mov     rax, [rsp+0A8h+arg_50]
0x14001c9e5  mov     [rax+8], r14
0x14001c9e9  mov     rdi, [rsp+0A8h+DeviceObject]
0x14001c9f1  mov     eax, [rdi+30h]
0x14001c9f4  test    al, 4
0x14001c9f6  jz      short loc_14001CA45
0x14001c9f8  mov     rsi, r14
0x14001c9fb  mov     rbx, cs:WPP_GLOBAL_Control
0x14001ca02  cmp     rbx, r12
0x14001ca05  jz      short loc_14001CA37
0x14001ca07  test    dword ptr [rbx+2Ch], 2000h
0x14001ca0e  jz      short loc_14001CA37
0x14001ca10  mov     rbx, [rbx+18h]
0x14001ca14  call    cs:__imp_PsGetCurrentThreadId
0x14001ca1b  nop     dword ptr [rax+rax+00h]
0x14001ca20  mov     r9, rax
0x14001ca23  mov     edx, 33h ; '3'
0x14001ca28  lea     r8, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids
0x14001ca2f  mov     rcx, rbx
0x14001ca32  call    WPP_SF_q
0x14001ca37  mov     r15d, 0C0000010h
0x14001ca3d  or      edi, 0FFFFFFFFh
0x14001ca40  jmp     loc_14001CD84
0x14001ca45  mov     ebx, r14d
0x14001ca48  test    r15w, r15w
0x14001ca4c  setz    bl
0x14001ca4f  xor     edx, edx; ChargeQuota
0x14001ca51  mov     cl, [rdi+4Ch]; StackSize
0x14001ca54  call    cs:__imp_IoAllocateIrp
0x14001ca5b  nop     dword ptr [rax+rax+00h]
0x14001ca60  mov     rsi, rax
0x14001ca63  mov     [rsp+0A8h+DeviceObject], rax
0x14001ca6b  test    rax, rax
0x14001ca6e  jnz     short loc_14001CAB2
0x14001ca70  mov     rbx, cs:WPP_GLOBAL_Control
0x14001ca77  cmp     rbx, r12
0x14001ca7a  jz      short loc_14001CAAA
0x14001ca7c  test    dword ptr [rbx+2Ch], 2000h
0x14001ca83  jz      short loc_14001CAAA
0x14001ca85  mov     rbx, [rbx+18h]
0x14001ca89  call    cs:__imp_PsGetCurrentThreadId
0x14001ca90  nop     dword ptr [rax+rax+00h]
0x14001ca95  lea     edx, [rsi+34h]
0x14001ca98  mov     r9, rax
0x14001ca9b  lea     r8, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids
0x14001caa2  mov     rcx, rbx
0x14001caa5  call    WPP_SF_q
0x14001caaa  mov     r15d, 0C000009Ah
0x14001cab0  jmp     short loc_14001CA3D
0x14001cab2  mov     rax, gs:188h
0x14001cabb  mov     [rsi+98h], rax
0x14001cac2  mov     rcx, [rsi+0B8h]
0x14001cac9  test    r15w, r15w
0x14001cacd  setnz   al
0x14001cad0  add     al, 3
0x14001cad2  mov     [rcx-48h], al
0x14001cad5  mov     rax, [rsp+0A8h+arg_28]
0x14001cadd  mov     [rcx-18h], rax
0x14001cae1  mov     rax, [rsi+0B8h]
0x14001cae8  lea     rdx, DavReadWriteIrpCompletionRoutine
0x14001caef  mov     [rax-10h], rdx
0x14001caf3  lea     rdx, [rsp+0A8h+Event]
0x14001caf8  mov     [rax-8], rdx
0x14001cafc  mov     byte ptr [rax-45h], 0E0h
0x14001cb00  mov     edx, [rsp+0A8h+Length]; Length
0x14001cb07  mov     [rcx-40h], edx
0x14001cb0a  mov     rax, [rsp+0A8h+arg_30]
0x14001cb12  mov     [rcx-30h], rax
0x14001cb16  mov     [rcx-38h], r14d
0x14001cb1a  mov     [rsi+40h], r14b
0x14001cb1e  mov     rcx, [rsp+0A8h+VirtualAddress]; VirtualAddress
0x14001cb26  mov     [rsi+70h], rcx
0x14001cb2a  mov     [rsp+0A8h+Irp], r14; Irp
0x14001cb2f  xor     r9d, r9d; ChargeQuota
0x14001cb32  xor     r8d, r8d; SecondaryBuffer
0x14001cb35  call    cs:__imp_IoAllocateMdl
0x14001cb3c  nop     dword ptr [rax+rax+00h]
0x14001cb41  mov     rcx, rax; MemoryDescriptorList
0x14001cb44  mov     [rsi+8], rax
0x14001cb48  test    rax, rax
0x14001cb4b  jnz     short loc_14001CB84
0x14001cb4d  mov     rbx, cs:WPP_GLOBAL_Control
0x14001cb54  cmp     rbx, r12
0x14001cb57  jz      loc_14001CAAA
0x14001cb5d  test    dword ptr [rbx+2Ch], 2000h
0x14001cb64  jz      loc_14001CAAA
0x14001cb6a  mov     rbx, [rbx+18h]
0x14001cb6e  call    cs:__imp_PsGetCurrentThreadId
0x14001cb75  nop     dword ptr [rax+rax+00h]
0x14001cb7a  mov     edx, 35h ; '5'
0x14001cb7f  jmp     loc_14001CA98
0x14001cb84  mov     eax, dword ptr [rsp+0A8h+arg_48]
0x14001cb8b  and     eax, 1
0x14001cb8e  or      [rsi+10h], eax
0x14001cb91  cmp     [rsp+0A8h+arg_10], r14d
0x14001cb99  jz      short loc_14001CBC0
0x14001cb9b  mov     r9d, [rsp+0A8h+Length]; Length
0x14001cba3  mov     r8, [rsi+70h]; VirtualAddress
0x14001cba7  mov     rdx, rcx; TargetMdl
0x14001cbaa  mov     rcx, [rsp+0A8h+SourceMdl]; SourceMdl
0x14001cbb2  call    cs:__imp_IoBuildPartialMdl
0x14001cbb9  nop     dword ptr [rax+rax+00h]
0x14001cbbe  jmp     short loc_14001CBF4
0x14001cbc0  cmp     [rsp+0A8h+arg_8], r14d
0x14001cbc8  jz      short loc_14001CBD8
0x14001cbca  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14001cbd1  nop     dword ptr [rax+rax+00h]
0x14001cbd6  jmp     short loc_14001CBF4
0x14001cbd8  mov     r8d, ebx; Operation
0x14001cbdb  xor     edx, edx; AccessMode
0x14001cbdd  call    cs:__imp_MmProbeAndLockPages
0x14001cbe4  nop     dword ptr [rax+rax+00h]
0x14001cbe9  mov     r13d, 1
0x14001cbef  mov     [rsp+0A8h+var_68], r13d
0x14001cbf4  mov     [rsp+0A8h+var_60], r14
0x14001cbf9  xor     r8d, r8d; State
0x14001cbfc  xor     edx, edx; Type
0x14001cbfe  lea     rcx, [rsp+0A8h+Event]; Event
0x14001cc03  call    cs:__imp_KeInitializeEvent
0x14001cc0a  nop     dword ptr [rax+rax+00h]
0x14001cc0f  nop
0x14001cc10  call    cs:__imp_IoGetTopLevelIrp
0x14001cc17  nop     dword ptr [rax+rax+00h]
0x14001cc1c  mov     rbx, rax
0x14001cc1f  mov     [rsp+0A8h+var_60], rax
0x14001cc24  xor     ecx, ecx; Irp
0x14001cc26  call    cs:__imp_IoSetTopLevelIrp
0x14001cc2d  nop     dword ptr [rax+rax+00h]
0x14001cc32  mov     rdx, rsi; Irp
0x14001cc35  mov     rcx, rdi; DeviceObject
0x14001cc38  call    cs:__imp_IofCallDriver
0x14001cc3f  nop     dword ptr [rax+rax+00h]
0x14001cc44  mov     r15d, eax
0x14001cc47  mov     [rsp+0A8h+var_64], eax
0x14001cc4b  mov     rcx, rbx; Irp
0x14001cc4e  call    cs:__imp_IoSetTopLevelIrp
0x14001cc55  nop     dword ptr [rax+rax+00h]
0x14001cc5a  cmp     r15d, 103h
0x14001cc61  jnz     short loc_14001CC85
0x14001cc63  mov     [rsp+0A8h+Irp], r14; Timeout
0x14001cc68  xor     r9d, r9d; Alertable
0x14001cc6b  xor     r8d, r8d; WaitMode
0x14001cc6e  xor     edx, edx; WaitReason
0x14001cc70  lea     rcx, [rsp+0A8h+Event]; Object
0x14001cc75  call    cs:__imp_KeWaitForSingleObject
0x14001cc7c  nop     dword ptr [rax+rax+00h]
0x14001cc81  mov     r15d, [rsi+30h]
0x14001cc85  test    r15d, r15d
0x14001cc88  jnz     short loc_14001CC9E
0x14001cc8a  mov     edi, [rsi+38h]
0x14001cc8d  mov     rbx, [rsp+0A8h+arg_50]
0x14001cc95  mov     [rbx+8], rdi
0x14001cc99  jmp     loc_14001CD8C
0x14001cc9e  cmp     r15d, 0C0000011h
0x14001cca5  jnz     short loc_14001CCAF
0x14001cca7  mov     edi, r14d
0x14001ccaa  jmp     loc_14001CD84
0x14001ccaf  or      edi, 0FFFFFFFFh
0x14001ccb2  mov     rbx, cs:WPP_GLOBAL_Control
0x14001ccb9  cmp     rbx, r12
0x14001ccbc  jz      loc_14001CD84
0x14001ccc2  test    dword ptr [rbx+2Ch], 2000h
0x14001ccc9  jz      loc_14001CD84
0x14001cccf  mov     rbx, [rbx+18h]
0x14001ccd3  call    cs:__imp_PsGetCurrentThreadId
0x14001ccda  nop     dword ptr [rax+rax+00h]
0x14001ccdf  mov     r9, rax
0x14001cce2  mov     edx, 37h ; '7'
0x14001cce7  mov     dword ptr [rsp+0A8h+Irp], r15d
0x14001ccec  lea     r8, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids
0x14001ccf3  mov     rcx, rbx
0x14001ccf6  call    WPP_SF_qD
0x14001ccfb  jmp     loc_14001CD84
0x14001cd00  mov     r15d, eax
0x14001cd03  lea     rax, WPP_GLOBAL_Control
0x14001cd0a  mov     rbx, cs:WPP_GLOBAL_Control
0x14001cd11  cmp     rbx, rax
0x14001cd14  jz      short loc_14001CD4B
0x14001cd16  test    dword ptr [rbx+2Ch], 2000h
0x14001cd1d  jz      short loc_14001CD4B
0x14001cd1f  mov     rbx, [rbx+18h]
0x14001cd23  call    cs:__imp_PsGetCurrentThreadId
0x14001cd2a  nop     dword ptr [rax+rax+00h]
0x14001cd2f  mov     r9, rax
0x14001cd32  mov     edx, 36h ; '6'
0x14001cd37  mov     dword ptr [rsp+0A8h+Irp], r15d
0x14001cd3c  lea     r8, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids
0x14001cd43  mov     rcx, rbx
0x14001cd46  call    WPP_SF_qD
0x14001cd4b  mov     rsi, [rsp+0A8h+DeviceObject]
0x14001cd53  mov     rcx, [rsi+8]; Mdl
0x14001cd57  call    cs:__imp_IoFreeMdl
0x14001cd5e  nop     dword ptr [rax+rax+00h]
0x14001cd63  mov     qword ptr [rsi+8], 0
0x14001cd6b  or      edi, 0FFFFFFFFh
0x14001cd6e  lea     r12, WPP_GLOBAL_Control
0x14001cd75  mov     r13d, [rsp+0A8h+var_68]
0x14001cd7a  mov     rbx, [rsp+0A8h+arg_50]
0x14001cd82  jmp     short loc_14001CD8C
0x14001cd84  mov     rbx, [rsp+0A8h+arg_50]
0x14001cd8c  test    rsi, rsi
0x14001cd8f  jz      short loc_14001CDCA
0x14001cd91  mov     rcx, [rsi+8]; MemoryDescriptorList
0x14001cd95  test    rcx, rcx
0x14001cd98  jz      short loc_14001CDBB
0x14001cd9a  test    r13d, r13d
0x14001cd9d  jz      short loc_14001CDAB
0x14001cd9f  call    cs:__imp_MmUnlockPages
0x14001cda6  nop     dword ptr [rax+rax+00h]
0x14001cdab  mov     rcx, [rsi+8]; Mdl
0x14001cdaf  call    cs:__imp_IoFreeMdl
0x14001cdb6  nop     dword ptr [rax+rax+00h]
0x14001cdbb  mov     rcx, rsi; Irp
0x14001cdbe  call    cs:__imp_IoFreeIrp
0x14001cdc5  nop     dword ptr [rax+rax+00h]
0x14001cdca  mov     [rbx], r15d
0x14001cdcd  mov     rbx, cs:WPP_GLOBAL_Control
0x14001cdd4  cmp     rbx, r12
0x14001cdd7  jz      short loc_14001CE0D
0x14001cdd9  test    dword ptr [rbx+2Ch], 4000h
0x14001cde0  jz      short loc_14001CE0D
0x14001cde2  mov     rbx, [rbx+18h]
0x14001cde6  call    cs:__imp_PsGetCurrentThreadId
0x14001cded  nop     dword ptr [rax+rax+00h]
0x14001cdf2  mov     r9, rax
0x14001cdf5  mov     edx, 38h ; '8'
0x14001cdfa  mov     dword ptr [rsp+0A8h+Irp], edi
0x14001cdfe  lea     r8, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids
0x14001ce05  mov     rcx, rbx
0x14001ce08  call    WPP_SF_qD
0x14001ce0d  mov     eax, edi
0x14001ce0f  add     rsp, 70h
0x14001ce13  pop     r15
0x14001ce15  pop     r14
0x14001ce17  pop     r13
0x14001ce19  pop     r12
0x14001ce1b  pop     rdi
0x14001ce1c  pop     rsi
0x14001ce1d  pop     rbx
0x14001ce1e  retn
0x140029017  push    rbp
0x140029019  sub     rsp, 40h
0x14002901d  mov     rbp, rdx
0x140029020  mov     rcx, [rbp+48h]; Irp
0x140029024  call    cs:__imp_IoSetTopLevelIrp
0x14002902b  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
