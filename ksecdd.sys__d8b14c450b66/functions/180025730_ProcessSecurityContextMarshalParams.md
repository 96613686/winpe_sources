# ProcessSecurityContextMarshalParams

- ea: `0x180025730`
- end: `0x180025bc0`
- name: `ProcessSecurityContextMarshalParams`
- size: `1168`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000f414`
- `0x180010980`
- `0x180010c80`
- `0x180025730`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800257d1`
- `ntoskrnl!ExAllocatePool2` at `0x1800257d1`

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
  const void **v17; // r15
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
  v17 = *(const void ***)(a1 + 72);
  v50 = v14 + 120;
  *((_OWORD *)v14 + 3) = 0;
  if ( v17 )
  {
    v49 = AsyncSspiMarshaler<KernelAllocator>::CopyBuffer<unsigned char>(
            (__int64)&v50,
            (_QWORD *)v14 + 7,
            v17[1],
            *(unsigned __int16 *)v17);
    v4 = v52;
    v16 = v50;
    v15 = v51;
    if ( v49 >= 0 )
    {
      *((_WORD *)v14 + 24) = *(_WORD *)v17;
      *((_WORD *)v14 + 25) = *(_WORD *)v17;
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
0x180025730  push    rsi
0x180025732  push    r13
0x180025734  push    r14
0x180025736  push    r15
0x180025738  sub     rsp, 58h
0x18002573c  mov     rax, [rcx+48h]
0x180025740  xor     esi, esi
0x180025742  mov     [rsp+78h+var_48], esi
0x180025746  mov     r15, r8
0x180025749  mov     r13, rdx
0x18002574c  mov     r14, rcx
0x18002574f  test    rax, rax
0x180025752  jz      short loc_18002575B
0x180025754  movzx   esi, word ptr [rax]
0x180025757  mov     [rsp+78h+var_48], esi
0x18002575b  mov     r10, [rcx+50h]
0x18002575f  mov     [rsp+78h+arg_8], rbx
0x180025767  mov     [rsp+78h+var_28], rbp
0x18002576c  mov     [rsp+78h+var_30], rdi
0x180025771  test    r10, r10
0x180025774  jz      short loc_18002578C
0x180025776  mov     r11d, [r10+4]
0x18002577a  add     esi, 10h
0x18002577d  mov     [rsp+78h+var_48], esi
0x180025781  mov     eax, esi
0x180025783  test    r11d, r11d
0x180025786  jnz     loc_180025A46
0x18002578c  mov     rax, [r14+68h]
0x180025790  test    rax, rax
0x180025793  jz      short loc_1800257AA
0x180025795  mov     ecx, [rax+4]
0x180025798  add     esi, 10h
0x18002579b  mov     [rsp+78h+var_48], esi
0x18002579f  test    ecx, ecx
0x1800257a1  jz      short loc_1800257AA
0x1800257a3  lea     esi, [rsi+rcx*8]
0x1800257a6  mov     [rsp+78h+var_48], esi
0x1800257aa  mov     [rsp+78h+var_38], r12
0x1800257af  mov     dword ptr [r15], 0
0x1800257b6  test    esi, esi
0x1800257b8  jz      loc_180025BB6
0x1800257be  lea     ebp, [rsi+78h]
0x1800257c1  mov     r8d, 436C7353h
0x1800257c7  mov     edx, ebp
0x1800257c9  mov     ecx, 100h
0x1800257ce  mov     r12d, ebp
0x1800257d1  call    cs:__imp_ExAllocatePool2
0x1800257d8  nop     dword ptr [rax+rax+00h]
0x1800257dd  mov     [rsp+78h+var_50], rax
0x1800257e2  mov     rbx, rax
0x1800257e5  mov     rdi, rax
0x1800257e8  test    rax, rax
0x1800257eb  jz      loc_180025BB6
0x1800257f1  mov     r8d, r12d; Size
0x1800257f4  xor     edx, edx; Val
0x1800257f6  mov     rcx, rax; void *
0x1800257f9  call    memset
0x1800257fe  mov     [r15], ebp
0x180025801  xorps   xmm0, xmm0
0x180025804  mov     [r13+0], rbx
0x180025808  lea     rbp, [rbx+78h]
0x18002580c  mov     r15, [r14+48h]
0x180025810  mov     [rsp+78h+var_58], rbp
0x180025815  movups  xmmword ptr [rbx+30h], xmm0
0x180025819  test    r15, r15
0x18002581c  jnz     loc_180025B55
0x180025822  lea     rcx, [r14+28h]
0x180025826  test    rcx, rcx
0x180025829  jz      short loc_18002583A
0x18002582b  mov     rax, [rcx]
0x18002582e  mov     [rbx+40h], rax
0x180025832  mov     rax, [rcx+8]
0x180025836  mov     [rbx+48h], rax
0x18002583a  lea     rcx, [r14+38h]
0x18002583e  test    rcx, rcx
0x180025841  jz      short loc_180025852
0x180025843  mov     rax, [rcx]
0x180025846  mov     [rbx+50h], rax
0x18002584a  mov     rax, [rcx+8]
0x18002584e  mov     [rbx+58h], rax
0x180025852  mov     eax, [r14+58h]
0x180025856  xor     r8d, r8d
0x180025859  mov     [rbx+60h], eax
0x18002585c  mov     eax, [r14+5Ch]
0x180025860  mov     [rbx+64h], eax
0x180025863  mov     r15, [r14+50h]
0x180025867  mov     [rbx+68h], r8
0x18002586b  test    rdi, rdi
0x18002586e  jz      loc_18002594E
0x180025874  test    r15, r15
0x180025877  jz      loc_18002594E
0x18002587d  cmp     esi, 10h
0x180025880  jb      loc_18002594E
0x180025886  mov     rax, rbp
0x180025889  mov     [rbx+68h], rbp
0x18002588d  add     rbp, 10h
0x180025891  add     esi, 0FFFFFFF0h
0x180025894  test    rax, rax
0x180025897  jz      loc_18002594E
0x18002589d  movups  xmm0, xmmword ptr [r15]
0x1800258a1  movups  xmmword ptr [rax], xmm0
0x1800258a4  mov     ecx, [r15+4]
0x1800258a8  mov     rax, [rbx+68h]
0x1800258ac  shl     ecx, 4
0x1800258af  mov     [rax+8], r8
0x1800258b3  cmp     esi, ecx
0x1800258b5  jb      short loc_1800258C2
0x1800258b7  mov     [rax+8], rbp
0x1800258bb  mov     eax, ecx
0x1800258bd  add     rbp, rax
0x1800258c0  sub     esi, ecx
0x1800258c2  mov     rax, [rbx+68h]
0x1800258c6  mov     r13, [rax+8]
0x1800258ca  test    r13, r13
0x1800258cd  jz      loc_180025B96
0x1800258d3  mov     rax, [r15+8]
0x1800258d7  mov     r12d, r8d
0x1800258da  mov     [rsp+78h+arg_10], rax
0x1800258e2  cmp     r12d, [r15+4]
0x1800258e6  jnb     short loc_18002593D
0x1800258e8  movups  xmm0, xmmword ptr [rax]
0x1800258eb  movups  xmmword ptr [r13+0], xmm0
0x1800258f0  mov     rdx, [rax+8]; Src
0x1800258f4  mov     ecx, [rax]
0x1800258f6  mov     [r13+8], r8
0x1800258fa  test    rdx, rdx
0x1800258fd  jz      short loc_180025930
0x1800258ff  cmp     esi, ecx
0x180025901  jb      loc_180025B9F
0x180025907  mov     edi, ecx
0x180025909  mov     r8d, ecx; Size
0x18002590c  mov     rcx, rbp; void *
0x18002590f  call    memmove
0x180025914  mov     rax, rbp
0x180025917  sub     esi, edi
0x180025919  sub     rax, [rsp+78h+var_50]
0x18002591e  add     rbp, rdi
0x180025921  mov     [r13+8], rax
0x180025925  xor     r8d, r8d
0x180025928  mov     rax, [rsp+78h+arg_10]
0x180025930  add     r13, 10h
0x180025934  add     rax, 10h
0x180025938  inc     r12d
0x18002593b  jmp     short loc_1800258DA
0x18002593d  mov     rax, [rbx+68h]
0x180025941  mov     rdi, [rsp+78h+var_50]
0x180025946  sub     [rax+8], rdi
0x18002594a  sub     [rbx+68h], rdi
0x18002594e  mov     r10, [r14+68h]
0x180025952  mov     [rbx+70h], r8
0x180025956  test    rdi, rdi
0x180025959  jz      loc_180025A20
0x18002595f  test    r10, r10
0x180025962  jz      loc_180025A20
0x180025968  cmp     esi, 10h
0x18002596b  jb      loc_180025A20
0x180025971  mov     [rbx+70h], rbp
0x180025975  lea     rdx, [rbp+10h]
0x180025979  test    rbp, rbp
0x18002597c  jz      loc_180025A20
0x180025982  mov     ecx, [r10+4]
0x180025986  lea     eax, [rsi-10h]
0x180025989  mov     [rbp+8], r8
0x18002598d  lea     ecx, ds:0[rcx*8]
0x180025994  cmp     eax, ecx
0x180025996  jb      short loc_18002599C
0x180025998  mov     [rbp+8], rdx
0x18002599c  mov     rcx, [rbx+70h]
0x1800259a0  cmp     qword ptr [rcx+8], 0
0x1800259a5  jz      loc_180025BAD
0x1800259ab  mov     eax, [r10]
0x1800259ae  mov     r11d, r8d
0x1800259b1  mov     [rcx], eax
0x1800259b3  mov     rcx, [rbx+70h]
0x1800259b7  mov     eax, [r10+4]
0x1800259bb  mov     [rcx+4], eax
0x1800259be  cmp     dword ptr [r10+4], 0
0x1800259c3  jbe     short loc_180025A14
0x1800259c5  nop     word ptr [rax+rax+00000000h]
0x1800259d0  mov     rdx, [r10+8]
0x1800259d4  mov     eax, r11d
0x1800259d7  lea     r8, ds:0[rax*8]
0x1800259df  mov     r9d, r11d
0x1800259e2  mov     rax, [rbx+70h]
0x1800259e6  add     r9, r9
0x1800259e9  inc     r11d
0x1800259ec  mov     rcx, [rax+8]
0x1800259f0  mov     eax, [rdx+r9*8+4]
0x1800259f5  mov     [rcx+r8+4], eax
0x1800259fa  mov     rax, [rbx+70h]
0x1800259fe  mov     rdx, [r10+8]
0x180025a02  mov     rcx, [rax+8]
0x180025a06  mov     eax, [rdx+r9*8]
0x180025a0a  mov     [r8+rcx], eax
0x180025a0e  cmp     r11d, [r10+4]
0x180025a12  jb      short loc_1800259D0
0x180025a14  mov     rax, [rbx+70h]
0x180025a18  sub     [rax+8], rdi
0x180025a1c  sub     [rbx+70h], rdi
0x180025a20  xor     eax, eax
0x180025a22  mov     r12, [rsp+78h+var_38]
0x180025a27  mov     rdi, [rsp+78h+var_30]
0x180025a2c  mov     rbp, [rsp+78h+var_28]
0x180025a31  mov     rbx, [rsp+78h+arg_8]
0x180025a39  add     rsp, 58h
0x180025a3d  pop     r15
0x180025a3f  pop     r14
0x180025a41  pop     r13
0x180025a43  pop     rsi
0x180025a44  retn
0x180025a46  mov     esi, r11d
0x180025a49  shl     esi, 4
0x180025a4c  add     esi, eax
0x180025a4e  mov     [rsp+78h+var_48], esi
0x180025a52  test    r11d, r11d
0x180025a55  jz      loc_18002578C
0x180025a5b  xor     ebx, ebx
0x180025a5d  cmp     r11d, 8
0x180025a61  jb      loc_180025B38
0x180025a67  mov     rbp, [r10+8]
0x180025a6b  mov     edi, r11d
0x180025a6e  and     edi, 0FFFFFFF8h
0x180025a71  xorps   xmm5, xmm5
0x180025a74  xorps   xmm4, xmm4
0x180025a77  lea     r8d, [rbx+3]
0x180025a7b  mov     eax, ebx
0x180025a7d  add     r8, r8
0x180025a80  lea     edx, [rbx+2]
0x180025a83  add     rdx, rdx
0x180025a86  lea     ecx, [rbx+1]
0x180025a89  add     rcx, rcx
0x180025a8c  lea     r9d, [rbx+7]
0x180025a90  add     rax, rax
0x180025a93  add     r9, r9
0x180025a96  movd    xmm1, dword ptr [rbp+r8*8+0]
0x180025a9d  lea     r8d, [rbx+6]
0x180025aa1  movd    xmm2, dword ptr [rbp+rdx*8+0]
0x180025aa7  add     r8, r8
0x180025aaa  movd    xmm0, dword ptr [rbp+rcx*8+0]
0x180025ab0  lea     edx, [rbx+5]
0x180025ab3  movd    xmm3, dword ptr [rbp+rax*8+0]
0x180025ab9  lea     ecx, [rbx+4]
0x180025abc  punpckldq xmm3, xmm0
0x180025ac0  add     rdx, rdx
0x180025ac3  punpckldq xmm2, xmm1
0x180025ac7  add     rcx, rcx
0x180025aca  movd    xmm1, dword ptr [rbp+r9*8+0]
0x180025ad1  add     ebx, 8
0x180025ad4  punpcklqdq xmm3, xmm2
0x180025ad8  movd    xmm2, dword ptr [rbp+r8*8+0]
0x180025adf  paddd   xmm5, xmm3
0x180025ae3  movd    xmm0, dword ptr [rbp+rdx*8+0]
0x180025ae9  movd    xmm3, dword ptr [rbp+rcx*8+0]
0x180025aef  punpckldq xmm2, xmm1
0x180025af3  punpckldq xmm3, xmm0
0x180025af7  punpcklqdq xmm3, xmm2
0x180025afb  paddd   xmm4, xmm3
0x180025aff  cmp     ebx, edi
0x180025b01  jb      loc_180025A77
0x180025b07  paddd   xmm4, xmm5
0x180025b0b  movdqa  xmm0, xmm4
0x180025b0f  psrldq  xmm0, 8
0x180025b14  paddd   xmm4, xmm0
0x180025b18  movdqa  xmm0, xmm4
0x180025b1c  psrldq  xmm0, 4
0x180025b21  paddd   xmm4, xmm0
0x180025b25  movd    eax, xmm4
0x180025b29  add     esi, eax
0x180025b2b  mov     [rsp+78h+var_48], esi
0x180025b2f  cmp     ebx, r11d
0x180025b32  jnb     loc_18002578C
0x180025b38  mov     rcx, [r10+8]
0x180025b3c  mov     eax, ebx
0x180025b3e  inc     ebx
0x180025b40  shl     rax, 4
0x180025b44  add     esi, [rax+rcx]
0x180025b47  cmp     ebx, r11d
0x180025b4a  jb      short loc_180025B3C
0x180025b4c  mov     [rsp+78h+var_48], esi
0x180025b50  jmp     loc_18002578C
0x180025b55  movzx   r9d, word ptr [r15]
0x180025b59  lea     rdx, [rbx+38h]
0x180025b5d  mov     r8, [r15+8]
0x180025b61  lea     rcx, [rsp+78h+var_58]
0x180025b66  call    ??$CopyBuffer@E@?$AsyncSspiMarshaler@UKernelAllocator@@@@QEAAJPEAPEAEPEAEK@Z; AsyncSspiMarshaler<KernelAllocator>::CopyBuffer<uchar>(uchar * *,uchar *,ulong)
0x180025b6b  mov     esi, [rsp+78h+var_48]
0x180025b6f  mov     rbp, [rsp+78h+var_58]
0x180025b74  mov     rdi, [rsp+78h+var_50]
0x180025b79  test    eax, eax
0x180025b7b  js      loc_180025822
0x180025b81  movzx   eax, word ptr [r15]
0x180025b85  mov     [rbx+30h], ax
0x180025b89  movzx   eax, word ptr [r15]
0x180025b8d  mov     [rbx+32h], ax
0x180025b91  jmp     loc_180025822
0x180025b96  mov     [rbx+68h], r8
0x180025b9a  jmp     loc_18002594E
0x180025b9f  mov     rdi, [rsp+78h+var_50]
0x180025ba4  mov     [rbx+68h], r8
0x180025ba8  jmp     loc_18002594E
  ... truncated ...
```
