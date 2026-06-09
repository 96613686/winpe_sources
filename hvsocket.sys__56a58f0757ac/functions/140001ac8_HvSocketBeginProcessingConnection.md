# HvSocketBeginProcessingConnection

- ea: `0x140001ac8`
- end: `0x140001b9a`
- name: `HvSocketBeginProcessingConnection`
- size: `210`
- prototype: `char __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140019110`
- `0x14001bd20`
- `0x14002509c`
- `0x140025e9c`

## callees

- `0x140001ac8`
- `0x140001ba0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001b21`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001b21`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001b40`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001b40`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001b63`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001b7f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001b63`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001b7f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140001b57`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140001b73`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140001b57`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140001b73`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001ad9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001b01`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001ad9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001b01`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140001ae9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140001b11`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140001ae9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140001b11`

## pseudocode

```c
char __fastcall HvSocketBeginProcessingConnection(__int64 a1)
{
  char v2; // r14
  __int64 v3; // rbx
  KIRQL v4; // bl

  v2 = 0;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  v3 = *(_QWORD *)(a1 + 872);
  if ( v3 )
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v3 + 16));
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 72));
    v2 = HvSocketBeginProcessingConnectionLocked(a1);
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 72), v4);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 872) + 16LL));
    KeLeaveCriticalRegion();
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  KeLeaveCriticalRegion();
  return v2;
}

```

## disassembly

```asm
0x140001ac8  push    rbx
0x140001aca  push    rbp
0x140001acb  push    rsi
0x140001acc  push    rdi
0x140001acd  push    r14
0x140001acf  sub     rsp, 20h
0x140001ad3  mov     rsi, rcx
0x140001ad6  xor     r14b, r14b
0x140001ad9  call    cs:__imp_KeEnterCriticalRegion
0x140001ae0  nop     dword ptr [rax+rax+00h]
0x140001ae5  lea     rcx, [rsi+10h]; FastMutex
0x140001ae9  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140001af0  nop     dword ptr [rax+rax+00h]
0x140001af5  mov     rbx, [rsi+368h]
0x140001afc  test    rbx, rbx
0x140001aff  jz      short loc_140001B6F
0x140001b01  call    cs:__imp_KeEnterCriticalRegion
0x140001b08  nop     dword ptr [rax+rax+00h]
0x140001b0d  lea     rcx, [rbx+10h]; FastMutex
0x140001b11  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140001b18  nop     dword ptr [rax+rax+00h]
0x140001b1d  lea     rcx, [rsi+48h]; SpinLock
0x140001b21  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001b28  nop     dword ptr [rax+rax+00h]
0x140001b2d  mov     rcx, rsi
0x140001b30  mov     bl, al
0x140001b32  call    HvSocketBeginProcessingConnectionLocked
0x140001b37  mov     dl, bl; NewIrql
0x140001b39  lea     rcx, [rsi+48h]; SpinLock
0x140001b3d  mov     r14b, al
0x140001b40  call    cs:__imp_KeReleaseSpinLock
0x140001b47  nop     dword ptr [rax+rax+00h]
0x140001b4c  mov     rcx, [rsi+368h]
0x140001b53  add     rcx, 10h; FastMutex
0x140001b57  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140001b5e  nop     dword ptr [rax+rax+00h]
0x140001b63  call    cs:__imp_KeLeaveCriticalRegion
0x140001b6a  nop     dword ptr [rax+rax+00h]
0x140001b6f  lea     rcx, [rsi+10h]; FastMutex
0x140001b73  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140001b7a  nop     dword ptr [rax+rax+00h]
0x140001b7f  call    cs:__imp_KeLeaveCriticalRegion
0x140001b86  nop     dword ptr [rax+rax+00h]
0x140001b8b  mov     al, r14b
0x140001b8e  add     rsp, 20h
0x140001b92  pop     r14
0x140001b94  pop     rdi
0x140001b95  pop     rsi
0x140001b96  pop     rbp
0x140001b97  pop     rbx
0x140001b98  retn
```
