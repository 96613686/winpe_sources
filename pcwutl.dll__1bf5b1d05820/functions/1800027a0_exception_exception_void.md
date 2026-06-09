# exception::~exception(void)

- ea: `0x1800027a0`
- end: `0x1800027a6`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000162c`
- `0x180001644`
- `0x180001680`
- `0x1800016c0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x1800027a0`

## pseudocode

```c
// attributes: thunk
void __fastcall exception::~exception(exception *this)
{
  __imp_??1exception@@UEAA@XZ(this);
}

```

## disassembly

```asm
0x1800027a0  jmp     cs:__imp_??1exception@@UEAA@XZ
```
