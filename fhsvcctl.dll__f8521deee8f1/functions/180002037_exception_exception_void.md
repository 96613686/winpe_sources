# exception::~exception(void)

- ea: `0x180002037`
- end: `0x18000203d`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001f78`
- `0x180001fe0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180002037`

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
0x180002037  jmp     cs:__imp_??1exception@@UEAA@XZ
```
