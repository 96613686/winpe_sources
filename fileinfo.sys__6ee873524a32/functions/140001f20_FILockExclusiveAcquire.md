# FILockExclusiveAcquire

- ea: `0x140001f20`
- end: `0x140001f4b`
- name: `FILockExclusiveAcquire`
- size: `43`
- prototype: ``
- caller_count: `43`
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
- `0x140012fdc`
- `0x14001334c`
- `0x1400138d4`
- `0x140013bc0`
- `0x140013d70`
- `0x1400145b8`
- `0x140014940`
- `0x140015460`
- `0x1400156d4`
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
- `0x140017510`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140001f29`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001f29`
- `ntoskrnl!ExfAcquirePushLockExclusive` at `0x140001f38`
- `ntoskrnl!ExfAcquirePushLockExclusive` at `0x140001f38`

## pseudocode

```c
__int64 __fastcall FILockExclusiveAcquire(__int64 a1)
{
  KeEnterCriticalRegion();
  return ExfAcquirePushLockExclusive(a1);
}

```

## disassembly

```asm
0x140001f20  push    rbx
0x140001f22  sub     rsp, 20h
0x140001f26  mov     rbx, rcx
0x140001f29  call    cs:__imp_KeEnterCriticalRegion
0x140001f30  nop     dword ptr [rax+rax+00h]
0x140001f35  mov     rcx, rbx
0x140001f38  call    cs:__imp_ExfAcquirePushLockExclusive
0x140001f3f  nop     dword ptr [rax+rax+00h]
0x140001f44  add     rsp, 20h
0x140001f48  pop     rbx
0x140001f49  retn
```
