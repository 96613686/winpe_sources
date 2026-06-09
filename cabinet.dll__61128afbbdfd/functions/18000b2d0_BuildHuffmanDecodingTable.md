# BuildHuffmanDecodingTable

- ea: `0x18000b2d0`
- end: `0x18000bb18`
- name: `BuildHuffmanDecodingTable`
- size: `2120`
- prototype: `__int16 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180009650`
- `0x18000b0e0`

## callees

- `0x18000b2d0`
- `0x18000bb20`
- `0x18001562a`

## pseudocode

```c
__int16 __fastcall BuildHuffmanDecodingTable(unsigned int *a1)
{
  unsigned int *v1; // rsi
  unsigned int *v3; // rdi
  unsigned __int64 v4; // r11
  unsigned __int64 i; // rdx
  unsigned int v6; // ecx
  unsigned __int64 j; // rcx
  unsigned int *k; // rdx
  __int64 v9; // rax
  unsigned __int64 m; // r10
  __int64 v11; // r8
  unsigned int v12; // r9d
  char *v13; // rcx
  __int64 v14; // rdx
  unsigned int *v15; // r8
  _DWORD *v16; // r9
  unsigned int *v17; // rdx
  unsigned int *v18; // rcx
  unsigned int v19; // eax
  unsigned __int64 v20; // r11
  __int64 v21; // rcx
  char v22; // al
  unsigned __int64 v23; // rdx
  char *v24; // rcx
  __int64 v25; // r8
  __int16 result; // ax
  unsigned __int64 v27; // rcx
  __int16 v28; // bp
  bool v29; // zf
  __int64 v30; // rdx
  __int64 v31; // r9
  unsigned __int64 v32; // r10
  __int64 v33; // rcx
  __int64 v34; // r11
  __int64 v35; // r9
  __int64 v36; // rcx
  __int16 v37; // dx
  unsigned __int64 v38; // r8
  unsigned int *n; // rcx
  unsigned int v40; // eax
  __int64 v41; // rdx

  v1 = a1 + 1284;
  v3 = a1 + 1284;
  memset_0(a1 + 13578, 0, 0x202u);
  memset_0((char *)a1 + 54826, 0, 0x202u);
  v4 = *a1;
  for ( i = 0; i < v4; v3 += 6 )
  {
    v6 = a1[i + 3];
    *v3 = v6;
    ++*((_WORD *)a1 + (unsigned int)(unsigned __int8)v6 + 27157);
    ++*((_WORD *)a1 + (v6 >> 8) + 27414);
    v3[4] = i++;
    *((_QWORD *)v3 + 1) = 0;
  }
  for ( j = 1; j < 0x100; ++j )
  {
    *((_WORD *)a1 + j + 27156) += *((_WORD *)a1 + j + 27155);
    *((_WORD *)a1 + j + 27413) += *((_WORD *)a1 + j + 27412);
  }
  for ( k = v1; k < v3; ++*((_WORD *)a1 + v9 + 27156) )
  {
    *((_WORD *)a1 + *((unsigned __int16 *)a1 + *(unsigned __int8 *)k + 27156) + 27670) = *((_WORD *)k + 8);
    v9 = *(unsigned __int8 *)k;
    k += 6;
  }
  for ( m = 0; m < v4; a1[6 * v14 + 1284] = v12 )
  {
    v11 = *((unsigned __int16 *)a1 + m++ + 27670);
    v12 = a1[v11 + 3];
    v13 = (char *)a1 + 2 * ((unsigned __int64)v12 >> 8);
    v14 = *((unsigned __int16 *)v13 + 27413);
    *((_WORD *)v13 + 27413) = v14 + 1;
    a1[6 * v14 + 1288] = v11;
  }
  v15 = v3;
  v16 = a1 + 1290;
  while ( 1 )
  {
    v17 = v3;
    v18 = a1 + 1296;
    v3 = v15;
    *((_QWORD *)v17 + 1) = v1;
    *((_QWORD *)v17 + 2) = v16;
    *v17 = *v1 + *v16;
    while ( v18 != v15 || v17 != v3 )
    {
      v3 += 6;
      if ( v18 == v15 || v17 < v3 && *v17 < *v18 )
      {
        *((_QWORD *)v3 + 1) = v17;
        v19 = *v17;
        v17 += 6;
      }
      else
      {
        *((_QWORD *)v3 + 1) = v18;
        v19 = *v18;
        v18 += 6;
      }
      *v3 = v19;
      if ( v18 == v15 || v17 < v3 && *v17 < *v18 )
      {
        *((_QWORD *)v3 + 2) = v17;
        *v3 += *v17;
        v17 += 6;
      }
      else
      {
        *((_QWORD *)v3 + 2) = v18;
        *v3 += *v18;
        v18 += 6;
      }
    }
    TraverseHuffmanTree(0, v3);
    if ( a1[1286] <= 0xF )
      break;
    for ( n = v1; n < v15; n += 6 )
    {
      v40 = *n + 1;
      *((_QWORD *)n + 1) = 0;
      *n = v40 >> 1;
    }
  }
  for ( ; v1 < v15; *((_BYTE *)a1 + v21 + 4108) = v22 )
  {
    v21 = v1[4];
    v22 = *((_BYTE *)v1 + 8);
    v1 += 6;
  }
  a1[14859] = 67109888;
  a1[14860] = 67109888;
  v23 = 0;
  a1[14861] = 67109888;
  a1[14862] = 67109888;
  a1[14863] = 67109888;
  a1[14864] = 67109888;
  a1[14865] = 67109888;
  for ( a1[14866] = 67109888; v23 < v20; ++v23 )
  {
    v24 = (char *)a1 + 2 * *((unsigned __int8 *)a1 + v23 + 4108);
    *((_WORD *)a1 + v23 + 28694) = *((_WORD *)v24 + 29718);
    *((_WORD *)v24 + 29718) = v23;
  }
  v25 = (unsigned int)(2 * v20);
  result = -2 * v20;
  v27 = 15;
  v28 = 1 - 2 * v20;
  while ( v27 > 0xA )
  {
    v29 = v28 == result;
    if ( v28 < result )
    {
      v41 = v25 + 30758;
      do
      {
        *((_WORD *)a1 + v41--) = v28;
        v28 += 2;
        --v25;
        v29 = v28 == result;
      }
      while ( v28 < result );
    }
    if ( v29 )
      return result;
    v30 = *((unsigned __int16 *)a1 + v27 + 29718);
    v28 = result + 1;
    if ( v30 != 1024 )
    {
      v31 = v25 + 30758;
      do
      {
        --v31;
        --v25;
        *((_WORD *)a1 + v31 + 1) = v27 + 16 * v30;
        v30 = *((unsigned __int16 *)a1 + v30 + 28694);
      }
      while ( v30 != 1024 );
    }
    result = -(__int16)v25;
    --v27;
  }
  v32 = 1023;
  if ( v28 < result )
  {
    v33 = 30757;
    do
    {
      *((_WORD *)a1 + v33--) = v28;
      v28 += 2;
      --v32;
    }
    while ( v28 < result );
  }
  v34 = 10;
LABEL_41:
  if ( v34 )
  {
    v35 = *((unsigned __int16 *)a1 + v34 + 29718);
    v36 = 10 - v34;
    while ( 1 )
    {
      if ( v35 == 1024 )
      {
        v32 >>= 1;
        --v34;
        goto LABEL_41;
      }
      v37 = v34 + 16 * v35;
      v38 = v32 << v36;
      if ( v36 == 2 )
        goto LABEL_48;
      if ( v36 == 1 )
        goto LABEL_49;
      if ( v36 == 3 )
        break;
      switch ( v36 )
      {
        case 0LL:
          break;
        default:
          __fastfail(0x25u);
      }
LABEL_50:
      *((_WORD *)a1 + v38 + 29734) = v37;
      --v32;
      v35 = *((unsigned __int16 *)a1 + v35 + 28694);
    }
    *((_WORD *)a1 + v38 + 29741) = v37;
    *((_WORD *)a1 + v38 + 29740) = v37;
    *((_WORD *)a1 + v38 + 29739) = v37;
    *((_WORD *)a1 + v38 + 29738) = v37;
LABEL_48:
    *((_WORD *)a1 + v38 + 29737) = v37;
    *((_WORD *)a1 + v38 + 29736) = v37;
LABEL_49:
    *((_WORD *)a1 + v38 + 29735) = v37;
    goto LABEL_50;
  }
  return result;
}

```

## disassembly

```asm
0x18000b2d0  push    rbx
0x18000b2d2  push    rbp
0x18000b2d3  push    rsi
0x18000b2d4  push    rdi
0x18000b2d5  push    r14
0x18000b2d7  sub     rsp, 20h
0x18000b2db  lea     rsi, [rcx+1410h]
0x18000b2e2  mov     rbx, rcx
0x18000b2e5  add     rcx, 0D428h; void *
0x18000b2ec  xor     edx, edx; Val
0x18000b2ee  mov     r8d, 202h; Size
0x18000b2f4  mov     rdi, rsi
0x18000b2f7  call    memset_0
0x18000b2fc  lea     rcx, [rbx+0D62Ah]; void *
0x18000b303  xor     edx, edx; Val
0x18000b305  mov     r8d, 202h; Size
0x18000b30b  call    memset_0
0x18000b310  mov     r11d, [rbx]
0x18000b313  xor     r14d, r14d
0x18000b316  mov     edx, r14d
0x18000b319  test    r11, r11
0x18000b31c  jz      short loc_18000B353
0x18000b31e  xchg    ax, ax
0x18000b320  mov     ecx, [rbx+rdx*4+0Ch]
0x18000b324  mov     [rdi], ecx
0x18000b326  movzx   eax, cl
0x18000b329  shr     ecx, 8
0x18000b32c  inc     eax
0x18000b32e  inc     ecx
0x18000b330  inc     word ptr [rbx+rax*2+0D428h]
0x18000b338  inc     word ptr [rbx+rcx*2+0D62Ah]
0x18000b340  mov     [rdi+10h], edx
0x18000b343  inc     rdx
0x18000b346  mov     [rdi+8], r14
0x18000b34a  add     rdi, 18h
0x18000b34e  cmp     rdx, r11
0x18000b351  jb      short loc_18000B320
0x18000b353  mov     ebp, 1
0x18000b358  mov     ecx, ebp
0x18000b35a  nop     word ptr [rax+rax+00h]
0x18000b360  movzx   eax, word ptr [rbx+rcx*2+0D426h]
0x18000b368  add     [rbx+rcx*2+0D428h], ax
0x18000b370  movzx   eax, word ptr [rbx+rcx*2+0D628h]
0x18000b378  add     [rbx+rcx*2+0D62Ah], ax
0x18000b380  inc     rcx
0x18000b383  cmp     rcx, 100h
0x18000b38a  jb      short loc_18000B360
0x18000b38c  mov     rdx, rsi
0x18000b38f  cmp     rsi, rdi
0x18000b392  jnb     short loc_18000B3CB
0x18000b394  nop     dword ptr [rax+00h]
0x18000b398  nop     dword ptr [rax+rax+00000000h]
0x18000b3a0  movzx   eax, byte ptr [rdx]
0x18000b3a3  movzx   ecx, word ptr [rbx+rax*2+0D428h]
0x18000b3ab  movzx   eax, word ptr [rdx+10h]
0x18000b3af  mov     [rbx+rcx*2+0D82Ch], ax
0x18000b3b7  movzx   eax, byte ptr [rdx]
0x18000b3ba  add     rdx, 18h
0x18000b3be  inc     word ptr [rbx+rax*2+0D428h]
0x18000b3c6  cmp     rdx, rdi
0x18000b3c9  jb      short loc_18000B3A0
0x18000b3cb  mov     r10, r14
0x18000b3ce  test    r11, r11
0x18000b3d1  jz      short loc_18000B41D
0x18000b3d3  movzx   r8d, word ptr [rbx+r10*2+0D82Ch]
0x18000b3dc  inc     r10
0x18000b3df  mov     r9d, [rbx+r8*4+0Ch]
0x18000b3e4  mov     eax, r9d
0x18000b3e7  shr     rax, 8
0x18000b3eb  lea     rcx, [rbx+rax*2]
0x18000b3ef  movzx   edx, word ptr [rcx+0D62Ah]
0x18000b3f6  lea     eax, [rdx+1]
0x18000b3f9  mov     [rcx+0D62Ah], ax
0x18000b400  lea     rax, [rdx+rdx*2]
0x18000b404  mov     [rbx+rax*8+1420h], r8d
0x18000b40c  lea     rax, [rdx+rdx*2]
0x18000b410  mov     [rbx+rax*8+1410h], r9d
0x18000b418  cmp     r10, r11
0x18000b41b  jb      short loc_18000B3D3
0x18000b41d  mov     r8, rdi
0x18000b420  lea     r9, [rbx+1428h]
0x18000b427  mov     rdx, rdi
0x18000b42a  lea     rcx, [rbx+1440h]
0x18000b431  mov     rdi, r8
0x18000b434  mov     [rdx+8], rsi
0x18000b438  mov     [rdx+10h], r9
0x18000b43c  mov     eax, [r9]
0x18000b43f  add     eax, [rsi]
0x18000b441  mov     [rdx], eax
0x18000b443  cmp     rcx, r8
0x18000b446  jz      short loc_18000B4A0
0x18000b448  add     rdi, 18h
0x18000b44c  cmp     rcx, r8
0x18000b44f  jz      short loc_18000B486
0x18000b451  cmp     rdx, rdi
0x18000b454  jnb     short loc_18000B45C
0x18000b456  mov     eax, [rcx]
0x18000b458  cmp     [rdx], eax
0x18000b45a  jb      short loc_18000B486
0x18000b45c  mov     [rdi+8], rcx
0x18000b460  mov     eax, [rcx]
0x18000b462  add     rcx, 18h
0x18000b466  mov     [rdi], eax
0x18000b468  cmp     rcx, r8
0x18000b46b  jz      short loc_18000B492
0x18000b46d  cmp     rdx, rdi
0x18000b470  jnb     short loc_18000B478
0x18000b472  mov     eax, [rcx]
0x18000b474  cmp     [rdx], eax
0x18000b476  jb      short loc_18000B492
0x18000b478  mov     [rdi+10h], rcx
0x18000b47c  mov     eax, [rcx]
0x18000b47e  add     [rdi], eax
0x18000b480  add     rcx, 18h
0x18000b484  jmp     short loc_18000B443
0x18000b486  mov     [rdi+8], rdx
0x18000b48a  mov     eax, [rdx]
0x18000b48c  add     rdx, 18h
0x18000b490  jmp     short loc_18000B466
0x18000b492  mov     [rdi+10h], rdx
0x18000b496  mov     eax, [rdx]
0x18000b498  add     [rdi], eax
0x18000b49a  add     rdx, 18h
0x18000b49e  jmp     short loc_18000B443
0x18000b4a0  cmp     rdx, rdi
0x18000b4a3  jnz     short loc_18000B448
0x18000b4a5  mov     rdx, rdi
0x18000b4a8  xor     ecx, ecx
0x18000b4aa  call    TraverseHuffmanTree
0x18000b4af  cmp     dword ptr [rbx+1418h], 0Fh
0x18000b4b6  ja      loc_18000BA63
0x18000b4bc  cmp     rsi, r8
0x18000b4bf  jnb     short loc_18000B4D8
0x18000b4c1  mov     ecx, [rsi+10h]
0x18000b4c4  movzx   eax, byte ptr [rsi+8]
0x18000b4c8  add     rsi, 18h
0x18000b4cc  mov     [rcx+rbx+100Ch], al
0x18000b4d3  cmp     rsi, r8
0x18000b4d6  jb      short loc_18000B4C1
0x18000b4d8  mov     dword ptr [rbx+0E82Ch], 4000400h
0x18000b4e2  mov     edi, 400h
0x18000b4e7  mov     dword ptr [rbx+0E830h], 4000400h
0x18000b4f1  mov     rdx, r14
0x18000b4f4  mov     dword ptr [rbx+0E834h], 4000400h
0x18000b4fe  mov     dword ptr [rbx+0E838h], 4000400h
0x18000b508  mov     dword ptr [rbx+0E83Ch], 4000400h
0x18000b512  mov     dword ptr [rbx+0E840h], 4000400h
0x18000b51c  mov     dword ptr [rbx+0E844h], 4000400h
0x18000b526  mov     dword ptr [rbx+0E848h], 4000400h
0x18000b530  test    r11, r11
0x18000b533  jz      short loc_18000B56A
0x18000b535  nop     word ptr [rax+rax+00000000h]
0x18000b540  movzx   eax, byte ptr [rbx+rdx+100Ch]
0x18000b548  lea     rcx, [rbx+rax*2]
0x18000b54c  movzx   eax, word ptr [rcx+0E82Ch]
0x18000b553  mov     [rbx+rdx*2+0E02Ch], ax
0x18000b55b  mov     [rcx+0E82Ch], dx
0x18000b562  inc     rdx
0x18000b565  cmp     rdx, r11
0x18000b568  jb      short loc_18000B540
0x18000b56a  movzx   eax, r11w
0x18000b56e  lea     r8d, [r11+r11]
0x18000b572  neg     ax
0x18000b575  add     r11w, r11w
0x18000b579  add     ax, ax
0x18000b57c  mov     ecx, 0Fh
0x18000b581  sub     bp, r11w
0x18000b585  cmp     rcx, 0Ah
0x18000b589  jbe     short loc_18000B5E3
0x18000b58b  cmp     bp, ax
0x18000b58e  jl      loc_18000BACF
0x18000b594  jz      loc_18000B721
0x18000b59a  movzx   edx, word ptr [rbx+rcx*2+0E82Ch]
0x18000b5a2  lea     ebp, [rax+1]
0x18000b5a5  cmp     rdx, rdi
0x18000b5a8  jnz     short loc_18000B5B6
0x18000b5aa  movzx   eax, r8w
0x18000b5ae  neg     ax
0x18000b5b1  dec     rcx
0x18000b5b4  jmp     short loc_18000B585
0x18000b5b6  lea     r9, [r8+7826h]
0x18000b5bd  movzx   eax, dx
0x18000b5c0  lea     r9, [r9-1]
0x18000b5c4  shl     ax, 4
0x18000b5c8  dec     r8
0x18000b5cb  add     ax, cx
0x18000b5ce  mov     [rbx+r9*2+2], ax
0x18000b5d4  movzx   edx, word ptr [rbx+rdx*2+0E02Ch]
0x18000b5dc  cmp     rdx, rdi
0x18000b5df  jz      short loc_18000B5AA
0x18000b5e1  jmp     short loc_18000B5BD
0x18000b5e3  mov     r10d, 3FFh
0x18000b5e9  cmp     bp, ax
0x18000b5ec  jge     short loc_18000B607
0x18000b5ee  mov     ecx, 7825h
0x18000b5f3  mov     [rbx+rcx*2], bp
0x18000b5f7  lea     rcx, [rcx-1]
0x18000b5fb  add     bp, 2
0x18000b5ff  dec     r10
0x18000b602  cmp     bp, ax
0x18000b605  jl      short loc_18000B5F3
0x18000b607  mov     r11d, 0Ah
0x18000b60d  lea     rsi, __ImageBase
0x18000b614  test    r11, r11
0x18000b617  jz      loc_18000B721
0x18000b61d  movzx   r9d, word ptr [rbx+r11*2+0E82Ch]
0x18000b626  mov     ecx, 0Ah
0x18000b62b  sub     rcx, r11
0x18000b62e  xchg    ax, ax
0x18000b630  cmp     r9, rdi
0x18000b633  jz      loc_18000B70F
0x18000b639  movzx   edx, r9w
0x18000b63d  mov     r8, r10
0x18000b640  shl     dx, 4
0x18000b644  add     dx, r11w
0x18000b648  shl     r8, cl
0x18000b64b  cmp     rcx, 2
0x18000b64f  jz      short loc_18000B681
0x18000b651  cmp     rcx, 1
0x18000b655  jz      short loc_18000B693
0x18000b657  cmp     rcx, 3
0x18000b65b  jnz     short loc_18000B6B6
0x18000b65d  mov     [rbx+r8*2+0E85Ah], dx
0x18000b666  mov     [rbx+r8*2+0E858h], dx
0x18000b66f  mov     [rbx+r8*2+0E856h], dx
0x18000b678  mov     [rbx+r8*2+0E854h], dx
0x18000b681  mov     [rbx+r8*2+0E852h], dx
0x18000b68a  mov     [rbx+r8*2+0E850h], dx
0x18000b693  mov     [rbx+r8*2+0E84Eh], dx
0x18000b69c  mov     [rbx+r8*2+0E84Ch], dx; jumptable 000000018000B6C6 case 0
0x18000b6a5  dec     r10
0x18000b6a8  movzx   r9d, word ptr [rbx+r9*2+0E02Ch]
0x18000b6b1  jmp     loc_18000B630
0x18000b6b6  cmp     rcx, 9; switch 1 cases
0x18000b6ba  ja      short def_18000B6C6; jumptable 000000018000B6C6 default case
0x18000b6bc  mov     eax, ds:(jpt_18000B6C6 - 180000000h)[rsi+rcx*4]
0x18000b6c3  add     rax, rsi
0x18000b6c6  jmp     rax; switch jump
0x18000b6c8  mov     eax, 4
0x18000b6cd  nop     dword ptr [rax]
0x18000b6d0  mov     [rbx+r8*2+0E84Ch], dx
0x18000b6d9  mov     [rbx+r8*2+0E84Eh], dx
0x18000b6e2  mov     [rbx+r8*2+0E850h], dx
0x18000b6eb  mov     [rbx+r8*2+0E852h], dx
0x18000b6f4  lea     r8, [r8+4]
0x18000b6f8  sub     rax, 1
0x18000b6fc  jnz     short loc_18000B6D0
0x18000b6fe  movzx   r9d, word ptr [rbx+r9*2+0E02Ch]
0x18000b707  dec     r10
0x18000b70a  jmp     loc_18000B630
0x18000b70f  shr     r10, 1
0x18000b712  dec     r11
0x18000b715  jmp     loc_18000B614
0x18000b71a  mov     ecx, 25h ; '%'; jumptable 000000018000B6C6 default case
0x18000b71f  int     29h; Win8: RtlFailFast(ecx)
0x18000b721  add     rsp, 20h
0x18000b725  pop     r14
0x18000b727  pop     rdi
0x18000b728  pop     rsi
0x18000b729  pop     rbp
0x18000b72a  pop     rbx
0x18000b72b  retn
0x18000b72c  mov     eax, 8
0x18000b731  mov     [rbx+r8*2+0E84Ch], dx
0x18000b73a  mov     [rbx+r8*2+0E84Eh], dx
0x18000b743  mov     [rbx+r8*2+0E850h], dx
0x18000b74c  mov     [rbx+r8*2+0E852h], dx
0x18000b755  lea     r8, [r8+4]
0x18000b759  sub     rax, 1
0x18000b75d  jnz     short loc_18000B731
0x18000b75f  movzx   r9d, word ptr [rbx+r9*2+0E02Ch]
0x18000b768  dec     r10
0x18000b76b  jmp     loc_18000B630
0x18000b770  mov     eax, 40h ; '@'
0x18000b775  mov     [rbx+r8*2+0E84Ch], dx
0x18000b77e  mov     [rbx+r8*2+0E84Eh], dx
0x18000b787  mov     [rbx+r8*2+0E850h], dx
0x18000b790  mov     [rbx+r8*2+0E852h], dx
0x18000b799  lea     r8, [r8+4]
0x18000b79d  sub     rax, 1
0x18000b7a1  jnz     short loc_18000B775
0x18000b7a3  movzx   r9d, word ptr [rbx+r9*2+0E02Ch]
0x18000b7ac  dec     r10
0x18000b7af  jmp     loc_18000B630
0x18000b7b4  mov     eax, 8
0x18000b7b9  nop     dword ptr [rax+00000000h]
0x18000b7c0  mov     [rbx+r8*2+0E84Ch], dx
0x18000b7c9  mov     [rbx+r8*2+0E84Eh], dx
0x18000b7d2  mov     [rbx+r8*2+0E850h], dx
0x18000b7db  mov     [rbx+r8*2+0E852h], dx
0x18000b7e4  mov     [rbx+r8*2+0E854h], dx
0x18000b7ed  mov     [rbx+r8*2+0E856h], dx
0x18000b7f6  mov     [rbx+r8*2+0E858h], dx
0x18000b7ff  mov     [rbx+r8*2+0E85Ah], dx
0x18000b808  mov     [rbx+r8*2+0E85Ch], dx
0x18000b811  mov     [rbx+r8*2+0E85Eh], dx
0x18000b81a  mov     [rbx+r8*2+0E860h], dx
0x18000b823  mov     [rbx+r8*2+0E862h], dx
0x18000b82c  mov     [rbx+r8*2+0E864h], dx
0x18000b835  mov     [rbx+r8*2+0E866h], dx
  ... truncated ...
```
