# SchedMapRpcError(ulong)

- ea: `0x18000ca2c`
- end: `0x18000ca4b`
- name: `?SchedMapRpcError@@YAJK@Z`
- size: `31`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004220`
- `0x18000b740`
- `0x18000be60`
- `0x18000be90`
- `0x180011fc0`

## callees

- `0x18000ca2c`

## pseudocode

```c
__int64 __fastcall SchedMapRpcError(int a1)
{
  if ( a1 == 1753 )
  {
    return (unsigned int)-2147216619;
  }
  else if ( a1 > 0 )
  {
    return (unsigned __int16)a1 | 0x80070000;
  }
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x18000ca2c  cmp     ecx, 6D9h
0x18000ca32  jnz     short loc_18000CA3B
0x18000ca34  mov     ecx, 80041315h
0x18000ca39  jmp     short loc_18000CA48
0x18000ca3b  test    ecx, ecx
0x18000ca3d  jle     short loc_18000CA48
0x18000ca3f  movzx   ecx, cx
0x18000ca42  or      ecx, 80070000h
0x18000ca48  mov     eax, ecx
0x18000ca4a  retn
```
