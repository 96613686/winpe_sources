# DfscGetDevicelessNetUseTable

- ea: `0x140025d4c`
- end: `0x140025d62`
- name: `DfscGetDevicelessNetUseTable`
- size: `22`
- prototype: `PRTL_AVL_TABLE __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14001338c`
- `0x140017458`
- `0x14002545c`
- `0x140025aa0`
- `0x140025f20`

## callees

- `0x140025d4c`

## pseudocode

```c
PRTL_AVL_TABLE __fastcall DfscGetDevicelessNetUseTable(__int64 a1)
{
  if ( a1 )
    return *(PRTL_AVL_TABLE *)(a1 + 264);
  else
    return qword_14000C710;
}

```

## disassembly

```asm
0x140025d4c  test    rcx, rcx
0x140025d4f  jnz     short loc_140025D5A
0x140025d51  mov     rax, cs:qword_14000C710
0x140025d58  retn
0x140025d5a  mov     rax, [rcx+108h]
0x140025d61  retn
```
