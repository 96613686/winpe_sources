# MupiGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities

- ea: `0x14001d548`
- end: `0x14001d55b`
- name: `MupiGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities`
- size: `19`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001bbb0`
- `0x14001cd50`

## callees

- `0x14001d548`

## pseudocode

```c
__int64 __fastcall MupiGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities(char a1)
{
  if ( (a1 & 4) != 0 )
    return 3;
  else
    return a1 & 2;
}

```

## disassembly

```asm
0x14001d548  test    cl, 4
0x14001d54b  jnz     short loc_14001D555
0x14001d54d  movzx   eax, cl
0x14001d550  and     eax, 2
0x14001d553  retn
0x14001d555  mov     eax, 3
0x14001d55a  retn
```
