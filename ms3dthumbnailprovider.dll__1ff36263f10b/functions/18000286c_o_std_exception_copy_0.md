# _o___std_exception_copy_0

- ea: `0x18000286c`
- end: `0x180002872`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180005044`
- `0x180005158`
- `0x18000519c`
- `0x180005208`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18000286c`

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
0x18000286c  jmp     cs:__imp__o___std_exception_copy
```
