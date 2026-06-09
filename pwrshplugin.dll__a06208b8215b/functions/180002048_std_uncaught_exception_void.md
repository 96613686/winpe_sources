# std::uncaught_exception(void)

- ea: `0x180002048`
- end: `0x18000204f`
- name: `?uncaught_exception@std@@YA_NXZ`
- size: `7`
- prototype: `bool(void)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180007018`
- `0x180007208`
- `0x1800075d8`
- `0x1800077d0`

## import_xrefs

- `msvcrt!__uncaught_exception` at `0x180002048`

## pseudocode

```c
// attributes: thunk
bool std::uncaught_exception(void)
{
  return __uncaught_exception();
}

```

## disassembly

```asm
0x180002048  jmp     cs:__imp_?__uncaught_exception@@YA_NXZ; __uncaught_exception(void)
```
