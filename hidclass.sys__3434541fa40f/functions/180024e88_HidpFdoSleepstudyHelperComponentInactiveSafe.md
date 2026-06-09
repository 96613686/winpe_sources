# HidpFdoSleepstudyHelperComponentInactiveSafe

- ea: `0x180024e88`
- end: `0x180024eea`
- name: `HidpFdoSleepstudyHelperComponentInactiveSafe`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003f40`
- `0x180011738`

## callees

- `0x180024e88`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x180024ecd`
- `ntoskrnl!KeReleaseSpinLock` at `0x180024ecd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180024ea4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180024ea4`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x180024ebb`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x180024ebb`

## pseudocode

```c
void __fastcall HidpFdoSleepstudyHelperComponentInactiveSafe(__int64 a1, _QWORD *a2)
{
  KSPIN_LOCK *v2; // rdi
  KIRQL v4; // si

  v2 = (KSPIN_LOCK *)(a1 + 2136);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 2136));
  if ( *a2 )
    SleepstudyHelper_ComponentInactive();
  KeReleaseSpinLock(v2, v4);
}

```

## disassembly

```asm
0x180024e88  mov     [rsp+arg_0], rbx
0x180024e8d  mov     [rsp+arg_8], rsi
0x180024e92  push    rdi
0x180024e93  sub     rsp, 20h
0x180024e97  lea     rdi, [rcx+858h]
0x180024e9e  mov     rbx, rdx
0x180024ea1  mov     rcx, rdi; SpinLock
0x180024ea4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180024eab  nop     dword ptr [rax+rax+00h]
0x180024eb0  mov     rcx, [rbx]
0x180024eb3  mov     sil, al
0x180024eb6  test    rcx, rcx
0x180024eb9  jz      short loc_180024EC7
0x180024ebb  call    cs:__imp_SleepstudyHelper_ComponentInactive
0x180024ec2  nop     dword ptr [rax+rax+00h]
0x180024ec7  mov     dl, sil; NewIrql
0x180024eca  mov     rcx, rdi; SpinLock
0x180024ecd  call    cs:__imp_KeReleaseSpinLock
0x180024ed4  nop     dword ptr [rax+rax+00h]
0x180024ed9  mov     rbx, [rsp+28h+arg_0]
0x180024ede  mov     rsi, [rsp+28h+arg_8]
0x180024ee3  add     rsp, 20h
0x180024ee7  pop     rdi
0x180024ee8  retn
```
