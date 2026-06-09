# pgsetComputeSymbolCP(void)

- ea: `0x14005a7b8`
- end: `0x14005a928`
- name: `?pgsetComputeSymbolCP@@YAPEAU_FD_GLYPHSET@@XZ`
- size: `368`
- prototype: `struct _FD_GLYPHSET *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140091fdc`

## callees

- `0x14005a7b8`
- `0x14005a930`
- `0x140076eea`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x14005a8bf`
- `KERNEL32!GlobalFree` at `0x14005a8bf`
- `KERNEL32!GlobalAlloc` at `0x14005a7f0`
- `KERNEL32!GlobalAlloc` at `0x14005a7f0`

## pseudocode

```c
struct _FD_GLYPHSET *__fastcall pgsetComputeSymbolCP(__int64 a1, INT a2, INT a3)
{
  _DWORD *v3; // rdi
  FD_GLYPHSET *v4; // rax
  FD_GLYPHSET *v5; // rbp
  __int64 cRuns; // r15
  _DWORD *v7; // rax
  unsigned int v8; // r14d
  __m128i *v9; // rsi
  WCHAR wcLow; // ax
  __int64 cGlyphs; // rax
  __int64 v12; // r13
  __int64 v13; // rax
  signed int i; // eax
  __m128i v15; // xmm0
  __int64 v17; // rbx
  __int64 v18; // r13
  __int64 v19; // rcx
  __int64 v20; // rcx

  v3 = 0;
  v4 = EngComputeGlyphSet(0, a2, a3);
  v5 = v4;
  if ( v4 )
  {
    cRuns = (int)v4->cRuns;
    v7 = GlobalAlloc(0, (unsigned int)(16 * (cRuns + 122)));
    v3 = v7;
    if ( v7 )
    {
      *v7 = 16 * (cRuns + 122);
      v8 = 0;
      v7[1] = 4;
      v9 = (__m128i *)&v7[4 * cRuns + 8];
      v7[2] = 480;
      for ( v7[3] = cRuns + 1; (int)v8 < (int)cRuns; v9 = (__m128i *)((char *)v9 + 4 * cGlyphs) )
      {
        wcLow = v5->awcrun[v8].wcLow;
        if ( wcLow >= 0xF000u )
          break;
        LOWORD(v3[4 * v8 + 4]) = wcLow;
        HIWORD(v3[4 * v8 + 4]) = v5->awcrun[v8].cGlyphs;
        *(_QWORD *)&v3[4 * v8 + 6] = v9;
        memcpy_0(v9, v5->awcrun[v8].phg, 4LL * v5->awcrun[v8].cGlyphs);
        cGlyphs = v5->awcrun[v8++].cGlyphs;
      }
      v12 = (int)v8;
      v13 = 2LL * (int)v8;
      v3[2 * v13 + 4] = 14741536;
      *(_QWORD *)&v3[2 * v13 + 6] = v9;
      for ( i = 32; i < 256; i += 4 )
      {
        v15 = _mm_cvtsi32_si128(i);
        *v9++ = _mm_add_epi32(_mm_shuffle_epi32(v15, 0), (__m128i)_xmm);
      }
      while ( (int)v8 < (int)cRuns )
      {
        v17 = v12 + 1;
        v18 = v12;
        v19 = 2 * v17;
        LOWORD(v3[2 * v19 + 4]) = v5->awcrun[v18].wcLow;
        HIWORD(v3[2 * v19 + 4]) = v5->awcrun[v18].cGlyphs;
        *(_QWORD *)&v3[2 * v19 + 6] = v9;
        memcpy_0(v9, v5->awcrun[v18].phg, 4LL * v5->awcrun[v18].cGlyphs);
        v20 = v5->awcrun[v18].cGlyphs;
        ++v8;
        v12 = v17;
        v9 = (__m128i *)((char *)v9 + 4 * v20);
      }
    }
    GlobalFree(v5);
  }
  return (struct _FD_GLYPHSET *)v3;
}

```

## disassembly

```asm
0x14005a7b8  push    rbx
0x14005a7ba  push    rbp
0x14005a7bb  push    rsi
0x14005a7bc  push    rdi
0x14005a7bd  push    r13
0x14005a7bf  push    r14
0x14005a7c1  push    r15
0x14005a7c3  sub     rsp, 20h
0x14005a7c7  xor     ecx, ecx; nCodePage
0x14005a7c9  xor     edi, edi
0x14005a7cb  call    EngComputeGlyphSet
0x14005a7d0  mov     rbp, rax
0x14005a7d3  test    rax, rax
0x14005a7d6  jz      loc_14005A8C5
0x14005a7dc  movsxd  r15, dword ptr [rax+0Ch]
0x14005a7e0  xor     ecx, ecx; uFlags
0x14005a7e2  lea     ebx, [r15+1]
0x14005a7e6  lea     eax, [rbx+79h]
0x14005a7e9  shl     eax, 4
0x14005a7ec  mov     edx, eax; dwBytes
0x14005a7ee  mov     esi, eax
0x14005a7f0  call    cs:__imp_GlobalAlloc
0x14005a7f6  mov     rdi, rax
0x14005a7f9  test    rax, rax
0x14005a7fc  jz      loc_14005A8BC
0x14005a802  mov     [rax], esi
0x14005a804  xor     r14d, r14d
0x14005a807  lea     rsi, [r15+2]
0x14005a80b  mov     dword ptr [rax+4], 4
0x14005a812  shl     rsi, 4
0x14005a816  add     rsi, rax
0x14005a819  mov     dword ptr [rax+8], 1E0h
0x14005a820  mov     [rax+0Ch], ebx
0x14005a823  test    r15d, r15d
0x14005a826  jle     short loc_14005A879
0x14005a828  mov     ebx, r14d
0x14005a82b  mov     ecx, 0F000h
0x14005a830  add     rbx, rbx
0x14005a833  movzx   eax, word ptr [rbp+rbx*8+10h]
0x14005a838  cmp     ax, cx
0x14005a83b  jnb     short loc_14005A879
0x14005a83d  mov     [rdi+rbx*8+10h], ax
0x14005a842  mov     rcx, rsi; void *
0x14005a845  movzx   eax, word ptr [rbp+rbx*8+12h]
0x14005a84a  mov     [rdi+rbx*8+12h], ax
0x14005a84f  mov     [rdi+rbx*8+18h], rsi
0x14005a854  movzx   r8d, word ptr [rbp+rbx*8+12h]
0x14005a85a  mov     rdx, [rbp+rbx*8+18h]; Src
0x14005a85f  shl     r8, 2; Size
0x14005a863  call    memcpy_0
0x14005a868  movzx   eax, word ptr [rbp+rbx*8+12h]
0x14005a86d  inc     r14d
0x14005a870  lea     rsi, [rsi+rax*4]
0x14005a874  cmp     r14d, r15d
0x14005a877  jl      short loc_14005A828
0x14005a879  movsxd  r13, r14d
0x14005a87c  mov     rax, r13
0x14005a87f  add     rax, rax
0x14005a882  mov     dword ptr [rdi+rax*8+10h], 0E0F020h
0x14005a88a  mov     [rdi+rax*8+18h], rsi
0x14005a88f  mov     eax, 20h ; ' '
0x14005a894  movd    xmm0, eax
0x14005a898  add     eax, 4
0x14005a89b  pshufd  xmm0, xmm0, 0
0x14005a8a0  paddd   xmm0, cs:__xmm@00000003000000020000000100000000
0x14005a8a8  movdqu  xmmword ptr [rsi], xmm0
0x14005a8ac  add     rsi, 10h
0x14005a8b0  cmp     eax, 100h
0x14005a8b5  jl      short loc_14005A894
0x14005a8b7  cmp     r14d, r15d
0x14005a8ba  jl      short loc_14005A8D7
0x14005a8bc  mov     rcx, rbp; hMem
0x14005a8bf  call    cs:__imp_GlobalFree
0x14005a8c5  mov     rax, rdi
0x14005a8c8  add     rsp, 20h
0x14005a8cc  pop     r15
0x14005a8ce  pop     r14
0x14005a8d0  pop     r13
0x14005a8d2  pop     rdi
0x14005a8d3  pop     rsi
0x14005a8d4  pop     rbp
0x14005a8d5  pop     rbx
0x14005a8d6  retn
0x14005a8d7  lea     rbx, [r13+1]
0x14005a8db  add     r13, r13
0x14005a8de  mov     rcx, rbx
0x14005a8e1  add     rcx, rcx
0x14005a8e4  movzx   eax, word ptr [rbp+r13*8+10h]
0x14005a8ea  mov     [rdi+rcx*8+10h], ax
0x14005a8ef  movzx   eax, word ptr [rbp+r13*8+12h]
0x14005a8f5  mov     [rdi+rcx*8+12h], ax
0x14005a8fa  mov     [rdi+rcx*8+18h], rsi
0x14005a8ff  mov     rcx, rsi; void *
0x14005a902  movzx   r8d, word ptr [rbp+r13*8+12h]
0x14005a908  mov     rdx, [rbp+r13*8+18h]; Src
0x14005a90d  shl     r8, 2; Size
0x14005a911  call    memcpy_0
0x14005a916  movzx   ecx, word ptr [rbp+r13*8+12h]
0x14005a91c  inc     r14d
0x14005a91f  mov     r13, rbx
0x14005a922  lea     rsi, [rsi+rcx*4]
0x14005a926  jmp     short loc_14005A8B7
```
