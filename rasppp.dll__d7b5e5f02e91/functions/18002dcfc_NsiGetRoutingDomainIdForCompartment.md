# NsiGetRoutingDomainIdForCompartment

- ea: `0x18002dcfc`
- end: `0x18002dd16`
- name: `NsiGetRoutingDomainIdForCompartment`
- size: `26`
- prototype: `__int64 __fastcall(__int64, GUID *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002e3cc`
- `0x180032358`
- `0x180032738`
- `0x180032b1c`
- `0x180033304`

## callees

- `0x18002dcfc`

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
0x18002dcfc  test    rdx, rdx
0x18002dcff  jz      short loc_18002DD10
0x18002dd01  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002dd08  movdqu  xmmword ptr [rdx], xmm0
0x18002dd0c  xor     eax, eax
0x18002dd0e  retn
0x18002dd10  mov     eax, 57h ; 'W'
0x18002dd15  retn
```
