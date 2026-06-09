# DfscGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities

- ea: `0x140011a18`
- end: `0x140011a2b`
- name: `DfscGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities`
- size: `19`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400239b0`
- `0x140026660`

## callees

- `0x140011a18`

## pseudocode

```c
__int64 __fastcall DfscGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities(char a1)
{
  if ( (a1 & 4) != 0 )
    return 3;
  else
    return a1 & 2;
}

```

## disassembly

```asm
0x140011a18  test    cl, 4
0x140011a1b  jz      short loc_140011A24
0x140011a1d  mov     eax, 3
0x140011a22  retn
0x140011a24  movzx   eax, cl
0x140011a27  and     eax, 2
0x140011a2a  retn
```
