# MdaMapShareAccess

- ea: `0x140033c50`
- end: `0x140033c87`
- name: `MdaMapShareAccess`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140030b60`
- `0x1400316d0`

## callees

- `0x140033c50`

## pseudocode

```c
__int64 __fastcall MdaMapShareAccess(char a1)
{
  __int64 result; // rax
  int v3; // ecx

  if ( (a1 & 3) == 3 )
    return 0;
  v3 = a1 & 1;
  if ( (a1 & 4) != 0 )
    return v3 ^ 1u;
  result = 2;
  if ( !v3 )
  {
    result = 3;
    if ( (a1 & 2) != 0 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x140033c50  mov     eax, ecx
0x140033c52  mov     edx, ecx
0x140033c54  and     eax, 3
0x140033c57  cmp     al, 3
0x140033c59  jnz     short loc_140033C5F
0x140033c5b  xor     eax, eax
0x140033c5d  retn
0x140033c5f  mov     r8d, 1
0x140033c65  and     ecx, r8d
0x140033c68  test    dl, 4
0x140033c6b  jz      short loc_140033C74
0x140033c6d  mov     eax, ecx
0x140033c6f  xor     eax, r8d
0x140033c72  retn
0x140033c74  mov     eax, 2
0x140033c79  test    ecx, ecx
0x140033c7b  jnz     short locret_140033C86
0x140033c7d  test    al, dl
0x140033c7f  lea     eax, [rcx+3]
0x140033c82  cmovnz  eax, r8d
0x140033c86  retn
```
