# DiscpCreateTarget

- ea: `0x180005d2c`
- end: `0x1800060d7`
- name: `DiscpCreateTarget`
- size: `939`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const wchar_t *, _DWORD *, __int64, int, unsigned int, __int64, int, int, __int64 *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180001fb8`
- `0x1800027cc`
- `0x180008af8`
- `0x180008e84`
- `0x18000a748`
- `0x18000e040`

## callees

- `0x180001410`
- `0x18000325c`
- `0x180005d2c`
- `0x18001d38c`

## import_xrefs

- `ISCSIUM!DiscpValidateiSCSIString` at `0x180005d90`
- `ISCSIUM!DiscpValidateiSCSIString` at `0x180005d90`
- `ISCSIUM!DiscpAllocMemory` at `0x180005eb0`
- `ISCSIUM!DiscpAllocMemory` at `0x180005eb0`
- `ISCSIUM!DiscpULongAddList` at `0x180005e9f`
- `ISCSIUM!DiscpULongAddList` at `0x180005e9f`

## pseudocode

```c
__int64 __fastcall DiscpCreateTarget(
        const wchar_t *a1,
        const wchar_t *a2,
        const wchar_t *a3,
        _DWORD *a4,
        __int64 a5,
        int a6,
        unsigned int a7,
        __int64 a8,
        int a9,
        int a10,
        __int64 *a11)
{
  unsigned int v15; // ebx
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned int v18; // esi
  __int64 v19; // rcx
  unsigned int v20; // r9d
  unsigned int v21; // r15d
  unsigned int v22; // r8d
  unsigned int i; // edx
  _DWORD *v24; // rcx
  int v25; // r13d
  int v26; // edx
  __int64 v27; // rax
  __int64 v28; // rdi
  const wchar_t *v29; // r8
  unsigned int v30; // esi
  const wchar_t *v31; // r8
  wchar_t *v32; // rcx
  size_t v33; // rdx
  const wchar_t *v34; // r8
  int v35; // r11d
  unsigned int v36; // esi
  wchar_t *v37; // rcx
  unsigned int v38; // r15d
  unsigned int v39; // esi
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rcx
  unsigned int v43; // ebx
  const void **v44; // r15
  void *v45; // rdx
  _QWORD *v46; // rbx
  unsigned int v47; // r15d
  __int64 v48; // rsi
  const void *v49; // rdx
  const void *v50; // rdx
  unsigned int v52; // [rsp+20h] [rbp-61h] BYREF
  unsigned int v53; // [rsp+24h] [rbp-5Dh]
  __int64 v54; // [rsp+28h] [rbp-59h]
  STRSAFE_LPCWSTR pszSrc; // [rsp+30h] [rbp-51h]
  STRSAFE_LPCWSTR v56; // [rsp+38h] [rbp-49h]
  STRSAFE_LPCWSTR v57; // [rsp+40h] [rbp-41h]
  void *Src; // [rsp+48h] [rbp-39h]
  __int64 *v59; // [rsp+50h] [rbp-31h]
  _DWORD v60[8]; // [rsp+58h] [rbp-29h] BYREF

  v54 = a8;
  v59 = a11;
  Src = a4;
  pszSrc = a3;
  v57 = a2;
  v56 = a1;
  v52 = 0;
  v15 = DiscpValidateiSCSIString();
  if ( !v15 )
  {
    v16 = -1;
    if ( a3 )
    {
      v17 = -1;
      do
        ++v17;
      while ( a3[v17] );
      v18 = (2 * v17 + 9) & 0xFFFFFFF8;
    }
    else
    {
      v18 = 0;
    }
    v19 = -1;
    do
      ++v19;
    while ( a1[v19] );
    v20 = (2 * v19 + 9) & 0xFFFFFFF8;
    v53 = v20;
    if ( a2 )
    {
      do
        ++v16;
      while ( a2[v16] );
      v21 = (2 * v16 + 9) & 0xFFFFFFF8;
    }
    else
    {
      v21 = 0;
    }
    v22 = 0;
    for ( i = 0; i < a7; ++i )
    {
      v24 = *(_DWORD **)(a8 + 8LL * i);
      if ( *v24 )
        v22 = (1026 * *v24 + v22 + 15) & 0xFFFFFFF8;
    }
    if ( a4 )
      v25 = 16 * (a4[376] + 95);
    else
      v25 = 0;
    if ( a5 )
      v26 = *(_DWORD *)(a5 + 40) + *(_DWORD *)(a5 + 36) + 64;
    else
      v26 = 0;
    v60[5] = v22;
    v60[7] = v26;
    v15 = 8;
    v60[0] = 112;
    v60[1] = v18;
    v60[2] = v20;
    v60[3] = v21;
    v60[4] = 8 * a7;
    v60[6] = v25;
    if ( (int)DiscpULongAddList(v60, 8, &v52) < 0 )
    {
      return 87;
    }
    else
    {
      v27 = DiscpAllocMemory(v52);
      v28 = v27;
      if ( v27 )
      {
        v29 = pszSrc;
        *(_QWORD *)(v27 + 24) = v27 + 16;
        v15 = 0;
        *(_QWORD *)(v27 + 16) = v27 + 16;
        *(_DWORD *)(v27 + 44) = a9;
        *(_DWORD *)(v27 + 40) = a10;
        *(_DWORD *)(v27 + 104) = a6;
        *(_QWORD *)(v27 + 32) = 1;
        if ( v29 )
        {
          *(_QWORD *)(v27 + 64) = v27 + 112;
          StringCchCopyW((STRSAFE_LPWSTR)(v27 + 112), (unsigned __int64)v18 >> 1, v29);
          v30 = v18 + 112;
        }
        else
        {
          *(_QWORD *)(v27 + 64) = 0;
          v30 = 112;
        }
        v31 = v56;
        v32 = (wchar_t *)(v28 + v30);
        v33 = (unsigned __int64)v53 >> 1;
        *(_QWORD *)(v28 + 48) = v32;
        StringCchCopyW(v32, v33, v31);
        v34 = v57;
        v36 = v35 + v30;
        if ( v57 )
        {
          v37 = (wchar_t *)(v28 + v36);
          *(_QWORD *)(v28 + 56) = v37;
          StringCchCopyW(v37, (unsigned __int64)v21 >> 1, v34);
          v36 += v21;
        }
        else
        {
          *(_QWORD *)(v28 + 56) = 0;
        }
        v38 = 0;
        *(_DWORD *)(v28 + 72) = a7;
        *(_QWORD *)(v28 + 80) = v28 + v36;
        v39 = 8 * a7 + v36;
        if ( a7 )
        {
          v40 = v54;
          do
          {
            v41 = *(_QWORD *)(v40 + 8LL * v38);
            if ( *(_DWORD *)v41 )
            {
              v42 = v28 + v39;
              *(_QWORD *)(*(_QWORD *)(v28 + 80) + 8LL * v38) = v42;
              *(_DWORD *)v42 = *(_DWORD *)v41;
              *(_WORD *)(v42 + 6) = *(_WORD *)(v41 + 6);
              *(_BYTE *)(v42 + 4) = *(_BYTE *)(v41 + 4);
              v43 = 1026 * *(_DWORD *)v41;
              memcpy_0((void *)(v42 + 8), (const void *)(v41 + 8), v43);
              v39 += (v43 + 15) & 0xFFFFFFF8;
              v40 = v54;
              v15 = 0;
            }
            ++v38;
          }
          while ( v38 < a7 );
        }
        v44 = (const void **)Src;
        if ( Src )
        {
          v45 = Src;
          v46 = (_QWORD *)(v28 + v39);
          *(_QWORD *)(v28 + 88) = v46;
          memcpy_0(v46, v45, 0x5F0u);
          v46[189] = v46 + 190;
          memcpy_0(v46 + 190, v44[189], 16LL * *((unsigned int *)v44 + 376));
          v15 = 0;
        }
        else
        {
          *(_QWORD *)(v28 + 88) = 0;
        }
        if ( a5 )
        {
          v47 = 64;
          v48 = v28 + v25 + v39;
          *(_QWORD *)(v28 + 96) = v48;
          *(_OWORD *)v48 = *(_OWORD *)a5;
          *(_OWORD *)(v48 + 16) = *(_OWORD *)(a5 + 16);
          *(_OWORD *)(v48 + 32) = *(_OWORD *)(a5 + 32);
          *(_OWORD *)(v48 + 48) = *(_OWORD *)(a5 + 48);
          v49 = *(const void **)(a5 + 48);
          if ( v49 )
          {
            memcpy_0((void *)(v48 + 64), v49, *(unsigned int *)(a5 + 36));
            *(_QWORD *)(v48 + 48) = v48 + 64;
            v47 = *(_DWORD *)(a5 + 36) + 64;
            v15 = 0;
          }
          v50 = *(const void **)(a5 + 56);
          if ( v50 )
          {
            memcpy_0((void *)(v48 + v47), v50, *(unsigned int *)(a5 + 40));
            *(_QWORD *)(v48 + 56) = v48 + v47;
            v15 = 0;
          }
        }
        else
        {
          *(_QWORD *)(v28 + 96) = 0;
        }
      }
      *v59 = v28;
    }
  }
  return v15;
}

```

## disassembly

```asm
0x180005d2c  push    rbp
0x180005d2e  push    rbx
0x180005d2f  push    rsi
0x180005d30  push    rdi
0x180005d31  push    r12
0x180005d33  push    r13
0x180005d35  push    r14
0x180005d37  push    r15
0x180005d39  lea     rbp, [rsp-7]
0x180005d3e  sub     rsp, 88h
0x180005d45  mov     rax, cs:__security_cookie
0x180005d4c  xor     rax, rsp
0x180005d4f  mov     [rbp+3Fh+var_48], rax
0x180005d53  mov     rax, [rbp+3Fh+arg_50]
0x180005d5a  mov     rdi, r9
0x180005d5d  mov     r13, [rbp+3Fh+arg_38]
0x180005d64  mov     rsi, r8
0x180005d67  mov     r14, [rbp+3Fh+arg_20]
0x180005d6b  mov     r15, rdx
0x180005d6e  mov     [rbp+3Fh+var_98], r13
0x180005d72  mov     r12, rcx
0x180005d75  mov     [rbp+3Fh+var_70], rax
0x180005d79  mov     [rbp+3Fh+Src], r9
0x180005d7d  mov     [rbp+3Fh+pszSrc], r8
0x180005d81  mov     [rbp+3Fh+var_80], rdx
0x180005d85  mov     [rbp+3Fh+var_88], rcx
0x180005d89  mov     [rbp+3Fh+var_A0], 0
0x180005d90  call    cs:__imp_DiscpValidateiSCSIString
0x180005d96  xor     r11d, r11d
0x180005d99  mov     ebx, eax
0x180005d9b  test    eax, eax
0x180005d9d  jnz     loc_1800060B5
0x180005da3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005da7  mov     ebx, 0FFFFFFF8h
0x180005dac  test    rsi, rsi
0x180005daf  jz      short loc_180005DC9
0x180005db1  mov     rcx, rax
0x180005db4  inc     rcx
0x180005db7  cmp     [rsi+rcx*2], r11w
0x180005dbc  jnz     short loc_180005DB4
0x180005dbe  lea     esi, ds:9[rcx*2]
0x180005dc5  and     esi, ebx
0x180005dc7  jmp     short loc_180005DCC
0x180005dc9  mov     esi, r11d
0x180005dcc  mov     rcx, rax
0x180005dcf  inc     rcx
0x180005dd2  cmp     [r12+rcx*2], r11w
0x180005dd7  jnz     short loc_180005DCF
0x180005dd9  lea     r9d, ds:9[rcx*2]
0x180005de1  and     r9d, ebx
0x180005de4  mov     [rbp+3Fh+var_9C], r9d
0x180005de8  test    r15, r15
0x180005deb  jz      short loc_180005E04
0x180005ded  inc     rax
0x180005df0  cmp     [r15+rax*2], r11w
0x180005df5  jnz     short loc_180005DED
0x180005df7  lea     r15d, ds:9[rax*2]
0x180005dff  and     r15d, ebx
0x180005e02  jmp     short loc_180005E07
0x180005e04  mov     r15d, r11d
0x180005e07  mov     r12d, [rbp+3Fh+arg_30]
0x180005e0b  mov     r8d, r11d
0x180005e0e  mov     edx, r11d
0x180005e11  lea     r10d, ds:0[r12*8]
0x180005e19  test    r12d, r12d
0x180005e1c  jz      short loc_180005E41
0x180005e1e  mov     eax, edx
0x180005e20  mov     rcx, [r13+rax*8+0]
0x180005e25  cmp     [rcx], r11d
0x180005e28  jbe     short loc_180005E3A
0x180005e2a  imul    eax, [rcx], 402h
0x180005e30  add     r8d, 0Fh
0x180005e34  add     r8d, eax
0x180005e37  and     r8d, ebx
0x180005e3a  inc     edx
0x180005e3c  cmp     edx, r12d
0x180005e3f  jb      short loc_180005E1E
0x180005e41  test    rdi, rdi
0x180005e44  jz      short loc_180005E57
0x180005e46  mov     r13d, [rdi+5E0h]
0x180005e4d  add     r13d, 5Fh ; '_'
0x180005e51  shl     r13d, 4
0x180005e55  jmp     short loc_180005E5A
0x180005e57  mov     r13d, r11d
0x180005e5a  test    r14, r14
0x180005e5d  jz      short loc_180005E6C
0x180005e5f  mov     edx, [r14+24h]
0x180005e63  add     edx, 40h ; '@'
0x180005e66  add     edx, [r14+28h]
0x180005e6a  jmp     short loc_180005E6F
0x180005e6c  mov     edx, r11d
0x180005e6f  mov     [rbp+3Fh+var_54], r8d
0x180005e73  lea     rcx, [rbp+3Fh+var_68]
0x180005e77  mov     [rbp+3Fh+var_4C], edx
0x180005e7a  lea     r8, [rbp+3Fh+var_A0]
0x180005e7e  mov     ebx, 8
0x180005e83  mov     [rbp+3Fh+var_68], 70h ; 'p'
0x180005e8a  mov     edx, ebx
0x180005e8c  mov     [rbp+3Fh+var_64], esi
0x180005e8f  mov     [rbp+3Fh+var_60], r9d
0x180005e93  mov     [rbp+3Fh+var_5C], r15d
0x180005e97  mov     [rbp+3Fh+var_58], r10d
0x180005e9b  mov     [rbp+3Fh+var_50], r13d
0x180005e9f  call    cs:__imp_DiscpULongAddList
0x180005ea5  test    eax, eax
0x180005ea7  js      loc_1800060B0
0x180005ead  mov     ecx, [rbp+3Fh+var_A0]
0x180005eb0  call    cs:__imp_DiscpAllocMemory
0x180005eb6  mov     rdi, rax
0x180005eb9  test    rax, rax
0x180005ebc  jz      loc_1800060A7
0x180005ec2  mov     r8, [rbp+3Fh+pszSrc]; pszSrc
0x180005ec6  lea     rcx, [rax+10h]
0x180005eca  mov     [rcx+8], rcx
0x180005ece  xor     ebx, ebx
0x180005ed0  mov     [rcx], rcx
0x180005ed3  mov     ecx, [rbp+3Fh+arg_40]
0x180005ed9  mov     [rax+2Ch], ecx
0x180005edc  mov     ecx, [rbp+3Fh+arg_48]
0x180005ee2  mov     [rax+28h], ecx
0x180005ee5  mov     ecx, [rbp+3Fh+arg_28]
0x180005ee8  mov     [rax+68h], ecx
0x180005eeb  mov     qword ptr [rax+20h], 1
0x180005ef3  test    r8, r8
0x180005ef6  jz      short loc_180005F0F
0x180005ef8  lea     rcx, [rax+70h]; pszDest
0x180005efc  mov     edx, esi
0x180005efe  shr     rdx, 1; cchDest
0x180005f01  mov     [rax+40h], rcx
0x180005f05  call    StringCchCopyW
0x180005f0a  add     esi, 70h ; 'p'
0x180005f0d  jmp     short loc_180005F18
0x180005f0f  mov     [rax+40h], rbx
0x180005f13  mov     esi, 70h ; 'p'
0x180005f18  mov     r11d, [rbp+3Fh+var_9C]
0x180005f1c  mov     r8, [rbp+3Fh+var_88]; pszSrc
0x180005f20  mov     edx, r11d
0x180005f23  mov     ecx, esi
0x180005f25  add     rcx, rdi; pszDest
0x180005f28  shr     rdx, 1; cchDest
0x180005f2b  mov     [rdi+30h], rcx
0x180005f2f  call    StringCchCopyW
0x180005f34  mov     r8, [rbp+3Fh+var_80]; pszSrc
0x180005f38  add     esi, r11d
0x180005f3b  test    r8, r8
0x180005f3e  jz      short loc_180005F59
0x180005f40  mov     ecx, esi
0x180005f42  add     rcx, rdi; pszDest
0x180005f45  mov     edx, r15d
0x180005f48  shr     rdx, 1; cchDest
0x180005f4b  mov     [rdi+38h], rcx
0x180005f4f  call    StringCchCopyW
0x180005f54  add     esi, r15d
0x180005f57  jmp     short loc_180005F5D
0x180005f59  mov     [rdi+38h], rbx
0x180005f5d  mov     eax, esi
0x180005f5f  mov     r15d, ebx
0x180005f62  add     rax, rdi
0x180005f65  mov     [rdi+48h], r12d
0x180005f69  mov     [rdi+50h], rax
0x180005f6d  lea     eax, ds:0[r12*8]
0x180005f75  add     esi, eax
0x180005f77  test    r12d, r12d
0x180005f7a  jz      short loc_180005FD6
0x180005f7c  mov     rax, [rbp+3Fh+var_98]
0x180005f80  mov     r8d, r15d
0x180005f83  mov     rdx, [rax+r8*8]
0x180005f87  cmp     [rdx], ebx
0x180005f89  jbe     short loc_180005FCE
0x180005f8b  mov     rax, [rdi+50h]
0x180005f8f  mov     ecx, esi
0x180005f91  add     rcx, rdi
0x180005f94  mov     [rax+r8*8], rcx
0x180005f98  mov     eax, [rdx]
0x180005f9a  mov     [rcx], eax
0x180005f9c  movzx   eax, word ptr [rdx+6]
0x180005fa0  mov     [rcx+6], ax
0x180005fa4  mov     al, [rdx+4]
0x180005fa7  mov     [rcx+4], al
0x180005faa  add     rcx, 8; void *
0x180005fae  imul    ebx, [rdx], 402h
0x180005fb4  add     rdx, 8; Src
0x180005fb8  mov     r8d, ebx; Size
0x180005fbb  call    memcpy_0
0x180005fc0  lea     eax, [rbx+0Fh]
0x180005fc3  and     eax, 0FFFFFFF8h
0x180005fc6  add     esi, eax
0x180005fc8  mov     rax, [rbp+3Fh+var_98]
0x180005fcc  xor     ebx, ebx
0x180005fce  inc     r15d
0x180005fd1  cmp     r15d, r12d
0x180005fd4  jb      short loc_180005F80
0x180005fd6  mov     r15, [rbp+3Fh+Src]
0x180005fda  test    r15, r15
0x180005fdd  jz      short loc_180006022
0x180005fdf  mov     ebx, esi
0x180005fe1  mov     rdx, r15; Src
0x180005fe4  add     rbx, rdi
0x180005fe7  mov     r8d, 5F0h; Size
0x180005fed  mov     rcx, rbx; void *
0x180005ff0  mov     [rdi+58h], rbx
0x180005ff4  call    memcpy_0
0x180005ff9  lea     rcx, [rbx+5F0h]; void *
0x180006000  mov     [rbx+5E8h], rcx
0x180006007  mov     r8d, [r15+5E0h]
0x18000600e  mov     rdx, [r15+5E8h]; Src
0x180006015  shl     r8, 4; Size
0x180006019  call    memcpy_0
0x18000601e  xor     ebx, ebx
0x180006020  jmp     short loc_180006026
0x180006022  mov     [rdi+58h], rbx
0x180006026  test    r14, r14
0x180006029  jz      short loc_1800060A3
0x18000602b  add     esi, r13d
0x18000602e  mov     r15d, 40h ; '@'
0x180006034  add     rsi, rdi
0x180006037  mov     [rdi+60h], rsi
0x18000603b  movups  xmm0, xmmword ptr [r14]
0x18000603f  movups  xmmword ptr [rsi], xmm0
0x180006042  movups  xmm1, xmmword ptr [r14+10h]
0x180006047  movups  xmmword ptr [rsi+10h], xmm1
0x18000604b  movups  xmm0, xmmword ptr [r14+20h]
0x180006050  movups  xmmword ptr [rsi+20h], xmm0
0x180006054  movups  xmm1, xmmword ptr [r14+30h]
0x180006059  movups  xmmword ptr [rsi+30h], xmm1
0x18000605d  mov     rdx, [r14+30h]; Src
0x180006061  test    rdx, rdx
0x180006064  jz      short loc_180006080
0x180006066  mov     r8d, [r14+24h]; Size
0x18000606a  lea     rbx, [rsi+40h]
0x18000606e  mov     rcx, rbx; void *
0x180006071  call    memcpy_0
0x180006076  mov     [rsi+30h], rbx
0x18000607a  add     r15d, [r14+24h]
0x18000607e  xor     ebx, ebx
0x180006080  mov     rdx, [r14+38h]; Src
0x180006084  test    rdx, rdx
0x180006087  jz      short loc_1800060A7
0x180006089  mov     r8d, [r14+28h]; Size
0x18000608d  mov     ebx, r15d
0x180006090  add     rbx, rsi
0x180006093  mov     rcx, rbx; void *
0x180006096  call    memcpy_0
0x18000609b  mov     [rsi+38h], rbx
0x18000609f  xor     ebx, ebx
0x1800060a1  jmp     short loc_1800060A7
0x1800060a3  mov     [rdi+60h], rbx
0x1800060a7  mov     rax, [rbp+3Fh+var_70]
0x1800060ab  mov     [rax], rdi
0x1800060ae  jmp     short loc_1800060B5
0x1800060b0  mov     ebx, 57h ; 'W'
0x1800060b5  mov     eax, ebx
0x1800060b7  mov     rcx, [rbp+3Fh+var_48]
0x1800060bb  xor     rcx, rsp; StackCookie
0x1800060be  call    __security_check_cookie
0x1800060c3  add     rsp, 88h
0x1800060ca  pop     r15
0x1800060cc  pop     r14
0x1800060ce  pop     r13
0x1800060d0  pop     r12
0x1800060d2  pop     rdi
0x1800060d3  pop     rsi
0x1800060d4  pop     rbx
0x1800060d5  pop     rbp
0x1800060d6  retn
```
