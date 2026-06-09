# CollectionWaitWakeIrpCancelRoutine

- ea: `0x180017fd0`
- end: `0x18001807a`
- name: `CollectionWaitWakeIrpCancelRoutine`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180017fd0`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x18001803e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x18001803e`
- `ntoskrnl!IofCompleteRequest` at `0x180018056`
- `ntoskrnl!IofCompleteRequest` at `0x180018056`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001802f`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001802f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180017ff1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180017ff1`

## pseudocode

```c
void __fastcall CollectionWaitWakeIrpCancelRoutine(__int64 a1, IRP *a2)
{
  __int64 v2; // rdi
  __int64 v4; // rsi
  KIRQL v5; // al
  _LIST_ENTRY *Flink; // r9
  _LIST_ENTRY *Blink; // rdx

  v2 = *(_QWORD *)(a1 + 64);
  v4 = *(_QWORD *)(v2 + 96);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 520));
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  if ( (void **)Flink->Blink != &a2->Tail.CompletionKey + 6
    || (Blink = a2->Tail.Overlay.ListEntry.Blink, (void **)Blink->Flink != &a2->Tail.CompletionKey + 6) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  _InterlockedExchange64((volatile __int64 *)(v2 + 144), 0);
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 520), v5);
  IoReleaseCancelSpinLock(a2->CancelIrql);
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x180017fd0  mov     [rsp+arg_0], rbx
0x180017fd5  mov     [rsp+arg_8], rsi
0x180017fda  push    rdi
0x180017fdb  sub     rsp, 20h
0x180017fdf  mov     rdi, [rcx+40h]
0x180017fe3  mov     rbx, rdx
0x180017fe6  mov     rsi, [rdi+60h]
0x180017fea  lea     rcx, [rsi+208h]; SpinLock
0x180017ff1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180017ff8  nop     dword ptr [rax+rax+00h]
0x180017ffd  lea     r8, [rbx+0A8h]
0x180018004  mov     r9, [r8]
0x180018007  cmp     [r9+8], r8
0x18001800b  jnz     short loc_180018073
0x18001800d  mov     rdx, [r8+8]
0x180018011  cmp     [rdx], r8
0x180018014  jnz     short loc_180018073
0x180018016  mov     [rdx], r9
0x180018019  lea     rcx, [rsi+208h]; SpinLock
0x180018020  mov     [r9+8], rdx
0x180018024  xor     edx, edx
0x180018026  xchg    rdx, [rdi+90h]
0x18001802d  mov     dl, al; NewIrql
0x18001802f  call    cs:__imp_KeReleaseSpinLock
0x180018036  nop     dword ptr [rax+rax+00h]
0x18001803b  mov     cl, [rbx+45h]; Irql
0x18001803e  call    cs:__imp_IoReleaseCancelSpinLock
0x180018045  nop     dword ptr [rax+rax+00h]
0x18001804a  xor     edx, edx; PriorityBoost
0x18001804c  mov     dword ptr [rbx+30h], 0C0000120h
0x180018053  mov     rcx, rbx; Irp
0x180018056  call    cs:__imp_IofCompleteRequest
0x18001805d  nop     dword ptr [rax+rax+00h]
0x180018062  mov     rbx, [rsp+28h+arg_0]
0x180018067  mov     rsi, [rsp+28h+arg_8]
0x18001806c  add     rsp, 20h
0x180018070  pop     rdi
0x180018071  retn
0x180018073  mov     ecx, 3
0x180018078  int     29h; Win8: RtlFailFast(ecx)
```
