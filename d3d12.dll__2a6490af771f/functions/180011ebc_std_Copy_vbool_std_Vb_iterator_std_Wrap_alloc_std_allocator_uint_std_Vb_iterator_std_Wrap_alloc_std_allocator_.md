# std::_Copy_vbool<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>>(std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>)

- ea: `0x180011ebc`
- end: `0x18001227f`
- name: `??$_Copy_vbool@V?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@V12@@std@@YA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@0@V10@00@Z`
- size: `963`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800124b0`

## callees

- `0x18000c341`
- `0x180011ebc`
- `0x18001256c`

## pseudocode

```c
__int64 __fastcall std::_Copy_vbool<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int *v4; // rdi
  unsigned int *v6; // r13
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // rdx
  int *v10; // r10
  unsigned __int64 v11; // r11
  unsigned __int64 v12; // rdx
  int v13; // r8d
  unsigned int v14; // r14d
  unsigned int v15; // r15d
  int v16; // ebx
  int v17; // r8d
  char v18; // cl
  unsigned int v19; // eax
  unsigned int v20; // r9d
  unsigned int v21; // eax
  int v22; // eax
  char v23; // cl
  unsigned int v24; // eax
  unsigned int v25; // r8d
  unsigned int v26; // eax
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // r14
  _BYTE *v32; // r9
  _BYTE *v33; // r15
  _BYTE *v34; // rdi
  char v35; // dl
  __int64 v36; // rsi
  unsigned int v37; // r8d
  unsigned int *v38; // rdi
  int v39; // r14d
  unsigned __int64 v40; // r11
  char v41; // bp
  int v42; // r8d
  unsigned int v43; // r9d
  unsigned int v44; // eax
  int v45; // eax
  int v46; // edx
  unsigned int v47; // edx
  unsigned __int64 v48; // rdx
  unsigned __int64 v49; // rbp
  int v50; // ebx
  unsigned int *v52; // [rsp+68h] [rbp+10h]

  v4 = *(unsigned int **)a3;
  v6 = *(unsigned int **)a2;
  v52 = *(unsigned int **)a3;
  if ( *(_QWORD *)a2 == *(_QWORD *)a3 && *(_QWORD *)(a2 + 8) == *(_QWORD *)(a3 + 8) )
  {
    *(_OWORD *)a1 = *(_OWORD *)a4;
    return a1;
  }
  v8 = *(_QWORD *)(a3 + 8);
  v9 = v8 + 32 * (v4 - v6) - *(_QWORD *)(a2 + 8);
  *(_OWORD *)a1 = *(_OWORD *)a4;
  std::_Vb_const_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>::operator+=(a1, v9);
  v12 = *(_QWORD *)(a4 + 8);
  v13 = -1 << v11;
  if ( v12 )
    v14 = 0xFFFFFFFF >> (32 - v12);
  else
    v14 = 0;
  if ( v8 )
    v15 = 0xFFFFFFFF >> (32 - v8);
  else
    v15 = 0;
  v16 = -1 << *(_QWORD *)(a1 + 8);
  if ( v6 == v4 )
  {
    v17 = v15 & v13;
    if ( v12 >= v11 )
      v18 = v12 - v11;
    else
      v18 = v11 - v12;
    v19 = *v6 & v17;
    v20 = v19 >> v18;
    v21 = v19 << v18;
    if ( v12 >= v11 )
      v20 = v21;
    if ( v10 != (int *)((-(__int64)(*(_QWORD *)(a1 + 8) == 0) & 0xFFFFFFFFFFFFFFFCuLL) + *(_QWORD *)a1) )
    {
      *v10 = v20 | v14 & *v10;
      v10[1] = v16 & v10[1] | ((*v6 & v17) >> (v8 - *(_BYTE *)(a1 + 8)));
      return a1;
    }
    v22 = v20 | *v10 & (v14 | (*(_QWORD *)(a1 + 8) != 0 ? v16 : 0));
LABEL_51:
    *v10 = v22;
    return a1;
  }
  if ( v10 == (int *)((-(__int64)(*(_QWORD *)(a1 + 8) == 0) & 0xFFFFFFFFFFFFFFFCuLL) + *(_QWORD *)a1) )
  {
    if ( v12 >= v11 )
      v23 = v12 - v11;
    else
      v23 = v11 - v12;
    v24 = *v6 & v13;
    v25 = v24 >> v23;
    v26 = v24 << v23;
    v27 = *(_QWORD *)(a1 + 8);
    if ( v12 >= v11 )
      v25 = v26;
    if ( v8 )
      v28 = *v10 & (v14 | (v27 != 0 ? v16 : 0)) | ((v15 & *v4) << (v27 - v8));
    else
      v28 = *v10 & (v14 | (v27 != 0 ? v16 : 0));
LABEL_50:
    v22 = v25 | v28;
    goto LABEL_51;
  }
  v29 = v11 & 7;
  v30 = v12 & 7;
  if ( v29 == v30 )
  {
    v31 = v8 & 7;
    v32 = (char *)v6 + ((v11 - v29) >> 3);
    v33 = (char *)v4 + ((v8 - v31) >> 3);
    v34 = (char *)v10 + ((v12 - v30) >> 3);
    if ( (v11 & 7) != 0 )
    {
      v35 = *v32++ & (-1 << v29) | *v34 & (255 >> (8 - v29));
      *v34++ = v35;
    }
    v36 = v33 - v32;
    memmove_0(v34, v32, v33 - v32);
    if ( v31 )
      v34[v36] = v34[v36] & (-1 << v31) | *v33 & (255 >> (8 - v31));
    return a1;
  }
  v37 = *v6 & v13;
  v38 = v6 + 1;
  v39 = *v10 & v14;
  if ( v12 >= v11 )
  {
    v48 = v12 - v11;
    v49 = 32 - v48;
    *v10 = v39 | (v37 << v48);
    v25 = *v6 >> (32 - v48);
    ++v10;
    while ( v38 != v52 )
    {
      *v10++ = v25 | (*v38 << v48);
      v25 = *v38++ >> v49;
    }
    if ( v8 < v49 )
    {
      v50 = *v10 & v16;
      if ( !v8 )
      {
        *v10 = v25 | v50;
        return a1;
      }
      v28 = v50 | ((v15 & *v38) << v48);
      goto LABEL_50;
    }
    *v10 = v25 | (*v38 << v48);
    if ( v8 == v49 )
      return a1;
    v47 = ~v16 & (*v38 >> v49);
LABEL_47:
    v10[1] = v16 & v10[1] | v47;
    return a1;
  }
  v40 = v11 - v12;
  v41 = 32 - v40;
  v42 = v39 | (v37 >> v40);
  v43 = 0xFFFFFFFF >> v40;
  for ( *v10 = v42; v38 != v52; *v10 = v42 )
  {
    *v10++ = (*v38 << v41) | v42 & v43;
    v44 = *v38++;
    v42 = (v44 >> v40) | ~v43 & *v10;
  }
  if ( v8 )
  {
    v45 = *v10;
    v46 = (v15 & *v38) << v41;
    if ( v8 < v40 )
    {
      *v10 = v46 | v45 & (v16 | v43);
      return a1;
    }
    *v10 = v46 | v43 & v45;
    if ( v8 != v40 )
    {
      v47 = (v15 & *v38) >> v40;
      goto LABEL_47;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180011ebc  mov     [rsp+arg_0], rbx
0x180011ec1  push    rbp
0x180011ec2  push    rsi
0x180011ec3  push    rdi
0x180011ec4  push    r12
0x180011ec6  push    r13
0x180011ec8  push    r14
0x180011eca  push    r15
0x180011ecc  sub     rsp, 20h
0x180011ed0  mov     rdi, [r8]
0x180011ed3  mov     rbx, r9
0x180011ed6  mov     r13, [rdx]
0x180011ed9  mov     r12, rcx
0x180011edc  mov     [rsp+58h+arg_8], rdi
0x180011ee1  cmp     r13, rdi
0x180011ee4  jnz     short loc_180011EFD
0x180011ee6  mov     rax, [r8+8]
0x180011eea  cmp     [rdx+8], rax
0x180011eee  jnz     short loc_180011EFD
0x180011ef0  movaps  xmm0, xmmword ptr [r9]
0x180011ef4  movdqu  xmmword ptr [rcx], xmm0
0x180011ef8  jmp     loc_180012267
0x180011efd  mov     r11, [rdx+8]
0x180011f01  mov     rdx, rdi
0x180011f04  mov     rsi, [r8+8]
0x180011f08  sub     rdx, r13
0x180011f0b  movaps  xmm0, xmmword ptr [r9]
0x180011f0f  mov     r10, [r9]
0x180011f12  sar     rdx, 2
0x180011f16  shl     rdx, 5
0x180011f1a  sub     rdx, r11
0x180011f1d  add     rdx, rsi
0x180011f20  movdqu  xmmword ptr [rcx], xmm0
0x180011f24  call    ??Y?$_Vb_const_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@QEAAAEAV01@_J@Z; std::_Vb_const_iterator<std::_Wrap_alloc<std::allocator<uint>>>::operator+=(__int64)
0x180011f29  mov     rdx, [rbx+8]
0x180011f2d  or      r9d, 0FFFFFFFFh
0x180011f31  mov     r8d, r9d
0x180011f34  mov     rcx, r11
0x180011f37  shl     r8d, cl
0x180011f3a  mov     ebp, 20h ; ' '
0x180011f3f  test    rdx, rdx
0x180011f42  jnz     short loc_180011F49
0x180011f44  xor     r14d, r14d
0x180011f47  jmp     short loc_180011F53
0x180011f49  mov     ecx, ebp
0x180011f4b  mov     r14d, r9d
0x180011f4e  sub     cl, dl
0x180011f50  shr     r14d, cl
0x180011f53  test    rsi, rsi
0x180011f56  jnz     short loc_180011F5D
0x180011f58  xor     r15d, r15d
0x180011f5b  jmp     short loc_180011F68
0x180011f5d  mov     ecx, ebp
0x180011f5f  mov     r15d, r9d
0x180011f62  sub     cl, sil
0x180011f65  shr     r15d, cl
0x180011f68  mov     rax, [r12+8]
0x180011f6d  mov     ebx, r9d
0x180011f70  mov     rcx, rax
0x180011f73  shl     ebx, cl
0x180011f75  neg     rax
0x180011f78  mov     rax, [r12]
0x180011f7c  sbb     rcx, rcx
0x180011f7f  not     rcx
0x180011f82  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180011f86  add     rax, rcx
0x180011f89  mov     [rsp+58h+arg_10], rax
0x180011f8e  cmp     r13, rdi
0x180011f91  jnz     short loc_18001200D
0x180011f93  and     r8d, r15d
0x180011f96  cmp     rdx, r11
0x180011f99  jnb     short loc_180011FA3
0x180011f9b  mov     rcx, r11
0x180011f9e  sub     rcx, rdx
0x180011fa1  jmp     short loc_180011FA9
0x180011fa3  mov     rcx, rdx
0x180011fa6  sub     rcx, r11
0x180011fa9  mov     r9d, r8d
0x180011fac  and     r9d, [r13+0]
0x180011fb0  mov     eax, r9d
0x180011fb3  shr     r9d, cl
0x180011fb6  shl     eax, cl
0x180011fb8  cmp     rdx, r11
0x180011fbb  cmovnb  r9d, eax
0x180011fbf  cmp     r10, [rsp+58h+arg_10]
0x180011fc4  jnz     short loc_180011FE0
0x180011fc6  mov     rcx, [r12+8]
0x180011fcb  neg     rcx
0x180011fce  sbb     eax, eax
0x180011fd0  and     eax, ebx
0x180011fd2  or      eax, r14d
0x180011fd5  and     eax, [r10]
0x180011fd8  or      eax, r9d
0x180011fdb  jmp     loc_18001225C
0x180011fe0  mov     eax, [r10]
0x180011fe3  mov     cl, sil
0x180011fe6  and     eax, r14d
0x180011fe9  or      eax, r9d
0x180011fec  mov     [r10], eax
0x180011fef  sub     cl, [r12+8]
0x180011ff4  and     r8d, [r13+0]
0x180011ff8  mov     eax, [r10+4]
0x180011ffc  shr     r8d, cl
0x180011fff  and     eax, ebx
0x180012001  or      r8d, eax
0x180012004  mov     [r10+4], r8d
0x180012008  jmp     loc_180012267
0x18001200d  cmp     r10, rax
0x180012010  jnz     short loc_18001206A
0x180012012  cmp     rdx, r11
0x180012015  jnb     short loc_18001201F
0x180012017  mov     rcx, r11
0x18001201a  sub     rcx, rdx
0x18001201d  jmp     short loc_180012025
0x18001201f  mov     rcx, rdx
0x180012022  sub     rcx, r11
0x180012025  and     r8d, [r13+0]
0x180012029  mov     eax, r8d
0x18001202c  shr     r8d, cl
0x18001202f  shl     eax, cl
0x180012031  mov     rcx, [r12+8]
0x180012036  cmp     rdx, r11
0x180012039  cmovnb  r8d, eax
0x18001203d  mov     rax, rcx
0x180012040  neg     rax
0x180012043  sbb     edx, edx
0x180012045  and     edx, ebx
0x180012047  or      edx, r14d
0x18001204a  and     edx, [r10]
0x18001204d  test    rsi, rsi
0x180012050  jz      short loc_180012063
0x180012052  mov     eax, [rdi]
0x180012054  sub     cl, sil
0x180012057  and     eax, r15d
0x18001205a  shl     eax, cl
0x18001205c  or      eax, edx
0x18001205e  jmp     loc_180012259
0x180012063  mov     eax, edx
0x180012065  jmp     loc_180012259
0x18001206a  mov     rax, r11
0x18001206d  mov     rcx, rdx
0x180012070  and     eax, 7
0x180012073  and     ecx, 7
0x180012076  cmp     rax, rcx
0x180012079  jnz     loc_180012115
0x18001207f  mov     r14, rsi
0x180012082  sub     r11, rax
0x180012085  and     r14d, 7
0x180012089  shr     r11, 3
0x18001208d  sub     rsi, r14
0x180012090  sub     rdx, rcx
0x180012093  shr     rsi, 3
0x180012097  or      ebp, 0FFFFFFFFh
0x18001209a  shr     rdx, 3
0x18001209e  mov     ebx, 0FFh
0x1800120a3  lea     r9, [r11+r13]
0x1800120a7  mov     r13d, 8
0x1800120ad  lea     r15, [rsi+rdi]
0x1800120b1  lea     rdi, [rdx+r10]
0x1800120b5  test    rax, rax
0x1800120b8  jz      short loc_1800120D8
0x1800120ba  mov     ecx, r13d
0x1800120bd  mov     edx, ebx
0x1800120bf  sub     cl, al
0x1800120c1  sar     edx, cl
0x1800120c3  mov     ecx, eax
0x1800120c5  and     dl, [rdi]
0x1800120c7  mov     eax, ebp
0x1800120c9  shl     al, cl
0x1800120cb  and     al, [r9]
0x1800120ce  or      dl, al
0x1800120d0  inc     r9
0x1800120d3  mov     [rdi], dl
0x1800120d5  inc     rdi
0x1800120d8  mov     rsi, r15
0x1800120db  mov     rdx, r9; Src
0x1800120de  sub     rsi, r9
0x1800120e1  mov     rcx, rdi; void *
0x1800120e4  mov     r8, rsi; Size
0x1800120e7  call    memmove_0
0x1800120ec  test    r14, r14
0x1800120ef  jz      loc_180012267
0x1800120f5  mov     ecx, r13d
0x1800120f8  sub     cl, r14b
0x1800120fb  sar     ebx, cl
0x1800120fd  mov     rcx, r14
0x180012100  and     bl, [r15]
0x180012103  shl     bpl, cl
0x180012106  and     bpl, [rsi+rdi]
0x18001210a  or      bl, bpl
0x18001210d  mov     [rsi+rdi], bl
0x180012110  jmp     loc_180012267
0x180012115  and     r8d, [r13+0]
0x180012119  lea     rdi, [r13+4]
0x18001211d  and     r14d, [r10]
0x180012120  cmp     rdx, r11
0x180012123  jnb     loc_1800121C9
0x180012129  sub     r11, rdx
0x18001212c  mov     rcx, r11
0x18001212f  sub     rbp, r11
0x180012132  shr     r8d, cl
0x180012135  or      r8d, r14d
0x180012138  shr     r9d, cl
0x18001213b  mov     r14, [rsp+58h+arg_8]
0x180012140  mov     [r10], r8d
0x180012143  cmp     rdi, r14
0x180012146  jz      short loc_180012180
0x180012148  mov     r13d, r9d
0x18001214b  not     r13d
0x18001214e  mov     eax, [rdi]
0x180012150  mov     rcx, rbp
0x180012153  shl     eax, cl
0x180012155  mov     edx, r9d
0x180012158  and     edx, r8d
0x18001215b  mov     rcx, r11
0x18001215e  or      edx, eax
0x180012160  mov     [r10], edx
0x180012163  add     r10, 4
0x180012167  mov     eax, [rdi]
0x180012169  add     rdi, 4
0x18001216d  shr     eax, cl
0x18001216f  mov     r8d, [r10]
0x180012172  and     r8d, r13d
0x180012175  or      r8d, eax
0x180012178  mov     [r10], r8d
0x18001217b  cmp     rdi, r14
0x18001217e  jnz     short loc_18001214E
0x180012180  test    rsi, rsi
0x180012183  jz      loc_180012267
0x180012189  mov     edx, [rdi]
0x18001218b  mov     rcx, rbp
0x18001218e  mov     eax, [r10]
0x180012191  and     edx, r15d
0x180012194  shl     edx, cl
0x180012196  cmp     rsi, r11
0x180012199  jb      short loc_1800121B8
0x18001219b  and     eax, r9d
0x18001219e  or      eax, edx
0x1800121a0  mov     [r10], eax
0x1800121a3  cmp     rsi, r11
0x1800121a6  jz      loc_180012267
0x1800121ac  mov     edx, [rdi]
0x1800121ae  mov     rcx, r11
0x1800121b1  and     edx, r15d
0x1800121b4  shr     edx, cl
0x1800121b6  jmp     short loc_180012237
0x1800121b8  or      r9d, ebx
0x1800121bb  and     r9d, eax
0x1800121be  or      r9d, edx
0x1800121c1  mov     [r10], r9d
0x1800121c4  jmp     loc_180012267
0x1800121c9  sub     rdx, r11
0x1800121cc  mov     rcx, rdx
0x1800121cf  sub     rbp, rdx
0x1800121d2  shl     r8d, cl
0x1800121d5  mov     rcx, rbp
0x1800121d8  or      r8d, r14d
0x1800121db  mov     r14, [rsp+58h+arg_8]
0x1800121e0  mov     [r10], r8d
0x1800121e3  mov     r8d, [r13+0]
0x1800121e7  shr     r8d, cl
0x1800121ea  add     r10, 4
0x1800121ee  jmp     short loc_18001220E
0x1800121f0  mov     eax, [rdi]
0x1800121f2  mov     rcx, rdx
0x1800121f5  shl     eax, cl
0x1800121f7  mov     rcx, rbp
0x1800121fa  or      eax, r8d
0x1800121fd  mov     [r10], eax
0x180012200  add     r10, 4
0x180012204  mov     r8d, [rdi]
0x180012207  shr     r8d, cl
0x18001220a  add     rdi, 4
0x18001220e  cmp     rdi, r14
0x180012211  jnz     short loc_1800121F0
0x180012213  cmp     rsi, rbp
0x180012216  jb      short loc_180012245
0x180012218  mov     eax, [rdi]
0x18001221a  mov     rcx, rdx
0x18001221d  shl     eax, cl
0x18001221f  or      eax, r8d
0x180012222  mov     [r10], eax
0x180012225  cmp     rsi, rbp
0x180012228  jz      short loc_180012267
0x18001222a  mov     edx, [rdi]
0x18001222c  mov     rcx, rbp
0x18001222f  mov     eax, ebx
0x180012231  shr     edx, cl
0x180012233  not     eax
0x180012235  and     edx, eax
0x180012237  mov     eax, [r10+4]
0x18001223b  and     eax, ebx
0x18001223d  or      edx, eax
0x18001223f  mov     [r10+4], edx
0x180012243  jmp     short loc_180012267
0x180012245  and     ebx, [r10]
0x180012248  test    rsi, rsi
0x18001224b  jz      short loc_180012261
0x18001224d  mov     eax, [rdi]
0x18001224f  mov     rcx, rdx
  ... truncated ...
```
