# ValidateClientKeyHandle

- ea: `0x18000a650`
- end: `0x18000a665`
- name: `ValidateClientKeyHandle`
- size: `21`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180008820`
- `0x18000a3d0`
- `0x180010a90`
- `0x180010c90`
- `0x180011f00`
- `0x180012e00`
- `0x1800140b0`
- `0x1800147a0`
- `0x180016330`
- `0x180016620`
- `0x180017990`
- `0x18001bbe8`
- `0x18001bed0`
- `0x18001c0b0`
- `0x18001c3a0`

## callees

- `0x18000a650`

## pseudocode

```c
_DWORD *__fastcall ValidateClientKeyHandle(_DWORD *a1)
{
  _DWORD *result; // rax

  result = 0;
  if ( a1 )
  {
    if ( *a1 != 1145307138 )
      return 0;
    return a1;
  }
  return result;
}

```

## disassembly

```asm
0x18000a650  xor     eax, eax
0x18000a652  test    rcx, rcx
0x18000a655  jz      short locret_18000A664
0x18000a657  cmp     dword ptr [rcx], 44440002h
0x18000a65d  cmovnz  rcx, rax
0x18000a661  mov     rax, rcx
0x18000a664  retn
```
