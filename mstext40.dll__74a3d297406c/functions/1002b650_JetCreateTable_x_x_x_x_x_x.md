# JetCreateTable(x,x,x,x,x,x)

- ea: `0x1002b650`
- end: `0x1002b656`
- name: `_JetCreateTable@24`
- size: `6`
- prototype: `int __stdcall(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1001c680`

## import_xrefs

- `msjet40!__imp__JetCreateTable@24` at `0x1002b650`

## pseudocode

```c
// attributes: thunk
int __stdcall JetCreateTable(int a1, int a2, int a3, int a4, int a5, int a6)
{
  return __imp__JetCreateTable@24(a1, a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x1002b650  jmp     ds:__imp__JetCreateTable@24
```
