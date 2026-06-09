# strcmp_0

- ea: `0x18000a7da`
- end: `0x18000a7e0`
- name: `strcmp_0`
- size: `6`
- prototype: `int __cdecl(const char *Str1, const char *Str2)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180003c90`
- `0x1800052a0`
- `0x180007180`

## import_xrefs

- `msvcrt!strcmp` at `0x18000a7da`

## pseudocode

```c
// attributes: thunk
int __cdecl strcmp_0(const char *Str1, const char *Str2)
{
  return strcmp(Str1, Str2);
}

```

## disassembly

```asm
0x18000a7da  jmp     cs:__imp_strcmp
```
