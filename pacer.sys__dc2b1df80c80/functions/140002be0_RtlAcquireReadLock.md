# RtlAcquireReadLock

- ea: `0x140002be0`
- end: `0x140002c14`
- name: `RtlAcquireReadLock`
- size: `52`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e0b0`
- `0x14000e464`
- `0x140010110`

## callees

- `0x140003934`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140002bf2`
- `ntoskrnl!KfRaiseIrql` at `0x140002bf2`

## pseudocode

```c
void __fastcall RtlAcquireReadLock(volatile signed __int32 *SpinLock, KIRQL *a2)
{
  *a2 = KfRaiseIrql(2u);
  RtlAcquireReadLockAtDpcLevel(SpinLock);
}

```

## disassembly

```asm
0x140002be0  mov     [rsp+arg_0], rbx
0x140002be5  push    rdi
0x140002be6  sub     rsp, 20h
0x140002bea  mov     rdi, rcx
0x140002bed  mov     rbx, rdx
0x140002bf0  mov     cl, 2; NewIrql
0x140002bf2  call    cs:__imp_KfRaiseIrql
0x140002bf9  nop     dword ptr [rax+rax+00h]
0x140002bfe  mov     rcx, rdi; SpinLock
0x140002c01  mov     [rbx], al
0x140002c03  call    RtlAcquireReadLockAtDpcLevel
0x140002c08  mov     rbx, [rsp+28h+arg_0]
0x140002c0d  add     rsp, 20h
0x140002c11  pop     rdi
0x140002c12  retn
```
