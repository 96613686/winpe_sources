# _o___std_exception_destroy_0

- ea: `0x18000297e`
- end: `0x180002984`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180007c48`
- `0x180007c70`
- `0x180007ca0`
- `0x180007cf0`
- `0x1800081e8`
- `0x180008210`
- `0x18000c5fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x18000297e`

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
0x18000297e  jmp     cs:__imp___std_exception_destroy
```
