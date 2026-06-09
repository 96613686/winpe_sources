# RtdspInitializeLock

- ea: `0x1400018b0`
- end: `0x1400018c8`
- name: `RtdspInitializeLock`
- size: `24`
- prototype: `void __fastcall(struct _KMUTANT *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14000a5d0`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x1400018b6`
- `ntoskrnl!KeInitializeMutex` at `0x1400018b6`

## pseudocode

```c
void __fastcall RtdspInitializeLock(struct _KMUTANT *a1)
{
  KeInitializeMutex(a1, 0);
}

```

## disassembly

```asm
0x1400018b0  sub     rsp, 28h
0x1400018b4  xor     edx, edx; Level
0x1400018b6  call    cs:__imp_KeInitializeMutex
0x1400018bd  nop     dword ptr [rax+rax+00h]
0x1400018c2  add     rsp, 28h
0x1400018c6  retn
```
