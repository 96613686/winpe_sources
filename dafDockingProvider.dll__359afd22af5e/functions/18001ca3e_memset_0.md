# memset_0

- ea: `0x18001ca3e`
- end: `0x18001ca44`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `46`
- callee_count: `0`
- tags: ``

## callers

- `0x180002710`
- `0x180002978`
- `0x180002c14`
- `0x1800037a8`
- `0x180003b4c`
- `0x1800048b4`
- `0x180006c98`
- `0x18000709c`
- `0x180007d20`
- `0x180008220`
- `0x180008510`
- `0x180008738`
- `0x18000a428`
- `0x18000a810`
- `0x18000bc20`
- `0x18000bd70`
- `0x18000c6e4`
- `0x18000ce20`
- `0x18000d658`
- `0x18000d9b4`
- `0x18000e344`
- `0x18000e5a4`
- `0x18000e7d0`
- `0x18000ee64`
- `0x18000f3ec`
- `0x180010d58`
- `0x180010f04`
- `0x180012ba0`
- `0x180012ddc`
- `0x1800144a8`
- `0x1800151b8`
- `0x180015460`
- `0x180015700`
- `0x1800160c0`
- `0x180016480`
- `0x180018540`
- `0x180018be0`
- `0x180019260`
- `0x18001a9e0`
- `0x18001aad0`
- `0x18001abac`
- `0x18001afd0`
- `0x18001b428`
- `0x18001bad0`
- `0x18001bfb0`
- `0x18001c1d0`

## import_xrefs

- `msvcrt!memset` at `0x18001ca3e`

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
0x18001ca3e  jmp     cs:__imp_memset
```
