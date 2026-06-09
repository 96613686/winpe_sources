# SdbpCheckMatchingWildcardRegistry

- ea: `0x140822170`
- end: `0x140822295`
- name: `SdbpCheckMatchingWildcardRegistry`
- size: `293`
- prototype: `__int64 __fastcall(_DWORD *, __int64, int, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x14073394c`
- `0x140822170`
- `0x14082229c`
- `0x14097d158`

## string_xrefs

- `0x14082225d`: `Failed to check MATCHING_WILDCARD_REGISTRY entry`
- `0x140822206`: `SdbpCheckMatchingWildcardRegistry`
- `0x1408221f9`: `Failed to read MATCHING_WILDCARD_REGISTRY entry`

## pseudocode

```c
__int64 __fastcall SdbpCheckMatchingWildcardRegistry(_DWORD *a1, __int64 a2, int a3, __int64 a4, int a5, __int64 a6)
{
  int v6; // edx
  unsigned int v7; // ebx
  const char *v9; // r9
  int v10; // r8d
  unsigned int v12; // [rsp+58h] [rbp-1h] BYREF
  int v13; // [rsp+5Ch] [rbp+3h] BYREF
  __int64 v14; // [rsp+60h] [rbp+7h] BYREF
  __int64 v15; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v16; // [rsp+70h] [rbp+17h] BYREF
  __int64 v17; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v18; // [rsp+80h] [rbp+27h] BYREF
  __int64 v19; // [rsp+88h] [rbp+2Fh] BYREF
  int v20; // [rsp+A8h] [rbp+4Fh] BYREF

  v6 = a5;
  v7 = 0;
  *a1 = 0;
  v13 = 0;
  v19 = 0;
  v18 = 0;
  v12 = 0;
  v17 = 0;
  v20 = 0;
  v16 = 0;
  v15 = 0;
  v14 = 0;
  if ( (unsigned int)SdbpGetRegistryMatchingAttributes(
                       a3,
                       v6,
                       (unsigned int)&v19,
                       (unsigned int)&v18,
                       (__int64)&v12,
                       (__int64)&v17,
                       (__int64)&v20,
                       (__int64)&v16,
                       (__int64)&v15,
                       (__int64)&v14) )
  {
    if ( (unsigned int)SdbpCheckMatchingWildcardRegistryEntry(v19, v18, v12, v17, v20, v16, v15, v14, &v13) )
    {
      v7 = 1;
      *(_DWORD *)(a6 + 80) = 1;
      *a1 = v13;
      return v7;
    }
    v9 = "Failed to check MATCHING_WILDCARD_REGISTRY entry";
    v10 = 1699;
  }
  else
  {
    v9 = "Failed to read MATCHING_WILDCARD_REGISTRY entry";
    v10 = 1682;
  }
  AslLogCallPrintf(1, (unsigned int)"SdbpCheckMatchingWildcardRegistry", v10, (_DWORD)v9);
  return v7;
}

```

## disassembly

```asm
0x140822170  mov     r11, rsp
0x140822173  mov     [r11+10h], rbx
0x140822177  mov     [r11+18h], rdi
0x14082217b  push    rbp
0x14082217c  lea     rbp, [r11-47h]
0x140822180  sub     rsp, 90h
0x140822187  mov     edx, [rbp+3Fh+arg_20]
0x14082218a  lea     r9, [rbp+3Fh+var_18]
0x14082218e  xor     ebx, ebx
0x140822190  mov     rdi, rcx
0x140822193  mov     [rcx], ebx
0x140822195  mov     rax, r8
0x140822198  lea     rcx, [rbp+3Fh+var_38]
0x14082219c  mov     [rbp+3Fh+var_3C], ebx
0x14082219f  mov     [r11-50h], rcx
0x1408221a3  lea     r8, [rbp+3Fh+var_10]
0x1408221a7  lea     rcx, [rbp+3Fh+var_30]
0x1408221ab  mov     [rbp+3Fh+var_10], rbx
0x1408221af  mov     [r11-58h], rcx
0x1408221b3  lea     rcx, [rbp+3Fh+var_28]
0x1408221b7  mov     [r11-60h], rcx
0x1408221bb  lea     rcx, [rbp+3Fh+arg_0]
0x1408221bf  mov     [r11-68h], rcx
0x1408221c3  lea     rcx, [rbp+3Fh+var_20]
0x1408221c7  mov     [r11-70h], rcx
0x1408221cb  lea     rcx, [rbp+3Fh+var_40]
0x1408221cf  mov     [r11-78h], rcx
0x1408221d3  mov     rcx, rax
0x1408221d6  mov     [rbp+3Fh+var_18], rbx
0x1408221da  mov     [rbp+3Fh+var_40], ebx
0x1408221dd  mov     [rbp+3Fh+var_20], rbx
0x1408221e1  mov     [rbp+3Fh+arg_0], ebx
0x1408221e4  mov     [rbp+3Fh+var_28], rbx
0x1408221e8  mov     [rbp+3Fh+var_30], rbx
0x1408221ec  mov     [rbp+3Fh+var_38], rbx
0x1408221f0  call    SdbpGetRegistryMatchingAttributes
0x1408221f5  test    eax, eax
0x1408221f7  jnz     short loc_140822219
0x1408221f9  lea     r9, aFailedToReadMa; "Failed to read MATCHING_WILDCARD_REGIST"...
0x140822200  mov     r8d, 692h
0x140822206  lea     rdx, aSdbpcheckmatch_0; "SdbpCheckMatchingWildcardRegistry"
0x14082220d  mov     ecx, 1
0x140822212  call    AslLogCallPrintf
0x140822217  jmp     short loc_14082227D
0x140822219  mov     r9, [rbp+3Fh+var_20]
0x14082221d  lea     rax, [rbp+3Fh+var_3C]
0x140822221  mov     r8d, [rbp+3Fh+var_40]
0x140822225  mov     rdx, [rbp+3Fh+var_18]
0x140822229  mov     rcx, [rbp+3Fh+var_10]
0x14082222d  mov     [rsp+90h+var_50], rax
0x140822232  mov     rax, [rbp+3Fh+var_38]
0x140822236  mov     [rsp+90h+var_58], rax
0x14082223b  mov     rax, [rbp+3Fh+var_30]
0x14082223f  mov     [rsp+90h+var_60], rax
0x140822244  mov     rax, [rbp+3Fh+var_28]
0x140822248  mov     [rsp+90h+var_68], rax
0x14082224d  mov     eax, [rbp+3Fh+arg_0]
0x140822250  mov     dword ptr [rsp+90h+var_70], eax
0x140822254  call    SdbpCheckMatchingWildcardRegistryEntry
0x140822259  test    eax, eax
0x14082225b  jnz     short loc_14082226C
0x14082225d  lea     r9, aFailedToCheckM; "Failed to check MATCHING_WILDCARD_REGIS"...
0x140822264  mov     r8d, 6A3h
0x14082226a  jmp     short loc_140822206
0x14082226c  mov     rcx, [rbp+3Fh+arg_28]
0x140822270  mov     ebx, 1
0x140822275  mov     [rcx+50h], ebx
0x140822278  mov     ecx, [rbp+3Fh+var_3C]
0x14082227b  mov     [rdi], ecx
0x14082227d  lea     r11, [rsp+90h+var_s0]
0x140822285  mov     eax, ebx
0x140822287  mov     rbx, [r11+18h]
0x14082228b  mov     rdi, [r11+20h]
0x14082228f  mov     rsp, r11
0x140822292  pop     rbp
0x140822293  retn
```
