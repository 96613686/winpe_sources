# DecompressQueryIndirect(x,x,x,x,x,x,x,x,x,x,x,x,x,x)

- ea: `0x1000ff0e`
- end: `0x1001002e`
- name: `_DecompressQueryIndirect@56`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100101f2`

## callees

- `0x1000f82f`
- `0x1000ff0e`

## pseudocode

```c
int __stdcall DecompressQueryIndirect(
        int a1,
        int a2,
        int a3,
        int a4,
        _DWORD *a5,
        int *a6,
        int a7,
        int a8,
        int a9,
        int a10,
        _DWORD *a11,
        unsigned int *a12)
{
  int v12; // ecx
  int v13; // eax
  int v14; // esi
  int v15; // ecx
  unsigned int v16; // esi
  int v17; // eax

  if ( !a1 )
    return -2;
  v12 = ((*(_BYTE *)(a1 + 14) & 0x1F) == 8) + 1;
  if ( *(_DWORD *)(a1 + 16) != 1684633187 )
    v12 = 0;
  if ( !v12 )
    return -2;
  if ( *a5 == -1 )
    *a5 = *(_DWORD *)(a1 + 4);
  v13 = *a6;
  if ( *a6 == -1 )
  {
    v13 = *(_DWORD *)(a1 + 8);
    *a6 = v13;
  }
  if ( !a3 && !a4 )
  {
    v14 = *(_DWORD *)(a1 + 4);
    if ( *a5 == v14 )
    {
      v15 = *(_DWORD *)(a1 + 8);
      if ( v13 == v15 && (unsigned int)(v14 - 1) <= 0x7FFE && (unsigned int)(v15 + 0x8000) <= 0xFFFF )
      {
        if ( !a7 )
          return 0;
        if ( *a11 == -1 )
          *a11 = *(_DWORD *)(a7 + 4);
        v16 = *a12;
        if ( *a12 == -1 )
        {
          v16 = abs32(*(_DWORD *)(a7 + 8));
          *a12 = v16;
        }
        v17 = DecompressedDibType(a7);
        if ( v17 != -1
          && (*a11 == *a5 && v16 == *a6 || !v17 && *a11 == 2 * *a5 && v16 == 2 * *a6)
          && (v17 != 5 && v17 != 8 || (((unsigned __int8)v16 | *(_BYTE *)a11) & 3) == 0)
          && (v17 != 6 && v17 != 7 || (*(_BYTE *)a11 & 1) == 0) )
        {
          return 0;
        }
        return -2;
      }
    }
  }
  return -6;
}

```

## disassembly

```asm
0x1000ff0e  mov     edi, edi
0x1000ff10  push    ebp
0x1000ff11  mov     ebp, esp
0x1000ff13  mov     edx, [ebp+arg_0]
0x1000ff16  push    ebx
0x1000ff17  push    esi
0x1000ff18  push    edi
0x1000ff19  test    edx, edx
0x1000ff1b  jz      loc_10010024
0x1000ff21  mov     al, [edx+0Eh]
0x1000ff24  xor     ecx, ecx
0x1000ff26  and     al, 1Fh
0x1000ff28  cmp     al, 8
0x1000ff2a  setz    cl
0x1000ff2d  xor     eax, eax
0x1000ff2f  inc     ecx
0x1000ff30  cmp     dword ptr [edx+10h], 64697663h
0x1000ff37  cmovnz  ecx, eax
0x1000ff3a  test    ecx, ecx
0x1000ff3c  jz      loc_10010024
0x1000ff42  mov     edi, [ebp+arg_10]
0x1000ff45  cmp     dword ptr [edi], 0FFFFFFFFh
0x1000ff48  jnz     short loc_1000FF4F
0x1000ff4a  mov     eax, [edx+4]
0x1000ff4d  mov     [edi], eax
0x1000ff4f  mov     ecx, [ebp+arg_14]
0x1000ff52  mov     eax, [ecx]
0x1000ff54  cmp     eax, 0FFFFFFFFh
0x1000ff57  jnz     short loc_1000FF5E
0x1000ff59  mov     eax, [edx+8]
0x1000ff5c  mov     [ecx], eax
0x1000ff5e  cmp     [ebp+arg_8], 0
0x1000ff62  jnz     loc_10010020
0x1000ff68  cmp     [ebp+arg_C], 0
0x1000ff6c  jnz     loc_10010020
0x1000ff72  mov     esi, [edx+4]
0x1000ff75  cmp     [edi], esi
0x1000ff77  jnz     loc_10010020
0x1000ff7d  mov     ecx, [edx+8]
0x1000ff80  cmp     eax, ecx
0x1000ff82  jnz     loc_10010020
0x1000ff88  lea     eax, [esi-1]
0x1000ff8b  cmp     eax, 7FFEh
0x1000ff90  ja      loc_10010020
0x1000ff96  lea     eax, [ecx+8000h]
0x1000ff9c  cmp     eax, 0FFFFh
0x1000ffa1  ja      short loc_10010020
0x1000ffa3  mov     ecx, [ebp+arg_18]
0x1000ffa6  test    ecx, ecx
0x1000ffa8  jz      short loc_1001001C
0x1000ffaa  mov     ebx, [ebp+arg_28]
0x1000ffad  cmp     dword ptr [ebx], 0FFFFFFFFh
0x1000ffb0  jnz     short loc_1000FFB7
0x1000ffb2  mov     eax, [ecx+4]
0x1000ffb5  mov     [ebx], eax
0x1000ffb7  mov     esi, [ebp+arg_2C]
0x1000ffba  mov     esi, [esi]
0x1000ffbc  cmp     esi, 0FFFFFFFFh
0x1000ffbf  jnz     short loc_1000FFD0
0x1000ffc1  mov     eax, [ecx+8]
0x1000ffc4  cdq
0x1000ffc5  mov     esi, eax
0x1000ffc7  mov     eax, [ebp+arg_2C]
0x1000ffca  xor     esi, edx
0x1000ffcc  sub     esi, edx
0x1000ffce  mov     [eax], esi
0x1000ffd0  call    _DecompressedDibType@4; DecompressedDibType(x)
0x1000ffd5  mov     ecx, eax
0x1000ffd7  cmp     ecx, 0FFFFFFFFh
0x1000ffda  jz      short loc_10010024
0x1000ffdc  mov     eax, [edi]
0x1000ffde  mov     edx, [ebp+arg_14]
0x1000ffe1  cmp     [ebx], eax
0x1000ffe3  jnz     short loc_1000FFE9
0x1000ffe5  cmp     esi, [edx]
0x1000ffe7  jz      short loc_1000FFFB
0x1000ffe9  test    ecx, ecx
0x1000ffeb  jnz     short loc_10010024
0x1000ffed  add     eax, eax
0x1000ffef  cmp     [ebx], eax
0x1000fff1  jnz     short loc_10010024
0x1000fff3  mov     eax, [edx]
0x1000fff5  add     eax, eax
0x1000fff7  cmp     esi, eax
0x1000fff9  jnz     short loc_10010024
0x1000fffb  cmp     ecx, 5
0x1000fffe  jz      short loc_10010005
0x10010000  cmp     ecx, 8
0x10010003  jnz     short loc_1001000D
0x10010005  mov     eax, [ebx]
0x10010007  or      eax, esi
0x10010009  test    al, 3
0x1001000b  jnz     short loc_10010024
0x1001000d  cmp     ecx, 6
0x10010010  jz      short loc_10010017
0x10010012  cmp     ecx, 7
0x10010015  jnz     short loc_1001001C
0x10010017  test    byte ptr [ebx], 1
0x1001001a  jnz     short loc_10010024
0x1001001c  xor     eax, eax
0x1001001e  jmp     short loc_10010027
0x10010020  push    0FFFFFFFAh
0x10010022  jmp     short loc_10010026
0x10010024  push    0FFFFFFFEh
0x10010026  pop     eax
0x10010027  pop     edi
0x10010028  pop     esi
0x10010029  pop     ebx
0x1001002a  pop     ebp
0x1001002b  retn    30h ; '0'
```
