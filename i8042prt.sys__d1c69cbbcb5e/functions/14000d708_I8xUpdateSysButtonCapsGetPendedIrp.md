# I8xUpdateSysButtonCapsGetPendedIrp

- ea: `0x14000d708`
- end: `0x14000d777`
- name: `I8xUpdateSysButtonCapsGetPendedIrp`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14001d300`

## callees

- `0x14000d708`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d724`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d724`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d757`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d757`

## pseudocode

```c
__int64 __fastcall I8xUpdateSysButtonCapsGetPendedIrp(__int64 a1)
{
  KSPIN_LOCK *v1; // rsi
  KIRQL v3; // al
  __int64 v4; // rdi

  v1 = (KSPIN_LOCK *)(a1 + 664);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 664));
  v4 = *(_QWORD *)(a1 + 592);
  *(_QWORD *)(a1 + 592) = 0;
  if ( v4 )
    v4 &= -(__int64)(_InterlockedExchange64((volatile __int64 *)(v4 + 104), 0) != 0);
  KeReleaseSpinLock(v1, v3);
  return v4;
}

```

## disassembly

```asm
0x14000d708  mov     [rsp+arg_0], rbx
0x14000d70d  mov     [rsp+arg_8], rsi
0x14000d712  push    rdi
0x14000d713  sub     rsp, 20h
0x14000d717  lea     rsi, [rcx+298h]
0x14000d71e  mov     rbx, rcx
0x14000d721  mov     rcx, rsi; SpinLock
0x14000d724  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d72b  nop     dword ptr [rax+rax+00h]
0x14000d730  mov     rdi, [rbx+250h]
0x14000d737  xor     edx, edx
0x14000d739  mov     [rbx+250h], rdx
0x14000d740  test    rdi, rdi
0x14000d743  jz      short loc_14000D752
0x14000d745  xchg    rdx, [rdi+68h]
0x14000d749  neg     rdx
0x14000d74c  sbb     rdx, rdx
0x14000d74f  and     rdi, rdx
0x14000d752  mov     dl, al; NewIrql
0x14000d754  mov     rcx, rsi; SpinLock
0x14000d757  call    cs:__imp_KeReleaseSpinLock
0x14000d75e  nop     dword ptr [rax+rax+00h]
0x14000d763  mov     rbx, [rsp+28h+arg_0]
0x14000d768  mov     rax, rdi
0x14000d76b  mov     rsi, [rsp+28h+arg_8]
0x14000d770  add     rsp, 20h
0x14000d774  pop     rdi
0x14000d775  retn
```
