# _o__initialize_wide_environment_0

- ea: `0x140001c1e`
- end: `0x140001c24`
- name: `_o__initialize_wide_environment_0`
- size: `6`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001090`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__initialize_wide_environment` at `0x140001c1e`

## pseudocode

```c
// attributes: thunk
int __cdecl o__initialize_wide_environment_0()
{
  return _initialize_wide_environment();
}

```

## disassembly

```asm
0x140001c1e  jmp     cs:__imp__initialize_wide_environment
```
