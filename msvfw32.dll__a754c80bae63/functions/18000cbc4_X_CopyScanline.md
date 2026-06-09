# X_CopyScanline

- ea: `0x18000cbc4`
- end: `0x18000cc5f`
- name: `X_CopyScanline`
- size: `155`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c4d0`
- `0x18000cc70`
- `0x18000cc80`
- `0x18000cc90`

## callees

- `0x18000cbc4`

## pseudocode

```c
char __fastcall X_CopyScanline(_BYTE *a1, _BYTE *a2, int a3)
{
  _DWORD *v3; // r10
  _BYTE *v4; // r9
  __int16 v5; // ax
  int j; // eax
  int v7; // ecx
  int i; // eax
  int v9; // ecx
  int v10; // eax
  int v11; // edx

  v3 = a2;
  v4 = a1;
  if ( (((unsigned __int8)a1 ^ (unsigned __int8)a2) & 3) != 0 )
  {
    for ( i = a3 / 4; i > 0; --i )
    {
      v9 = *(_DWORD *)v4;
      v4 += 4;
      *v3++ = v9;
    }
  }
  else
  {
    if ( ((unsigned __int8)a1 & 1) != 0 )
    {
      v3 = a2 + 1;
      v4 = a1 + 1;
      *a2 = *a1;
      --a3;
    }
    if ( ((unsigned __int8)v4 & 2) != 0 )
    {
      v5 = *(_WORD *)v4;
      v4 += 2;
      *(_WORD *)v3 = v5;
      v3 = (_DWORD *)((char *)v3 + 2);
      a3 -= 2;
    }
    for ( j = a3 / 4; j > 0; --j )
    {
      v7 = *(_DWORD *)v4;
      v4 += 4;
      *v3++ = v7;
    }
  }
  v11 = a3 % 4;
  v10 = a3 / 4;
  while ( v11 > 0 )
  {
    LOBYTE(v10) = *v4++;
    *(_BYTE *)v3 = v10;
    v3 = (_DWORD *)((char *)v3 + 1);
    --v11;
  }
  return v10;
}

```

## disassembly

```asm
0x18000cbc4  mov     eax, edx
0x18000cbc6  mov     r10, rdx
0x18000cbc9  xor     eax, ecx
0x18000cbcb  mov     r9, rcx
0x18000cbce  test    al, 3
0x18000cbd0  jnz     short loc_18000CC22
0x18000cbd2  test    r9b, 1
0x18000cbd6  jz      short loc_18000CBE5
0x18000cbd8  mov     al, [rcx]
0x18000cbda  inc     r10
0x18000cbdd  inc     r9
0x18000cbe0  mov     [rdx], al
0x18000cbe2  dec     r8d
0x18000cbe5  test    r9b, 2
0x18000cbe9  jz      short loc_18000CBFF
0x18000cbeb  movzx   eax, word ptr [r9]
0x18000cbef  add     r9, 2
0x18000cbf3  mov     [r10], ax
0x18000cbf7  add     r10, 2
0x18000cbfb  sub     r8d, 2
0x18000cbff  mov     eax, r8d
0x18000cc02  mov     r11d, 4
0x18000cc08  cdq
0x18000cc09  idiv    r11d
0x18000cc0c  jmp     short loc_18000CC1C
0x18000cc0e  mov     ecx, [r9]
0x18000cc11  add     r9, r11
0x18000cc14  mov     [r10], ecx
0x18000cc17  add     r10, r11
0x18000cc1a  dec     eax
0x18000cc1c  test    eax, eax
0x18000cc1e  jg      short loc_18000CC0E
0x18000cc20  jmp     short loc_18000CC43
0x18000cc22  mov     eax, r8d
0x18000cc25  mov     r11d, 4
0x18000cc2b  cdq
0x18000cc2c  idiv    r11d
0x18000cc2f  jmp     short loc_18000CC3F
0x18000cc31  mov     ecx, [r9]
0x18000cc34  add     r9, r11
0x18000cc37  mov     [r10], ecx
0x18000cc3a  add     r10, r11
0x18000cc3d  dec     eax
0x18000cc3f  test    eax, eax
0x18000cc41  jg      short loc_18000CC31
0x18000cc43  mov     eax, r8d
0x18000cc46  cdq
0x18000cc47  idiv    r11d
0x18000cc4a  jmp     short loc_18000CC5A
0x18000cc4c  mov     al, [r9]
0x18000cc4f  inc     r9
0x18000cc52  mov     [r10], al
0x18000cc55  inc     r10
0x18000cc58  dec     edx
0x18000cc5a  test    edx, edx
0x18000cc5c  jg      short loc_18000CC4C
0x18000cc5e  retn
```
