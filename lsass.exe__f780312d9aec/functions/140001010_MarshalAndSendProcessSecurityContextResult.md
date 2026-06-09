# MarshalAndSendProcessSecurityContextResult

- ea: `0x140001010`
- end: `0x1400014b7`
- name: `MarshalAndSendProcessSecurityContextResult`
- size: `1191`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400049c8`

## callees

- `0x140001010`
- `0x140002a02`
- `0x140005295`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140001495`
- `ntdll!RtlFreeHeap` at `0x140001495`
- `ntdll!RtlAllocateHeap` at `0x14000109a`
- `ntdll!RtlAllocateHeap` at `0x14000109a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001467`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000145d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000145d`

## pseudocode

```c
__int64 __fastcall MarshalAndSendProcessSecurityContextResult(__int64 a1)
{
  __int64 v1; // r10
  unsigned int v2; // esi
  unsigned int v4; // r11d
  __int64 v5; // rax
  int v6; // ecx
  __int64 v7; // rax
  DWORD v8; // r12d
  PVOID Heap; // rax
  void *v10; // rbx
  _OWORD *v11; // rax
  _OWORD *v12; // rbp
  __int64 v13; // r15
  unsigned int v14; // ecx
  __int64 v15; // r13
  __int64 v16; // rax
  unsigned int i; // r12d
  const void *v18; // rdx
  unsigned int v19; // ecx
  __int64 v20; // rdi
  signed __int64 v21; // rax
  __int64 v22; // r9
  __int64 v23; // rax
  const void *v24; // rdx
  __int64 v25; // r14
  unsigned int v26; // ecx
  unsigned int v27; // ebx
  __int64 v28; // rdi
  __m128i v29; // xmm5
  __m128i v30; // xmm4
  __int64 v31; // r8
  __m128i v32; // xmm3
  __int64 v33; // rdx
  __m128i v34; // xmm2
  __int64 v35; // rcx
  __m128i v36; // xmm1
  __m128i v37; // xmm4
  __m128i v38; // xmm4
  __int64 v39; // rax
  _OWORD *v40; // rcx
  _OWORD *v41; // rdx
  int v42; // eax
  unsigned int v43; // eax
  __int64 v44; // rcx
  unsigned int v45; // r10d
  __int64 v46; // rax
  __int64 v47; // r8
  unsigned int v48; // edi
  signed int LastError; // eax
  DWORD v51; // [rsp+80h] [rbp+8h]
  __int64 v52; // [rsp+90h] [rbp+18h]

  v1 = *(_QWORD *)(a1 + 16);
  v2 = 0;
  if ( v1 )
  {
    v4 = *(_DWORD *)(v1 + 4);
    v2 = 16;
    if ( v4 )
    {
      v2 = 16 * (v4 + 1);
      v27 = 0;
      if ( v4 < 8 )
        goto LABEL_60;
      v28 = *(_QWORD *)(v1 + 8);
      v29 = 0;
      v30 = 0;
      do
      {
        v31 = 2LL * (v27 + 6);
        v32 = _mm_unpacklo_epi32(
                _mm_cvtsi32_si128(*(_DWORD *)(v28 + 16LL * v27)),
                _mm_cvtsi32_si128(*(_DWORD *)(v28 + 16LL * (v27 + 1))));
        v33 = 2LL * (v27 + 5);
        v34 = _mm_unpacklo_epi32(
                _mm_cvtsi32_si128(*(_DWORD *)(v28 + 16LL * (v27 + 2))),
                _mm_cvtsi32_si128(*(_DWORD *)(v28 + 16LL * (v27 + 3))));
        v35 = 2LL * (v27 + 4);
        v36 = _mm_cvtsi32_si128(*(_DWORD *)(v28 + 16LL * (v27 + 7)));
        v27 += 8;
        v29 = _mm_add_epi32(v29, _mm_unpacklo_epi64(v32, v34));
        v30 = _mm_add_epi32(
                v30,
                _mm_unpacklo_epi64(
                  _mm_unpacklo_epi32(
                    _mm_cvtsi32_si128(*(_DWORD *)(v28 + 8 * v35)),
                    _mm_cvtsi32_si128(*(_DWORD *)(v28 + 8 * v33))),
                  _mm_unpacklo_epi32(_mm_cvtsi32_si128(*(_DWORD *)(v28 + 8 * v31)), v36)));
      }
      while ( v27 < (v4 & 0xFFFFFFF8) );
      v37 = _mm_add_epi32(v30, v29);
      v38 = _mm_add_epi32(v37, _mm_srli_si128(v37, 8));
      v2 += _mm_cvtsi128_si32(_mm_add_epi32(v38, _mm_srli_si128(v38, 4)));
      if ( v27 < v4 )
      {
LABEL_60:
        do
        {
          v39 = v27++;
          v2 += *(_DWORD *)(16 * v39 + *(_QWORD *)(v1 + 8));
        }
        while ( v27 < v4 );
      }
    }
  }
  v5 = *(_QWORD *)(a1 + 24);
  if ( v5 )
  {
    v6 = *(_DWORD *)(v5 + 4);
    v2 += 16;
    if ( v6 )
      v2 += 8 * v6;
  }
  v7 = *(_QWORD *)(a1 + 32);
  if ( v7 )
  {
    v2 += 16;
    if ( *(_QWORD *)(v7 + 8) )
      v2 += *(_DWORD *)v7;
  }
  if ( !v2 )
    return 3221225626LL;
  v8 = v2 + 80;
  v51 = v2 + 80;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v2 + 80);
  v10 = Heap;
  if ( !Heap )
    return 3221225626LL;
  memset_0(Heap, 0, v2 + 80);
  v11 = (char *)v10 + 80;
  *(_OWORD *)v10 = *(_OWORD *)a1;
  v12 = (char *)v10 + 80;
  *((_OWORD *)v10 + 1) = *(_OWORD *)(a1 + 16);
  *((_OWORD *)v10 + 2) = *(_OWORD *)(a1 + 32);
  *((_OWORD *)v10 + 3) = *(_OWORD *)(a1 + 48);
  *((_OWORD *)v10 + 4) = *(_OWORD *)(a1 + 64);
  v13 = *(_QWORD *)(a1 + 16);
  *((_QWORD *)v10 + 2) = 0;
  if ( !v13 )
    goto LABEL_25;
  if ( v2 < 0x10 )
    goto LABEL_25;
  v2 -= 16;
  *((_QWORD *)v10 + 2) = v11;
  v12 = (char *)v10 + 96;
  if ( v10 == (void *)-80LL )
    goto LABEL_25;
  *v11 = *(_OWORD *)v13;
  v14 = 16 * *(_DWORD *)(v13 + 4);
  *((_QWORD *)v10 + 11) = 0;
  if ( v2 >= v14 )
  {
    *((_QWORD *)v10 + 11) = v12;
    v12 = (_OWORD *)((char *)v12 + v14);
    v2 -= v14;
  }
  v15 = *(_QWORD *)(*((_QWORD *)v10 + 2) + 8LL);
  if ( !v15 )
  {
    *((_QWORD *)v10 + 2) = 0;
    goto LABEL_25;
  }
  v16 = *(_QWORD *)(v13 + 8);
  for ( i = 0; ; ++i )
  {
    v52 = v16;
    if ( i >= *(_DWORD *)(v13 + 4) )
    {
      *(_QWORD *)(*((_QWORD *)v10 + 2) + 8LL) -= v10;
      *((_QWORD *)v10 + 2) -= v10;
      goto LABEL_24;
    }
    *(_OWORD *)v15 = *(_OWORD *)v16;
    v18 = *(const void **)(v16 + 8);
    v19 = *(_DWORD *)v16;
    *(_QWORD *)(v15 + 8) = 0;
    if ( v18 )
      break;
LABEL_22:
    v15 += 16;
    v16 += 16;
  }
  if ( v2 >= v19 )
  {
    v20 = v19;
    memcpy_0(v12, v18, v19);
    v2 -= v20;
    v21 = (char *)v12 - (_BYTE *)v10;
    v12 = (_OWORD *)((char *)v12 + v20);
    *(_QWORD *)(v15 + 8) = v21;
    v16 = v52;
    goto LABEL_22;
  }
  *((_QWORD *)v10 + 2) = 0;
LABEL_24:
  v8 = v51;
LABEL_25:
  v22 = *(_QWORD *)(a1 + 24);
  *((_QWORD *)v10 + 3) = 0;
  if ( v22 )
  {
    if ( v2 < 0x10 )
      goto LABEL_48;
    v40 = v12;
    *((_QWORD *)v10 + 3) = v12++;
    v2 -= 16;
    v41 = v12;
    if ( !v40 )
      goto LABEL_48;
    v42 = *(_DWORD *)(v22 + 4);
    *((_QWORD *)v40 + 1) = 0;
    v43 = 8 * v42;
    if ( v2 >= v43 )
    {
      v12 = (_OWORD *)((char *)v12 + v43);
      *((_QWORD *)v40 + 1) = v41;
      v2 -= v43;
    }
    v44 = *((_QWORD *)v10 + 3);
    if ( *(_QWORD *)(v44 + 8) )
    {
      v45 = 0;
      *(_DWORD *)v44 = *(_DWORD *)v22;
      for ( *(_DWORD *)(*((_QWORD *)v10 + 3) + 4LL) = *(_DWORD *)(v22 + 4);
            v45 < *(_DWORD *)(v22 + 4);
            *(_DWORD *)(v47 + *(_QWORD *)(*((_QWORD *)v10 + 3) + 8LL)) = *(_DWORD *)(8 * v46 + *(_QWORD *)(v22 + 8)) )
      {
        v46 = v45++;
        v47 = 8 * v46;
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v10 + 3) + 8LL) + v47 + 4) = *(_DWORD *)(*(_QWORD *)(v22 + 8) + 8 * v46 + 4);
      }
      *(_QWORD *)(*((_QWORD *)v10 + 3) + 8LL) -= v10;
      *((_QWORD *)v10 + 3) -= v10;
    }
    else
    {
LABEL_48:
      *((_QWORD *)v10 + 3) = 0;
    }
  }
  v23 = *(_QWORD *)(a1 + 32);
  *((_QWORD *)v10 + 4) = 0;
  if ( v23 )
  {
    if ( v2 >= 0x10 )
    {
      *((_QWORD *)v10 + 4) = v12;
      if ( v12 )
      {
        *v12 = *(_OWORD *)v23;
        v24 = *(const void **)(v23 + 8);
        v25 = *((_QWORD *)v10 + 4);
        v26 = *(_DWORD *)v23;
        *(_QWORD *)(v25 + 8) = 0;
        if ( !v24 )
          goto LABEL_32;
        if ( v2 - 16 < v26 )
        {
          *((_QWORD *)v10 + 4) = 0;
        }
        else
        {
          memcpy_0(v12 + 1, v24, v26);
          *(_QWORD *)(v25 + 8) = (char *)(v12 + 1) - (_BYTE *)v10;
LABEL_32:
          *((_QWORD *)v10 + 4) -= v10;
        }
      }
    }
  }
  if ( v8 )
  {
    v48 = 0;
    if ( !DeviceIoControl(fl, 0x39006Fu, v10, v8, 0, 0, 0, 0) )
    {
      LastError = GetLastError();
      v48 = LastError;
      if ( LastError > 0 )
        v48 = (unsigned __int16)LastError | 0xC0070000;
    }
  }
  else
  {
    v48 = -1073741811;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  return v48;
}

```

## disassembly

```asm
0x140001010  push    rbx
0x140001012  push    rbp
0x140001013  push    rsi
0x140001014  push    rdi
0x140001015  push    r14
0x140001017  sub     rsp, 50h
0x14000101b  mov     r10, [rcx+10h]
0x14000101f  xor     esi, esi
0x140001021  mov     r14, rcx
0x140001024  test    r10, r10
0x140001027  jz      short loc_14000103B
0x140001029  mov     r11d, [r10+4]
0x14000102d  mov     esi, 10h
0x140001032  test    r11d, r11d
0x140001035  jnz     loc_14000125D
0x14000103b  mov     rax, [r14+18h]
0x14000103f  test    rax, rax
0x140001042  jz      short loc_140001051
0x140001044  mov     ecx, [rax+4]
0x140001047  add     esi, 10h
0x14000104a  test    ecx, ecx
0x14000104c  jz      short loc_140001051
0x14000104e  lea     esi, [rsi+rcx*8]
0x140001051  mov     rax, [r14+20h]
0x140001055  test    rax, rax
0x140001058  jz      short loc_140001066
0x14000105a  add     esi, 10h
0x14000105d  cmp     qword ptr [rax+8], 0
0x140001062  jz      short loc_140001066
0x140001064  add     esi, [rax]
0x140001066  mov     [rsp+78h+arg_18], r12
0x14000106e  test    esi, esi
0x140001070  jz      loc_14000149F
0x140001076  mov     rcx, gs:60h
0x14000107f  lea     r12d, [rsi+50h]
0x140001083  mov     r8d, r12d; Size
0x140001086  mov     edx, 8; Flags
0x14000108b  mov     [rsp+78h+arg_0], r12d
0x140001093  mov     edi, r12d
0x140001096  mov     rcx, [rcx+30h]; HeapHandle
0x14000109a  call    cs:__imp_RtlAllocateHeap
0x1400010a0  mov     rbx, rax
0x1400010a3  test    rax, rax
0x1400010a6  jz      loc_14000149F
0x1400010ac  mov     r8d, edi; Size
0x1400010af  mov     [rsp+78h+var_38], r15
0x1400010b4  xor     edx, edx; Val
0x1400010b6  mov     rcx, rax; void *
0x1400010b9  call    memset_0
0x1400010be  movups  xmm0, xmmword ptr [r14]
0x1400010c2  lea     rax, [rbx+50h]
0x1400010c6  movups  xmmword ptr [rbx], xmm0
0x1400010c9  xor     r8d, r8d
0x1400010cc  mov     rbp, rax
0x1400010cf  movups  xmm1, xmmword ptr [r14+10h]
0x1400010d4  movups  xmmword ptr [rbx+10h], xmm1
0x1400010d8  movups  xmm0, xmmword ptr [r14+20h]
0x1400010dd  movups  xmmword ptr [rbx+20h], xmm0
0x1400010e1  movups  xmm1, xmmword ptr [r14+30h]
0x1400010e6  movups  xmmword ptr [rbx+30h], xmm1
0x1400010ea  movups  xmm0, xmmword ptr [r14+40h]
0x1400010ef  movups  xmmword ptr [rbx+40h], xmm0
0x1400010f3  mov     r15, [r14+10h]
0x1400010f7  mov     [rbx+10h], r8
0x1400010fb  test    r15, r15
0x1400010fe  jz      loc_1400011D9
0x140001104  cmp     esi, 10h
0x140001107  jb      loc_1400011D9
0x14000110d  add     esi, 0FFFFFFF0h
0x140001110  mov     [rbx+10h], rax
0x140001114  lea     rbp, [rax+10h]
0x140001118  test    rax, rax
0x14000111b  jz      loc_1400011D9
0x140001121  movups  xmm0, xmmword ptr [r15]
0x140001125  mov     [rsp+78h+var_30], r13
0x14000112a  movups  xmmword ptr [rax], xmm0
0x14000112d  mov     ecx, [r15+4]
0x140001131  shl     ecx, 4
0x140001134  mov     [rax+8], r8
0x140001138  cmp     esi, ecx
0x14000113a  jb      short loc_140001147
0x14000113c  mov     [rax+8], rbp
0x140001140  mov     eax, ecx
0x140001142  add     rbp, rax
0x140001145  sub     esi, ecx
0x140001147  mov     rax, [rbx+10h]
0x14000114b  mov     r13, [rax+8]
0x14000114f  test    r13, r13
0x140001152  jz      loc_140001410
0x140001158  mov     rax, [r15+8]
0x14000115c  mov     r12d, r8d
0x14000115f  mov     [rsp+78h+arg_10], rax
0x140001167  cmp     r12d, [r15+4]
0x14000116b  jnb     short loc_1400011C0
0x14000116d  movups  xmm0, xmmword ptr [rax]
0x140001170  movups  xmmword ptr [r13+0], xmm0
0x140001175  mov     rdx, [rax+8]; Src
0x140001179  mov     ecx, [rax]
0x14000117b  mov     [r13+8], r8
0x14000117f  test    rdx, rdx
0x140001182  jz      short loc_1400011B3
0x140001184  cmp     esi, ecx
0x140001186  jb      loc_140001422
0x14000118c  mov     edi, ecx
0x14000118e  mov     r8d, ecx; Size
0x140001191  mov     rcx, rbp; void *
0x140001194  call    memcpy_0
0x140001199  mov     rax, rbp
0x14000119c  sub     esi, edi
0x14000119e  sub     rax, rbx
0x1400011a1  add     rbp, rdi
0x1400011a4  mov     [r13+8], rax
0x1400011a8  xor     r8d, r8d
0x1400011ab  mov     rax, [rsp+78h+arg_10]
0x1400011b3  add     r13, 10h
0x1400011b7  add     rax, 10h
0x1400011bb  inc     r12d
0x1400011be  jmp     short loc_14000115F
0x1400011c0  mov     rax, [rbx+10h]
0x1400011c4  sub     [rax+8], rbx
0x1400011c8  sub     [rbx+10h], rbx
0x1400011cc  mov     r12d, [rsp+78h+arg_0]
0x1400011d4  mov     r13, [rsp+78h+var_30]
0x1400011d9  mov     r9, [r14+18h]
0x1400011dd  mov     r15, [rsp+78h+var_38]
0x1400011e2  mov     [rbx+18h], r8
0x1400011e6  test    r9, r9
0x1400011e9  jnz     loc_140001358
0x1400011ef  mov     rax, [r14+20h]
0x1400011f3  mov     [rbx+20h], r8
0x1400011f7  test    rax, rax
0x1400011fa  jz      loc_14000142F
0x140001200  cmp     esi, 10h
0x140001203  jb      loc_14000142F
0x140001209  mov     [rbx+20h], rbp
0x14000120d  test    rbp, rbp
0x140001210  jz      loc_14000142F
0x140001216  movups  xmm0, xmmword ptr [rax]
0x140001219  movups  xmmword ptr [rbp+0], xmm0
0x14000121d  mov     rdx, [rax+8]; Src
0x140001221  mov     r14, [rbx+20h]
0x140001225  mov     ecx, [rax]
0x140001227  mov     [r14+8], r8
0x14000122b  test    rdx, rdx
0x14000122e  jz      short loc_140001254
0x140001230  lea     eax, [rsi-10h]
0x140001233  cmp     eax, ecx
0x140001235  jb      loc_14000142B
0x14000123b  mov     r8d, ecx; Size
0x14000123e  lea     rdi, [rbp+10h]
0x140001242  mov     rcx, rdi; void *
0x140001245  call    memcpy_0
0x14000124a  sub     rdi, rbx
0x14000124d  mov     [r14+8], rdi
0x140001251  xor     r8d, r8d
0x140001254  sub     [rbx+20h], rbx
0x140001258  jmp     loc_14000142F
0x14000125d  lea     esi, [r11+1]
0x140001261  shl     esi, 4
0x140001264  test    r11d, r11d
0x140001267  jz      loc_14000103B
0x14000126d  xor     ebx, ebx
0x14000126f  cmp     r11d, 8
0x140001273  jb      loc_14000133E
0x140001279  mov     rdi, [r10+8]
0x14000127d  mov     ebp, r11d
0x140001280  and     ebp, 0FFFFFFF8h
0x140001283  xorps   xmm5, xmm5
0x140001286  xorps   xmm4, xmm4
0x140001289  lea     r8d, [rbx+3]
0x14000128d  mov     eax, ebx
0x14000128f  add     r8, r8
0x140001292  lea     edx, [rbx+2]
0x140001295  add     rdx, rdx
0x140001298  lea     ecx, [rbx+1]
0x14000129b  add     rcx, rcx
0x14000129e  lea     r9d, [rbx+7]
0x1400012a2  add     rax, rax
0x1400012a5  add     r9, r9
0x1400012a8  movd    xmm1, dword ptr [rdi+r8*8]
0x1400012ae  lea     r8d, [rbx+6]
0x1400012b2  movd    xmm2, dword ptr [rdi+rdx*8]
0x1400012b7  add     r8, r8
0x1400012ba  movd    xmm0, dword ptr [rdi+rcx*8]
0x1400012bf  lea     edx, [rbx+5]
0x1400012c2  movd    xmm3, dword ptr [rdi+rax*8]
0x1400012c7  lea     ecx, [rbx+4]
0x1400012ca  punpckldq xmm3, xmm0
0x1400012ce  add     rdx, rdx
0x1400012d1  punpckldq xmm2, xmm1
0x1400012d5  add     rcx, rcx
0x1400012d8  movd    xmm1, dword ptr [rdi+r9*8]
0x1400012de  add     ebx, 8
0x1400012e1  punpcklqdq xmm3, xmm2
0x1400012e5  movd    xmm2, dword ptr [rdi+r8*8]
0x1400012eb  paddd   xmm5, xmm3
0x1400012ef  movd    xmm0, dword ptr [rdi+rdx*8]
0x1400012f4  movd    xmm3, dword ptr [rdi+rcx*8]
0x1400012f9  punpckldq xmm2, xmm1
0x1400012fd  punpckldq xmm3, xmm0
0x140001301  punpcklqdq xmm3, xmm2
0x140001305  paddd   xmm4, xmm3
0x140001309  cmp     ebx, ebp
0x14000130b  jb      loc_140001289
0x140001311  paddd   xmm4, xmm5
0x140001315  movdqa  xmm0, xmm4
0x140001319  psrldq  xmm0, 8
0x14000131e  paddd   xmm4, xmm0
0x140001322  movdqa  xmm0, xmm4
0x140001326  psrldq  xmm0, 4
0x14000132b  paddd   xmm4, xmm0
0x14000132f  movd    eax, xmm4
0x140001333  add     esi, eax
0x140001335  cmp     ebx, r11d
0x140001338  jnb     loc_14000103B
0x14000133e  mov     rcx, [r10+8]
0x140001342  mov     eax, ebx
0x140001344  inc     ebx
0x140001346  shl     rax, 4
0x14000134a  add     esi, [rax+rcx]
0x14000134d  cmp     ebx, r11d
0x140001350  jnb     loc_14000103B
0x140001356  jmp     short loc_140001342
0x140001358  cmp     esi, 10h
0x14000135b  jb      loc_140001419
0x140001361  mov     rcx, rbp
0x140001364  mov     [rbx+18h], rbp
0x140001368  add     rbp, 10h
0x14000136c  add     esi, 0FFFFFFF0h
0x14000136f  mov     rdx, rbp
0x140001372  test    rcx, rcx
0x140001375  jz      loc_140001419
0x14000137b  mov     eax, [r9+4]
0x14000137f  mov     [rcx+8], r8
0x140001383  lea     eax, ds:0[rax*8]
0x14000138a  cmp     esi, eax
0x14000138c  jb      short loc_140001399
0x14000138e  mov     ebp, eax
0x140001390  add     rbp, rdx
0x140001393  mov     [rcx+8], rdx
0x140001397  sub     esi, eax
0x140001399  mov     rcx, [rbx+18h]
0x14000139d  cmp     qword ptr [rcx+8], 0
0x1400013a2  jz      short loc_140001419
0x1400013a4  mov     eax, [r9]
0x1400013a7  mov     r10d, r8d
0x1400013aa  mov     [rcx], eax
0x1400013ac  mov     rcx, [rbx+18h]
0x1400013b0  mov     eax, [r9+4]
0x1400013b4  mov     [rcx+4], eax
0x1400013b7  cmp     dword ptr [r9+4], 0
0x1400013bc  jbe     short loc_1400013FF
0x1400013be  mov     rdx, [r9+8]
0x1400013c2  mov     eax, r10d
0x1400013c5  inc     r10d
0x1400013c8  lea     r8, ds:0[rax*8]
0x1400013d0  mov     rax, [rbx+18h]
0x1400013d4  mov     rcx, [rax+8]
0x1400013d8  mov     eax, [rdx+r8+4]
0x1400013dd  mov     [rcx+r8+4], eax
0x1400013e2  mov     rax, [rbx+18h]
0x1400013e6  mov     rdx, [r9+8]
0x1400013ea  mov     rcx, [rax+8]
0x1400013ee  mov     eax, [r8+rdx]
0x1400013f2  mov     [r8+rcx], eax
0x1400013f6  cmp     r10d, [r9+4]
0x1400013fa  jb      short loc_1400013BE
0x1400013fc  xor     r8d, r8d
0x1400013ff  mov     rax, [rbx+18h]
0x140001403  sub     [rax+8], rbx
0x140001407  sub     [rbx+18h], rbx
0x14000140b  jmp     loc_1400011EF
0x140001410  mov     [rbx+10h], r8
0x140001414  jmp     loc_1400011D4
0x140001419  mov     [rbx+18h], r8
0x14000141d  jmp     loc_1400011EF
0x140001422  mov     [rbx+10h], r8
0x140001426  jmp     loc_1400011CC
0x14000142b  mov     [rbx+20h], r8
0x14000142f  test    r12d, r12d
0x140001432  jz      short loc_14000147E
0x140001434  mov     rcx, cs:fl; hDevice
0x14000143b  mov     edi, r8d
0x14000143e  mov     [rsp+78h+lpOverlapped], r8; lpOverlapped
0x140001443  mov     r9d, r12d; nInBufferSize
0x140001446  mov     [rsp+78h+lpBytesReturned], r8; lpBytesReturned
0x14000144b  mov     edx, 39006Fh; dwIoControlCode
0x140001450  mov     [rsp+78h+nOutBufferSize], r8d; nOutBufferSize
0x140001455  mov     [rsp+78h+lpOutBuffer], r8; lpOutBuffer
0x14000145a  mov     r8, rbx; lpInBuffer
0x14000145d  call    cs:__imp_DeviceIoControl
0x140001463  test    eax, eax
0x140001465  jnz     short loc_140001483
0x140001467  call    cs:__imp_GetLastError
0x14000146d  mov     edi, eax
0x14000146f  test    eax, eax
0x140001471  jle     short loc_140001483
0x140001473  movzx   edi, ax
0x140001476  or      edi, 0C0070000h
0x14000147c  jmp     short loc_140001483
  ... truncated ...
```
