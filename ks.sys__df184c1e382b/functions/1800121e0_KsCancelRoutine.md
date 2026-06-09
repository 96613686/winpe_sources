# KsCancelRoutine

- ea: `0x1800121e0`
- end: `0x180012272`
- name: `KsCancelRoutine`
- size: `146`
- prototype: `DRIVER_CANCEL`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017bf0`

## callees

- `0x1800121e0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1800121f7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1800121f7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x180012226`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x180012226`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180012235`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180012235`
- `ntoskrnl!IofCompleteRequest` at `0x180012253`
- `ntoskrnl!IofCompleteRequest` at `0x180012253`

## pseudocode

```c
void __stdcall KsCancelRoutine(struct _DEVICE_OBJECT *DeviceObject, struct _IRP *Irp)
{
  struct _LIST_ENTRY *Blink; // rdi
  struct _LIST_ENTRY *Flink; // r8
  struct _LIST_ENTRY *v5; // rdx

  Blink = Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink;
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)Blink);
  Flink = Irp->Tail.Overlay.ListEntry.Flink;
  if ( (PVOID *)Flink->Blink != &Irp->Tail.CompletionKey + 6
    || (v5 = Irp->Tail.Overlay.ListEntry.Blink, (PVOID *)v5->Flink != &Irp->Tail.CompletionKey + 6) )
  {
    __fastfail(3u);
  }
  v5->Flink = Flink;
  Flink->Blink = v5;
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)Blink);
  IoReleaseCancelSpinLock(Irp->CancelIrql);
  if ( Irp->IoStatus.Status != -1073741536 )
  {
    Irp->IoStatus.Status = -1073741536;
    IofCompleteRequest(Irp, 0);
  }
}

```

## disassembly

```asm
0x1800121e0  mov     [rsp+arg_0], rbx
0x1800121e5  push    rdi
0x1800121e6  sub     rsp, 20h
0x1800121ea  mov     rdi, [rdx+80h]
0x1800121f1  mov     rbx, rdx
0x1800121f4  mov     rcx, rdi; SpinLock
0x1800121f7  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1800121fe  nop     dword ptr [rax+rax+00h]
0x180012203  lea     rax, [rbx+0A8h]
0x18001220a  mov     r8, [rax]
0x18001220d  cmp     [r8+8], rax
0x180012211  jnz     short loc_18001226B
0x180012213  mov     rdx, [rax+8]
0x180012217  cmp     [rdx], rax
0x18001221a  jnz     short loc_18001226B
0x18001221c  mov     [rdx], r8
0x18001221f  mov     rcx, rdi; SpinLock
0x180012222  mov     [r8+8], rdx
0x180012226  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x18001222d  nop     dword ptr [rax+rax+00h]
0x180012232  mov     cl, [rbx+45h]; Irql
0x180012235  call    cs:__imp_IoReleaseCancelSpinLock
0x18001223c  nop     dword ptr [rax+rax+00h]
0x180012241  mov     eax, 0C0000120h
0x180012246  cmp     [rbx+30h], eax
0x180012249  jz      short loc_18001225F
0x18001224b  xor     edx, edx; PriorityBoost
0x18001224d  mov     [rbx+30h], eax
0x180012250  mov     rcx, rbx; Irp
0x180012253  call    cs:__imp_IofCompleteRequest
0x18001225a  nop     dword ptr [rax+rax+00h]
0x18001225f  mov     rbx, [rsp+28h+arg_0]
0x180012264  add     rsp, 20h
0x180012268  pop     rdi
0x180012269  retn
0x18001226b  mov     ecx, 3
0x180012270  int     29h; Win8: RtlFailFast(ecx)
```
