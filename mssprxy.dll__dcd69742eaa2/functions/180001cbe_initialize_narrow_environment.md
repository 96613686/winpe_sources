# _initialize_narrow_environment

- ea: `0x180001cbe`
- end: `0x180001cc4`
- name: `_initialize_narrow_environment`
- size: `6`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800015dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__initialize_narrow_environment` at `0x180001cbe`

## pseudocode

```c
// attributes: thunk
int __cdecl initialize_narrow_environment()
{
  return _initialize_narrow_environment();
}

```

## disassembly

```asm
0x180001cbe  jmp     cs:__imp__initialize_narrow_environment
```
