# IrpList_EnqueueEx

- ea: `0x14001ed50`
- end: `0x14001eda1`
- name: `IrpList_EnqueueEx`
- size: `81`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140001eec`
- `0x1400074d0`
- `0x140008ac0`
- `0x14000a9d0`
- `0x14000aca0`

## callees

- `0x14001eda8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ed64`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ed64`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ed87`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ed87`

## pseudocode

```c
__int64 __fastcall IrpList_EnqueueEx(__int64 a1, __int64 a2)
{
  __int64 v4; // r9
  __int64 v5; // r8
  KIRQL v6; // r9

  LOBYTE(v4) = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(a1 + 24));
  LODWORD(a2) = IrpList_EnqueueLocked(a1, a2, v5, v4);
  KeReleaseSpinLock(*(PKSPIN_LOCK *)(a1 + 24), v6);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x14001ed50  mov     [rsp+arg_0], rbx
0x14001ed55  push    rdi
0x14001ed56  sub     rsp, 20h
0x14001ed5a  mov     rdi, rcx
0x14001ed5d  mov     rbx, rdx
0x14001ed60  mov     rcx, [rcx+18h]; SpinLock
0x14001ed64  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001ed6b  nop     dword ptr [rax+rax+00h]
0x14001ed70  mov     rdx, rbx
0x14001ed73  mov     rcx, rdi
0x14001ed76  mov     r9b, al
0x14001ed79  call    IrpList_EnqueueLocked
0x14001ed7e  mov     rcx, [rdi+18h]; SpinLock
0x14001ed82  mov     dl, r9b; NewIrql
0x14001ed85  mov     ebx, eax
0x14001ed87  call    cs:__imp_KeReleaseSpinLock
0x14001ed8e  nop     dword ptr [rax+rax+00h]
0x14001ed93  mov     eax, ebx
0x14001ed95  mov     rbx, [rsp+28h+arg_0]
0x14001ed9a  add     rsp, 20h
0x14001ed9e  pop     rdi
0x14001ed9f  retn
```
