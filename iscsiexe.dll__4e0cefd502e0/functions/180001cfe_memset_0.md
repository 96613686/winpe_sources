# memset_0

- ea: `0x180001cfe`
- end: `0x180001d04`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `56`
- callee_count: `0`
- tags: ``

## callers

- `0x180001df4`
- `0x180001fb8`
- `0x1800027cc`
- `0x180002bc0`
- `0x180004af8`
- `0x180004cf8`
- `0x180004ee8`
- `0x180005290`
- `0x1800060e0`
- `0x180006c30`
- `0x1800074e8`
- `0x180008960`
- `0x180008af8`
- `0x180008e84`
- `0x180009898`
- `0x180009f14`
- `0x18000a488`
- `0x18000a748`
- `0x18000b720`
- `0x18000c124`
- `0x18000c474`
- `0x18000ce28`
- `0x18000d090`
- `0x18000d6f0`
- `0x18000d8ac`
- `0x18000dcc0`
- `0x18000e040`
- `0x18000ecdc`
- `0x18000f5b0`
- `0x18000fbdc`
- `0x1800111e0`
- `0x180011250`
- `0x1800113b4`
- `0x180013548`
- `0x180014888`
- `0x180014960`
- `0x180014b08`
- `0x180014b74`
- `0x180014d7c`
- `0x180014e84`
- `0x1800156e0`
- `0x180015918`
- `0x180015c9c`
- `0x1800165c4`
- `0x180016780`
- `0x180016934`
- `0x180016d20`
- `0x180017e50`
- `0x18001827c`
- `0x1800192e8`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180001cfe`

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
0x180001cfe  jmp     cs:__imp_memset
```
