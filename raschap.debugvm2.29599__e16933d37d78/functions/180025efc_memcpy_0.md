# memcpy_0

- ea: `0x180025efc`
- end: `0x180025f02`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `43`
- callee_count: `0`
- tags: ``

## callers

- `0x180001260`
- `0x180002040`
- `0x180002530`
- `0x180002954`
- `0x1800038d0`
- `0x180004f50`
- `0x180005df0`
- `0x180007370`
- `0x180008cf0`
- `0x180009c08`
- `0x18000a4c0`
- `0x18000a900`
- `0x18000b610`
- `0x18000b9b4`
- `0x18000cd68`
- `0x18000e634`
- `0x18000ead0`
- `0x18000f300`
- `0x1800118a4`
- `0x180012424`
- `0x180015780`
- `0x180015998`
- `0x180015db0`
- `0x180016674`
- `0x180017870`
- `0x180018b50`
- `0x180018c8c`
- `0x180019034`
- `0x1800192e0`
- `0x180019c3c`
- `0x18001a1dc`
- `0x18001a6b0`
- `0x18001ab6c`
- `0x18001ae48`
- `0x18001c188`
- `0x18001cbe4`
- `0x18001d330`
- `0x18001da68`
- `0x18001e018`
- `0x18001e120`
- `0x18001e3bc`
- `0x18001e494`
- `0x180023900`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x180025efc`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy_0(void *a1, const void *Src, size_t Size)
{
  return memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x180025efc  jmp     cs:__imp_memcpy
```
