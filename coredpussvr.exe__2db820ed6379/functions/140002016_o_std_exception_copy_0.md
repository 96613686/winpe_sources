# _o___std_exception_copy_0

- ea: `0x140002016`
- end: `0x14000201c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001e28`
- `0x140001e94`
- `0x140002c3c`
- `0x140002d50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x140002016`

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
0x140002016  jmp     cs:__imp__o___std_exception_copy
```
