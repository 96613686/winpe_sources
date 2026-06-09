# __p__commode_0

- ea: `0x140013d5a`
- end: `0x140013d60`
- name: `__p__commode_0`
- size: `6`
- prototype: `int *__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140012f60`

## import_xrefs

- `ucrtbase_clr0400!__p__commode` at `0x140013d5a`

## pseudocode

```c
// attributes: thunk
int *__cdecl _p__commode_0()
{
  return __p__commode();
}

```

## disassembly

```asm
0x140013d5a  jmp     cs:__imp___p__commode
```
