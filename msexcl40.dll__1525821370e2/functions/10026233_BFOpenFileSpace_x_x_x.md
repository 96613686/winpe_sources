# BFOpenFileSpace(x,x,x)

- ea: `0x10026233`
- end: `0x100264bc`
- name: `_BFOpenFileSpace@12`
- size: `649`
- prototype: `int __fastcall(size_t *, int, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x10013ee0`
- `0x10014020`
- `0x10017790`

## callees

- `0x10025bee`
- `0x10025d54`
- `0x10025df5`
- `0x10026233`
- `0x100366a8`

## pseudocode

```c
int __fastcall BFOpenFileSpace(size_t *a1, int a2, int a3)
{
  int v5; // eax
  size_t v6; // esi
  int v7; // ecx
  size_t v8; // edx
  bool v9; // zf
  int v10; // ecx
  char *v11; // esi
  int *v12; // esi
  size_t v13; // eax
  int result; // eax
  int v15; // esi
  int v16; // ecx
  signed int v17; // edx
  int v18; // esi
  _DWORD *v19; // eax
  int v20; // esi
  size_t v21; // esi
  size_t v22; // eax
  size_t v23; // esi
  size_t v24; // [esp-4h] [ebp-1Ch]
  _DWORD *v25; // [esp+Ch] [ebp-Ch]
  size_t *v26; // [esp+Ch] [ebp-Ch]
  signed int v27; // [esp+10h] [ebp-8h]
  int v28; // [esp+14h] [ebp-4h]
  size_t v29; // [esp+14h] [ebp-4h]

  v5 = a1[21];
  if ( a2 < v5 || (v6 = *a1, v7 = *a1 + v5, a2 > v7 - 1) )
  {
    v10 = a3;
  }
  else
  {
    v8 = a1[22];
    v9 = v7 == v8;
    v10 = a3;
    if ( v9 && (int)(v6 + a3) <= (int)a1[16] )
    {
      v11 = (char *)(a2 + a1[1] - a1[21]);
      memmove(&v11[a3], v11, v8 - a2);
      a1[22] += a3;
      *a1 += a3;
      a1[2] = (size_t)v11;
LABEL_33:
      a1[23] = 1;
      goto LABEL_34;
    }
  }
  v12 = (int *)(a1 + 22);
  v13 = a1[22];
  if ( v13 == a2 )
  {
    a1[20] = v13;
    a1[21] = v13;
    *a1 = 0;
    *v12 = v10 + v13;
LABEL_34:
    a1[19] = 0;
    return 0;
  }
  v25 = a1 + 22;
  if ( a1[23] == 1 )
  {
    result = WriteFileBlock(a1);
    if ( result < 0 )
      return result;
    v25 = a1 + 22;
  }
  v15 = *v12;
  v16 = a3;
  v17 = a1[16];
  a1[18] = 0;
  v27 = v17;
  if ( a3 + v15 - a2 <= v17 )
  {
    a1[20] = a2;
    OSSetFilePosition(a1, 0, a2);
    result = ReadFileBlock(a1);
    if ( result < 0 )
      return result;
    v18 = a3;
    memmove((void *)(a3 + a1[1]), (const void *)a1[1], *a1);
    *a1 += a3;
    goto LABEL_32;
  }
  if ( v15 - a2 > v17 )
  {
    v20 = v15 - v17;
    if ( v20 < a2 )
    {
      v26 = a1 + 16;
LABEL_25:
      v28 = v20;
      v21 = v17 + v20;
      if ( v16 + v21 - a2 > v17 )
      {
        v22 = v16 + v28 - a2;
        v21 -= v22;
        a1[16] = v22;
        a1[20] = v21;
        OSSetFilePosition(a1, 0, v21);
        result = ReadFileBlock(a1);
        if ( result < 0 )
          return result;
        a1[21] = v21 + a3;
        result = WriteFileBlock(a1);
        if ( result < 0 )
          return result;
        a1[16] = v27;
      }
      a1[20] = a2;
      OSSetFilePosition(a1, 0, a2);
      v23 = v21 - a2;
      v29 = *v26;
      *v26 = v23;
      result = ReadFileBlock(a1);
      if ( result < 0 )
        return result;
      v24 = v23;
      v18 = a3;
      memmove((void *)(a3 + a1[1]), (const void *)a1[1], v24);
      *a1 = a3 + *v26;
      *v26 = v29;
      v19 = a1 + 22;
      goto LABEL_31;
    }
    while ( 1 )
    {
      a1[20] = v20;
      OSSetFilePosition(a1, 0, v20);
      result = ReadFileBlock(a1);
      if ( result < 0 )
        break;
      a1[21] = v20 + a3;
      result = WriteFileBlock(a1);
      if ( result < 0 )
        break;
      v17 = a1[16];
      v20 -= v17;
      v27 = v17;
      if ( v20 < a2 )
      {
        v26 = a1 + 16;
        v16 = a3;
        goto LABEL_25;
      }
    }
  }
  else
  {
    a1[20] = a2;
    OSSetFilePosition(a1, 0, a2);
    result = ReadFileBlock(a1);
    if ( result >= 0 )
    {
      v18 = a3;
      a1[21] = a2 + a3;
      result = WriteFileBlock(a1);
      if ( result >= 0 )
      {
        memmove((void *)(a1[1] + a3), (const void *)a1[1], a1[16] - a3);
        *a1 = a1[16];
        v19 = v25;
LABEL_31:
        v25 = v19;
        a1[21] = a2;
LABEL_32:
        *v25 = v18 + a1[22];
        a1[18] = 1;
        goto LABEL_33;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x10026233  mov     edi, edi
0x10026235  push    ebp
0x10026236  mov     ebp, esp
0x10026238  and     esp, 0FFFFFFF8h
0x1002623b  sub     esp, 0Ch
0x1002623e  push    ebx
0x1002623f  push    esi
0x10026240  push    edi
0x10026241  mov     edi, ecx
0x10026243  mov     ebx, edx
0x10026245  mov     eax, [edi+54h]
0x10026248  cmp     ebx, eax
0x1002624a  jl      short loc_10026292
0x1002624c  mov     esi, [edi]
0x1002624e  lea     ecx, [esi+eax]
0x10026251  lea     eax, [ecx-1]
0x10026254  cmp     ebx, eax
0x10026256  jg      short loc_10026292
0x10026258  mov     edx, [edi+58h]
0x1002625b  cmp     ecx, edx
0x1002625d  mov     ecx, [ebp+arg_0]
0x10026260  jnz     short loc_10026295
0x10026262  lea     eax, [esi+ecx]
0x10026265  cmp     eax, [edi+40h]
0x10026268  jg      short loc_10026295
0x1002626a  mov     esi, [edi+4]
0x1002626d  sub     edx, ebx
0x1002626f  sub     esi, [edi+54h]
0x10026272  add     esi, ebx
0x10026274  push    edx; Size
0x10026275  push    esi; Src
0x10026276  lea     eax, [esi+ecx]
0x10026279  push    eax; void *
0x1002627a  call    _memmove
0x1002627f  mov     eax, [ebp+arg_0]
0x10026282  add     esp, 0Ch
0x10026285  add     [edi+58h], eax
0x10026288  add     [edi], eax
0x1002628a  mov     [edi+8], esi
0x1002628d  jmp     loc_100264A3
0x10026292  mov     ecx, [ebp+arg_0]
0x10026295  lea     esi, [edi+58h]
0x10026298  mov     eax, [esi]
0x1002629a  cmp     eax, ebx
0x1002629c  jnz     short loc_100262B3
0x1002629e  mov     [edi+50h], eax
0x100262a1  mov     [edi+54h], eax
0x100262a4  add     eax, ecx
0x100262a6  mov     dword ptr [edi], 0
0x100262ac  mov     [esi], eax
0x100262ae  jmp     loc_100264AA
0x100262b3  cmp     dword ptr [edi+5Ch], 1
0x100262b7  mov     [esp+18h+var_C], esi
0x100262bb  jnz     short loc_100262D3
0x100262bd  mov     ecx, edi
0x100262bf  call    WriteFileBlock
0x100262c4  test    eax, eax
0x100262c6  js      loc_100264B3
0x100262cc  lea     eax, [edi+58h]
0x100262cf  mov     [esp+18h+var_C], eax
0x100262d3  mov     esi, [esi]
0x100262d5  mov     eax, esi
0x100262d7  mov     ecx, [ebp+arg_0]
0x100262da  sub     eax, ebx
0x100262dc  mov     edx, [edi+40h]
0x100262df  mov     [esp+18h+var_4], eax
0x100262e3  add     eax, ecx
0x100262e5  mov     dword ptr [edi+48h], 0
0x100262ec  mov     [esp+18h+var_8], edx
0x100262f0  cmp     eax, edx
0x100262f2  jg      short loc_1002632B
0x100262f4  push    ebx
0x100262f5  xor     edx, edx
0x100262f7  mov     [edi+50h], ebx
0x100262fa  mov     ecx, edi
0x100262fc  call    OSSetFilePosition
0x10026301  mov     ecx, edi
0x10026303  call    ReadFileBlock
0x10026308  test    eax, eax
0x1002630a  js      loc_100264B3
0x10026310  push    dword ptr [edi]; Size
0x10026312  mov     eax, [edi+4]
0x10026315  mov     esi, [ebp+arg_0]
0x10026318  push    eax; Src
0x10026319  add     eax, esi
0x1002631b  push    eax; void *
0x1002631c  call    _memmove
0x10026321  add     esp, 0Ch
0x10026324  add     [edi], esi
0x10026326  jmp     loc_1002648C
0x1002632b  cmp     [esp+18h+var_4], edx
0x1002632f  jg      short loc_10026389
0x10026331  push    ebx
0x10026332  xor     edx, edx
0x10026334  mov     [edi+50h], ebx
0x10026337  mov     ecx, edi
0x10026339  call    OSSetFilePosition
0x1002633e  mov     ecx, edi
0x10026340  call    ReadFileBlock
0x10026345  test    eax, eax
0x10026347  js      loc_100264B3
0x1002634d  mov     esi, [ebp+arg_0]
0x10026350  mov     ecx, edi
0x10026352  lea     eax, [ebx+esi]
0x10026355  mov     [edi+54h], eax
0x10026358  call    WriteFileBlock
0x1002635d  test    eax, eax
0x1002635f  js      loc_100264B3
0x10026365  mov     ecx, [edi+4]
0x10026368  mov     eax, [edi+40h]
0x1002636b  sub     eax, esi
0x1002636d  push    eax; Size
0x1002636e  push    ecx; Src
0x1002636f  lea     eax, [ecx+esi]
0x10026372  push    eax; void *
0x10026373  call    _memmove
0x10026378  mov     eax, [edi+40h]
0x1002637b  add     esp, 0Ch
0x1002637e  mov     [edi], eax
0x10026380  mov     eax, [esp+18h+var_C]
0x10026384  jmp     loc_10026485
0x10026389  sub     esi, edx
0x1002638b  cmp     esi, ebx
0x1002638d  jl      short loc_100263DB
0x1002638f  push    esi
0x10026390  xor     edx, edx
0x10026392  mov     [edi+50h], esi
0x10026395  mov     ecx, edi
0x10026397  call    OSSetFilePosition
0x1002639c  mov     ecx, edi
0x1002639e  call    ReadFileBlock
0x100263a3  test    eax, eax
0x100263a5  js      loc_100264B3
0x100263ab  mov     eax, [ebp+arg_0]
0x100263ae  mov     ecx, edi
0x100263b0  add     eax, esi
0x100263b2  mov     [edi+54h], eax
0x100263b5  call    WriteFileBlock
0x100263ba  test    eax, eax
0x100263bc  js      loc_100264B3
0x100263c2  mov     edx, [edi+40h]
0x100263c5  sub     esi, edx
0x100263c7  mov     [esp+18h+var_8], edx
0x100263cb  cmp     esi, ebx
0x100263cd  jge     short loc_1002638F
0x100263cf  lea     ecx, [edi+40h]
0x100263d2  mov     [esp+18h+var_C], ecx
0x100263d6  mov     ecx, [ebp+arg_0]
0x100263d9  jmp     short loc_100263E2
0x100263db  lea     eax, [edi+40h]
0x100263de  mov     [esp+18h+var_C], eax
0x100263e2  mov     [esp+18h+var_4], esi
0x100263e6  add     esi, edx
0x100263e8  mov     eax, esi
0x100263ea  sub     eax, ebx
0x100263ec  add     eax, ecx
0x100263ee  cmp     eax, edx
0x100263f0  jbe     short loc_10026439
0x100263f2  mov     eax, [esp+18h+var_4]
0x100263f6  xor     edx, edx
0x100263f8  sub     eax, ebx
0x100263fa  add     eax, ecx
0x100263fc  mov     ecx, edi
0x100263fe  sub     esi, eax
0x10026400  mov     [edi+40h], eax
0x10026403  push    esi
0x10026404  mov     [edi+50h], esi
0x10026407  call    OSSetFilePosition
0x1002640c  mov     ecx, edi
0x1002640e  call    ReadFileBlock
0x10026413  test    eax, eax
0x10026415  js      loc_100264B3
0x1002641b  mov     eax, [ebp+arg_0]
0x1002641e  mov     ecx, edi
0x10026420  add     eax, esi
0x10026422  mov     [edi+54h], eax
0x10026425  call    WriteFileBlock
0x1002642a  test    eax, eax
0x1002642c  js      loc_100264B3
0x10026432  mov     eax, [esp+18h+var_8]
0x10026436  mov     [edi+40h], eax
0x10026439  push    ebx
0x1002643a  xor     edx, edx
0x1002643c  mov     [edi+50h], ebx
0x1002643f  mov     ecx, edi
0x10026441  call    OSSetFilePosition
0x10026446  mov     eax, [esp+18h+var_C]
0x1002644a  sub     esi, ebx
0x1002644c  mov     ecx, [eax]
0x1002644e  mov     [esp+18h+var_4], ecx
0x10026452  mov     ecx, edi
0x10026454  mov     [eax], esi
0x10026456  call    ReadFileBlock
0x1002645b  test    eax, eax
0x1002645d  js      short loc_100264B3
0x1002645f  mov     eax, [edi+4]
0x10026462  push    esi; Size
0x10026463  mov     esi, [ebp+arg_0]
0x10026466  push    eax; Src
0x10026467  add     eax, esi
0x10026469  push    eax; void *
0x1002646a  call    _memmove
0x1002646f  mov     ecx, [esp+24h+var_C]
0x10026473  add     esp, 0Ch
0x10026476  mov     eax, [ecx]
0x10026478  add     eax, esi
0x1002647a  mov     [edi], eax
0x1002647c  mov     eax, [esp+18h+var_4]
0x10026480  mov     [ecx], eax
0x10026482  lea     eax, [edi+58h]
0x10026485  mov     [esp+18h+var_C], eax
0x10026489  mov     [edi+54h], ebx
0x1002648c  mov     eax, [edi+58h]
0x1002648f  mov     edx, edi
0x10026491  mov     ecx, [esp+18h+var_C]
0x10026495  add     eax, esi
0x10026497  push    48h ; 'H'
0x10026499  pop     ebx
0x1002649a  mov     [ecx], eax
0x1002649c  mov     dword ptr [ebx+edx], 1
0x100264a3  mov     dword ptr [edi+5Ch], 1
0x100264aa  mov     dword ptr [edi+4Ch], 0
0x100264b1  xor     eax, eax
0x100264b3  pop     edi
0x100264b4  pop     esi
0x100264b5  pop     ebx
0x100264b6  mov     esp, ebp
0x100264b8  pop     ebp
0x100264b9  retn    4
```
