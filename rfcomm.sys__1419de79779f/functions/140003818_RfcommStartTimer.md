# RfcommStartTimer

- ea: `0x140003818`
- end: `0x14000385f`
- name: `RfcommStartTimer`
- size: `71`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000fc00`
- `0x140011050`
- `0x14001291c`
- `0x1400149b4`
- `0x140014c64`
- `0x140014eb4`
- `0x14001513c`
- `0x1400152ec`
- `0x14001552c`
- `0x1400174a8`
- `0x140017db4`
- `0x140019f70`

## callees

- `0x140003868`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003829`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003829`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003847`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003847`

## pseudocode

```c
void __fastcall RfcommStartTimer(__int64 a1)
{
  *(_BYTE *)(a1 + 32) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 24));
  RfcommStartTimerLocked(a1);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 24), *(_BYTE *)(a1 + 32));
}

```

## disassembly

```asm
0x140003818  mov     [rsp+arg_0], rbx
0x14000381d  push    rdi
0x14000381e  sub     rsp, 20h
0x140003822  mov     rdi, rcx
0x140003825  add     rcx, 18h; SpinLock
0x140003829  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003830  nop     dword ptr [rax+rax+00h]
0x140003835  mov     rcx, rdi
0x140003838  mov     [rdi+20h], al
0x14000383b  call    RfcommStartTimerLocked
0x140003840  mov     dl, [rdi+20h]; NewIrql
0x140003843  lea     rcx, [rdi+18h]; SpinLock
0x140003847  call    cs:__imp_KeReleaseSpinLock
0x14000384e  nop     dword ptr [rax+rax+00h]
0x140003853  mov     rbx, [rsp+28h+arg_0]
0x140003858  add     rsp, 20h
0x14000385c  pop     rdi
0x14000385d  retn
```
