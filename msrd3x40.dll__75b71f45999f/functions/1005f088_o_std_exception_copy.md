# __o___std_exception_copy

- ea: `0x1005f088`
- end: `0x1005f08e`
- name: `__o___std_exception_copy`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x10008550`
- `0x10009790`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1005f088`

## pseudocode

```c
// attributes: thunk
int _o___std_exception_copy()
{
  return __o___std_exception_copy();
}

```

## disassembly

```asm
0x1005f088  jmp     ds:__imp___o___std_exception_copy
```
