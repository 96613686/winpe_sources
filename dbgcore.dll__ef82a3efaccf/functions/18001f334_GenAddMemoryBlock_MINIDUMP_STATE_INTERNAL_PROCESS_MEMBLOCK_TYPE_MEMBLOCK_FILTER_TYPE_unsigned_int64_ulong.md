# GenAddMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE,unsigned __int64,ulong)

- ea: `0x18001f334`
- end: `0x18001f82d`
- name: `?GenAddMemoryBlock@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@W4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@_KK@Z`
- size: `1273`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, __int64, unsigned int, unsigned int, unsigned __int64, unsigned int)`
- caller_count: `14`
- callee_count: `8`
- tags: ``

## callers

- `0x1800053dc`
- `0x180005700`
- `0x18000670c`
- `0x18000f8e8`
- `0x180016930`
- `0x180016c20`
- `0x180016c50`
- `0x180016eec`
- `0x180016f50`
- `0x180017220`
- `0x18001766c`
- `0x180017890`
- `0x18001b970`
- `0x18001f8f0`

## callees

- `0x18001951c`
- `0x18001f164`
- `0x18001f334`
- `0x18001fbd0`
- `0x18001fe48`
- `0x18001febc`
- `0x18001fff8`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall GenAddMemoryBlock(
        struct _MINIDUMP_STATE *a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  struct _VA_RANGE_REF *v6; // r15
  __int64 result; // rax
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // rbx
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r8
  __int64 v15; // rcx
  int v16; // r9d
  unsigned __int64 v17; // r9
  unsigned __int64 v18; // r10
  int v19; // ecx
  int v20; // eax
  unsigned __int64 v21; // r12
  unsigned __int64 v22; // rdx
  unsigned int v23; // r13d
  struct _VA_RANGE_REF *v24; // rcx
  _QWORD *v25; // rdx
  int v26; // r11d
  unsigned __int64 *v27; // r8
  unsigned __int64 v28; // r15
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // rdx
  unsigned __int64 v31; // r11
  unsigned __int64 v32; // rax
  bool v33; // cl
  struct _VA_RANGE_REF *v34; // rax
  struct _MINIDUMP_STATE *v35; // rcx
  struct _VA_RANGE_REF *v36; // rax
  struct _MINIDUMP_STATE *v37; // rcx
  unsigned int v38; // ebx
  struct _VA_RANGE_REF *v39; // rax
  struct _MINIDUMP_STATE *v40; // rcx
  unsigned int v41; // r15d
  struct _VA_RANGE *MemoryBlock; // rax
  struct _VA_RANGE_REF *v43; // rcx
  struct _VA_RANGE_REF *v44; // rdx
  _QWORD *v45; // r8
  unsigned int v46; // [rsp+40h] [rbp-40h]
  int v47; // [rsp+44h] [rbp-3Ch]
  unsigned __int64 v48; // [rsp+48h] [rbp-38h] BYREF
  struct _VA_RANGE_REF *v49; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v50; // [rsp+58h] [rbp-28h]
  unsigned __int64 v51; // [rsp+60h] [rbp-20h]
  unsigned __int64 v52; // [rsp+68h] [rbp-18h]
  unsigned __int64 v53; // [rsp+70h] [rbp-10h]

  v6 = 0;
  v48 = 0;
  v49 = 0;
  if ( (unsigned int)GenCheckCancel(a1) )
    return 2147943623LL;
  v10 = a5;
  v11 = a5 + a6;
  if ( v11 < a5 )
    v11 = -1;
  if ( !a6 || a5 == v11 )
    return 0;
  if ( v11 - a5 > ~((*((_DWORD *)a1 + 14) & 0x100000) == 0 ? 0x20 : 0) - *(_DWORD *)(a2 + 172) )
  {
    v12 = *((_QWORD *)a1 + 5);
    *((_DWORD *)a1 + 44) |= 8u;
    (*(void (__fastcall **)(__int64, __int64, const char *))(*(_QWORD *)v12 + 8LL))(
      v12,
      4,
      "GenAddMemoryBlock total size overflow");
    return 2147942487LL;
  }
  if ( a5 >= v11 )
    return 0;
  v13 = (*((_DWORD *)a1 + 14) & 0x100000) == 0 ? 0x10 : 0;
  if ( a5 > v13 )
    v14 = a5 - v13;
  else
    v14 = 0;
  v15 = *((_QWORD *)a1 + 2);
  v16 = v13 + v11;
  v48 = v14;
  if ( v13 + v11 < v11 )
    v16 = -1;
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, unsigned __int64, _QWORD, unsigned __int64 *, unsigned int *))(*(_QWORD *)v15 + 264LL))(
         v15,
         *(_QWORD *)a1,
         v14,
         (unsigned int)(v16 - v14),
         &v48,
         &a6) )
  {
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, _QWORD, unsigned __int64 *, unsigned int *))(**((_QWORD **)a1 + 2) + 264LL))(
               *((_QWORD *)a1 + 2),
               *(_QWORD *)a1,
               a5,
               (unsigned int)(v11 - a5),
               &v48,
               &a6);
    if ( (_DWORD)result )
      return result;
  }
  if ( !a6 )
    return 0;
  v17 = v48;
  if ( a5 < v48 )
    v10 = v48;
  v18 = v48 + a6;
  v51 = v18;
  if ( v11 > v18 )
    v11 = v48 + a6;
  if ( v11 <= v10 )
    return 0;
  v19 = v18 + 1;
  v47 = v18 + 1;
LABEL_24:
  v20 = *((_DWORD *)a1 + 47);
  v21 = 0;
  v22 = v17;
  v50 = v17;
  v23 = (v19 + v20 + ((unsigned int)v17 & v20) - (unsigned int)v17) >> *((_DWORD *)a1 + 46);
  if ( v6 )
  {
    do
    {
      v24 = v6;
      v6 = (struct _VA_RANGE_REF *)*((_QWORD *)v6 + 1);
      v25 = *(_QWORD **)v24;
      if ( *(_QWORD *)v24 )
      {
        *v25 = *(_QWORD *)(a2 + 7552);
        *(_QWORD *)(a2 + 7552) = v25;
      }
      *(_QWORD *)v24 = *(_QWORD *)(a2 + 7584);
      *(_QWORD *)(a2 + 7584) = v24;
    }
    while ( v6 );
    v17 = v48;
    v22 = v50;
    v49 = 0;
  }
LABEL_29:
  if ( v23 )
  {
    v26 = a3;
LABEL_31:
    v27 = *(unsigned __int64 **)(a2 + 8 * ((v22 >> *((_DWORD *)a1 + 46)) % 0x397) + 176);
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !v27 )
        {
          --v23;
          v22 = *((unsigned int *)a1 + 47) + v50 + 1;
          v50 = v22;
          goto LABEL_29;
        }
        v28 = *v27;
        v27 = (unsigned __int64 *)v27[1];
        v29 = *(_QWORD *)v28;
        if ( *(_QWORD *)v28 <= v18 )
        {
          v30 = v29 + *(unsigned int *)(v28 + 8);
          if ( v30 >= v17 )
            break;
        }
      }
      if ( v10 < v29 )
        goto LABEL_39;
      if ( v30 >= v11 )
      {
        result = 0;
        if ( a4 != *(_DWORD *)(v28 + 20) )
          result = GenAddExtendFilterList(a4, a2, v28 + 24, v10, a6, v26, a4);
        if ( a3 != *(_DWORD *)(v28 + 16) )
          *(_DWORD *)(v28 + 16) = 1;
        return result;
      }
      if ( v10 <= v29 )
      {
LABEL_39:
        if ( v11 >= v30 && v26 != *(_DWORD *)(v28 + 16) )
        {
          GenFreeMemoryBlock(a1, (struct _INTERNAL_PROCESS *)a2, (struct _VA_RANGE *)v28, 0);
          v18 = v51;
          v19 = v47;
          v17 = v48;
          v6 = v49;
          goto LABEL_24;
        }
      }
      v31 = v10;
      v32 = v11;
      if ( v29 <= v10 )
        v31 = *(_QWORD *)v28;
      v53 = v31;
      if ( v30 >= v11 )
        v32 = v30;
      v52 = v32;
      v33 = v30 < v11 && v29 <= v10;
      v46 = *(_DWORD *)(v28 + 20);
      if ( v46 != a4 )
      {
        v38 = *(_DWORD *)(v28 + 16);
        v39 = GenFreeMemoryBlock(a1, (struct _INTERNAL_PROCESS *)a2, (struct _VA_RANGE *)v28, 1u);
        GenMergeFilterList(v40, (struct _INTERNAL_PROCESS *)a2, &v49, v39);
        GenAddExtendFilterList(a3, a2, &v49, v10, a6, a3, a4);
        v26 = v38;
        v10 = v53;
        a3 = v38;
        v11 = v52;
        a4 = v46;
        goto LABEL_53;
      }
      v11 = v52;
      v10 = v31;
      v26 = 1;
      a3 = 1;
      if ( !v33 )
      {
        if ( v21 )
        {
LABEL_50:
          if ( v21 != 1 )
          {
            v34 = GenFreeMemoryBlock(a1, (struct _INTERNAL_PROCESS *)a2, (struct _VA_RANGE *)v21, 1u);
            GenMergeFilterList(v35, (struct _INTERNAL_PROCESS *)a2, &v49, v34);
          }
        }
        v21 = 1;
        v36 = GenFreeMemoryBlock(a1, (struct _INTERNAL_PROCESS *)a2, (struct _VA_RANGE *)v28, 1u);
        GenMergeFilterList(v37, (struct _INTERNAL_PROCESS *)a2, &v49, v36);
        v26 = 1;
LABEL_53:
        v18 = v51;
        v17 = v48;
        v22 = v50;
        goto LABEL_31;
      }
      if ( v21 && v21 != v28 )
        goto LABEL_50;
      v21 = v28;
    }
  }
  if ( v21 <= 1 )
    v21 = 0;
  v41 = GenAddOrExtendMemoryRange(a1, a2, v21, v10, v11, a3, a4);
  if ( v41 )
  {
    v43 = v49;
    while ( v43 )
    {
      v44 = v43;
      v43 = (struct _VA_RANGE_REF *)*((_QWORD *)v43 + 1);
      v45 = *(_QWORD **)v44;
      if ( *(_QWORD *)v44 )
      {
        *v45 = *(_QWORD *)(a2 + 7552);
        *(_QWORD *)(a2 + 7552) = v45;
      }
      *(_QWORD *)v44 = *(_QWORD *)(a2 + 7584);
      *(_QWORD *)(a2 + 7584) = v44;
    }
  }
  else
  {
    MemoryBlock = GenFindMemoryBlock(a1, (struct _INTERNAL_PROCESS *)a2, v10, (int)v11 - (int)v10);
    if ( MemoryBlock )
      *((_QWORD *)MemoryBlock + 3) = v49;
  }
  return v41;
}

```

## disassembly

```asm
0x18001f334  mov     [rsp-38h+arg_0], rbx
0x18001f339  mov     [rsp-38h+arg_18], r9d
0x18001f33e  mov     [rsp-38h+arg_10], r8d
0x18001f343  push    rbp
0x18001f344  push    rsi
0x18001f345  push    rdi
0x18001f346  push    r12
0x18001f348  push    r13
0x18001f34a  push    r14
0x18001f34c  push    r15
0x18001f34e  mov     rbp, rsp
0x18001f351  sub     rsp, 80h
0x18001f358  xor     r15d, r15d
0x18001f35b  mov     [rbp+var_38], 0
0x18001f363  mov     [rbp+var_30], r15
0x18001f367  mov     rsi, rdx
0x18001f36a  mov     r14, rcx
0x18001f36d  call    ?GenCheckCancel@@YAHPEAU_MINIDUMP_STATE@@@Z; GenCheckCancel(_MINIDUMP_STATE *)
0x18001f372  test    eax, eax
0x18001f374  jz      short loc_18001F380
0x18001f376  mov     eax, 800704C7h
0x18001f37b  jmp     loc_18001F812
0x18001f380  mov     ecx, [rbp+arg_28]
0x18001f383  or      r10, 0FFFFFFFFFFFFFFFFh
0x18001f387  mov     rdi, [rbp+arg_20]
0x18001f38b  lea     rbx, [rdi+rcx]
0x18001f38f  cmp     rbx, rdi
0x18001f392  cmovb   rbx, r10
0x18001f396  test    ecx, ecx
0x18001f398  jz      loc_18001F810
0x18001f39e  cmp     rdi, rbx
0x18001f3a1  jz      loc_18001F810
0x18001f3a7  mov     edx, [r14+38h]
0x18001f3ab  and     edx, 100000h
0x18001f3b1  mov     eax, edx
0x18001f3b3  neg     eax
0x18001f3b5  mov     rax, rbx
0x18001f3b8  sbb     ecx, ecx
0x18001f3ba  sub     rax, rdi
0x18001f3bd  not     ecx
0x18001f3bf  and     ecx, 20h
0x18001f3c2  not     ecx
0x18001f3c4  sub     ecx, [rsi+0ACh]
0x18001f3ca  cmp     rax, rcx
0x18001f3cd  jbe     short loc_18001F3FC
0x18001f3cf  mov     rcx, [r14+28h]
0x18001f3d3  lea     r8, aGenaddmemorybl; "GenAddMemoryBlock total size overflow"
0x18001f3da  or      dword ptr [r14+0B0h], 8
0x18001f3e2  lea     edx, [r10+5]
0x18001f3e6  mov     rax, [rcx]
0x18001f3e9  mov     rax, [rax+8]
0x18001f3ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3f2  mov     eax, 80070057h
0x18001f3f7  jmp     loc_18001F812
0x18001f3fc  cmp     rdi, rbx
0x18001f3ff  jnb     loc_18001F810
0x18001f405  neg     edx
0x18001f407  sbb     rax, rax
0x18001f40a  not     rax
0x18001f40d  and     eax, 10h
0x18001f410  cmp     rdi, rax
0x18001f413  ja      short loc_18001F41A
0x18001f415  xor     r8d, r8d
0x18001f418  jmp     short loc_18001F420
0x18001f41a  mov     r8, rdi
0x18001f41d  sub     r8, rax
0x18001f420  mov     rcx, [r14+10h]
0x18001f424  lea     r9, [rax+rbx]
0x18001f428  cmp     r9, rbx
0x18001f42b  mov     [rbp+var_38], r8
0x18001f42f  lea     rdx, [rbp+arg_28]
0x18001f433  mov     [rsp+80h+var_58], rdx
0x18001f438  cmovb   r9, r10
0x18001f43c  mov     rax, [rcx]
0x18001f43f  lea     rdx, [rbp+var_38]
0x18001f443  mov     [rsp+80h+var_60], rdx
0x18001f448  sub     r9d, r8d
0x18001f44b  mov     rdx, [r14]
0x18001f44e  mov     rax, [rax+108h]
0x18001f455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f45a  test    eax, eax
0x18001f45c  jz      short loc_18001F497
0x18001f45e  mov     rcx, [r14+10h]
0x18001f462  lea     rdx, [rbp+arg_28]
0x18001f466  mov     [rsp+80h+var_58], rdx
0x18001f46b  mov     r9d, ebx
0x18001f46e  lea     rdx, [rbp+var_38]
0x18001f472  sub     r9d, edi
0x18001f475  mov     [rsp+80h+var_60], rdx
0x18001f47a  mov     r8, rdi
0x18001f47d  mov     rax, [rcx]
0x18001f480  mov     rdx, [r14]
0x18001f483  mov     rax, [rax+108h]
0x18001f48a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f48f  test    eax, eax
0x18001f491  jnz     loc_18001F812
0x18001f497  mov     eax, [rbp+arg_28]
0x18001f49a  test    eax, eax
0x18001f49c  jz      loc_18001F810
0x18001f4a2  mov     r9, [rbp+var_38]
0x18001f4a6  cmp     rdi, r9
0x18001f4a9  cmovb   rdi, r9
0x18001f4ad  lea     r10, [r9+rax]
0x18001f4b1  cmp     rbx, r10
0x18001f4b4  mov     [rbp+var_20], r10
0x18001f4b8  cmova   rbx, r10
0x18001f4bc  cmp     rbx, rdi
0x18001f4bf  jbe     loc_18001F810
0x18001f4c5  lea     ecx, [r10+1]
0x18001f4c9  mov     [rbp+var_3C], ecx
0x18001f4cc  mov     eax, [r14+0BCh]
0x18001f4d3  xor     r12d, r12d
0x18001f4d6  mov     r13d, eax
0x18001f4d9  mov     rdx, r9
0x18001f4dc  and     r13d, r9d
0x18001f4df  mov     [rbp+var_28], rdx
0x18001f4e3  sub     r13d, r9d
0x18001f4e6  add     r13d, eax
0x18001f4e9  add     r13d, ecx
0x18001f4ec  mov     ecx, [r14+0B8h]
0x18001f4f3  shr     r13d, cl
0x18001f4f6  test    r15, r15
0x18001f4f9  jz      short loc_18001F53D
0x18001f4fb  mov     rcx, r15
0x18001f4fe  mov     r15, [r15+8]
0x18001f502  mov     rdx, [rcx]
0x18001f505  test    rdx, rdx
0x18001f508  jz      short loc_18001F51B
0x18001f50a  mov     rax, [rsi+1D80h]
0x18001f511  mov     [rdx], rax
0x18001f514  mov     [rsi+1D80h], rdx
0x18001f51b  mov     rax, [rsi+1DA0h]
0x18001f522  mov     [rcx], rax
0x18001f525  mov     [rsi+1DA0h], rcx
0x18001f52c  test    r15, r15
0x18001f52f  jnz     short loc_18001F4FB
0x18001f531  mov     r9, [rbp+var_38]
0x18001f535  mov     rdx, [rbp+var_28]
0x18001f539  mov     [rbp+var_30], r15
0x18001f53d  test    r13d, r13d
0x18001f540  jz      loc_18001F778
0x18001f546  mov     r11d, [rbp+arg_10]
0x18001f54a  mov     ecx, [r14+0B8h]
0x18001f551  mov     r8, rdx
0x18001f554  shr     r8, cl
0x18001f557  mov     rax, 1D3FCA840A073E1Fh
0x18001f561  mul     r8
0x18001f564  mov     rax, r8
0x18001f567  sub     rax, rdx
0x18001f56a  shr     rax, 1
0x18001f56d  add     rax, rdx
0x18001f570  shr     rax, 9
0x18001f574  imul    rax, 397h
0x18001f57b  sub     r8, rax
0x18001f57e  mov     eax, r8d
0x18001f581  mov     r8, [rsi+rax*8+0B0h]
0x18001f589  test    r8, r8
0x18001f58c  jz      loc_18001F6F2
0x18001f592  mov     r15, [r8]
0x18001f595  mov     r8, [r8+8]
0x18001f599  mov     rcx, [r15]
0x18001f59c  cmp     rcx, r10
0x18001f59f  ja      short loc_18001F589
0x18001f5a1  mov     edx, [r15+8]
0x18001f5a5  add     rdx, rcx
0x18001f5a8  cmp     rdx, r9
0x18001f5ab  jb      short loc_18001F589
0x18001f5ad  cmp     rdi, rcx
0x18001f5b0  jb      short loc_18001F5C0
0x18001f5b2  cmp     rdx, rbx
0x18001f5b5  jnb     loc_18001F734
0x18001f5bb  cmp     rdi, rcx
0x18001f5be  ja      short loc_18001F5CF
0x18001f5c0  cmp     rbx, rdx
0x18001f5c3  jb      short loc_18001F5CF
0x18001f5c5  cmp     r11d, [r15+10h]
0x18001f5c9  jnz     loc_18001F70F
0x18001f5cf  cmp     rcx, rdi
0x18001f5d2  mov     r11, rdi
0x18001f5d5  mov     rax, rbx
0x18001f5d8  cmovbe  r11, rcx
0x18001f5dc  cmp     rdx, rbx
0x18001f5df  mov     [rbp+var_10], r11
0x18001f5e3  cmovnb  rax, rdx
0x18001f5e7  cmp     rcx, rdi
0x18001f5ea  mov     [rbp+var_18], rax
0x18001f5ee  setbe   al
0x18001f5f1  cmp     rdx, rbx
0x18001f5f4  sbb     cl, cl
0x18001f5f6  and     cl, al
0x18001f5f8  mov     eax, [r15+14h]
0x18001f5fc  mov     [rbp+var_40], eax
0x18001f5ff  cmp     eax, [rbp+arg_18]
0x18001f602  jnz     loc_18001F694
0x18001f608  mov     rbx, [rbp+var_18]
0x18001f60c  mov     rdi, r11
0x18001f60f  mov     r11d, 1
0x18001f615  mov     [rbp+arg_10], r11d
0x18001f619  test    cl, cl
0x18001f61b  jz      short loc_18001F62F
0x18001f61d  test    r12, r12
0x18001f620  jz      short loc_18001F627
0x18001f622  cmp     r12, r15
0x18001f625  jnz     short loc_18001F634
0x18001f627  mov     r12, r15
0x18001f62a  jmp     loc_18001F589
0x18001f62f  test    r12, r12
0x18001f632  jz      short loc_18001F659
0x18001f634  cmp     r12, r11
0x18001f637  jz      short loc_18001F659
0x18001f639  mov     r9b, r11b; unsigned __int8
0x18001f63c  mov     r8, r12; struct _VA_RANGE *
0x18001f63f  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x18001f642  mov     rcx, r14; struct _MINIDUMP_STATE *
0x18001f645  call    ?GenFreeMemoryBlock@@YAPEAU_VA_RANGE_REF@@PEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_VA_RANGE@@E@Z; GenFreeMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_VA_RANGE *,uchar)
0x18001f64a  mov     r9, rax; struct _VA_RANGE_REF *
0x18001f64d  lea     r8, [rbp+var_30]; struct _VA_RANGE_REF **
0x18001f651  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x18001f654  call    ?GenMergeFilterList@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAPEAU_VA_RANGE_REF@@PEAU3@@Z; GenMergeFilterList(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_VA_RANGE_REF * *,_VA_RANGE_REF *)
0x18001f659  mov     r12d, 1
0x18001f65f  mov     r8, r15; struct _VA_RANGE *
0x18001f662  mov     r9b, r12b; unsigned __int8
0x18001f665  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x18001f668  mov     rcx, r14; struct _MINIDUMP_STATE *
0x18001f66b  call    ?GenFreeMemoryBlock@@YAPEAU_VA_RANGE_REF@@PEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_VA_RANGE@@E@Z; GenFreeMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_VA_RANGE *,uchar)
0x18001f670  mov     r9, rax; struct _VA_RANGE_REF *
0x18001f673  lea     r8, [rbp+var_30]; struct _VA_RANGE_REF **
0x18001f677  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x18001f67a  call    ?GenMergeFilterList@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAPEAU_VA_RANGE_REF@@PEAU3@@Z; GenMergeFilterList(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_VA_RANGE_REF * *,_VA_RANGE_REF *)
0x18001f67f  mov     r11d, [rbp+arg_10]
0x18001f683  mov     r10, [rbp+var_20]
0x18001f687  mov     r9, [rbp+var_38]
0x18001f68b  mov     rdx, [rbp+var_28]
0x18001f68f  jmp     loc_18001F54A
0x18001f694  mov     ebx, [r15+10h]
0x18001f698  mov     r9b, 1; unsigned __int8
0x18001f69b  mov     r8, r15; struct _VA_RANGE *
0x18001f69e  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x18001f6a1  mov     rcx, r14; struct _MINIDUMP_STATE *
0x18001f6a4  call    ?GenFreeMemoryBlock@@YAPEAU_VA_RANGE_REF@@PEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_VA_RANGE@@E@Z; GenFreeMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_VA_RANGE *,uchar)
0x18001f6a9  mov     r9, rax; struct _VA_RANGE_REF *
0x18001f6ac  lea     r8, [rbp+var_30]; struct _VA_RANGE_REF **
0x18001f6b0  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x18001f6b3  call    ?GenMergeFilterList@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAPEAU_VA_RANGE_REF@@PEAU3@@Z; GenMergeFilterList(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_VA_RANGE_REF * *,_VA_RANGE_REF *)
0x18001f6b8  mov     eax, [rbp+arg_18]
0x18001f6bb  lea     r8, [rbp+var_30]
0x18001f6bf  mov     ecx, [rbp+arg_10]
0x18001f6c2  mov     r9, rdi
0x18001f6c5  mov     [rsp+80h+var_50], eax
0x18001f6c9  mov     rdx, rsi
0x18001f6cc  mov     eax, [rbp+arg_28]
0x18001f6cf  mov     dword ptr [rsp+80h+var_58], ecx
0x18001f6d3  mov     dword ptr [rsp+80h+var_60], eax
0x18001f6d7  call    ?GenAddExtendFilterList@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAPEAU_VA_RANGE_REF@@_KKW4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@@Z; GenAddExtendFilterList(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_VA_RANGE_REF * *,unsigned __int64,ulong,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE)
0x18001f6dc  mov     eax, [rbp+var_40]
0x18001f6df  mov     r11d, ebx
0x18001f6e2  mov     rdi, [rbp+var_10]
0x18001f6e6  mov     [rbp+arg_10], ebx
0x18001f6e9  mov     rbx, [rbp+var_18]
0x18001f6ed  mov     [rbp+arg_18], eax
0x18001f6f0  jmp     short loc_18001F683
0x18001f6f2  mov     rdx, [rbp+var_28]
0x18001f6f6  dec     r13d
0x18001f6f9  mov     eax, [r14+0BCh]
0x18001f700  inc     rdx
0x18001f703  add     rdx, rax
0x18001f706  mov     [rbp+var_28], rdx
0x18001f70a  jmp     loc_18001F53D
0x18001f70f  xor     r9d, r9d; unsigned __int8
0x18001f712  mov     r8, r15; struct _VA_RANGE *
0x18001f715  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x18001f718  mov     rcx, r14; struct _MINIDUMP_STATE *
0x18001f71b  call    ?GenFreeMemoryBlock@@YAPEAU_VA_RANGE_REF@@PEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_VA_RANGE@@E@Z; GenFreeMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_VA_RANGE *,uchar)
0x18001f720  mov     r10, [rbp+var_20]
0x18001f724  mov     ecx, [rbp+var_3C]
0x18001f727  mov     r9, [rbp+var_38]
0x18001f72b  mov     r15, [rbp+var_30]
0x18001f72f  jmp     loc_18001F4CC
0x18001f734  mov     ecx, [rbp+arg_18]
0x18001f737  xor     eax, eax
0x18001f739  cmp     ecx, [r15+14h]
0x18001f73d  jz      short loc_18001F75E
0x18001f73f  mov     eax, [rbp+arg_28]
0x18001f742  lea     r8, [r15+18h]
0x18001f746  mov     [rsp+80h+var_50], ecx
0x18001f74a  mov     r9, rdi
0x18001f74d  mov     dword ptr [rsp+80h+var_58], r11d
0x18001f752  mov     rdx, rsi
0x18001f755  mov     dword ptr [rsp+80h+var_60], eax
0x18001f759  call    ?GenAddExtendFilterList@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAPEAU_VA_RANGE_REF@@_KKW4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@@Z; GenAddExtendFilterList(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_VA_RANGE_REF * *,unsigned __int64,ulong,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE)
0x18001f75e  mov     ecx, [rbp+arg_10]
0x18001f761  cmp     ecx, [r15+10h]
0x18001f765  jz      loc_18001F812
0x18001f76b  mov     dword ptr [r15+10h], 1
0x18001f773  jmp     loc_18001F812
0x18001f778  mov     ecx, [rbp+arg_10]
0x18001f77b  xor     eax, eax
0x18001f77d  cmp     r12, 1
0x18001f781  mov     r9, rdi
0x18001f784  mov     rdx, rsi
  ... truncated ...
```
