# exception::~exception(void)

- ea: `0x140001fad`
- end: `0x140001fb3`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001618`
- `0x140001630`
- `0x140001640`
- `0x140001680`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x140001fad`

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
0x140001fad  jmp     cs:__imp_??1exception@@UEAA@XZ
```
