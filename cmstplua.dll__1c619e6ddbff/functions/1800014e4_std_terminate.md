# __std_terminate

- ea: `0x1800014e4`
- end: `0x1800014ef`
- name: `__std_terminate`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!?terminate@@YAXXZ` at `0x1800014e8`
- `msvcrt!?terminate@@YAXXZ` at `0x1800014e8`

## pseudocode

```c
void __noreturn _std_terminate()
{
  terminate();
}

```

## disassembly

```asm
0x1800014e4  sub     rsp, 28h
0x1800014e8  call    cs:__imp_?terminate@@YAXXZ; terminate(void)
```
