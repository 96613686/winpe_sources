# BuildEncodings

- ea: `0x18001ae0c`
- end: `0x18001b0e4`
- name: `BuildEncodings`
- size: `728`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800182f0`
- `0x18001b0ec`
- `0x18001b254`

## callees

- `0x18000bb20`
- `0x18001562a`
- `0x18001ae0c`

## pseudocode

```c
char __fastcall BuildEncodings(_DWORD *a1)
{
  __int64 v2; // r8
  unsigned int *v3; // r11
  unsigned int *i; // r10
  unsigned int v5; // edx
  unsigned int v6; // r8d
  __int64 v7; // rdx
  __int64 v8; // rax
  unsigned __int8 *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rdi
  __int64 v13; // r8
  unsigned int v14; // r9d
  unsigned __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned int *v17; // r8
  _DWORD *v18; // rsi
  unsigned int *v19; // rbp
  unsigned int *v20; // rcx
  unsigned int *v21; // rdx
  unsigned int *v22; // r10
  int *v23; // rax
  int v24; // r9d
  unsigned int v25; // r9d
  int v26; // eax
  unsigned int *j; // rcx
  unsigned int v28; // eax
  __int64 v29; // rcx
  int v30; // r10d
  int v31; // edx
  int k; // ecx
  __int64 m; // r8
  __int64 v34; // r8

  memset_0(a1 + 13578, 0, 0x202u);
  memset_0((char *)a1 + 54826, 0, 0x202u);
  v2 = 0;
  v3 = a1 + 1284;
  for ( i = a1 + 1284; (unsigned int)v2 < *a1; i += 6 )
  {
    v5 = a1[v2 + 14347];
    *i = v5;
    ++*((_WORD *)a1 + (unsigned int)(unsigned __int8)v5 + 27157);
    ++*((_WORD *)a1 + (v5 >> 8) + 27414);
    i[4] = v2;
    v2 = (unsigned int)(v2 + 1);
    *((_QWORD *)i + 1) = 0;
  }
  v6 = 1;
  v7 = 1;
  do
  {
    v8 = v6++ - 1;
    *((_WORD *)a1 + v7 + 27156) += *((_WORD *)a1 + v8 + 27156);
    *((_WORD *)a1 + v7++ + 27413) += *((_WORD *)a1 + (unsigned int)v8 + 27413);
  }
  while ( v6 < 0x100 );
  v9 = (unsigned __int8 *)(a1 + 1284);
  if ( v3 < i )
  {
    do
    {
      *((_WORD *)a1 + *((unsigned __int16 *)a1 + *v9 + 27156) + 27670) = *((_WORD *)v9 + 8);
      v10 = *v9;
      v9 += 24;
      ++*((_WORD *)a1 + v10 + 27156);
    }
    while ( v9 < (unsigned __int8 *)i );
  }
  v11 = 0;
  v12 = ((char *)i - (char *)a1 - 5136) / 24;
  if ( (_DWORD)v12 )
  {
    do
    {
      v13 = *((unsigned __int16 *)a1 + v11 + 27670);
      v11 = (unsigned int)(v11 + 1);
      v14 = a1[v13 + 14347];
      v15 = (unsigned __int64)v14 >> 8;
      v16 = *((unsigned __int16 *)a1 + v15 + 27413);
      *((_WORD *)a1 + v15 + 27413) = v16 + 1;
      a1[6 * v16 + 1288] = v13;
      a1[6 * v16 + 1284] = v14;
    }
    while ( (unsigned int)v11 < (unsigned int)v12 );
  }
  v17 = i;
  v18 = a1 + 1290;
  v19 = i;
  while ( 1 )
  {
    v20 = i;
    v21 = a1 + 1296;
    v22 = v17;
    *((_QWORD *)v20 + 1) = v3;
    *((_QWORD *)v20 + 2) = v18;
    *v20 = *v18 + *v3;
    while ( v21 != v17 || v20 != v22 )
    {
      v22 += 6;
      if ( v21 == v17 || v20 < v22 && *v20 < *v21 )
      {
        v23 = (int *)v20;
        v20 += 6;
      }
      else
      {
        v23 = (int *)v21;
        v21 += 6;
      }
      *((_QWORD *)v22 + 1) = v23;
      v24 = *v23;
      *v22 = *v23;
      if ( v21 == v17 || v20 < v22 && *v20 < *v21 )
      {
        *((_QWORD *)v22 + 2) = v20;
        v25 = *v20 + v24;
        v20 += 6;
      }
      else
      {
        *((_QWORD *)v22 + 2) = v21;
        v25 = *v21 + v24;
        v21 += 6;
      }
      *v22 = v25;
    }
    LOBYTE(v26) = TraverseHuffmanTree(0, v22);
    if ( a1[1286] <= 0xFu )
      break;
    for ( j = v3; j < v17; j += 6 )
    {
      v28 = *j + 1;
      *((_QWORD *)j + 1) = 0;
      *j = v28 >> 1;
    }
  }
  while ( v3 < v17 )
  {
    v29 = v3[4];
    LOBYTE(v26) = *((_BYTE *)v3 + 8);
    v3 += 6;
    *((_BYTE *)a1 + v29 + 12) = v26;
  }
  v30 = a1[1286];
  v31 = 0;
  for ( k = *(v19 - 4); k <= v30; ++k )
  {
    for ( m = 0; (unsigned int)m < *a1; m = (unsigned int)(v34 + 1) )
    {
      if ( *((unsigned __int8 *)a1 + m + 12) == k )
      {
        HIWORD(a1[m + 259]) = v31++;
        LOWORD(a1[m + 259]) = k;
      }
      v34 = (unsigned int)(m + 1);
      v26 = *((unsigned __int8 *)a1 + v34 + 12);
      if ( v26 == k )
      {
        HIWORD(a1[v34 + 259]) = v31++;
        LOWORD(a1[v34 + 259]) = k;
      }
    }
    v31 *= 2;
  }
  return v26;
}

```

## disassembly

```asm
0x18001ae0c  push    rbx
0x18001ae0e  push    rbp
0x18001ae0f  push    rsi
0x18001ae10  push    rdi
0x18001ae11  push    r14
0x18001ae13  push    r15
0x18001ae15  sub     rsp, 28h
0x18001ae19  mov     rbx, rcx
0x18001ae1c  mov     edi, 202h
0x18001ae21  mov     r8d, edi; Size
0x18001ae24  add     rcx, 0D428h; void *
0x18001ae2b  xor     edx, edx; Val
0x18001ae2d  call    memset_0
0x18001ae32  lea     rcx, [rbx+0D62Ah]; void *
0x18001ae39  mov     r8d, edi; Size
0x18001ae3c  xor     edx, edx; Val
0x18001ae3e  call    memset_0
0x18001ae43  xor     r8d, r8d
0x18001ae46  lea     r11, [rbx+1410h]
0x18001ae4d  mov     r10, r11
0x18001ae50  lea     r15d, [r8+1]
0x18001ae54  cmp     [rbx], r8d
0x18001ae57  jbe     short loc_18001AE9A
0x18001ae59  mov     edx, [rbx+r8*4+0E02Ch]
0x18001ae61  mov     [r10], edx
0x18001ae64  movzx   eax, dl
0x18001ae67  shr     edx, 8
0x18001ae6a  add     eax, r15d
0x18001ae6d  add     edx, r15d
0x18001ae70  add     [rbx+rax*2+0D428h], r15w
0x18001ae79  add     [rbx+rdx*2+0D62Ah], r15w
0x18001ae82  mov     [r10+10h], r8d
0x18001ae86  add     r8d, r15d
0x18001ae89  mov     qword ptr [r10+8], 0
0x18001ae91  add     r10, 18h
0x18001ae95  cmp     r8d, [rbx]
0x18001ae98  jb      short loc_18001AE59
0x18001ae9a  mov     r8d, r15d
0x18001ae9d  mov     rdx, r15
0x18001aea0  lea     eax, [r8-1]
0x18001aea4  add     r8d, r15d
0x18001aea7  mov     ecx, eax
0x18001aea9  movzx   eax, word ptr [rbx+rax*2+0D428h]
0x18001aeb1  add     [rbx+rdx*2+0D428h], ax
0x18001aeb9  movzx   eax, word ptr [rbx+rcx*2+0D62Ah]
0x18001aec1  add     [rbx+rdx*2+0D62Ah], ax
0x18001aec9  add     rdx, r15
0x18001aecc  cmp     r8d, 100h
0x18001aed3  jb      short loc_18001AEA0
0x18001aed5  mov     rdx, r11
0x18001aed8  cmp     r11, r10
0x18001aedb  jnb     short loc_18001AF09
0x18001aedd  movzx   eax, byte ptr [rdx]
0x18001aee0  movzx   ecx, word ptr [rbx+rax*2+0D428h]
0x18001aee8  movzx   eax, word ptr [rdx+10h]
0x18001aeec  mov     [rbx+rcx*2+0D82Ch], ax
0x18001aef4  movzx   eax, byte ptr [rdx]
0x18001aef7  add     rdx, 18h
0x18001aefb  add     [rbx+rax*2+0D428h], r15w
0x18001af04  cmp     rdx, r10
0x18001af07  jb      short loc_18001AEDD
0x18001af09  mov     rcx, r10
0x18001af0c  mov     rax, 2AAAAAAAAAAAAAABh
0x18001af16  sub     rcx, rbx
0x18001af19  xor     esi, esi
0x18001af1b  sub     rcx, 1410h
0x18001af22  imul    rcx
0x18001af25  mov     rdi, rdx
0x18001af28  sar     rdi, 2
0x18001af2c  mov     rax, rdi
0x18001af2f  shr     rax, 3Fh
0x18001af33  add     rdi, rax
0x18001af36  test    edi, edi
0x18001af38  jz      short loc_18001AF85
0x18001af3a  movzx   r8d, word ptr [rbx+rsi*2+0D82Ch]
0x18001af43  add     esi, r15d
0x18001af46  mov     r9d, [rbx+r8*4+0E02Ch]
0x18001af4e  mov     edx, r9d
0x18001af51  shr     rdx, 8
0x18001af55  movzx   ecx, word ptr [rbx+rdx*2+0D62Ah]
0x18001af5d  lea     eax, [r15+rcx]
0x18001af61  mov     [rbx+rdx*2+0D62Ah], ax
0x18001af69  lea     rax, [rcx+rcx*2]
0x18001af6d  mov     [rbx+rax*8+1420h], r8d
0x18001af75  lea     rax, [rcx+rcx*2]
0x18001af79  mov     [rbx+rax*8+1410h], r9d
0x18001af81  cmp     esi, edi
0x18001af83  jb      short loc_18001AF3A
0x18001af85  mov     r8, r10
0x18001af88  lea     rsi, [rbx+1428h]
0x18001af8f  mov     rbp, r10
0x18001af92  mov     rcx, r10
0x18001af95  lea     rdx, [rbx+1440h]
0x18001af9c  mov     r10, r8
0x18001af9f  mov     [rcx+8], r11
0x18001afa3  mov     [rcx+10h], rsi
0x18001afa7  mov     eax, [r11]
0x18001afaa  add     eax, [rsi]
0x18001afac  mov     [rcx], eax
0x18001afae  cmp     rdx, r8
0x18001afb1  jnz     short loc_18001AFB8
0x18001afb3  cmp     rcx, r10
0x18001afb6  jz      short loc_18001B01B
0x18001afb8  add     r10, 18h
0x18001afbc  cmp     rdx, r8
0x18001afbf  jz      short loc_18001AFD5
0x18001afc1  cmp     rcx, r10
0x18001afc4  jnb     short loc_18001AFCC
0x18001afc6  mov     eax, [rdx]
0x18001afc8  cmp     [rcx], eax
0x18001afca  jb      short loc_18001AFD5
0x18001afcc  mov     rax, rdx
0x18001afcf  add     rdx, 18h
0x18001afd3  jmp     short loc_18001AFDC
0x18001afd5  mov     rax, rcx
0x18001afd8  add     rcx, 18h
0x18001afdc  mov     edi, 8
0x18001afe1  mov     r9, r10
0x18001afe4  mov     [rdi+r10], rax
0x18001afe8  mov     r9d, [rax]
0x18001afeb  mov     [r10], r9d
0x18001afee  cmp     rdx, r8
0x18001aff1  jz      short loc_18001B00B
0x18001aff3  cmp     rcx, r10
0x18001aff6  jnb     short loc_18001AFFE
0x18001aff8  mov     eax, [rdx]
0x18001affa  cmp     [rcx], eax
0x18001affc  jb      short loc_18001B00B
0x18001affe  mov     [r10+10h], rdx
0x18001b002  add     r9d, [rdx]
0x18001b005  add     rdx, 18h
0x18001b009  jmp     short loc_18001B016
0x18001b00b  mov     [r10+10h], rcx
0x18001b00f  add     r9d, [rcx]
0x18001b012  add     rcx, 18h
0x18001b016  mov     [r10], r9d
0x18001b019  jmp     short loc_18001AFAE
0x18001b01b  mov     rdx, r10
0x18001b01e  xor     ecx, ecx
0x18001b020  call    TraverseHuffmanTree
0x18001b025  cmp     dword ptr [rbx+1418h], 0Fh
0x18001b02c  jbe     short loc_18001B069
0x18001b02e  mov     rcx, r11
0x18001b031  cmp     r11, r8
0x18001b034  jnb     loc_18001AF92
0x18001b03a  mov     eax, [rcx]
0x18001b03c  add     eax, r15d
0x18001b03f  mov     qword ptr [rcx+8], 0
0x18001b047  shr     eax, 1
0x18001b049  mov     [rcx], eax
0x18001b04b  add     rcx, 18h
0x18001b04f  cmp     rcx, r8
0x18001b052  jb      short loc_18001B03A
0x18001b054  jmp     loc_18001AF92
0x18001b059  mov     ecx, [r11+10h]
0x18001b05d  mov     al, [r11+8]
0x18001b061  add     r11, 18h
0x18001b065  mov     [rcx+rbx+0Ch], al
0x18001b069  cmp     r11, r8
0x18001b06c  jb      short loc_18001B059
0x18001b06e  mov     r10d, [rbx+1418h]
0x18001b075  xor     edx, edx
0x18001b077  mov     ecx, [rbp-10h]
0x18001b07a  jmp     short loc_18001B0D2
0x18001b07c  xor     r8d, r8d
0x18001b07f  cmp     [rbx], r8d
0x18001b082  jbe     short loc_18001B0CD
0x18001b084  movzx   eax, byte ptr [r8+rbx+0Ch]
0x18001b08a  cmp     eax, ecx
0x18001b08c  jnz     short loc_18001B0A3
0x18001b08e  mov     [rbx+r8*4+40Eh], dx
0x18001b097  add     edx, r15d
0x18001b09a  mov     [rbx+r8*4+40Ch], cx
0x18001b0a3  add     r8d, r15d
0x18001b0a6  movzx   eax, byte ptr [r8+rbx+0Ch]
0x18001b0ac  cmp     eax, ecx
0x18001b0ae  jnz     short loc_18001B0C5
0x18001b0b0  mov     [rbx+r8*4+40Eh], dx
0x18001b0b9  add     edx, r15d
0x18001b0bc  mov     [rbx+r8*4+40Ch], cx
0x18001b0c5  add     r8d, r15d
0x18001b0c8  cmp     r8d, [rbx]
0x18001b0cb  jb      short loc_18001B084
0x18001b0cd  add     edx, edx
0x18001b0cf  add     ecx, r15d
0x18001b0d2  cmp     ecx, r10d
0x18001b0d5  jle     short loc_18001B07C
0x18001b0d7  add     rsp, 28h
0x18001b0db  pop     r15
0x18001b0dd  pop     r14
0x18001b0df  pop     rdi
0x18001b0e0  pop     rsi
0x18001b0e1  pop     rbp
0x18001b0e2  pop     rbx
0x18001b0e3  retn
```
