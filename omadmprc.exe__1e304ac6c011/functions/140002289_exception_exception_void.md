# exception::~exception(void)

- ea: `0x140002289`
- end: `0x14000228f`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001d9c`
- `0x140001db4`
- `0x140001dc0`
- `0x140001e00`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x140002289`

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
0x140002289  jmp     cs:__imp_??1exception@@UEAA@XZ
```
