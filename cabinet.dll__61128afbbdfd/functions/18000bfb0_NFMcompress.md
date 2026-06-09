# NFMcompress

- ea: `0x18000bfb0`
- end: `0x18000c2ce`
- name: `NFMcompress`
- size: `798`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003730`
- `0x18000bf30`

## callees

- `0x18000bec0`
- `0x18000bfb0`
- `0x18000c2d4`
- `0x18000c500`
- `0x18001562a`
- `0x18001b625`

## pseudocode

```c
__int64 __fastcall NFMcompress(__int64 a1, const void *a2, unsigned int a3, __int64 a4, int a5, _DWORD *a6)
{
  __int64 v8; // r14
  char *v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // ecx
  __int64 v13; // rdx
  unsigned __int16 v14; // ax
  __int64 i; // rax
  int v16; // ecx
  __int16 v17; // dx
  int v18; // r8d
  int v19; // r10d
  __int16 v20; // dx
  int v21; // eax
  int v22; // r9d
  unsigned int v24; // r8d
  __int64 v25; // rcx
  __int64 v26; // rdx
  int v27; // eax
  unsigned int v28; // r8d
  __int64 v29; // rcx
  int v30; // edx
  unsigned int v31; // eax

  v8 = a3;
  v9 = (char *)(*(_QWORD *)(a1 + 12240) + 0x8000LL);
  if ( !*(_BYTE *)(a1 + 12248) )
    v9 = *(char **)(a1 + 12240);
  memcpy_0(v9, a2, a3);
  if ( (unsigned int)v8 < 0x8000 )
  {
    v31 = 265;
    if ( (unsigned int)(0x8000 - v8) < 0x109 )
      v31 = 0x8000 - v8;
    memset_0(&v9[v8], 0, v31);
  }
  v10 = *(_QWORD *)(a1 + 12240);
  *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 12232);
  *(_QWORD *)(a1 + 48) = *(_QWORD *)(a1 + 12224);
  *(_DWORD *)(a1 + 28) = a5;
  *(_QWORD *)(a1 + 8) = a4;
  *(_WORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = v10;
  *(_DWORD *)(a1 + 60) = v8;
  *(_DWORD *)(a1 + 64) = 0;
  if ( !*(_BYTE *)(a1 + 12248) )
    memcpy_0((void *)(v10 + 0x8000), (const void *)v10, 0x8000u);
  *(_WORD *)(a1 + 68) = 0;
  *(_DWORD *)(a1 + 72) = 0;
  ct_init(a1);
  v11 = *(_QWORD *)(a1 + 32);
  LOWORD(v12) = 0;
  v13 = 0;
  *(_WORD *)(a1 + 84) = 0x8000;
  *(_DWORD *)(a1 + 76) = 0x8000;
  *(_DWORD *)(a1 + 56) = 0;
  do
  {
    v14 = *(unsigned __int8 *)(v11 + v13++ + 0x8000);
    v12 = (v14 ^ (unsigned __int16)(32 * v12)) & 0x7FFF;
    *(_DWORD *)(a1 + 56) = v12;
  }
  while ( v13 != 2 );
  if ( *(_BYTE *)(a1 + 12248) )
  {
    lm_init_use_tables(a1);
  }
  else
  {
    for ( i = 0; i != 0x8000; ++i )
      *(_WORD *)(*(_QWORD *)(a1 + 40) + 2 * i) = 0;
  }
  v16 = *(_DWORD *)(a1 + 72);
  *(_WORD *)(a1 + 68) |= 67 << v16;
  v17 = *(_WORD *)(a1 + 68);
  if ( v16 <= 8 )
  {
    v18 = v16 + 8;
    LOWORD(v19) = *(_WORD *)(a1 + 68);
    goto LABEL_13;
  }
  v24 = *(_DWORD *)(a1 + 28);
  v25 = *(unsigned __int16 *)(a1 + 24);
  if ( (unsigned int)v25 >= v24 - 2 )
  {
    if ( (unsigned int)v25 < v24 )
    {
      *(_BYTE *)(v25 + *(_QWORD *)(a1 + 8)) = v17;
      LOWORD(v25) = ++*(_WORD *)(a1 + 24);
    }
    else
    {
      *(_DWORD *)(a1 + 64) = 1;
    }
    if ( (unsigned int)(unsigned __int16)v25 >= *(_DWORD *)(a1 + 28) )
    {
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_22;
    }
    v26 = (unsigned __int16)v25;
  }
  else
  {
    *(_BYTE *)(v25 + *(_QWORD *)(a1 + 8)) = v17;
    v26 = (unsigned __int16)++*(_WORD *)(a1 + 24);
  }
  *(_BYTE *)(v26 + *(_QWORD *)(a1 + 8)) = *(_BYTE *)(a1 + 69);
  ++*(_WORD *)(a1 + 24);
LABEL_22:
  v27 = *(_DWORD *)(a1 + 72);
  v19 = 67 >> (16 - v27);
  v18 = v27 - 8;
LABEL_13:
  *(_DWORD *)(a1 + 72) = v18;
  v20 = v19 | (75 << v18);
  if ( v18 <= 8 )
  {
    v21 = v18 + 8;
    LOWORD(v22) = v19 | (75 << v18);
    goto LABEL_15;
  }
  v28 = *(_DWORD *)(a1 + 28);
  v29 = *(unsigned __int16 *)(a1 + 24);
  *(_WORD *)(a1 + 68) = v20;
  if ( (unsigned int)v29 >= v28 - 2 )
  {
    if ( (unsigned int)v29 < v28 )
    {
      *(_BYTE *)(v29 + *(_QWORD *)(a1 + 8)) = v20;
      LOWORD(v29) = ++*(_WORD *)(a1 + 24);
    }
    else
    {
      *(_DWORD *)(a1 + 64) = 1;
    }
    if ( (unsigned int)(unsigned __int16)v29 >= *(_DWORD *)(a1 + 28) )
    {
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_26;
    }
    *(_BYTE *)((unsigned __int16)v29 + *(_QWORD *)(a1 + 8)) = *(_BYTE *)(a1 + 69);
  }
  else
  {
    *(_BYTE *)(v29 + *(_QWORD *)(a1 + 8)) = v20;
    *(_BYTE *)((unsigned __int16)++*(_WORD *)(a1 + 24) + *(_QWORD *)(a1 + 8)) = *(_BYTE *)(a1 + 69);
  }
  ++*(_WORD *)(a1 + 24);
LABEL_26:
  v30 = *(_DWORD *)(a1 + 72);
  v22 = 75 >> (16 - v30);
  v21 = v30 - 8;
LABEL_15:
  *(_DWORD *)(a1 + 72) = v21;
  *(_WORD *)(a1 + 68) = v22;
  *a6 = (unsigned __int16)(deflate(a1) + 2);
  if ( *(_BYTE *)(a1 + 12248) )
    memcpy_0(*(void **)(a1 + 32), (const void *)(*(_QWORD *)(a1 + 32) + 0x8000LL), 0x8000u);
  if ( *(_DWORD *)(a1 + 64) )
    return 3;
  *(_BYTE *)(a1 + 12248) = (_DWORD)v8 == 0x8000;
  return 0;
}

```

## disassembly

```asm
0x18000bfb0  push    rbx
0x18000bfb2  push    rbp
0x18000bfb3  push    rsi
0x18000bfb4  push    rdi
0x18000bfb5  push    r14
0x18000bfb7  push    r15
0x18000bfb9  sub     rsp, 28h
0x18000bfbd  mov     rax, [rcx+2FD0h]
0x18000bfc4  mov     rbx, rcx
0x18000bfc7  cmp     byte ptr [rcx+2FD8h], 0
0x18000bfce  mov     rbp, r9
0x18000bfd1  mov     r14d, r8d
0x18000bfd4  mov     r8d, r8d; Size
0x18000bfd7  lea     rdi, [rax+8000h]
0x18000bfde  cmovz   rdi, rax
0x18000bfe2  mov     rcx, rdi; void *
0x18000bfe5  call    memcpy_0
0x18000bfea  mov     r15d, 8000h
0x18000bff0  cmp     r14d, r15d
0x18000bff3  jb      loc_18000C22C
0x18000bff9  mov     rax, [rbx+2FC8h]
0x18000c000  xor     edi, edi
0x18000c002  mov     rdx, [rbx+2FD0h]; Src
0x18000c009  mov     [rbx+28h], rax
0x18000c00d  mov     rax, [rbx+2FC0h]
0x18000c014  mov     [rbx+30h], rax
0x18000c018  mov     eax, [rsp+58h+arg_20]
0x18000c01f  mov     [rbx+1Ch], eax
0x18000c022  mov     [rbx+8], rbp
0x18000c026  mov     [rbx+18h], di
0x18000c02a  mov     [rbx+20h], rdx
0x18000c02e  mov     [rbx+3Ch], r14d
0x18000c032  mov     [rbx+40h], edi
0x18000c035  cmp     [rbx+2FD8h], dil
0x18000c03c  jz      loc_18000C1F9
0x18000c042  mov     rcx, rbx
0x18000c045  mov     [rbx+44h], di
0x18000c049  mov     [rbx+48h], edi
0x18000c04c  call    ct_init
0x18000c051  mov     r8, [rbx+20h]
0x18000c055  mov     ecx, edi
0x18000c057  mov     rdx, rdi
0x18000c05a  mov     [rbx+54h], r15w
0x18000c05f  mov     [rbx+4Ch], r15d
0x18000c063  mov     [rbx+38h], edi
0x18000c066  movzx   eax, byte ptr [r8+rdx+8000h]
0x18000c06f  inc     rdx
0x18000c072  shl     ecx, 5
0x18000c075  xor     ecx, eax
0x18000c077  and     ecx, 7FFFh
0x18000c07d  mov     [rbx+38h], ecx
0x18000c080  cmp     rdx, 2
0x18000c084  jnz     short loc_18000C066
0x18000c086  cmp     [rbx+2FD8h], dil
0x18000c08d  jnz     loc_18000C21F
0x18000c093  mov     rax, rdi
0x18000c096  nop     word ptr [rax+rax+00000000h]
0x18000c0a0  mov     rdx, [rbx+28h]
0x18000c0a4  mov     [rdx+rax*2], di
0x18000c0a8  inc     rax
0x18000c0ab  cmp     rax, r15
0x18000c0ae  jnz     short loc_18000C0A0
0x18000c0b0  mov     ecx, [rbx+48h]
0x18000c0b3  mov     r10d, 43h ; 'C'
0x18000c0b9  mov     eax, r10d
0x18000c0bc  mov     r11d, 10h
0x18000c0c2  shl     ax, cl
0x18000c0c5  or      [rbx+44h], ax
0x18000c0c9  movzx   edx, word ptr [rbx+44h]
0x18000c0cd  cmp     ecx, 8
0x18000c0d0  jg      loc_18000C168
0x18000c0d6  lea     r8d, [rcx+8]
0x18000c0da  movzx   r10d, dx
0x18000c0de  mov     r9d, 4Bh ; 'K'
0x18000c0e4  mov     [rbx+48h], r8d
0x18000c0e8  mov     edx, r9d
0x18000c0eb  mov     ecx, r8d
0x18000c0ee  shl     dx, cl
0x18000c0f1  or      dx, r10w
0x18000c0f5  cmp     r8d, 8
0x18000c0f9  jg      loc_18000C1AE
0x18000c0ff  lea     eax, [r8+8]
0x18000c103  movzx   r9d, dx
0x18000c107  mov     [rbx+48h], eax
0x18000c10a  mov     rcx, rbx
0x18000c10d  mov     [rbx+44h], r9w
0x18000c112  call    deflate
0x18000c117  add     ax, 2
0x18000c11b  movzx   ecx, ax
0x18000c11e  mov     rax, [rsp+58h+arg_28]
0x18000c126  mov     [rax], ecx
0x18000c128  cmp     [rbx+2FD8h], dil
0x18000c12f  jz      short loc_18000C144
0x18000c131  mov     rcx, [rbx+20h]; void *
0x18000c135  mov     r8, r15; Size
0x18000c138  lea     rdx, [rcx+8000h]; Src
0x18000c13f  call    memcpy_0
0x18000c144  cmp     [rbx+40h], edi
0x18000c147  jnz     loc_18000C20D
0x18000c14d  cmp     r14d, r15d
0x18000c150  setz    al
0x18000c153  mov     [rbx+2FD8h], al
0x18000c159  xor     eax, eax
0x18000c15b  add     rsp, 28h
0x18000c15f  pop     r15
0x18000c161  pop     r14
0x18000c163  pop     rdi
0x18000c164  pop     rsi
0x18000c165  pop     rbp
0x18000c166  pop     rbx
0x18000c167  retn
0x18000c168  mov     r8d, [rbx+1Ch]
0x18000c16c  movzx   ecx, word ptr [rbx+18h]
0x18000c170  lea     eax, [r8-2]
0x18000c174  cmp     ecx, eax
0x18000c176  jnb     loc_18000C24F
0x18000c17c  mov     rax, [rbx+8]
0x18000c180  mov     [rcx+rax], dl
0x18000c183  inc     word ptr [rbx+18h]
0x18000c187  movzx   edx, word ptr [rbx+18h]
0x18000c18b  mov     rcx, [rbx+8]
0x18000c18f  movzx   eax, byte ptr [rbx+45h]
0x18000c193  mov     [rdx+rcx], al
0x18000c196  inc     word ptr [rbx+18h]
0x18000c19a  mov     eax, [rbx+48h]
0x18000c19d  mov     ecx, r11d
0x18000c1a0  sub     ecx, eax
0x18000c1a2  sar     r10d, cl
0x18000c1a5  lea     r8d, [rax-8]
0x18000c1a9  jmp     loc_18000C0DE
0x18000c1ae  mov     r8d, [rbx+1Ch]
0x18000c1b2  movzx   ecx, word ptr [rbx+18h]
0x18000c1b6  mov     [rbx+44h], dx
0x18000c1ba  lea     eax, [r8-2]
0x18000c1be  cmp     ecx, eax
0x18000c1c0  jnb     loc_18000C288
0x18000c1c6  mov     rax, [rbx+8]
0x18000c1ca  mov     [rcx+rax], dl
0x18000c1cd  inc     word ptr [rbx+18h]
0x18000c1d1  movzx   edx, word ptr [rbx+18h]
0x18000c1d5  mov     rcx, [rbx+8]
0x18000c1d9  movzx   eax, byte ptr [rbx+45h]
0x18000c1dd  mov     [rdx+rcx], al
0x18000c1e0  inc     word ptr [rbx+18h]
0x18000c1e4  mov     edx, [rbx+48h]
0x18000c1e7  sub     r11d, edx
0x18000c1ea  movzx   ecx, r11b
0x18000c1ee  sar     r9d, cl
0x18000c1f1  lea     eax, [rdx-8]
0x18000c1f4  jmp     loc_18000C107
0x18000c1f9  lea     rcx, [rdx+8000h]; void *
0x18000c200  mov     r8, r15; Size
0x18000c203  call    memcpy_0
0x18000c208  jmp     loc_18000C042
0x18000c20d  mov     eax, 3
0x18000c212  add     rsp, 28h
0x18000c216  pop     r15
0x18000c218  pop     r14
0x18000c21a  pop     rdi
0x18000c21b  pop     rsi
0x18000c21c  pop     rbp
0x18000c21d  pop     rbx
0x18000c21e  retn
0x18000c21f  mov     rcx, rbx
0x18000c222  call    lm_init_use_tables
0x18000c227  jmp     loc_18000C0B0
0x18000c22c  mov     eax, 109h
0x18000c231  mov     ecx, r15d
0x18000c234  sub     ecx, r14d
0x18000c237  cmp     ecx, eax
0x18000c239  cmovb   eax, ecx
0x18000c23c  lea     rcx, [rdi+r14]; void *
0x18000c240  mov     r8d, eax; Size
0x18000c243  xor     edx, edx; Val
0x18000c245  call    memset_0
0x18000c24a  jmp     loc_18000BFF9
0x18000c24f  cmp     ecx, r8d
0x18000c252  jb      short loc_18000C25D
0x18000c254  mov     dword ptr [rbx+40h], 1
0x18000c25b  jmp     short loc_18000C26C
0x18000c25d  mov     rax, [rbx+8]
0x18000c261  mov     [rcx+rax], dl
0x18000c264  inc     word ptr [rbx+18h]
0x18000c268  movzx   ecx, word ptr [rbx+18h]
0x18000c26c  movzx   eax, cx
0x18000c26f  cmp     eax, [rbx+1Ch]
0x18000c272  jb      short loc_18000C280
0x18000c274  mov     dword ptr [rbx+40h], 1
0x18000c27b  jmp     loc_18000C19A
0x18000c280  movzx   edx, cx
0x18000c283  jmp     loc_18000C18B
0x18000c288  cmp     ecx, r8d
0x18000c28b  jb      short loc_18000C296
0x18000c28d  mov     dword ptr [rbx+40h], 1
0x18000c294  jmp     short loc_18000C2A5
0x18000c296  mov     rax, [rbx+8]
0x18000c29a  mov     [rcx+rax], dl
0x18000c29d  inc     word ptr [rbx+18h]
0x18000c2a1  movzx   ecx, word ptr [rbx+18h]
0x18000c2a5  movzx   eax, cx
0x18000c2a8  cmp     eax, [rbx+1Ch]
0x18000c2ab  jb      short loc_18000C2B9
0x18000c2ad  mov     dword ptr [rbx+40h], 1
0x18000c2b4  jmp     loc_18000C1E4
0x18000c2b9  mov     rdx, [rbx+8]
0x18000c2bd  movzx   eax, byte ptr [rbx+45h]
0x18000c2c1  movzx   r8d, cx
0x18000c2c5  mov     [r8+rdx], al
0x18000c2c9  jmp     loc_18000C1E0
```
