# HvStatspLockExclusive

- ea: `0x14000e070`
- end: `0x14000e09d`
- name: `HvStatspLockExclusive`
- size: `45`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000fee8`
- `0x14001006c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e079`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e079`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000e08a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000e08a`

## pseudocode

```c
__int64 __fastcall HvStatspLockExclusive(__int64 a1)
{
  KeEnterCriticalRegion();
  return ExAcquirePushLockExclusiveEx(a1, 0);
}

```

## disassembly

```asm
0x14000e070  push    rbx
0x14000e072  sub     rsp, 20h
0x14000e076  mov     rbx, rcx
0x14000e079  call    cs:__imp_KeEnterCriticalRegion
0x14000e080  nop     dword ptr [rax+rax+00h]
0x14000e085  xor     edx, edx
0x14000e087  mov     rcx, rbx
0x14000e08a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000e091  nop     dword ptr [rax+rax+00h]
0x14000e096  add     rsp, 20h
0x14000e09a  pop     rbx
0x14000e09b  retn
```
