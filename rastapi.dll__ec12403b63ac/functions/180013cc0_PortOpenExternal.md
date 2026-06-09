# PortOpenExternal

- ea: `0x180013cc0`
- end: `0x180013cc5`
- name: `PortOpenExternal`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180013ccc`

## pseudocode

```c
// attributes: thunk
DWORD __fastcall PortOpenExternal(char *String1, _QWORD *a2, __int64 a3, __int64 a4, char a5)
{
  return PortOpenInternal(String1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180013cc0  jmp     PortOpenInternal
```
