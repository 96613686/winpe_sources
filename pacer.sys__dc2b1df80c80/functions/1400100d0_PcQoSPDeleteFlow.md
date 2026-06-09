# PcQoSPDeleteFlow

- ea: `0x1400100d0`
- end: `0x1400100e2`
- name: `PcQoSPDeleteFlow`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140005578`

## pseudocode

```c
__int64 __fastcall PcQoSPDeleteFlow(char **a1, __int64 a2)
{
  return PcpDeleteFlow(*a1, a2);
}

```

## disassembly

```asm
0x1400100d0  sub     rsp, 28h
0x1400100d4  mov     rcx, [rcx]; P
0x1400100d7  call    PcpDeleteFlow
0x1400100dc  add     rsp, 28h
0x1400100e0  retn
```
