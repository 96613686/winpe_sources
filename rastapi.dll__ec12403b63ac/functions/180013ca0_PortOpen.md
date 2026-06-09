# PortOpen

- ea: `0x180013ca0`
- end: `0x180013cb6`
- name: `PortOpen`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180013ccc`

## pseudocode

```c
DWORD __fastcall PortOpen(char *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  return PortOpenInternal(a1, a2, a3, a4, 0);
}

```

## disassembly

```asm
0x180013ca0  sub     rsp, 38h
0x180013ca4  mov     dword ptr [rsp+38h+var_18], 0; char
0x180013cac  call    PortOpenInternal
0x180013cb1  add     rsp, 38h
0x180013cb5  retn
```
