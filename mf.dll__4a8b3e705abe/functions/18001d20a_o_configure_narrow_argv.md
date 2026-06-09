# _o__configure_narrow_argv

- ea: `0x18001d20a`
- end: `0x18001d210`
- name: `_o__configure_narrow_argv`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18001c650`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configure_narrow_argv` at `0x18001d20a`

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
0x18001d20a  jmp     cs:__imp__o__configure_narrow_argv
```
