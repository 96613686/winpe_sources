# CredSSPGetCert

- ea: `0x1800030cc`
- end: `0x180003297`
- name: `CredSSPGetCert`
- size: `459`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800020d0`

## callees

- `0x1800030cc`
- `0x180003dd9`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000314a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800031a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003246`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000314a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800031a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003246`

## pseudocode

```c
__int64 __fastcall CredSSPGetCert(__int64 a1, _QWORD *a2, unsigned int *a3)
{
  __int64 *v5; // rbx
  int v6; // edx
  int v7; // eax
  unsigned int v8; // esi
  char *v9; // rax
  _DWORD *v10; // rdi
  __int64 result; // rax
  __int64 v12; // rbp
  _DWORD *v13; // rax
  _OWORD *v14; // rcx
  __int128 v15; // xmm1
  __int64 v16; // rax
  _DWORD *v17; // rax

  if ( !a1 || !a2 || !a3 )
    return 2148074333LL;
  *a3 = 0;
  *a2 = 0;
  if ( *(_DWORD *)a1 == 5 )
  {
    v5 = *(__int64 **)(a1 + 16);
    v6 = *(_DWORD *)(a1 + 8);
    v7 = *(_DWORD *)(a1 + 4);
  }
  else
  {
    if ( *(_DWORD *)a1 != 4 )
      return 2148074333LL;
    v5 = *(__int64 **)(a1 + 8);
    v6 = *(_DWORD *)(a1 + 4);
    v7 = *(_DWORD *)(a1 + 76);
  }
  if ( v6 == 1 && v5 )
  {
    if ( (v7 & 1) != 0 )
    {
      v8 = 52;
      v9 = (char *)LocalAlloc(0x40u, 0x34u);
      v10 = v9;
      if ( !v9 )
        return 2148074240LL;
      *(_DWORD *)v9 = 1;
      *((_DWORD *)v9 + 1) = 40;
      *(_OWORD *)(v9 + 8) = *(_OWORD *)v5;
      *(_OWORD *)(v9 + 24) = *((_OWORD *)v5 + 1);
      *((_QWORD *)v9 + 5) = v5[4];
      goto LABEL_24;
    }
    v12 = 2;
    if ( (v7 & 2) != 0 )
    {
      v8 = 308;
      v13 = LocalAlloc(0x40u, 0x134u);
      v10 = v13;
      if ( !v13 )
        return 2148074240LL;
      *v13 = 2;
      v14 = v13 + 2;
      v13[1] = 296;
      do
      {
        *v14 = *(_OWORD *)v5;
        v14[1] = *((_OWORD *)v5 + 1);
        v14[2] = *((_OWORD *)v5 + 2);
        v14[3] = *((_OWORD *)v5 + 3);
        v14[4] = *((_OWORD *)v5 + 4);
        v14[5] = *((_OWORD *)v5 + 5);
        v14[6] = *((_OWORD *)v5 + 6);
        v15 = *((_OWORD *)v5 + 7);
        v5 += 16;
        v14[7] = v15;
        v14 += 8;
        --v12;
      }
      while ( v12 );
      *v14 = *(_OWORD *)v5;
      v14[1] = *((_OWORD *)v5 + 1);
      *((_QWORD *)v14 + 4) = v5[4];
LABEL_24:
      *a2 = v10;
      result = 0;
      *a3 = v8;
      return result;
    }
    v16 = *v5;
    if ( *v5 )
    {
      v8 = *(_DWORD *)(v16 + 16) + 12;
      if ( *(_DWORD *)(v16 + 16) >= 0xFFFFFFF4 )
        return 3221225621LL;
      v17 = LocalAlloc(0x40u, v8);
      v10 = v17;
      if ( !v17 )
        return 2148074240LL;
      *v17 = 3;
      v17[1] = *(_DWORD *)(*v5 + 16);
      memcpy_0(v17 + 2, *(const void **)(*v5 + 8), *(unsigned int *)(*v5 + 16));
      goto LABEL_24;
    }
  }
  return 2148074333LL;
}

```

## disassembly

```asm
0x1800030cc  push    rbx
0x1800030ce  push    rbp
0x1800030cf  push    rsi
0x1800030d0  push    rdi
0x1800030d1  push    r14
0x1800030d3  push    r15
0x1800030d5  sub     rsp, 28h
0x1800030d9  mov     r14, r8
0x1800030dc  mov     r15, rdx
0x1800030df  test    rcx, rcx
0x1800030e2  jz      loc_180003285
0x1800030e8  test    rdx, rdx
0x1800030eb  jz      loc_180003285
0x1800030f1  test    r8, r8
0x1800030f4  jz      loc_180003285
0x1800030fa  mov     dword ptr [r8], 0
0x180003101  mov     qword ptr [rdx], 0
0x180003108  cmp     dword ptr [rcx], 5
0x18000310b  jnz     short loc_180003119
0x18000310d  mov     rbx, [rcx+10h]
0x180003111  mov     edx, [rcx+8]
0x180003114  mov     eax, [rcx+4]
0x180003117  jmp     short loc_18000312C
0x180003119  cmp     dword ptr [rcx], 4
0x18000311c  jnz     loc_180003285
0x180003122  mov     rbx, [rcx+8]
0x180003126  mov     edx, [rcx+4]
0x180003129  mov     eax, [rcx+4Ch]
0x18000312c  cmp     edx, 1
0x18000312f  jnz     loc_180003285
0x180003135  test    rbx, rbx
0x180003138  jz      loc_180003285
0x18000313e  test    dl, al
0x180003140  jz      short loc_18000318D
0x180003142  lea     esi, [rdx+33h]
0x180003145  mov     edx, esi; uBytes
0x180003147  lea     ecx, [rsi+0Ch]; uFlags
0x18000314a  call    cs:__imp_LocalAlloc
0x180003150  mov     rdi, rax
0x180003153  test    rax, rax
0x180003156  jnz     short loc_180003162
0x180003158  mov     eax, 80090300h
0x18000315d  jmp     loc_18000328A
0x180003162  mov     dword ptr [rax], 1
0x180003168  mov     dword ptr [rax+4], 28h ; '('
0x18000316f  movups  xmm0, xmmword ptr [rbx]
0x180003172  movups  xmmword ptr [rax+8], xmm0
0x180003176  movups  xmm1, xmmword ptr [rbx+10h]
0x18000317a  movups  xmmword ptr [rax+18h], xmm1
0x18000317e  movsd   xmm0, qword ptr [rbx+20h]
0x180003183  movsd   qword ptr [rax+28h], xmm0
0x180003188  jmp     loc_18000327B
0x18000318d  mov     ebp, 2
0x180003192  test    bpl, al
0x180003195  jz      loc_180003225
0x18000319b  mov     esi, 134h
0x1800031a0  lea     ecx, [rbp+3Eh]; uFlags
0x1800031a3  mov     edx, esi; uBytes
0x1800031a5  call    cs:__imp_LocalAlloc
0x1800031ab  mov     rdi, rax
0x1800031ae  test    rax, rax
0x1800031b1  jz      short loc_180003158
0x1800031b3  mov     [rax], ebp
0x1800031b5  lea     rcx, [rax+8]
0x1800031b9  mov     dword ptr [rax+4], 128h
0x1800031c0  lea     eax, [rbp+7Eh]
0x1800031c3  movups  xmm0, xmmword ptr [rbx]
0x1800031c6  movups  xmmword ptr [rcx], xmm0
0x1800031c9  movups  xmm1, xmmword ptr [rbx+10h]
0x1800031cd  movups  xmmword ptr [rcx+10h], xmm1
0x1800031d1  movups  xmm0, xmmword ptr [rbx+20h]
0x1800031d5  movups  xmmword ptr [rcx+20h], xmm0
0x1800031d9  movups  xmm1, xmmword ptr [rbx+30h]
0x1800031dd  movups  xmmword ptr [rcx+30h], xmm1
0x1800031e1  movups  xmm0, xmmword ptr [rbx+40h]
0x1800031e5  movups  xmmword ptr [rcx+40h], xmm0
0x1800031e9  movups  xmm1, xmmword ptr [rbx+50h]
0x1800031ed  movups  xmmword ptr [rcx+50h], xmm1
0x1800031f1  movups  xmm0, xmmword ptr [rbx+60h]
0x1800031f5  movups  xmmword ptr [rcx+60h], xmm0
0x1800031f9  movups  xmm1, xmmword ptr [rbx+70h]
0x1800031fd  add     rbx, rax
0x180003200  movups  xmmword ptr [rcx+70h], xmm1
0x180003204  add     rcx, rax
0x180003207  sub     rbp, 1
0x18000320b  jnz     short loc_1800031C3
0x18000320d  movups  xmm0, xmmword ptr [rbx]
0x180003210  movups  xmmword ptr [rcx], xmm0
0x180003213  movups  xmm1, xmmword ptr [rbx+10h]
0x180003217  movups  xmmword ptr [rcx+10h], xmm1
0x18000321b  mov     rax, [rbx+20h]
0x18000321f  mov     [rcx+20h], rax
0x180003223  jmp     short loc_18000327B
0x180003225  mov     rax, [rbx]
0x180003228  test    rax, rax
0x18000322b  jz      short loc_180003285
0x18000322d  mov     esi, [rax+10h]
0x180003230  add     esi, 0Ch
0x180003233  cmp     esi, 0Ch
0x180003236  jnb     short loc_18000323F
0x180003238  mov     eax, 0C0000095h
0x18000323d  jmp     short loc_18000328A
0x18000323f  mov     edx, esi; uBytes
0x180003241  mov     ecx, 40h ; '@'; uFlags
0x180003246  call    cs:__imp_LocalAlloc
0x18000324c  mov     rdi, rax
0x18000324f  test    rax, rax
0x180003252  jz      loc_180003158
0x180003258  mov     dword ptr [rax], 3
0x18000325e  mov     rax, [rbx]
0x180003261  mov     ecx, [rax+10h]
0x180003264  mov     [rdi+4], ecx
0x180003267  lea     rcx, [rdi+8]; void *
0x18000326b  mov     rdx, [rbx]
0x18000326e  mov     r8d, [rdx+10h]; Size
0x180003272  mov     rdx, [rdx+8]; Src
0x180003276  call    memcpy_0
0x18000327b  mov     [r15], rdi
0x18000327e  xor     eax, eax
0x180003280  mov     [r14], esi
0x180003283  jmp     short loc_18000328A
0x180003285  mov     eax, 8009035Dh
0x18000328a  add     rsp, 28h
0x18000328e  pop     r15
0x180003290  pop     r14
0x180003292  pop     rdi
0x180003293  pop     rsi
0x180003294  pop     rbp
0x180003295  pop     rbx
0x180003296  retn
```
