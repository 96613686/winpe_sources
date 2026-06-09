# FILockSharedAcquire

- ea: `0x140001c00`
- end: `0x140001c2b`
- name: `FILockSharedAcquire`
- size: `43`
- prototype: ``
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x14000e148`
- `0x14000f9b8`
- `0x140010350`
- `0x140010cd0`
- `0x140012850`
- `0x14001313c`
- `0x14001334c`
- `0x140013560`
- `0x140013d70`
- `0x140014648`
- `0x140015460`
- `0x1400157b0`
- `0x140015a48`
- `0x140015d3c`
- `0x14001606c`
- `0x140016494`
- `0x140016fa0`
- `0x140017284`
- `0x140017510`

## import_xrefs

- `ntoskrnl!ExfAcquirePushLockShared` at `0x140001c18`
- `ntoskrnl!ExfAcquirePushLockShared` at `0x140001c18`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001c09`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001c09`

## pseudocode

```c
__int64 __fastcall FILockSharedAcquire(__int64 a1)
{
  KeEnterCriticalRegion();
  return ExfAcquirePushLockShared(a1);
}

```

## disassembly

```asm
0x140001c00  push    rbx
0x140001c02  sub     rsp, 20h
0x140001c06  mov     rbx, rcx
0x140001c09  call    cs:__imp_KeEnterCriticalRegion
0x140001c10  nop     dword ptr [rax+rax+00h]
0x140001c15  mov     rcx, rbx
0x140001c18  call    cs:__imp_ExfAcquirePushLockShared
0x140001c1f  nop     dword ptr [rax+rax+00h]
0x140001c24  add     rsp, 20h
0x140001c28  pop     rbx
0x140001c29  retn
```
