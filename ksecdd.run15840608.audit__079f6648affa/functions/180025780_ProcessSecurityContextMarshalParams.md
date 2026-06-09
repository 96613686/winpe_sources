# ProcessSecurityContextMarshalParams

- ea: `0x180025780`
- end: `0x180025c10`
- name: `ProcessSecurityContextMarshalParams`
- size: `1168`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000f47c`
- `0x180010a00`
- `0x180010d00`
- `0x180025780`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180025821`
- `ntoskrnl!ExAllocatePool2` at `0x180025821`

## pseudocode

```c
__int64 __fastcall ProcessSecurityContextMarshalParams(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  unsigned __int16 *v3; // rax
  unsigned int v4; // esi
  __int64 v8; // r10
  unsigned int v9; // r11d
  unsigned int v10; // eax
  __int64 v11; // rax
  int v12; // ecx
  char *Pool2; // rax
  char *v14; // rbx
  void *v15; // rdi
  _QWORD *v16; // rbp
  unsigned __int16 *v17; // r15
  __int64 v18; // r15
  _OWORD *v19; // rax
  __int64 v20; // rax
  unsigned int v21; // ecx
  __int64 v22; // r13
  __int64 v23; // rax
  unsigned int i; // r12d
  const void *v25; // rdx
  unsigned int v26; // ecx
  __int64 v27; // rdi
  char *v28; // rax
  __int64 v29; // r10
  int v30; // ecx
  __int64 v31; // rcx
  unsigned int v32; // r11d
  __int64 v33; // r8
  __int64 v34; // r9
  unsigned int v36; // ebx
  __int64 v37; // rbp
  __m128i v38; // xmm5
  __m128i v39; // xmm4
  __int64 v40; // r8
  __m128i v41; // xmm3
  __int64 v42; // rdx
  __m128i v43; // xmm2
  __int64 v44; // rcx
  __m128i v45; // xmm1
  __m128i v46; // xmm4
  __m128i v47; // xmm4
  __int64 v48; // rax
  int v49; // eax
  _QWORD *v50; // [rsp+20h] [rbp-58h] BYREF
  void *v51; // [rsp+28h] [rbp-50h]
  unsigned int v52; // [rsp+30h] [rbp-48h]
  __int64 v53; // [rsp+90h] [rbp+18h]

  v3 = *(unsigned __int16 **)(a1 + 72);
  v4 = 0;
  v52 = 0;
  if ( v3 )
  {
    v4 = *v3;
    v52 = v4;
  }
  v8 = *(_QWORD *)(a1 + 80);
  if ( v8 )
  {
    v9 = *(_DWORD *)(v8 + 4);
    v4 += 16;
    v52 = v4;
    v10 = v4;
    if ( v9 )
    {
      v4 += 16 * v9;
      v52 = v10 + 16 * v9;
      v36 = 0;
      if ( v9 < 8 )
        goto LABEL_55;
      v37 = *(_QWORD *)(v8 + 8);
      v38 = 0;
      v39 = 0;
      do
      {
        v40 = 2LL * (v36 + 6);
        v41 = _mm_unpacklo_epi32(
                _mm_cvtsi32_si128(*(_DWORD *)(v37 + 16LL * v36)),
                _mm_cvtsi32_si128(*(_DWORD *)(v37 + 16LL * (v36 + 1))));
        v42 = 2LL * (v36 + 5);
        v43 = _mm_unpacklo_epi32(
                _mm_cvtsi32_si128(*(_DWORD *)(v37 + 16LL * (v36 + 2))),
                _mm_cvtsi32_si128(*(_DWORD *)(v37 + 16LL * (v36 + 3))));
        v44 = 2LL * (v36 + 4);
        v45 = _mm_cvtsi32_si128(*(_DWORD *)(v37 + 16LL * (v36 + 7)));
        v36 += 8;
        v38 = _mm_add_epi32(v38, _mm_unpacklo_epi64(v41, v43));
        v39 = _mm_add_epi32(
                v39,
                _mm_unpacklo_epi64(
                  _mm_unpacklo_epi32(
                    _mm_cvtsi32_si128(*(_DWORD *)(v37 + 8 * v44)),
                    _mm_cvtsi32_si128(*(_DWORD *)(v37 + 8 * v42))),
                  _mm_unpacklo_epi32(_mm_cvtsi32_si128(*(_DWORD *)(v37 + 8 * v40)), v45)));
      }
      while ( v36 < (v9 & 0xFFFFFFF8) );
      v46 = _mm_add_epi32(v39, v38);
      v47 = _mm_add_epi32(v46, _mm_srli_si128(v46, 8));
      v4 += _mm_cvtsi128_si32(_mm_add_epi32(v47, _mm_srli_si128(v47, 4)));
      v52 = v4;
      if ( v36 < v9 )
      {
LABEL_55:
        do
        {
          v48 = v36++;
          v4 += *(_DWORD *)(16 * v48 + *(_QWORD *)(v8 + 8));
        }
        while ( v36 < v9 );
        v52 = v4;
      }
    }
  }
  v11 = *(_QWORD *)(a1 + 104);
  if ( v11 )
  {
    v12 = *(_DWORD *)(v11 + 4);
    v4 += 16;
    v52 = v4;
    if ( v12 )
    {
      v4 += 8 * v12;
      v52 = v4;
    }
  }
  *a3 = 0;
  if ( !v4 )
    return 3221225626LL;
  Pool2 = (char *)ExAllocatePool2(256, v4 + 120, 1131180883);
  v51 = Pool2;
  v14 = Pool2;
  v15 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  memset(Pool2, 0, v4 + 120);
  *a3 = v4 + 120;
  *a2 = v14;
  v16 = v14 + 120;
  v17 = *(unsigned __int16 **)(a1 + 72);
  v50 = v14 + 120;
  *((_OWORD *)v14 + 3) = 0;
  if ( v17 )
  {
    v49 = AsyncSspiMarshaler<KernelAllocator>::CopyBuffer<unsigned char>(&v50, v14 + 56, *((_QWORD *)v17 + 1), *v17);
    v4 = v52;
    v16 = v50;
    v15 = v51;
    if ( v49 >= 0 )
    {
      *((_WORD *)v14 + 24) = *v17;
      *((_WORD *)v14 + 25) = *v17;
    }
  }
  if ( a1 != -40 )
  {
    *((_QWORD *)v14 + 8) = *(_QWORD *)(a1 + 40);
    *((_QWORD *)v14 + 9) = *(_QWORD *)(a1 + 48);
  }
  if ( a1 != -56 )
  {
    *((_QWORD *)v14 + 10) = *(_QWORD *)(a1 + 56);
    *((_QWORD *)v14 + 11) = *(_QWORD *)(a1 + 64);
  }
  *((_DWORD *)v14 + 24) = *(_DWORD *)(a1 + 88);
  *((_DWORD *)v14 + 25) = *(_DWORD *)(a1 + 92);
  v18 = *(_QWORD *)(a1 + 80);
  *((_QWORD *)v14 + 13) = 0;
  if ( v15 )
  {
    if ( v18 )
    {
      if ( v4 >= 0x10 )
      {
        v19 = v16;
        *((_QWORD *)v14 + 13) = v16;
        v16 += 2;
        v4 -= 16;
        if ( v19 )
        {
          *v19 = *(_OWORD *)v18;
          v20 = *((_QWORD *)v14 + 13);
          v21 = 16 * *(_DWORD *)(v18 + 4);
          *(_QWORD *)(v20 + 8) = 0;
          if ( v4 >= v21 )
          {
            *(_QWORD *)(v20 + 8) = v16;
            v16 = (_QWORD *)((char *)v16 + v21);
            v4 -= v21;
          }
          v22 = *(_QWORD *)(*((_QWORD *)v14 + 13) + 8LL);
          if ( v22 )
          {
            v23 = *(_QWORD *)(v18 + 8);
            for ( i = 0; ; ++i )
            {
              v53 = v23;
              if ( i >= *(_DWORD *)(v18 + 4) )
              {
                v15 = v51;
                *(_QWORD *)(*((_QWORD *)v14 + 13) + 8LL) -= v51;
                *((_QWORD *)v14 + 13) -= v15;
                goto LABEL_29;
              }
              *(_OWORD *)v22 = *(_OWORD *)v23;
              v25 = *(const void **)(v23 + 8);
              v26 = *(_DWORD *)v23;
              *(_QWORD *)(v22 + 8) = 0;
              if ( v25 )
              {
                if ( v4 < v26 )
                {
                  v15 = v51;
                  *((_QWORD *)v14 + 13) = 0;
                  goto LABEL_29;
                }
                v27 = v26;
                memmove(v16, v25, v26);
                v4 -= v27;
                v28 = (char *)((char *)v16 - (_BYTE *)v51);
                v16 = (_QWORD *)((char *)v16 + v27);
                *(_QWORD *)(v22 + 8) = v28;
                v23 = v53;
              }
              v22 += 16;
              v23 += 16;
            }
          }
          *((_QWORD *)v14 + 13) = 0;
        }
      }
    }
  }
LABEL_29:
  v29 = *(_QWORD *)(a1 + 104);
  *((_QWORD *)v14 + 14) = 0;
  if ( v15 )
  {
    if ( v29 )
    {
      if ( v4 >= 0x10 )
      {
        *((_QWORD *)v14 + 14) = v16;
        if ( v16 )
        {
          v30 = *(_DWORD *)(v29 + 4);
          v16[1] = 0;
          if ( v4 - 16 >= 8 * v30 )
            v16[1] = v16 + 2;
          v31 = *((_QWORD *)v14 + 14);
          if ( *(_QWORD *)(v31 + 8) )
          {
            v32 = 0;
            *(_DWORD *)v31 = *(_DWORD *)v29;
            for ( *(_DWORD *)(*((_QWORD *)v14 + 14) + 4LL) = *(_DWORD *)(v29 + 4);
                  v32 < *(_DWORD *)(v29 + 4);
                  *(_DWORD *)(v33 + *(_QWORD *)(*((_QWORD *)v14 + 14) + 8LL)) = *(_DWORD *)(*(_QWORD *)(v29 + 8)
                                                                                          + 8 * v34) )
            {
              v33 = 8LL * v32;
              v34 = 2LL * v32++;
              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v14 + 14) + 8LL) + v33 + 4) = *(_DWORD *)(*(_QWORD *)(v29 + 8)
                                                                                          + 8 * v34
                                                                                          + 4);
            }
            *(_QWORD *)(*((_QWORD *)v14 + 14) + 8LL) -= v15;
            *((_QWORD *)v14 + 14) -= v15;
          }
          else
          {
            *((_QWORD *)v14 + 14) = 0;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180025780  push    rsi
0x180025782  push    r13
0x180025784  push    r14
0x180025786  push    r15
0x180025788  sub     rsp, 58h
0x18002578c  mov     rax, [rcx+48h]
0x180025790  xor     esi, esi
0x180025792  mov     [rsp+78h+var_48], esi
0x180025796  mov     r15, r8
0x180025799  mov     r13, rdx
0x18002579c  mov     r14, rcx
0x18002579f  test    rax, rax
0x1800257a2  jz      short loc_1800257AB
0x1800257a4  movzx   esi, word ptr [rax]
0x1800257a7  mov     [rsp+78h+var_48], esi
0x1800257ab  mov     r10, [rcx+50h]
0x1800257af  mov     [rsp+78h+arg_8], rbx
0x1800257b7  mov     [rsp+78h+var_28], rbp
0x1800257bc  mov     [rsp+78h+var_30], rdi
0x1800257c1  test    r10, r10
0x1800257c4  jz      short loc_1800257DC
0x1800257c6  mov     r11d, [r10+4]
0x1800257ca  add     esi, 10h
0x1800257cd  mov     [rsp+78h+var_48], esi
0x1800257d1  mov     eax, esi
0x1800257d3  test    r11d, r11d
0x1800257d6  jnz     loc_180025A96
0x1800257dc  mov     rax, [r14+68h]
0x1800257e0  test    rax, rax
0x1800257e3  jz      short loc_1800257FA
0x1800257e5  mov     ecx, [rax+4]
0x1800257e8  add     esi, 10h
0x1800257eb  mov     [rsp+78h+var_48], esi
0x1800257ef  test    ecx, ecx
0x1800257f1  jz      short loc_1800257FA
0x1800257f3  lea     esi, [rsi+rcx*8]
0x1800257f6  mov     [rsp+78h+var_48], esi
0x1800257fa  mov     [rsp+78h+var_38], r12
0x1800257ff  mov     dword ptr [r15], 0
0x180025806  test    esi, esi
0x180025808  jz      loc_180025C06
0x18002580e  lea     ebp, [rsi+78h]
0x180025811  mov     r8d, 436C7353h
0x180025817  mov     edx, ebp
0x180025819  mov     ecx, 100h
0x18002581e  mov     r12d, ebp
0x180025821  call    cs:__imp_ExAllocatePool2
0x180025828  nop     dword ptr [rax+rax+00h]
0x18002582d  mov     [rsp+78h+var_50], rax
0x180025832  mov     rbx, rax
0x180025835  mov     rdi, rax
0x180025838  test    rax, rax
0x18002583b  jz      loc_180025C06
0x180025841  mov     r8d, r12d; Size
0x180025844  xor     edx, edx; Val
0x180025846  mov     rcx, rax; void *
0x180025849  call    memset
0x18002584e  mov     [r15], ebp
0x180025851  xorps   xmm0, xmm0
0x180025854  mov     [r13+0], rbx
0x180025858  lea     rbp, [rbx+78h]
0x18002585c  mov     r15, [r14+48h]
0x180025860  mov     [rsp+78h+var_58], rbp
0x180025865  movups  xmmword ptr [rbx+30h], xmm0
0x180025869  test    r15, r15
0x18002586c  jnz     loc_180025BA5
0x180025872  lea     rcx, [r14+28h]
0x180025876  test    rcx, rcx
0x180025879  jz      short loc_18002588A
0x18002587b  mov     rax, [rcx]
0x18002587e  mov     [rbx+40h], rax
0x180025882  mov     rax, [rcx+8]
0x180025886  mov     [rbx+48h], rax
0x18002588a  lea     rcx, [r14+38h]
0x18002588e  test    rcx, rcx
0x180025891  jz      short loc_1800258A2
0x180025893  mov     rax, [rcx]
0x180025896  mov     [rbx+50h], rax
0x18002589a  mov     rax, [rcx+8]
0x18002589e  mov     [rbx+58h], rax
0x1800258a2  mov     eax, [r14+58h]
0x1800258a6  xor     r8d, r8d
0x1800258a9  mov     [rbx+60h], eax
0x1800258ac  mov     eax, [r14+5Ch]
0x1800258b0  mov     [rbx+64h], eax
0x1800258b3  mov     r15, [r14+50h]
0x1800258b7  mov     [rbx+68h], r8
0x1800258bb  test    rdi, rdi
0x1800258be  jz      loc_18002599E
0x1800258c4  test    r15, r15
0x1800258c7  jz      loc_18002599E
0x1800258cd  cmp     esi, 10h
0x1800258d0  jb      loc_18002599E
0x1800258d6  mov     rax, rbp
0x1800258d9  mov     [rbx+68h], rbp
0x1800258dd  add     rbp, 10h
0x1800258e1  add     esi, 0FFFFFFF0h
0x1800258e4  test    rax, rax
0x1800258e7  jz      loc_18002599E
0x1800258ed  movups  xmm0, xmmword ptr [r15]
0x1800258f1  movups  xmmword ptr [rax], xmm0
0x1800258f4  mov     ecx, [r15+4]
0x1800258f8  mov     rax, [rbx+68h]
0x1800258fc  shl     ecx, 4
0x1800258ff  mov     [rax+8], r8
0x180025903  cmp     esi, ecx
0x180025905  jb      short loc_180025912
0x180025907  mov     [rax+8], rbp
0x18002590b  mov     eax, ecx
0x18002590d  add     rbp, rax
0x180025910  sub     esi, ecx
0x180025912  mov     rax, [rbx+68h]
0x180025916  mov     r13, [rax+8]
0x18002591a  test    r13, r13
0x18002591d  jz      loc_180025BE6
0x180025923  mov     rax, [r15+8]
0x180025927  mov     r12d, r8d
0x18002592a  mov     [rsp+78h+arg_10], rax
0x180025932  cmp     r12d, [r15+4]
0x180025936  jnb     short loc_18002598D
0x180025938  movups  xmm0, xmmword ptr [rax]
0x18002593b  movups  xmmword ptr [r13+0], xmm0
0x180025940  mov     rdx, [rax+8]; Src
0x180025944  mov     ecx, [rax]
0x180025946  mov     [r13+8], r8
0x18002594a  test    rdx, rdx
0x18002594d  jz      short loc_180025980
0x18002594f  cmp     esi, ecx
0x180025951  jb      loc_180025BEF
0x180025957  mov     edi, ecx
0x180025959  mov     r8d, ecx; Size
0x18002595c  mov     rcx, rbp; void *
0x18002595f  call    memmove
0x180025964  mov     rax, rbp
0x180025967  sub     esi, edi
0x180025969  sub     rax, [rsp+78h+var_50]
0x18002596e  add     rbp, rdi
0x180025971  mov     [r13+8], rax
0x180025975  xor     r8d, r8d
0x180025978  mov     rax, [rsp+78h+arg_10]
0x180025980  add     r13, 10h
0x180025984  add     rax, 10h
0x180025988  inc     r12d
0x18002598b  jmp     short loc_18002592A
0x18002598d  mov     rax, [rbx+68h]
0x180025991  mov     rdi, [rsp+78h+var_50]
0x180025996  sub     [rax+8], rdi
0x18002599a  sub     [rbx+68h], rdi
0x18002599e  mov     r10, [r14+68h]
0x1800259a2  mov     [rbx+70h], r8
0x1800259a6  test    rdi, rdi
0x1800259a9  jz      loc_180025A70
0x1800259af  test    r10, r10
0x1800259b2  jz      loc_180025A70
0x1800259b8  cmp     esi, 10h
0x1800259bb  jb      loc_180025A70
0x1800259c1  mov     [rbx+70h], rbp
0x1800259c5  lea     rdx, [rbp+10h]
0x1800259c9  test    rbp, rbp
0x1800259cc  jz      loc_180025A70
0x1800259d2  mov     ecx, [r10+4]
0x1800259d6  lea     eax, [rsi-10h]
0x1800259d9  mov     [rbp+8], r8
0x1800259dd  lea     ecx, ds:0[rcx*8]
0x1800259e4  cmp     eax, ecx
0x1800259e6  jb      short loc_1800259EC
0x1800259e8  mov     [rbp+8], rdx
0x1800259ec  mov     rcx, [rbx+70h]
0x1800259f0  cmp     qword ptr [rcx+8], 0
0x1800259f5  jz      loc_180025BFD
0x1800259fb  mov     eax, [r10]
0x1800259fe  mov     r11d, r8d
0x180025a01  mov     [rcx], eax
0x180025a03  mov     rcx, [rbx+70h]
0x180025a07  mov     eax, [r10+4]
0x180025a0b  mov     [rcx+4], eax
0x180025a0e  cmp     dword ptr [r10+4], 0
0x180025a13  jbe     short loc_180025A64
0x180025a15  nop     word ptr [rax+rax+00000000h]
0x180025a20  mov     rdx, [r10+8]
0x180025a24  mov     eax, r11d
0x180025a27  lea     r8, ds:0[rax*8]
0x180025a2f  mov     r9d, r11d
0x180025a32  mov     rax, [rbx+70h]
0x180025a36  add     r9, r9
0x180025a39  inc     r11d
0x180025a3c  mov     rcx, [rax+8]
0x180025a40  mov     eax, [rdx+r9*8+4]
0x180025a45  mov     [rcx+r8+4], eax
0x180025a4a  mov     rax, [rbx+70h]
0x180025a4e  mov     rdx, [r10+8]
0x180025a52  mov     rcx, [rax+8]
0x180025a56  mov     eax, [rdx+r9*8]
0x180025a5a  mov     [r8+rcx], eax
0x180025a5e  cmp     r11d, [r10+4]
0x180025a62  jb      short loc_180025A20
0x180025a64  mov     rax, [rbx+70h]
0x180025a68  sub     [rax+8], rdi
0x180025a6c  sub     [rbx+70h], rdi
0x180025a70  xor     eax, eax
0x180025a72  mov     r12, [rsp+78h+var_38]
0x180025a77  mov     rdi, [rsp+78h+var_30]
0x180025a7c  mov     rbp, [rsp+78h+var_28]
0x180025a81  mov     rbx, [rsp+78h+arg_8]
0x180025a89  add     rsp, 58h
0x180025a8d  pop     r15
0x180025a8f  pop     r14
0x180025a91  pop     r13
0x180025a93  pop     rsi
0x180025a94  retn
0x180025a96  mov     esi, r11d
0x180025a99  shl     esi, 4
0x180025a9c  add     esi, eax
0x180025a9e  mov     [rsp+78h+var_48], esi
0x180025aa2  test    r11d, r11d
0x180025aa5  jz      loc_1800257DC
0x180025aab  xor     ebx, ebx
0x180025aad  cmp     r11d, 8
0x180025ab1  jb      loc_180025B88
0x180025ab7  mov     rbp, [r10+8]
0x180025abb  mov     edi, r11d
0x180025abe  and     edi, 0FFFFFFF8h
0x180025ac1  xorps   xmm5, xmm5
0x180025ac4  xorps   xmm4, xmm4
0x180025ac7  lea     r8d, [rbx+3]
0x180025acb  mov     eax, ebx
0x180025acd  add     r8, r8
0x180025ad0  lea     edx, [rbx+2]
0x180025ad3  add     rdx, rdx
0x180025ad6  lea     ecx, [rbx+1]
0x180025ad9  add     rcx, rcx
0x180025adc  lea     r9d, [rbx+7]
0x180025ae0  add     rax, rax
0x180025ae3  add     r9, r9
0x180025ae6  movd    xmm1, dword ptr [rbp+r8*8+0]
0x180025aed  lea     r8d, [rbx+6]
0x180025af1  movd    xmm2, dword ptr [rbp+rdx*8+0]
0x180025af7  add     r8, r8
0x180025afa  movd    xmm0, dword ptr [rbp+rcx*8+0]
0x180025b00  lea     edx, [rbx+5]
0x180025b03  movd    xmm3, dword ptr [rbp+rax*8+0]
0x180025b09  lea     ecx, [rbx+4]
0x180025b0c  punpckldq xmm3, xmm0
0x180025b10  add     rdx, rdx
0x180025b13  punpckldq xmm2, xmm1
0x180025b17  add     rcx, rcx
0x180025b1a  movd    xmm1, dword ptr [rbp+r9*8+0]
0x180025b21  add     ebx, 8
0x180025b24  punpcklqdq xmm3, xmm2
0x180025b28  movd    xmm2, dword ptr [rbp+r8*8+0]
0x180025b2f  paddd   xmm5, xmm3
0x180025b33  movd    xmm0, dword ptr [rbp+rdx*8+0]
0x180025b39  movd    xmm3, dword ptr [rbp+rcx*8+0]
0x180025b3f  punpckldq xmm2, xmm1
0x180025b43  punpckldq xmm3, xmm0
0x180025b47  punpcklqdq xmm3, xmm2
0x180025b4b  paddd   xmm4, xmm3
0x180025b4f  cmp     ebx, edi
0x180025b51  jb      loc_180025AC7
0x180025b57  paddd   xmm4, xmm5
0x180025b5b  movdqa  xmm0, xmm4
0x180025b5f  psrldq  xmm0, 8
0x180025b64  paddd   xmm4, xmm0
0x180025b68  movdqa  xmm0, xmm4
0x180025b6c  psrldq  xmm0, 4
0x180025b71  paddd   xmm4, xmm0
0x180025b75  movd    eax, xmm4
0x180025b79  add     esi, eax
0x180025b7b  mov     [rsp+78h+var_48], esi
0x180025b7f  cmp     ebx, r11d
0x180025b82  jnb     loc_1800257DC
0x180025b88  mov     rcx, [r10+8]
0x180025b8c  mov     eax, ebx
0x180025b8e  inc     ebx
0x180025b90  shl     rax, 4
0x180025b94  add     esi, [rax+rcx]
0x180025b97  cmp     ebx, r11d
0x180025b9a  jb      short loc_180025B8C
0x180025b9c  mov     [rsp+78h+var_48], esi
0x180025ba0  jmp     loc_1800257DC
0x180025ba5  movzx   r9d, word ptr [r15]
0x180025ba9  lea     rdx, [rbx+38h]
0x180025bad  mov     r8, [r15+8]
0x180025bb1  lea     rcx, [rsp+78h+var_58]
0x180025bb6  call    ??$CopyBuffer@E@?$AsyncSspiMarshaler@UKernelAllocator@@@@QEAAJPEAPEAEPEAEK@Z; AsyncSspiMarshaler<KernelAllocator>::CopyBuffer<uchar>(uchar * *,uchar *,ulong)
0x180025bbb  mov     esi, [rsp+78h+var_48]
0x180025bbf  mov     rbp, [rsp+78h+var_58]
0x180025bc4  mov     rdi, [rsp+78h+var_50]
0x180025bc9  test    eax, eax
0x180025bcb  js      loc_180025872
0x180025bd1  movzx   eax, word ptr [r15]
0x180025bd5  mov     [rbx+30h], ax
0x180025bd9  movzx   eax, word ptr [r15]
0x180025bdd  mov     [rbx+32h], ax
0x180025be1  jmp     loc_180025872
0x180025be6  mov     [rbx+68h], r8
0x180025bea  jmp     loc_18002599E
0x180025bef  mov     rdi, [rsp+78h+var_50]
0x180025bf4  mov     [rbx+68h], r8
0x180025bf8  jmp     loc_18002599E
  ... truncated ...
```
