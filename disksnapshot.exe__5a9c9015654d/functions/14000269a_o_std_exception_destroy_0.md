# _o___std_exception_destroy_0

- ea: `0x14000269a`
- end: `0x1400026a0`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140003024`
- `0x140003040`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x14000269a`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_destroy_0()
{
  return __std_exception_destroy();
}

```

## disassembly

```asm
0x14000269a  jmp     cs:__imp___std_exception_destroy
```
