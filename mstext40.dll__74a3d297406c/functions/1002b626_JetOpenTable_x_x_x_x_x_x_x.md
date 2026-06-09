# JetOpenTable(x,x,x,x,x,x,x)

- ea: `0x1002b626`
- end: `0x1002b62c`
- name: `_JetOpenTable@28`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1001ba80`

## import_xrefs

- `msjet40!__imp__JetOpenTable@28` at `0x1002b626`

## pseudocode

```c
// attributes: thunk
int __stdcall JetOpenTable(int a1, int a2, int a3, int a4, int a5, int a6, int a7)
{
  return __imp__JetOpenTable@28(a1, a2, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x1002b626  jmp     ds:__imp__JetOpenTable@28
```
