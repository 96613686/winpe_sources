# SdbpCheckMatchingWildcardRegistry

- ea: `0x1408240e0`
- end: `0x140824205`
- name: `SdbpCheckMatchingWildcardRegistry`
- size: `293`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x14073810c`
- `0x1408240e0`
- `0x14082420c`
- `0x1408c2f88`

## string_xrefs

- `0x140824169`: `Failed to read MATCHING_WILDCARD_REGISTRY entry`
- `0x1408241cd`: `Failed to check MATCHING_WILDCARD_REGISTRY entry`
- `0x140824176`: `SdbpCheckMatchingWildcardRegistry`

## pseudocode

```c
__int64 __fastcall SdbpCheckMatchingWildcardRegistry(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  int v10; // [rsp+58h] [rbp-1h] BYREF
  int v11; // [rsp+5Ch] [rbp+3h] BYREF
  __int64 v12; // [rsp+60h] [rbp+7h] BYREF
  __int64 v13; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v14; // [rsp+70h] [rbp+17h] BYREF
  __int64 v15; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v16; // [rsp+80h] [rbp+27h] BYREF
  __int16 *v17; // [rsp+88h] [rbp+2Fh] BYREF
  int v18; // [rsp+A8h] [rbp+4Fh] BYREF

  v6 = a5;
  v7 = 0;
  *a1 = 0;
  v11 = 0;
  v17 = 0;
  v16 = 0;
  v10 = 0;
  v15 = 0;
  v18 = 0;
  v14 = 0;
  v13 = 0;
  v12 = 0;
  if ( (unsigned int)SdbpGetRegistryMatchingAttributes(a3, v6, &v17, &v16, &v10, &v15, &v18, &v14, &v13, &v12) )
  {
    if ( (unsigned int)SdbpCheckMatchingWildcardRegistryEntry(
                         (_DWORD)v17,
                         v16,
                         v10,
                         v15,
                         v18,
                         v14,
                         v13,
                         v12,
                         (__int64)&v11) )
    {
      v7 = 1;
      *(_DWORD *)(a6 + 80) = 1;
      *a1 = v11;
    }
    else
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpCheckMatchingWildcardRegistry",
        1699,
        (unsigned int)"Failed to check MATCHING_WILDCARD_REGISTRY entry");
    }
  }
  else
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpCheckMatchingWildcardRegistry",
      1682,
      (unsigned int)"Failed to read MATCHING_WILDCARD_REGISTRY entry");
  }
  return v7;
}

```

## disassembly

```asm
0x1408240e0  mov     r11, rsp
0x1408240e3  mov     [r11+10h], rbx
0x1408240e7  mov     [r11+18h], rdi
0x1408240eb  push    rbp
0x1408240ec  lea     rbp, [r11-47h]
0x1408240f0  sub     rsp, 90h
0x1408240f7  mov     edx, [rbp+3Fh+arg_20]
0x1408240fa  lea     r9, [rbp+3Fh+var_18]
0x1408240fe  xor     ebx, ebx
0x140824100  mov     rdi, rcx
0x140824103  mov     [rcx], ebx
0x140824105  mov     rax, r8
0x140824108  lea     rcx, [rbp+3Fh+var_38]
0x14082410c  mov     [rbp+3Fh+var_3C], ebx
0x14082410f  mov     [r11-50h], rcx
0x140824113  lea     r8, [rbp+3Fh+var_10]
0x140824117  lea     rcx, [rbp+3Fh+var_30]
0x14082411b  mov     [rbp+3Fh+var_10], rbx
0x14082411f  mov     [r11-58h], rcx
0x140824123  lea     rcx, [rbp+3Fh+var_28]
0x140824127  mov     [r11-60h], rcx
0x14082412b  lea     rcx, [rbp+3Fh+arg_0]
0x14082412f  mov     [r11-68h], rcx
0x140824133  lea     rcx, [rbp+3Fh+var_20]
0x140824137  mov     [r11-70h], rcx
0x14082413b  lea     rcx, [rbp+3Fh+var_40]
0x14082413f  mov     [r11-78h], rcx
0x140824143  mov     rcx, rax
0x140824146  mov     [rbp+3Fh+var_18], rbx
0x14082414a  mov     [rbp+3Fh+var_40], ebx
0x14082414d  mov     [rbp+3Fh+var_20], rbx
0x140824151  mov     [rbp+3Fh+arg_0], ebx
0x140824154  mov     [rbp+3Fh+var_28], rbx
0x140824158  mov     [rbp+3Fh+var_30], rbx
0x14082415c  mov     [rbp+3Fh+var_38], rbx
0x140824160  call    SdbpGetRegistryMatchingAttributes
0x140824165  test    eax, eax
0x140824167  jnz     short loc_140824189
0x140824169  lea     r9, aFailedToReadMa; "Failed to read MATCHING_WILDCARD_REGIST"...
0x140824170  mov     r8d, 692h
0x140824176  lea     rdx, aSdbpcheckmatch_0; "SdbpCheckMatchingWildcardRegistry"
0x14082417d  mov     ecx, 1
0x140824182  call    AslLogCallPrintf
0x140824187  jmp     short loc_1408241ED
0x140824189  mov     r9, [rbp+3Fh+var_20]
0x14082418d  lea     rax, [rbp+3Fh+var_3C]
0x140824191  mov     r8d, [rbp+3Fh+var_40]
0x140824195  mov     rdx, [rbp+3Fh+var_18]
0x140824199  mov     rcx, [rbp+3Fh+var_10]
0x14082419d  mov     [rsp+90h+var_50], rax
0x1408241a2  mov     rax, [rbp+3Fh+var_38]
0x1408241a6  mov     [rsp+90h+var_58], rax
0x1408241ab  mov     rax, [rbp+3Fh+var_30]
0x1408241af  mov     [rsp+90h+var_60], rax
0x1408241b4  mov     rax, [rbp+3Fh+var_28]
0x1408241b8  mov     [rsp+90h+var_68], rax
0x1408241bd  mov     eax, [rbp+3Fh+arg_0]
0x1408241c0  mov     dword ptr [rsp+90h+var_70], eax
0x1408241c4  call    SdbpCheckMatchingWildcardRegistryEntry
0x1408241c9  test    eax, eax
0x1408241cb  jnz     short loc_1408241DC
0x1408241cd  lea     r9, aFailedToCheckM; "Failed to check MATCHING_WILDCARD_REGIS"...
0x1408241d4  mov     r8d, 6A3h
0x1408241da  jmp     short loc_140824176
0x1408241dc  mov     rcx, [rbp+3Fh+arg_28]
0x1408241e0  mov     ebx, 1
0x1408241e5  mov     [rcx+50h], ebx
0x1408241e8  mov     ecx, [rbp+3Fh+var_3C]
0x1408241eb  mov     [rdi], ecx
0x1408241ed  lea     r11, [rsp+90h+var_s0]
0x1408241f5  mov     eax, ebx
0x1408241f7  mov     rbx, [r11+18h]
0x1408241fb  mov     rdi, [r11+20h]
0x1408241ff  mov     rsp, r11
0x140824202  pop     rbp
0x140824203  retn
```
