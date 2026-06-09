# CompressQuery

- ea: `0x18000689c`
- end: `0x18000692c`
- name: `CompressQuery`
- size: `144`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005e00`
- `0x1800064e8`
- `0x1800067c0`

## callees

- `0x18000689c`

## pseudocode

```c
__int64 __fastcall CompressQuery(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // r9d
  int v4; // ecx

  if ( !a2 )
    return 4294967294LL;
  if ( ((*(_WORD *)(a2 + 14) - 8) & 0xFFE7) != 0 )
    return 4294967294LL;
  if ( *(_WORD *)(a2 + 12) != 1 )
    return 4294967294LL;
  v3 = *(_DWORD *)(a2 + 4);
  if ( v3 < 4 )
    return 4294967294LL;
  v4 = *(_DWORD *)(a2 + 8);
  if ( v4 < 4 || *(_DWORD *)(a2 + 16) )
    return 4294967294LL;
  if ( a3
    && (*(_DWORD *)(a3 + 16) != 1129730893 && *(_DWORD *)(a3 + 16) != 1296126531
     || ((*(_WORD *)(a3 + 14) - 8) & 0xFFF7) != 0
     || *(_WORD *)(a3 + 12) != 1
     || ((*(_DWORD *)(a3 + 4) ^ v3) & 0xFFFFFFFC) != 0
     || ((*(_DWORD *)(a3 + 8) ^ v4) & 0xFFFFFFFC) != 0) )
  {
    return 4294967294LL;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18000689c  test    rdx, rdx
0x18000689f  jz      loc_180006926
0x1800068a5  movzx   eax, word ptr [rdx+0Eh]
0x1800068a9  mov     ecx, 0FFE7h
0x1800068ae  sub     ax, 8
0x1800068b2  test    cx, ax
0x1800068b5  jnz     short loc_180006926
0x1800068b7  cmp     word ptr [rdx+0Ch], 1
0x1800068bc  jnz     short loc_180006926
0x1800068be  mov     r9d, [rdx+4]
0x1800068c2  cmp     r9d, 4
0x1800068c6  jl      short loc_180006926
0x1800068c8  mov     ecx, [rdx+8]
0x1800068cb  cmp     ecx, 4
0x1800068ce  jl      short loc_180006926
0x1800068d0  cmp     dword ptr [rdx+10h], 0
0x1800068d4  jnz     short loc_180006926
0x1800068d6  test    r8, r8
0x1800068d9  jnz     short loc_1800068DE
0x1800068db  xor     eax, eax
0x1800068dd  retn
0x1800068de  cmp     dword ptr [r8+10h], 4356534Dh
0x1800068e6  jz      short loc_1800068F2
0x1800068e8  cmp     dword ptr [r8+10h], 4D415243h
0x1800068f0  jnz     short loc_180006926
0x1800068f2  movzx   eax, word ptr [r8+0Eh]
0x1800068f7  mov     edx, 0FFF7h
0x1800068fc  sub     ax, 8
0x180006900  test    dx, ax
0x180006903  jnz     short loc_180006926
0x180006905  cmp     word ptr [r8+0Ch], 1
0x18000690b  jnz     short loc_180006926
0x18000690d  xor     r9d, [r8+4]
0x180006911  test    r9d, 0FFFFFFFCh
0x180006918  jnz     short loc_180006926
0x18000691a  xor     ecx, [r8+8]
0x18000691e  test    ecx, 0FFFFFFFCh
0x180006924  jz      short loc_1800068DB
0x180006926  mov     eax, 0FFFFFFFEh
0x18000692b  retn
```
