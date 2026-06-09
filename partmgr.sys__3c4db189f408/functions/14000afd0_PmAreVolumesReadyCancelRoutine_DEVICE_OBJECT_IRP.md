# PmAreVolumesReadyCancelRoutine(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14000afd0`
- end: `0x14000b076`
- name: `?PmAreVolumesReadyCancelRoutine@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `166`
- prototype: `void(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000afd0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000b005`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b005`
- `ntoskrnl!IofCompleteRequest` at `0x14000b057`
- `ntoskrnl!IofCompleteRequest` at `0x14000b057`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000afe4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000afe4`
- `ntoskrnl!KeReleaseMutex` at `0x14000b037`
- `ntoskrnl!KeReleaseMutex` at `0x14000b037`

## pseudocode

```c
void __fastcall PmAreVolumesReadyCancelRoutine(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _KMUTANT *DeviceExtension; // rbx
  struct _LIST_ENTRY *Flink; // r8
  struct _LIST_ENTRY *Blink; // rax

  DeviceExtension = (struct _KMUTANT *)a1->DeviceExtension;
  IoReleaseCancelSpinLock(a2->CancelIrql);
  KeWaitForSingleObject(&DeviceExtension[1], Executive, 0, 0, 0);
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  if ( (PVOID *)Flink->Blink != &a2->Tail.CompletionKey + 6
    || (Blink = a2->Tail.Overlay.ListEntry.Blink, (PVOID *)Blink->Flink != &a2->Tail.CompletionKey + 6) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  KeReleaseMutex(DeviceExtension + 1, 0);
  a2->IoStatus.Status = -1073741536;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x14000afd0  mov     [rsp+arg_0], rbx
0x14000afd5  push    rdi
0x14000afd6  sub     rsp, 30h
0x14000afda  mov     rbx, [rcx+40h]
0x14000afde  mov     rdi, rdx
0x14000afe1  mov     cl, [rdx+45h]; Irql
0x14000afe4  call    cs:__imp_IoReleaseCancelSpinLock
0x14000afeb  nop     dword ptr [rax+rax+00h]
0x14000aff0  xor     r9d, r9d; Alertable
0x14000aff3  mov     [rsp+38h+Timeout], 0; Timeout
0x14000affc  xor     r8d, r8d; WaitMode
0x14000afff  lea     rcx, [rbx+38h]; Object
0x14000b003  xor     edx, edx; WaitReason
0x14000b005  call    cs:__imp_KeWaitForSingleObject
0x14000b00c  nop     dword ptr [rax+rax+00h]
0x14000b011  lea     rdx, [rdi+0A8h]
0x14000b018  mov     r8, [rdx]
0x14000b01b  cmp     [r8+8], rdx
0x14000b01f  jnz     short loc_14000B06F
0x14000b021  mov     rax, [rdx+8]
0x14000b025  cmp     [rax], rdx
0x14000b028  jnz     short loc_14000B06F
0x14000b02a  mov     [rax], r8
0x14000b02d  lea     rcx, [rbx+38h]; Mutex
0x14000b031  xor     edx, edx; Wait
0x14000b033  mov     [r8+8], rax
0x14000b037  call    cs:__imp_KeReleaseMutex
0x14000b03e  nop     dword ptr [rax+rax+00h]
0x14000b043  xor     edx, edx; PriorityBoost
0x14000b045  mov     dword ptr [rdi+30h], 0C0000120h
0x14000b04c  mov     rcx, rdi; Irp
0x14000b04f  mov     qword ptr [rdi+38h], 0
0x14000b057  call    cs:__imp_IofCompleteRequest
0x14000b05e  nop     dword ptr [rax+rax+00h]
0x14000b063  mov     rbx, [rsp+38h+arg_0]
0x14000b068  add     rsp, 30h
0x14000b06c  pop     rdi
0x14000b06d  retn
0x14000b06f  mov     ecx, 3
0x14000b074  int     29h; Win8: RtlFailFast(ecx)
```
