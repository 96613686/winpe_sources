# SslpValidateKemKeyHandle

- ea: `0x180023a78`
- end: `0x180023a93`
- name: `SslpValidateKemKeyHandle`
- size: `27`
- prototype: `_DWORD *__fastcall(_DWORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180021da8`
- `0x180021efc`
- `0x180022ca4`
- `0x1800237a0`
- `0x18002396c`

## callees

- `0x180023a78`

## pseudocode

```c
_DWORD *__fastcall SslpValidateKemKeyHandle(_DWORD *a1)
{
  _DWORD *result; // rax

  if ( !a1 || *a1 < 0x38u )
    return 0;
  result = 0;
  if ( a1[1] == 1936944188 )
    return a1;
  return result;
}

```

## disassembly

```asm
0x180023a78  test    rcx, rcx
0x180023a7b  jz      short loc_180023A90
0x180023a7d  cmp     dword ptr [rcx], 38h ; '8'
0x180023a80  jb      short loc_180023A90
0x180023a82  xor     eax, eax
0x180023a84  cmp     dword ptr [rcx+4], 73736C3Ch
0x180023a8b  cmovz   rax, rcx
0x180023a8f  retn
0x180023a90  xor     eax, eax
0x180023a92  retn
```
