# __o__configure_narrow_argv

- ea: `0x10035ee0`
- end: `0x10035ee6`
- name: `__o__configure_narrow_argv`
- size: `6`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x100355c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configure_narrow_argv` at `0x10035ee0`

## pseudocode

```c
// attributes: thunk
errno_t __cdecl _o__configure_narrow_argv(_crt_argv_mode mode)
{
  return __configure_narrow_argv(mode);
}

```

## disassembly

```asm
0x10035ee0  jmp     ds:__imp___configure_narrow_argv
```
