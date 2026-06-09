# ORCreateHiveHandle

- ea: `0x18002f82c`
- end: `0x18002f9d3`
- name: `ORCreateHiveHandle`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002e14c`

## callees

- `0x180003542`
- `0x18000354e`
- `0x18000362c`
- `0x18002f82c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f99f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f99f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002f89d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002f89d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f8ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f8ad`

## pseudocode

```c
__int64 __fastcall ORCreateHiveHandle(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  char *v6; // rax
  char *v7; // rbx
  DWORD LastError; // edi
  void *v9; // rax
  __int64 v10; // r9
  __m128i v11; // xmm3
  __int64 v12; // r8
  __m128i v13; // xmm2
  __int64 v14; // rax
  unsigned __int64 v15; // xmm0_8
  void *v17; // rcx

  *a4 = 0;
  v6 = (char *)o__aligned_malloc_0(0x118u, 0x10u);
  v7 = v6;
  if ( !v6 )
    return 8;
  memset_0(v6, 0, 0x118u);
  *((_QWORD *)v7 + 2) = a1;
  *(_DWORD *)v7 = -1092567328;
  *((_DWORD *)v7 + 6) = *(_DWORD *)(a1 + 24) - 4096 + (*(_DWORD *)(a1 + 20) << 12);
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v7 + 136), 0x80000400) )
  {
    LastError = GetLastError();
LABEL_10:
    v17 = (void *)*((_QWORD *)v7 + 5);
    if ( v17 )
      aligned_free(v17);
    aligned_free(v7);
    return LastError;
  }
  *((_DWORD *)v7 + 8) = 0;
  v9 = o__aligned_malloc_0(0, 0x10u);
  *((_QWORD *)v7 + 5) = v9;
  if ( !v9 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(v7 + 136));
    LastError = 8;
    goto LABEL_10;
  }
  *((_DWORD *)v7 + 12) = 0x2000;
  *((_QWORD *)v7 + 11) = v7 + 80;
  v10 = 0;
  *((_QWORD *)v7 + 10) = v7 + 80;
  v11 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)(v7 + 184), (__m128i)(unsigned __int64)(v7 + 184));
  do
  {
    v12 = 2LL * (unsigned int)v10;
    v13 = _mm_add_epi64(
            _mm_slli_epi64(
              _mm_unpacklo_epi32(
                _mm_add_epi32(_mm_shuffle_epi32(_mm_cvtsi32_si128(v10), 0), _mm_loadl_epi64((const __m128i *)&_xmm)),
                (__m128i)0LL),
              4u),
            v11);
    *(_QWORD *)&v7[16 * v10 + 192] = v13.m128i_i64[0];
    v14 = (unsigned int)(v10 + 1);
    v15 = _mm_srli_si128(v13, 8).m128i_u64[0];
    v10 = (unsigned int)(v10 + 2);
    *(_QWORD *)&v7[8 * v12 + 184] = v13.m128i_i64[0];
    *(_QWORD *)&v7[16 * v14 + 192] = v15;
    *(_QWORD *)&v7[16 * v14 + 184] = v15;
  }
  while ( (unsigned int)v10 < 6 );
  *a4 = v7;
  *((_QWORD *)v7 + 13) = v7 + 96;
  *((_QWORD *)v7 + 12) = v7 + 96;
  *((_QWORD *)v7 + 15) = v7 + 112;
  *((_QWORD *)v7 + 14) = v7 + 112;
  *((_QWORD *)v7 + 9) = v7 + 64;
  *((_QWORD *)v7 + 8) = v7 + 64;
  return 0;
}

```

## disassembly

```asm
0x18002f82c  push    rbx
0x18002f82e  push    rsi
0x18002f82f  push    rdi
0x18002f830  push    r14
0x18002f832  sub     rsp, 28h
0x18002f836  mov     rdi, rcx
0x18002f839  mov     qword ptr [r9], 0
0x18002f840  mov     esi, 118h
0x18002f845  mov     edx, 10h; Alignment
0x18002f84a  mov     ecx, esi; Size
0x18002f84c  mov     r14, r9
0x18002f84f  call    _o__aligned_malloc_0
0x18002f854  mov     rbx, rax
0x18002f857  test    rax, rax
0x18002f85a  jnz     short loc_18002F864
0x18002f85c  lea     edi, [rax+8]
0x18002f85f  jmp     loc_18002F9C6
0x18002f864  mov     r8, rsi; Size
0x18002f867  xor     edx, edx; Val
0x18002f869  mov     rcx, rbx; void *
0x18002f86c  call    memset_0
0x18002f871  mov     [rbx+10h], rdi
0x18002f875  mov     edx, 80000400h; dwSpinCount
0x18002f87a  mov     dword ptr [rbx], 0BEE0BEE0h
0x18002f880  mov     ecx, [rdi+14h]
0x18002f883  mov     eax, [rdi+18h]
0x18002f886  lea     rdi, [rbx+88h]
0x18002f88d  shl     ecx, 0Ch
0x18002f890  add     eax, 0FFFFF000h
0x18002f895  add     ecx, eax
0x18002f897  mov     [rbx+18h], ecx
0x18002f89a  mov     rcx, rdi; lpCriticalSection
0x18002f89d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002f8a4  nop     dword ptr [rax+rax+00h]
0x18002f8a9  test    eax, eax
0x18002f8ab  jnz     short loc_18002F8C0
0x18002f8ad  call    cs:__imp_GetLastError
0x18002f8b4  nop     dword ptr [rax+rax+00h]
0x18002f8b9  mov     edi, eax
0x18002f8bb  jmp     loc_18002F9B0
0x18002f8c0  xor     eax, eax
0x18002f8c2  xor     ecx, ecx; Size
0x18002f8c4  mov     [rbx+20h], eax
0x18002f8c7  lea     edx, [rax+10h]; Alignment
0x18002f8ca  call    _o__aligned_malloc_0
0x18002f8cf  mov     [rbx+28h], rax
0x18002f8d3  test    rax, rax
0x18002f8d6  jz      loc_18002F99C
0x18002f8dc  lea     rax, [rbx+50h]
0x18002f8e0  mov     dword ptr [rbx+30h], 2000h
0x18002f8e7  mov     [rax+8], rax
0x18002f8eb  xor     r9d, r9d
0x18002f8ee  mov     [rax], rax
0x18002f8f1  lea     rax, [rbx+0B8h]
0x18002f8f8  movq    xmm3, rax
0x18002f8fd  punpcklqdq xmm3, xmm3
0x18002f901  movq    xmm0, cs:__xmm@00000003000000020000000100000000
0x18002f909  lea     rax, [r9+0Ch]
0x18002f90d  add     rax, rax
0x18002f910  movd    xmm2, r9d
0x18002f915  pshufd  xmm2, xmm2, 0
0x18002f91a  xorps   xmm1, xmm1
0x18002f91d  paddd   xmm2, xmm0
0x18002f921  mov     r8d, r9d
0x18002f924  punpckldq xmm2, xmm1
0x18002f928  add     r8, r8
0x18002f92b  psllq   xmm2, 4
0x18002f930  paddq   xmm2, xmm3
0x18002f934  movq    qword ptr [rbx+rax*8], xmm2
0x18002f939  movdqa  xmm0, xmm2
0x18002f93d  lea     eax, [r9+1]
0x18002f941  psrldq  xmm0, 8
0x18002f946  mov     edx, eax
0x18002f948  add     r9d, 2
0x18002f94c  add     rax, 0Ch
0x18002f950  movq    qword ptr [rbx+r8*8+0B8h], xmm2
0x18002f95a  add     rax, rax
0x18002f95d  add     rdx, rdx
0x18002f960  movq    qword ptr [rbx+rax*8], xmm0
0x18002f965  movq    qword ptr [rbx+rdx*8+0B8h], xmm0
0x18002f96e  cmp     r9d, 6
0x18002f972  jb      short loc_18002F901
0x18002f974  lea     rax, [rbx+60h]
0x18002f978  mov     [r14], rbx
0x18002f97b  mov     [rax+8], rax
0x18002f97f  mov     [rax], rax
0x18002f982  lea     rax, [rbx+70h]
0x18002f986  mov     [rax+8], rax
0x18002f98a  mov     [rax], rax
0x18002f98d  lea     rax, [rbx+40h]
0x18002f991  mov     [rax+8], rax
0x18002f995  mov     [rax], rax
0x18002f998  xor     eax, eax
0x18002f99a  jmp     short loc_18002F9C8
0x18002f99c  mov     rcx, rdi; lpCriticalSection
0x18002f99f  call    cs:__imp_DeleteCriticalSection
0x18002f9a6  nop     dword ptr [rax+rax+00h]
0x18002f9ab  mov     edi, 8
0x18002f9b0  mov     rcx, [rbx+28h]; Block
0x18002f9b4  test    rcx, rcx
0x18002f9b7  jz      short loc_18002F9BE
0x18002f9b9  call    _aligned_free
0x18002f9be  mov     rcx, rbx; Block
0x18002f9c1  call    _aligned_free
0x18002f9c6  mov     eax, edi
0x18002f9c8  add     rsp, 28h
0x18002f9cc  pop     r14
0x18002f9ce  pop     rdi
0x18002f9cf  pop     rsi
0x18002f9d0  pop     rbx
0x18002f9d1  retn
```
