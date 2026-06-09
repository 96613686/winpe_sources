# exception::~exception(void)

- ea: `0x18000268a`
- end: `0x180002690`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001df4`
- `0x180001e0c`
- `0x180001e50`
- `0x180001e90`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x18000268a`

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
0x18000268a  jmp     cs:__imp_??1exception@@UEAA@XZ
```
