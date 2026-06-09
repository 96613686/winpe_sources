# acmdFormatDetails

- ea: `0x180002488`
- end: `0x1800025b4`
- name: `acmdFormatDetails`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800020d0`

## callees

- `0x180002488`
- `0x180002aec`
- `0x180002b54`

## pseudocode

```c
__int64 __fastcall acmdFormatDetails(__int64 a1, __int64 a2, char a3)
{
  int v4; // r8d
  __int64 result; // rax
  __int64 v6; // r8
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned __int16 v9; // dx
  int v10; // ecx
  _WORD *v11; // rcx
  int IsValidFormat; // eax
  __int64 v13; // r11
  int v14; // eax

  v4 = a3 & 0xF;
  if ( v4 )
  {
    if ( v4 != 1 )
      return 8;
  }
  else
  {
    v6 = *(_QWORD *)(a2 + 16);
    if ( *(_DWORD *)(a2 + 8) == 1 )
    {
      if ( *(_DWORD *)(a2 + 4) >= 8u )
        return 512;
      *(_WORD *)v6 = 1;
      v8 = *(_DWORD *)(a2 + 4);
      *(_WORD *)(v6 + 2) = 1;
      v9 = gauPcmFormatIndexToBitsPerSample[2 * (v8 & 1)];
      v10 = gauFormatIndexToSampleRate[((unsigned __int64)v8 >> 1) & 3];
      *(_WORD *)(v6 + 14) = v9;
      v9 >>= 3;
      *(_WORD *)(v6 + 12) = v9;
      *(_DWORD *)(v6 + 4) = v10;
      *(_DWORD *)(v6 + 8) = v10 * v9;
    }
    else
    {
      if ( *(_DWORD *)(a2 + 8) != 49 || *(_DWORD *)(a2 + 4) >= 4u )
        return 512;
      *(_WORD *)v6 = *(_WORD *)(a2 + 8);
      v7 = *(_DWORD *)(a2 + 4) & 3;
      *(_WORD *)(v6 + 2) = 1;
      *(_DWORD *)(v6 + 12) = 65;
      *(_DWORD *)(v6 + 16) = 20971522;
      LODWORD(v7) = gauFormatIndexToSampleRate[v7];
      *(_DWORD *)(v6 + 4) = v7;
      *(_DWORD *)(v6 + 8) = 65 * (int)v7 / 0x140u;
      *(_DWORD *)(a2 + 12) = 1;
    }
  }
  v11 = *(_WORD **)(a2 + 16);
  if ( *v11 != 1 )
  {
    if ( *v11 == 49 )
    {
      IsValidFormat = gsm610IsValidFormat(v11);
      goto LABEL_14;
    }
    return 512;
  }
  IsValidFormat = pcmIsValidFormat(v11);
LABEL_14:
  if ( !IsValidFormat )
    return 512;
  v14 = 284;
  *(_DWORD *)(v13 + 12) = 1;
  if ( *(_DWORD *)v13 < 0x11Cu )
    v14 = *(_DWORD *)v13;
  *(_DWORD *)v13 = v14;
  result = 0;
  *(_WORD *)(v13 + 28) = 0;
  return result;
}

```

## disassembly

```asm
0x180002488  push    rbx
0x18000248a  sub     rsp, 20h
0x18000248e  mov     r11, rdx
0x180002491  mov     ebx, 1
0x180002496  and     r8d, 0Fh
0x18000249a  jz      short loc_1800024AD
0x18000249c  cmp     r8d, ebx
0x18000249f  jz      loc_18000256D
0x1800024a5  lea     eax, [rbx+7]
0x1800024a8  jmp     loc_1800025AE
0x1800024ad  mov     ecx, [rdx+8]
0x1800024b0  mov     r8, [rdx+10h]
0x1800024b4  sub     ecx, ebx
0x1800024b6  jz      short loc_180002518
0x1800024b8  cmp     ecx, 30h ; '0'
0x1800024bb  jnz     loc_1800025A9
0x1800024c1  cmp     dword ptr [rdx+4], 4
0x1800024c5  jnb     loc_1800025A9
0x1800024cb  movzx   eax, word ptr [rdx+8]
0x1800024cf  lea     r9, __ImageBase
0x1800024d6  mov     [r8], ax
0x1800024da  mov     eax, 0CCCCCCCDh
0x1800024df  mov     ecx, [rdx+4]
0x1800024e2  and     ecx, 3
0x1800024e5  mov     [r8+2], bx
0x1800024ea  mov     dword ptr [r8+0Ch], 41h ; 'A'
0x1800024f2  mov     dword ptr [r8+10h], 1400002h
0x1800024fa  mov     ecx, ds:rva gauFormatIndexToSampleRate[r9+rcx*4]
0x180002502  mov     [r8+4], ecx
0x180002506  imul    ecx, 41h ; 'A'
0x180002509  mul     ecx
0x18000250b  shr     edx, 8
0x18000250e  mov     [r8+8], edx
0x180002512  mov     [r11+0Ch], ebx
0x180002516  jmp     short loc_18000256D
0x180002518  cmp     dword ptr [rdx+4], 8
0x18000251c  jnb     loc_1800025A9
0x180002522  lea     r9, __ImageBase
0x180002529  mov     [r8], bx
0x18000252d  mov     eax, [rdx+4]
0x180002530  mov     ecx, eax
0x180002532  mov     [r8+2], bx
0x180002537  and     rax, rbx
0x18000253a  shr     rcx, 1
0x18000253d  and     ecx, 3
0x180002540  movzx   edx, ds:rva gauPcmFormatIndexToBitsPerSample[r9+rax*4]
0x180002549  mov     ecx, ds:rva gauFormatIndexToSampleRate[r9+rcx*4]
0x180002551  mov     [r8+0Eh], dx
0x180002556  shr     dx, 3
0x18000255a  movzx   eax, dx
0x18000255d  mov     [r8+0Ch], ax
0x180002562  imul    eax, ecx
0x180002565  mov     [r8+4], ecx
0x180002569  mov     [r8+8], eax
0x18000256d  mov     rcx, [r11+10h]
0x180002571  movzx   edx, word ptr [rcx]
0x180002574  sub     edx, ebx
0x180002576  jz      short loc_180002584
0x180002578  cmp     edx, 30h ; '0'
0x18000257b  jnz     short loc_1800025A9
0x18000257d  call    gsm610IsValidFormat
0x180002582  jmp     short loc_180002589
0x180002584  call    pcmIsValidFormat
0x180002589  test    eax, eax
0x18000258b  jz      short loc_1800025A9
0x18000258d  mov     eax, 11Ch
0x180002592  mov     [r11+0Ch], ebx
0x180002596  cmp     [r11], eax
0x180002599  cmovb   eax, [r11]
0x18000259d  mov     [r11], eax
0x1800025a0  xor     eax, eax
0x1800025a2  mov     [r11+1Ch], ax
0x1800025a7  jmp     short loc_1800025AE
0x1800025a9  mov     eax, 200h
0x1800025ae  add     rsp, 20h
0x1800025b2  pop     rbx
0x1800025b3  retn
```
