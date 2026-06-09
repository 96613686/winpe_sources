# exception::~exception(void)

- ea: `0x180001f1d`
- end: `0x180001f23`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001478`
- `0x180001490`
- `0x1800014a0`
- `0x1800014e0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180001f1d`

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
0x180001f1d  jmp     cs:__imp_??1exception@@UEAA@XZ
```
