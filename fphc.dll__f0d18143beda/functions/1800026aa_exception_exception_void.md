# exception::~exception(void)

- ea: `0x1800026aa`
- end: `0x1800026b0`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001358`
- `0x180001370`
- `0x1800013b0`
- `0x1800013f0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x1800026aa`

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
0x1800026aa  jmp     cs:__imp_??1exception@@UEAA@XZ
```
