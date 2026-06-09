# HidpFdoSleepstudyHelperComponentActiveSafe

- ea: `0x180024e20`
- end: `0x180024e82`
- name: `HidpFdoSleepstudyHelperComponentActiveSafe`
- size: `98`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003b70`
- `0x180011738`
- `0x18003b748`

## callees

- `0x180024e20`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x180024e65`
- `ntoskrnl!KeReleaseSpinLock` at `0x180024e65`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180024e3c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180024e3c`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x180024e53`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x180024e53`

## pseudocode

```c
void __fastcall HidpFdoSleepstudyHelperComponentActiveSafe(__int64 a1, _QWORD *a2)
{
  KSPIN_LOCK *v2; // rdi
  KIRQL v4; // si

  v2 = (KSPIN_LOCK *)(a1 + 2136);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 2136));
  if ( *a2 )
    SleepstudyHelper_ComponentActive();
  KeReleaseSpinLock(v2, v4);
}

```

## disassembly

```asm
0x180024e20  mov     [rsp+arg_0], rbx
0x180024e25  mov     [rsp+arg_8], rsi
0x180024e2a  push    rdi
0x180024e2b  sub     rsp, 20h
0x180024e2f  lea     rdi, [rcx+858h]
0x180024e36  mov     rbx, rdx
0x180024e39  mov     rcx, rdi; SpinLock
0x180024e3c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180024e43  nop     dword ptr [rax+rax+00h]
0x180024e48  mov     rcx, [rbx]
0x180024e4b  mov     sil, al
0x180024e4e  test    rcx, rcx
0x180024e51  jz      short loc_180024E5F
0x180024e53  call    cs:__imp_SleepstudyHelper_ComponentActive
0x180024e5a  nop     dword ptr [rax+rax+00h]
0x180024e5f  mov     dl, sil; NewIrql
0x180024e62  mov     rcx, rdi; SpinLock
0x180024e65  call    cs:__imp_KeReleaseSpinLock
0x180024e6c  nop     dword ptr [rax+rax+00h]
0x180024e71  mov     rbx, [rsp+28h+arg_0]
0x180024e76  mov     rsi, [rsp+28h+arg_8]
0x180024e7b  add     rsp, 20h
0x180024e7f  pop     rdi
0x180024e80  retn
```
