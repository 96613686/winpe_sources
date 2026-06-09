# AscendingOffsetCompare

- ea: `0x18000d410`
- end: `0x18000d423`
- name: `AscendingOffsetCompare`
- size: `19`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d410`

## pseudocode

```c
__int64 __fastcall AscendingOffsetCompare(_DWORD *a1, _DWORD *a2)
{
  unsigned int v2; // eax

  v2 = a1[2];
  if ( v2 == a2[2] )
    return 0;
  else
    return v2 < a2[2] ? -1 : 1;
}

```

## disassembly

```asm
0x18000d410  mov     eax, [rcx+8]
0x18000d413  cmp     eax, [rdx+8]
0x18000d416  jnz     short loc_18000D41B
0x18000d418  xor     eax, eax
0x18000d41a  retn
0x18000d41b  sbb     eax, eax
0x18000d41d  and     eax, 0FFFFFFFEh
0x18000d420  inc     eax
0x18000d422  retn
```
