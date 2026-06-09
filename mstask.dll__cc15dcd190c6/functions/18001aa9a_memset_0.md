# memset_0

- ea: `0x18001aa9a`
- end: `0x18001aaa0`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `39`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x180001610`
- `0x180004220`
- `0x180005270`
- `0x180005cd0`
- `0x1800069e8`
- `0x180006ba0`
- `0x180007860`
- `0x180008688`
- `0x180009490`
- `0x18000b740`
- `0x18000b920`
- `0x18000beb8`
- `0x18000c93c`
- `0x18000cdcc`
- `0x18000e578`
- `0x18000e750`
- `0x18000f510`
- `0x18000f850`
- `0x18000fe24`
- `0x18000ff30`
- `0x180010710`
- `0x180010c90`
- `0x1800110c4`
- `0x18001140c`
- `0x1800116c0`
- `0x180011c90`
- `0x180011fc0`
- `0x180012a04`
- `0x180013fd8`
- `0x180014328`
- `0x180014aa0`
- `0x180016b70`
- `0x180017e90`
- `0x180018300`
- `0x1800199e4`
- `0x180019bb0`
- `0x18001a43c`
- `0x18001a5e4`

## import_xrefs

- `msvcrt!memset` at `0x18001aa9a`

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
0x18001aa9a  jmp     cs:__imp_memset
```
