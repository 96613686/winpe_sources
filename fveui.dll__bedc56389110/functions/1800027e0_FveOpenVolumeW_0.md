# FveOpenVolumeW_0

- ea: `0x1800027e0`
- end: `0x1800027e6`
- name: `FveOpenVolumeW_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180012be8`
- `0x180013b88`

## import_xrefs

- `FVEAPI!FveOpenVolumeW` at `0x1800027e0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall FveOpenVolumeW_0(__int64 a1, __int64 a2, __int64 a3)
{
  return FveOpenVolumeW(a1, a2, a3);
}

```

## disassembly

```asm
0x1800027e0  jmp     cs:__imp_FveOpenVolumeW
```
