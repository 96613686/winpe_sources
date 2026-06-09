# memset_0

- ea: `0x180014dce`
- end: `0x180014dd4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `24`
- callee_count: `0`
- tags: ``

## callers

- `0x180002b54`
- `0x180002dcc`
- `0x18000307c`
- `0x1800037f4`
- `0x180003ba0`
- `0x180004934`
- `0x180006db8`
- `0x180007c2c`
- `0x1800080bc`
- `0x180009090`
- `0x180009630`
- `0x18000aec0`
- `0x18000be70`
- `0x18000cba0`
- `0x18000d610`
- `0x18000d9b0`
- `0x18000e160`
- `0x18000e8e4`
- `0x1800103a0`
- `0x180010bdc`
- `0x180013178`
- `0x1800136a0`
- `0x180013cc0`
- `0x180014328`

## import_xrefs

- `msvcrt!memset` at `0x180014dce`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset_0(void *a1, int Val, size_t Size)
{
  return memset(a1, Val, Size);
}

```

## disassembly

```asm
0x180014dce  jmp     cs:__imp_memset
```
