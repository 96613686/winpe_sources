# FltpMarkAllCallbacksForDeletion

- ea: `0x18001ae50`
- end: `0x18001aeb6`
- name: `FltpMarkAllCallbacksForDeletion`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180063b40`

## callees

- `0x18001ae50`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x18001ae64`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18001ae64`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001ae9e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001ae9e`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x18001ae73`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x18001ae73`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x18001ae92`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x18001ae92`

## pseudocode

```c
void __fastcall FltpMarkAllCallbacksForDeletion(__int64 a1)
{
  __int64 v1; // rdi

  v1 = qword_18003E9A0;
  KeEnterGuardedRegion();
  ExAcquireCacheAwarePushLockExclusive(v1);
  if ( (*(_DWORD *)(a1 + 80) & 2) == 0 )
    _InterlockedOr((volatile signed __int32 *)(a1 + 80), 2u);
  ExReleaseCacheAwarePushLockExclusive(qword_18003E9A0);
  KeLeaveGuardedRegion();
}

```

## disassembly

```asm
0x18001ae50  mov     [rsp+arg_0], rbx
0x18001ae55  push    rdi
0x18001ae56  sub     rsp, 20h
0x18001ae5a  mov     rdi, cs:qword_18003E9A0
0x18001ae61  mov     rbx, rcx
0x18001ae64  call    cs:__imp_KeEnterGuardedRegion
0x18001ae6b  nop     dword ptr [rax+rax+00h]
0x18001ae70  mov     rcx, rdi
0x18001ae73  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x18001ae7a  nop     dword ptr [rax+rax+00h]
0x18001ae7f  mov     eax, [rbx+50h]
0x18001ae82  test    al, 2
0x18001ae84  jnz     short loc_18001AE8B
0x18001ae86  lock or dword ptr [rbx+50h], 2
0x18001ae8b  mov     rcx, cs:qword_18003E9A0
0x18001ae92  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x18001ae99  nop     dword ptr [rax+rax+00h]
0x18001ae9e  call    cs:__imp_KeLeaveGuardedRegion
0x18001aea5  nop     dword ptr [rax+rax+00h]
0x18001aeaa  mov     rbx, [rsp+28h+arg_0]
0x18001aeaf  add     rsp, 20h
0x18001aeb3  pop     rdi
0x18001aeb4  retn
```
