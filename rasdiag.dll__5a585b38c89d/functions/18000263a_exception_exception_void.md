# exception::~exception(void)

- ea: `0x18000263a`
- end: `0x180002640`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800012e4`
- `0x1800012fc`
- `0x180001340`
- `0x180001380`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x18000263a`

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
0x18000263a  jmp     cs:__imp_??1exception@@UEAA@XZ
```
