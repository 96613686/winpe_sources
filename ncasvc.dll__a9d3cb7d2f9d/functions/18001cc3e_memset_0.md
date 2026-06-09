# memset_0

- ea: `0x18001cc3e`
- end: `0x18001cc44`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `47`
- callee_count: `0`
- tags: ``

## callers

- `0x180005770`
- `0x180005d04`
- `0x180005df8`
- `0x180006190`
- `0x1800067e0`
- `0x180006c60`
- `0x180006ec0`
- `0x180007360`
- `0x180008ee8`
- `0x180009714`
- `0x180009f1c`
- `0x18000a398`
- `0x18000a954`
- `0x18000c1d0`
- `0x18000ce40`
- `0x18000cfa0`
- `0x18000d720`
- `0x18000db90`
- `0x18000e250`
- `0x18000e5d0`
- `0x18000ebf0`
- `0x18000f1b0`
- `0x18000f430`
- `0x18000fcf0`
- `0x18000fe20`
- `0x1800100f0`
- `0x180010430`
- `0x180010820`
- `0x180010c70`
- `0x1800112ac`
- `0x1800123a4`
- `0x180012570`
- `0x180012950`
- `0x1800136e0`
- `0x180013c10`
- `0x180014330`
- `0x180014900`
- `0x180014b80`
- `0x180014f40`
- `0x1800156d0`
- `0x180015f20`
- `0x1800164e0`
- `0x1800169b0`
- `0x180016ee4`
- `0x180018090`
- `0x180018930`
- `0x18001b2b0`

## import_xrefs

- `msvcrt!memset` at `0x18001cc3e`

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
0x18001cc3e  jmp     cs:__imp_memset
```
