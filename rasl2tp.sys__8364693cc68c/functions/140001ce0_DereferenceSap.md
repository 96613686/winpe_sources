# DereferenceSap

- ea: `0x140001ce0`
- end: `0x140001d52`
- name: `DereferenceSap`
- size: `114`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400022e0`
- `0x140011518`
- `0x1400133ac`

## callees

- `0x1400012e0`
- `0x140001ce0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140001d1f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001d1f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001cfc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001cfc`

## pseudocode

```c
void __fastcall DereferenceSap(__int64 a1)
{
  KSPIN_LOCK *v1; // rdi
  KIRQL v3; // al
  int v4; // ebx

  v1 = (KSPIN_LOCK *)(a1 + 384);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 384));
  v4 = --*(_DWORD *)(a1 + 380);
  *(_BYTE *)(a1 + 392) = v3;
  KeReleaseSpinLock(v1, v3);
  if ( !v4 )
    ScheduleWork(a1, (NDIS_IO_WORKITEM_FUNCTION *)DeregisterSapPassive, (void *)a1);
}

```

## disassembly

```asm
0x140001ce0  mov     [rsp+arg_0], rbx
0x140001ce5  mov     [rsp+arg_8], rsi
0x140001cea  push    rdi
0x140001ceb  sub     rsp, 20h
0x140001cef  lea     rdi, [rcx+180h]
0x140001cf6  mov     rsi, rcx
0x140001cf9  mov     rcx, rdi; SpinLock
0x140001cfc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001d03  nop     dword ptr [rax+rax+00h]
0x140001d08  dec     dword ptr [rsi+17Ch]
0x140001d0e  mov     rcx, rdi; SpinLock
0x140001d11  mov     ebx, [rsi+17Ch]
0x140001d17  mov     dl, al; NewIrql
0x140001d19  mov     [rsi+188h], al
0x140001d1f  call    cs:__imp_KeReleaseSpinLock
0x140001d26  nop     dword ptr [rax+rax+00h]
0x140001d2b  test    ebx, ebx
0x140001d2d  jnz     short loc_140001D41
0x140001d2f  mov     r8, rsi
0x140001d32  lea     rdx, DeregisterSapPassive
0x140001d39  mov     rcx, rsi
0x140001d3c  call    ScheduleWork
0x140001d41  mov     rbx, [rsp+28h+arg_0]
0x140001d46  mov     rsi, [rsp+28h+arg_8]
0x140001d4b  add     rsp, 20h
0x140001d4f  pop     rdi
0x140001d50  retn
```
