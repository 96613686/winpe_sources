# DecompressGetFormat(x,x,x)

- ea: `0x10010034`
- end: `0x100100b9`
- name: `_DecompressGetFormat@12`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100093a0`

## callees

- `0x10010034`

## pseudocode

```c
int __fastcall DecompressGetFormat(int a1, int a2, int a3)
{
  int v3; // ecx
  unsigned int v4; // eax

  if ( !a2 )
    return -2;
  v3 = ((*(_BYTE *)(a2 + 14) & 0x1F) == 8) + 1;
  if ( *(_DWORD *)(a2 + 16) != 1684633187 )
    v3 = 0;
  if ( !v3 )
    return -2;
  if ( a3 )
  {
    *(_DWORD *)a3 = 40;
    *(_DWORD *)(a3 + 4) = *(_DWORD *)(a2 + 4);
    *(_DWORD *)(a3 + 8) = *(_DWORD *)(a2 + 8);
    *(_WORD *)(a3 + 12) = 1;
    *(_WORD *)(a3 + 14) = 24;
    *(_DWORD *)(a3 + 16) = 0;
    v4 = *(_DWORD *)(a2 + 8) * (((unsigned int)(24 * *(_DWORD *)(a2 + 4) + 31) >> 3) & 0x1FFFFFFC);
    *(_DWORD *)(a3 + 36) = 0;
    *(_DWORD *)(a3 + 32) = 0;
    *(_DWORD *)(a3 + 28) = 0;
    *(_DWORD *)(a3 + 24) = 0;
    *(_DWORD *)(a3 + 20) = v4;
    return 0;
  }
  return 40;
}

```

## disassembly

```asm
0x10010034  mov     edi, edi
0x10010036  push    ebp
0x10010037  mov     ebp, esp
0x10010039  test    edx, edx
0x1001003b  jz      short loc_100100B2
0x1001003d  mov     al, [edx+0Eh]
0x10010040  xor     ecx, ecx
0x10010042  and     al, 1Fh
0x10010044  cmp     al, 8
0x10010046  setz    cl
0x10010049  xor     eax, eax
0x1001004b  inc     ecx
0x1001004c  cmp     dword ptr [edx+10h], 64697663h
0x10010053  cmovnz  ecx, eax
0x10010056  test    ecx, ecx
0x10010058  jz      short loc_100100B2
0x1001005a  mov     ecx, [ebp+arg_0]
0x1001005d  test    ecx, ecx
0x1001005f  jnz     short loc_10010065
0x10010061  push    28h ; '('
0x10010063  jmp     short loc_100100B4
0x10010065  mov     dword ptr [ecx], 28h ; '('
0x1001006b  mov     eax, [edx+4]
0x1001006e  mov     [ecx+4], eax
0x10010071  mov     eax, [edx+8]
0x10010074  mov     [ecx+8], eax
0x10010077  xor     eax, eax
0x10010079  inc     eax
0x1001007a  push    esi
0x1001007b  mov     [ecx+0Ch], ax
0x1001007f  xor     esi, esi
0x10010081  push    18h
0x10010083  pop     eax
0x10010084  mov     [ecx+0Eh], ax
0x10010088  mov     [ecx+10h], esi
0x1001008b  imul    eax, [edx+4], 18h
0x1001008f  add     eax, 1Fh
0x10010092  shr     eax, 3
0x10010095  and     eax, 1FFFFFFCh
0x1001009a  imul    eax, [edx+8]
0x1001009e  mov     [ecx+24h], esi
0x100100a1  mov     [ecx+20h], esi
0x100100a4  mov     [ecx+1Ch], esi
0x100100a7  mov     [ecx+18h], esi
0x100100aa  mov     [ecx+14h], eax
0x100100ad  xor     eax, eax
0x100100af  pop     esi
0x100100b0  jmp     short loc_100100B5
0x100100b2  push    0FFFFFFFEh
0x100100b4  pop     eax
0x100100b5  pop     ebp
0x100100b6  retn    4
```
