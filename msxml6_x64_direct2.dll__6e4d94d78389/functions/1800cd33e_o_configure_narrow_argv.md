# _o__configure_narrow_argv

- ea: `0x1800cd33e`
- end: `0x1800cd344`
- name: `_o__configure_narrow_argv`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800cc730`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configure_narrow_argv` at `0x1800cd33e`

## pseudocode

```c
// attributes: thunk
__int64 o__configure_narrow_argv()
{
  return _o__configure_narrow_argv();
}

```

## disassembly

```asm
0x1800cd33e  jmp     cs:__imp__o__configure_narrow_argv
```
