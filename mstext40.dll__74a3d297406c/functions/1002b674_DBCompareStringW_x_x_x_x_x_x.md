# DBCompareStringW(x,x,x,x,x,x)

- ea: `0x1002b674`
- end: `0x1002b67a`
- name: `_DBCompareStringW@24`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1000bf80`

## import_xrefs

- `mswstr10!__imp__DBCompareStringW@24` at `0x1002b674`

## pseudocode

```c
// attributes: thunk
int __stdcall DBCompareStringW(int a1, int a2, int a3, int a4, int a5, int a6)
{
  return __imp__DBCompareStringW@24(a1, a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x1002b674  jmp     ds:__imp__DBCompareStringW@24
```
