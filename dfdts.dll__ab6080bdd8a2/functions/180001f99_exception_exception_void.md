# exception::~exception(void)

- ea: `0x180001f99`
- end: `0x180001f9f`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000116c`
- `0x180001184`
- `0x1800011c0`
- `0x180001200`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180001f99`

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
0x180001f99  jmp     cs:__imp_??1exception@@UEAA@XZ
```
