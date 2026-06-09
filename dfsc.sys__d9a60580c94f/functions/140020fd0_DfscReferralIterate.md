# DfscReferralIterate

- ea: `0x140020fd0`
- end: `0x140021136`
- name: `DfscReferralIterate`
- size: `358`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1400110d8`
- `0x140016070`
- `0x140018d44`
- `0x1400191d0`
- `0x140020e10`
- `0x140021410`
- `0x140021688`
- `0x14002184c`
- `0x1400281ac`

## callees

- `0x140020fd0`

## pseudocode

```c
__int64 __fastcall DfscReferralIterate(__int64 a1)
{
  __int64 v1; // r8
  __int64 v2; // r8
  __int64 v3; // r9
  __int16 v4; // ax
  unsigned int v5; // r10d
  __int16 v6; // ax
  __int16 v8; // ax
  __int16 v9; // r9
  __int16 v10; // r9
  __int64 v11; // r11
  int i; // r10d
  __int64 v13; // r10
  __int16 v14; // r9

  if ( (*(_DWORD *)(a1 + 8) & 6) != 0 )
    return 3221225485LL;
  v1 = *(unsigned __int16 *)(a1 + 32);
  if ( (_WORD)v1 == 0xFFFF )
  {
    v2 = *(_QWORD *)(a1 + 16);
    if ( *(_WORD *)(v2 + 24) )
    {
      v3 = *(unsigned __int16 *)(v2 + 26);
      v4 = *(_WORD *)(a1 + 24);
      *(_WORD *)(a1 + 26) = v3;
      v5 = *(_DWORD *)(112 * v3 + v2 + 164);
      *(_DWORD *)(a1 + 28) = v5;
      if ( (v4 & 1) != 0 && v5 > 1 )
      {
        *(_WORD *)(a1 + 24) = v4 | 2;
        v8 = 0;
LABEL_26:
        *(_WORD *)(a1 + 32) = v8;
      }
      else
      {
        *(_WORD *)(a1 + 32) = v3;
        v6 = v4 & 0xFFFE;
        *(_WORD *)(a1 + 24) = v6;
        if ( (_WORD)v3 )
          *(_WORD *)(a1 + 24) = v6 | 4;
      }
      return 0;
    }
    return 3221225530LL;
  }
  else
  {
    v9 = *(_WORD *)(a1 + 24);
    if ( (v9 & 4) == 0 )
    {
      do
      {
        LOWORD(v1) = v1 + 1;
        *(_WORD *)(a1 + 32) = v1;
        v13 = *(_QWORD *)(a1 + 16);
        if ( (unsigned __int16)v1 >= *(_WORD *)(v13 + 24) )
          return 2147483674LL;
      }
      while ( (v9 & 8) != 0 && (_WORD)v1 == *(_WORD *)(a1 + 26) );
      if ( (v9 & 2) != 0 && *(_DWORD *)(a1 + 28) == *(_DWORD *)(112LL * (unsigned __int16)v1 + v13 + 164) )
      {
        v14 = v9 & 0xFFFD;
        v8 = *(_WORD *)(a1 + 26);
        *(_WORD *)(a1 + 24) = v14;
        if ( (_WORD)v1 != v8 )
        {
          *(_WORD *)(a1 + 24) = v14 | 4;
          goto LABEL_26;
        }
      }
      return 0;
    }
    v10 = v9 & 0xFFFB;
    *(_WORD *)(a1 + 24) = v10;
    if ( (v10 & 1) != 0 )
    {
      v11 = *(_QWORD *)(a1 + 16);
      for ( i = *(_DWORD *)(a1 + 28); i == *(_DWORD *)(112 * v1 + v11 + 52); *(_WORD *)(a1 + 32) = v1 )
        v1 = (unsigned __int16)(v1 - 1);
    }
    else
    {
      *(_WORD *)(a1 + 32) = 0;
    }
    *(_WORD *)(a1 + 24) = v10 | 8;
    return 0;
  }
}

```

## disassembly

```asm
0x140020fd0  mov     eax, [rcx+8]
0x140020fd3  test    al, 6
0x140020fd5  jnz     short loc_140021037
0x140020fd7  movzx   r8d, word ptr [rcx+20h]
0x140020fdc  mov     eax, 0FFFFh
0x140020fe1  cmp     r8w, ax
0x140020fe5  jnz     short loc_14002105D
0x140020fe7  mov     r8, [rcx+10h]
0x140020feb  cmp     word ptr [r8+18h], 0
0x140020ff1  jz      short loc_140021030
0x140020ff3  movzx   r9d, word ptr [r8+1Ah]
0x140020ff8  movzx   eax, word ptr [rcx+18h]
0x140020ffc  imul    rdx, r9, 70h ; 'p'
0x140021000  mov     [rcx+1Ah], r9w
0x140021005  mov     r10d, [rdx+r8+0A4h]
0x14002100d  mov     [rcx+1Ch], r10d
0x140021011  test    al, 1
0x140021013  jnz     short loc_14002103E
0x140021015  mov     edx, 0FFFEh
0x14002101a  mov     [rcx+20h], r9w
0x14002101f  and     ax, dx
0x140021022  mov     [rcx+18h], ax
0x140021026  test    r9w, r9w
0x14002102a  jnz     short loc_140021053
0x14002102c  xor     eax, eax
0x14002102e  retn
0x140021030  mov     eax, 0C000003Ah
0x140021035  retn
0x140021037  mov     eax, 0C000000Dh
0x14002103c  retn
0x14002103e  cmp     r10d, 1
0x140021042  jbe     short loc_140021015
0x140021044  or      ax, 2
0x140021048  mov     [rcx+18h], ax
0x14002104c  xor     eax, eax
0x14002104e  jmp     loc_140021127
0x140021053  or      ax, 4
0x140021057  mov     [rcx+18h], ax
0x14002105b  jmp     short loc_14002102C
0x14002105d  movzx   r9d, word ptr [rcx+18h]
0x140021062  test    r9b, 4
0x140021066  jz      short loc_1400210BD
0x140021068  mov     eax, 0FFFBh
0x14002106d  and     r9w, ax
0x140021071  mov     [rcx+18h], r9w
0x140021076  test    r9b, 1
0x14002107a  jz      short loc_1400210A9
0x14002107c  mov     r11, [rcx+10h]
0x140021080  mov     r10d, [rcx+1Ch]
0x140021084  imul    rdx, r8, 70h ; 'p'
0x140021088  cmp     r10d, [rdx+r11+34h]
0x14002108d  jnz     short loc_1400210AF
0x14002108f  dec     r8w
0x140021093  movzx   r8d, r8w
0x140021097  imul    rax, r8, 70h ; 'p'
0x14002109b  mov     [rcx+20h], r8w
0x1400210a0  cmp     r10d, [rax+r11+34h]
0x1400210a5  jz      short loc_14002108F
0x1400210a7  jmp     short loc_1400210AF
0x1400210a9  xor     eax, eax
0x1400210ab  mov     [rcx+20h], ax
0x1400210af  or      r9w, 8
0x1400210b4  mov     [rcx+18h], r9w
0x1400210b9  xor     eax, eax
0x1400210bb  retn
0x1400210bd  inc     r8w
0x1400210c1  mov     [rcx+20h], r8w
0x1400210c6  mov     r10, [rcx+10h]
0x1400210ca  cmp     r8w, [r10+18h]
0x1400210cf  jnb     short loc_140021130
0x1400210d1  test    r9b, 8
0x1400210d5  jz      short loc_1400210DE
0x1400210d7  cmp     r8w, [rcx+1Ah]
0x1400210dc  jz      short loc_1400210BD
0x1400210de  test    r9b, 2
0x1400210e2  jz      loc_14002102C
0x1400210e8  movzx   eax, r8w
0x1400210ec  imul    rdx, rax, 70h ; 'p'
0x1400210f0  mov     eax, [rdx+r10+0A4h]
0x1400210f8  cmp     [rcx+1Ch], eax
0x1400210fb  jnz     loc_14002102C
0x140021101  mov     eax, 0FFFDh
0x140021106  and     r9w, ax
0x14002110a  movzx   eax, word ptr [rcx+1Ah]
0x14002110e  mov     [rcx+18h], r9w
0x140021113  cmp     r8w, ax
0x140021117  jz      loc_14002102C
0x14002111d  or      r9w, 4
0x140021122  mov     [rcx+18h], r9w
0x140021127  mov     [rcx+20h], ax
0x14002112b  jmp     loc_14002102C
0x140021130  mov     eax, 8000001Ah
0x140021135  retn
```
