# IrpList_Dequeue

- ea: `0x14001ebd8`
- end: `0x14001ec25`
- name: `IrpList_Dequeue`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140007350`
- `0x14000877c`
- `0x140008ac0`
- `0x1400097f4`
- `0x140011634`
- `0x14001204c`
- `0x1400121d4`

## callees

- `0x14001ece8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ebe9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ebe9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ec0a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ec0a`

## pseudocode

```c
__int64 __fastcall IrpList_Dequeue(__int64 a1)
{
  __int64 v2; // r9
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rbx
  KIRQL v6; // r9

  LOBYTE(v2) = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(a1 + 24));
  v5 = IrpList_DequeueLocked(a1, v3, v4, v2);
  KeReleaseSpinLock(*(PKSPIN_LOCK *)(a1 + 24), v6);
  return v5;
}

```

## disassembly

```asm
0x14001ebd8  mov     [rsp+arg_0], rbx
0x14001ebdd  push    rdi
0x14001ebde  sub     rsp, 20h
0x14001ebe2  mov     rdi, rcx
0x14001ebe5  mov     rcx, [rcx+18h]; SpinLock
0x14001ebe9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001ebf0  nop     dword ptr [rax+rax+00h]
0x14001ebf5  mov     rcx, rdi
0x14001ebf8  mov     r9b, al
0x14001ebfb  call    IrpList_DequeueLocked
0x14001ec00  mov     rcx, [rdi+18h]; SpinLock
0x14001ec04  mov     dl, r9b; NewIrql
0x14001ec07  mov     rbx, rax
0x14001ec0a  call    cs:__imp_KeReleaseSpinLock
0x14001ec11  nop     dword ptr [rax+rax+00h]
0x14001ec16  mov     rax, rbx
0x14001ec19  mov     rbx, [rsp+28h+arg_0]
0x14001ec1e  add     rsp, 20h
0x14001ec22  pop     rdi
0x14001ec23  retn
```
