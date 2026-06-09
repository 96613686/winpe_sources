# exception::~exception(void)

- ea: `0x180001c5c`
- end: `0x180001c62`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000150c`
- `0x180001524`
- `0x180001530`
- `0x180001570`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180001c5c`

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
0x180001c5c  jmp     cs:__imp_??1exception@@UEAA@XZ
```
