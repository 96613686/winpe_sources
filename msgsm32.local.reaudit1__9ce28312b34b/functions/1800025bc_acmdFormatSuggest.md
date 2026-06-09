# acmdFormatSuggest

- ea: `0x1800025bc`
- end: `0x18000274a`
- name: `acmdFormatSuggest`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800020d0`

## callees

- `0x1800025bc`
- `0x180002aec`
- `0x180002b54`

## pseudocode

```c
__int64 __fastcall acmdFormatSuggest(__int64 a1, __int64 a2)
{
  int v2; // edi
  __int64 v4; // rbx
  __int64 v5; // r11
  unsigned __int16 v6; // r9
  int v7; // r8d
  unsigned __int16 v8; // dx
  unsigned __int16 v9; // dx
  __int64 v10; // r11
  __int16 v11; // ax
  int v12; // eax

  v2 = *(_DWORD *)(a2 + 4);
  if ( (v2 & 0xF00000) != 0 )
    return 8;
  v4 = *(_QWORD *)(a2 + 8);
  if ( *(_WORD *)v4 == 1 )
  {
    if ( (unsigned int)pcmIsValidFormat(*(_QWORD *)(a2 + 8)) )
    {
      if ( (v2 & 0x10000) != 0 )
      {
        if ( *(_WORD *)v10 != 49 )
          return 512;
      }
      else
      {
        *(_WORD *)v10 = 49;
      }
      v11 = *(_WORD *)(v4 + 2);
      if ( (v2 & 0x20000) != 0 )
      {
        if ( v11 != *(_WORD *)(v10 + 2) )
          return 512;
      }
      else
      {
        *(_WORD *)(v10 + 2) = v11;
      }
      if ( (v2 & 0x40000) != 0 )
      {
        v12 = *(_DWORD *)(v10 + 4);
        if ( *(_DWORD *)(v4 + 4) != v12 )
          return 512;
      }
      else
      {
        v12 = *(_DWORD *)(v4 + 4);
        *(_DWORD *)(v10 + 4) = v12;
      }
      if ( (v2 & 0x80000) != 0 )
      {
        if ( *(_WORD *)(v10 + 14) )
          return 512;
      }
      else
      {
        *(_WORD *)(v10 + 14) = 0;
      }
      *(_WORD *)(v10 + 12) = 65;
      *(_DWORD *)(v10 + 16) = 20971522;
      *(_DWORD *)(v10 + 8) = 65 * v12 / 0x140u;
      return 0;
    }
    return 512;
  }
  if ( *(_WORD *)v4 != 49 || !(unsigned int)gsm610IsValidFormat(*(_QWORD *)(a2 + 8)) )
    return 512;
  if ( (v2 & 0x10000) != 0 )
  {
    if ( *(_WORD *)v5 != 1 )
      return 512;
  }
  else
  {
    *(_WORD *)v5 = 1;
  }
  if ( (v2 & 0x20000) != 0 )
  {
    v6 = *(_WORD *)(v5 + 2);
    if ( *(_WORD *)(v4 + 2) != v6 )
      return 512;
  }
  else
  {
    v6 = *(_WORD *)(v4 + 2);
    *(_WORD *)(v5 + 2) = v6;
  }
  if ( (v2 & 0x40000) != 0 )
  {
    v7 = *(_DWORD *)(v5 + 4);
    if ( *(_DWORD *)(v4 + 4) != v7 )
      return 512;
  }
  else
  {
    v7 = *(_DWORD *)(v4 + 4);
    *(_DWORD *)(v5 + 4) = v7;
  }
  if ( (v2 & 0x80000) != 0 )
  {
    v8 = *(_WORD *)(v5 + 14);
    if ( ((v8 - 8) & 0xFFF7) == 0 )
      goto LABEL_22;
    return 512;
  }
  v8 = 16;
  *(_WORD *)(v5 + 14) = 16;
LABEL_22:
  v9 = v8 >> 3 << (v6 >> 1);
  *(_WORD *)(v5 + 12) = v9;
  *(_DWORD *)(v5 + 8) = v7 * v9;
  return 0;
}

```

## disassembly

```asm
0x1800025bc  mov     [rsp+arg_0], rbx
0x1800025c1  push    rdi
0x1800025c2  sub     rsp, 20h
0x1800025c6  mov     edi, [rdx+4]
0x1800025c9  test    edi, 0F00000h
0x1800025cf  jz      short loc_1800025DB
0x1800025d1  mov     eax, 8
0x1800025d6  jmp     loc_18000273F
0x1800025db  mov     rbx, [rdx+8]
0x1800025df  mov     r11, [rdx+14h]
0x1800025e3  movzx   ecx, word ptr [rbx]
0x1800025e6  sub     ecx, 1
0x1800025e9  jz      loc_1800026AF
0x1800025ef  cmp     ecx, 30h ; '0'
0x1800025f2  jnz     loc_180002711
0x1800025f8  mov     rcx, rbx
0x1800025fb  call    gsm610IsValidFormat
0x180002600  test    eax, eax
0x180002602  jz      loc_180002711
0x180002608  bt      edi, 10h
0x18000260c  jnb     short loc_18000261F
0x18000260e  mov     eax, 1
0x180002613  cmp     ax, [r11]
0x180002617  jnz     loc_180002711
0x18000261d  jmp     short loc_180002625
0x18000261f  mov     word ptr [r11], 1
0x180002625  bt      edi, 11h
0x180002629  jnb     short loc_18000263D
0x18000262b  movzx   r9d, word ptr [r11+2]
0x180002630  cmp     [rbx+2], r9w
0x180002635  jnz     loc_180002711
0x18000263b  jmp     short loc_180002647
0x18000263d  movzx   r9d, word ptr [rbx+2]
0x180002642  mov     [r11+2], r9w
0x180002647  bt      edi, 12h
0x18000264b  jnb     short loc_18000265D
0x18000264d  mov     r8d, [r11+4]
0x180002651  cmp     [rbx+4], r8d
0x180002655  jnz     loc_180002711
0x18000265b  jmp     short loc_180002665
0x18000265d  mov     r8d, [rbx+4]
0x180002661  mov     [r11+4], r8d
0x180002665  bt      edi, 13h
0x180002669  jnb     short loc_180002683
0x18000266b  movzx   edx, word ptr [r11+0Eh]
0x180002670  mov     ecx, 0FFF7h
0x180002675  lea     eax, [rdx-8]
0x180002678  test    cx, ax
0x18000267b  jnz     loc_180002711
0x180002681  jmp     short loc_18000268D
0x180002683  mov     edx, 10h
0x180002688  mov     [r11+0Eh], dx
0x18000268d  shr     dx, 3
0x180002691  movzx   ecx, r9w
0x180002695  shr     ecx, 1
0x180002697  shl     dx, cl
0x18000269a  movzx   eax, dx
0x18000269d  mov     [r11+0Ch], ax
0x1800026a2  imul    eax, r8d
0x1800026a6  mov     [r11+8], eax
0x1800026aa  jmp     loc_18000273D
0x1800026af  mov     rcx, rbx
0x1800026b2  call    pcmIsValidFormat
0x1800026b7  xor     ecx, ecx
0x1800026b9  test    eax, eax
0x1800026bb  jz      short loc_180002711
0x1800026bd  bt      edi, 10h
0x1800026c1  jnb     short loc_1800026CE
0x1800026c3  lea     eax, [rcx+31h]
0x1800026c6  cmp     ax, [r11]
0x1800026ca  jnz     short loc_180002711
0x1800026cc  jmp     short loc_1800026D4
0x1800026ce  mov     word ptr [r11], 31h ; '1'
0x1800026d4  movzx   eax, word ptr [rbx+2]
0x1800026d8  bt      edi, 11h
0x1800026dc  jnb     short loc_1800026E7
0x1800026de  cmp     ax, [r11+2]
0x1800026e3  jnz     short loc_180002711
0x1800026e5  jmp     short loc_1800026EC
0x1800026e7  mov     [r11+2], ax
0x1800026ec  bt      edi, 12h
0x1800026f0  jnb     short loc_1800026FD
0x1800026f2  mov     eax, [r11+4]
0x1800026f6  cmp     [rbx+4], eax
0x1800026f9  jnz     short loc_180002711
0x1800026fb  jmp     short loc_180002704
0x1800026fd  mov     eax, [rbx+4]
0x180002700  mov     [r11+4], eax
0x180002704  bt      edi, 13h
0x180002708  jnb     short loc_180002718
0x18000270a  cmp     cx, [r11+0Eh]
0x18000270f  jz      short loc_18000271D
0x180002711  mov     eax, 200h
0x180002716  jmp     short loc_18000273F
0x180002718  mov     [r11+0Eh], cx
0x18000271d  imul    ecx, eax, 41h ; 'A'
0x180002720  mov     eax, 0CCCCCCCDh
0x180002725  mov     word ptr [r11+0Ch], 41h ; 'A'
0x18000272c  mov     dword ptr [r11+10h], 1400002h
0x180002734  mul     ecx
0x180002736  shr     edx, 8
0x180002739  mov     [r11+8], edx
0x18000273d  xor     eax, eax
0x18000273f  mov     rbx, [rsp+28h+arg_0]
0x180002744  add     rsp, 20h
0x180002748  pop     rdi
0x180002749  retn
```
