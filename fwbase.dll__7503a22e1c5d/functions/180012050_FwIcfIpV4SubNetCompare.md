# FwIcfIpV4SubNetCompare

- ea: `0x180012050`
- end: `0x180012073`
- name: `FwIcfIpV4SubNetCompare`
- size: `35`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012050`

## pseudocode

```c
__int64 __fastcall FwIcfIpV4SubNetCompare(_DWORD *a1, _DWORD *a2)
{
  unsigned int v3; // ecx

  if ( *a1 < *a2 )
    return 0xFFFFFFFFLL;
  if ( *a1 > *a2 )
    return 1;
  v3 = a1[1];
  if ( v3 < a2[1] )
    return 0xFFFFFFFFLL;
  else
    return v3 > a2[1];
}

```

## disassembly

```asm
0x180012050  mov     eax, [rcx]
0x180012052  cmp     eax, [rdx]
0x180012054  jb      short loc_18001205E
0x180012056  jbe     short loc_180012062
0x180012058  mov     eax, 1
0x18001205d  retn
0x18001205e  or      eax, 0FFFFFFFFh
0x180012061  retn
0x180012062  mov     ecx, [rcx+4]
0x180012065  cmp     ecx, [rdx+4]
0x180012068  jb      short loc_18001205E
0x18001206a  xor     eax, eax
0x18001206c  cmp     ecx, [rdx+4]
0x18001206f  setnbe  al
0x180012072  retn
```
