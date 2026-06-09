# acmdFormatSuggest

- ea: `0x1800025f8`
- end: `0x1800027ba`
- name: `acmdFormatSuggest`
- size: `450`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800020b0`
- `0x18000494c`

## callees

- `0x1800025f8`
- `0x180002ccc`
- `0x180002d70`

## pseudocode

```c
__int64 __fastcall acmdFormatSuggest(__int64 a1, __int64 a2)
{
  int v2; // esi
  __int64 v4; // rdi
  __int64 v5; // rbx
  unsigned __int16 v6; // bp
  unsigned __int16 v7; // cx
  int v8; // edx
  unsigned __int16 v9; // bp
  unsigned int v10; // eax
  unsigned __int16 v11; // ax
  unsigned int v12; // r9d
  int v13; // ecx
  unsigned int v14; // edx
  unsigned int v15; // ecx

  v2 = *(_DWORD *)(a2 + 4);
  if ( (v2 & 0xF00000) != 0 )
    return 8;
  v4 = *(_QWORD *)(a2 + 8);
  v5 = *(_QWORD *)(a2 + 20);
  if ( *(_WORD *)v4 == 1 )
  {
    if ( (unsigned int)pcmIsValidFormat(*(_QWORD *)(a2 + 8)) )
    {
      if ( (v2 & 0x10000) != 0 )
      {
        if ( *(_WORD *)v5 != 17 )
          return 512;
      }
      else
      {
        *(_WORD *)v5 = 17;
      }
      if ( (v2 & 0x20000) != 0 )
      {
        v11 = *(_WORD *)(v5 + 2);
        if ( *(_WORD *)(v4 + 2) != v11 )
          return 512;
      }
      else
      {
        v11 = *(_WORD *)(v4 + 2);
        *(_WORD *)(v5 + 2) = v11;
      }
      if ( (v2 & 0x40000) != 0 )
      {
        v12 = *(_DWORD *)(v5 + 4);
        if ( *(_DWORD *)(v4 + 4) != v12 )
          return 512;
      }
      else
      {
        v12 = *(_DWORD *)(v4 + 4);
        *(_DWORD *)(v5 + 4) = v12;
      }
      if ( (v2 & 0x80000) != 0 )
      {
        if ( *(_WORD *)(v5 + 14) != 4 )
          return 512;
      }
      else
      {
        *(_WORD *)(v5 + 14) = 4;
      }
      v13 = v11 >> 1;
      if ( v12 <= 0x2B11 )
        LOWORD(v14) = 256 << v13;
      else
        v14 = (256 << v13) * (v12 / 0x2AF8);
      *(_WORD *)(v5 + 12) = v14;
      *(_WORD *)(v5 + 16) = 2;
      v15 = (unsigned __int16)(8 * ((unsigned int)(unsigned __int16)v14 - (4 << v13)) / (4 << v13) + 1);
      *(_WORD *)(v5 + 18) = v15;
      v10 = v12 * (unsigned __int16)v14 / v15;
      goto LABEL_44;
    }
    return 512;
  }
  v6 = 16;
  if ( *(_WORD *)v4 != 17 || !(unsigned int)imaadpcmIsValidFormat(*(_QWORD *)(a2 + 8)) )
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
    v7 = *(_WORD *)(v5 + 2);
    if ( *(_WORD *)(v4 + 2) != v7 )
      return 512;
  }
  else
  {
    v7 = *(_WORD *)(v4 + 2);
    *(_WORD *)(v5 + 2) = v7;
  }
  if ( (v2 & 0x40000) != 0 )
  {
    v8 = *(_DWORD *)(v5 + 4);
    if ( *(_DWORD *)(v4 + 4) != v8 )
      return 512;
  }
  else
  {
    v8 = *(_DWORD *)(v4 + 4);
    *(_DWORD *)(v5 + 4) = v8;
  }
  if ( (v2 & 0x80000) != 0 )
  {
    v6 = *(_WORD *)(v5 + 14);
    if ( ((v6 - 8) & 0xFFF7) == 0 )
      goto LABEL_22;
    return 512;
  }
  *(_WORD *)(v5 + 14) = 16;
LABEL_22:
  v9 = v6 >> 3 << (v7 >> 1);
  *(_WORD *)(v5 + 12) = v9;
  v10 = v8 * v9;
LABEL_44:
  *(_DWORD *)(v5 + 8) = v10;
  return 0;
}

```

## disassembly

```asm
0x1800025f8  push    rbx
0x1800025fa  push    rbp
0x1800025fb  push    rsi
0x1800025fc  push    rdi
0x1800025fd  sub     rsp, 28h
0x180002601  mov     esi, [rdx+4]
0x180002604  test    esi, 0F00000h
0x18000260a  jz      short loc_180002616
0x18000260c  mov     eax, 8
0x180002611  jmp     loc_1800027B1
0x180002616  mov     rdi, [rdx+8]
0x18000261a  mov     rbx, [rdx+14h]
0x18000261e  movzx   ecx, word ptr [rdi]
0x180002621  sub     ecx, 1
0x180002624  jz      loc_1800026D6
0x18000262a  mov     ebp, 10h
0x18000262f  cmp     ecx, ebp
0x180002631  jnz     loc_180002740
0x180002637  mov     rcx, rdi
0x18000263a  call    imaadpcmIsValidFormat
0x18000263f  test    eax, eax
0x180002641  jz      loc_180002740
0x180002647  bt      esi, 10h
0x18000264b  jnb     short loc_18000265B
0x18000264d  lea     ecx, [rbp-0Fh]
0x180002650  cmp     cx, [rbx]
0x180002653  jnz     loc_180002740
0x180002659  jmp     short loc_180002660
0x18000265b  mov     word ptr [rbx], 1
0x180002660  bt      esi, 11h
0x180002664  jnb     short loc_180002676
0x180002666  movzx   ecx, word ptr [rbx+2]
0x18000266a  cmp     [rdi+2], cx
0x18000266e  jnz     loc_180002740
0x180002674  jmp     short loc_18000267E
0x180002676  movzx   ecx, word ptr [rdi+2]
0x18000267a  mov     [rbx+2], cx
0x18000267e  bt      esi, 12h
0x180002682  jnb     short loc_180002692
0x180002684  mov     edx, [rbx+4]
0x180002687  cmp     [rdi+4], edx
0x18000268a  jnz     loc_180002740
0x180002690  jmp     short loc_180002698
0x180002692  mov     edx, [rdi+4]
0x180002695  mov     [rbx+4], edx
0x180002698  bt      esi, 13h
0x18000269c  jnb     short loc_1800026B7
0x18000269e  movzx   ebp, word ptr [rbx+0Eh]
0x1800026a2  mov     r8d, 0FFF7h
0x1800026a8  lea     eax, [rbp-8]
0x1800026ab  test    r8w, ax
0x1800026af  jnz     loc_180002740
0x1800026b5  jmp     short loc_1800026BB
0x1800026b7  mov     [rbx+0Eh], bp
0x1800026bb  shr     bp, 3
0x1800026bf  movzx   ecx, cx
0x1800026c2  shr     ecx, 1
0x1800026c4  shl     bp, cl
0x1800026c7  movzx   eax, bp
0x1800026ca  mov     [rbx+0Ch], ax
0x1800026ce  imul    eax, edx
0x1800026d1  jmp     loc_1800027AC
0x1800026d6  mov     rcx, rdi
0x1800026d9  call    pcmIsValidFormat
0x1800026de  test    eax, eax
0x1800026e0  jz      short loc_180002740
0x1800026e2  bt      esi, 10h
0x1800026e6  jnb     short loc_1800026F4
0x1800026e8  mov     eax, 11h
0x1800026ed  cmp     ax, [rbx]
0x1800026f0  jnz     short loc_180002740
0x1800026f2  jmp     short loc_1800026F9
0x1800026f4  mov     word ptr [rbx], 11h
0x1800026f9  bt      esi, 11h
0x1800026fd  jnb     short loc_18000270B
0x1800026ff  movzx   eax, word ptr [rbx+2]
0x180002703  cmp     [rdi+2], ax
0x180002707  jnz     short loc_180002740
0x180002709  jmp     short loc_180002713
0x18000270b  movzx   eax, word ptr [rdi+2]
0x18000270f  mov     [rbx+2], ax
0x180002713  bt      esi, 12h
0x180002717  jnb     short loc_180002725
0x180002719  mov     r9d, [rbx+4]
0x18000271d  cmp     [rdi+4], r9d
0x180002721  jnz     short loc_180002740
0x180002723  jmp     short loc_18000272D
0x180002725  mov     r9d, [rdi+4]
0x180002729  mov     [rbx+4], r9d
0x18000272d  mov     r10d, 4
0x180002733  bt      esi, 13h
0x180002737  jnb     short loc_180002747
0x180002739  cmp     r10w, [rbx+0Eh]
0x18000273e  jz      short loc_18000274C
0x180002740  mov     eax, 200h
0x180002745  jmp     short loc_1800027B1
0x180002747  mov     [rbx+0Eh], r10w
0x18000274c  movzx   ecx, ax
0x18000274f  mov     r8d, 100h
0x180002755  shr     ecx, 1
0x180002757  shl     r8d, cl
0x18000275a  cmp     r9d, 2B11h
0x180002761  jbe     short loc_180002774
0x180002763  mov     eax, 0BEA67251h
0x180002768  mul     r9d
0x18000276b  shr     edx, 0Dh
0x18000276e  imul    edx, r8d
0x180002772  jmp     short loc_180002777
0x180002774  mov     edx, r8d
0x180002777  movzx   r8d, dx
0x18000277b  xor     edx, edx
0x18000277d  shl     r10d, cl
0x180002780  mov     eax, r8d
0x180002783  sub     eax, r10d
0x180002786  mov     [rbx+0Ch], r8w
0x18000278b  shl     eax, 3
0x18000278e  div     r10d
0x180002791  imul    r8d, r9d
0x180002795  xor     edx, edx
0x180002797  inc     ax
0x18000279a  mov     word ptr [rbx+10h], 2
0x1800027a0  movzx   ecx, ax
0x1800027a3  mov     [rbx+12h], cx
0x1800027a7  mov     eax, r8d
0x1800027aa  div     ecx
0x1800027ac  mov     [rbx+8], eax
0x1800027af  xor     eax, eax
0x1800027b1  add     rsp, 28h
0x1800027b5  pop     rdi
0x1800027b6  pop     rsi
0x1800027b7  pop     rbp
0x1800027b8  pop     rbx
0x1800027b9  retn
```
