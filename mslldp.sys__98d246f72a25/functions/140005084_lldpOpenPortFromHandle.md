# lldpOpenPortFromHandle

- ea: `0x140005084`
- end: `0x140005099`
- name: `lldpOpenPortFromHandle`
- size: `21`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ed90`
- `0x14000edc0`
- `0x14000f0b0`
- `0x14000f120`
- `0x14000f1c0`
- `0x14000f230`
- `0x14000f330`
- `0x14000f360`

## callees

- `0x140005084`

## pseudocode

```c
_DWORD *__fastcall lldpOpenPortFromHandle(_DWORD *a1)
{
  _DWORD *result; // rax

  result = 0;
  if ( a1 )
  {
    if ( *a1 != 1866746956 )
      return 0;
    return a1;
  }
  return result;
}

```

## disassembly

```asm
0x140005084  xor     eax, eax
0x140005086  test    rcx, rcx
0x140005089  jz      short locret_140005098
0x14000508b  cmp     dword ptr [rcx], 6F444C4Ch
0x140005091  cmovnz  rcx, rax
0x140005095  mov     rax, rcx
0x140005098  retn
```
