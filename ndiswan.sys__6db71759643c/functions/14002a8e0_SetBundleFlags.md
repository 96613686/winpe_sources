# SetBundleFlags

- ea: `0x14002a8e0`
- end: `0x14002aa2e`
- name: `SetBundleFlags`
- size: `334`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140025c80`
- `0x140025fa0`
- `0x1400274e0`
- `0x14002aa40`
- `0x14002b270`
- `0x14002bab0`

## callees

- `0x14002a8e0`

## pseudocode

```c
__int64 __fastcall SetBundleFlags(__int64 a1)
{
  unsigned int v1; // edx
  int v2; // r10d
  int v3; // r9d
  int v4; // r8d
  int v5; // eax
  int v6; // edx
  int v7; // r8d
  int v8; // r8d
  BOOL v9; // eax
  int v10; // r8d
  unsigned int v11; // r8d
  int v12; // eax
  int v13; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 464);
  v2 = 2;
  v3 = 1;
  if ( (v1 & 1) == 0 || (v4 = 2, !*(_QWORD *)(a1 + 776)) )
    v4 = 0;
  v5 = v4 | (v1 >> 13) & 0x800;
  if ( *(_QWORD *)(a1 + 1208) )
  {
    if ( (v1 & 0x10) != 0 )
    {
      v5 |= 0x44u;
    }
    else if ( (v1 & 0x20) != 0 )
    {
      v5 |= 0x84u;
    }
    else if ( (v1 & 0x80u) == 0 )
    {
      if ( (v1 & 0x40) != 0 )
        v5 |= 0x104u;
    }
    else
    {
      v5 |= 0x1004u;
    }
  }
  v6 = 512;
  if ( *(_WORD *)(a1 + 392) != 45 || (v7 = 512, !*(_QWORD *)(a1 + 400)) )
    v7 = 0;
  v8 = v5 | v7;
  v9 = (*(_DWORD *)(a1 + 68) & 0x10) != 0 && (*(_DWORD *)(a1 + 64) > 1u || (*(_DWORD *)(a1 + 16) & 0x400) != 0);
  v10 = v9 | v8;
  *(_DWORD *)(a1 + 104) = v10;
  if ( v10 )
    *(_DWORD *)(a1 + 16) &= ~0x100000u;
  v11 = *(_DWORD *)(a1 + 840);
  if ( (v11 & 1) == 0 || !*(_QWORD *)(a1 + 1152) )
    v2 = 0;
  v12 = v2 | (v11 >> 13) & 0x800;
  if ( *(_QWORD *)(a1 + 1288) )
  {
    if ( (v11 & 0x10) != 0 )
    {
      v12 |= 0x44u;
    }
    else if ( (v11 & 0x20) != 0 )
    {
      v12 |= 0x84u;
    }
    else if ( (v11 & 0x80u) == 0 )
    {
      if ( (v11 & 0x40) != 0 )
        v12 |= 0x104u;
    }
    else
    {
      v12 |= 0x1004u;
    }
  }
  if ( *(_WORD *)(a1 + 396) != 45 || !*(_QWORD *)(a1 + 400) )
    v6 = 0;
  v13 = v12 | v6;
  result = *(unsigned int *)(a1 + 72);
  if ( (result & 0x10) == 0 || *(_DWORD *)(a1 + 64) <= 1u && (*(_DWORD *)(a1 + 16) & 0x400) == 0 )
    v3 = 0;
  *(_DWORD *)(a1 + 256) = v3 | v13;
  return result;
}

```

## disassembly

```asm
0x14002a8e0  mov     edx, [rcx+1D0h]
0x14002a8e6  mov     r10d, 2
0x14002a8ec  xor     r11d, r11d
0x14002a8ef  lea     r9d, [r10-1]
0x14002a8f3  test    r9b, dl
0x14002a8f6  jz      short loc_14002A904
0x14002a8f8  mov     r8d, r10d
0x14002a8fb  cmp     [rcx+308h], r11
0x14002a902  jnz     short loc_14002A907
0x14002a904  mov     r8d, r11d
0x14002a907  mov     eax, edx
0x14002a909  shr     eax, 0Dh
0x14002a90c  and     eax, 800h
0x14002a911  or      eax, r8d
0x14002a914  cmp     [rcx+4B8h], r11
0x14002a91b  jz      short loc_14002A948
0x14002a91d  test    dl, 10h
0x14002a920  jz      short loc_14002A927
0x14002a922  or      eax, 44h
0x14002a925  jmp     short loc_14002A948
0x14002a927  test    dl, 20h
0x14002a92a  jz      short loc_14002A933
0x14002a92c  or      eax, 84h
0x14002a931  jmp     short loc_14002A948
0x14002a933  test    dl, dl
0x14002a935  jns     short loc_14002A93E
0x14002a937  or      eax, 1004h
0x14002a93c  jmp     short loc_14002A948
0x14002a93e  test    dl, 40h
0x14002a941  jz      short loc_14002A948
0x14002a943  or      eax, 104h
0x14002a948  cmp     word ptr [rcx+188h], 2Dh ; '-'
0x14002a950  mov     edx, 200h
0x14002a955  jnz     short loc_14002A963
0x14002a957  mov     r8d, edx
0x14002a95a  cmp     [rcx+190h], r11
0x14002a961  jnz     short loc_14002A966
0x14002a963  mov     r8d, r11d
0x14002a966  or      r8d, eax
0x14002a969  mov     eax, [rcx+44h]
0x14002a96c  test    al, 10h
0x14002a96e  jz      short loc_14002A984
0x14002a970  cmp     [rcx+40h], r9d
0x14002a974  ja      short loc_14002A97F
0x14002a976  test    dword ptr [rcx+10h], 400h
0x14002a97d  jz      short loc_14002A984
0x14002a97f  mov     eax, r9d
0x14002a982  jmp     short loc_14002A987
0x14002a984  mov     eax, r11d
0x14002a987  or      r8d, eax
0x14002a98a  mov     [rcx+68h], r8d
0x14002a98e  jz      short loc_14002A995
0x14002a990  btr     dword ptr [rcx+10h], 14h
0x14002a995  mov     r8d, [rcx+348h]
0x14002a99c  test    r9b, r8b
0x14002a99f  jz      short loc_14002A9AA
0x14002a9a1  cmp     [rcx+480h], r11
0x14002a9a8  jnz     short loc_14002A9AD
0x14002a9aa  mov     r10d, r11d
0x14002a9ad  mov     eax, r8d
0x14002a9b0  shr     eax, 0Dh
0x14002a9b3  and     eax, 800h
0x14002a9b8  or      eax, r10d
0x14002a9bb  cmp     [rcx+508h], r11
0x14002a9c2  jz      short loc_14002A9F3
0x14002a9c4  test    r8b, 10h
0x14002a9c8  jz      short loc_14002A9CF
0x14002a9ca  or      eax, 44h
0x14002a9cd  jmp     short loc_14002A9F3
0x14002a9cf  test    r8b, 20h
0x14002a9d3  jz      short loc_14002A9DC
0x14002a9d5  or      eax, 84h
0x14002a9da  jmp     short loc_14002A9F3
0x14002a9dc  test    r8b, r8b
0x14002a9df  jns     short loc_14002A9E8
0x14002a9e1  or      eax, 1004h
0x14002a9e6  jmp     short loc_14002A9F3
0x14002a9e8  test    r8b, 40h
0x14002a9ec  jz      short loc_14002A9F3
0x14002a9ee  or      eax, 104h
0x14002a9f3  cmp     word ptr [rcx+18Ch], 2Dh ; '-'
0x14002a9fb  jnz     short loc_14002AA06
0x14002a9fd  cmp     [rcx+190h], r11
0x14002aa04  jnz     short loc_14002AA09
0x14002aa06  mov     edx, r11d
0x14002aa09  or      edx, eax
0x14002aa0b  mov     eax, [rcx+48h]
0x14002aa0e  test    al, 10h
0x14002aa10  jz      short loc_14002AA21
0x14002aa12  cmp     [rcx+40h], r9d
0x14002aa16  ja      short loc_14002AA24
0x14002aa18  test    dword ptr [rcx+10h], 400h
0x14002aa1f  jnz     short loc_14002AA24
0x14002aa21  mov     r9d, r11d
0x14002aa24  or      edx, r9d
0x14002aa27  mov     [rcx+100h], edx
0x14002aa2d  retn
```
