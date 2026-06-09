# AscendingGlyphIndexCompare

- ea: `0x180014d90`
- end: `0x180014db9`
- name: `AscendingGlyphIndexCompare`
- size: `41`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014d90`

## pseudocode

```c
__int64 __fastcall AscendingGlyphIndexCompare(_WORD *a1, _WORD *a2)
{
  unsigned __int16 v2; // ax
  unsigned int v3; // eax

  v2 = a1[8];
  if ( v2 != a2[8] )
    return v2 < a2[8] ? -1 : 1;
  v3 = *((_DWORD *)a1 + 3);
  if ( v3 == *((_DWORD *)a2 + 3) )
    return 0;
  if ( v3 < *((_DWORD *)a2 + 3) )
    return 1;
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180014d90  movzx   eax, word ptr [rcx+10h]
0x180014d94  cmp     ax, [rdx+10h]
0x180014d98  jnz     short loc_180014DB1
0x180014d9a  mov     eax, [rcx+0Ch]
0x180014d9d  cmp     eax, [rdx+0Ch]
0x180014da0  jnz     short loc_180014DA5
0x180014da2  xor     eax, eax
0x180014da4  retn
0x180014da5  jb      short loc_180014DAB
0x180014da7  or      eax, 0FFFFFFFFh
0x180014daa  retn
0x180014dab  mov     eax, 1
0x180014db0  retn
0x180014db1  sbb     eax, eax
0x180014db3  and     eax, 0FFFFFFFEh
0x180014db6  inc     eax
0x180014db8  retn
```
