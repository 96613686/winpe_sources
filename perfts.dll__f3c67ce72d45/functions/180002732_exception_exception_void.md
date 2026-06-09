# exception::~exception(void)

- ea: `0x180002732`
- end: `0x180002738`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001eb0`
- `0x180001ec8`
- `0x180001f10`
- `0x180001f50`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180002732`

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
0x180002732  jmp     cs:__imp_??1exception@@UEAA@XZ
```
