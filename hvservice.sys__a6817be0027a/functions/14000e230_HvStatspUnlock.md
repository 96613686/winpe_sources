# HvStatspUnlock

- ea: `0x14000e230`
- end: `0x14000e254`
- name: `HvStatspUnlock`
- size: `36`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000fee8`
- `0x14001006c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e242`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e242`
- `ntoskrnl!ExReleasePushLockEx` at `0x14000e236`
- `ntoskrnl!ExReleasePushLockEx` at `0x14000e236`

## pseudocode

```c
void __fastcall HvStatspUnlock(__int64 a1)
{
  ExReleasePushLockEx(a1, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14000e230  sub     rsp, 28h
0x14000e234  xor     edx, edx
0x14000e236  call    cs:__imp_ExReleasePushLockEx
0x14000e23d  nop     dword ptr [rax+rax+00h]
0x14000e242  call    cs:__imp_KeLeaveCriticalRegion
0x14000e249  nop     dword ptr [rax+rax+00h]
0x14000e24e  add     rsp, 28h
0x14000e252  retn
```
