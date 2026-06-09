# SortSampleSuffixes

- ea: `0x180019e74`
- end: `0x18001a206`
- name: `SortSampleSuffixes`
- size: `914`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180017ba0`
- `0x180019e74`

## callees

- `0x180019d14`
- `0x180019e74`
- `0x18001a714`

## pseudocode

```c
__int64 __fastcall SortSampleSuffixes(__int64 *a1, signed int a2, signed int a3, unsigned int a4)
{
  unsigned int v5; // edi
  __int64 v7; // rcx
  __int64 v9; // rax
  __int64 v10; // r9
  int v11; // r10d
  __int64 v12; // r14
  int v13; // r8d
  __int64 v14; // r11
  __int64 v15; // r8
  int v16; // edi
  int v17; // r13d
  unsigned int v18; // r11d
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rax
  __int64 v22; // r10
  __int64 v23; // rax
  int v24; // ecx
  int v25; // r10d
  unsigned int v26; // r14d
  int v27; // r15d
  int i; // r11d
  __int64 v29; // rdx
  int v30; // eax
  int v31; // ecx
  int v32; // r10d
  int v33; // r11d
  __int64 v34; // rdx
  int v35; // eax
  signed int v36; // edi
  __int64 v37; // rdx
  int k; // r8d
  __int64 v39; // rcx
  int m; // r8d
  __int64 v41; // rcx
  int j; // r8d
  __int64 v43; // rcx
  __int64 result; // rax
  __int64 v45; // r8
  __int64 v46; // rdx
  unsigned int v47; // ecx
  __int64 v48; // rdx
  __int64 v49; // [rsp+70h] [rbp+8h]
  int v50; // [rsp+78h] [rbp+10h]

  v5 = a4;
  v7 = 4LL * (int)a4;
  v49 = v7;
  do
  {
    v9 = a1[2];
    v10 = *a1;
    v11 = a3 - a2;
    v12 = v9 + v7;
    if ( a3 - a2 == 2 )
    {
      v45 = *(unsigned int *)(v10 + 4LL * a2 + 4);
      v46 = *(unsigned int *)(v10 + 4LL * a2);
      v47 = *(_DWORD *)(v12 + 4 * v45);
      if ( *(_DWORD *)(v12 + 4 * v46) >= v47 )
      {
        if ( *(_DWORD *)(v12 + 4 * v46) == v47 )
        {
          *(_DWORD *)(v9 + 4 * v46) = a2;
          v48 = (unsigned int)(a3 - 1);
          *(_DWORD *)(a1[2] + 4 * v45) = a2;
          *(_DWORD *)(*a1 + 4LL * (int)(*((_DWORD *)a1 + 587))++) = v48;
          return SuffixArrayJobIteratorMakeValid(a1 + 293, v48, v45);
        }
        else
        {
          *(_DWORD *)(v10 + 4LL * a2) = v45;
          *(_DWORD *)(*a1 + 4LL * a2 + 4) = v46;
          *(_DWORD *)(a1[2] + 4 * v46) = a2 + 1;
          result = a1[2];
          *(_DWORD *)(result + 4 * v45) = a2;
        }
      }
      else
      {
        *(_DWORD *)(v9 + 4 * v46) = a2;
        result = a1[2];
        *(_DWORD *)(result + 4 * v45) = a2 + 1;
      }
      return result;
    }
    v13 = *(_DWORD *)(v10 + 4LL * a2);
    v14 = (a2 + a3) / 2;
    *(_DWORD *)(v10 + 4LL * a2) = *(_DWORD *)(v10 + 4 * v14);
    *(_DWORD *)(*a1 + 4 * v14) = v13;
    if ( v11 > 16 )
      Sort3UsingSampleRank((_DWORD)a1, v11 / 4 + a2, a2, v11 / 4 + v14, v5);
    LODWORD(v15) = a2;
    v16 = a3;
    v50 = a3;
    v17 = a2;
    v18 = *(_DWORD *)(v12 + 4LL * *(unsigned int *)(*a1 + 4LL * a2));
LABEL_6:
    while ( 1 )
    {
      v15 = (unsigned int)(v15 + 1);
      if ( (_DWORD)v15 == v16 )
        break;
      v19 = *a1;
      v20 = *(int *)(*a1 + 4LL * (int)v15);
      if ( *(_DWORD *)(v12 + 4 * v20) > v18 )
      {
        while ( (_DWORD)v15 != --v16 )
        {
          v22 = *(int *)(v19 + 4LL * v16);
          if ( *(_DWORD *)(v12 + 4 * v22) < v18 )
          {
            v24 = *(_DWORD *)(v19 + 4LL * (int)v15);
            *(_DWORD *)(v19 + 4LL * (int)v15) = v22;
            *(_DWORD *)(*a1 + 4LL * v16) = v24;
            goto LABEL_6;
          }
          if ( *(_DWORD *)(v12 + 4 * v22) == v18 )
          {
            v23 = v50--;
            *(_DWORD *)(v19 + 4LL * v16) = *(_DWORD *)(v19 + 4 * v23 - 4);
            *(_DWORD *)(*a1 + 4 * v23 - 4) = v22;
            v19 = *a1;
          }
        }
        break;
      }
      if ( *(_DWORD *)(v12 + 4 * v20) == v18 )
      {
        v21 = v17++;
        *(_DWORD *)(v19 + 4LL * (int)v15) = *(_DWORD *)(v19 + 4 * v21 + 4);
        *(_DWORD *)(*a1 + 4 * v21 + 4) = v20;
      }
    }
    v25 = v17 - a2 + 1;
    v26 = v16 - v25;
    v27 = v16 - (v17 + 1);
    if ( v25 >= v27 )
      v25 = v16 - (v17 + 1);
    for ( i = 0; i < v25; *(_DWORD *)(*a1 + 4LL * v30 - 4) = v15 )
    {
      v29 = i + a2;
      v30 = v16 - i++;
      v15 = *(unsigned int *)(*a1 + 4 * v29);
      *(_DWORD *)(*a1 + 4 * v29) = *(_DWORD *)(*a1 + 4LL * v30 - 4);
    }
    v31 = v50;
    v32 = a3 - v50;
    if ( a3 - v50 >= v50 - v16 )
      v32 = v50 - v16;
    v33 = 0;
    if ( v32 > 0 )
    {
      do
      {
        v34 = v33 + v16;
        v35 = a3 - v33++;
        v15 = *(unsigned int *)(*a1 + 4 * v34);
        *(_DWORD *)(*a1 + 4 * v34) = *(_DWORD *)(*a1 + 4LL * v35 - 4);
        *(_DWORD *)(*a1 + 4LL * v35 - 4) = v15;
      }
      while ( v33 < v32 );
      v31 = v50;
    }
    v36 = a3 + v16 - v31;
    if ( (int)(v36 - v26) > 1 )
    {
      v37 = (unsigned int)(v36 - 1);
      *(_DWORD *)(*a1 + 4LL * (int)(*((_DWORD *)a1 + 587))++) = v37;
      SuffixArrayJobIteratorMakeValid(a1 + 293, v37, v15);
    }
    if ( v27 >= a3 - v36 )
    {
      if ( a3 - v36 <= 1 )
      {
        if ( v36 < a3 )
          *(_DWORD *)(a1[2] + 4LL * *(unsigned int *)(*a1 + 4LL * v36)) = v36;
      }
      else
      {
        SortSampleSuffixes(a1, (unsigned int)v36, (unsigned int)a3, a4);
      }
      for ( j = v26; j < v36; *(_DWORD *)(a1[2] + 4LL * *(unsigned int *)(*a1 + 4 * v43)) = v26 )
        v43 = j++;
      a3 = v26;
    }
    else
    {
      for ( k = v26; k < v36; *(_DWORD *)(a1[2] + 4LL * *(unsigned int *)(*a1 + 4 * v39)) = v26 )
        v39 = k++;
      for ( m = v36; m < a3; *(_DWORD *)(a1[2] + 4LL * *(unsigned int *)(*a1 + 4 * v41)) = v36 )
        v41 = m++;
      if ( v27 <= 1 )
      {
        if ( a2 < (int)v26 )
          *(_DWORD *)(a1[2] + 4LL * *(unsigned int *)(*a1 + 4LL * a2)) = a2;
      }
      else
      {
        SortSampleSuffixes(a1, (unsigned int)a2, v26, a4);
      }
      a2 = v36;
    }
    v5 = a4;
    v7 = v49;
    result = (unsigned int)(a3 - a2);
  }
  while ( (int)result >= 2 );
  if ( a2 < a3 )
  {
    result = a1[2];
    *(_DWORD *)(result + 4LL * *(unsigned int *)(*a1 + 4LL * a2)) = a2;
  }
  return result;
}

```

## disassembly

```asm
0x180019e74  mov     [rsp+arg_10], rbx
0x180019e79  mov     [rsp+arg_18], r9d
0x180019e7e  push    rbp
0x180019e7f  push    rsi
0x180019e80  push    rdi
0x180019e81  push    r12
0x180019e83  push    r13
0x180019e85  push    r14
0x180019e87  push    r15
0x180019e89  sub     rsp, 30h
0x180019e8d  mov     rbx, rcx
0x180019e90  movsxd  rdi, r9d
0x180019e93  mov     rcx, rdi
0x180019e96  mov     ebp, r8d
0x180019e99  shl     rcx, 2
0x180019e9d  mov     esi, edx
0x180019e9f  mov     [rsp+68h+arg_0], rcx
0x180019ea4  mov     r8d, 2
0x180019eaa  mov     rax, [rbx+10h]
0x180019eae  mov     r10d, ebp
0x180019eb1  mov     r9, [rbx]
0x180019eb4  sub     r10d, esi
0x180019eb7  movsxd  r12, esi
0x180019eba  lea     r14, [rax+rcx]
0x180019ebe  cmp     r10d, r8d
0x180019ec1  jz      loc_18001A17F
0x180019ec7  lea     eax, [rsi+rbp]
0x180019eca  cdq
0x180019ecb  idiv    r8d
0x180019ece  mov     r8d, [r9+r12*4]
0x180019ed2  movsxd  r11, eax
0x180019ed5  mov     ecx, [r9+r11*4]
0x180019ed9  mov     [r9+r12*4], ecx
0x180019edd  mov     rcx, [rbx]
0x180019ee0  mov     [rcx+r11*4], r8d
0x180019ee4  cmp     r10d, 10h
0x180019ee8  jle     short loc_180019F0B
0x180019eea  mov     eax, r10d
0x180019eed  mov     [rsp+68h+var_48], edi
0x180019ef1  cdq
0x180019ef2  mov     ecx, 4
0x180019ef7  idiv    ecx
0x180019ef9  mov     r8d, esi
0x180019efc  mov     rcx, rbx
0x180019eff  lea     r9d, [rax+r11]
0x180019f03  lea     edx, [rax+rsi]
0x180019f06  call    Sort3UsingSampleRank
0x180019f0b  mov     rax, [rbx]
0x180019f0e  mov     r8d, esi
0x180019f11  mov     edi, ebp
0x180019f13  mov     [rsp+68h+arg_8], ebp
0x180019f17  mov     r13d, esi
0x180019f1a  mov     ecx, [rax+r12*4]
0x180019f1e  mov     r11d, [r14+rcx*4]
0x180019f22  inc     r8d
0x180019f25  cmp     r8d, edi
0x180019f28  jz      short loc_180019FA7
0x180019f2a  mov     rdx, [rbx]
0x180019f2d  movsxd  r15, r8d
0x180019f30  movsxd  r9, dword ptr [rdx+r15*4]
0x180019f34  cmp     [r14+r9*4], r11d
0x180019f38  ja      short loc_180019F57
0x180019f3a  jnz     short loc_180019F22
0x180019f3c  movsxd  rax, r13d
0x180019f3f  inc     r13d
0x180019f42  mov     rcx, rax
0x180019f45  mov     eax, [rdx+rax*4+4]
0x180019f49  mov     [rdx+r15*4], eax
0x180019f4d  mov     rax, [rbx]
0x180019f50  mov     [rax+rcx*4+4], r9d
0x180019f55  jmp     short loc_180019F22
0x180019f57  dec     edi
0x180019f59  cmp     r8d, edi
0x180019f5c  jz      short loc_180019FA7
0x180019f5e  movsxd  r9, edi
0x180019f61  movsxd  r10, dword ptr [rdx+r9*4]
0x180019f65  cmp     [r14+r10*4], r11d
0x180019f69  jb      short loc_180019F93
0x180019f6b  jnz     short loc_180019F57
0x180019f6d  movsxd  rcx, [rsp+68h+arg_8]
0x180019f72  mov     rax, rcx
0x180019f75  dec     ecx
0x180019f77  mov     [rsp+68h+arg_8], ecx
0x180019f7b  mov     rcx, rax
0x180019f7e  mov     eax, [rdx+rax*4-4]
0x180019f82  mov     [rdx+r9*4], eax
0x180019f86  mov     rax, [rbx]
0x180019f89  mov     [rax+rcx*4-4], r10d
0x180019f8e  mov     rdx, [rbx]
0x180019f91  jmp     short loc_180019F57
0x180019f93  mov     ecx, [rdx+r15*4]
0x180019f97  mov     [rdx+r15*4], r10d
0x180019f9b  mov     rax, [rbx]
0x180019f9e  mov     [rax+r9*4], ecx
0x180019fa2  jmp     loc_180019F22
0x180019fa7  sub     r13d, esi
0x180019faa  mov     r14d, edi
0x180019fad  lea     r10d, [r13+1]
0x180019fb1  sub     r14d, r10d
0x180019fb4  mov     r15d, r14d
0x180019fb7  sub     r15d, esi
0x180019fba  cmp     r10d, r15d
0x180019fbd  cmovge  r10d, r15d
0x180019fc1  xor     r11d, r11d
0x180019fc4  test    r10d, r10d
0x180019fc7  jle     short loc_180019FF8
0x180019fc9  mov     r9, [rbx]
0x180019fcc  lea     eax, [r11+rsi]
0x180019fd0  movsxd  rdx, eax
0x180019fd3  mov     eax, edi
0x180019fd5  sub     eax, r11d
0x180019fd8  inc     r11d
0x180019fdb  movsxd  rcx, eax
0x180019fde  mov     r8d, [r9+rdx*4]
0x180019fe2  mov     eax, [r9+rcx*4-4]
0x180019fe7  mov     [r9+rdx*4], eax
0x180019feb  mov     rax, [rbx]
0x180019fee  mov     [rax+rcx*4-4], r8d
0x180019ff3  cmp     r11d, r10d
0x180019ff6  jl      short loc_180019FC9
0x180019ff8  mov     ecx, [rsp+68h+arg_8]
0x180019ffc  mov     r10d, ebp
0x180019fff  sub     r10d, ecx
0x18001a002  mov     eax, ecx
0x18001a004  sub     eax, edi
0x18001a006  cmp     r10d, eax
0x18001a009  cmovge  r10d, eax
0x18001a00d  xor     r11d, r11d
0x18001a010  test    r10d, r10d
0x18001a013  jle     short loc_18001A048
0x18001a015  mov     r9, [rbx]
0x18001a018  lea     eax, [r11+rdi]
0x18001a01c  movsxd  rdx, eax
0x18001a01f  mov     eax, ebp
0x18001a021  sub     eax, r11d
0x18001a024  inc     r11d
0x18001a027  movsxd  rcx, eax
0x18001a02a  mov     r8d, [r9+rdx*4]
0x18001a02e  mov     eax, [r9+rcx*4-4]
0x18001a033  mov     [r9+rdx*4], eax
0x18001a037  mov     rax, [rbx]
0x18001a03a  mov     [rax+rcx*4-4], r8d
0x18001a03f  cmp     r11d, r10d
0x18001a042  jl      short loc_18001A015
0x18001a044  mov     ecx, [rsp+68h+arg_8]
0x18001a048  sub     edi, ecx
0x18001a04a  add     edi, ebp
0x18001a04c  mov     eax, edi
0x18001a04e  sub     eax, r14d
0x18001a051  cmp     eax, 1
0x18001a054  jle     short loc_18001A075
0x18001a056  movsxd  rcx, dword ptr [rbx+92Ch]
0x18001a05d  lea     edx, [rdi-1]
0x18001a060  mov     rax, [rbx]
0x18001a063  mov     [rax+rcx*4], edx
0x18001a066  lea     rcx, [rbx+928h]
0x18001a06d  inc     dword ptr [rcx+4]
0x18001a070  call    SuffixArrayJobIteratorMakeValid
0x18001a075  mov     eax, ebp
0x18001a077  sub     eax, edi
0x18001a079  cmp     r15d, eax
0x18001a07c  jge     short loc_18001A0F2
0x18001a07e  mov     r8d, r14d
0x18001a081  cmp     r14d, edi
0x18001a084  jge     short loc_18001A09F
0x18001a086  mov     rax, [rbx]
0x18001a089  movsxd  rcx, r8d
0x18001a08c  inc     r8d
0x18001a08f  mov     edx, [rax+rcx*4]
0x18001a092  mov     rax, [rbx+10h]
0x18001a096  mov     [rax+rdx*4], r14d
0x18001a09a  cmp     r8d, edi
0x18001a09d  jl      short loc_18001A086
0x18001a09f  mov     r8d, edi
0x18001a0a2  cmp     edi, ebp
0x18001a0a4  jge     short loc_18001A0BE
0x18001a0a6  mov     rax, [rbx]
0x18001a0a9  movsxd  rcx, r8d
0x18001a0ac  inc     r8d
0x18001a0af  mov     edx, [rax+rcx*4]
0x18001a0b2  mov     rax, [rbx+10h]
0x18001a0b6  mov     [rax+rdx*4], edi
0x18001a0b9  cmp     r8d, ebp
0x18001a0bc  jl      short loc_18001A0A6
0x18001a0be  cmp     r15d, 1
0x18001a0c2  jle     short loc_18001A0DB
0x18001a0c4  mov     r9d, [rsp+68h+arg_18]
0x18001a0cc  mov     r8d, r14d
0x18001a0cf  mov     edx, esi
0x18001a0d1  mov     rcx, rbx
0x18001a0d4  call    SortSampleSuffixes
0x18001a0d9  jmp     short loc_18001A0EE
0x18001a0db  cmp     esi, r14d
0x18001a0de  jge     short loc_18001A0EE
0x18001a0e0  mov     rax, [rbx]
0x18001a0e3  mov     ecx, [rax+r12*4]
0x18001a0e7  mov     rax, [rbx+10h]
0x18001a0eb  mov     [rax+rcx*4], esi
0x18001a0ee  mov     esi, edi
0x18001a0f0  jmp     short loc_18001A146
0x18001a0f2  cmp     eax, 1
0x18001a0f5  jle     short loc_18001A10E
0x18001a0f7  mov     r9d, [rsp+68h+arg_18]
0x18001a0ff  mov     r8d, ebp
0x18001a102  mov     edx, edi
0x18001a104  mov     rcx, rbx
0x18001a107  call    SortSampleSuffixes
0x18001a10c  jmp     short loc_18001A122
0x18001a10e  cmp     edi, ebp
0x18001a110  jge     short loc_18001A122
0x18001a112  mov     rax, [rbx]
0x18001a115  movsxd  rcx, edi
0x18001a118  mov     edx, [rax+rcx*4]
0x18001a11b  mov     rax, [rbx+10h]
0x18001a11f  mov     [rax+rdx*4], edi
0x18001a122  mov     r8d, r14d
0x18001a125  cmp     r14d, edi
0x18001a128  jge     short loc_18001A143
0x18001a12a  mov     rax, [rbx]
0x18001a12d  movsxd  rcx, r8d
0x18001a130  inc     r8d
0x18001a133  mov     edx, [rax+rcx*4]
0x18001a136  mov     rax, [rbx+10h]
0x18001a13a  mov     [rax+rdx*4], r14d
0x18001a13e  cmp     r8d, edi
0x18001a141  jl      short loc_18001A12A
0x18001a143  mov     ebp, r14d
0x18001a146  mov     edi, [rsp+68h+arg_18]
0x18001a14d  mov     eax, ebp
0x18001a14f  mov     rcx, [rsp+68h+arg_0]
0x18001a154  sub     eax, esi
0x18001a156  mov     r8d, 2
0x18001a15c  cmp     eax, r8d
0x18001a15f  jge     loc_180019EAA
0x18001a165  cmp     esi, ebp
0x18001a167  jge     loc_18001A1EE
0x18001a16d  mov     rax, [rbx]
0x18001a170  movsxd  rcx, esi
0x18001a173  mov     edx, [rax+rcx*4]
0x18001a176  mov     rax, [rbx+10h]
0x18001a17a  mov     [rax+rdx*4], esi
0x18001a17d  jmp     short loc_18001A1EE
0x18001a17f  mov     r8d, [r9+r12*4+4]
0x18001a184  mov     edx, [r9+r12*4]
0x18001a188  mov     ecx, [r14+r8*4]
0x18001a18c  cmp     [r14+rdx*4], ecx
0x18001a190  jnb     short loc_18001A1A2
0x18001a192  mov     [rax+rdx*4], esi
0x18001a195  lea     ecx, [rsi+1]
0x18001a198  mov     rax, [rbx+10h]
0x18001a19c  mov     [rax+r8*4], ecx
0x18001a1a0  jmp     short loc_18001A1EE
0x18001a1a2  jnz     short loc_18001A1D0
0x18001a1a4  mov     [rax+rdx*4], esi
0x18001a1a7  lea     edx, [rbp-1]
0x18001a1aa  mov     rax, [rbx+10h]
0x18001a1ae  mov     [rax+r8*4], esi
0x18001a1b2  movsxd  rcx, dword ptr [rbx+92Ch]
0x18001a1b9  mov     rax, [rbx]
0x18001a1bc  mov     [rax+rcx*4], edx
0x18001a1bf  lea     rcx, [rbx+928h]
0x18001a1c6  inc     dword ptr [rcx+4]
0x18001a1c9  call    SuffixArrayJobIteratorMakeValid
0x18001a1ce  jmp     short loc_18001A1EE
0x18001a1d0  mov     [r9+r12*4], r8d
0x18001a1d4  lea     ecx, [rsi+1]
0x18001a1d7  mov     rax, [rbx]
0x18001a1da  mov     [rax+r12*4+4], edx
0x18001a1df  mov     rax, [rbx+10h]
0x18001a1e3  mov     [rax+rdx*4], ecx
0x18001a1e6  mov     rax, [rbx+10h]
0x18001a1ea  mov     [rax+r8*4], esi
0x18001a1ee  mov     rbx, [rsp+68h+arg_10]
0x18001a1f6  add     rsp, 30h
0x18001a1fa  pop     r15
0x18001a1fc  pop     r14
0x18001a1fe  pop     r13
0x18001a200  pop     r12
0x18001a202  pop     rdi
0x18001a203  pop     rsi
0x18001a204  pop     rbp
0x18001a205  retn
```
