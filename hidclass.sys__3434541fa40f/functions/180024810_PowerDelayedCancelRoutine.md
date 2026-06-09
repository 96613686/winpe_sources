# PowerDelayedCancelRoutine

- ea: `0x180024810`
- end: `0x1800248cf`
- name: `PowerDelayedCancelRoutine`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003f40`
- `0x180024810`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180024829`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180024829`
- `ntoskrnl!IofCompleteRequest` at `0x18002489a`
- `ntoskrnl!IofCompleteRequest` at `0x18002489a`
- `ntoskrnl!KeReleaseSpinLock` at `0x180024882`
- `ntoskrnl!KeReleaseSpinLock` at `0x180024882`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180024843`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180024843`

## pseudocode

```c
__int64 __fastcall PowerDelayedCancelRoutine(__int64 a1, IRP *a2)
{
  __int64 v2; // rbx
  __int64 v4; // rbx
  KIRQL v5; // al
  _LIST_ENTRY *Flink; // r9
  _LIST_ENTRY *Blink; // rdx

  v2 = *(_QWORD *)(a1 + 64);
  IoReleaseCancelSpinLock(a2->CancelIrql);
  v4 = *(_QWORD *)(v2 + 96);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 416));
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  if ( (void **)Flink->Blink != &a2->Tail.CompletionKey + 6
    || (Blink = a2->Tail.Overlay.ListEntry.Blink, (void **)Blink->Flink != &a2->Tail.CompletionKey + 6) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = 0;
  --*(_DWORD *)(v4 + 440);
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 416), v5);
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 0);
  return HidpFdoReleasePoFxPowerReferenceWithTag(v4 + 32, 8);
}

```

## disassembly

```asm
0x180024810  mov     [rsp+arg_0], rbx
0x180024815  mov     [rsp+arg_8], rsi
0x18002481a  push    rdi
0x18002481b  sub     rsp, 20h
0x18002481f  mov     rbx, [rcx+40h]
0x180024823  mov     rdi, rdx
0x180024826  mov     cl, [rdx+45h]; Irql
0x180024829  call    cs:__imp_IoReleaseCancelSpinLock
0x180024830  nop     dword ptr [rax+rax+00h]
0x180024835  mov     rbx, [rbx+60h]
0x180024839  lea     rsi, [rbx+1A0h]
0x180024840  mov     rcx, rsi; SpinLock
0x180024843  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18002484a  nop     dword ptr [rax+rax+00h]
0x18002484f  lea     r8, [rdi+0A8h]
0x180024856  mov     r9, [r8]
0x180024859  cmp     [r9+8], r8
0x18002485d  jnz     short loc_1800248C8
0x18002485f  mov     rdx, [r8+8]
0x180024863  cmp     [rdx], r8
0x180024866  jnz     short loc_1800248C8
0x180024868  mov     [rdx], r9
0x18002486b  mov     rcx, rsi; SpinLock
0x18002486e  mov     [r9+8], rdx
0x180024872  mov     dl, al; NewIrql
0x180024874  mov     qword ptr [rdi+78h], 0
0x18002487c  dec     dword ptr [rbx+1B8h]
0x180024882  call    cs:__imp_KeReleaseSpinLock
0x180024889  nop     dword ptr [rax+rax+00h]
0x18002488e  xor     edx, edx; PriorityBoost
0x180024890  mov     dword ptr [rdi+30h], 0C0000120h
0x180024897  mov     rcx, rdi; Irp
0x18002489a  call    cs:__imp_IofCompleteRequest
0x1800248a1  nop     dword ptr [rax+rax+00h]
0x1800248a6  mov     r8, rdi
0x1800248a9  lea     rcx, [rbx+20h]
0x1800248ad  mov     edx, 8
0x1800248b2  call    HidpFdoReleasePoFxPowerReferenceWithTag
0x1800248b7  mov     rbx, [rsp+28h+arg_0]
0x1800248bc  mov     rsi, [rsp+28h+arg_8]
0x1800248c1  add     rsp, 20h
0x1800248c5  pop     rdi
0x1800248c6  retn
0x1800248c8  mov     ecx, 3
0x1800248cd  int     29h; Win8: RtlFailFast(ecx)
```
