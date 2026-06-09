# NbtCancelClientReceive

- ea: `0x14002dbf0`
- end: `0x14002dcc9`
- name: `NbtCancelClientReceive`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14002dbf0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002dcaa`
- `ntoskrnl!IofCompleteRequest` at `0x14002dcaa`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002dc01`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002dc01`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002dc45`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002dc45`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002dc80`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002dc80`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002dc2a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002dc2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002dc92`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002dc92`

## pseudocode

```c
void __fastcall NbtCancelClientReceive(__int64 a1, IRP *a2)
{
  _QWORD *FsContext; // rax
  __int64 v4; // rsi
  KSPIN_LOCK *v5; // rbp
  KIRQL v6; // r14
  __int64 v7; // rbx
  struct _LIST_ENTRY *Flink; // rdx
  struct _LIST_ENTRY *Blink; // r8

  IoReleaseCancelSpinLock(a2->CancelIrql);
  FsContext = a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  v4 = FsContext[3];
  v5 = FsContext + 31;
  v6 = KeAcquireSpinLockRaiseToDpc(FsContext + 31);
  if ( v4 )
  {
    v7 = v4 + 104;
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v4 + 104));
  }
  else
  {
    v7 = 104;
  }
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  if ( (PVOID *)Flink->Blink != &a2->Tail.CompletionKey + 6
    || (Blink = a2->Tail.Overlay.ListEntry.Blink, (PVOID *)Blink->Flink != &a2->Tail.CompletionKey + 6) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  if ( v4 )
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v7);
  KeReleaseSpinLock(v5, v6);
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 2);
}

```

## disassembly

```asm
0x14002dbf0  push    rbx
0x14002dbf2  push    rbp
0x14002dbf3  push    rsi
0x14002dbf4  push    rdi
0x14002dbf5  push    r14
0x14002dbf7  sub     rsp, 20h
0x14002dbfb  mov     cl, [rdx+45h]; Irql
0x14002dbfe  mov     rdi, rdx
0x14002dc01  call    cs:__imp_IoReleaseCancelSpinLock
0x14002dc08  nop     dword ptr [rax+rax+00h]
0x14002dc0d  mov     rax, [rdi+0B8h]
0x14002dc14  mov     rcx, [rax+30h]
0x14002dc18  mov     rax, [rcx+18h]
0x14002dc1c  mov     rsi, [rax+18h]
0x14002dc20  lea     rbp, [rax+0F8h]
0x14002dc27  mov     rcx, rbp; SpinLock
0x14002dc2a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002dc31  nop     dword ptr [rax+rax+00h]
0x14002dc36  mov     r14b, al
0x14002dc39  test    rsi, rsi
0x14002dc3c  jz      short loc_14002DC53
0x14002dc3e  lea     rbx, [rsi+68h]
0x14002dc42  mov     rcx, rbx; SpinLock
0x14002dc45  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14002dc4c  nop     dword ptr [rax+rax+00h]
0x14002dc51  jmp     short loc_14002DC58
0x14002dc53  mov     ebx, 68h ; 'h'
0x14002dc58  lea     rax, [rdi+0A8h]
0x14002dc5f  mov     rdx, [rax]
0x14002dc62  cmp     [rdx+8], rax
0x14002dc66  jnz     short loc_14002DCC2
0x14002dc68  mov     r8, [rax+8]
0x14002dc6c  cmp     [r8], rax
0x14002dc6f  jnz     short loc_14002DCC2
0x14002dc71  mov     [r8], rdx
0x14002dc74  mov     [rdx+8], r8
0x14002dc78  test    rsi, rsi
0x14002dc7b  jz      short loc_14002DC8C
0x14002dc7d  mov     rcx, rbx; SpinLock
0x14002dc80  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14002dc87  nop     dword ptr [rax+rax+00h]
0x14002dc8c  mov     dl, r14b; NewIrql
0x14002dc8f  mov     rcx, rbp; SpinLock
0x14002dc92  call    cs:__imp_KeReleaseSpinLock
0x14002dc99  nop     dword ptr [rax+rax+00h]
0x14002dc9e  mov     dl, 2; PriorityBoost
0x14002dca0  mov     dword ptr [rdi+30h], 0C0000120h
0x14002dca7  mov     rcx, rdi; Irp
0x14002dcaa  call    cs:__imp_IofCompleteRequest
0x14002dcb1  nop     dword ptr [rax+rax+00h]
0x14002dcb6  add     rsp, 20h
0x14002dcba  pop     r14
0x14002dcbc  pop     rdi
0x14002dcbd  pop     rsi
0x14002dcbe  pop     rbp
0x14002dcbf  pop     rbx
0x14002dcc0  retn
0x14002dcc2  mov     ecx, 3
0x14002dcc7  int     29h; Win8: RtlFailFast(ecx)
```
