# exception::~exception(void)

- ea: `0x14000271c`
- end: `0x140002722`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x14000218c`
- `0x1400021a4`
- `0x1400021b0`
- `0x1400021f0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x14000271c`

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
0x14000271c  jmp     cs:__imp_??1exception@@UEAA@XZ
```
