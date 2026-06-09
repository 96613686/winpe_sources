# DfscRmSendSynchFsctlIrp

- ea: `0x14002747c`
- end: `0x140027648`
- name: `DfscRmSendSynchFsctlIrp`
- size: `460`
- prototype: `__int64 __fastcall(DWORD, struct _FILE_OBJECT *, struct _IRP *, ULONG, void *, ULONG, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400195dc`

## callees

- `0x14002747c`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400274be`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400274be`
- `ntoskrnl!IoFreeIrp` at `0x1400275ac`
- `ntoskrnl!IoFreeIrp` at `0x1400275ac`
- `ntoskrnl!IoAllocateIrp` at `0x1400274d4`
- `ntoskrnl!IoAllocateIrp` at `0x1400274d4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002762a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002762a`
- `ntoskrnl!KeReadStateEvent` at `0x140027604`
- `ntoskrnl!KeReadStateEvent` at `0x140027604`
- `ntoskrnl!IoCancelIrp` at `0x1400275ef`
- `ntoskrnl!IoCancelIrp` at `0x1400275ef`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x1400275d2`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x1400275d2`
- `ntoskrnl!IofCallDriver` at `0x140027587`
- `ntoskrnl!IofCallDriver` at `0x140027587`
- `ntoskrnl!KeInitializeEvent` at `0x1400274af`
- `ntoskrnl!KeInitializeEvent` at `0x1400274af`

## pseudocode

```c
__int64 __fastcall DfscRmSendSynchFsctlIrp(
        DWORD a1,
        struct _FILE_OBJECT *a2,
        struct _IRP *a3,
        ULONG a4,
        void *a5,
        ULONG a6,
        _DWORD *a7)
{
  PDEVICE_OBJECT RelatedDeviceObject; // rdi
  PIRP Irp; // rax
  PIRP v13; // rbx
  IRP *v14; // rdx
  struct _KTHREAD *CurrentThread; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v17; // rcx
  unsigned int Status; // edi
  NTSTATUS v20; // eax
  struct _KEVENT Event; // [rsp+30h] [rbp-58h] BYREF

  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  RelatedDeviceObject = IoGetRelatedDeviceObject(a2);
  Irp = IoAllocateIrp(RelatedDeviceObject->StackSize + 1, 0);
  v13 = Irp;
  if ( !Irp )
    return 3221225626LL;
  Irp->RequestorMode = 0;
  v14 = Irp;
  Irp->Tail.Overlay.OriginalFileObject = a2;
  CurrentThread = KeGetCurrentThread();
  --Irp->Tail.Overlay.CurrentStackLocation;
  --Irp->CurrentLocation;
  Irp->Tail.Overlay.Thread = CurrentThread;
  Irp->Tail.Overlay.CurrentStackLocation->DeviceObject = RelatedDeviceObject;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)DfscRmCompletionRoutine;
  CurrentStackLocation[-1].Context = &Event;
  CurrentStackLocation[-1].Control = -32;
  v17 = v13->Tail.Overlay.CurrentStackLocation;
  v17[-1].Parameters.Read.Length = a6;
  *(_WORD *)&v17[-1].MajorFunction = 13;
  v17[-1].FileObject = a2;
  v17[-1].DeviceObject = RelatedDeviceObject;
  v17[-1].Parameters.Create.Options = a4;
  v17[-1].Parameters.Read.ByteOffset.LowPart = a1;
  v13->UserBuffer = a5;
  v13->MdlAddress = 0;
  v13->AssociatedIrp.MasterIrp = a3;
  v13->Flags = 80;
  Status = IofCallDriver(RelatedDeviceObject, v14);
  if ( Status == 259 )
  {
    v20 = FsRtlCancellableWaitForSingleObject(&Event, 0, 0);
    if ( (v20 == -1073741536 || v20 == -1073741749) && (!IoCancelIrp(v13) || !KeReadStateEvent(&Event)) )
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = v13->IoStatus.Status;
  }
  *a7 = v13->IoStatus.Information;
  IoFreeIrp(v13);
  return Status;
}

```

## disassembly

```asm
0x14002747c  push    rbx
0x14002747e  push    rbp
0x14002747f  push    rsi
0x140027480  push    rdi
0x140027481  push    r14
0x140027483  push    r15
0x140027485  sub     rsp, 58h
0x140027489  xor     eax, eax
0x14002748b  mov     r14, r8
0x14002748e  mov     rsi, rdx
0x140027491  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x140027496  mov     r15d, ecx
0x140027499  xorps   xmm0, xmm0
0x14002749c  xor     r8d, r8d; State
0x14002749f  lea     rcx, [rsp+88h+Event]; Event
0x1400274a4  lea     edx, [rax+1]; Type
0x1400274a7  mov     ebp, r9d
0x1400274aa  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x1400274af  call    cs:__imp_KeInitializeEvent
0x1400274b6  nop     dword ptr [rax+rax+00h]
0x1400274bb  mov     rcx, rsi; FileObject
0x1400274be  call    cs:__imp_IoGetRelatedDeviceObject
0x1400274c5  nop     dword ptr [rax+rax+00h]
0x1400274ca  xor     edx, edx; ChargeQuota
0x1400274cc  mov     rdi, rax
0x1400274cf  mov     cl, [rax+4Ch]
0x1400274d2  inc     cl; StackSize
0x1400274d4  call    cs:__imp_IoAllocateIrp
0x1400274db  nop     dword ptr [rax+rax+00h]
0x1400274e0  mov     rbx, rax
0x1400274e3  test    rax, rax
0x1400274e6  jz      loc_14002763E
0x1400274ec  mov     byte ptr [rax+40h], 0
0x1400274f0  mov     rdx, rbx; Irp
0x1400274f3  mov     [rax+0C0h], rsi
0x1400274fa  mov     rcx, gs:188h
0x140027503  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x14002750b  dec     byte ptr [rax+43h]
0x14002750e  mov     [rax+98h], rcx
0x140027515  mov     rcx, [rax+0B8h]
0x14002751c  mov     [rcx+28h], rdi
0x140027520  lea     rcx, DfscRmCompletionRoutine
0x140027527  mov     rax, [rax+0B8h]
0x14002752e  mov     [rax-10h], rcx
0x140027532  lea     rcx, [rsp+88h+Event]
0x140027537  mov     [rax-8], rcx
0x14002753b  mov     byte ptr [rax-45h], 0E0h
0x14002753f  mov     rcx, [rbx+0B8h]
0x140027546  mov     eax, [rsp+88h+arg_28]
0x14002754d  mov     [rcx-40h], eax
0x140027550  mov     rax, [rsp+88h+arg_20]
0x140027558  mov     word ptr [rcx-48h], 0Dh
0x14002755e  mov     [rcx-18h], rsi
0x140027562  mov     [rcx-20h], rdi
0x140027566  mov     [rcx-38h], ebp
0x140027569  mov     [rcx-30h], r15d
0x14002756d  mov     rcx, rdi; DeviceObject
0x140027570  mov     [rbx+70h], rax
0x140027574  mov     qword ptr [rbx+8], 0
0x14002757c  mov     [rbx+18h], r14
0x140027580  mov     dword ptr [rbx+10h], 50h ; 'P'
0x140027587  call    cs:__imp_IofCallDriver
0x14002758e  nop     dword ptr [rax+rax+00h]
0x140027593  mov     edi, eax
0x140027595  cmp     eax, 103h
0x14002759a  jz      short loc_1400275C8
0x14002759c  mov     ecx, [rbx+38h]
0x14002759f  mov     rax, [rsp+88h+arg_30]
0x1400275a7  mov     [rax], ecx
0x1400275a9  mov     rcx, rbx; Irp
0x1400275ac  call    cs:__imp_IoFreeIrp
0x1400275b3  nop     dword ptr [rax+rax+00h]
0x1400275b8  mov     eax, edi
0x1400275ba  add     rsp, 58h
0x1400275be  pop     r15
0x1400275c0  pop     r14
0x1400275c2  pop     rdi
0x1400275c3  pop     rsi
0x1400275c4  pop     rbp
0x1400275c5  pop     rbx
0x1400275c6  retn
0x1400275c8  xor     r8d, r8d; Irp
0x1400275cb  lea     rcx, [rsp+88h+Event]; Object
0x1400275d0  xor     edx, edx; Timeout
0x1400275d2  call    cs:__imp_FsRtlCancellableWaitForSingleObject
0x1400275d9  nop     dword ptr [rax+rax+00h]
0x1400275de  cmp     eax, 0C0000120h
0x1400275e3  jz      short loc_1400275EC
0x1400275e5  cmp     eax, 0C000004Bh
0x1400275ea  jnz     short loc_140027636
0x1400275ec  mov     rcx, rbx; Irp
0x1400275ef  call    cs:__imp_IoCancelIrp
0x1400275f6  nop     dword ptr [rax+rax+00h]
0x1400275fb  test    al, al
0x1400275fd  jz      short loc_140027614
0x1400275ff  lea     rcx, [rsp+88h+Event]; Event
0x140027604  call    cs:__imp_KeReadStateEvent
0x14002760b  nop     dword ptr [rax+rax+00h]
0x140027610  test    eax, eax
0x140027612  jnz     short loc_140027636
0x140027614  xor     r9d, r9d; Alertable
0x140027617  mov     [rsp+88h+Timeout], 0; Timeout
0x140027620  xor     r8d, r8d; WaitMode
0x140027623  lea     rcx, [rsp+88h+Event]; Object
0x140027628  xor     edx, edx; WaitReason
0x14002762a  call    cs:__imp_KeWaitForSingleObject
0x140027631  nop     dword ptr [rax+rax+00h]
0x140027636  mov     edi, [rbx+30h]
0x140027639  jmp     loc_14002759C
0x14002763e  mov     eax, 0C000009Ah
0x140027643  jmp     loc_1400275BA
```
