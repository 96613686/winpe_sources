# _o___std_exception_copy_0

- ea: `0x14000301a`
- end: `0x140003020`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140004984`
- `0x140004b60`
- `0x140004ba4`
- `0x140004c10`
- `0x14000e780`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x14000301a`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy_0()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x14000301a  jmp     cs:__imp__o___std_exception_copy
```
