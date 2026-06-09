# LdrpResolveDllName

- ea: `0x180027a70`
- end: `0x180027dd4`
- name: `LdrpResolveDllName`
- size: `868`
- prototype: `__int64 __usercall@<rax>(char ArgList@<cl>, int)`
- caller_count: `5`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x18002782c`
- `0x180027910`
- `0x180029eb0`
- `0x18002bc70`
- `0x1800c29c0`

## callees

- `0x18001d490`
- `0x18001eb80`
- `0x180021fd0`
- `0x180027a70`
- `0x180027de0`
- `0x180027f10`
- `0x180164280`

## string_xrefs

- `0x180027a86`: `DLL name: %wZ\n`
- `0x180027a9e`: `LdrpResolveDllName`
- `0x180027ade`: `LdrpResolveDllName`
- `0x180027c2f`: `LdrpResolveDllName`
- `0x180027c62`: `LdrpResolveDllName`
- `0x180027cc6`: `LdrpResolveDllName`
- `0x180027d22`: `LdrpResolveDllName`
- `0x180027d53`: `LdrpResolveDllName`

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
0x180027a70  push    rbx
0x180027a72  push    rbp
0x180027a73  push    rsi
0x180027a74  push    rdi
0x180027a75  push    r12
0x180027a77  push    r13
0x180027a79  push    r14
0x180027a7b  push    r15
0x180027a7d  sub     rsp, 58h
0x180027a81  mov     qword ptr [rsp+98h+ArgList], rcx; ArgList
0x180027a86  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x180027a8d  mov     r13, r9
0x180027a90  mov     [rsp+98h+Format], rax; Format
0x180027a95  mov     r14, r8
0x180027a98  mov     rdi, rdx
0x180027a9b  mov     rbx, rcx
0x180027a9e  lea     r8, aLdrpresolvedll; "LdrpResolveDllName"
0x180027aa5  xorps   xmm0, xmm0
0x180027aa8  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x180027aaf  mov     r9d, 3; int
0x180027ab5  mov     edx, 6C3h; int
0x180027aba  movups  [rsp+98h+Src], xmm0
0x180027abf  xor     r15d, r15d
0x180027ac2  call    LdrpLogInternal
0x180027ac7  lea     rax, aWz_0; "%wZ\n"
0x180027ace  mov     qword ptr [rsp+98h+ArgList], rbx; ArgList
0x180027ad3  mov     r9d, 5; int
0x180027ad9  mov     [rsp+98h+Format], rax; Format
0x180027ade  lea     r8, aLdrpresolvedll; "LdrpResolveDllName"
0x180027ae5  mov     edx, 6C4h; int
0x180027aea  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x180027af1  call    LdrpLogInternal
0x180027af6  test    [rsp+98h+arg_20], 200h
0x180027b01  jz      loc_180027D7B
0x180027b07  movups  xmm0, xmmword ptr [rbx]
0x180027b0a  xor     bpl, bpl
0x180027b0d  movups  [rsp+98h+Src], xmm0
0x180027b12  movzx   esi, word ptr [rsp+98h+Src]
0x180027b17  xor     eax, eax
0x180027b19  mov     r12, qword ptr [rsp+98h+Src+8]
0x180027b1e  mov     dword ptr [rsp+98h+Src], eax
0x180027b22  mov     qword ptr [rsp+98h+Src+8], rax
0x180027b27  lea     ebx, [rsi+2]
0x180027b2a  cmp     ebx, 0FFFEh
0x180027b30  ja      loc_180027DB6
0x180027b36  test    bl, 1
0x180027b39  jnz     loc_180027DCA
0x180027b3f  mov     ecx, ebx
0x180027b41  call    RtlpAllocateAtom
0x180027b46  mov     qword ptr [rsp+98h+Src+8], rax
0x180027b4b  test    rax, rax
0x180027b4e  jz      loc_180027DC0
0x180027b54  lea     r8, [rsi+2]; Size
0x180027b58  mov     word ptr [rsp+98h+Src+2], bx
0x180027b5d  mov     rdx, r12; Src
0x180027b60  mov     rcx, rax; void *
0x180027b63  mov     bpl, 1
0x180027b66  call    memmove
0x180027b6b  mov     word ptr [rsp+98h+Src], si
0x180027b70  jmp     short loc_180027B97
0x180027b72  movups  xmm0, xmmword ptr [rdi]
0x180027b75  lea     rcx, [rdi+10h]
0x180027b79  cmp     rcx, [rdi+8]
0x180027b7d  movups  [rsp+98h+Src], xmm0
0x180027b82  setnz   bpl
0x180027b86  jz      short loc_180027B12
0x180027b88  xor     eax, eax
0x180027b8a  mov     [rdi+8], rcx
0x180027b8e  mov     [rcx], ax
0x180027b91  mov     word ptr [rdi+2], 100h
0x180027b97  xor     eax, eax
0x180027b99  lea     rcx, [rsp+98h+Src]
0x180027b9e  mov     rdx, rdi
0x180027ba1  mov     [rdi], ax
0x180027ba4  call    LdrpGetNtPathFromDosPath
0x180027ba9  mov     ebx, eax
0x180027bab  test    eax, eax
0x180027bad  js      loc_180027C8E
0x180027bb3  movups  xmm0, [rsp+98h+Src]
0x180027bb8  movd    r9d, xmm0
0x180027bbd  movups  xmmword ptr [r13+0], xmm0
0x180027bc2  movzx   edx, r9w
0x180027bc6  psrldq  xmm0, 8
0x180027bcb  shr     dx, 1
0x180027bce  movq    r8, xmm0
0x180027bd3  jz      short loc_180027BFB
0x180027bd5  mov     r10d, 0FFFFh
0x180027bdb  nop     dword ptr [rax+rax+00h]
0x180027be0  movzx   eax, dx
0x180027be3  movzx   ecx, word ptr [r8+rax*2-2]
0x180027be9  cmp     cx, 5Ch ; '\'
0x180027bed  jz      short loc_180027BFB
0x180027bef  cmp     cx, 2Fh ; '/'
0x180027bf3  jz      short loc_180027BFB
0x180027bf5  add     dx, r10w
0x180027bf9  jnz     short loc_180027BE0
0x180027bfb  movzx   eax, dx
0x180027bfe  add     dx, dx
0x180027c01  sub     r9w, dx
0x180027c05  mov     dword ptr [rsp+98h+ArgList], ebx; ArgList
0x180027c09  mov     [r14], r9w
0x180027c0d  lea     rcx, [r8+rax*2]
0x180027c11  movzx   eax, word ptr [rsp+98h+Src+2]
0x180027c16  sub     ax, dx
0x180027c19  mov     [r14+8], rcx
0x180027c1d  mov     [r14+2], ax
0x180027c22  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x180027c29  mov     r9d, 4; int
0x180027c2f  lea     r8, aLdrpresolvedll; "LdrpResolveDllName"
0x180027c36  mov     [rsp+98h+Format], rax; Format
0x180027c3b  mov     edx, 73Dh; int
0x180027c40  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x180027c47  call    LdrpLogInternal
0x180027c4c  lea     rax, asc_180175AB4; "%x\n"
0x180027c53  mov     dword ptr [rsp+98h+ArgList], ebx; ArgList
0x180027c57  mov     r9d, 6; int
0x180027c5d  mov     [rsp+98h+Format], rax; Format
0x180027c62  lea     r8, aLdrpresolvedll; "LdrpResolveDllName"
0x180027c69  mov     edx, 741h; int
0x180027c6e  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x180027c75  call    LdrpLogInternal
0x180027c7a  mov     eax, ebx
0x180027c7c  add     rsp, 58h
0x180027c80  pop     r15
0x180027c82  pop     r14
0x180027c84  pop     r13
0x180027c86  pop     r12
0x180027c88  pop     rdi
0x180027c89  pop     rsi
0x180027c8a  pop     rbp
0x180027c8b  pop     rbx
0x180027c8c  retn
0x180027c8e  add     eax, 3FFFFFF1h
0x180027c93  cmp     eax, 2Ch ; ','
0x180027c96  ja      loc_180027D99
0x180027c9c  mov     rcx, 1C3000000011h
0x180027ca6  bt      rcx, rax
0x180027caa  jnb     loc_180027D99
0x180027cb0  lea     rax, aOriginalStatus; "Original status: 0x%08lx\n"
0x180027cb7  mov     dword ptr [rsp+98h+ArgList], ebx; ArgList
0x180027cbb  mov     r9d, 2; int
0x180027cc1  mov     [rsp+98h+Format], rax; Format
0x180027cc6  lea     r8, aLdrpresolvedll; "LdrpResolveDllName"
0x180027ccd  mov     edx, 729h; int
0x180027cd2  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x180027cd9  call    LdrpLogInternal
0x180027cde  mov     r15d, ebx
0x180027ce1  mov     ebx, 0C0000135h
0x180027ce6  mov     rax, qword ptr [rsp+98h+Src+8]
0x180027ceb  test    bpl, bpl
0x180027cee  jz      short loc_180027D0C
0x180027cf0  test    rax, rax
0x180027cf3  jz      short loc_180027D06
0x180027cf5  mov     rcx, rax
0x180027cf8  call    RtlpSysVolFree
0x180027cfd  mov     qword ptr [rsp+98h+Src+8], 0
0x180027d06  xor     eax, eax
0x180027d08  mov     dword ptr [rsp+98h+Src], eax
0x180027d0c  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x180027d13  mov     dword ptr [rsp+98h+ArgList], ebx; ArgList
0x180027d17  mov     r9d, 4; int
0x180027d1d  mov     [rsp+98h+Format], rax; Format
0x180027d22  lea     r8, aLdrpresolvedll; "LdrpResolveDllName"
0x180027d29  mov     edx, 73Dh; int
0x180027d2e  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x180027d35  call    LdrpLogInternal
0x180027d3a  test    r15d, r15d
0x180027d3d  jz      loc_180027C4C
0x180027d43  mov     [rsp+98h+var_68], ebx
0x180027d47  lea     rax, aXX; "%x-%x\n"
0x180027d4e  mov     dword ptr [rsp+98h+ArgList], r15d; ArgList
0x180027d53  lea     r8, aLdrpresolvedll; "LdrpResolveDllName"
0x180027d5a  mov     r9d, 6; int
0x180027d60  mov     [rsp+98h+Format], rax; Format
0x180027d65  mov     edx, 73Fh; int
0x180027d6a  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x180027d71  call    LdrpLogInternal
0x180027d76  jmp     loc_180027C7A
0x180027d7b  mov     rdx, rdi
0x180027d7e  mov     rcx, rbx
0x180027d81  call    LdrpGetFullPath
0x180027d86  mov     ebx, eax
0x180027d88  test    eax, eax
0x180027d8a  jns     loc_180027B72
0x180027d90  mov     dword ptr [rsp+98h+ArgList], eax
0x180027d94  jmp     loc_180027C22
0x180027d99  cmp     ebx, 80000010h
0x180027d9f  jz      loc_180027CB0
0x180027da5  cmp     ebx, 0C00000A3h
0x180027dab  jnz     loc_180027CE6
0x180027db1  jmp     loc_180027CB0
0x180027db6  mov     ebx, 0C0000106h
0x180027dbb  jmp     loc_180027CEB
0x180027dc0  mov     ebx, 0C0000017h
0x180027dc5  jmp     loc_180027CEB
0x180027dca  mov     ebx, 0C000000Dh
0x180027dcf  jmp     loc_180027CEB
```
