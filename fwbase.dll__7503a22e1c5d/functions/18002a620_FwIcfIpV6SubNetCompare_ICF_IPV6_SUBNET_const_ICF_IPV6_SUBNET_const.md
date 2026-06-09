# FwIcfIpV6SubNetCompare(ICF_IPV6_SUBNET const *,ICF_IPV6_SUBNET const *)

- ea: `0x18002a620`
- end: `0x18002a63b`
- name: `?FwIcfIpV6SubNetCompare@@YAHPEBUICF_IPV6_SUBNET@@0@Z`
- size: `27`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002a620`

## pseudocode

```c
__int64 __fastcall FwIcfIpV6SubNetCompare(_DWORD *a1, _DWORD *a2)
{
  unsigned int v2; // r8d

  v2 = a1[4];
  if ( v2 >= a2[4] )
    return v2 > a2[4];
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18002a620  mov     r8d, [rcx+10h]
0x18002a624  cmp     r8d, [rdx+10h]
0x18002a628  jnb     short loc_18002A62E
0x18002a62a  or      eax, 0FFFFFFFFh
0x18002a62d  retn
0x18002a62e  xor     eax, eax
0x18002a630  cmp     r8d, [rdx+10h]
0x18002a634  lea     ecx, [rax+1]
0x18002a637  cmova   eax, ecx
0x18002a63a  retn
```
