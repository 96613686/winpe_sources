# JetSetSystemParameter(x,x,x,x,x)

- ea: `0x1002b64a`
- end: `0x1002b650`
- name: `_JetSetSystemParameter@20`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1001ca20`
- `0x1001cb00`

## import_xrefs

- `msjet40!__imp__JetSetSystemParameter@20` at `0x1002b64a`

## pseudocode

```c
// attributes: thunk
int __stdcall JetSetSystemParameter(int a1, int a2, int a3, int a4, int a5)
{
  return __imp__JetSetSystemParameter@20(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x1002b64a  jmp     ds:__imp__JetSetSystemParameter@20
```
