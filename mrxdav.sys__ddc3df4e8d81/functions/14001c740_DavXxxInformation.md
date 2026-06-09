# DavXxxInformation

- ea: `0x14001c740`
- end: `0x14001c8f7`
- name: `DavXxxInformation`
- size: `439`
- prototype: `__int64 __fastcall(UCHAR, struct _FILE_OBJECT *, ULONG, ULONG, struct _IRP *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140022a80`
- `0x1400241b0`

## callees

- `0x14000163c`
- `0x14001c740`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c7b4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c7b4`
- `ntoskrnl!KeInitializeEvent` at `0x14001c84f`
- `ntoskrnl!KeInitializeEvent` at `0x14001c84f`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14001c85c`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14001c85c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001c872`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001c899`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140028ffd`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001c872`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001c899`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140028ffd`
- `ntoskrnl!IofCallDriver` at `0x14001c884`
- `ntoskrnl!IofCallDriver` at `0x14001c884`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c8c3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c8c3`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14001c76c`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14001c76c`
- `ntoskrnl!IoAllocateIrp` at `0x14001c780`
- `ntoskrnl!IoAllocateIrp` at `0x14001c780`
- `ntoskrnl!IoFreeIrp` at `0x14001c8da`
- `ntoskrnl!IoFreeIrp` at `0x14001c8da`

## pseudocode

```c
__int64 __fastcall DavXxxInformation(UCHAR a1, struct _FILE_OBJECT *a2, ULONG a3, ULONG a4, struct _IRP *a5)
{
  PDEVICE_OBJECT RelatedDeviceObject; // rbx
  PIRP Irp; // rax
  IRP *v11; // rdi
  __int64 v12; // rbx
  HANDLE CurrentThreadId; // rax
  unsigned int Status; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IO_STACK_LOCATION *v16; // rax
  IRP *TopLevelIrp; // [rsp+38h] [rbp-60h]
  struct _KEVENT Event; // [rsp+40h] [rbp-58h] BYREF

  memset(&Event, 0, sizeof(Event));
  RelatedDeviceObject = IoGetRelatedDeviceObject(a2);
  Irp = IoAllocateIrp(RelatedDeviceObject->StackSize, 1u);
  v11 = Irp;
  if ( Irp )
  {
    Irp->Tail.Overlay.OriginalFileObject = a2;
    Irp->Tail.Overlay.Thread = KeGetCurrentThread();
    Irp->RequestorMode = 0;
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].MajorFunction = a1;
    CurrentStackLocation[-1].FileObject = a2;
    v16 = Irp->Tail.Overlay.CurrentStackLocation;
    v16[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&DavReadWriteIrpCompletionRoutine;
    v16[-1].Context = &Event;
    v16[-1].Control = -32;
    v11->AssociatedIrp.MasterIrp = a5;
    CurrentStackLocation[-1].Parameters.Read.Length = a4;
    CurrentStackLocation[-1].Parameters.Create.Options = a3;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    TopLevelIrp = IoGetTopLevelIrp();
    IoSetTopLevelIrp(0);
    Status = IofCallDriver(RelatedDeviceObject, v11);
    IoSetTopLevelIrp(TopLevelIrp);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v11->IoStatus.Status;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v12, 10, WPP_6ba8396c2d573372635dfed7cc8d762f_Traceguids, CurrentThreadId);
    }
    Status = -1073741670;
  }
  if ( v11 )
    IoFreeIrp(v11);
  return Status;
}

```

## disassembly

```asm
0x14001c740  push    rbx
0x14001c742  push    rsi
0x14001c743  push    rdi
0x14001c744  push    r12
0x14001c746  push    r14
0x14001c748  push    r15
0x14001c74a  sub     rsp, 68h
0x14001c74e  mov     r14d, r9d
0x14001c751  mov     r15d, r8d
0x14001c754  mov     rsi, rdx
0x14001c757  mov     r12d, ecx
0x14001c75a  xorps   xmm0, xmm0
0x14001c75d  xor     eax, eax
0x14001c75f  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x14001c764  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x14001c769  mov     rcx, rdx; FileObject
0x14001c76c  call    cs:__imp_IoGetRelatedDeviceObject
0x14001c773  nop     dword ptr [rax+rax+00h]
0x14001c778  mov     rbx, rax
0x14001c77b  mov     dl, 1; ChargeQuota
0x14001c77d  mov     cl, [rax+4Ch]; StackSize
0x14001c780  call    cs:__imp_IoAllocateIrp
0x14001c787  nop     dword ptr [rax+rax+00h]
0x14001c78c  mov     rdi, rax
0x14001c78f  test    rax, rax
0x14001c792  jnz     short loc_14001C7DF
0x14001c794  lea     rax, WPP_GLOBAL_Control
0x14001c79b  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c7a2  cmp     rbx, rax
0x14001c7a5  jz      short loc_14001C7D5
0x14001c7a7  test    dword ptr [rbx+2Ch], 4000h
0x14001c7ae  jz      short loc_14001C7D5
0x14001c7b0  mov     rbx, [rbx+18h]
0x14001c7b4  call    cs:__imp_PsGetCurrentThreadId
0x14001c7bb  nop     dword ptr [rax+rax+00h]
0x14001c7c0  mov     r9, rax
0x14001c7c3  lea     edx, [rdi+0Ah]
0x14001c7c6  lea     r8, WPP_6ba8396c2d573372635dfed7cc8d762f_Traceguids
0x14001c7cd  mov     rcx, rbx
0x14001c7d0  call    WPP_SF_q
0x14001c7d5  mov     ebx, 0C000009Ah
0x14001c7da  jmp     loc_14001C8D2
0x14001c7df  mov     [rsp+98h+var_60], 0
0x14001c7e8  mov     [rax+0C0h], rsi
0x14001c7ef  mov     rax, gs:188h
0x14001c7f8  mov     [rdi+98h], rax
0x14001c7ff  mov     byte ptr [rdi+40h], 0
0x14001c803  mov     rcx, [rdi+0B8h]
0x14001c80a  mov     [rcx-48h], r12b
0x14001c80e  mov     [rcx-18h], rsi
0x14001c812  mov     rax, [rdi+0B8h]
0x14001c819  lea     rdx, DavReadWriteIrpCompletionRoutine
0x14001c820  mov     [rax-10h], rdx
0x14001c824  lea     rdx, [rsp+98h+Event]
0x14001c829  mov     [rax-8], rdx
0x14001c82d  mov     byte ptr [rax-45h], 0E0h
0x14001c831  mov     rax, [rsp+98h+arg_20]
0x14001c839  mov     [rdi+18h], rax
0x14001c83d  mov     [rcx-40h], r14d
0x14001c841  mov     [rcx-38h], r15d
0x14001c845  xor     r8d, r8d; State
0x14001c848  xor     edx, edx; Type
0x14001c84a  lea     rcx, [rsp+98h+Event]; Event
0x14001c84f  call    cs:__imp_KeInitializeEvent
0x14001c856  nop     dword ptr [rax+rax+00h]
0x14001c85b  nop
0x14001c85c  call    cs:__imp_IoGetTopLevelIrp
0x14001c863  nop     dword ptr [rax+rax+00h]
0x14001c868  mov     rsi, rax
0x14001c86b  mov     [rsp+98h+var_60], rax
0x14001c870  xor     ecx, ecx; Irp
0x14001c872  call    cs:__imp_IoSetTopLevelIrp
0x14001c879  nop     dword ptr [rax+rax+00h]
0x14001c87e  mov     rdx, rdi; Irp
0x14001c881  mov     rcx, rbx; DeviceObject
0x14001c884  call    cs:__imp_IofCallDriver
0x14001c88b  nop     dword ptr [rax+rax+00h]
0x14001c890  mov     ebx, eax
0x14001c892  mov     [rsp+98h+var_68], eax
0x14001c896  mov     rcx, rsi; Irp
0x14001c899  call    cs:__imp_IoSetTopLevelIrp
0x14001c8a0  nop     dword ptr [rax+rax+00h]
0x14001c8a5  cmp     ebx, 103h
0x14001c8ab  jnz     short loc_14001C8D2
0x14001c8ad  mov     [rsp+98h+Timeout], 0; Timeout
0x14001c8b6  xor     r9d, r9d; Alertable
0x14001c8b9  xor     r8d, r8d; WaitMode
0x14001c8bc  xor     edx, edx; WaitReason
0x14001c8be  lea     rcx, [rsp+98h+Event]; Object
0x14001c8c3  call    cs:__imp_KeWaitForSingleObject
0x14001c8ca  nop     dword ptr [rax+rax+00h]
0x14001c8cf  mov     ebx, [rdi+30h]
0x14001c8d2  test    rdi, rdi
0x14001c8d5  jz      short loc_14001C8E6
0x14001c8d7  mov     rcx, rdi; Irp
0x14001c8da  call    cs:__imp_IoFreeIrp
0x14001c8e1  nop     dword ptr [rax+rax+00h]
0x14001c8e6  mov     eax, ebx
0x14001c8e8  add     rsp, 68h
0x14001c8ec  pop     r15
0x14001c8ee  pop     r14
0x14001c8f0  pop     r12
0x14001c8f2  pop     rdi
0x14001c8f3  pop     rsi
0x14001c8f4  pop     rbx
0x14001c8f5  retn
0x140028ff0  push    rbp
0x140028ff2  sub     rsp, 30h
0x140028ff6  mov     rbp, rdx
0x140028ff9  mov     rcx, [rbp+38h]; Irp
0x140028ffd  call    cs:__imp_IoSetTopLevelIrp
0x140029004  nop     dword ptr [rax+rax+00h]
0x140029009  nop
0x14002900a  add     rsp, 30h
0x14002900e  pop     rbp
0x14002900f  retn
```
