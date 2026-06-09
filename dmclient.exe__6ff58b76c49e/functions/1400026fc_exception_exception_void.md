# exception::~exception(void)

- ea: `0x1400026fc`
- end: `0x140002702`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140002168`
- `0x140002180`
- `0x140002190`
- `0x1400021d0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x1400026fc`

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
0x1400026fc  jmp     cs:__imp_??1exception@@UEAA@XZ
```
