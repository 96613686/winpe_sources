# LEQ_process

- ea: `0x18004c620`
- end: `0x18004ca56`
- name: `LEQ_process`
- size: `1078`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001eea0`

## callees

- `0x18004c0f0`
- `0x18004c620`
- `0x1800886fc`

## import_xrefs

- `mfperfhelper!__imp_ippsCopy_8u` at `0x18004c78e`
- `mfperfhelper!__imp_ippsCopy_8u` at `0x18004c8b8`
- `mfperfhelper!__imp_ippsCopy_8u` at `0x18004ca18`
- `mfperfhelper!__imp_ippsCopy_8u` at `0x18004c78e`
- `mfperfhelper!__imp_ippsCopy_8u` at `0x18004c8b8`
- `mfperfhelper!__imp_ippsCopy_8u` at `0x18004ca18`

## pseudocode

```c
void *__fastcall LEQ_process(_QWORD *a1, int a2, char *a3, char *a4)
{
  int v4; // r12d
  int v6; // ecx
  __int64 v10; // rax
  int v11; // edi
  void *result; // rax
  unsigned int v13; // ecx
  int v14; // ecx
  const void *v15; // rdx
  int v16; // r15d
  __int64 v17; // rax
  char *v18; // rsi
  char *v19; // r14
  void *v20; // rcx
  __int64 v21; // rcx
  int v22; // eax
  int v23; // ebp
  char *v24; // rsi
  char *v25; // rdx
  size_t v26; // r8
  char *v27; // rcx
  __int64 v28; // rcx
  int v29; // edx
  int v30; // r15d
  __int64 v31; // r8
  char *v32; // rbp
  __int64 v33; // r14
  int v34; // r8d
  int v35; // r8d
  char *v36; // rsi
  unsigned int v37; // r8d
  int v38; // r15d
  char *i; // rbp
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rdi
  char *v43; // rsi
  char *v44; // r14

  v4 = *((_DWORD *)a1 + 14);
  v6 = *((_DWORD *)a1 + 15);
  v10 = a1[2];
  v11 = (*((_DWORD *)a1 + 17) >> 1) - v6;
  *((_DWORD *)a1 + 68) = 0;
  if ( a2 < v11 )
    v11 = a2;
  memcpy_0(a4, (const void *)(v10 + 4LL * v4 * v6), 4LL * (unsigned int)(v11 * v4));
  result = memcpy_0(
             (void *)(a1[1] + 4LL * *((_DWORD *)a1 + 15) * v4),
             a3,
             4LL * (unsigned int)(*((_DWORD *)a1 + 14) * v11));
  v13 = *((_DWORD *)a1 + 17);
  *((_DWORD *)a1 + 15) += v11;
  v14 = v13 >> 1;
  if ( *((_DWORD *)a1 + 15) >= v14 )
  {
    v15 = (const void *)a1[3];
    v16 = a2 - v11;
    v17 = 4LL * (unsigned int)(*((_DWORD *)a1 + 14) * v11);
    v18 = &a3[v17];
    v19 = &a4[v17];
    if ( v16 >= 2 * v14 )
    {
      memcpy_0(v19, v15, 4LL * v4 * v14);
      LEQ_block(*a1, a1[1], (_DWORD)v19, (_DWORD)v19 + 4 * v4 * (*((_DWORD *)a1 + 17) >> 1), (__int64)a1);
      v28 = a1[1];
      v29 = *((_DWORD *)a1 + 17) >> 1;
      v30 = v16 - v29;
      v31 = 4LL * v4 * v29;
      v32 = &v19[v31];
      if ( v30 >= 2 * v29 )
      {
        LEQ_block(v28, (_DWORD)v18, v31 + (_DWORD)v19, v31 + (_DWORD)v32, (__int64)a1);
        v37 = *((_DWORD *)a1 + 17);
        v38 = v30 - (v37 >> 1);
        for ( i = &v32[4 * v4 * (v37 >> 1)]; v38 >= (int)(2 * (v37 >> 1)); i += v40 )
        {
          LEQ_block(
            (_DWORD)v18,
            (_DWORD)v18 + 4 * v4 * (v37 >> 1),
            (_DWORD)i,
            (_DWORD)i + 4 * v4 * (v37 >> 1),
            (__int64)a1);
          v37 = *((_DWORD *)a1 + 17);
          v38 -= v37 >> 1;
          v40 = 4LL * (int)(v4 * (v37 >> 1));
          v18 += v40;
        }
        LEQ_block((_DWORD)v18, (_DWORD)v18 + 4 * v4 * (v37 >> 1), (_DWORD)i, a1[2], (__int64)a1);
        v16 = v38 - (*((_DWORD *)a1 + 17) >> 1);
        v41 = v4 * (*((_DWORD *)a1 + 17) >> 1);
        v42 = 4 * v41;
        v43 = &v18[4 * v41];
        LEQ_block((_DWORD)v43, 4 * v41 + (_DWORD)v43, a1[2], a1[3], (__int64)a1);
        v44 = &v43[4 * v4 * (*((_DWORD *)a1 + 17) >> 1)];
        memcpy_0(&i[v42], (const void *)a1[2], 4LL * v4 * v16);
        ippsCopy_8u(v44, *a1, (unsigned int)(4 * v4 * (*((_DWORD *)a1 + 17) >> 1)));
        v26 = 4LL * v4 * v16;
        v27 = (char *)a1[1];
        v25 = &v44[4 * v4 * (*((_DWORD *)a1 + 17) >> 1)];
      }
      else
      {
        LEQ_block(v28, (_DWORD)v18, v31 + (_DWORD)v19, a1[2], (__int64)a1);
        v33 = 4LL * v4 * (*((_DWORD *)a1 + 17) >> 1);
        LEQ_block((_DWORD)v18, v33 + (_DWORD)v18, a1[2], a1[3], (__int64)a1);
        v34 = *((_DWORD *)a1 + 17) >> 1;
        v16 = v30 - v34;
        v35 = v4 * v34;
        v36 = &v18[4 * v35];
        ippsCopy_8u(v36, *a1, (unsigned int)(4 * v35));
        memcpy_0((void *)a1[1], &v36[4 * v4 * (*((_DWORD *)a1 + 17) >> 1)], 4LL * v4 * v16);
        v25 = (char *)a1[2];
        v27 = &v32[v33];
        v26 = 4LL * v4 * v16;
      }
    }
    else
    {
      if ( v16 < v14 )
      {
        LEQ_block(*a1, a1[1], (_DWORD)v15, a1[2], (__int64)a1);
        memcpy_0((void *)*a1, v18, 4LL * v4 * v16);
        memcpy_0(v19, (const void *)a1[3], 4LL * v4 * v16);
        v20 = (void *)*a1;
        *a1 = a1[1];
        result = (void *)a1[3];
        a1[1] = v20;
        v21 = a1[2];
        a1[2] = result;
        a1[3] = v21;
LABEL_14:
        *((_DWORD *)a1 + 15) = v16;
        return result;
      }
      memcpy_0(v19, v15, 4LL * v4 * v14);
      LEQ_block(*a1, a1[1], (_DWORD)v19, a1[2], (__int64)a1);
      v22 = *((_DWORD *)a1 + 17) >> 1;
      v16 -= v22;
      v23 = v4 * v22;
      ippsCopy_8u(v18, *a1, (unsigned int)(4 * v4 * v22));
      v24 = &v18[4 * v4 * (*((_DWORD *)a1 + 17) >> 1)];
      LEQ_block(a1[1], *a1, a1[2], a1[3], (__int64)a1);
      memcpy_0((void *)a1[1], v24, 4LL * v4 * v16);
      v25 = (char *)a1[2];
      v26 = 4LL * v4 * v16;
      v27 = &v19[4 * v23];
    }
    result = memcpy_0(v27, v25, v26);
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x18004c620  push    rbx
0x18004c622  push    rbp
0x18004c623  push    rsi
0x18004c624  push    rdi
0x18004c625  push    r12
0x18004c627  push    r15
0x18004c629  sub     rsp, 38h
0x18004c62d  mov     r12d, [rcx+38h]
0x18004c631  mov     rbx, rcx
0x18004c634  mov     ecx, [rcx+3Ch]
0x18004c637  mov     rsi, r8
0x18004c63a  mov     r8d, r12d
0x18004c63d  mov     r15d, edx
0x18004c640  mov     rbp, r9
0x18004c643  mov     edi, [rbx+44h]
0x18004c646  mov     rax, [rbx+10h]
0x18004c64a  shr     edi, 1
0x18004c64c  sub     edi, ecx
0x18004c64e  mov     dword ptr [rbx+110h], 0
0x18004c658  cmp     edx, edi
0x18004c65a  cmovl   edi, edx
0x18004c65d  imul    ecx, r12d
0x18004c661  imul    r8d, edi
0x18004c665  movsxd  rcx, ecx
0x18004c668  shl     r8, 2; Size
0x18004c66c  lea     rdx, [rax+rcx*4]; Src
0x18004c670  mov     rcx, r9; void *
0x18004c673  call    memcpy_0
0x18004c678  mov     eax, r12d
0x18004c67b  mov     r8d, edi
0x18004c67e  imul    eax, [rbx+3Ch]
0x18004c682  mov     rdx, rsi; Src
0x18004c685  imul    r8d, [rbx+38h]
0x18004c68a  movsxd  rcx, eax
0x18004c68d  mov     rax, [rbx+8]
0x18004c691  shl     r8, 2; Size
0x18004c695  lea     rcx, [rax+rcx*4]; void *
0x18004c699  call    memcpy_0
0x18004c69e  mov     ecx, [rbx+44h]
0x18004c6a1  add     [rbx+3Ch], edi
0x18004c6a4  shr     ecx, 1
0x18004c6a6  cmp     [rbx+3Ch], ecx
0x18004c6a9  jl      loc_18004CA48
0x18004c6af  mov     rdx, [rbx+18h]; Src
0x18004c6b3  mov     eax, edi
0x18004c6b5  imul    eax, [rbx+38h]
0x18004c6b9  sub     r15d, edi
0x18004c6bc  mov     [rsp+68h+arg_0], r14
0x18004c6c1  lea     rax, ds:0[rax*4]
0x18004c6c9  add     rsi, rax
0x18004c6cc  lea     r14, [rax+rbp]
0x18004c6d0  lea     eax, [rcx+rcx]
0x18004c6d3  cmp     r15d, eax
0x18004c6d6  jge     loc_18004C7F2
0x18004c6dc  cmp     r15d, ecx
0x18004c6df  jge     short loc_18004C747
0x18004c6e1  mov     r9, [rbx+10h]
0x18004c6e5  mov     r8, rdx
0x18004c6e8  mov     rdx, [rbx+8]
0x18004c6ec  mov     rcx, [rbx]
0x18004c6ef  mov     [rsp+68h+var_48], rbx
0x18004c6f4  call    LEQ_block
0x18004c6f9  mov     rcx, [rbx]; void *
0x18004c6fc  mov     eax, r15d
0x18004c6ff  imul    eax, r12d
0x18004c703  mov     rdx, rsi; Src
0x18004c706  movsxd  rdi, eax
0x18004c709  shl     rdi, 2
0x18004c70d  mov     r8, rdi; Size
0x18004c710  call    memcpy_0
0x18004c715  mov     rdx, [rbx+18h]; Src
0x18004c719  mov     r8, rdi; Size
0x18004c71c  mov     rcx, r14; void *
0x18004c71f  call    memcpy_0
0x18004c724  mov     rcx, [rbx]
0x18004c727  mov     rax, [rbx+8]
0x18004c72b  mov     [rbx], rax
0x18004c72e  mov     rax, [rbx+18h]
0x18004c732  mov     [rbx+8], rcx
0x18004c736  mov     rcx, [rbx+10h]
0x18004c73a  mov     [rbx+10h], rax
0x18004c73e  mov     [rbx+18h], rcx
0x18004c742  jmp     loc_18004CA3F
0x18004c747  imul    ecx, r12d
0x18004c74b  movsxd  r8, ecx
0x18004c74e  mov     rcx, r14; void *
0x18004c751  shl     r8, 2; Size
0x18004c755  call    memcpy_0
0x18004c75a  mov     r9, [rbx+10h]
0x18004c75e  mov     r8, r14
0x18004c761  mov     rdx, [rbx+8]
0x18004c765  mov     rcx, [rbx]
0x18004c768  mov     [rsp+68h+var_48], rbx
0x18004c76d  call    LEQ_block
0x18004c772  mov     eax, [rbx+44h]
0x18004c775  mov     rcx, rsi
0x18004c778  mov     rdx, [rbx]
0x18004c77b  shr     eax, 1
0x18004c77d  mov     ebp, eax
0x18004c77f  sub     r15d, eax
0x18004c782  imul    ebp, r12d
0x18004c786  lea     r8d, ds:0[rbp*4]
0x18004c78e  call    cs:__imp_ippsCopy_8u
0x18004c795  nop     dword ptr [rax+rax+00h]
0x18004c79a  mov     eax, [rbx+44h]
0x18004c79d  mov     r9, [rbx+18h]
0x18004c7a1  mov     r8, [rbx+10h]
0x18004c7a5  mov     rdx, [rbx]
0x18004c7a8  mov     rcx, [rbx+8]
0x18004c7ac  shr     eax, 1
0x18004c7ae  imul    eax, r12d
0x18004c7b2  mov     [rsp+68h+var_48], rbx
0x18004c7b7  cdqe
0x18004c7b9  lea     rsi, [rsi+rax*4]
0x18004c7bd  call    LEQ_block
0x18004c7c2  mov     rcx, [rbx+8]; void *
0x18004c7c6  mov     eax, r15d
0x18004c7c9  imul    eax, r12d
0x18004c7cd  mov     rdx, rsi; Src
0x18004c7d0  movsxd  rdi, eax
0x18004c7d3  shl     rdi, 2
0x18004c7d7  mov     r8, rdi; Size
0x18004c7da  call    memcpy_0
0x18004c7df  mov     rdx, [rbx+10h]
0x18004c7e3  mov     r8, rdi
0x18004c7e6  movsxd  rax, ebp
0x18004c7e9  lea     rcx, [r14+rax*4]
0x18004c7ed  jmp     loc_18004CA3A
0x18004c7f2  imul    ecx, r12d
0x18004c7f6  movsxd  r8, ecx
0x18004c7f9  mov     rcx, r14; void *
0x18004c7fc  shl     r8, 2; Size
0x18004c800  call    memcpy_0
0x18004c805  mov     eax, [rbx+44h]
0x18004c808  mov     r8, r14
0x18004c80b  mov     rdx, [rbx+8]
0x18004c80f  mov     rcx, [rbx]
0x18004c812  shr     eax, 1
0x18004c814  imul    eax, r12d
0x18004c818  mov     [rsp+68h+var_48], rbx
0x18004c81d  cdqe
0x18004c81f  lea     r9, [r14+rax*4]
0x18004c823  call    LEQ_block
0x18004c828  mov     edx, [rbx+44h]
0x18004c82b  mov     rcx, [rbx+8]
0x18004c82f  shr     edx, 1
0x18004c831  mov     eax, edx
0x18004c833  mov     [rsp+68h+var_48], rbx
0x18004c838  imul    eax, r12d
0x18004c83c  sub     r15d, edx
0x18004c83f  cdqe
0x18004c841  lea     r8, ds:0[rax*4]
0x18004c849  lea     eax, [rdx+rdx]
0x18004c84c  mov     rdx, rsi
0x18004c84f  lea     rbp, [r8+r14]
0x18004c853  cmp     r15d, eax
0x18004c856  jge     loc_18004C8FD
0x18004c85c  mov     r9, [rbx+10h]
0x18004c860  mov     r8, rbp
0x18004c863  call    LEQ_block
0x18004c868  mov     eax, [rbx+44h]
0x18004c86b  mov     rcx, rsi
0x18004c86e  mov     r9, [rbx+18h]
0x18004c872  mov     r8, [rbx+10h]
0x18004c876  shr     eax, 1
0x18004c878  imul    eax, r12d
0x18004c87c  mov     [rsp+68h+var_48], rbx
0x18004c881  cdqe
0x18004c883  lea     r14, ds:0[rax*4]
0x18004c88b  lea     rdx, [r14+rsi]
0x18004c88f  call    LEQ_block
0x18004c894  mov     ecx, [rbx+44h]
0x18004c897  mov     rdx, [rbx]
0x18004c89a  shr     ecx, 1
0x18004c89c  mov     r8d, ecx
0x18004c89f  sub     r15d, ecx
0x18004c8a2  imul    r8d, r12d
0x18004c8a6  movsxd  rax, r8d
0x18004c8a9  lea     r8d, ds:0[r8*4]
0x18004c8b1  lea     rsi, [rsi+rax*4]
0x18004c8b5  mov     rcx, rsi
0x18004c8b8  call    cs:__imp_ippsCopy_8u
0x18004c8bf  nop     dword ptr [rax+rax+00h]
0x18004c8c4  mov     rcx, [rbx+8]; void *
0x18004c8c8  mov     eax, r15d
0x18004c8cb  imul    eax, r12d
0x18004c8cf  movsxd  rdi, eax
0x18004c8d2  mov     eax, [rbx+44h]
0x18004c8d5  shr     eax, 1
0x18004c8d7  imul    eax, r12d
0x18004c8db  shl     rdi, 2
0x18004c8df  mov     r8, rdi; Size
0x18004c8e2  cdqe
0x18004c8e4  lea     rdx, [rsi+rax*4]; Src
0x18004c8e8  call    memcpy_0
0x18004c8ed  mov     rdx, [rbx+10h]
0x18004c8f1  lea     rcx, [r14+rbp]
0x18004c8f5  mov     r8, rdi
0x18004c8f8  jmp     loc_18004CA3A
0x18004c8fd  lea     r9, [r8+rbp]
0x18004c901  mov     r8, rbp
0x18004c904  call    LEQ_block
0x18004c909  mov     r8d, [rbx+44h]
0x18004c90d  mov     ecx, r8d
0x18004c910  shr     ecx, 1
0x18004c912  mov     eax, ecx
0x18004c914  sub     r15d, ecx
0x18004c917  imul    eax, r12d
0x18004c91b  cdqe
0x18004c91d  lea     rbp, [rbp+rax*4+0]
0x18004c922  lea     eax, [rcx+rcx]
0x18004c925  cmp     r15d, eax
0x18004c928  jl      short loc_18004C980
0x18004c92a  nop     word ptr [rax+rax+00h]
0x18004c930  shr     r8d, 1
0x18004c933  mov     rcx, rsi
0x18004c936  imul    r8d, r12d
0x18004c93a  mov     [rsp+68h+var_48], rbx
0x18004c93f  movsxd  rax, r8d
0x18004c942  mov     r8, rbp
0x18004c945  lea     r9, ds:0[rax*4]
0x18004c94d  add     r9, rbp
0x18004c950  lea     rdx, [rsi+rax*4]
0x18004c954  call    LEQ_block
0x18004c959  mov     r8d, [rbx+44h]
0x18004c95d  mov     edx, r8d
0x18004c960  shr     edx, 1
0x18004c962  mov     eax, edx
0x18004c964  sub     r15d, edx
0x18004c967  imul    eax, r12d
0x18004c96b  movsxd  rcx, eax
0x18004c96e  lea     eax, [rdx+rdx]
0x18004c971  shl     rcx, 2
0x18004c975  add     rsi, rcx
0x18004c978  add     rbp, rcx
0x18004c97b  cmp     r15d, eax
0x18004c97e  jge     short loc_18004C930
0x18004c980  mov     r9, [rbx+10h]
0x18004c984  mov     rcx, rsi
0x18004c987  shr     r8d, 1
0x18004c98a  imul    r8d, r12d
0x18004c98e  mov     [rsp+68h+var_48], rbx
0x18004c993  movsxd  rax, r8d
0x18004c996  mov     r8, rbp
0x18004c999  lea     rdx, [rsi+rax*4]
0x18004c99d  call    LEQ_block
0x18004c9a2  mov     ecx, [rbx+44h]
0x18004c9a5  mov     r9, [rbx+18h]
0x18004c9a9  mov     r8, [rbx+10h]
0x18004c9ad  shr     ecx, 1
0x18004c9af  mov     eax, ecx
0x18004c9b1  mov     [rsp+68h+var_48], rbx
0x18004c9b6  imul    eax, r12d
0x18004c9ba  sub     r15d, ecx
0x18004c9bd  cdqe
0x18004c9bf  lea     rdi, ds:0[rax*4]
0x18004c9c7  add     rsi, rdi
0x18004c9ca  mov     rcx, rsi
0x18004c9cd  lea     rdx, [rdi+rsi]
0x18004c9d1  call    LEQ_block
0x18004c9d6  mov     eax, [rbx+44h]
0x18004c9d9  lea     rcx, [rdi+rbp]; void *
0x18004c9dd  mov     rdx, [rbx+10h]; Src
0x18004c9e1  shr     eax, 1
0x18004c9e3  imul    eax, r12d
0x18004c9e7  cdqe
0x18004c9e9  lea     r14, [rsi+rax*4]
0x18004c9ed  mov     eax, r15d
0x18004c9f0  imul    eax, r12d
0x18004c9f4  movsxd  rsi, eax
0x18004c9f7  shl     rsi, 2
0x18004c9fb  mov     r8, rsi; Size
0x18004c9fe  call    memcpy_0
0x18004ca03  mov     r8d, [rbx+44h]
0x18004ca07  mov     rcx, r14
0x18004ca0a  mov     rdx, [rbx]
0x18004ca0d  shr     r8d, 1
0x18004ca10  imul    r8d, r12d
0x18004ca14  shl     r8d, 2
0x18004ca18  call    cs:__imp_ippsCopy_8u
0x18004ca1f  nop     dword ptr [rax+rax+00h]
0x18004ca24  mov     eax, [rbx+44h]
0x18004ca27  mov     r8, rsi; Size
0x18004ca2a  mov     rcx, [rbx+8]; void *
0x18004ca2e  shr     eax, 1
0x18004ca30  imul    eax, r12d
0x18004ca34  cdqe
0x18004ca36  lea     rdx, [r14+rax*4]; Src
0x18004ca3a  call    memcpy_0
0x18004ca3f  mov     r14, [rsp+68h+arg_0]
0x18004ca44  mov     [rbx+3Ch], r15d
0x18004ca48  add     rsp, 38h
0x18004ca4c  pop     r15
0x18004ca4e  pop     r12
0x18004ca50  pop     rdi
0x18004ca51  pop     rsi
0x18004ca52  pop     rbp
0x18004ca53  pop     rbx
0x18004ca54  retn
```
