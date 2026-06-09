# _configthreadlocale

- ea: `0x140003056`
- end: `0x14000305c`
- name: `_configthreadlocale`
- size: `6`
- prototype: `int __cdecl(int Flag)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140002360`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configthreadlocale` at `0x140003056`

## pseudocode

```c
// attributes: thunk
int __cdecl configthreadlocale(int Flag)
{
  return _o__configthreadlocale(Flag);
}

```

## disassembly

```asm
0x140003056  jmp     cs:__imp__o__configthreadlocale
```
