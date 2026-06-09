# CLRCreateInstance_0

- ea: `0x18001ecdd`
- end: `0x18001ece3`
- name: `CLRCreateInstance_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180003168`

## import_xrefs

- `mscoree!CLRCreateInstance` at `0x18001ecdd`

## pseudocode

```c
// attributes: thunk
__int64 CLRCreateInstance_0()
{
  return CLRCreateInstance();
}

```

## disassembly

```asm
0x18001ecdd  jmp     cs:__imp_CLRCreateInstance
```
