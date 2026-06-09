# vCopyClearTypeBits(_TT_FONTCONTEXT *,_GLYPHBITS *,uchar *,_GMC *,ushort,ushort)

- ea: `0x140043730`
- end: `0x140043932`
- name: `?vCopyClearTypeBits@@YAXPEAU_TT_FONTCONTEXT@@PEAU_GLYPHBITS@@PEAEPEAU_GMC@@GG@Z`
- size: `514`
- prototype: `void __fastcall(struct _TT_FONTCONTEXT *, struct _GLYPHBITS *, unsigned __int8 *, struct _GMC *, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140015d80`

## callees

- `0x140043730`
- `0x14007680c`

## pseudocode

```c
void __fastcall vCopyClearTypeBits(
        struct _TT_FONTCONTEXT *a1,
        struct _GLYPHBITS *a2,
        unsigned __int8 *a3,
        struct _GMC *a4,
        unsigned __int16 a5,
        unsigned __int16 a6)
{
  size_t v6; // rbp
  unsigned __int16 v8; // si
  struct _GLYPHBITS *v9; // r15
  BYTE *i; // rbx
  unsigned int v12; // r10d
  int v13; // r14d
  unsigned __int16 v14; // r8
  BYTE *aj; // rcx
  __int64 v16; // r11
  unsigned __int8 *v17; // r11
  LONG v18; // eax
  BYTE *v19; // r8
  __int64 v20; // r15
  __int64 v21; // r14
  unsigned __int8 *v22; // r10
  BYTE v23; // al
  int v24; // eax
  unsigned int v25; // edi
  unsigned int v26; // esi
  int v27; // r11d
  int v28; // ecx

  v6 = *((unsigned int *)a4 + 4);
  v8 = a6;
  v9 = a2;
  i = 0;
  v12 = 4
      * ((unsigned int)(((*((_DWORD *)a1 + 10) & 0x10000) != 0 ? 8 : 1)
                      * (*((_DWORD *)a4 + 2) + v6 + *((_DWORD *)a4 + 3))
                      + 31) >> 5);
  v13 = *((_DWORD *)a1 + 10) & 0x20000000;
  if ( v13 && *((_DWORD *)a4 + 1) )
  {
    v27 = (a5 - a6) % 5;
    if ( !(_WORD)v27 )
      LOWORD(v27) = 5;
    v14 = 5 - 5 * *((_WORD *)a4 + 2) - v27 + a5;
  }
  else
  {
    v14 = a5;
  }
  if ( *(_DWORD *)a4 )
  {
    if ( v13 )
    {
      v8 = 5;
      v28 = (unsigned __int16)(a6 + 5 * *(_WORD *)a4 - 5);
      a3 += v12 * v28;
      v14 -= v28;
    }
    else
    {
      a3 += *(_DWORD *)a4 * v12;
    }
  }
  aj = a2->aj;
  v16 = *((unsigned int *)a4 + 2);
  LOWORD(a2) = 5 * *((_WORD *)a4 + 10);
  v9->sizlBitmap.cx = v6;
  if ( (unsigned __int16)a2 >= v14 )
    LOWORD(a2) = v14;
  v17 = &a3[v16];
  if ( (*((_DWORD *)a1 + 10) & 0x20000000) != 0 )
  {
    LODWORD(a2) = (unsigned __int16)a2;
    v18 = v8;
  }
  else
  {
    LODWORD(a2) = *((_DWORD *)a4 + 5);
    v18 = (int)a2;
  }
  v9->sizlBitmap.cy = v18;
  v19 = &aj[(unsigned int)((_DWORD)a2 * v6)];
  if ( aj < v19 )
  {
    v20 = *((unsigned int *)a4 + 4);
    v21 = v12;
    do
    {
      v22 = v17;
      for ( i = aj; i < &aj[v20]; ++i )
      {
        v23 = *v22++;
        *i = v23;
      }
      aj += v6;
      v17 += v21;
    }
    while ( aj < v19 );
  }
  if ( (*((_DWORD *)a1 + 10) & 0x20000000) != 0 && (unsigned int)a2 < (unsigned __int16)(5 * *((_WORD *)a4 + 10)) )
  {
    v24 = *((_DWORD *)a4 + 5);
    v25 = 0;
    v26 = 5 * v24 - (_DWORD)a2;
    if ( 5 * v24 != (_DWORD)a2 )
    {
      do
      {
        memset_0(i, 0, v6);
        i += v6;
        ++v25;
      }
      while ( v25 < v26 );
    }
  }
}

```

## disassembly

```asm
0x140043730  push    rbx
0x140043732  push    rbp
0x140043733  push    rsi
0x140043734  push    rdi
0x140043735  push    r12
0x140043737  push    r13
0x140043739  push    r14
0x14004373b  push    r15
0x14004373d  sub     rsp, 28h
0x140043741  mov     r14d, [rcx+28h]
0x140043745  xor     r12d, r12d
0x140043748  mov     ebp, [r9+10h]
0x14004374c  mov     r13, rcx
0x14004374f  mov     r10d, [r9+0Ch]
0x140043753  mov     eax, r14d
0x140043756  movzx   esi, [rsp+68h+arg_28]
0x14004375e  add     r10d, ebp
0x140043761  add     r10d, [r9+8]
0x140043765  and     eax, 10000h
0x14004376a  neg     eax
0x14004376c  mov     r15, rdx
0x14004376f  mov     rdi, r8
0x140043772  lea     edx, [r12+5]
0x140043777  sbb     ecx, ecx
0x140043779  mov     ebx, r12d
0x14004377c  and     ecx, 7
0x14004377f  inc     ecx
0x140043781  imul    r10d, ecx
0x140043785  add     r10d, 1Fh
0x140043789  shr     r10d, 5
0x14004378d  shl     r10d, 2
0x140043791  and     r14d, 20000000h
0x140043798  jnz     loc_140043891
0x14004379e  movzx   r8d, [rsp+68h+arg_20]
0x1400437a7  cmp     [r9], r12d
0x1400437aa  jnz     loc_1400438ED
0x1400437b0  movzx   edx, word ptr [r9+14h]
0x1400437b5  lea     rcx, [r15+10h]
0x1400437b9  mov     r11d, [r9+8]
0x1400437bd  movzx   eax, dx
0x1400437c0  shl     ax, 2
0x1400437c4  add     dx, ax
0x1400437c7  mov     [r15+8], ebp
0x1400437cb  cmp     dx, r8w
0x1400437cf  cmovnb  dx, r8w
0x1400437d4  add     r11, rdi
0x1400437d7  test    dword ptr [r13+28h], 20000000h
0x1400437df  jnz     loc_140043886
0x1400437e5  mov     edx, [r9+14h]
0x1400437e9  mov     eax, edx
0x1400437eb  mov     r8d, ebp
0x1400437ee  mov     [r15+0Ch], eax
0x1400437f2  imul    r8d, edx
0x1400437f6  add     r8, rcx
0x1400437f9  cmp     rcx, r8
0x1400437fc  jnb     short loc_14004382F
0x1400437fe  mov     r15d, [r9+10h]
0x140043802  mov     r14d, r10d
0x140043805  lea     rdi, [r15+rcx]
0x140043809  mov     r10, r11
0x14004380c  mov     rbx, rcx
0x14004380f  cmp     rcx, rdi
0x140043812  jnb     short loc_140043824
0x140043814  mov     al, [r10]
0x140043817  inc     r10
0x14004381a  mov     [rbx], al
0x14004381c  inc     rbx
0x14004381f  cmp     rbx, rdi
0x140043822  jb      short loc_140043814
0x140043824  add     rcx, rbp
0x140043827  add     r11, r14
0x14004382a  cmp     rcx, r8
0x14004382d  jb      short loc_140043805
0x14004382f  test    dword ptr [r13+28h], 20000000h
0x140043837  jnz     short loc_14004384A
0x140043839  add     rsp, 28h
0x14004383d  pop     r15
0x14004383f  pop     r14
0x140043841  pop     r13
0x140043843  pop     r12
0x140043845  pop     rdi
0x140043846  pop     rsi
0x140043847  pop     rbp
0x140043848  pop     rbx
0x140043849  retn
0x14004384a  movzx   ecx, word ptr [r9+14h]
0x14004384f  movzx   eax, cx
0x140043852  shl     ax, 2
0x140043856  add     cx, ax
0x140043859  movzx   eax, cx
0x14004385c  cmp     edx, eax
0x14004385e  jnb     short loc_140043839
0x140043860  mov     eax, [r9+14h]
0x140043864  mov     edi, r12d
0x140043867  lea     esi, [rax+rax*4]
0x14004386a  sub     esi, edx
0x14004386c  jz      short loc_140043839
0x14004386e  mov     r8, rbp; Size
0x140043871  xor     edx, edx; Val
0x140043873  mov     rcx, rbx; void *
0x140043876  call    memset_0
0x14004387b  add     rbx, rbp
0x14004387e  inc     edi
0x140043880  cmp     edi, esi
0x140043882  jb      short loc_14004386E
0x140043884  jmp     short loc_140043839
0x140043886  movzx   edx, dx
0x140043889  movzx   eax, si
0x14004388c  jmp     loc_1400437EB
0x140043891  cmp     [r9+4], r12d
0x140043895  jz      loc_14004379E
0x14004389b  movzx   r8d, [rsp+68h+arg_20]
0x1400438a4  mov     eax, 66666667h
0x1400438a9  mov     r11d, r8d
0x1400438ac  sub     r11d, esi
0x1400438af  imul    r11d
0x1400438b2  sar     edx, 1
0x1400438b4  mov     eax, edx
0x1400438b6  shr     eax, 1Fh
0x1400438b9  add     edx, eax
0x1400438bb  lea     eax, [rdx+rdx*4]
0x1400438be  mov     edx, 5
0x1400438c3  sub     r11d, eax
0x1400438c6  test    r11w, r11w
0x1400438ca  jz      short loc_14004391D
0x1400438cc  movzx   ecx, word ptr [r9+4]
0x1400438d1  movzx   eax, cx
0x1400438d4  shl     ax, 2
0x1400438d8  add     cx, ax
0x1400438db  mov     eax, edx
0x1400438dd  sub     ax, cx
0x1400438e0  sub     ax, r11w
0x1400438e4  add     r8w, ax
0x1400438e8  jmp     loc_1400437A7
0x1400438ed  test    r14d, r14d
0x1400438f0  jz      short loc_140043923
0x1400438f2  movzx   ecx, word ptr [r9]
0x1400438f6  movzx   eax, cx
0x1400438f9  shl     ax, 2
0x1400438fd  add     cx, ax
0x140043900  add     cx, si
0x140043903  mov     esi, edx
0x140043905  sub     cx, dx
0x140043908  movzx   ecx, cx
0x14004390b  mov     eax, ecx
0x14004390d  imul    eax, r10d
0x140043911  add     rdi, rax
0x140043914  sub     r8w, cx
0x140043918  jmp     loc_1400437B0
0x14004391d  movzx   r11d, dx
0x140043921  jmp     short loc_1400438CC
0x140043923  mov     eax, r10d
0x140043926  imul    eax, [r9]
0x14004392a  add     rdi, rax
0x14004392d  jmp     loc_1400437B0
```
