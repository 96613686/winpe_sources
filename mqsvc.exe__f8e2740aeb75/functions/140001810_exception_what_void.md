# exception::what(void)

- ea: `0x140001810`
- end: `0x140001816`
- name: `?what@exception@@UEBAPEBDXZ_0`
- size: `6`
- prototype: `const char *__fastcall(exception *this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!?what@exception@@UEBAPEBDXZ` at `0x140001810`

## pseudocode

```c
// attributes: thunk
const char *__fastcall exception::what(exception *this)
{
  return __imp_?what@exception@@UEBAPEBDXZ(this);
}

```

## disassembly

```asm
0x140001810  jmp     cs:__imp_?what@exception@@UEBAPEBDXZ
```
