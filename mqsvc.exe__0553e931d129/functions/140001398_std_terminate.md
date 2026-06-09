# __std_terminate

- ea: `0x140001398`
- end: `0x1400013a3`
- name: `__std_terminate`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!?terminate@@YAXXZ` at `0x14000139c`
- `msvcrt!?terminate@@YAXXZ` at `0x14000139c`

## pseudocode

```c
void __noreturn _std_terminate()
{
  terminate();
}

```

## disassembly

```asm
0x140001398  sub     rsp, 28h
0x14000139c  call    cs:__imp_?terminate@@YAXXZ; terminate(void)
```
