# cjComputeGLYPHSET_HIGH_BYTE(sfnt_mappingTable *,ulong * *,_CMAPINFO *)

- ea: `0x1400711f0`
- end: `0x140071450`
- name: `?cjComputeGLYPHSET_HIGH_BYTE@@YAKPEAUsfnt_mappingTable@@PEAPEAKPEAU_CMAPINFO@@@Z`
- size: `608`
- prototype: `unsigned int __fastcall(struct sfnt_mappingTable *, unsigned int **, struct _CMAPINFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a018`

## callees

- `0x140070dc8`
- `0x1400711f0`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x140071428`
- `KERNEL32!GlobalFree` at `0x140071428`
- `KERNEL32!GlobalAlloc` at `0x140071285`
- `KERNEL32!GlobalAlloc` at `0x140071285`

## pseudocode

```c
__int64 __fastcall cjComputeGLYPHSET_HIGH_BYTE(struct sfnt_mappingTable *a1, unsigned int **a2, struct _CMAPINFO *a3)
{
  int v5; // r9d
  __int64 i; // r10
  unsigned __int16 v7; // cx
  struct _MbcsToIndex *v8; // rdi
  unsigned __int16 v9; // r10
  unsigned __int16 v10; // r9
  __int64 v11; // r8
  __int64 v12; // rdx
  char *v13; // rax
  int v14; // ecx
  __int64 v15; // rax
  unsigned __int16 j; // r9
  unsigned __int16 v17; // cx
  char *v18; // rdx
  int v19; // r12d
  int v20; // r13d
  __int64 v21; // r8
  char *v22; // rbp
  __int64 v23; // r15
  unsigned int k; // r14d
  int v25; // r11d
  __int64 v26; // rdx
  unsigned int GlyphSetFromMITable; // ebx

  v5 = (*((unsigned __int8 *)a1 + 520) << 8) | *((unsigned __int8 *)a1 + 521);
  for ( i = 0; i != 256; ++i )
  {
    v7 = _byteswap_ushort(*((_WORD *)a1 + i + 3));
    if ( v7 )
      v5 += (*((unsigned __int8 *)a1 + v7 + 520) << 8) | *((unsigned __int8 *)a1 + v7 + 521);
  }
  if ( (unsigned int)(v5 - 1) <= 0xFFFE && (v8 = (struct _MbcsToIndex *)GlobalAlloc(0, (unsigned int)(8 * v5))) != 0 )
  {
    v9 = 0;
    v10 = 0;
    v11 = 0;
    do
    {
      if ( !_byteswap_ushort(*((_WORD *)a1 + v11 + 3)) )
      {
        v12 = v11 - (*((unsigned __int8 *)a1 + 519) | ((unsigned __int64)*((unsigned __int8 *)a1 + 518) << 8));
        v13 = (char *)a1 + (*((unsigned __int8 *)a1 + 525) | ((unsigned __int64)*((unsigned __int8 *)a1 + 524) << 8));
        v14 = (unsigned __int8)v13[2 * v12 + 525] | ((unsigned __int8)v13[2 * v12 + 524] << 8);
        if ( v14 )
        {
          v15 = v9++;
          *((_BYTE *)v8 + 8 * v15) = v10;
          *((_BYTE *)v8 + 8 * v15 + 1) = 0;
          *((_DWORD *)v8 + 2 * v15 + 1) = v14;
        }
      }
      ++v10;
      ++v11;
    }
    while ( v10 < 0x100u );
    for ( j = 0; j < 0x100u; ++j )
    {
      v17 = _byteswap_ushort(*((_WORD *)a1 + j + 3));
      if ( v17 )
      {
        v18 = (char *)a1 + v17 + 518;
        v19 = (unsigned __int8)v18[5];
        v20 = (unsigned __int8)v18[4];
        v21 = _byteswap_ushort(*(_WORD *)v18);
        v22 = &v18[((unsigned __int64)(unsigned __int8)v18[6] << 8) | (unsigned __int8)v18[7]];
        v23 = v21;
        for ( k = v21 + (((unsigned __int8)v18[2] << 8) | (unsigned __int8)v18[3]);
              (unsigned __int16)v21 < k;
              LOWORD(v21) = v21 + 1 )
        {
          v25 = ((unsigned __int8)v22[2 * ((unsigned __int16)v21 - v23) + 6] << 8)
              | (unsigned __int8)v22[2 * ((unsigned __int16)v21 - v23) + 7];
          if ( v25 )
          {
            v26 = v9;
            *((_BYTE *)v8 + 8 * v9++) = j;
            *((_BYTE *)v8 + 8 * v26 + 1) = v21;
            *((_BYTE *)v8 + 8 * v26 + 2) = 0;
            *((_DWORD *)v8 + 2 * v26 + 1) = v25 + (v19 | (v20 << 8));
          }
        }
      }
    }
    GlyphSetFromMITable = CreateGlyphSetFromMITable(a3, v8, v9, a2);
    GlobalFree(v8);
    return GlyphSetFromMITable;
  }
  else
  {
    *a2 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x1400711f0  mov     [rsp+arg_0], rbx
0x1400711f5  mov     [rsp+arg_10], r8
0x1400711fa  mov     [rsp+arg_8], rdx
0x1400711ff  push    rbp
0x140071200  push    rsi
0x140071201  push    rdi
0x140071202  push    r12
0x140071204  push    r13
0x140071206  push    r14
0x140071208  push    r15
0x14007120a  sub     rsp, 20h
0x14007120e  movzx   eax, byte ptr [rcx+208h]
0x140071215  mov     rsi, rdx
0x140071218  movzx   r9d, byte ptr [rcx+209h]
0x140071220  mov     rbx, rcx
0x140071223  shl     eax, 8
0x140071226  or      r9d, eax
0x140071229  xor     r10d, r10d
0x14007122c  lea     ebp, [r10+1]
0x140071230  movzx   ecx, byte ptr [rbx+r10*2+6]
0x140071236  movzx   eax, byte ptr [rbx+r10*2+7]
0x14007123c  shl     cx, 8
0x140071240  or      cx, ax
0x140071243  jz      short loc_140071260
0x140071245  movzx   eax, cx
0x140071248  movzx   ecx, byte ptr [rax+rbx+209h]
0x140071250  movzx   eax, byte ptr [rax+rbx+208h]
0x140071258  shl     eax, 8
0x14007125b  or      ecx, eax
0x14007125d  add     r9d, ecx
0x140071260  add     r10, rbp
0x140071263  cmp     r10, 100h
0x14007126a  jnz     short loc_140071230
0x14007126c  lea     eax, [r9-1]
0x140071270  cmp     eax, 0FFFEh
0x140071275  ja      loc_140071432
0x14007127b  lea     edx, ds:0[r9*8]; dwBytes
0x140071283  xor     ecx, ecx; uFlags
0x140071285  call    cs:__imp_GlobalAlloc
0x14007128b  mov     rdi, rax
0x14007128e  test    rax, rax
0x140071291  jz      loc_140071432
0x140071297  xor     r10d, r10d
0x14007129a  xor     r9d, r9d
0x14007129d  xor     r8d, r8d
0x1400712a0  mov     r11d, 100h
0x1400712a6  movzx   ecx, byte ptr [rbx+r8*2+6]
0x1400712ac  movzx   edx, byte ptr [rbx+r8*2+7]
0x1400712b2  shl     cx, 8
0x1400712b6  or      dx, cx
0x1400712b9  jnz     short loc_14007131A
0x1400712bb  movzx   eax, byte ptr [rbx+207h]
0x1400712c2  mov     rdx, r8
0x1400712c5  movzx   ecx, byte ptr [rbx+206h]
0x1400712cc  shl     rcx, 8
0x1400712d0  or      rcx, rax
0x1400712d3  movzx   eax, byte ptr [rbx+20Ch]
0x1400712da  sub     rdx, rcx
0x1400712dd  shl     rax, 8
0x1400712e1  movzx   ecx, byte ptr [rbx+20Dh]
0x1400712e8  or      rax, rcx
0x1400712eb  add     rax, rbx
0x1400712ee  movzx   ecx, byte ptr [rax+rdx*2+20Ch]
0x1400712f6  movzx   eax, byte ptr [rax+rdx*2+20Dh]
0x1400712fe  shl     ecx, 8
0x140071301  or      ecx, eax
0x140071303  jz      short loc_14007131A
0x140071305  movzx   eax, r10w
0x140071309  add     r10w, bp
0x14007130d  mov     [rdi+rax*8], r9b
0x140071311  mov     byte ptr [rdi+rax*8+1], 0
0x140071316  mov     [rdi+rax*8+4], ecx
0x14007131a  add     r9w, bp
0x14007131e  add     r8, rbp
0x140071321  cmp     r9w, r11w
0x140071325  jb      loc_1400712A6
0x14007132b  xor     r9d, r9d
0x14007132e  movzx   eax, r9w
0x140071332  movzx   ecx, byte ptr [rbx+rax*2+7]
0x140071337  movzx   eax, byte ptr [rbx+rax*2+6]
0x14007133c  shl     ax, 8
0x140071340  or      cx, ax
0x140071343  jz      loc_1400713FA
0x140071349  movzx   edx, cx
0x14007134c  add     rdx, 206h
0x140071353  add     rdx, rbx
0x140071356  movzx   eax, byte ptr [rdx]
0x140071359  movzx   ecx, byte ptr [rdx+1]
0x14007135d  movzx   ebp, byte ptr [rdx+7]
0x140071361  movzx   r14d, byte ptr [rdx+3]
0x140071366  movzx   r12d, byte ptr [rdx+5]
0x14007136b  movzx   r13d, byte ptr [rdx+4]
0x140071370  shl     ax, 8
0x140071374  or      cx, ax
0x140071377  movzx   eax, byte ptr [rdx+6]
0x14007137b  shl     rax, 8
0x14007137f  or      rbp, rax
0x140071382  movzx   r8d, cx
0x140071386  movzx   eax, byte ptr [rdx+2]
0x14007138a  add     rbp, rdx
0x14007138d  shl     eax, 8
0x140071390  mov     r15d, r8d
0x140071393  or      r14d, eax
0x140071396  add     r14d, r8d
0x140071399  cmp     r8d, r14d
0x14007139c  jnb     short loc_1400713F5
0x14007139e  mov     esi, 1
0x1400713a3  movzx   ecx, r8w
0x1400713a7  sub     rcx, r15
0x1400713aa  movzx   eax, byte ptr [rbp+rcx*2+6]
0x1400713af  movzx   r11d, byte ptr [rbp+rcx*2+7]
0x1400713b5  shl     eax, 8
0x1400713b8  or      r11d, eax
0x1400713bb  jz      short loc_1400713E3
0x1400713bd  movzx   edx, r10w
0x1400713c1  mov     ecx, r13d
0x1400713c4  shl     ecx, 8
0x1400713c7  or      ecx, r12d
0x1400713ca  add     ecx, r11d
0x1400713cd  mov     [rdi+rdx*8], r9b
0x1400713d1  add     r10w, si
0x1400713d5  mov     [rdi+rdx*8+1], r8b
0x1400713da  mov     byte ptr [rdi+rdx*8+2], 0
0x1400713df  mov     [rdi+rdx*8+4], ecx
0x1400713e3  add     r8w, si
0x1400713e7  movzx   eax, r8w
0x1400713eb  cmp     eax, r14d
0x1400713ee  jb      short loc_1400713A3
0x1400713f0  mov     rbp, rsi
0x1400713f3  jmp     short loc_1400713FA
0x1400713f5  mov     ebp, 1
0x1400713fa  add     r9w, bp
0x1400713fe  mov     eax, 100h
0x140071403  cmp     r9w, ax
0x140071407  jb      loc_14007132E
0x14007140d  mov     r9, [rsp+58h+arg_8]; unsigned int **
0x140071412  movzx   r8d, r10w; unsigned __int16
0x140071416  mov     rcx, [rsp+58h+arg_10]; struct _CMAPINFO *
0x14007141b  mov     rdx, rdi; struct _MbcsToIndex *
0x14007141e  call    ?CreateGlyphSetFromMITable@@YAKPEAU_CMAPINFO@@PEAU_MbcsToIndex@@GPEAPEAK@Z; CreateGlyphSetFromMITable(_CMAPINFO *,_MbcsToIndex *,ushort,ulong * *)
0x140071423  mov     rcx, rdi; hMem
0x140071426  mov     ebx, eax
0x140071428  call    cs:__imp_GlobalFree
0x14007142e  mov     eax, ebx
0x140071430  jmp     short loc_14007143B
0x140071432  mov     qword ptr [rsi], 0
0x140071439  xor     eax, eax
0x14007143b  mov     rbx, [rsp+58h+arg_0]
0x140071440  add     rsp, 20h
0x140071444  pop     r15
0x140071446  pop     r14
0x140071448  pop     r13
0x14007144a  pop     r12
0x14007144c  pop     rdi
0x14007144d  pop     rsi
0x14007144e  pop     rbp
0x14007144f  retn
```
