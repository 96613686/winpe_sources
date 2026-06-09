# DecompressedDibType(x)

- ea: `0x1000f82f`
- end: `0x1000f903`
- name: `_DecompressedDibType@4`
- size: `212`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1000fa28`
- `0x1000fbcc`
- `0x1000fe21`
- `0x1000ff0e`
- `0x100100bf`
- `0x100101f2`

## callees

- `0x1000f82f`

## pseudocode

```c
int __thiscall DecompressedDibType(int this)
{
  int v1; // eax
  int result; // eax
  bool v3; // zf
  int v4; // eax
  int v5; // ecx
  int v7; // [esp-4h] [ebp-8h]

  if ( *(_WORD *)(this + 12) != 1 )
    return -1;
  if ( !*(_DWORD *)(this + 16) )
  {
    v4 = *(unsigned __int16 *)(this + 14);
    v5 = v4;
    if ( v4 == 8 )
      return 0;
    if ( v4 != 16 )
    {
      if ( v4 == 24 )
        return 3;
      result = -1;
      v3 = v5 == 32;
      v7 = 4;
      goto LABEL_26;
    }
    return 1;
  }
  if ( *(_DWORD *)(this + 16) != 3 )
    return -1;
  v1 = *(unsigned __int16 *)(this + 14);
  if ( v1 == 8 )
    return -1;
  if ( v1 != 16 )
  {
    if ( v1 != 24 )
    {
      if ( *(_WORD *)(this + 14) == 32
        && *(_DWORD *)(this + 48) == 255
        && *(_DWORD *)(this + 44) == 65280
        && *(_DWORD *)(this + 40) == 16711680 )
      {
        return 4;
      }
      return -1;
    }
    if ( *(_DWORD *)(this + 48) != 255 || *(_DWORD *)(this + 44) != 65280 || *(_DWORD *)(this + 40) != 16711680 )
      return -1;
    return 3;
  }
  if ( *(_DWORD *)(this + 48) != 31 )
    return -1;
  if ( *(_DWORD *)(this + 44) != 2016 )
  {
    if ( *(_DWORD *)(this + 44) != 992 || *(_DWORD *)(this + 40) != 31744 )
      return -1;
    return 1;
  }
  result = -1;
  v3 = *(_DWORD *)(this + 40) == 63488;
  v7 = 2;
LABEL_26:
  if ( v3 )
    return v7;
  return result;
}

```

## disassembly

```asm
0x1000f82f  mov     edi, edi
0x1000f831  push    esi
0x1000f832  xor     esi, esi
0x1000f834  inc     esi
0x1000f835  cmp     [ecx+0Ch], si
0x1000f839  jnz     short loc_1000F89F
0x1000f83b  cmp     dword ptr [ecx+10h], 0
0x1000f83f  jz      loc_1000F8D7
0x1000f845  cmp     dword ptr [ecx+10h], 3
0x1000f849  jnz     short loc_1000F89F
0x1000f84b  movzx   edx, word ptr [ecx+0Eh]
0x1000f84f  mov     eax, edx
0x1000f851  cmp     eax, 8
0x1000f854  jz      short loc_1000F89F
0x1000f856  cmp     eax, 10h
0x1000f859  jz      short loc_1000F8A4
0x1000f85b  cmp     eax, 18h
0x1000f85e  jz      short loc_1000F884
0x1000f860  cmp     edx, 20h ; ' '
0x1000f863  jnz     short loc_1000F89F
0x1000f865  cmp     dword ptr [ecx+30h], 0FFh
0x1000f86c  jnz     short loc_1000F89F
0x1000f86e  cmp     dword ptr [ecx+2Ch], 0FF00h
0x1000f875  jnz     short loc_1000F89F
0x1000f877  cmp     dword ptr [ecx+28h], 0FF0000h
0x1000f87e  jnz     short loc_1000F89F
0x1000f880  push    4
0x1000f882  jmp     short loc_1000F8FC
0x1000f884  cmp     dword ptr [ecx+30h], 0FFh
0x1000f88b  jnz     short loc_1000F89F
0x1000f88d  cmp     dword ptr [ecx+2Ch], 0FF00h
0x1000f894  jnz     short loc_1000F89F
0x1000f896  cmp     dword ptr [ecx+28h], 0FF0000h
0x1000f89d  jz      short loc_1000F8FA
0x1000f89f  or      eax, 0FFFFFFFFh
0x1000f8a2  pop     esi
0x1000f8a3  retn
0x1000f8a4  cmp     dword ptr [ecx+30h], 1Fh
0x1000f8a8  jnz     short loc_1000F89F
0x1000f8aa  cmp     dword ptr [ecx+2Ch], 7E0h
0x1000f8b1  jnz     short loc_1000F8C1
0x1000f8b3  or      eax, 0FFFFFFFFh
0x1000f8b6  cmp     dword ptr [ecx+28h], 0F800h
0x1000f8bd  push    2
0x1000f8bf  jmp     short loc_1000F8F4
0x1000f8c1  cmp     dword ptr [ecx+2Ch], 3E0h
0x1000f8c8  jnz     short loc_1000F89F
0x1000f8ca  cmp     dword ptr [ecx+28h], 7C00h
0x1000f8d1  jnz     short loc_1000F89F
0x1000f8d3  mov     eax, esi
0x1000f8d5  pop     esi
0x1000f8d6  retn
0x1000f8d7  movzx   eax, word ptr [ecx+0Eh]
0x1000f8db  mov     ecx, eax
0x1000f8dd  cmp     eax, 8
0x1000f8e0  jz      short loc_1000F8FF
0x1000f8e2  cmp     eax, 10h
0x1000f8e5  jz      short loc_1000F8D3
0x1000f8e7  cmp     eax, 18h
0x1000f8ea  jz      short loc_1000F8FA
0x1000f8ec  or      eax, 0FFFFFFFFh
0x1000f8ef  cmp     ecx, 20h ; ' '
0x1000f8f2  push    4
0x1000f8f4  pop     edx
0x1000f8f5  cmovz   eax, edx
0x1000f8f8  pop     esi
0x1000f8f9  retn
0x1000f8fa  push    3
0x1000f8fc  pop     eax
0x1000f8fd  pop     esi
0x1000f8fe  retn
0x1000f8ff  xor     eax, eax
0x1000f901  pop     esi
0x1000f902  retn
```
