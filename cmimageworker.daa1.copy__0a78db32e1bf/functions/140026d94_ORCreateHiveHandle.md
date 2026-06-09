# ORCreateHiveHandle

- ea: `0x140026d94`
- end: `0x140026fa2`
- name: `ORCreateHiveHandle`
- size: `526`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140022fe0`
- `0x1400234b0`

## callees

- `0x1400029c6`
- `0x1400029d2`
- `0x140002b2c`
- `0x140026d94`
- `0x14002e8cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140026f6e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140026f6e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140026e11`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140026e11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026e21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026e21`

## pseudocode

```c
__int64 __fastcall ORCreateHiveHandle(__int64 a1, unsigned __int64 a2, _WORD *a3, _QWORD *a4)
{
  char *v8; // rax
  char *v9; // rbx
  DWORD LastError; // edi
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  size_t v13; // rdi
  void *v14; // rax
  unsigned int v15; // r9d
  __m128i v16; // xmm3
  __m128i v17; // xmm2
  __int64 v18; // r8
  unsigned __int64 v19; // xmm0_8
  __int64 v20; // rax
  void *v22; // rcx

  *a4 = 0;
  v8 = (char *)o__aligned_malloc_0(0x118u, 0x10u);
  v9 = v8;
  if ( !v8 )
    return 8;
  memset_0(v8, 0, 0x118u);
  *(_DWORD *)v9 = -1092567328;
  *((_QWORD *)v9 + 2) = a1;
  *((_DWORD *)v9 + 6) = *(_DWORD *)(a1 + 24) - 4096 + (*(_DWORD *)(a1 + 20) << 12);
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v9 + 136), 0x80000400) )
  {
    LastError = GetLastError();
LABEL_19:
    v22 = (void *)*((_QWORD *)v9 + 5);
    if ( v22 )
      aligned_free(v22);
    aligned_free(v9);
    return LastError;
  }
  if ( a3 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a3[v11] );
    v12 = 2 * v11;
    if ( v12 > 0xFFFF )
    {
      *((_WORD *)v9 + 16) = -1;
      LastError = 87;
      goto LABEL_18;
    }
    v13 = (unsigned __int16)v12;
    *((_WORD *)v9 + 16) = v12;
    *((_WORD *)v9 + 17) = v12;
    v14 = o__aligned_malloc_0((unsigned __int16)v12, 0x10u);
    *((_QWORD *)v9 + 5) = v14;
    if ( !v14 )
    {
      LastError = 8;
LABEL_18:
      DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 136));
      goto LABEL_19;
    }
    memcpy_0(v14, a3, v13);
  }
  if ( a2 > 0xFFFFFFFF )
  {
    *((_DWORD *)v9 + 12) = -1;
    LastError = 534;
    goto LABEL_18;
  }
  *((_DWORD *)v9 + 12) = a2;
  *((_QWORD *)v9 + 11) = v9 + 80;
  v15 = 0;
  *((_QWORD *)v9 + 10) = v9 + 80;
  v16 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)(v9 + 184), (__m128i)(unsigned __int64)(v9 + 184));
  do
  {
    v17 = _mm_add_epi64(
            _mm_slli_epi64(
              _mm_unpacklo_epi32(
                _mm_add_epi32(_mm_shuffle_epi32(_mm_cvtsi32_si128(v15), 0), _mm_loadl_epi64((const __m128i *)&_xmm)),
                (__m128i)0LL),
              4u),
            v16);
    v18 = 2LL * v15;
    v19 = _mm_srli_si128(v17, 8).m128i_u64[0];
    *(_QWORD *)&v9[16 * v15 + 192] = v17.m128i_i64[0];
    v20 = v15 + 1;
    v15 += 2;
    *(_QWORD *)&v9[8 * v18 + 184] = v17.m128i_i64[0];
    *(_QWORD *)&v9[16 * v20 + 192] = v19;
    *(_QWORD *)&v9[16 * v20 + 184] = v19;
  }
  while ( v15 < 6 );
  *a4 = v9;
  *((_QWORD *)v9 + 13) = v9 + 96;
  *((_QWORD *)v9 + 12) = v9 + 96;
  *((_QWORD *)v9 + 15) = v9 + 112;
  *((_QWORD *)v9 + 14) = v9 + 112;
  *((_QWORD *)v9 + 9) = v9 + 64;
  *((_QWORD *)v9 + 8) = v9 + 64;
  return 0;
}

```

## disassembly

```asm
0x140026d94  push    rbx
0x140026d96  push    rbp
0x140026d97  push    rsi
0x140026d98  push    rdi
0x140026d99  push    r12
0x140026d9b  push    r14
0x140026d9d  push    r15
0x140026d9f  sub     rsp, 20h
0x140026da3  xor     r12d, r12d
0x140026da6  mov     rbp, rdx
0x140026da9  mov     rdi, rcx
0x140026dac  mov     [r9], r12
0x140026daf  mov     r15d, 118h
0x140026db5  mov     r14, r9
0x140026db8  mov     ecx, r15d; Size
0x140026dbb  mov     rsi, r8
0x140026dbe  lea     edx, [r12+10h]; Alignment
0x140026dc3  call    _o__aligned_malloc_0
0x140026dc8  mov     rbx, rax
0x140026dcb  test    rax, rax
0x140026dce  jnz     short loc_140026DD8
0x140026dd0  lea     edi, [rax+8]
0x140026dd3  jmp     loc_140026F90
0x140026dd8  mov     r8, r15; Size
0x140026ddb  xor     edx, edx; Val
0x140026ddd  mov     rcx, rbx; void *
0x140026de0  call    memset_0
0x140026de5  mov     dword ptr [rbx], 0BEE0BEE0h
0x140026deb  lea     r15, [rbx+88h]
0x140026df2  mov     [rbx+10h], rdi
0x140026df6  mov     edx, 80000400h; dwSpinCount
0x140026dfb  mov     ecx, [rdi+14h]
0x140026dfe  mov     eax, [rdi+18h]
0x140026e01  shl     ecx, 0Ch
0x140026e04  add     eax, 0FFFFF000h
0x140026e09  add     ecx, eax
0x140026e0b  mov     [rbx+18h], ecx
0x140026e0e  mov     rcx, r15; lpCriticalSection
0x140026e11  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140026e18  nop     dword ptr [rax+rax+00h]
0x140026e1d  test    eax, eax
0x140026e1f  jnz     short loc_140026E34
0x140026e21  call    cs:__imp_GetLastError
0x140026e28  nop     dword ptr [rax+rax+00h]
0x140026e2d  mov     edi, eax
0x140026e2f  jmp     loc_140026F7A
0x140026e34  test    rsi, rsi
0x140026e37  jz      short loc_140026E8E
0x140026e39  or      rax, 0FFFFFFFFFFFFFFFFh
0x140026e3d  inc     rax
0x140026e40  cmp     [rsi+rax*2], r12w
0x140026e45  jnz     short loc_140026E3D
0x140026e47  add     rax, rax
0x140026e4a  mov     ecx, 0FFFFh
0x140026e4f  cmp     rax, rcx
0x140026e52  ja      loc_140026F58
0x140026e58  movzx   edi, ax
0x140026e5b  mov     edx, 10h; Alignment
0x140026e60  mov     [rbx+20h], di
0x140026e64  mov     ecx, edi; Size
0x140026e66  mov     [rbx+22h], di
0x140026e6a  call    _o__aligned_malloc_0
0x140026e6f  mov     [rbx+28h], rax
0x140026e73  test    rax, rax
0x140026e76  jnz     short loc_140026E80
0x140026e78  lea     edi, [rax+8]
0x140026e7b  jmp     loc_140026F6B
0x140026e80  mov     r8, rdi; Size
0x140026e83  mov     rdx, rsi; Src
0x140026e86  mov     rcx, rax; void *
0x140026e89  call    memcpy_0
0x140026e8e  mov     eax, 0FFFFFFFFh
0x140026e93  cmp     rbp, rax
0x140026e96  ja      loc_140026F63
0x140026e9c  lea     rax, [rbx+50h]
0x140026ea0  mov     [rbx+30h], ebp
0x140026ea3  mov     [rax+8], rax
0x140026ea7  mov     r9d, r12d
0x140026eaa  mov     [rax], rax
0x140026ead  lea     rax, [rbx+0B8h]
0x140026eb4  movq    xmm3, rax
0x140026eb9  punpcklqdq xmm3, xmm3
0x140026ebd  movq    xmm0, cs:__xmm@00000003000000020000000100000000
0x140026ec5  xorps   xmm1, xmm1
0x140026ec8  mov     r8d, r9d
0x140026ecb  movd    xmm2, r9d
0x140026ed0  pshufd  xmm2, xmm2, 0
0x140026ed5  paddd   xmm2, xmm0
0x140026ed9  lea     rax, [r8+0Ch]
0x140026edd  punpckldq xmm2, xmm1
0x140026ee1  add     rax, rax
0x140026ee4  psllq   xmm2, 4
0x140026ee9  paddq   xmm2, xmm3
0x140026eed  add     r8, r8
0x140026ef0  movdqa  xmm0, xmm2
0x140026ef4  psrldq  xmm0, 8
0x140026ef9  movq    qword ptr [rbx+rax*8], xmm2
0x140026efe  lea     eax, [r9+1]
0x140026f02  mov     edx, eax
0x140026f04  add     r9d, 2
0x140026f08  add     rax, 0Ch
0x140026f0c  movq    qword ptr [rbx+r8*8+0B8h], xmm2
0x140026f16  add     rax, rax
0x140026f19  add     rdx, rdx
0x140026f1c  movq    qword ptr [rbx+rax*8], xmm0
0x140026f21  movq    qword ptr [rbx+rdx*8+0B8h], xmm0
0x140026f2a  cmp     r9d, 6
0x140026f2e  jb      short loc_140026EBD
0x140026f30  lea     rax, [rbx+60h]
0x140026f34  mov     [r14], rbx
0x140026f37  mov     [rax+8], rax
0x140026f3b  mov     [rax], rax
0x140026f3e  lea     rax, [rbx+70h]
0x140026f42  mov     [rax+8], rax
0x140026f46  mov     [rax], rax
0x140026f49  lea     rax, [rbx+40h]
0x140026f4d  mov     [rax+8], rax
0x140026f51  mov     [rax], rax
0x140026f54  xor     eax, eax
0x140026f56  jmp     short loc_140026F92
0x140026f58  mov     [rbx+20h], cx
0x140026f5c  mov     edi, 57h ; 'W'
0x140026f61  jmp     short loc_140026F6B
0x140026f63  mov     [rbx+30h], eax
0x140026f66  mov     edi, 216h
0x140026f6b  mov     rcx, r15; lpCriticalSection
0x140026f6e  call    cs:__imp_DeleteCriticalSection
0x140026f75  nop     dword ptr [rax+rax+00h]
0x140026f7a  mov     rcx, [rbx+28h]; Block
0x140026f7e  test    rcx, rcx
0x140026f81  jz      short loc_140026F88
0x140026f83  call    _aligned_free
0x140026f88  mov     rcx, rbx; Block
0x140026f8b  call    _aligned_free
0x140026f90  mov     eax, edi
0x140026f92  add     rsp, 20h
0x140026f96  pop     r15
0x140026f98  pop     r14
0x140026f9a  pop     r12
0x140026f9c  pop     rdi
0x140026f9d  pop     rsi
0x140026f9e  pop     rbp
0x140026f9f  pop     rbx
0x140026fa0  retn
```
