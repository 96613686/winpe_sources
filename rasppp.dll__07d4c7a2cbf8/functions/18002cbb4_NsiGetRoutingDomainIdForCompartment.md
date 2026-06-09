# NsiGetRoutingDomainIdForCompartment

- ea: `0x18002cbb4`
- end: `0x18002cbcd`
- name: `NsiGetRoutingDomainIdForCompartment`
- size: `25`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002d194`
- `0x180030de8`
- `0x180031190`
- `0x18003153c`
- `0x180031d0c`

## callees

- `0x18002cbb4`

## pseudocode

```c
__int64 __fastcall NsiGetRoutingDomainIdForCompartment(__int64 a1, GUID *a2)
{
  if ( !a2 )
    return 87;
  *a2 = GUID_NULL;
  return 0;
}

```

## disassembly

```asm
0x18002cbb4  test    rdx, rdx
0x18002cbb7  jz      short loc_18002CBC7
0x18002cbb9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002cbc0  movdqu  xmmword ptr [rdx], xmm0
0x18002cbc4  xor     eax, eax
0x18002cbc6  retn
0x18002cbc7  mov     eax, 57h ; 'W'
0x18002cbcc  retn
```
