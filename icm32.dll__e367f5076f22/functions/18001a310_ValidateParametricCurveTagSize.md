# ValidateParametricCurveTagSize

- ea: `0x18001a310`
- end: `0x18001a352`
- name: `ValidateParametricCurveTagSize`
- size: `66`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800042fc`
- `0x18000464c`
- `0x18001bb30`

## callees

- `0x18001a310`

## pseudocode

```c
__int64 __fastcall ValidateParametricCurveTagSize(__int64 a1, unsigned int a2)
{
  __int64 v3; // rax
  unsigned __int64 v4; // rcx
  unsigned int v5; // edx

  if ( *(_WORD *)(a1 + 8) <= 4u )
  {
    v3 = 32LL * *(unsigned __int16 *)(a1 + 8);
    v4 = a2;
    v5 = 0;
    if ( v4 < 4 * (unsigned __int64)*(unsigned int *)((char *)&unk_18003F008 + v3) + 12 )
      return 2011;
    return v5;
  }
  else
  {
    return 2011;
  }
}

```

## disassembly

```asm
0x18001a310  cmp     word ptr [rcx+8], 4
0x18001a315  jbe     short loc_18001A31F
0x18001a317  mov     r8d, 7DBh
0x18001a31d  jmp     short loc_18001A34E
0x18001a31f  movzx   eax, word ptr [rcx+8]
0x18001a323  lea     r8, unk_18003F008
0x18001a32a  shl     rax, 5
0x18001a32e  mov     ecx, edx
0x18001a330  xor     edx, edx
0x18001a332  mov     eax, [rax+r8]
0x18001a336  mov     r8d, 7DBh
0x18001a33c  lea     rax, ds:0Ch[rax*4]
0x18001a344  cmp     rcx, rax
0x18001a347  cmovb   edx, r8d
0x18001a34b  mov     r8d, edx
0x18001a34e  mov     eax, r8d
0x18001a351  retn
```
