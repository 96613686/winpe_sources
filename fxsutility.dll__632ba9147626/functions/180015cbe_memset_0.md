# memset_0

- ea: `0x180015cbe`
- end: `0x180015cc4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `27`
- callee_count: `0`
- tags: ``

## callers

- `0x180002274`
- `0x180004680`
- `0x180005200`
- `0x1800052b0`
- `0x18000613c`
- `0x18000701c`
- `0x180007288`
- `0x180007790`
- `0x1800079f8`
- `0x180007c94`
- `0x180008828`
- `0x180008bcc`
- `0x1800099e4`
- `0x18000bdc8`
- `0x18000c1cc`
- `0x18000cd20`
- `0x18000d210`
- `0x18000de40`
- `0x18000dfe4`
- `0x18000edb0`
- `0x18000f3e4`
- `0x18000f784`
- `0x18000fd8c`
- `0x1800101a0`
- `0x180011cb0`
- `0x180012060`
- `0x1800131f0`

## import_xrefs

- `msvcrt!memset` at `0x180015cbe`

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
0x180015cbe  jmp     cs:__imp_memset
```
