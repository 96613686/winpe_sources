# cjComputeGLYPHSET_MSFT_GENERAL(sfnt_mappingTable *,ulong,ulong * *,_CMAPINFO *)

- ea: `0x140071458`
- end: `0x1400716e8`
- name: `?cjComputeGLYPHSET_MSFT_GENERAL@@YAKPEAUsfnt_mappingTable@@KPEAPEAKPEAU_CMAPINFO@@@Z`
- size: `656`
- prototype: `unsigned int __fastcall(struct sfnt_mappingTable *, unsigned int, unsigned int **, struct _CMAPINFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a018`

## callees

- `0x140070dc8`
- `0x140071458`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1400716c3`
- `KERNEL32!GlobalFree` at `0x1400716c3`
- `KERNEL32!GlobalAlloc` at `0x14007154a`
- `KERNEL32!GlobalAlloc` at `0x14007154a`

## pseudocode

```c
__int64 __fastcall cjComputeGLYPHSET_MSFT_GENERAL(
        struct sfnt_mappingTable *a1,
        unsigned int a2,
        unsigned int **a3,
        struct _CMAPINFO *a4)
{
  unsigned int v5; // r9d
  __int64 v6; // r11
  unsigned __int16 *v7; // r10
  unsigned __int16 *v8; // r12
  unsigned __int16 *v9; // r8
  int v10; // edi
  unsigned __int16 *v11; // r13
  unsigned __int16 v12; // r11
  unsigned __int16 v13; // dx
  unsigned __int16 v14; // cx
  struct _MbcsToIndex *v15; // rdi
  int v16; // ecx
  unsigned __int16 v17; // bp
  unsigned __int16 v18; // r11
  unsigned __int16 v19; // r9
  unsigned __int16 v20; // r14
  unsigned __int16 v21; // r10
  unsigned __int16 v22; // ax
  unsigned int v23; // eax
  unsigned int GlyphSetFromMITable; // ebx
  unsigned __int16 *v26; // [rsp+20h] [rbp-68h]
  unsigned __int16 *v27; // [rsp+28h] [rbp-60h]
  unsigned __int16 *v28; // [rsp+30h] [rbp-58h]
  unsigned __int16 *v29; // [rsp+38h] [rbp-50h]
  int v30; // [rsp+90h] [rbp+8h]

  v5 = 0;
  v6 = (unsigned __int16)(*((unsigned __int8 *)a1 + 6) << 7) | (unsigned __int8)(*((_BYTE *)a1 + 7) >> 1);
  v7 = (unsigned __int16 *)((char *)a1 + 14);
  v8 = (unsigned __int16 *)((char *)a1 + 14);
  v26 = (unsigned __int16 *)((char *)a1 + 14);
  v9 = (unsigned __int16 *)((char *)a1 + 2 * (unsigned int)(v6 + 1) + 14);
  v27 = v9;
  v10 = v6 - 1;
  v28 = &v9[v6];
  v30 = v10;
  v11 = v9;
  v29 = &v9[(unsigned int)(2 * v6)];
  v12 = 0;
  if ( v10 <= 0 )
    goto LABEL_23;
  do
  {
    v13 = _byteswap_ushort(*v9);
    v14 = _byteswap_ushort(*v7);
    if ( v14 >= v13 && v13 != 0xFFFF )
      v5 += v14 - v13 + 1;
    ++v12;
    ++v7;
    ++v9;
  }
  while ( v12 < v10 );
  if ( v5 - 1 <= 0xFFFE && (v15 = (struct _MbcsToIndex *)GlobalAlloc(0, 8LL * v5)) != 0 )
  {
    v16 = v30;
    v17 = 0;
    v18 = 0;
    do
    {
      v19 = _byteswap_ushort(*v11);
      v20 = _byteswap_ushort(*v8);
      if ( v20 >= v19 && v19 != 0xFFFF )
      {
        v21 = v19;
        do
        {
          v22 = v21;
          *((_DWORD *)v15 + 2 * v17) = 0;
          if ( v19 > 0xFFu )
            v22 = __ROR2__(v21, 8);
          *((_WORD *)v15 + 4 * v17) = v22;
          if ( v29[v18] )
            v23 = (unsigned __int16)(_byteswap_ushort(v29[v18
                                                        + (((unsigned __int64)HIBYTE(v29[v18]) >> 1)
                                                         | ((unsigned __int64)LOBYTE(v29[v18]) << 7))
                                                        - v19
                                                        + v21])
                                   + _byteswap_ushort(v28[v18]));
          else
            v23 = (unsigned __int16)(v21 + _byteswap_ushort(v28[v18]));
          *((_DWORD *)v15 + 2 * v17 + 1) = v23;
          if ( v23 >= a2 )
            *((_DWORD *)v15 + 2 * v17 + 1) = 0;
          ++v17;
          ++v21;
        }
        while ( v21 <= v20 );
        v8 = v26;
        v11 = v27;
        v16 = v30;
      }
      ++v18;
      ++v8;
      ++v11;
      v26 = v8;
      v27 = v11;
    }
    while ( v18 < v16 );
    GlyphSetFromMITable = CreateGlyphSetFromMITable(a4, v15, v17, a3);
    GlobalFree(v15);
    return GlyphSetFromMITable;
  }
  else
  {
LABEL_23:
    if ( a3 )
      *a3 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x140071458  mov     [rsp+arg_18], r9
0x14007145d  mov     [rsp+arg_10], r8
0x140071462  mov     [rsp+arg_8], edx
0x140071466  push    rbx
0x140071467  push    rbp
0x140071468  push    rsi
0x140071469  push    rdi
0x14007146a  push    r12
0x14007146c  push    r13
0x14007146e  push    r14
0x140071470  push    r15
0x140071472  sub     rsp, 48h
0x140071476  mov     al, [rcx+7]
0x140071479  xor     esi, esi
0x14007147b  shr     al, 1
0x14007147d  mov     rbx, r8
0x140071480  movzx   r10d, al
0x140071484  mov     r9d, esi
0x140071487  movzx   eax, byte ptr [rcx+6]
0x14007148b  shl     ax, 7
0x14007148f  or      r10w, ax
0x140071493  movzx   r11d, r10w
0x140071497  lea     r10, [rcx+0Eh]
0x14007149b  mov     r12, r10
0x14007149e  mov     [rsp+88h+var_68], r10
0x1400714a3  lea     eax, [r11+1]
0x1400714a7  lea     r8, [r10+rax*2]
0x1400714ab  lea     rax, [r8+r11*2]
0x1400714af  mov     [rsp+88h+var_60], r8
0x1400714b4  lea     edi, [r11-1]
0x1400714b8  mov     [rsp+88h+var_58], rax
0x1400714bd  mov     [rsp+88h+arg_0], edi
0x1400714c4  lea     eax, [r11+r11]
0x1400714c8  lea     rax, [r8+rax*2]
0x1400714cc  mov     r13, r8
0x1400714cf  mov     [rsp+88h+var_50], rax
0x1400714d4  mov     r11d, esi
0x1400714d7  test    edi, edi
0x1400714d9  jle     loc_1400716CD
0x1400714df  mov     r15d, 0FFFFh
0x1400714e5  movzx   eax, byte ptr [r8+1]
0x1400714ea  movzx   edx, byte ptr [r8]
0x1400714ee  movzx   ecx, byte ptr [r10+1]
0x1400714f3  shl     dx, 8
0x1400714f7  or      dx, ax
0x1400714fa  movzx   eax, byte ptr [r10]
0x1400714fe  shl     ax, 8
0x140071502  or      cx, ax
0x140071505  cmp     cx, dx
0x140071508  jb      short loc_14007151E
0x14007150a  cmp     dx, r15w
0x14007150e  jz      short loc_14007151E
0x140071510  movzx   ecx, cx
0x140071513  inc     r9d
0x140071516  movzx   eax, dx
0x140071519  sub     ecx, eax
0x14007151b  add     r9d, ecx
0x14007151e  inc     r11w
0x140071522  add     r10, 2
0x140071526  movzx   eax, r11w
0x14007152a  add     r8, 2
0x14007152e  cmp     eax, edi
0x140071530  jl      short loc_1400714E5
0x140071532  lea     eax, [r9-1]
0x140071536  cmp     eax, 0FFFEh
0x14007153b  ja      loc_1400716CD
0x140071541  mov     edx, r9d
0x140071544  xor     ecx, ecx; uFlags
0x140071546  shl     rdx, 3; dwBytes
0x14007154a  call    cs:__imp_GlobalAlloc
0x140071550  mov     rdi, rax
0x140071553  test    rax, rax
0x140071556  jz      loc_1400716CD
0x14007155c  mov     ecx, [rsp+88h+arg_0]
0x140071563  mov     ebp, esi
0x140071565  mov     r11d, esi
0x140071568  movzx   eax, byte ptr [r13+1]
0x14007156d  movzx   r9d, byte ptr [r13+0]
0x140071572  movzx   r14d, byte ptr [r12+1]
0x140071578  shl     r9w, 8
0x14007157d  or      r9w, ax
0x140071581  movzx   eax, byte ptr [r12]
0x140071586  shl     ax, 8
0x14007158a  or      r14w, ax
0x14007158e  movzx   ebx, r9w
0x140071592  cmp     r14w, r9w
0x140071596  jb      loc_140071680
0x14007159c  cmp     r9w, r15w
0x1400715a0  jz      loc_140071680
0x1400715a6  mov     r13, [rsp+88h+var_58]
0x1400715ab  movzx   r10d, r9w
0x1400715af  mov     r12, [rsp+88h+var_50]
0x1400715b4  xor     edx, edx
0x1400715b6  movzx   r15d, r11w
0x1400715ba  mov     eax, 0FFh
0x1400715bf  movzx   esi, bp
0x1400715c2  cmp     r9w, ax
0x1400715c6  movzx   eax, r10w
0x1400715ca  mov     [rdi+rsi*8], edx
0x1400715cd  jbe     short loc_1400715D3
0x1400715cf  ror     ax, 8
0x1400715d3  mov     [rdi+rsi*8], ax
0x1400715d7  cmp     [r12+r15*2], dx
0x1400715dc  jnz     short loc_1400715FA
0x1400715de  movzx   eax, byte ptr [r13+r15*2+0]
0x1400715e4  movzx   ecx, byte ptr [r13+r15*2+1]
0x1400715ea  shl     ax, 8
0x1400715ee  or      cx, ax
0x1400715f1  add     cx, r10w
0x1400715f5  movzx   eax, cx
0x1400715f8  jmp     short loc_140071647
0x1400715fa  movzx   ecx, byte ptr [r12+r15*2+1]
0x140071600  movzx   eax, byte ptr [r12+r15*2]
0x140071605  movzx   r8d, byte ptr [r13+r15*2+1]
0x14007160b  shl     rax, 7
0x14007160f  shr     rcx, 1
0x140071612  or      rax, rcx
0x140071615  movzx   edx, r10w
0x140071619  sub     rax, rbx
0x14007161c  add     rax, r15
0x14007161f  add     rdx, rax
0x140071622  movzx   eax, byte ptr [r13+r15*2+0]
0x140071628  shl     eax, 8
0x14007162b  or      r8d, eax
0x14007162e  movzx   eax, byte ptr [r12+rdx*2]
0x140071633  movzx   ecx, byte ptr [r12+rdx*2+1]
0x140071639  shl     eax, 8
0x14007163c  or      ecx, eax
0x14007163e  add     r8d, ecx
0x140071641  movzx   eax, r8w
0x140071645  xor     edx, edx
0x140071647  mov     [rdi+rsi*8+4], eax
0x14007164b  cmp     eax, [rsp+88h+arg_8]
0x140071652  jb      short loc_140071658
0x140071654  mov     [rdi+rsi*8+4], edx
0x140071658  inc     bp
0x14007165b  inc     r10w
0x14007165f  cmp     r10w, r14w
0x140071663  jbe     loc_1400715BA
0x140071669  mov     r12, [rsp+88h+var_68]
0x14007166e  mov     r15d, 0FFFFh
0x140071674  mov     r13, [rsp+88h+var_60]
0x140071679  mov     ecx, [rsp+88h+arg_0]
0x140071680  inc     r11w
0x140071684  add     r12, 2
0x140071688  add     r13, 2
0x14007168c  movzx   eax, r11w
0x140071690  mov     [rsp+88h+var_68], r12
0x140071695  mov     [rsp+88h+var_60], r13
0x14007169a  cmp     eax, ecx
0x14007169c  jl      loc_140071568
0x1400716a2  mov     r9, [rsp+88h+arg_10]; unsigned int **
0x1400716aa  movzx   r8d, bp; unsigned __int16
0x1400716ae  mov     rcx, [rsp+88h+arg_18]; struct _CMAPINFO *
0x1400716b6  mov     rdx, rdi; struct _MbcsToIndex *
0x1400716b9  call    ?CreateGlyphSetFromMITable@@YAKPEAU_CMAPINFO@@PEAU_MbcsToIndex@@GPEAPEAK@Z; CreateGlyphSetFromMITable(_CMAPINFO *,_MbcsToIndex *,ushort,ulong * *)
0x1400716be  mov     rcx, rdi; hMem
0x1400716c1  mov     ebx, eax
0x1400716c3  call    cs:__imp_GlobalFree
0x1400716c9  mov     eax, ebx
0x1400716cb  jmp     short loc_1400716D7
0x1400716cd  test    rbx, rbx
0x1400716d0  jz      short loc_1400716D5
0x1400716d2  mov     [rbx], rsi
0x1400716d5  xor     eax, eax
0x1400716d7  add     rsp, 48h
0x1400716db  pop     r15
0x1400716dd  pop     r14
0x1400716df  pop     r13
0x1400716e1  pop     r12
0x1400716e3  pop     rdi
0x1400716e4  pop     rsi
0x1400716e5  pop     rbp
0x1400716e6  pop     rbx
0x1400716e7  retn
```
