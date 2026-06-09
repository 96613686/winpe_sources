# LdrpResolveDllName

- ea: `0x180027b80`
- end: `0x180027ee4`
- name: `LdrpResolveDllName`
- size: `868`
- prototype: `__int64 __usercall@<rax>(char ArgList@<cl>, int)`
- caller_count: `5`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x18002793c`
- `0x180027a20`
- `0x180029fc0`
- `0x18002c970`
- `0x1800be6e0`

## callees

- `0x18001d490`
- `0x18001eb80`
- `0x180021fe0`
- `0x180027b80`
- `0x180027ef0`
- `0x180028020`
- `0x180163a80`

## string_xrefs

- `0x180027b96`: `DLL name: %wZ\n`
- `0x180027bae`: `LdrpResolveDllName`
- `0x180027bee`: `LdrpResolveDllName`
- `0x180027d3f`: `LdrpResolveDllName`
- `0x180027d72`: `LdrpResolveDllName`
- `0x180027dd6`: `LdrpResolveDllName`
- `0x180027e32`: `LdrpResolveDllName`
- `0x180027e63`: `LdrpResolveDllName`

## pseudocode

```c
__int64 __fastcall LdrpResolveDllName(__m128i *ArgList, __m128i *a2, __int64 a3, _OWORD *a4, __int16 a5)
{
  unsigned int v9; // r15d
  bool v10; // bp
  __int64 v11; // rsi
  void *Atom; // rax
  const void *v13; // r12
  unsigned int v14; // ebx
  __m128i *v15; // rcx
  bool v16; // zf
  int NtPathFromDosPath; // eax
  unsigned int v18; // ebx
  __m128i v19; // xmm0
  unsigned __int16 v20; // r9
  unsigned __int64 v21; // xmm0_8
  unsigned __int16 v22; // dx
  __int16 v23; // cx
  __int64 v24; // rax
  __int16 v25; // dx
  unsigned __int64 v26; // rcx
  unsigned __int64 v28; // rax
  __int64 v29; // rcx
  int FullPath; // eax
  __m128i Src; // [rsp+40h] [rbp-58h] BYREF

  Src = 0;
  v9 = 0;
  LdrpLogInternal(
    (int)"minkernel\\ldr\\ldrfind.c",
    1731,
    (int)"LdrpResolveDllName",
    3,
    "DLL name: %wZ\n",
    (char)ArgList);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrfind.c", 1732, (int)"LdrpResolveDllName", 5, "%wZ\n", (char)ArgList);
  if ( (a5 & 0x200) != 0 )
  {
    v10 = 0;
    Src = *ArgList;
  }
  else
  {
    FullPath = LdrpGetFullPath(ArgList, a2);
    v18 = FullPath;
    if ( FullPath < 0 )
    {
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrfind.c",
        1853,
        (int)"LdrpResolveDllName",
        4,
        "Status: 0x%08lx\n",
        FullPath);
      goto LABEL_15;
    }
    v15 = a2 + 1;
    v16 = &a2[1] == (__m128i *)a2->m128i_i64[1];
    Src = *a2;
    v10 = !v16;
    if ( !v16 )
    {
      a2->m128i_i64[1] = (__int64)v15;
      v15->m128i_i16[0] = 0;
      a2->m128i_i16[1] = 256;
      goto LABEL_9;
    }
  }
  v11 = Src.m128i_u16[0];
  Atom = 0;
  v13 = (const void *)Src.m128i_i64[1];
  Src.m128i_i32[0] = 0;
  Src.m128i_i64[1] = 0;
  v14 = v11 + 2;
  if ( (unsigned int)(v11 + 2) > 0xFFFE )
  {
    v18 = -1073741562;
  }
  else if ( (v14 & 1) != 0 )
  {
    v18 = -1073741811;
  }
  else
  {
    Atom = (void *)RtlpAllocateAtom(v14);
    Src.m128i_i64[1] = (__int64)Atom;
    if ( Atom )
    {
      Src.m128i_i16[1] = v11 + 2;
      v10 = 1;
      memmove(Atom, v13, v11 + 2);
      Src.m128i_i16[0] = v11;
LABEL_9:
      a2->m128i_i16[0] = 0;
      NtPathFromDosPath = LdrpGetNtPathFromDosPath(&Src, a2);
      v18 = NtPathFromDosPath;
      if ( NtPathFromDosPath >= 0 )
      {
        v19 = Src;
        v20 = _mm_cvtsi128_si32(Src);
        *a4 = Src;
        v21 = _mm_srli_si128(v19, 8).m128i_u64[0];
        v22 = v20 >> 1;
        if ( v20 >> 1 )
        {
          do
          {
            v23 = *(_WORD *)(v21 + 2LL * v22 - 2);
            if ( v23 == 92 )
              break;
            if ( v23 == 47 )
              break;
            --v22;
          }
          while ( v22 );
        }
        v24 = v22;
        v25 = 2 * v22;
        *(_WORD *)a3 = v20 - v25;
        v26 = v21 + 2 * v24;
        LOWORD(v24) = Src.m128i_i16[1] - v25;
        *(_QWORD *)(a3 + 8) = v26;
        *(_WORD *)(a3 + 2) = v24;
        LdrpLogInternal((int)"minkernel\\ldr\\ldrfind.c", 1853, (int)"LdrpResolveDllName", 4, "Status: 0x%08lx\n", v18);
        goto LABEL_15;
      }
      v28 = (unsigned int)(NtPathFromDosPath + 1073741809);
      if ( (unsigned int)v28 <= 0x2C && (v29 = 0x1C3000000011LL, _bittest64(&v29, v28))
        || v18 == -2147483632
        || v18 == -1073741661 )
      {
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrfind.c",
          1833,
          (int)"LdrpResolveDllName",
          2,
          "Original status: 0x%08lx\n",
          v18);
        v9 = v18;
        v18 = -1073741515;
      }
      Atom = (void *)Src.m128i_i64[1];
      goto LABEL_21;
    }
    v18 = -1073741801;
  }
LABEL_21:
  if ( v10 )
  {
    if ( Atom )
    {
      RtlpSysVolFree(Atom);
      Src.m128i_i64[1] = 0;
    }
    Src.m128i_i32[0] = 0;
  }
  LdrpLogInternal((int)"minkernel\\ldr\\ldrfind.c", 1853, (int)"LdrpResolveDllName", 4, "Status: 0x%08lx\n", v18);
  if ( v9 )
  {
    LdrpLogInternal((int)"minkernel\\ldr\\ldrfind.c", 1855, (int)"LdrpResolveDllName", 6, "%x-%x\n", v9);
    return v18;
  }
LABEL_15:
  LdrpLogInternal((int)"minkernel\\ldr\\ldrfind.c", 1857, (int)"LdrpResolveDllName", 6, "%x\n", v18);
  return v18;
}

```

## disassembly

```asm
0x180027b80  push    rbx
0x180027b82  push    rbp
0x180027b83  push    rsi
0x180027b84  push    rdi
0x180027b85  push    r12
0x180027b87  push    r13
0x180027b89  push    r14
0x180027b8b  push    r15
0x180027b8d  sub     rsp, 58h
0x180027b91  mov     qword ptr [rsp+98h+ArgList], rcx; ArgList
0x180027b96  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x180027b9d  mov     r13, r9
0x180027ba0  mov     [rsp+98h+Format], rax; Format
0x180027ba5  mov     r14, r8
0x180027ba8  mov     rdi, rdx
0x180027bab  mov     rbx, rcx
0x180027bae  lea     r8, aLdrpresolvedll; "LdrpResolveDllName"
0x180027bb5  xorps   xmm0, xmm0
0x180027bb8  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x180027bbf  mov     r9d, 3; int
0x180027bc5  mov     edx, 6C3h; int
0x180027bca  movups  [rsp+98h+Src], xmm0
0x180027bcf  xor     r15d, r15d
0x180027bd2  call    LdrpLogInternal
0x180027bd7  lea     rax, aWz_0; "%wZ\n"
0x180027bde  mov     qword ptr [rsp+98h+ArgList], rbx; ArgList
0x180027be3  mov     r9d, 5; int
0x180027be9  mov     [rsp+98h+Format], rax; Format
0x180027bee  lea     r8, aLdrpresolvedll; "LdrpResolveDllName"
0x180027bf5  mov     edx, 6C4h; int
0x180027bfa  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x180027c01  call    LdrpLogInternal
0x180027c06  test    [rsp+98h+arg_20], 200h
0x180027c11  jz      loc_180027E8B
0x180027c17  movups  xmm0, xmmword ptr [rbx]
0x180027c1a  xor     bpl, bpl
0x180027c1d  movups  [rsp+98h+Src], xmm0
0x180027c22  movzx   esi, word ptr [rsp+98h+Src]
0x180027c27  xor     eax, eax
0x180027c29  mov     r12, qword ptr [rsp+98h+Src+8]
0x180027c2e  mov     dword ptr [rsp+98h+Src], eax
0x180027c32  mov     qword ptr [rsp+98h+Src+8], rax
0x180027c37  lea     ebx, [rsi+2]
0x180027c3a  cmp     ebx, 0FFFEh
0x180027c40  ja      loc_180027EC6
0x180027c46  test    bl, 1
0x180027c49  jnz     loc_180027EDA
0x180027c4f  mov     ecx, ebx
0x180027c51  call    RtlpAllocateAtom
0x180027c56  mov     qword ptr [rsp+98h+Src+8], rax
0x180027c5b  test    rax, rax
0x180027c5e  jz      loc_180027ED0
0x180027c64  lea     r8, [rsi+2]; Size
0x180027c68  mov     word ptr [rsp+98h+Src+2], bx
0x180027c6d  mov     rdx, r12; Src
0x180027c70  mov     rcx, rax; void *
0x180027c73  mov     bpl, 1
0x180027c76  call    memmove
0x180027c7b  mov     word ptr [rsp+98h+Src], si
0x180027c80  jmp     short loc_180027CA7
0x180027c82  movups  xmm0, xmmword ptr [rdi]
0x180027c85  lea     rcx, [rdi+10h]
0x180027c89  cmp     rcx, [rdi+8]
0x180027c8d  movups  [rsp+98h+Src], xmm0
0x180027c92  setnz   bpl
0x180027c96  jz      short loc_180027C22
0x180027c98  xor     eax, eax
0x180027c9a  mov     [rdi+8], rcx
0x180027c9e  mov     [rcx], ax
0x180027ca1  mov     word ptr [rdi+2], 100h
0x180027ca7  xor     eax, eax
0x180027ca9  lea     rcx, [rsp+98h+Src]
0x180027cae  mov     rdx, rdi
0x180027cb1  mov     [rdi], ax
0x180027cb4  call    LdrpGetNtPathFromDosPath
0x180027cb9  mov     ebx, eax
0x180027cbb  test    eax, eax
0x180027cbd  js      loc_180027D9E
0x180027cc3  movups  xmm0, [rsp+98h+Src]
0x180027cc8  movd    r9d, xmm0
0x180027ccd  movups  xmmword ptr [r13+0], xmm0
0x180027cd2  movzx   edx, r9w
0x180027cd6  psrldq  xmm0, 8
0x180027cdb  shr     dx, 1
0x180027cde  movq    r8, xmm0
0x180027ce3  jz      short loc_180027D0B
0x180027ce5  mov     r10d, 0FFFFh
0x180027ceb  nop     dword ptr [rax+rax+00h]
0x180027cf0  movzx   eax, dx
0x180027cf3  movzx   ecx, word ptr [r8+rax*2-2]
0x180027cf9  cmp     cx, 5Ch ; '\'
0x180027cfd  jz      short loc_180027D0B
0x180027cff  cmp     cx, 2Fh ; '/'
0x180027d03  jz      short loc_180027D0B
0x180027d05  add     dx, r10w
0x180027d09  jnz     short loc_180027CF0
0x180027d0b  movzx   eax, dx
0x180027d0e  add     dx, dx
0x180027d11  sub     r9w, dx
0x180027d15  mov     dword ptr [rsp+98h+ArgList], ebx; ArgList
0x180027d19  mov     [r14], r9w
0x180027d1d  lea     rcx, [r8+rax*2]
0x180027d21  movzx   eax, word ptr [rsp+98h+Src+2]
0x180027d26  sub     ax, dx
0x180027d29  mov     [r14+8], rcx
0x180027d2d  mov     [r14+2], ax
0x180027d32  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x180027d39  mov     r9d, 4; int
0x180027d3f  lea     r8, aLdrpresolvedll; "LdrpResolveDllName"
0x180027d46  mov     [rsp+98h+Format], rax; Format
0x180027d4b  mov     edx, 73Dh; int
0x180027d50  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x180027d57  call    LdrpLogInternal
0x180027d5c  lea     rax, asc_180175AB4; "%x\n"
0x180027d63  mov     dword ptr [rsp+98h+ArgList], ebx; ArgList
0x180027d67  mov     r9d, 6; int
0x180027d6d  mov     [rsp+98h+Format], rax; Format
0x180027d72  lea     r8, aLdrpresolvedll; "LdrpResolveDllName"
0x180027d79  mov     edx, 741h; int
0x180027d7e  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x180027d85  call    LdrpLogInternal
0x180027d8a  mov     eax, ebx
0x180027d8c  add     rsp, 58h
0x180027d90  pop     r15
0x180027d92  pop     r14
0x180027d94  pop     r13
0x180027d96  pop     r12
0x180027d98  pop     rdi
0x180027d99  pop     rsi
0x180027d9a  pop     rbp
0x180027d9b  pop     rbx
0x180027d9c  retn
0x180027d9e  add     eax, 3FFFFFF1h
0x180027da3  cmp     eax, 2Ch ; ','
0x180027da6  ja      loc_180027EA9
0x180027dac  mov     rcx, 1C3000000011h
0x180027db6  bt      rcx, rax
0x180027dba  jnb     loc_180027EA9
0x180027dc0  lea     rax, aOriginalStatus; "Original status: 0x%08lx\n"
0x180027dc7  mov     dword ptr [rsp+98h+ArgList], ebx; ArgList
0x180027dcb  mov     r9d, 2; int
0x180027dd1  mov     [rsp+98h+Format], rax; Format
0x180027dd6  lea     r8, aLdrpresolvedll; "LdrpResolveDllName"
0x180027ddd  mov     edx, 729h; int
0x180027de2  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x180027de9  call    LdrpLogInternal
0x180027dee  mov     r15d, ebx
0x180027df1  mov     ebx, 0C0000135h
0x180027df6  mov     rax, qword ptr [rsp+98h+Src+8]
0x180027dfb  test    bpl, bpl
0x180027dfe  jz      short loc_180027E1C
0x180027e00  test    rax, rax
0x180027e03  jz      short loc_180027E16
0x180027e05  mov     rcx, rax
0x180027e08  call    RtlpSysVolFree
0x180027e0d  mov     qword ptr [rsp+98h+Src+8], 0
0x180027e16  xor     eax, eax
0x180027e18  mov     dword ptr [rsp+98h+Src], eax
0x180027e1c  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x180027e23  mov     dword ptr [rsp+98h+ArgList], ebx; ArgList
0x180027e27  mov     r9d, 4; int
0x180027e2d  mov     [rsp+98h+Format], rax; Format
0x180027e32  lea     r8, aLdrpresolvedll; "LdrpResolveDllName"
0x180027e39  mov     edx, 73Dh; int
0x180027e3e  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x180027e45  call    LdrpLogInternal
0x180027e4a  test    r15d, r15d
0x180027e4d  jz      loc_180027D5C
0x180027e53  mov     [rsp+98h+var_68], ebx
0x180027e57  lea     rax, aXX; "%x-%x\n"
0x180027e5e  mov     dword ptr [rsp+98h+ArgList], r15d; ArgList
0x180027e63  lea     r8, aLdrpresolvedll; "LdrpResolveDllName"
0x180027e6a  mov     r9d, 6; int
0x180027e70  mov     [rsp+98h+Format], rax; Format
0x180027e75  mov     edx, 73Fh; int
0x180027e7a  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x180027e81  call    LdrpLogInternal
0x180027e86  jmp     loc_180027D8A
0x180027e8b  mov     rdx, rdi
0x180027e8e  mov     rcx, rbx
0x180027e91  call    LdrpGetFullPath
0x180027e96  mov     ebx, eax
0x180027e98  test    eax, eax
0x180027e9a  jns     loc_180027C82
0x180027ea0  mov     dword ptr [rsp+98h+ArgList], eax
0x180027ea4  jmp     loc_180027D32
0x180027ea9  cmp     ebx, 80000010h
0x180027eaf  jz      loc_180027DC0
0x180027eb5  cmp     ebx, 0C00000A3h
0x180027ebb  jnz     loc_180027DF6
0x180027ec1  jmp     loc_180027DC0
0x180027ec6  mov     ebx, 0C0000106h
0x180027ecb  jmp     loc_180027DFB
0x180027ed0  mov     ebx, 0C0000017h
0x180027ed5  jmp     loc_180027DFB
0x180027eda  mov     ebx, 0C000000Dh
0x180027edf  jmp     loc_180027DFB
```
