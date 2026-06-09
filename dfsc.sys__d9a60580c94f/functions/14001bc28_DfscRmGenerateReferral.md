# DfscRmGenerateReferral

- ea: `0x14001bc28`
- end: `0x14001bfdc`
- name: `DfscRmGenerateReferral`
- size: `948`
- prototype: `__int64 __fastcall(__int64, const void **, __int64, CSHORT, struct _IRP **, _DWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140011604`
- `0x14001a93c`
- `0x14001b9ec`

## callees

- `0x1400025f4`
- `0x1400027f8`
- `0x1400048b4`
- `0x140006080`
- `0x14001bc28`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14001bcec`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14001bcec`
- `ntoskrnl!IoFreeIrp` at `0x14001bdc9`
- `ntoskrnl!IoFreeIrp` at `0x14001bdc9`
- `ntoskrnl!IoAllocateIrp` at `0x14001bd02`
- `ntoskrnl!IoAllocateIrp` at `0x14001bd02`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001bf2d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001bf2d`
- `ntoskrnl!KeReadStateEvent` at `0x14001bf0b`
- `ntoskrnl!KeReadStateEvent` at `0x14001bf0b`
- `ntoskrnl!IoCancelIrp` at `0x14001bef6`
- `ntoskrnl!IoCancelIrp` at `0x14001bef6`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x14001bed9`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x14001bed9`
- `ntoskrnl!IofCallDriver` at `0x14001bda9`
- `ntoskrnl!IofCallDriver` at `0x14001bda9`
- `ntoskrnl!KeInitializeEvent` at `0x14001bcdd`
- `ntoskrnl!KeInitializeEvent` at `0x14001bcdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001be0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001be93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001be0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001be93`
- `ntoskrnl!ExAllocatePool2` at `0x14001bc6e`
- `ntoskrnl!ExAllocatePool2` at `0x14001bc6e`

## pseudocode

```c
__int64 __fastcall DfscRmGenerateReferral(
        __int64 a1,
        const void **a2,
        __int64 a3,
        CSHORT a4,
        struct _IRP **a5,
        _DWORD *a6)
{
  unsigned int v6; // esi
  __int64 v8; // rbp
  struct _IRP *Pool2; // rax
  struct _IRP *v11; // rdi
  USHORT *p_Size; // rbx
  struct _FILE_OBJECT *v13; // r15
  int v14; // r12d
  PDEVICE_OBJECT RelatedDeviceObject; // rbx
  PIRP Irp; // rax
  PIRP v17; // rbp
  IRP *v18; // rdx
  struct _KTHREAD *CurrentThread; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v21; // rax
  NTSTATUS Status; // ebx
  int Information; // r15d
  __int64 result; // rax
  NTSTATUS v25; // eax
  struct _KEVENT Event; // [rsp+30h] [rbp-68h] BYREF

  v6 = *(unsigned __int16 *)a2 + 5;
  v8 = a3;
  if ( v6 < 0x1000 )
    v6 = 4096;
  while ( 1 )
  {
    Pool2 = (struct _IRP *)ExAllocatePool2(258, v6, 1782801988);
    v11 = Pool2;
    if ( !Pool2 )
      break;
    Pool2->Type = a4;
    p_Size = &Pool2->Size;
    if ( *(_WORD *)a2 )
      memmove(p_Size, a2[1], *(unsigned __int16 *)a2);
    p_Size[(unsigned __int64)*(unsigned __int16 *)a2 >> 1] = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      WPP_SF_qS(
        WPP_GLOBAL_Control->AttachedDevice,
        23,
        (unsigned int)WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids,
        (_DWORD)v11,
        (__int64)p_Size);
    }
    v13 = *(struct _FILE_OBJECT **)(v8 + 48);
    v14 = *(unsigned __int16 *)a2 + 4;
    memset(&Event, 0, sizeof(Event));
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    RelatedDeviceObject = IoGetRelatedDeviceObject(v13);
    Irp = IoAllocateIrp(RelatedDeviceObject->StackSize + 1, 0);
    v17 = Irp;
    if ( !Irp )
    {
      Status = -1073741670;
LABEL_11:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids, v11);
      }
      ExFreePoolWithTag(v11, 0);
      v11 = 0;
      goto LABEL_15;
    }
    Irp->RequestorMode = 0;
    v18 = Irp;
    Irp->Tail.Overlay.OriginalFileObject = v13;
    CurrentThread = KeGetCurrentThread();
    --Irp->Tail.Overlay.CurrentStackLocation;
    --Irp->CurrentLocation;
    Irp->Tail.Overlay.Thread = CurrentThread;
    Irp->Tail.Overlay.CurrentStackLocation->DeviceObject = RelatedDeviceObject;
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&DfscRmCompletionRoutine;
    CurrentStackLocation[-1].Context = &Event;
    CurrentStackLocation[-1].Control = -32;
    v21 = v17->Tail.Overlay.CurrentStackLocation;
    v21[-1].Parameters.Create.Options = v14;
    *(_WORD *)&v21[-1].MajorFunction = 13;
    v21[-1].FileObject = v13;
    v21[-1].DeviceObject = RelatedDeviceObject;
    v21[-1].Parameters.Read.Length = v6;
    v21[-1].Parameters.Read.ByteOffset.LowPart = 393620;
    v17->MdlAddress = 0;
    v17->AssociatedIrp.MasterIrp = v11;
    v17->UserBuffer = v11;
    v17->Flags = 80;
    Status = IofCallDriver(RelatedDeviceObject, v18);
    if ( Status == 259 )
    {
      v25 = FsRtlCancellableWaitForSingleObject(&Event, 0, 0);
      if ( (v25 == -1073741536 || v25 == -1073741749) && (!IoCancelIrp(v17) || !KeReadStateEvent(&Event)) )
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v17->IoStatus.Status;
    }
    Information = v17->IoStatus.Information;
    IoFreeIrp(v17);
    if ( Status != -2147483643 )
    {
      if ( Status >= 0 )
      {
        *a6 = Information;
        goto LABEL_15;
      }
      goto LABEL_11;
    }
    if ( v6 >= 0xE000 )
      goto LABEL_11;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids, v11);
    }
    ExFreePoolWithTag(v11, 0);
    v8 = a3;
    v6 *= 2;
    if ( v6 > 0xE000 )
      v6 = 57344;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids, v6);
  Status = -1073741670;
LABEL_15:
  result = (unsigned int)Status;
  *a5 = v11;
  return result;
}

```

## disassembly

```asm
0x14001bc28  mov     [rsp+arg_10], r8
0x14001bc2d  push    rbx
0x14001bc2e  push    rbp
0x14001bc2f  push    rsi
0x14001bc30  push    rdi
0x14001bc31  push    r12
0x14001bc33  push    r13
0x14001bc35  push    r14
0x14001bc37  push    r15
0x14001bc39  sub     rsp, 58h
0x14001bc3d  movzx   esi, word ptr [rdx]
0x14001bc40  lea     r15, WPP_GLOBAL_Control
0x14001bc47  add     esi, 5
0x14001bc4a  mov     eax, 1000h
0x14001bc4f  cmp     esi, eax
0x14001bc51  movzx   r13d, r9w
0x14001bc55  mov     rbp, r8
0x14001bc58  mov     r14, rdx
0x14001bc5b  cmovb   esi, eax
0x14001bc5e  xor     r12d, r12d
0x14001bc61  mov     edx, esi
0x14001bc63  mov     ecx, 102h
0x14001bc68  mov     r8d, 6A436644h
0x14001bc6e  call    cs:__imp_ExAllocatePool2
0x14001bc75  nop     dword ptr [rax+rax+00h]
0x14001bc7a  mov     rdi, rax
0x14001bc7d  test    rax, rax
0x14001bc80  jz      loc_14001BFA5
0x14001bc86  mov     [rax], r13w
0x14001bc8a  lea     rbx, [rax+2]
0x14001bc8e  movzx   eax, word ptr [r14]
0x14001bc92  test    ax, ax
0x14001bc95  jnz     loc_14001BEBB
0x14001bc9b  movzx   ecx, word ptr [r14]
0x14001bc9f  shr     rcx, 1
0x14001bca2  mov     [rbx+rcx*2], r12w
0x14001bca7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bcae  cmp     rcx, r15
0x14001bcb1  jnz     loc_14001BE3C
0x14001bcb7  movzx   r12d, word ptr [r14]
0x14001bcbb  lea     rcx, [rsp+98h+Event]; Event
0x14001bcc0  mov     r15, [rbp+30h]
0x14001bcc4  xor     eax, eax
0x14001bcc6  xorps   xmm0, xmm0
0x14001bcc9  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x14001bcce  xor     r8d, r8d; State
0x14001bcd1  add     r12d, 4
0x14001bcd5  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x14001bcda  lea     edx, [rax+1]; Type
0x14001bcdd  call    cs:__imp_KeInitializeEvent
0x14001bce4  nop     dword ptr [rax+rax+00h]
0x14001bce9  mov     rcx, r15; FileObject
0x14001bcec  call    cs:__imp_IoGetRelatedDeviceObject
0x14001bcf3  nop     dword ptr [rax+rax+00h]
0x14001bcf8  xor     edx, edx; ChargeQuota
0x14001bcfa  mov     rbx, rax
0x14001bcfd  mov     cl, [rax+4Ch]
0x14001bd00  inc     cl; StackSize
0x14001bd02  call    cs:__imp_IoAllocateIrp
0x14001bd09  nop     dword ptr [rax+rax+00h]
0x14001bd0e  mov     rbp, rax
0x14001bd11  test    rax, rax
0x14001bd14  jz      loc_14001BF7B
0x14001bd1a  mov     byte ptr [rax+40h], 0
0x14001bd1e  mov     rdx, rbp; Irp
0x14001bd21  mov     [rax+0C0h], r15
0x14001bd28  mov     rcx, gs:188h
0x14001bd31  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x14001bd39  dec     byte ptr [rax+43h]
0x14001bd3c  mov     [rax+98h], rcx
0x14001bd43  mov     rcx, [rax+0B8h]
0x14001bd4a  mov     [rcx+28h], rbx
0x14001bd4e  lea     rcx, DfscRmCompletionRoutine
0x14001bd55  mov     rax, [rax+0B8h]
0x14001bd5c  mov     [rax-10h], rcx
0x14001bd60  lea     rcx, [rsp+98h+Event]
0x14001bd65  mov     [rax-8], rcx
0x14001bd69  mov     rcx, rbx; DeviceObject
0x14001bd6c  mov     byte ptr [rax-45h], 0E0h
0x14001bd70  mov     rax, [rbp+0B8h]
0x14001bd77  mov     [rax-38h], r12d
0x14001bd7b  xor     r12d, r12d
0x14001bd7e  mov     word ptr [rax-48h], 0Dh
0x14001bd84  mov     [rax-18h], r15
0x14001bd88  mov     [rax-20h], rbx
0x14001bd8c  mov     [rax-40h], esi
0x14001bd8f  mov     dword ptr [rax-30h], 60194h
0x14001bd96  mov     [rbp+8], r12
0x14001bd9a  mov     [rbp+18h], rdi
0x14001bd9e  mov     [rbp+70h], rdi
0x14001bda2  mov     dword ptr [rbp+10h], 50h ; 'P'
0x14001bda9  call    cs:__imp_IofCallDriver
0x14001bdb0  nop     dword ptr [rax+rax+00h]
0x14001bdb5  mov     ebx, eax
0x14001bdb7  cmp     eax, 103h
0x14001bdbc  jz      loc_14001BECF
0x14001bdc2  mov     r15d, [rbp+38h]
0x14001bdc6  mov     rcx, rbp; Irp
0x14001bdc9  call    cs:__imp_IoFreeIrp
0x14001bdd0  nop     dword ptr [rax+rax+00h]
0x14001bdd5  cmp     ebx, 80000005h
0x14001bddb  jz      loc_14001BE6B
0x14001bde1  test    ebx, ebx
0x14001bde3  jns     loc_14001BF6B
0x14001bde9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bdf0  lea     rax, WPP_GLOBAL_Control
0x14001bdf7  cmp     rcx, rax
0x14001bdfa  jz      short loc_14001BE09
0x14001bdfc  test    dword ptr [rcx+2Ch], 200000h
0x14001be03  jnz     loc_14001BF88
0x14001be09  xor     edx, edx; Tag
0x14001be0b  mov     rcx, rdi; P
0x14001be0e  call    cs:__imp_ExFreePoolWithTag
0x14001be15  nop     dword ptr [rax+rax+00h]
0x14001be1a  mov     rdi, r12
0x14001be1d  mov     rcx, [rsp+98h+arg_20]
0x14001be25  mov     eax, ebx
0x14001be27  mov     [rcx], rdi
0x14001be2a  add     rsp, 58h
0x14001be2e  pop     r15
0x14001be30  pop     r14
0x14001be32  pop     r13
0x14001be34  pop     r12
0x14001be36  pop     rdi
0x14001be37  pop     rsi
0x14001be38  pop     rbp
0x14001be39  pop     rbx
0x14001be3a  retn
0x14001be3c  test    dword ptr [rcx+2Ch], 200000h
0x14001be43  jz      loc_14001BCB7
0x14001be49  mov     rcx, [rcx+18h]
0x14001be4d  lea     r8, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids
0x14001be54  mov     edx, 17h
0x14001be59  mov     [rsp+98h+Timeout], rbx
0x14001be5e  mov     r9, rdi
0x14001be61  call    WPP_SF_qS
0x14001be66  jmp     loc_14001BCB7
0x14001be6b  cmp     esi, 0E000h
0x14001be71  jnb     loc_14001BDE9
0x14001be77  mov     rcx, cs:WPP_GLOBAL_Control
0x14001be7e  lea     r15, WPP_GLOBAL_Control
0x14001be85  cmp     rcx, r15
0x14001be88  jnz     loc_14001BF41
0x14001be8e  xor     edx, edx; Tag
0x14001be90  mov     rcx, rdi; P
0x14001be93  call    cs:__imp_ExFreePoolWithTag
0x14001be9a  nop     dword ptr [rax+rax+00h]
0x14001be9f  mov     rbp, [rsp+98h+arg_10]
0x14001bea7  lea     eax, [rsi+rsi]
0x14001beaa  mov     ebx, 0E000h
0x14001beaf  mov     esi, eax
0x14001beb1  cmp     eax, ebx
0x14001beb3  cmova   esi, ebx
0x14001beb6  jmp     loc_14001BC61
0x14001bebb  mov     rdx, [r14+8]; Src
0x14001bebf  mov     r8, rax; Size
0x14001bec2  mov     rcx, rbx; void *
0x14001bec5  call    memmove
0x14001beca  jmp     loc_14001BC9B
0x14001becf  xor     r8d, r8d; Irp
0x14001bed2  lea     rcx, [rsp+98h+Event]; Object
0x14001bed7  xor     edx, edx; Timeout
0x14001bed9  call    cs:__imp_FsRtlCancellableWaitForSingleObject
0x14001bee0  nop     dword ptr [rax+rax+00h]
0x14001bee5  cmp     eax, 0C0000120h
0x14001beea  jz      short loc_14001BEF3
0x14001beec  cmp     eax, 0C000004Bh
0x14001bef1  jnz     short loc_14001BF39
0x14001bef3  mov     rcx, rbp; Irp
0x14001bef6  call    cs:__imp_IoCancelIrp
0x14001befd  nop     dword ptr [rax+rax+00h]
0x14001bf02  test    al, al
0x14001bf04  jz      short loc_14001BF1B
0x14001bf06  lea     rcx, [rsp+98h+Event]; Event
0x14001bf0b  call    cs:__imp_KeReadStateEvent
0x14001bf12  nop     dword ptr [rax+rax+00h]
0x14001bf17  test    eax, eax
0x14001bf19  jnz     short loc_14001BF39
0x14001bf1b  xor     r9d, r9d; Alertable
0x14001bf1e  mov     [rsp+98h+Timeout], r12; Timeout
0x14001bf23  xor     r8d, r8d; WaitMode
0x14001bf26  lea     rcx, [rsp+98h+Event]; Object
0x14001bf2b  xor     edx, edx; WaitReason
0x14001bf2d  call    cs:__imp_KeWaitForSingleObject
0x14001bf34  nop     dword ptr [rax+rax+00h]
0x14001bf39  mov     ebx, [rbp+30h]
0x14001bf3c  jmp     loc_14001BDC2
0x14001bf41  test    dword ptr [rcx+2Ch], 100000h
0x14001bf48  jz      loc_14001BE8E
0x14001bf4e  mov     rcx, [rcx+18h]
0x14001bf52  lea     r8, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids
0x14001bf59  mov     edx, 18h
0x14001bf5e  mov     r9, rdi
0x14001bf61  call    WPP_SF_q
0x14001bf66  jmp     loc_14001BE8E
0x14001bf6b  mov     rax, [rsp+98h+arg_28]
0x14001bf73  mov     [rax], r15d
0x14001bf76  jmp     loc_14001BE1D
0x14001bf7b  mov     ebx, 0C000009Ah
0x14001bf80  xor     r12d, r12d
0x14001bf83  jmp     loc_14001BDE9
0x14001bf88  mov     rcx, [rcx+18h]
0x14001bf8c  lea     r8, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids
0x14001bf93  mov     edx, 19h
0x14001bf98  mov     r9, rdi
0x14001bf9b  call    WPP_SF_q
0x14001bfa0  jmp     loc_14001BE09
0x14001bfa5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bfac  cmp     rcx, r15
0x14001bfaf  jz      short loc_14001BFD2
0x14001bfb1  test    dword ptr [rcx+2Ch], 100000h
0x14001bfb8  jz      short loc_14001BFD2
0x14001bfba  mov     rcx, [rcx+18h]
0x14001bfbe  lea     r8, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids
0x14001bfc5  mov     edx, 16h
0x14001bfca  mov     r9d, esi
0x14001bfcd  call    WPP_SF_D
0x14001bfd2  mov     ebx, 0C000009Ah
0x14001bfd7  jmp     loc_14001BE1D
```
