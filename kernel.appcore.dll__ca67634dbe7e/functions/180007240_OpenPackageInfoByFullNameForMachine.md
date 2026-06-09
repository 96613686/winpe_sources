# OpenPackageInfoByFullNameForMachine

- ea: `0x180007240`
- end: `0x180007246`
- name: `OpenPackageInfoByFullNameForMachine`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!OpenPackageInfoByFullNameForMachine` at `0x180007240`

## pseudocode

```c
// attributes: thunk
__int64 OpenPackageInfoByFullNameForMachine()
{
  return __imp_OpenPackageInfoByFullNameForMachine();
}

```

## disassembly

```asm
0x180007240  jmp     cs:__imp_OpenPackageInfoByFullNameForMachine
```
