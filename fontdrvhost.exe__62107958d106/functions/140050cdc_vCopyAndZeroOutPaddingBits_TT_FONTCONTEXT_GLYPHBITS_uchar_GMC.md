# vCopyAndZeroOutPaddingBits(_TT_FONTCONTEXT *,_GLYPHBITS *,uchar *,_GMC *)

- ea: `0x140050cdc`
- end: `0x140050e43`
- name: `?vCopyAndZeroOutPaddingBits@@YAXPEAU_TT_FONTCONTEXT@@PEAU_GLYPHBITS@@PEAEPEAU_GMC@@@Z`
- size: `359`
- prototype: `void __fastcall(struct _TT_FONTCONTEXT *, struct _GLYPHBITS *, unsigned __int8 *, struct _GMC *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140015d80`

## callees

- `0x140050cdc`
- `0x140076eea`

## pseudocode

```c
void __fastcall vCopyAndZeroOutPaddingBits(
        struct _TT_FONTCONTEXT *a1,
        struct _GLYPHBITS *a2,
        unsigned __int8 *a3,
        struct _GMC *a4)
{
  LONG v4; // r10d
  LONG v6; // ebp
  int v7; // r11d
  char v8; // r12
  int v9; // eax
  unsigned int v10; // ecx
  unsigned int v11; // edx
  unsigned int v12; // r11d
  BYTE *aj; // rbx
  unsigned __int8 *v14; // rdi
  BYTE *v15; // rsi
  int v16; // r10d
  size_t v17; // rbp
  __int64 v18; // r14
  __int64 v19; // r15
  __int64 v20; // r15
  unsigned __int8 *v21; // r14
  char v22; // bp
  unsigned __int8 *v23; // r9
  BYTE *i; // r8
  BYTE v25; // dl
  BYTE v26; // dl
  char v27; // al

  v4 = *((_DWORD *)a4 + 4);
  v6 = *((_DWORD *)a4 + 5);
  v7 = v4 + *((_DWORD *)a4 + 2) + *((_DWORD *)a4 + 3);
  v8 = *((_BYTE *)&qword_14009C360 + (v4 & 7));
  v9 = *((_DWORD *)a1 + 10) & 0x10000;
  a2->sizlBitmap.cx = v4;
  a2->sizlBitmap.cy = v6;
  v10 = (unsigned int)(v4 + 7) >> 3;
  v11 = v10 - 1;
  v12 = 4 * ((unsigned int)((v9 != 0 ? 8 : 1) * v7 + 31) >> 5);
  if ( *(_DWORD *)a4 )
    a3 += *(_DWORD *)a4 * v12;
  aj = a2->aj;
  v14 = &a3[(unsigned __int64)*((unsigned int *)a4 + 2) >> 3];
  v15 = &aj[v6 * v10];
  v16 = *((_DWORD *)a4 + 2) & 7;
  if ( v16 )
  {
    if ( aj < v15 )
    {
      v20 = v11;
      v21 = &a3[v6 * v12];
      v22 = 8 - v16;
      do
      {
        v23 = v14;
        for ( i = aj; i < &aj[v20]; ++i )
        {
          v25 = *v23++ << v16;
          *i = v25;
          *i = v25 | (*v23 >> v22);
        }
        v26 = *v23 << v16;
        *i = v26;
        if ( v23 + 1 >= v21 )
          v27 = v26;
        else
          v27 = v26 | (v23[1] >> v22);
        v14 += v12;
        aj += v10;
        *i = v8 & v27;
      }
      while ( aj < v15 );
    }
  }
  else if ( aj < v15 )
  {
    v17 = v10;
    v18 = v11;
    v19 = v12;
    do
    {
      memcpy_0(aj, v14, v17);
      aj[v18] &= v8;
      v14 += v19;
      aj += v17;
    }
    while ( aj < v15 );
  }
}

```

## disassembly

```asm
0x140050cdc  push    rbx
0x140050cde  push    rbp
0x140050cdf  push    rsi
0x140050ce0  push    rdi
0x140050ce1  push    r12
0x140050ce3  push    r13
0x140050ce5  push    r14
0x140050ce7  push    r15
0x140050ce9  sub     rsp, 28h
0x140050ced  mov     r10d, [r9+10h]
0x140050cf1  lea     r12, qword_14009C360
0x140050cf8  mov     r11d, [r9+0Ch]
0x140050cfc  mov     rbx, rdx
0x140050cff  add     r11d, [r9+8]
0x140050d03  mov     eax, r10d
0x140050d06  mov     ebp, [r9+14h]
0x140050d0a  add     r11d, r10d
0x140050d0d  and     eax, 7
0x140050d10  mov     r12b, [rax+r12]
0x140050d14  mov     eax, [rcx+28h]
0x140050d17  and     eax, 10000h
0x140050d1c  mov     [rbx+8], r10d
0x140050d20  neg     eax
0x140050d22  mov     [rbx+0Ch], ebp
0x140050d25  sbb     ecx, ecx
0x140050d27  and     ecx, 7
0x140050d2a  inc     ecx
0x140050d2c  imul    r11d, ecx
0x140050d30  lea     ecx, [r10+7]
0x140050d34  shr     ecx, 3
0x140050d37  add     r11d, 1Fh
0x140050d3b  lea     edx, [rcx-1]
0x140050d3e  shr     r11d, 5
0x140050d42  shl     r11d, 2
0x140050d46  cmp     dword ptr [r9], 0
0x140050d4a  jnz     short loc_140050DA7
0x140050d4c  mov     r10d, [r9+8]
0x140050d50  mov     esi, ecx
0x140050d52  imul    esi, ebp
0x140050d55  add     rbx, 10h
0x140050d59  mov     edi, r10d
0x140050d5c  shr     rdi, 3
0x140050d60  add     rdi, r8
0x140050d63  add     rsi, rbx
0x140050d66  and     r10d, 7
0x140050d6a  jnz     short loc_140050DB3
0x140050d6c  cmp     rbx, rsi
0x140050d6f  jnb     short loc_140050D96
0x140050d71  mov     ebp, ecx
0x140050d73  mov     r14d, edx
0x140050d76  mov     r15d, r11d
0x140050d79  mov     r8, rbp; Size
0x140050d7c  mov     rdx, rdi; Src
0x140050d7f  mov     rcx, rbx; void *
0x140050d82  call    memcpy_0
0x140050d87  and     [r14+rbx], r12b
0x140050d8b  add     rdi, r15
0x140050d8e  add     rbx, rbp
0x140050d91  cmp     rbx, rsi
0x140050d94  jb      short loc_140050D79
0x140050d96  add     rsp, 28h
0x140050d9a  pop     r15
0x140050d9c  pop     r14
0x140050d9e  pop     r13
0x140050da0  pop     r12
0x140050da2  pop     rdi
0x140050da3  pop     rsi
0x140050da4  pop     rbp
0x140050da5  pop     rbx
0x140050da6  retn
0x140050da7  mov     eax, r11d
0x140050daa  imul    eax, [r9]
0x140050dae  add     r8, rax
0x140050db1  jmp     short loc_140050D4C
0x140050db3  cmp     rbx, rsi
0x140050db6  jnb     short loc_140050D96
0x140050db8  mov     r14d, r11d
0x140050dbb  mov     eax, r11d
0x140050dbe  imul    r14d, ebp
0x140050dc2  mov     ebp, 8
0x140050dc7  mov     r15d, edx
0x140050dca  mov     r13d, ecx
0x140050dcd  mov     [rsp+68h+arg_0], rax
0x140050dd2  add     r14, r8
0x140050dd5  sub     bpl, r10b
0x140050dd8  lea     r11, [r15+rbx]
0x140050ddc  mov     r9, rdi
0x140050ddf  mov     r8, rbx
0x140050de2  cmp     rbx, r11
0x140050de5  jnb     short loc_140050E0A
0x140050de7  mov     dl, [r9]
0x140050dea  mov     ecx, r10d
0x140050ded  shl     dl, cl
0x140050def  inc     r9
0x140050df2  mov     [r8], dl
0x140050df5  mov     cl, bpl
0x140050df8  mov     al, [r9]
0x140050dfb  shr     al, cl
0x140050dfd  or      al, dl
0x140050dff  mov     [r8], al
0x140050e02  inc     r8
0x140050e05  cmp     r8, r11
0x140050e08  jb      short loc_140050DE7
0x140050e0a  mov     dl, [r9]
0x140050e0d  lea     rax, [r9+1]
0x140050e11  mov     ecx, r10d
0x140050e14  shl     dl, cl
0x140050e16  mov     [r8], dl
0x140050e19  cmp     rax, r14
0x140050e1c  jnb     short loc_140050E29
0x140050e1e  mov     al, [rax]
0x140050e20  mov     cl, bpl
0x140050e23  shr     al, cl
0x140050e25  or      al, dl
0x140050e27  jmp     short loc_140050E2B
0x140050e29  mov     al, dl
0x140050e2b  add     rdi, [rsp+68h+arg_0]
0x140050e30  and     al, r12b
0x140050e33  add     rbx, r13
0x140050e36  mov     [r8], al
0x140050e39  cmp     rbx, rsi
0x140050e3c  jb      short loc_140050DD8
0x140050e3e  jmp     loc_140050D96
```
