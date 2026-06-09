# lldpClientFromHandle

- ea: `0x140004e30`
- end: `0x140004e45`
- name: `lldpClientFromHandle`
- size: `21`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140005030`
- `0x140005060`
- `0x14000ef10`
- `0x14000efd0`

## callees

- `0x140004e30`

## pseudocode

```c
_DWORD *__fastcall lldpClientFromHandle(_DWORD *a1)
{
  _DWORD *result; // rax

  result = 0;
  if ( a1 )
  {
    if ( *a1 != 1665420364 )
      return 0;
    return a1;
  }
  return result;
}

```

## disassembly

```asm
0x140004e30  xor     eax, eax
0x140004e32  test    rcx, rcx
0x140004e35  jz      short locret_140004E44
0x140004e37  cmp     dword ptr [rcx], 63444C4Ch
0x140004e3d  cmovnz  rcx, rax
0x140004e41  mov     rax, rcx
0x140004e44  retn
```
