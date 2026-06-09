# AscendingNameRecordCompare

- ea: `0x18000d3c0`
- end: `0x18000d3fd`
- name: `AscendingNameRecordCompare`
- size: `61`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d3c0`

## pseudocode

```c
__int64 __fastcall AscendingNameRecordCompare(_WORD *a1, _WORD *a2)
{
  unsigned __int16 v2; // ax
  bool v3; // cf
  unsigned __int16 v4; // ax
  unsigned __int16 v5; // ax

  if ( *a1 != *a2 )
    return *a1 < *a2 ? -1 : 1;
  v2 = a1[1];
  v3 = v2 < a2[1];
  if ( v2 == a2[1] )
  {
    v4 = a1[2];
    v3 = v4 < a2[2];
    if ( v4 == a2[2] )
    {
      v5 = a1[3];
      v3 = v5 < a2[3];
      if ( v5 == a2[3] )
        return 0;
    }
  }
  if ( v3 )
    return 0xFFFFFFFFLL;
  return 1;
}

```

## disassembly

```asm
0x18000d3c0  movzx   eax, word ptr [rcx]
0x18000d3c3  cmp     ax, [rdx]
0x18000d3c6  jnz     short loc_18000D3F5
0x18000d3c8  movzx   eax, word ptr [rcx+2]
0x18000d3cc  cmp     ax, [rdx+2]
0x18000d3d0  jnz     short loc_18000D3E9
0x18000d3d2  movzx   eax, word ptr [rcx+4]
0x18000d3d6  cmp     ax, [rdx+4]
0x18000d3da  jnz     short loc_18000D3E9
0x18000d3dc  movzx   eax, word ptr [rcx+6]
0x18000d3e0  cmp     ax, [rdx+6]
0x18000d3e4  jnz     short loc_18000D3E9
0x18000d3e6  xor     eax, eax
0x18000d3e8  retn
0x18000d3e9  jb      short loc_18000D3F1
0x18000d3eb  mov     eax, 1
0x18000d3f0  retn
0x18000d3f1  or      eax, 0FFFFFFFFh
0x18000d3f4  retn
0x18000d3f5  sbb     eax, eax
0x18000d3f7  and     eax, 0FFFFFFFEh
0x18000d3fa  inc     eax
0x18000d3fc  retn
```
