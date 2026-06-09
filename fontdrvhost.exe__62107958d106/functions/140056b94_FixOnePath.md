# FixOnePath

- ea: `0x140056b94`
- end: `0x140056fe8`
- name: `FixOnePath`
- size: `1108`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400569dc`

## callees

- `0x14003d74c`
- `0x14003d880`
- `0x140056b94`
- `0x140060730`
- `0x1400607fc`
- `0x1400675a0`

## pseudocode

```c
__int64 __fastcall FixOnePath(__int64 a1, __int64 a2, int a3)
{
  __int64 v5; // rdi
  __int64 v6; // rcx
  int *v7; // r12
  __int16 v8; // si
  int v9; // r15d
  __int64 v10; // rbp
  __int64 v11; // rcx
  __int16 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // r15d
  int v17; // eax
  int v18; // eax
  __int16 v19; // dx
  __int16 i; // r11
  __int64 v21; // rax
  _DWORD *v22; // rax
  int v23; // eax
  unsigned int v24; // ebx
  __int16 v25; // r8
  __int16 v26; // r9
  __int16 j; // r10
  __int64 v28; // rcx
  __int16 v29; // ax
  __int16 k; // r9
  __int64 v31; // rax
  unsigned int v32; // eax
  int v33; // eax
  __int16 v34; // r8
  int v35; // r10d
  unsigned int v36; // edx
  __int16 v37; // r9
  int v38; // r9d
  __int16 m; // dx
  __int64 v40; // rcx
  __int64 v41; // rax
  int v42; // r8d
  int v43; // r15d
  int v44; // r9d
  signed int v45; // ecx
  int v46; // ebx
  int v47; // r10d
  int v48; // eax
  unsigned int v49; // ecx
  unsigned int v50; // eax
  __int64 v51; // rax
  int v52; // r8d
  int v53; // r9d
  int v54; // eax
  int v55; // ecx
  int v56; // edx
  int v57; // ecx
  int v59; // [rsp+20h] [rbp-58h]
  int v60; // [rsp+80h] [rbp+8h]

  v5 = a1;
  if ( !a1 )
    return 0;
  v6 = *(_QWORD *)(a1 + 64);
  if ( !v6 )
    return 0;
  v7 = (int *)(v5 + 24);
  v8 = 0;
  v9 = 0;
  if ( *(_DWORD *)(v5 + 20) > *(_DWORD *)(v5 + 24) )
  {
    os_raise(0xFFFFFFFFLL, 0);
    v6 = *(_QWORD *)(v5 + 64);
  }
  v10 = v5;
  v59 = *v7;
  v60 = *(_DWORD *)(v5 + 20);
  if ( v6 )
  {
    do
    {
      if ( v10 != v5 && (*(_BYTE *)(v10 + 72) & 2) != 0 )
        break;
      if ( v8 == a3 )
        return 0;
      v9 += *(__int16 *)(v10 + 10);
      v11 = v8++;
      *(_QWORD *)(a2 + 8 * v11) = *(_QWORD *)(v10 + 64);
      v10 = *(_QWORD *)(*(_QWORD *)(v10 + 64) + 24LL);
    }
    while ( *(_QWORD *)(v10 + 64) );
    if ( v8 > 2 )
    {
      v12 = 0;
      do
      {
        v13 = v12++;
        v14 = *(_QWORD *)(*(_QWORD *)(a2 + 8 * v13) + 16LL);
        *(_DWORD *)(v14 + 72) &= ~0x10u;
        v15 = *(_QWORD *)(*(_QWORD *)(a2 + 8 * v13) + 24LL);
        *(_DWORD *)(v15 + 72) &= ~0x10u;
      }
      while ( v12 < v8 );
    }
  }
  v16 = *(__int16 *)(v10 + 10) + v9;
  v17 = *(_DWORD *)(v5 + 20) - *v7;
  if ( v17 < 0 )
    v17 = *v7 - *(_DWORD *)(v5 + 20);
  v18 = fixdiv((unsigned int)(12 * v17), (unsigned int)(*(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 + 12)));
  if ( v18 >= 39322 )
    v18 = 39322;
  ClumpCounters(a2, (unsigned int)v8, (unsigned int)v18);
  SortGroupsByFrac(a2, (unsigned int)v8);
  v19 = 0;
  for ( i = 0; v19 < v8; i += *(_WORD *)(*(_QWORD *)(a2 + 8 * v21) + 42LL) )
    v21 = v19++;
  if ( (*(_BYTE *)(v5 + 72) & 2) != 0 )
    v22 = (_DWORD *)(v5 + 40);
  else
    v22 = (_DWORD *)(v5 + 24);
  v23 = *v22 - *(_DWORD *)(((*(_DWORD *)(v10 + 72) & 2) != 0 ? 0x10 : 0) + v10 + 20);
  v24 = -v23;
  if ( v23 > 0 )
    v24 = v23;
  v25 = v8 + v16 + i - ((v24 + 0x8000) >> 16);
  if ( v25 < 0 )
  {
    do
    {
      v26 = 0;
      for ( j = 0; j < v8; v26 += *(_WORD *)(*(_QWORD *)(a2 + 8 * v28) + 42LL) )
      {
        v28 = j++;
        *(_DWORD *)(*(_QWORD *)(a2 + 8 * v28) + 40LL) += 0x10000;
      }
      v29 = v26 - i;
      i = v26;
      v25 += v29;
    }
    while ( v25 < 0 );
    v7 = (int *)(v5 + 24);
  }
  if ( v25 > v8 )
  {
    do
    {
      for ( k = 0; k < v8; *(_DWORD *)(*(_QWORD *)(a2 + 8 * v31) + 40LL) -= 0x10000 )
        v31 = k++;
      v25 -= v8;
    }
    while ( v25 > v8 );
    v7 = (int *)(v5 + 24);
  }
  v32 = fixmul(v24);
  v33 = fixmul(v32);
  v35 = (v33 + 0x8000) >> 16;
  if ( (__int16)((unsigned int)(v33 + 0x8000) >> 16) > 0 && v34 > 0 )
  {
    v36 = (unsigned __int8)*(_WORD *)(*(_QWORD *)(a2 + 8LL * v34 - 8) + 44LL);
    if ( v36 != v34 - 1 )
    {
      v37 = 0;
      if ( *(unsigned __int8 *)(*(_QWORD *)a2 + 44LL) < v36 )
      {
        do
          ++v37;
        while ( *(unsigned __int8 *)(*(_QWORD *)(a2 + 8LL * v37) + 44LL) < v36 );
        v7 = (int *)(v5 + 24);
      }
      if ( v34 - v37 > (__int16)v35 )
      {
        if ( (int)(v36 - v34 + 1) <= (__int16)v35 )
          v34 = v36 + 1;
      }
      else
      {
        v34 = v37;
      }
    }
  }
  v38 = 0;
  for ( m = 0; m < v8; v38 += *(__int16 *)(v41 + 42) )
  {
    v40 = *(_QWORD *)(a2 + 8LL * m);
    if ( m >= v34 )
      *(_DWORD *)(v40 + 40) = (*(_DWORD *)(v40 + 40) & 0xFFFF0000) + 0x10000;
    else
      *(_WORD *)(v40 + 40) = 0;
    v41 = *(_QWORD *)(a2 + 8LL * m++);
  }
  v42 = *(_DWORD *)(v5 + 72);
  if ( (v42 & 2) != 0 )
  {
    v46 = v59;
  }
  else
  {
    v43 = v16 << 16;
    v44 = v38 << 16;
    v45 = v44 + v43 - v24;
    v46 = v59;
    v47 = *(_DWORD *)(v5 + 36) - *(_DWORD *)(v5 + 40);
    if ( v47 < 0 )
      v47 = *(_DWORD *)(v5 + 40) - *(_DWORD *)(v5 + 36);
    v48 = *(_DWORD *)(v10 + 72) & 2;
    if ( v60 < v59 )
    {
      if ( v48 )
        v49 = v44 + v43 + *(_DWORD *)(v10 + 36);
      else
        v49 = (*v7 + v45 / 2 + 0x8000) & 0xFFFF0000;
      v50 = v49 - v47;
    }
    else
    {
      if ( v48 )
        v49 = *(_DWORD *)(v10 + 36) - v44 - v43;
      else
        v49 = (*v7 - v45 / 2 + 0x7FFF) & 0xFFFF0000;
      v50 = v47 + v49;
    }
    *(_DWORD *)(v5 + 40) = v49;
    *(_DWORD *)(v5 + 72) = v42 | 2;
    *(_DWORD *)(v5 + 36) = v50;
    *(_WORD *)(v5 + 76) = 0;
  }
  do
  {
    v51 = *(_QWORD *)(v5 + 64);
    if ( v60 < v46 )
      v52 = *(_DWORD *)(v5 + 36) - *(_DWORD *)(v51 + 40);
    else
      v52 = *(_DWORD *)(v5 + 36) + *(_DWORD *)(v51 + 40);
    v5 = *(_QWORD *)(v51 + 24);
    v53 = *(_DWORD *)(v5 + 72);
    if ( (v53 & 2) != 0 )
      break;
    v54 = *(_DWORD *)(v5 + 40) - *(_DWORD *)(v5 + 36);
    *(_DWORD *)(v5 + 40) = v52;
    v55 = -v54;
    *(_WORD *)(v5 + 76) = 0;
    if ( v54 > 0 )
      v55 = v54;
    v56 = v52 - v55;
    v57 = v52 + v55;
    if ( v60 < v46 )
      v57 = v56;
    *(_DWORD *)(v5 + 36) = v57;
    *(_DWORD *)(v5 + 72) = v53 | 2;
  }
  while ( *(_QWORD *)(v5 + 64) );
  return 1;
}

```

## disassembly

```asm
0x140056b94  push    rbx
0x140056b96  push    rbp
0x140056b97  push    rsi
0x140056b98  push    rdi
0x140056b99  push    r12
0x140056b9b  push    r13
0x140056b9d  push    r14
0x140056b9f  push    r15
0x140056ba1  sub     rsp, 38h
0x140056ba5  mov     r13d, r9d
0x140056ba8  mov     ebx, r8d
0x140056bab  mov     r14, rdx
0x140056bae  mov     rdi, rcx
0x140056bb1  test    rcx, rcx
0x140056bb4  jz      loc_140056FD5
0x140056bba  mov     rcx, [rcx+40h]
0x140056bbe  test    rcx, rcx
0x140056bc1  jz      loc_140056FD5
0x140056bc7  lea     r12, [rdi+18h]
0x140056bcb  xor     esi, esi
0x140056bcd  mov     eax, [r12]
0x140056bd1  xor     r15d, r15d
0x140056bd4  cmp     [rdi+14h], eax
0x140056bd7  jle     short loc_140056BE7
0x140056bd9  xor     edx, edx
0x140056bdb  or      ecx, 0FFFFFFFFh
0x140056bde  call    os_raise
0x140056be3  mov     rcx, [rdi+40h]
0x140056be7  mov     edx, [r12]
0x140056beb  mov     rbp, rdi
0x140056bee  mov     eax, [rdi+14h]
0x140056bf1  mov     [rsp+78h+var_58], edx
0x140056bf5  mov     edx, 2
0x140056bfa  mov     [rsp+78h+arg_0], eax
0x140056c01  lea     r9d, [rdx-1]
0x140056c05  test    rcx, rcx
0x140056c08  jz      short loc_140056C79
0x140056c0a  cmp     rbp, rdi
0x140056c0d  jz      short loc_140056C14
0x140056c0f  test    [rbp+48h], dl
0x140056c12  jnz     short loc_140056C45
0x140056c14  movsx   eax, si
0x140056c17  cmp     eax, ebx
0x140056c19  jz      loc_140056FD5
0x140056c1f  movsx   eax, word ptr [rbp+0Ah]
0x140056c23  add     r15d, eax
0x140056c26  movsx   rcx, si
0x140056c2a  mov     rax, [rbp+40h]
0x140056c2e  add     si, r9w
0x140056c32  mov     [r14+rcx*8], rax
0x140056c36  mov     rax, [rbp+40h]
0x140056c3a  mov     rbp, [rax+18h]
0x140056c3e  cmp     qword ptr [rbp+40h], 0
0x140056c43  jnz     short loc_140056C0A
0x140056c45  cmp     si, dx
0x140056c48  jle     short loc_140056C79
0x140056c4a  xor     r8d, r8d
0x140056c4d  mov     r10d, 0FFFFFFEFh
0x140056c53  movsx   rdx, r8w
0x140056c57  add     r8w, r9w
0x140056c5b  mov     rax, [r14+rdx*8]
0x140056c5f  mov     rcx, [rax+10h]
0x140056c63  and     [rcx+48h], r10d
0x140056c67  mov     rax, [r14+rdx*8]
0x140056c6b  mov     rcx, [rax+18h]
0x140056c6f  and     [rcx+48h], r10d
0x140056c73  cmp     r8w, si
0x140056c77  jl      short loc_140056C53
0x140056c79  movsx   eax, word ptr [rbp+0Ah]
0x140056c7d  mov     ecx, [r12]
0x140056c81  add     r15d, eax
0x140056c84  sub     ecx, [rdi+14h]
0x140056c87  mov     edx, [rdi+10h]
0x140056c8a  mov     eax, ecx
0x140056c8c  sub     edx, [rdi+0Ch]
0x140056c8f  neg     eax
0x140056c91  cmovs   eax, ecx
0x140056c94  lea     ecx, [rax+rax*2]
0x140056c97  shl     ecx, 2
0x140056c9a  call    fixdiv
0x140056c9f  mov     ecx, 999Ah
0x140056ca4  movsx   ebx, si
0x140056ca7  cmp     eax, ecx
0x140056ca9  mov     edx, ebx
0x140056cab  cmovge  eax, ecx
0x140056cae  mov     rcx, r14
0x140056cb1  mov     r8d, eax
0x140056cb4  call    ClumpCounters
0x140056cb9  mov     edx, ebx
0x140056cbb  mov     rcx, r14
0x140056cbe  call    SortGroupsByFrac
0x140056cc3  xor     edx, edx
0x140056cc5  xor     r11d, r11d
0x140056cc8  xor     eax, eax
0x140056cca  cmp     ax, si
0x140056ccd  jge     short loc_140056CEB
0x140056ccf  lea     r8d, [rdx+1]
0x140056cd3  movsx   rax, dx
0x140056cd7  add     dx, r8w
0x140056cdb  mov     rcx, [r14+rax*8]
0x140056cdf  movsx   eax, word ptr [rcx+2Ah]
0x140056ce3  add     r11d, eax
0x140056ce6  cmp     dx, si
0x140056ce9  jl      short loc_140056CD3
0x140056ceb  mov     edx, [rbp+48h]
0x140056cee  and     edx, 2
0x140056cf1  mov     eax, edx
0x140056cf3  neg     eax
0x140056cf5  sbb     rcx, rcx
0x140056cf8  and     ecx, 10h
0x140056cfb  neg     edx
0x140056cfd  sbb     edx, edx
0x140056cff  and     edx, 0FFFF8000h
0x140056d05  add     edx, 10000h
0x140056d0b  test    byte ptr [rdi+48h], 2
0x140056d0f  jz      short loc_140056D1D
0x140056d11  add     edx, 0FFFF8000h
0x140056d17  lea     rax, [rdi+28h]
0x140056d1b  jmp     short loc_140056D20
0x140056d1d  mov     rax, r12
0x140056d20  mov     eax, [rax]
0x140056d22  movzx   r8d, r11w
0x140056d26  sub     eax, [rcx+rbp+14h]
0x140056d2a  mov     ebx, eax
0x140056d2c  neg     ebx
0x140056d2e  cmovs   ebx, eax
0x140056d31  lea     eax, [rbx+8000h]
0x140056d37  sar     eax, 10h
0x140056d3a  sub     r8w, ax
0x140056d3e  add     r8w, r15w
0x140056d42  add     r8w, si
0x140056d46  jns     short loc_140056D94
0x140056d48  mov     r12d, 1
0x140056d4e  xor     r9d, r9d
0x140056d51  xor     r10d, r10d
0x140056d54  xor     eax, eax
0x140056d56  cmp     ax, si
0x140056d59  jge     short loc_140056D7F
0x140056d5b  movsx   rcx, r10w
0x140056d5f  add     r10w, r12w
0x140056d63  mov     rax, [r14+rcx*8]
0x140056d67  add     dword ptr [rax+28h], 10000h
0x140056d6e  mov     rax, [r14+rcx*8]
0x140056d72  movsx   ecx, word ptr [rax+2Ah]
0x140056d76  add     r9d, ecx
0x140056d79  cmp     r10w, si
0x140056d7d  jl      short loc_140056D5B
0x140056d7f  movzx   eax, r9w
0x140056d83  sub     ax, r11w
0x140056d87  mov     r11d, r9d
0x140056d8a  add     r8w, ax
0x140056d8e  js      short loc_140056D4E
0x140056d90  lea     r12, [rdi+18h]
0x140056d94  cmp     r8w, si
0x140056d98  jle     short loc_140056DD1
0x140056d9a  mov     r12d, 1
0x140056da0  xor     r9d, r9d
0x140056da3  xor     eax, eax
0x140056da5  cmp     ax, si
0x140056da8  jge     short loc_140056DC3
0x140056daa  movsx   rax, r9w
0x140056dae  add     r9w, r12w
0x140056db2  mov     rcx, [r14+rax*8]
0x140056db6  add     dword ptr [rcx+28h], 0FFFF0000h
0x140056dbd  cmp     r9w, si
0x140056dc1  jl      short loc_140056DAA
0x140056dc3  sub     r8w, si
0x140056dc7  cmp     r8w, si
0x140056dcb  jg      short loc_140056DA0
0x140056dcd  lea     r12, [rdi+18h]
0x140056dd1  mov     ecx, ebx
0x140056dd3  call    fixmul
0x140056dd8  mov     ecx, eax
0x140056dda  mov     edx, r13d
0x140056ddd  call    fixmul
0x140056de2  xor     r13d, r13d
0x140056de5  lea     r10d, [rax+8000h]
0x140056dec  sar     r10d, 10h
0x140056df0  test    r10w, r10w
0x140056df4  jle     short loc_140056E59
0x140056df6  test    r8w, r8w
0x140056dfa  jle     short loc_140056E59
0x140056dfc  movsx   r11, r8w
0x140056e00  mov     eax, 0FFh
0x140056e05  mov     rcx, [r14+r11*8-8]
0x140056e0a  and     ax, [rcx+2Ch]
0x140056e0e  movzx   edx, ax
0x140056e11  lea     eax, [r11-1]
0x140056e15  cmp     edx, eax
0x140056e17  jz      short loc_140056E59
0x140056e19  mov     rax, [r14]
0x140056e1c  mov     r9d, r13d
0x140056e1f  movzx   ecx, byte ptr [rax+2Ch]
0x140056e23  cmp     ecx, edx
0x140056e25  jnb     short loc_140056E43
0x140056e27  lea     r12d, [r13+1]
0x140056e2b  add     r9w, r12w
0x140056e2f  movsx   rax, r9w
0x140056e33  mov     rcx, [r14+rax*8]
0x140056e37  movzx   eax, byte ptr [rcx+2Ch]
0x140056e3b  cmp     eax, edx
0x140056e3d  jb      short loc_140056E2B
0x140056e3f  lea     r12, [rdi+18h]
0x140056e43  movsx   eax, r9w
0x140056e47  mov     ecx, r11d
0x140056e4a  sub     ecx, eax
0x140056e4c  movsx   r10d, r10w
0x140056e50  cmp     ecx, r10d
0x140056e53  jg      short loc_140056E80
0x140056e55  movzx   r8d, r9w
0x140056e59  mov     r11d, 1
0x140056e5f  mov     r9d, r13d
0x140056e62  mov     edx, r13d
0x140056e65  cmp     r13w, si
0x140056e69  jge     short loc_140056EBD
0x140056e6b  movsx   r10, dx
0x140056e6f  mov     rcx, [r14+r10*8]
0x140056e73  cmp     dx, r8w
0x140056e77  jge     short loc_140056E99
0x140056e79  mov     [rcx+28h], r13w
0x140056e7e  jmp     short loc_140056EA9
0x140056e80  mov     eax, edx
0x140056e82  sub     eax, r11d
0x140056e85  mov     r11d, 1
0x140056e8b  add     eax, r11d
0x140056e8e  cmp     eax, r10d
0x140056e91  jg      short loc_140056E5F
0x140056e93  lea     r8d, [r11+rdx]
0x140056e97  jmp     short loc_140056E5F
0x140056e99  mov     eax, [rcx+28h]
0x140056e9c  and     eax, 0FFFF0000h
0x140056ea1  add     eax, 10000h
0x140056ea6  mov     [rcx+28h], eax
0x140056ea9  mov     rax, [r14+r10*8]
0x140056ead  add     dx, r11w
0x140056eb1  movsx   ecx, word ptr [rax+2Ah]
0x140056eb5  add     r9d, ecx
0x140056eb8  cmp     dx, si
0x140056ebb  jl      short loc_140056E6B
0x140056ebd  mov     r8d, [rdi+48h]
0x140056ec1  mov     esi, 2
0x140056ec6  mov     r11d, [rsp+78h+arg_0]
0x140056ece  test    sil, r8b
0x140056ed1  jnz     loc_140056F6E
0x140056ed7  mov     eax, [rdi+28h]
0x140056eda  sub     eax, [rdi+24h]
0x140056edd  shl     r15d, 10h
0x140056ee1  mov     r10d, eax
0x140056ee4  shl     r9d, 10h
0x140056ee8  lea     edx, [r9+r15]
0x140056eec  mov     ecx, edx
0x140056eee  sub     ecx, ebx
0x140056ef0  mov     ebx, [rsp+78h+var_58]
0x140056ef4  neg     r10d
0x140056ef7  cmovs   r10d, eax
0x140056efb  mov     eax, [rbp+48h]
0x140056efe  and     eax, esi
0x140056f00  cmp     r11d, ebx
0x140056f03  jl      short loc_140056F33
0x140056f05  test    eax, eax
0x140056f07  jz      short loc_140056F14
0x140056f09  mov     ecx, [rbp+24h]
0x140056f0c  sub     ecx, r9d
0x140056f0f  sub     ecx, r15d
0x140056f12  jmp     short loc_140056F2D
0x140056f14  mov     eax, ecx
0x140056f16  mov     ecx, [r12]
0x140056f1a  cdq
0x140056f1b  sub     eax, edx
0x140056f1d  sar     eax, 1
0x140056f1f  sub     ecx, eax
0x140056f21  add     ecx, 7FFFh
0x140056f27  and     ecx, 0FFFF0000h
0x140056f2d  lea     eax, [r10+rcx]
0x140056f31  jmp     short loc_140056F5A
0x140056f33  test    eax, eax
0x140056f35  jz      short loc_140056F3E
0x140056f37  mov     ecx, [rbp+24h]
0x140056f3a  add     ecx, edx
0x140056f3c  jmp     short loc_140056F55
0x140056f3e  mov     eax, ecx
0x140056f40  cdq
0x140056f41  sub     eax, edx
0x140056f43  sar     eax, 1
0x140056f45  lea     ecx, [rax+8000h]
0x140056f4b  add     ecx, [r12]
0x140056f4f  and     ecx, 0FFFF0000h
0x140056f55  mov     eax, ecx
0x140056f57  sub     eax, r10d
0x140056f5a  mov     [rdi+28h], ecx
0x140056f5d  or      r8d, esi
0x140056f60  mov     [rdi+48h], r8d
0x140056f64  mov     [rdi+24h], eax
0x140056f67  mov     [rdi+4Ch], r13w
0x140056f6c  jmp     short loc_140056F72
0x140056f6e  mov     ebx, [rsp+78h+var_58]
0x140056f72  mov     rax, [rdi+40h]
0x140056f76  cmp     r11d, ebx
0x140056f79  jl      short loc_140056F85
0x140056f7b  mov     r8d, [rax+28h]
  ... truncated ...
```
