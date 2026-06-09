# FILockExclusiveRelease

- ea: `0x140001da0`
- end: `0x140001dc2`
- name: `FILockExclusiveRelease`
- size: `34`
- prototype: ``
- caller_count: `51`
- callee_count: `0`
- tags: ``

## callers

- `0x14000d008`
- `0x14000d1b8`
- `0x14000d3cc`
- `0x14000d5cc`
- `0x14000df58`
- `0x14000e148`
- `0x14000e5a0`
- `0x14000e7e0`
- `0x14000e8d8`
- `0x14000f510`
- `0x14000f9b8`
- `0x14000ff0c`
- `0x14000ffb8`
- `0x140010050`
- `0x140010350`
- `0x14001070c`
- `0x140010808`
- `0x140010cd0`
- `0x140012850`
- `0x140012fdc`
- `0x14001313c`
- `0x14001334c`
- `0x140013560`
- `0x1400138d4`
- `0x140013bc0`
- `0x140013d70`
- `0x1400145b8`
- `0x140014648`
- `0x140014940`
- `0x140015460`
- `0x1400156d4`
- `0x1400157b0`
- `0x140015800`
- `0x14001588c`
- `0x140015950`
- `0x140015a00`
- `0x140015a48`
- `0x140015d3c`
- `0x14001606c`
- `0x140016494`
- `0x140016644`
- `0x140016710`
- `0x140016788`
- `0x14001689c`
- `0x140016910`
- `0x140016a40`
- `0x140016bc0`
- `0x140016ea0`
- `0x140016fa0`
- `0x140017284`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001db0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001db0`
- `ntoskrnl!ExfReleasePushLock` at `0x140001da4`
- `ntoskrnl!ExfReleasePushLock` at `0x140001da4`

## pseudocode

```c
void __fastcall FILockExclusiveRelease(__int64 a1)
{
  ExfReleasePushLock(a1);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140001da0  sub     rsp, 28h
0x140001da4  call    cs:__imp_ExfReleasePushLock
0x140001dab  nop     dword ptr [rax+rax+00h]
0x140001db0  call    cs:__imp_KeLeaveCriticalRegion
0x140001db7  nop     dword ptr [rax+rax+00h]
0x140001dbc  add     rsp, 28h
0x140001dc0  retn
```
