# NpCancelWaitQueueIrp

- ea: `0x1400019a0`
- end: `0x140001a90`
- name: `NpCancelWaitQueueIrp`
- size: `240`
- prototype: `void __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400019a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001a53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001a53`
- `ntoskrnl!IofCompleteRequest` at `0x140001a73`
- `ntoskrnl!IofCompleteRequest` at `0x140001a73`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400019af`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400019af`
- `ntoskrnl!ObfDereferenceObject` at `0x140001a42`
- `ntoskrnl!ObfDereferenceObject` at `0x140001a42`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400019c3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400019c3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001a2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001a2a`
- `ntoskrnl!KeCancelTimer` at `0x140001a0a`
- `ntoskrnl!KeCancelTimer` at `0x140001a0a`

## pseudocode

```c
void __fastcall NpCancelWaitQueueIrp(__int64 a1, IRP *a2)
{
  struct _LIST_ENTRY *Flink; // rsi
  KIRQL v4; // al
  struct _LIST_ENTRY *Blink; // rbx
  KIRQL v6; // bp
  struct _LIST_ENTRY *v7; // rdx
  struct _LIST_ENTRY *v8; // r8

  IoReleaseCancelSpinLock(a2->CancelIrql);
  Flink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&Flink[1]);
  Blink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink;
  v6 = v4;
  if ( Blink )
  {
    v7 = a2->Tail.Overlay.ListEntry.Flink;
    if ( (PVOID *)v7->Blink != &a2->Tail.CompletionKey + 6
      || (v8 = a2->Tail.Overlay.ListEntry.Blink, (PVOID *)v8->Flink != &a2->Tail.CompletionKey + 6) )
    {
      __fastfail(3u);
    }
    v8->Flink = v7;
    v7->Blink = v8;
    if ( !KeCancelTimer((PKTIMER)&Blink[4].Blink) )
    {
      Blink->Flink = 0;
      Blink = 0;
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)&Flink[1], v6);
  if ( Blink )
  {
    ObfDereferenceObject(Blink[9].Flink);
    ExFreePoolWithTag(Blink, 0);
  }
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 2);
}

```

## disassembly

```asm
0x1400019a0  push    rbx
0x1400019a2  push    rbp
0x1400019a3  push    rsi
0x1400019a4  push    rdi
0x1400019a5  sub     rsp, 28h
0x1400019a9  mov     cl, [rdx+45h]; Irql
0x1400019ac  mov     rdi, rdx
0x1400019af  call    cs:__imp_IoReleaseCancelSpinLock
0x1400019b6  nop     dword ptr [rax+rax+00h]
0x1400019bb  mov     rsi, [rdi+78h]
0x1400019bf  lea     rcx, [rsi+10h]; SpinLock
0x1400019c3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400019ca  nop     dword ptr [rax+rax+00h]
0x1400019cf  mov     rbx, [rdi+80h]
0x1400019d6  mov     bpl, al
0x1400019d9  test    rbx, rbx
0x1400019dc  jz      short loc_140001A23
0x1400019de  lea     rcx, [rdi+0A8h]
0x1400019e5  mov     rdx, [rcx]
0x1400019e8  cmp     [rdx+8], rcx
0x1400019ec  jnz     loc_140001A89
0x1400019f2  mov     r8, [rcx+8]
0x1400019f6  cmp     [r8], rcx
0x1400019f9  jnz     loc_140001A89
0x1400019ff  mov     [r8], rdx
0x140001a02  lea     rcx, [rbx+48h]; PKTIMER
0x140001a06  mov     [rdx+8], r8
0x140001a0a  call    cs:__imp_KeCancelTimer
0x140001a11  nop     dword ptr [rax+rax+00h]
0x140001a16  test    al, al
0x140001a18  jnz     short loc_140001A23
0x140001a1a  mov     qword ptr [rbx], 0
0x140001a21  xor     ebx, ebx
0x140001a23  mov     dl, bpl; NewIrql
0x140001a26  lea     rcx, [rsi+10h]; SpinLock
0x140001a2a  call    cs:__imp_KeReleaseSpinLock
0x140001a31  nop     dword ptr [rax+rax+00h]
0x140001a36  test    rbx, rbx
0x140001a39  jz      short loc_140001A5F
0x140001a3b  mov     rcx, [rbx+90h]; Object
0x140001a42  call    cs:__imp_ObfDereferenceObject
0x140001a49  nop     dword ptr [rax+rax+00h]
0x140001a4e  xor     edx, edx; Tag
0x140001a50  mov     rcx, rbx; P
0x140001a53  call    cs:__imp_ExFreePoolWithTag
0x140001a5a  nop     dword ptr [rax+rax+00h]
0x140001a5f  mov     dl, 2; PriorityBoost
0x140001a61  mov     qword ptr [rdi+38h], 0
0x140001a69  mov     rcx, rdi; Irp
0x140001a6c  mov     dword ptr [rdi+30h], 0C0000120h
0x140001a73  call    cs:__imp_IofCompleteRequest
0x140001a7a  nop     dword ptr [rax+rax+00h]
0x140001a7f  add     rsp, 28h
0x140001a83  pop     rdi
0x140001a84  pop     rsi
0x140001a85  pop     rbp
0x140001a86  pop     rbx
0x140001a87  retn
0x140001a89  mov     ecx, 3
0x140001a8e  int     29h; Win8: RtlFailFast(ecx)
```
