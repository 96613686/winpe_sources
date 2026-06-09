# exception::~exception(void)

- ea: `0x180001de4`
- end: `0x180001dea`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800011a0`
- `0x1800011c0`
- `0x180001200`
- `0x1800077c4`
- `0x180007960`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180001de4`

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
0x180001de4  jmp     cs:__imp_??1exception@@UEAA@XZ
```
