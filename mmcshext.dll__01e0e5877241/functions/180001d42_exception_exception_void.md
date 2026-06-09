# exception::~exception(void)

- ea: `0x180001d42`
- end: `0x180001d48`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800012a8`
- `0x1800012c0`
- `0x1800012d0`
- `0x180001310`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180001d42`

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
0x180001d42  jmp     cs:__imp_??1exception@@UEAA@XZ
```
