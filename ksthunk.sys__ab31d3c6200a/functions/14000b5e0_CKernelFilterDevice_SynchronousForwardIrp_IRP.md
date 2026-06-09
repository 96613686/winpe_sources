# CKernelFilterDevice::SynchronousForwardIrp(_IRP *)

- ea: `0x14000b5e0`
- end: `0x14000b6ac`
- name: `?SynchronousForwardIrp@CKernelFilterDevice@@QEAAJPEAU_IRP@@@Z`
- size: `204`
- prototype: `int __fastcall(PDEVICE_OBJECT *this, struct _IRP *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001ba0`
- `0x14000bcc0`
- `0x14000bd80`

## callees

- `0x14000b5e0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000b60a`
- `ntoskrnl!KeInitializeEvent` at `0x14000b60a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b691`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b691`
- `ntoskrnl!IofCallDriver` at `0x14000b668`
- `ntoskrnl!IofCallDriver` at `0x14000b668`

## pseudocode

```c
int __fastcall CKernelFilterDevice::SynchronousForwardIrp(PDEVICE_OBJECT *this, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v5; // rax
  int result; // eax
  struct _KEVENT Event; // [rsp+30h] [rbp-28h] BYREF

  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  v5 = a2->Tail.Overlay.CurrentStackLocation;
  v5[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)CKernelFilterDevice::DeferIrpCompletion;
  v5[-1].Context = &Event;
  v5[-1].Control = -32;
  result = IofCallDriver(this[7], a2);
  if ( result == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    return a2->IoStatus.Status;
  }
  return result;
}

```

## disassembly

```asm
0x14000b5e0  mov     [rsp+arg_0], rbx
0x14000b5e5  push    rdi
0x14000b5e6  sub     rsp, 50h
0x14000b5ea  xor     eax, eax
0x14000b5ec  mov     rdi, rdx
0x14000b5ef  mov     rbx, rcx
0x14000b5f2  mov     [rsp+58h+Event.Header.WaitListHead.Blink], rax
0x14000b5f7  xorps   xmm0, xmm0
0x14000b5fa  lea     rcx, [rsp+58h+Event]; Event
0x14000b5ff  xor     r8d, r8d; State
0x14000b602  lea     edx, [rax+1]; Type
0x14000b605  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x14000b60a  call    cs:__imp_KeInitializeEvent
0x14000b611  nop     dword ptr [rax+rax+00h]
0x14000b616  mov     rax, [rdi+0B8h]
0x14000b61d  lea     rcx, ?DeferIrpCompletion@CKernelFilterDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAU_KEVENT@@@Z; CKernelFilterDevice::DeferIrpCompletion(_DEVICE_OBJECT *,_IRP *,_KEVENT *)
0x14000b624  mov     rdx, rdi; Irp
0x14000b627  movups  xmm0, xmmword ptr [rax]
0x14000b62a  movups  xmmword ptr [rax-48h], xmm0
0x14000b62e  movups  xmm1, xmmword ptr [rax+10h]
0x14000b632  movups  xmmword ptr [rax-38h], xmm1
0x14000b636  movups  xmm0, xmmword ptr [rax+20h]
0x14000b63a  movups  xmmword ptr [rax-28h], xmm0
0x14000b63e  movsd   xmm1, qword ptr [rax+30h]
0x14000b643  movsd   qword ptr [rax-18h], xmm1
0x14000b648  mov     byte ptr [rax-45h], 0
0x14000b64c  mov     rax, [rdi+0B8h]
0x14000b653  mov     [rax-10h], rcx
0x14000b657  lea     rcx, [rsp+58h+Event]
0x14000b65c  mov     [rax-8], rcx
0x14000b660  mov     byte ptr [rax-45h], 0E0h
0x14000b664  mov     rcx, [rbx+38h]; DeviceObject
0x14000b668  call    cs:__imp_IofCallDriver
0x14000b66f  nop     dword ptr [rax+rax+00h]
0x14000b674  cmp     eax, 103h
0x14000b679  jnz     short loc_14000B6A0
0x14000b67b  xor     r9d, r9d; Alertable
0x14000b67e  mov     [rsp+58h+Timeout], 0; Timeout
0x14000b687  xor     r8d, r8d; WaitMode
0x14000b68a  lea     rcx, [rsp+58h+Event]; Object
0x14000b68f  xor     edx, edx; WaitReason
0x14000b691  call    cs:__imp_KeWaitForSingleObject
0x14000b698  nop     dword ptr [rax+rax+00h]
0x14000b69d  mov     eax, [rdi+30h]
0x14000b6a0  mov     rbx, [rsp+58h+arg_0]
0x14000b6a5  add     rsp, 50h
0x14000b6a9  pop     rdi
0x14000b6aa  retn
```
