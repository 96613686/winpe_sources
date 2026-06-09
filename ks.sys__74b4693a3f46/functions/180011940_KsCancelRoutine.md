# KsCancelRoutine

- ea: `0x180011940`
- end: `0x1800119d2`
- name: `KsCancelRoutine`
- size: `146`
- prototype: `DRIVER_CANCEL`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017ba0`

## callees

- `0x180011940`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x180011957`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x180011957`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x180011986`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x180011986`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180011995`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180011995`
- `ntoskrnl!IofCompleteRequest` at `0x1800119b3`
- `ntoskrnl!IofCompleteRequest` at `0x1800119b3`

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
0x180011940  mov     [rsp+arg_0], rbx
0x180011945  push    rdi
0x180011946  sub     rsp, 20h
0x18001194a  mov     rdi, [rdx+80h]
0x180011951  mov     rbx, rdx
0x180011954  mov     rcx, rdi; SpinLock
0x180011957  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x18001195e  nop     dword ptr [rax+rax+00h]
0x180011963  lea     rax, [rbx+0A8h]
0x18001196a  mov     r8, [rax]
0x18001196d  cmp     [r8+8], rax
0x180011971  jnz     short loc_1800119CB
0x180011973  mov     rdx, [rax+8]
0x180011977  cmp     [rdx], rax
0x18001197a  jnz     short loc_1800119CB
0x18001197c  mov     [rdx], r8
0x18001197f  mov     rcx, rdi; SpinLock
0x180011982  mov     [r8+8], rdx
0x180011986  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x18001198d  nop     dword ptr [rax+rax+00h]
0x180011992  mov     cl, [rbx+45h]; Irql
0x180011995  call    cs:__imp_IoReleaseCancelSpinLock
0x18001199c  nop     dword ptr [rax+rax+00h]
0x1800119a1  mov     eax, 0C0000120h
0x1800119a6  cmp     [rbx+30h], eax
0x1800119a9  jz      short loc_1800119BF
0x1800119ab  xor     edx, edx; PriorityBoost
0x1800119ad  mov     [rbx+30h], eax
0x1800119b0  mov     rcx, rbx; Irp
0x1800119b3  call    cs:__imp_IofCompleteRequest
0x1800119ba  nop     dword ptr [rax+rax+00h]
0x1800119bf  mov     rbx, [rsp+28h+arg_0]
0x1800119c4  add     rsp, 20h
0x1800119c8  pop     rdi
0x1800119c9  retn
0x1800119cb  mov     ecx, 3
0x1800119d0  int     29h; Win8: RtlFailFast(ecx)
```
