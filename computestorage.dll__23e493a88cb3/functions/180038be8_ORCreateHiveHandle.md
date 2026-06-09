# ORCreateHiveHandle

- ea: `0x180038be8`
- end: `0x180038df6`
- name: `ORCreateHiveHandle`
- size: `526`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18003b1d8`
- `0x18003b660`

## callees

- `0x180003166`
- `0x180003172`
- `0x1800032b8`
- `0x180003bb5`
- `0x180038be8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180038c65`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180038c65`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038dc2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038dc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038c75`

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
0x180038be8  push    rbx
0x180038bea  push    rbp
0x180038beb  push    rsi
0x180038bec  push    rdi
0x180038bed  push    r12
0x180038bef  push    r14
0x180038bf1  push    r15
0x180038bf3  sub     rsp, 20h
0x180038bf7  xor     r12d, r12d
0x180038bfa  mov     rbp, rdx
0x180038bfd  mov     rdi, rcx
0x180038c00  mov     [r9], r12
0x180038c03  mov     r15d, 118h
0x180038c09  mov     r14, r9
0x180038c0c  mov     ecx, r15d; Size
0x180038c0f  mov     rsi, r8
0x180038c12  lea     edx, [r12+10h]; Alignment
0x180038c17  call    _o__aligned_malloc_0
0x180038c1c  mov     rbx, rax
0x180038c1f  test    rax, rax
0x180038c22  jnz     short loc_180038C2C
0x180038c24  lea     edi, [rax+8]
0x180038c27  jmp     loc_180038DE4
0x180038c2c  mov     r8, r15; Size
0x180038c2f  xor     edx, edx; Val
0x180038c31  mov     rcx, rbx; void *
0x180038c34  call    memset_0
0x180038c39  mov     dword ptr [rbx], 0BEE0BEE0h
0x180038c3f  lea     r15, [rbx+88h]
0x180038c46  mov     [rbx+10h], rdi
0x180038c4a  mov     edx, 80000400h; dwSpinCount
0x180038c4f  mov     ecx, [rdi+14h]
0x180038c52  mov     eax, [rdi+18h]
0x180038c55  shl     ecx, 0Ch
0x180038c58  add     eax, 0FFFFF000h
0x180038c5d  add     ecx, eax
0x180038c5f  mov     [rbx+18h], ecx
0x180038c62  mov     rcx, r15; lpCriticalSection
0x180038c65  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180038c6c  nop     dword ptr [rax+rax+00h]
0x180038c71  test    eax, eax
0x180038c73  jnz     short loc_180038C88
0x180038c75  call    cs:__imp_GetLastError
0x180038c7c  nop     dword ptr [rax+rax+00h]
0x180038c81  mov     edi, eax
0x180038c83  jmp     loc_180038DCE
0x180038c88  test    rsi, rsi
0x180038c8b  jz      short loc_180038CE2
0x180038c8d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180038c91  inc     rax
0x180038c94  cmp     [rsi+rax*2], r12w
0x180038c99  jnz     short loc_180038C91
0x180038c9b  add     rax, rax
0x180038c9e  mov     ecx, 0FFFFh
0x180038ca3  cmp     rax, rcx
0x180038ca6  ja      loc_180038DAC
0x180038cac  movzx   edi, ax
0x180038caf  mov     edx, 10h; Alignment
0x180038cb4  mov     [rbx+20h], di
0x180038cb8  mov     ecx, edi; Size
0x180038cba  mov     [rbx+22h], di
0x180038cbe  call    _o__aligned_malloc_0
0x180038cc3  mov     [rbx+28h], rax
0x180038cc7  test    rax, rax
0x180038cca  jnz     short loc_180038CD4
0x180038ccc  lea     edi, [rax+8]
0x180038ccf  jmp     loc_180038DBF
0x180038cd4  mov     r8, rdi; Size
0x180038cd7  mov     rdx, rsi; Src
0x180038cda  mov     rcx, rax; void *
0x180038cdd  call    memcpy_0
0x180038ce2  mov     eax, 0FFFFFFFFh
0x180038ce7  cmp     rbp, rax
0x180038cea  ja      loc_180038DB7
0x180038cf0  lea     rax, [rbx+50h]
0x180038cf4  mov     [rbx+30h], ebp
0x180038cf7  mov     [rax+8], rax
0x180038cfb  mov     r9d, r12d
0x180038cfe  mov     [rax], rax
0x180038d01  lea     rax, [rbx+0B8h]
0x180038d08  movq    xmm3, rax
0x180038d0d  punpcklqdq xmm3, xmm3
0x180038d11  movq    xmm0, cs:__xmm@00000003000000020000000100000000
0x180038d19  xorps   xmm1, xmm1
0x180038d1c  mov     r8d, r9d
0x180038d1f  movd    xmm2, r9d
0x180038d24  pshufd  xmm2, xmm2, 0
0x180038d29  paddd   xmm2, xmm0
0x180038d2d  lea     rax, [r8+0Ch]
0x180038d31  punpckldq xmm2, xmm1
0x180038d35  add     rax, rax
0x180038d38  psllq   xmm2, 4
0x180038d3d  paddq   xmm2, xmm3
0x180038d41  add     r8, r8
0x180038d44  movdqa  xmm0, xmm2
0x180038d48  psrldq  xmm0, 8
0x180038d4d  movq    qword ptr [rbx+rax*8], xmm2
0x180038d52  lea     eax, [r9+1]
0x180038d56  mov     edx, eax
0x180038d58  add     r9d, 2
0x180038d5c  add     rax, 0Ch
0x180038d60  movq    qword ptr [rbx+r8*8+0B8h], xmm2
0x180038d6a  add     rax, rax
0x180038d6d  add     rdx, rdx
0x180038d70  movq    qword ptr [rbx+rax*8], xmm0
0x180038d75  movq    qword ptr [rbx+rdx*8+0B8h], xmm0
0x180038d7e  cmp     r9d, 6
0x180038d82  jb      short loc_180038D11
0x180038d84  lea     rax, [rbx+60h]
0x180038d88  mov     [r14], rbx
0x180038d8b  mov     [rax+8], rax
0x180038d8f  mov     [rax], rax
0x180038d92  lea     rax, [rbx+70h]
0x180038d96  mov     [rax+8], rax
0x180038d9a  mov     [rax], rax
0x180038d9d  lea     rax, [rbx+40h]
0x180038da1  mov     [rax+8], rax
0x180038da5  mov     [rax], rax
0x180038da8  xor     eax, eax
0x180038daa  jmp     short loc_180038DE6
0x180038dac  mov     [rbx+20h], cx
0x180038db0  mov     edi, 57h ; 'W'
0x180038db5  jmp     short loc_180038DBF
0x180038db7  mov     [rbx+30h], eax
0x180038dba  mov     edi, 216h
0x180038dbf  mov     rcx, r15; lpCriticalSection
0x180038dc2  call    cs:__imp_DeleteCriticalSection
0x180038dc9  nop     dword ptr [rax+rax+00h]
0x180038dce  mov     rcx, [rbx+28h]; Block
0x180038dd2  test    rcx, rcx
0x180038dd5  jz      short loc_180038DDC
0x180038dd7  call    _aligned_free
0x180038ddc  mov     rcx, rbx; Block
0x180038ddf  call    _aligned_free
0x180038de4  mov     eax, edi
0x180038de6  add     rsp, 20h
0x180038dea  pop     r15
0x180038dec  pop     r14
0x180038dee  pop     r12
0x180038df0  pop     rdi
0x180038df1  pop     rsi
0x180038df2  pop     rbp
0x180038df3  pop     rbx
0x180038df4  retn
```
