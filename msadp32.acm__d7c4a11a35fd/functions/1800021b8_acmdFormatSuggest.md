# acmdFormatSuggest

- ea: `0x1800021b8`
- end: `0x1800023c4`
- name: `acmdFormatSuggest`
- size: `524`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001cd0`

## callees

- `0x1800021b8`
- `0x1800028b8`
- `0x180002910`
- `0x180002988`

## pseudocode

```c
__int64 __fastcall acmdFormatSuggest(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v4; // rbx
  int v5; // r8d
  unsigned int v6; // ecx
  unsigned __int16 v7; // dx
  unsigned __int16 v8; // dx
  int IsValidFormat; // eax
  __int64 v10; // r9
  int v11; // ecx
  unsigned int v13; // r10d
  unsigned int v14; // eax
  unsigned int v15; // edx
  unsigned __int16 v16; // cx

  v2 = *(_QWORD *)(a2 + 8);
  v4 = *(_QWORD *)(a2 + 20);
  if ( *(_WORD *)v2 == 1 )
  {
    IsValidFormat = pcmIsValidFormat(v2);
    v10 = 0;
    if ( IsValidFormat )
    {
      v11 = *(_DWORD *)(a2 + 4);
      if ( ((v11 & 0x10000) == 0 || *(_WORD *)v4 == 2)
        && ((v11 & 0x20000) == 0 || *(_WORD *)(v2 + 2) == *(_WORD *)(v4 + 2))
        && ((v11 & 0x40000) == 0 || *(_DWORD *)(v2 + 4) == *(_DWORD *)(v4 + 4))
        && ((v11 & 0x80000) == 0 || *(_WORD *)(v4 + 14) == 4) )
      {
        *(_WORD *)v4 = 2;
        v13 = *(_DWORD *)(v2 + 4);
        *(_DWORD *)(v4 + 4) = v13;
        v14 = *(unsigned __int16 *)(v2 + 2);
        *(_WORD *)(v4 + 2) = v14;
        *(_WORD *)(v4 + 14) = 4;
        if ( v13 <= 0x2B11 )
          LOWORD(v15) = 256 << (v14 >> 1);
        else
          v15 = (256 << (v14 >> 1)) * (v13 / 0x2AF8);
        *(_WORD *)(v4 + 12) = v15;
        *(_WORD *)(v4 + 16) = 32;
        v16 = 8 * ((unsigned int)(unsigned __int16)v15 - (7 << (v14 >> 1))) / (4 << (v14 >> 1)) + 2;
        *(_WORD *)(v4 + 18) = v16;
        *(_WORD *)(v4 + 20) = 7;
        *(_DWORD *)(v4 + 8) = v13 * (unsigned __int16)v15 / v16;
        do
        {
          *(_WORD *)(v4 + 4 * v10 + 22) = gaiCoef1[v10];
          *(_WORD *)(v4 + 4 * v10 + 24) = gaiCoef2[v10];
          ++v10;
        }
        while ( v10 != 7 );
        return 0;
      }
    }
    return 512;
  }
  if ( *(_WORD *)v2 != 2
    || !(unsigned int)adpcmIsValidFormat(v2)
    || !(unsigned int)adpcmIsMagicFormat(v2)
    || (*(_DWORD *)(a2 + 4) & 0x10000) != 0 && *(_WORD *)v4 != 1
    || (*(_DWORD *)(a2 + 4) & 0x20000) != 0 && *(_WORD *)(v2 + 2) != *(_WORD *)(v4 + 2)
    || (*(_DWORD *)(a2 + 4) & 0x40000) != 0 && *(_DWORD *)(v2 + 4) != *(_DWORD *)(v4 + 4) )
  {
    return 512;
  }
  *(_WORD *)v4 = 1;
  v5 = *(_DWORD *)(v2 + 4);
  *(_DWORD *)(v4 + 4) = v5;
  v6 = *(unsigned __int16 *)(v2 + 2);
  *(_WORD *)(v4 + 2) = v6;
  if ( (*(_DWORD *)(a2 + 4) & 0x80000) != 0 )
  {
    v7 = *(_WORD *)(v4 + 14);
    if ( ((v7 - 8) & 0xFFF7) == 0 )
      goto LABEL_15;
    return 512;
  }
  v7 = 16;
  *(_WORD *)(v4 + 14) = 16;
LABEL_15:
  v8 = v7 >> 3 << (v6 >> 1);
  *(_WORD *)(v4 + 12) = v8;
  *(_DWORD *)(v4 + 8) = v5 * v8;
  return 0;
}

```

## disassembly

```asm
0x1800021b8  mov     [rsp+arg_0], rbx
0x1800021bd  mov     [rsp+arg_8], rsi
0x1800021c2  push    rdi
0x1800021c3  sub     rsp, 20h
0x1800021c7  mov     rdi, [rdx+8]
0x1800021cb  mov     rsi, rdx
0x1800021ce  mov     rbx, [rdx+14h]
0x1800021d2  movzx   ecx, word ptr [rdi]
0x1800021d5  sub     ecx, 1
0x1800021d8  jz      loc_1800022A0
0x1800021de  cmp     ecx, 1
0x1800021e1  jnz     loc_1800022F2
0x1800021e7  mov     rcx, rdi
0x1800021ea  call    adpcmIsValidFormat
0x1800021ef  test    eax, eax
0x1800021f1  jz      loc_1800022F2
0x1800021f7  mov     rcx, rdi
0x1800021fa  call    adpcmIsMagicFormat
0x1800021ff  test    eax, eax
0x180002201  jz      loc_1800022F2
0x180002207  test    dword ptr [rsi+4], 10000h
0x18000220e  mov     ecx, 1
0x180002213  jz      short loc_18000221E
0x180002215  cmp     [rbx], cx
0x180002218  jnz     loc_1800022F2
0x18000221e  test    dword ptr [rsi+4], 20000h
0x180002225  jz      short loc_180002235
0x180002227  movzx   eax, word ptr [rbx+2]
0x18000222b  cmp     [rdi+2], ax
0x18000222f  jnz     loc_1800022F2
0x180002235  test    dword ptr [rsi+4], 40000h
0x18000223c  jz      short loc_18000224A
0x18000223e  mov     eax, [rbx+4]
0x180002241  cmp     [rdi+4], eax
0x180002244  jnz     loc_1800022F2
0x18000224a  mov     [rbx], cx
0x18000224d  mov     r8d, [rdi+4]
0x180002251  mov     [rbx+4], r8d
0x180002255  movzx   ecx, word ptr [rdi+2]
0x180002259  mov     [rbx+2], cx
0x18000225d  test    dword ptr [rsi+4], 80000h
0x180002264  jz      short loc_18000227B
0x180002266  movzx   edx, word ptr [rbx+0Eh]
0x18000226a  mov     r9d, 0FFF7h
0x180002270  lea     eax, [rdx-8]
0x180002273  test    r9w, ax
0x180002277  jnz     short loc_1800022F2
0x180002279  jmp     short loc_180002284
0x18000227b  mov     edx, 10h
0x180002280  mov     [rbx+0Eh], dx
0x180002284  shr     ecx, 1
0x180002286  shr     dx, 3
0x18000228a  shl     dx, cl
0x18000228d  movzx   eax, dx
0x180002290  mov     [rbx+0Ch], ax
0x180002294  imul    eax, r8d
0x180002298  mov     [rbx+8], eax
0x18000229b  jmp     loc_1800023B2
0x1800022a0  mov     rcx, rdi
0x1800022a3  call    pcmIsValidFormat
0x1800022a8  xor     r9d, r9d
0x1800022ab  test    eax, eax
0x1800022ad  jz      short loc_1800022F2
0x1800022af  mov     ecx, [rsi+4]
0x1800022b2  lea     esi, [r9+2]
0x1800022b6  bt      ecx, 10h
0x1800022ba  jnb     short loc_1800022C1
0x1800022bc  cmp     [rbx], si
0x1800022bf  jnz     short loc_1800022F2
0x1800022c1  bt      ecx, 11h
0x1800022c5  jnb     short loc_1800022D1
0x1800022c7  movzx   eax, word ptr [rbx+2]
0x1800022cb  cmp     [rdi+2], ax
0x1800022cf  jnz     short loc_1800022F2
0x1800022d1  bt      ecx, 12h
0x1800022d5  jnb     short loc_1800022DF
0x1800022d7  mov     eax, [rbx+4]
0x1800022da  cmp     [rdi+4], eax
0x1800022dd  jnz     short loc_1800022F2
0x1800022df  mov     r11d, 4
0x1800022e5  bt      ecx, 13h
0x1800022e9  jnb     short loc_1800022FC
0x1800022eb  cmp     [rbx+0Eh], r11w
0x1800022f0  jz      short loc_1800022FC
0x1800022f2  mov     eax, 200h
0x1800022f7  jmp     loc_1800023B4
0x1800022fc  mov     [rbx], si
0x1800022ff  mov     r8d, 100h
0x180002305  mov     r10d, [rdi+4]
0x180002309  mov     [rbx+4], r10d
0x18000230d  movzx   eax, word ptr [rdi+2]
0x180002311  mov     ecx, eax
0x180002313  mov     [rbx+2], ax
0x180002317  shr     ecx, 1
0x180002319  shl     r8d, cl
0x18000231c  mov     [rbx+0Eh], r11w
0x180002321  cmp     r10d, 2B11h
0x180002328  jbe     short loc_18000233B
0x18000232a  mov     eax, 0BEA67251h
0x18000232f  mul     r10d
0x180002332  shr     edx, 0Dh
0x180002335  imul    edx, r8d
0x180002339  jmp     short loc_18000233E
0x18000233b  mov     edx, r8d
0x18000233e  movzx   r8d, dx
0x180002342  mov     edi, 7
0x180002347  shl     r11d, cl
0x18000234a  mov     edx, edi
0x18000234c  shl     edx, cl
0x18000234e  mov     eax, r8d
0x180002351  sub     eax, edx
0x180002353  mov     [rbx+0Ch], r8w
0x180002358  shl     eax, 3
0x18000235b  xor     edx, edx
0x18000235d  div     r11d
0x180002360  imul    r8d, r10d
0x180002364  xor     edx, edx
0x180002366  add     ax, si
0x180002369  mov     word ptr [rbx+10h], 20h ; ' '
0x18000236f  movzx   ecx, ax
0x180002372  mov     [rbx+12h], cx
0x180002376  mov     [rbx+14h], di
0x18000237a  mov     eax, r8d
0x18000237d  div     ecx
0x18000237f  lea     ecx, [rdi-6]
0x180002382  mov     [rbx+8], eax
0x180002385  lea     rdx, cs:180000000h
0x18000238c  movzx   eax, word ptr ds:rva gaiCoef1[rdx+r9*4]
0x180002395  mov     [rbx+r9*4+16h], ax
0x18000239b  movzx   eax, word ptr ds:rva gaiCoef2[rdx+r9*4]
0x1800023a4  mov     [rbx+r9*4+18h], ax
0x1800023aa  add     r9, rcx
0x1800023ad  cmp     r9, rdi
0x1800023b0  jnz     short loc_18000238C
0x1800023b2  xor     eax, eax
0x1800023b4  mov     rbx, [rsp+28h+arg_0]
0x1800023b9  mov     rsi, [rsp+28h+arg_8]
0x1800023be  add     rsp, 20h
0x1800023c2  pop     rdi
0x1800023c3  retn
```
