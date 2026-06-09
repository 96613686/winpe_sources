# SortSampleSuffixesUsingRawData

- ea: `0x18001a20c`
- end: `0x18001a6ec`
- name: `SortSampleSuffixesUsingRawData`
- size: `1248`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180017ba0`
- `0x18001a20c`

## callees

- `0x180019dc8`
- `0x18001a20c`
- `0x18001a714`

## pseudocode

```c
__int64 __fastcall SortSampleSuffixesUsingRawData(__int64 *a1, __int64 a2, int a3, int a4, int a5)
{
  __int64 result; // rax
  __int64 v9; // rdi
  int v10; // r8d
  int v11; // r10d
  int v12; // ebp
  int v13; // r13d
  unsigned __int8 v14; // r15
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r9
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // r11
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // ecx
  int v24; // r11d
  int v25; // edi
  int v26; // r12d
  int i; // r15d
  __int64 v28; // rdx
  int v29; // eax
  int v30; // r8d
  int v31; // r11d
  int j; // ebp
  __int64 v33; // rdx
  int v34; // eax
  int v35; // r8d
  int v36; // r10d
  int v37; // r13d
  int v38; // r15d
  int v39; // r9d
  int k; // ebp
  __int64 v41; // r8
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rcx
  int m; // r10d
  __int64 v46; // rdx
  __int64 v47; // r8
  int v48; // eax
  __int64 v49; // r8
  __int64 v50; // rax
  int v51; // ecx
  int v52; // ebp
  __int64 v53; // r8
  __int64 v54; // rcx
  __int64 v55; // rdx
  int v56; // eax
  bool v57; // cc
  int v58; // r9d
  int v59; // r14d
  int v60; // r8d
  int v61; // esi
  int v62; // r8d
  int v63; // esi

  result = a2;
  do
  {
    v9 = result + a5;
    if ( a4 - a3 > 64 )
      Sort3UsingString((_DWORD)a1, v9, (a3 + a4) / 2, a3, a4 - 1);
    v10 = a3;
    v11 = a4;
    v12 = a3;
    v13 = a4;
    v14 = *(_BYTE *)(*(unsigned int *)(a1[1] + 4LL * *(unsigned int *)(*a1 + 4LL * a3)) + v9);
LABEL_5:
    while ( ++v10 != v11 )
    {
      v15 = *a1;
      v16 = a1[1];
      v17 = *(unsigned int *)(*a1 + 4LL * v10);
      v18 = *(unsigned int *)(v16 + 4 * v17);
      if ( *(_BYTE *)(v18 + v9) > v14 )
      {
        while ( --v11 != v10 )
        {
          v20 = *(unsigned int *)(v15 + 4LL * v11);
          v21 = *(unsigned int *)(v16 + 4 * v20);
          if ( *(_BYTE *)(v21 + v9) < v14 )
          {
            v23 = *(_DWORD *)(v15 + 4LL * v10);
            *(_DWORD *)(v15 + 4LL * v10) = v20;
            *(_DWORD *)(*a1 + 4LL * v11) = v23;
            goto LABEL_5;
          }
          if ( *(_BYTE *)(v21 + v9) == v14 )
          {
            v22 = v13--;
            *(_DWORD *)(v15 + 4LL * v11) = *(_DWORD *)(v15 + 4 * v22 - 4);
            *(_DWORD *)(*a1 + 4 * v22 - 4) = v20;
            v15 = *a1;
            v16 = a1[1];
          }
        }
        break;
      }
      if ( *(_BYTE *)(v18 + v9) == v14 )
      {
        v19 = v12++;
        *(_DWORD *)(v15 + 4LL * v10) = *(_DWORD *)(v15 + 4 * v19 + 4);
        *(_DWORD *)(*a1 + 4 * v19 + 4) = v17;
      }
    }
    v24 = v12 - a3 + 1;
    v25 = v11 - v24;
    v26 = v11 - (v12 + 1);
    if ( v24 >= v26 )
      v24 = v11 - (v12 + 1);
    for ( i = 0; i < v24; *(_DWORD *)(*a1 + 4LL * v29 - 4) = v30 )
    {
      v28 = i + a3;
      v29 = v11 - i++;
      v30 = *(_DWORD *)(*a1 + 4 * v28);
      *(_DWORD *)(*a1 + 4 * v28) = *(_DWORD *)(*a1 + 4LL * v29 - 4);
    }
    v31 = a4 - v13;
    if ( a4 - v13 >= v13 - v11 )
      v31 = v13 - v11;
    for ( j = 0; j < v31; *(_DWORD *)(*a1 + 4LL * v34 - 4) = v35 )
    {
      v33 = v11 + j;
      v34 = a4 - j++;
      v35 = *(_DWORD *)(*a1 + 4 * v33);
      *(_DWORD *)(*a1 + 4 * v33) = *(_DWORD *)(*a1 + 4LL * v34 - 4);
    }
    v36 = v11 - v13;
    v37 = a5 + 1;
    v38 = v36 + a4;
    v39 = v36 + a4;
    for ( k = v36 + a4 - 1; k >= v25; --k )
    {
      v41 = *a1;
      v42 = *(unsigned int *)(*a1 + 4LL * k);
      if ( *(_DWORD *)(a1[1] + 4LL * (unsigned int)(v42 - 1)) - *(_DWORD *)(a1[1] + 4 * v42) >= v37 )
        break;
      if ( (_DWORD)v42 == 1 )
      {
        v43 = v39--;
        v44 = v43;
        LODWORD(v43) = *(_DWORD *)(v41 + 4 * v43 - 4);
        *(_DWORD *)(v41 + 4 * v44 - 4) = 1;
        *(_DWORD *)(v41 + 4LL * k) = v43;
      }
    }
    for ( m = k - 1; m >= v25; --m )
    {
      v46 = *a1;
      v47 = *(unsigned int *)(*a1 + 4LL * m);
      if ( *(_DWORD *)(a1[1] + 4LL * (unsigned int)(v47 - 1)) - *(_DWORD *)(a1[1] + 4 * v47) < v37 )
      {
        v48 = *(_DWORD *)(v46 + 4LL * k);
        *(_DWORD *)(v46 + 4LL * k) = v47;
        *(_DWORD *)(v46 + 4LL * m) = v48;
        if ( (_DWORD)v47 == 1 )
        {
          v49 = *a1;
          v50 = v39--;
          v51 = *(_DWORD *)(*a1 + 4 * v50 - 4);
          *(_DWORD *)(v49 + 4 * v50 - 4) = *(_DWORD *)(*a1 + 4LL * k);
          *(_DWORD *)(v49 + 4LL * k) = v51;
        }
        --k;
      }
    }
    v52 = k + 1;
    v53 = (unsigned int)v52;
    if ( v52 < v39 )
    {
      do
      {
        v54 = (int)v53;
        v53 = (unsigned int)(v53 + 1);
        *(_DWORD *)(a1[2] + 4LL * *(unsigned int *)(*a1 + 4 * v54)) = v52;
      }
      while ( (int)v53 < v39 );
    }
    if ( v39 < v38 )
      *(_DWORD *)(a1[2] + 4LL * *(unsigned int *)(*a1 + 4LL * v39)) = v39;
    if ( v39 - v52 > 1 )
    {
      v55 = (unsigned int)(v39 - 1);
      *(_DWORD *)(*a1 + 4LL * (int)(*((_DWORD *)a1 + 587))++) = v55;
      SuffixArrayJobIteratorMakeValid(a1 + 293, v55, v53);
    }
    v56 = a4 - v38;
    v57 = a4 - v38 <= v26;
    if ( a4 - v38 < v26 )
    {
      if ( v26 > v52 - v25 )
      {
        if ( v56 <= 1 )
        {
          v57 = v38 < a4;
          v59 = a2;
          if ( v57 )
            *(_DWORD *)(a1[2] + 4LL * *(unsigned int *)(*a1 + 4LL * v38)) = v38;
        }
        else
        {
          v58 = a4;
          v59 = a2;
          SortSampleSuffixesUsingRawData((_DWORD)a1, a2, v38, v58, a5);
        }
        if ( v52 - v25 <= 1 )
        {
          if ( v25 < v52 )
            *(_DWORD *)(a1[2] + 4LL * *(unsigned int *)(*a1 + 4LL * v25)) = v25;
        }
        else
        {
          SortSampleSuffixesUsingRawData((_DWORD)a1, v59, v25, v52, v37);
        }
        a4 = v25;
        goto LABEL_74;
      }
      v57 = v56 <= v26;
    }
    if ( v57 || v56 <= v52 - v25 )
    {
      if ( v25 - a3 <= 1 )
      {
        if ( a3 < v25 )
          *(_DWORD *)(a1[2] + 4LL * *(unsigned int *)(*a1 + 4LL * a3)) = a3;
        v63 = a2;
      }
      else
      {
        v62 = a3;
        v63 = a2;
        SortSampleSuffixesUsingRawData((_DWORD)a1, a2, v62, v25, a5);
      }
      if ( a4 - v38 <= 1 )
      {
        if ( v38 < a4 )
          *(_DWORD *)(a1[2] + 4LL * *(unsigned int *)(*a1 + 4LL * v38)) = v38;
      }
      else
      {
        SortSampleSuffixesUsingRawData((_DWORD)a1, v63, v38, a4, a5);
      }
      a3 = v25;
      ++a5;
      a4 = v52;
    }
    else
    {
      if ( v25 - a3 <= 1 )
      {
        if ( a3 < v25 )
          *(_DWORD *)(a1[2] + 4LL * *(unsigned int *)(*a1 + 4LL * a3)) = a3;
        v61 = a2;
      }
      else
      {
        v60 = a3;
        v61 = a2;
        SortSampleSuffixesUsingRawData((_DWORD)a1, a2, v60, v25, a5);
      }
      if ( v52 - v25 <= 1 )
      {
        if ( v25 < v52 )
          *(_DWORD *)(a1[2] + 4LL * *(unsigned int *)(*a1 + 4LL * v25)) = v25;
      }
      else
      {
        SortSampleSuffixesUsingRawData((_DWORD)a1, v61, v25, v52, v37);
      }
      a3 = v38;
    }
LABEL_74:
    result = a2;
  }
  while ( a4 - a3 >= 2 );
  if ( a3 < a4 )
  {
    result = a1[2];
    *(_DWORD *)(result + 4LL * *(unsigned int *)(*a1 + 4LL * a3)) = a3;
  }
  return result;
}

```

## disassembly

```asm
0x18001a20c  mov     [rsp+arg_0], rbx
0x18001a211  mov     [rsp+arg_8], rdx
0x18001a216  push    rbp
0x18001a217  push    rsi
0x18001a218  push    rdi
0x18001a219  push    r12
0x18001a21b  push    r13
0x18001a21d  push    r14
0x18001a21f  push    r15
0x18001a221  sub     rsp, 30h
0x18001a225  mov     esi, r8d
0x18001a228  mov     r14d, r9d
0x18001a22b  mov     r8d, 2
0x18001a231  mov     rax, rdx
0x18001a234  mov     rbx, rcx
0x18001a237  movsxd  rdi, [rsp+68h+arg_20]
0x18001a23f  add     rdi, rax
0x18001a242  mov     eax, r14d
0x18001a245  sub     eax, esi
0x18001a247  cmp     eax, 40h ; '@'
0x18001a24a  jle     short loc_18001A26D
0x18001a24c  lea     eax, [rsi+r14]
0x18001a250  mov     r9d, esi
0x18001a253  cdq
0x18001a254  lea     ecx, [r14-1]
0x18001a258  idiv    r8d
0x18001a25b  mov     [rsp+68h+var_48], ecx
0x18001a25f  mov     rdx, rdi
0x18001a262  mov     r8d, eax
0x18001a265  mov     rcx, rbx
0x18001a268  call    Sort3UsingString
0x18001a26d  mov     rax, [rbx]
0x18001a270  mov     r8d, esi
0x18001a273  movsxd  rcx, esi
0x18001a276  mov     r10d, r14d
0x18001a279  mov     ebp, esi
0x18001a27b  mov     r13d, r14d
0x18001a27e  mov     edx, [rax+rcx*4]
0x18001a281  mov     rax, [rbx+8]
0x18001a285  mov     ecx, [rax+rdx*4]
0x18001a288  mov     r15b, [rcx+rdi]
0x18001a28c  inc     r8d
0x18001a28f  cmp     r8d, r10d
0x18001a292  jz      loc_18001A31D
0x18001a298  mov     rdx, [rbx]
0x18001a29b  mov     rcx, [rbx+8]
0x18001a29f  movsxd  r12, r8d
0x18001a2a2  mov     r9d, [rdx+r12*4]
0x18001a2a6  mov     eax, [rcx+r9*4]
0x18001a2aa  cmp     [rax+rdi], r15b
0x18001a2ae  ja      short loc_18001A2CC
0x18001a2b0  jnz     short loc_18001A28C
0x18001a2b2  movsxd  rax, ebp
0x18001a2b5  inc     ebp
0x18001a2b7  mov     rcx, rax
0x18001a2ba  mov     eax, [rdx+rax*4+4]
0x18001a2be  mov     [rdx+r12*4], eax
0x18001a2c2  mov     rax, [rbx]
0x18001a2c5  mov     [rax+rcx*4+4], r9d
0x18001a2ca  jmp     short loc_18001A28C
0x18001a2cc  dec     r10d
0x18001a2cf  cmp     r10d, r8d
0x18001a2d2  jz      short loc_18001A31D
0x18001a2d4  movsxd  r9, r10d
0x18001a2d7  mov     r11d, [rdx+r9*4]
0x18001a2db  mov     eax, [rcx+r11*4]
0x18001a2df  cmp     [rax+rdi], r15b
0x18001a2e3  jb      short loc_18001A309
0x18001a2e5  jnz     short loc_18001A2CC
0x18001a2e7  movsxd  rax, r13d
0x18001a2ea  dec     r13d
0x18001a2ed  mov     rcx, rax
0x18001a2f0  mov     eax, [rdx+rax*4-4]
0x18001a2f4  mov     [rdx+r9*4], eax
0x18001a2f8  mov     rax, [rbx]
0x18001a2fb  mov     [rax+rcx*4-4], r11d
0x18001a300  mov     rdx, [rbx]
0x18001a303  mov     rcx, [rbx+8]
0x18001a307  jmp     short loc_18001A2CC
0x18001a309  mov     ecx, [rdx+r12*4]
0x18001a30d  mov     [rdx+r12*4], r11d
0x18001a311  mov     rax, [rbx]
0x18001a314  mov     [rax+r9*4], ecx
0x18001a318  jmp     loc_18001A28C
0x18001a31d  sub     ebp, esi
0x18001a31f  mov     edi, r10d
0x18001a322  lea     r11d, [rbp+1]
0x18001a326  sub     edi, r11d
0x18001a329  mov     r12d, edi
0x18001a32c  sub     r12d, esi
0x18001a32f  cmp     r11d, r12d
0x18001a332  mov     [rsp+68h+arg_10], r12d
0x18001a33a  cmovge  r11d, r12d
0x18001a33e  xor     r15d, r15d
0x18001a341  test    r11d, r11d
0x18001a344  jle     short loc_18001A376
0x18001a346  mov     r9, [rbx]
0x18001a349  lea     eax, [r15+rsi]
0x18001a34d  movsxd  rdx, eax
0x18001a350  mov     eax, r10d
0x18001a353  sub     eax, r15d
0x18001a356  inc     r15d
0x18001a359  movsxd  rcx, eax
0x18001a35c  mov     r8d, [r9+rdx*4]
0x18001a360  mov     eax, [r9+rcx*4-4]
0x18001a365  mov     [r9+rdx*4], eax
0x18001a369  mov     rax, [rbx]
0x18001a36c  mov     [rax+rcx*4-4], r8d
0x18001a371  cmp     r15d, r11d
0x18001a374  jl      short loc_18001A346
0x18001a376  mov     eax, r13d
0x18001a379  mov     r11d, r14d
0x18001a37c  sub     eax, r10d
0x18001a37f  sub     r11d, r13d
0x18001a382  cmp     r11d, eax
0x18001a385  cmovge  r11d, eax
0x18001a389  xor     ebp, ebp
0x18001a38b  test    r11d, r11d
0x18001a38e  jle     short loc_18001A3BE
0x18001a390  mov     r9, [rbx]
0x18001a393  lea     eax, [r10+rbp]
0x18001a397  movsxd  rdx, eax
0x18001a39a  mov     eax, r14d
0x18001a39d  sub     eax, ebp
0x18001a39f  inc     ebp
0x18001a3a1  movsxd  rcx, eax
0x18001a3a4  mov     r8d, [r9+rdx*4]
0x18001a3a8  mov     eax, [r9+rcx*4-4]
0x18001a3ad  mov     [r9+rdx*4], eax
0x18001a3b1  mov     rax, [rbx]
0x18001a3b4  mov     [rax+rcx*4-4], r8d
0x18001a3b9  cmp     ebp, r11d
0x18001a3bc  jl      short loc_18001A390
0x18001a3be  sub     r10d, r13d
0x18001a3c1  mov     r13d, [rsp+68h+arg_20]
0x18001a3c9  inc     r13d
0x18001a3cc  lea     r15d, [r10+r14]
0x18001a3d0  mov     r9d, r15d
0x18001a3d3  lea     ebp, [r15-1]
0x18001a3d7  jmp     short loc_18001A413
0x18001a3d9  mov     rcx, [rbx+8]
0x18001a3dd  mov     r8, [rbx]
0x18001a3e0  movsxd  r10, ebp
0x18001a3e3  mov     edx, [r8+r10*4]
0x18001a3e7  lea     eax, [rdx-1]
0x18001a3ea  mov     eax, [rcx+rax*4]
0x18001a3ed  sub     eax, [rcx+rdx*4]
0x18001a3f0  cmp     eax, r13d
0x18001a3f3  jge     short loc_18001A417
0x18001a3f5  cmp     edx, 1
0x18001a3f8  jnz     short loc_18001A411
0x18001a3fa  movsxd  rax, r9d
0x18001a3fd  dec     r9d
0x18001a400  mov     rcx, rax
0x18001a403  mov     eax, [r8+rax*4-4]
0x18001a408  mov     [r8+rcx*4-4], edx
0x18001a40d  mov     [r8+r10*4], eax
0x18001a411  dec     ebp
0x18001a413  cmp     ebp, edi
0x18001a415  jge     short loc_18001A3D9
0x18001a417  lea     r10d, [rbp-1]
0x18001a41b  cmp     r10d, edi
0x18001a41e  jl      short loc_18001A483
0x18001a420  mov     rcx, [rbx+8]
0x18001a424  mov     rdx, [rbx]
0x18001a427  movsxd  r12, r10d
0x18001a42a  mov     r8d, [rdx+r12*4]
0x18001a42e  lea     eax, [r8-1]
0x18001a432  mov     eax, [rcx+rax*4]
0x18001a435  sub     eax, [rcx+r8*4]
0x18001a439  cmp     eax, r13d
0x18001a43c  jge     short loc_18001A473
0x18001a43e  movsxd  r11, ebp
0x18001a441  mov     eax, [rdx+r11*4]
0x18001a445  mov     [rdx+r11*4], r8d
0x18001a449  mov     [rdx+r12*4], eax
0x18001a44d  cmp     r8d, 1
0x18001a451  jnz     short loc_18001A471
0x18001a453  mov     r8, [rbx]
0x18001a456  movsxd  rax, r9d
0x18001a459  dec     r9d
0x18001a45c  mov     rdx, rax
0x18001a45f  mov     ecx, [r8+rax*4-4]
0x18001a464  mov     eax, [r8+r11*4]
0x18001a468  mov     [r8+rdx*4-4], eax
0x18001a46d  mov     [r8+r11*4], ecx
0x18001a471  dec     ebp
0x18001a473  dec     r10d
0x18001a476  cmp     r10d, edi
0x18001a479  jge     short loc_18001A420
0x18001a47b  mov     r12d, [rsp+68h+arg_10]
0x18001a483  inc     ebp
0x18001a485  mov     r8d, ebp
0x18001a488  cmp     ebp, r9d
0x18001a48b  jge     short loc_18001A4A5
0x18001a48d  mov     rax, [rbx]
0x18001a490  movsxd  rcx, r8d
0x18001a493  inc     r8d
0x18001a496  mov     edx, [rax+rcx*4]
0x18001a499  mov     rax, [rbx+10h]
0x18001a49d  mov     [rax+rdx*4], ebp
0x18001a4a0  cmp     r8d, r9d
0x18001a4a3  jl      short loc_18001A48D
0x18001a4a5  cmp     r9d, r15d
0x18001a4a8  jge     short loc_18001A4BB
0x18001a4aa  mov     rax, [rbx]
0x18001a4ad  movsxd  rcx, r9d
0x18001a4b0  mov     edx, [rax+rcx*4]
0x18001a4b3  mov     rax, [rbx+10h]
0x18001a4b7  mov     [rax+rdx*4], r9d
0x18001a4bb  mov     eax, r9d
0x18001a4be  sub     eax, ebp
0x18001a4c0  cmp     eax, 1
0x18001a4c3  jle     short loc_18001A4E5
0x18001a4c5  movsxd  rcx, dword ptr [rbx+92Ch]
0x18001a4cc  lea     edx, [r9-1]
0x18001a4d0  mov     rax, [rbx]
0x18001a4d3  mov     [rax+rcx*4], edx
0x18001a4d6  lea     rcx, [rbx+928h]
0x18001a4dd  inc     dword ptr [rcx+4]
0x18001a4e0  call    SuffixArrayJobIteratorMakeValid
0x18001a4e5  mov     eax, r14d
0x18001a4e8  sub     eax, r15d
0x18001a4eb  cmp     eax, r12d
0x18001a4ee  jge     loc_18001A58C
0x18001a4f4  mov     r12d, ebp
0x18001a4f7  sub     r12d, edi
0x18001a4fa  cmp     [rsp+68h+arg_10], r12d
0x18001a502  jle     short loc_18001A581
0x18001a504  cmp     eax, 1
0x18001a507  jle     short loc_18001A52C
0x18001a509  mov     eax, [rsp+68h+arg_20]
0x18001a510  mov     r9d, r14d
0x18001a513  mov     r14, [rsp+68h+arg_8]
0x18001a518  mov     r8d, r15d
0x18001a51b  mov     rdx, r14
0x18001a51e  mov     [rsp+68h+var_48], eax
0x18001a522  mov     rcx, rbx
0x18001a525  call    SortSampleSuffixesUsingRawData
0x18001a52a  jmp     short loc_18001A547
0x18001a52c  cmp     r15d, r14d
0x18001a52f  mov     r14, [rsp+68h+arg_8]
0x18001a534  jge     short loc_18001A547
0x18001a536  mov     rax, [rbx]
0x18001a539  movsxd  rcx, r15d
0x18001a53c  mov     edx, [rax+rcx*4]
0x18001a53f  mov     rax, [rbx+10h]
0x18001a543  mov     [rax+rdx*4], r15d
0x18001a547  cmp     r12d, 1
0x18001a54b  jle     short loc_18001A565
0x18001a54d  mov     r9d, ebp
0x18001a550  mov     [rsp+68h+var_48], r13d
0x18001a555  mov     r8d, edi
0x18001a558  mov     rdx, r14
0x18001a55b  mov     rcx, rbx
0x18001a55e  call    SortSampleSuffixesUsingRawData
0x18001a563  jmp     short loc_18001A579
0x18001a565  cmp     edi, ebp
0x18001a567  jge     short loc_18001A579
0x18001a569  mov     rax, [rbx]
0x18001a56c  movsxd  rcx, edi
0x18001a56f  mov     edx, [rax+rcx*4]
0x18001a572  mov     rax, [rbx+10h]
0x18001a576  mov     [rax+rdx*4], edi
0x18001a579  mov     r14d, edi
0x18001a57c  jmp     loc_18001A6A9
0x18001a581  mov     r12d, [rsp+68h+arg_10]
0x18001a589  cmp     eax, r12d
0x18001a58c  jle     loc_18001A61C
0x18001a592  mov     r12d, ebp
0x18001a595  sub     r12d, edi
0x18001a598  cmp     eax, r12d
0x18001a59b  jle     short loc_18001A61C
0x18001a59d  mov     eax, edi
0x18001a59f  sub     eax, esi
0x18001a5a1  cmp     eax, 1
0x18001a5a4  jle     short loc_18001A5C9
0x18001a5a6  mov     eax, [rsp+68h+arg_20]
0x18001a5ad  mov     r8d, esi
0x18001a5b0  mov     rsi, [rsp+68h+arg_8]
0x18001a5b5  mov     r9d, edi
0x18001a5b8  mov     rdx, rsi
0x18001a5bb  mov     [rsp+68h+var_48], eax
0x18001a5bf  mov     rcx, rbx
0x18001a5c2  call    SortSampleSuffixesUsingRawData
0x18001a5c7  jmp     short loc_18001A5E2
0x18001a5c9  cmp     esi, edi
0x18001a5cb  jge     short loc_18001A5DD
0x18001a5cd  mov     rax, [rbx]
0x18001a5d0  movsxd  rcx, esi
0x18001a5d3  mov     edx, [rax+rcx*4]
0x18001a5d6  mov     rax, [rbx+10h]
0x18001a5da  mov     [rax+rdx*4], esi
0x18001a5dd  mov     rsi, [rsp+68h+arg_8]
0x18001a5e2  cmp     r12d, 1
0x18001a5e6  jle     short loc_18001A600
0x18001a5e8  mov     r9d, ebp
0x18001a5eb  mov     [rsp+68h+var_48], r13d
0x18001a5f0  mov     r8d, edi
0x18001a5f3  mov     rdx, rsi
  ... truncated ...
```
