# RtlCompareMemory

- ea: `0x14001c967`
- end: `0x14001c96d`
- name: `RtlCompareMemory`
- size: `6`
- prototype: `SIZE_T __stdcall(const void *Source1, const void *Source2, SIZE_T Length)`
- caller_count: `8`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140007550`
- `0x1400a78b8`
- `0x1400a80c4`
- `0x1400a8504`
- `0x1400a881c`
- `0x1400a9c24`
- `0x1400a9ce0`
- `0x1400a9d40`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14001c967`

## pseudocode

```c
// attributes: thunk
SIZE_T __stdcall RtlCompareMemory(const void *Source1, const void *Source2, SIZE_T Length)
{
  return __imp_RtlCompareMemory(Source1, Source2, Length);
}

```

## disassembly

```asm
0x14001c967  jmp     cs:__imp_RtlCompareMemory
```
