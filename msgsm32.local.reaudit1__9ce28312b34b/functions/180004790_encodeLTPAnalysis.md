# encodeLTPAnalysis

- ea: `0x180004790`
- end: `0x180004a07`
- name: `encodeLTPAnalysis`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005350`

## callees

- `0x180004790`

## pseudocode

```c
__int64 __fastcall encodeLTPAnalysis(__int64 a1, __int64 a2, __int16 *a3, _WORD *a4)
{
  int v5; // r8d
  __int16 v7; // r10
  char v8; // bp
  int v9; // r15d
  __int64 i; // r9
  __int16 v11; // ax
  __int16 v12; // dx
  int v13; // ecx
  __int16 v14; // si
  int v15; // ecx
  __int64 j; // rdx
  __int16 v17; // r14
  int v18; // edi
  __int16 v19; // bx
  int k; // r9d
  __int16 v21; // r11
  int v22; // r10d
  int v23; // edx
  int v24; // r9d
  int v25; // r8d
  __int64 v26; // rax
  int v27; // ecx
  int v28; // edx
  __int64 result; // rax
  char v30; // r8
  int v31; // ecx
  char v32; // cl
  int v33; // r9d
  __int16 v34; // r8
  int v35; // r9d
  int v36; // r10d
  int v37; // ecx
  _WORD v40[68]; // [rsp+10h] [rbp-88h]

  v5 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 39;
  for ( i = 39; i != -1; --i )
  {
    v11 = *(_WORD *)(a2 + 2 * i);
    if ( v11 < 0 )
    {
      if ( v11 == (__int16)0x8000 )
        v11 = 0x7FFF;
      else
        v11 = -v11;
    }
    if ( v11 <= v7 )
      v11 = v7;
    v7 = v11;
  }
  v12 = 0;
  if ( !v11 )
    goto LABEL_18;
  v13 = v11 << 16;
  if ( v13 > 0 )
  {
    while ( v13 < 0x40000000 )
    {
      ++v12;
      v13 *= 2;
    }
  }
  else if ( (unsigned int)(v13 + 0x3FFFFFFF) <= 0x3FFFFFFE )
  {
    do
    {
      ++v12;
      v13 *= 2;
    }
    while ( v13 > -1073741824 );
  }
  if ( v12 > 6 )
  {
    v14 = 0;
  }
  else
  {
LABEL_18:
    v15 = 6 - v12;
    if ( v15 >= -32768 )
    {
      if ( v15 > 0x7FFF )
        LOWORD(v15) = 0x7FFF;
    }
    else
    {
      LOWORD(v15) = 0x8000;
    }
    v14 = v15;
  }
  for ( j = 39; j != -1; --j )
    v40[j] = *(__int16 *)(a2 + 2 * j) >> v14;
  v17 = 40;
  v18 = 0;
  v19 = 40;
  do
  {
    for ( k = 39; k >= 0; --k )
      v5 += (__int16)v40[k] * *(__int16 *)(a1 + 2 * ((unsigned int)k - (unsigned __int64)(unsigned __int16)v19) + 252);
    v21 = v19;
    if ( v5 <= v18 )
    {
      v5 = v18;
      v21 = v17;
    }
    ++v19;
    v18 = v5;
    v17 = v21;
    v5 = 0;
  }
  while ( v19 <= 120 );
  v22 = 6 - v14;
  if ( v22 >= -32768 )
  {
    v8 = -1;
    if ( v22 <= 0x7FFF )
      v8 = 6 - v14;
  }
  v23 = 0;
  v24 = (2 * v18) >> v8;
  v25 = 39 - v21;
  do
  {
    v26 = v25--;
    v27 = *(__int16 *)(a1 + 2 * v26 + 252) >> 3;
    v23 += v27 * v27;
    --v9;
  }
  while ( v9 >= 0 );
  if ( v23 < 0x40000000 )
    v28 = 2 * v23;
  else
    v28 = 0x7FFFFFFF;
  result = (__int64)a3;
  *a3 = v21;
  if ( v24 > 0 )
  {
    if ( v24 >= v28 )
    {
LABEL_53:
      *a4 = 3;
    }
    else
    {
      v30 = 0;
      v31 = v28;
      if ( v28 <= 0 )
      {
        if ( (unsigned int)(v28 + 0x3FFFFFFF) <= 0x3FFFFFFE )
        {
          do
          {
            ++v30;
            v31 *= 2;
          }
          while ( v31 > -1073741824 );
        }
      }
      else if ( v28 < 0x40000000 )
      {
        do
        {
          ++v30;
          v31 *= 2;
        }
        while ( v31 < 0x40000000 );
      }
      v32 = v30;
      v33 = v24 << v30;
      v34 = 0;
      v35 = v33 >> 16;
      v36 = (__int16)((unsigned int)(v28 << v32) >> 16);
      *a4 = 0;
      while ( 1 )
      {
        result = 0x3FFFFFFF;
        v37 = v36 * *((__int16 *)&DLB + v34);
        if ( v37 >= 0x40000000 )
          v37 = 0x3FFFFFFF;
        if ( (__int16)v35 <= (__int16)((unsigned int)v37 >> 15) )
          break;
        *a4 = ++v34;
        if ( v34 > 2 )
          goto LABEL_53;
      }
    }
  }
  else
  {
    result = 0;
    *a4 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004790  mov     [rsp+arg_0], rbx
0x180004795  push    rbp
0x180004796  push    rsi
0x180004797  push    rdi
0x180004798  push    r12
0x18000479a  push    r13
0x18000479c  push    r14
0x18000479e  push    r15
0x1800047a0  sub     rsp, 60h
0x1800047a4  mov     [rsp+98h+var_90], r8
0x1800047a9  mov     r11, rdx
0x1800047ac  xor     r8d, r8d
0x1800047af  mov     [rsp+98h+var_98], r9
0x1800047b3  mov     r13, rcx
0x1800047b6  mov     r10d, r8d
0x1800047b9  mov     ebp, 0FFFF8000h
0x1800047be  mov     edi, 7FFFh
0x1800047c3  lea     r15d, [r8+27h]
0x1800047c7  mov     r9d, r15d
0x1800047ca  lea     ebx, [r8+1]
0x1800047ce  movzx   eax, word ptr [rdx+r9*2]
0x1800047d3  test    ax, ax
0x1800047d6  jns     short loc_1800047E4
0x1800047d8  cmp     ax, bp
0x1800047db  jnz     short loc_1800047E1
0x1800047dd  mov     eax, edi
0x1800047df  jmp     short loc_1800047E4
0x1800047e1  neg     ax
0x1800047e4  cmp     ax, r10w
0x1800047e8  cmovle  ax, r10w
0x1800047ed  sub     r9, rbx
0x1800047f0  movzx   r10d, ax
0x1800047f4  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x1800047f8  jnz     short loc_1800047CE
0x1800047fa  mov     edx, r8d
0x1800047fd  mov     r9d, 40000000h
0x180004803  mov     r10d, 6
0x180004809  test    ax, ax
0x18000480c  jz      short loc_180004847
0x18000480e  movsx   ecx, ax
0x180004811  shl     ecx, 10h
0x180004814  test    ecx, ecx
0x180004816  jg      short loc_180004840
0x180004818  lea     eax, [rcx+3FFFFFFFh]
0x18000481e  cmp     eax, 3FFFFFFEh
0x180004823  ja      short loc_180004831
0x180004825  add     edx, ebx
0x180004827  add     ecx, ecx
0x180004829  cmp     ecx, 0C0000000h
0x18000482f  jg      short loc_180004825
0x180004831  cmp     dx, r10w
0x180004835  jle     short loc_180004847
0x180004837  mov     esi, r8d
0x18000483a  jmp     short loc_180004861
0x18000483c  add     edx, ebx
0x18000483e  add     ecx, ecx
0x180004840  cmp     ecx, r9d
0x180004843  jl      short loc_18000483C
0x180004845  jmp     short loc_180004831
0x180004847  movsx   eax, dx
0x18000484a  mov     ecx, r10d
0x18000484d  sub     ecx, eax
0x18000484f  cmp     ecx, ebp
0x180004851  jge     short loc_180004858
0x180004853  movzx   ecx, bp
0x180004856  jmp     short loc_18000485E
0x180004858  cmp     ecx, edi
0x18000485a  jle     short loc_18000485E
0x18000485c  mov     ecx, edi
0x18000485e  movzx   esi, cx
0x180004861  mov     rdx, r15
0x180004864  movzx   eax, word ptr [r11+rdx*2]
0x180004869  movzx   ecx, si
0x18000486c  sar     ax, cl
0x18000486f  mov     [rsp+rdx*2+98h+var_88], ax
0x180004874  sub     rdx, rbx
0x180004877  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18000487b  jnz     short loc_180004864
0x18000487d  lea     r14d, [rdx+29h]
0x180004881  mov     edi, r8d
0x180004884  movzx   ebx, r14w
0x180004888  lea     r12d, [rdx+2]
0x18000488c  mov     r9d, r15d
0x18000488f  movzx   eax, bx
0x180004892  mov     ecx, r9d
0x180004895  sub     rcx, rax
0x180004898  mov     eax, r9d
0x18000489b  movsx   edx, word ptr [r13+rcx*2+0FCh]
0x1800048a4  movsx   ecx, [rsp+rax*2+98h+var_88]
0x1800048a9  imul    edx, ecx
0x1800048ac  add     r8d, edx
0x1800048af  sub     r9d, r12d
0x1800048b2  jns     short loc_18000488F
0x1800048b4  cmp     r8d, edi
0x1800048b7  movzx   r11d, bx
0x1800048bb  cmovle  r8d, edi
0x1800048bf  cmovle  r11w, r14w
0x1800048c4  add     bx, r12w
0x1800048c8  mov     edi, r8d
0x1800048cb  movzx   r14d, r11w
0x1800048cf  mov     r8d, 0
0x1800048d5  cmp     bx, 78h ; 'x'
0x1800048d9  jle     short loc_18000488C
0x1800048db  movsx   eax, si
0x1800048de  lea     r9d, [rdi+rdi]
0x1800048e2  sub     r10d, eax
0x1800048e5  cmp     r10d, ebp
0x1800048e8  jl      short loc_1800048F8
0x1800048ea  mov     ebp, 7FFFh
0x1800048ef  cmp     r10d, ebp
0x1800048f2  jg      short loc_1800048F8
0x1800048f4  movzx   ebp, r10w
0x1800048f8  mov     r12, [rsp+98h+var_98]
0x1800048fc  xor     edx, edx
0x1800048fe  mov     cl, bpl
0x180004901  movsx   eax, r11w
0x180004905  sar     r9d, cl
0x180004908  mov     r8d, r15d
0x18000490b  sub     r8d, eax
0x18000490e  lea     ebx, [rdx+1]
0x180004911  movsxd  rax, r8d
0x180004914  sub     r8d, ebx
0x180004917  movsx   ecx, word ptr [r13+rax*2+0FCh]
0x180004920  sar     ecx, 3
0x180004923  imul    ecx, ecx
0x180004926  add     edx, ecx
0x180004928  sub     r15d, ebx
0x18000492b  jns     short loc_180004911
0x18000492d  mov     edi, 40000000h
0x180004932  cmp     edx, edi
0x180004934  jl      short loc_18000493D
0x180004936  mov     edx, 7FFFFFFFh
0x18000493b  jmp     short loc_18000493F
0x18000493d  add     edx, edx
0x18000493f  mov     rax, [rsp+98h+var_90]
0x180004944  mov     [rax], r11w
0x180004948  test    r9d, r9d
0x18000494b  jg      short loc_180004959
0x18000494d  xor     eax, eax
0x18000494f  mov     [r12], ax
0x180004954  jmp     loc_1800049EF
0x180004959  cmp     r9d, edx
0x18000495c  jge     loc_1800049E8
0x180004962  xor     r8d, r8d
0x180004965  mov     ecx, edx
0x180004967  test    edx, edx
0x180004969  jle     short loc_18000497A
0x18000496b  cmp     edx, edi
0x18000496d  jge     short loc_180004994
0x18000496f  add     r8d, ebx
0x180004972  add     ecx, ecx
0x180004974  cmp     ecx, edi
0x180004976  jl      short loc_18000496F
0x180004978  jmp     short loc_180004994
0x18000497a  lea     eax, [rdx+3FFFFFFFh]
0x180004980  cmp     eax, 3FFFFFFEh
0x180004985  ja      short loc_180004994
0x180004987  add     r8d, ebx
0x18000498a  add     ecx, ecx
0x18000498c  cmp     ecx, 0C0000000h
0x180004992  jg      short loc_180004987
0x180004994  movsx   ecx, r8w
0x180004998  xor     eax, eax
0x18000499a  shl     r9d, cl
0x18000499d  xor     r8d, r8d
0x1800049a0  sar     r9d, 10h
0x1800049a4  shl     edx, cl
0x1800049a6  sar     edx, 10h
0x1800049a9  movsx   r10d, dx
0x1800049ad  mov     [r12], ax
0x1800049b2  movsx   rax, r8w
0x1800049b6  lea     rcx, DLB
0x1800049bd  movsx   ecx, word ptr [rcx+rax*2]
0x1800049c1  mov     eax, 3FFFFFFFh
0x1800049c6  imul    ecx, r10d
0x1800049ca  cmp     ecx, edi
0x1800049cc  cmovge  ecx, eax
0x1800049cf  shr     ecx, 0Fh
0x1800049d2  cmp     r9w, cx
0x1800049d6  jle     short loc_1800049EF
0x1800049d8  add     r8w, bx
0x1800049dc  mov     [r12], r8w
0x1800049e1  cmp     r8w, 2
0x1800049e6  jle     short loc_1800049B2
0x1800049e8  mov     word ptr [r12], 3
0x1800049ef  mov     rbx, [rsp+98h+arg_0]
0x1800049f7  add     rsp, 60h
0x1800049fb  pop     r15
0x1800049fd  pop     r14
0x1800049ff  pop     r13
0x180004a01  pop     r12
0x180004a03  pop     rdi
0x180004a04  pop     rsi
0x180004a05  pop     rbp
0x180004a06  retn
```
