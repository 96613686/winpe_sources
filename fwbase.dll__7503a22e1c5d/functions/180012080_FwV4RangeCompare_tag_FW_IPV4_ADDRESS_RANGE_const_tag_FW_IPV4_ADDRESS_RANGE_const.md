# FwV4RangeCompare(_tag_FW_IPV4_ADDRESS_RANGE const *,_tag_FW_IPV4_ADDRESS_RANGE const *)

- ea: `0x180012080`
- end: `0x1800120a3`
- name: `?FwV4RangeCompare@@YAHPEBU_tag_FW_IPV4_ADDRESS_RANGE@@0@Z`
- size: `35`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012080`

## pseudocode

```c
__int64 __fastcall FwV4RangeCompare(_DWORD *a1, _DWORD *a2)
{
  unsigned int v2; // ecx

  if ( *a1 < *a2 )
    return 0xFFFFFFFFLL;
  if ( *a1 > *a2 )
    return 1;
  v2 = a1[1];
  if ( v2 < a2[1] )
    return 0xFFFFFFFFLL;
  return v2 > a2[1];
}

```

## disassembly

```asm
0x180012080  mov     eax, [rcx]
0x180012082  cmp     eax, [rdx]
0x180012084  jb      short loc_180012090
0x180012086  ja      short loc_18001209D
0x180012088  mov     ecx, [rcx+4]
0x18001208b  cmp     ecx, [rdx+4]
0x18001208e  jnb     short loc_180012094
0x180012090  or      eax, 0FFFFFFFFh
0x180012093  retn
0x180012094  xor     eax, eax
0x180012096  cmp     ecx, [rdx+4]
0x180012099  setnbe  al
0x18001209c  retn
0x18001209d  mov     eax, 1
0x1800120a2  retn
```
