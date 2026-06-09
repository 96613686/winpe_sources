# DescendingStringLengthCompare

- ea: `0x18000db70`
- end: `0x18000db85`
- name: `DescendingStringLengthCompare`
- size: `21`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000db70`

## pseudocode

```c
__int64 __fastcall DescendingStringLengthCompare(_WORD *a1, _WORD *a2)
{
  unsigned __int16 v2; // ax

  v2 = a1[1];
  if ( v2 == a2[1] )
    return 0;
  else
    return v2 < a2[1] ? 1 : -1;
}

```

## disassembly

```asm
0x18000db70  movzx   eax, word ptr [rcx+2]
0x18000db74  cmp     ax, [rdx+2]
0x18000db78  jnz     short loc_18000DB7D
0x18000db7a  xor     eax, eax
0x18000db7c  retn
0x18000db7d  sbb     eax, eax
0x18000db7f  and     eax, 2
0x18000db82  dec     eax
0x18000db84  retn
```
