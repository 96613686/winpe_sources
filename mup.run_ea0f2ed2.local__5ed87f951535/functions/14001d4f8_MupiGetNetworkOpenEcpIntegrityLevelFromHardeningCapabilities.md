# MupiGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities

- ea: `0x14001d4f8`
- end: `0x14001d50b`
- name: `MupiGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001bb60`
- `0x14001cd00`

## callees

- `0x14001d4f8`

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
0x14001d4f8  test    cl, 4
0x14001d4fb  jnz     short loc_14001D505
0x14001d4fd  movzx   eax, cl
0x14001d500  and     eax, 2
0x14001d503  retn
0x14001d505  mov     eax, 3
0x14001d50a  retn
```
