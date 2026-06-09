# _EscapeXML(ushort const *,ushort *,unsigned __int64)

- ea: `0x18000cd38`
- end: `0x18000cfb3`
- name: `?_EscapeXML@@YA_KPEBGPEAG_K@Z`
- size: `635`
- prototype: `unsigned __int64(const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000bfcc`

## callees

- `0x1800064b4`
- `0x18000cbfc`
- `0x18000ccfc`
- `0x18000cd38`

## pseudocode

```c
__int64 __fastcall _EscapeXML(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  const unsigned __int16 *v3; // r14
  unsigned __int16 v4; // r8
  unsigned __int16 *v5; // rdi
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rsi
  unsigned __int16 v8; // bp
  char v9; // r12
  char v10; // cl
  unsigned __int64 v11; // rax
  unsigned __int16 v12; // cx
  unsigned __int64 v13; // rax
  __int16 v14; // ax
  unsigned __int64 v15; // rax

  v3 = a1;
  if ( !a2 )
    return -2147467261;
  v4 = *a1;
  v5 = a2;
  v6 = 512;
  v7 = 0;
  v8 = 0;
  v9 = 1;
  if ( !*a1 )
    goto LABEL_46;
  while ( 1 )
  {
    if ( v4 == 38 )
    {
      if ( v6 <= 6 )
        break;
      StringCchCopyW(v5, v6, aAmp);
      v5 += 5;
      v6 -= 5LL;
    }
    else if ( v4 == 60 || v4 == 62 )
    {
      if ( v6 <= 4 )
      {
        v9 = 0;
      }
      else
      {
        *v5 = 38;
        v14 = 108;
        if ( *v3 != 60 )
          v14 = 103;
        v5[1] = v14;
        *((_DWORD *)v5 + 1) = 3866740;
        v5 += 4;
        v6 -= 4LL;
      }
    }
    else if ( (unsigned __int16)(v4 + 10240) > 0x3FFu )
    {
      if ( !v8 )
        goto LABEL_23;
      if ( (unsigned __int16)(v4 + 9216) > 0x3FFu )
      {
        if ( v6 <= 8 )
          break;
        v11 = _CopyNCR(v8, v5, v6);
        v7 = v11;
        if ( v11 >= v6 )
          goto LABEL_46;
        v10 = 0;
        v6 -= v11;
      }
      else
      {
        if ( v6 <= 0xA )
          break;
        StringCchPrintfW(v5, v6, L"&#x%06X;", (v8 << 10) - 56613888 + (unsigned int)v4);
        v7 = -1;
        do
          ++v7;
        while ( v5[v7] );
        if ( v7 >= v6 )
          goto LABEL_46;
        v6 -= v7;
        v10 = 1;
      }
      v5 += v7;
      v8 = 0;
      if ( !v10 )
      {
LABEL_23:
        v12 = *v3;
        if ( (unsigned __int16)(*v3 - 32) > 0x5Eu )
        {
          if ( v6 <= 8 )
            break;
          v13 = _CopyNCR(v12, v5, v6);
          v7 = v13;
          if ( v13 >= v6 )
            goto LABEL_46;
          v5 += v13;
          v6 -= v13;
        }
        else
        {
          if ( v6 <= 1 )
            break;
          *v5++ = v12;
          --v6;
        }
      }
    }
    else
    {
      if ( v8 )
      {
        if ( v6 < 8 )
          break;
        v7 += _CopyNCR(v8, v5, v6);
        if ( v7 >= v6 )
          goto LABEL_46;
        v5 += v7;
        v6 -= v7;
      }
      v8 = *v3;
    }
    if ( !v9 )
      break;
    v4 = *++v3;
    if ( !*v3 )
    {
      if ( v8 )
      {
        if ( (unsigned __int16)(v8 - 32) > 0x5Eu )
        {
          if ( v6 > 8 )
          {
            v15 = _CopyNCR(v8, v5, v6);
            if ( v15 >= v6 )
              goto LABEL_46;
            v5 += v15;
            v6 -= v15;
          }
        }
        else if ( v6 > 1 )
        {
          *v5++ = v8;
          --v6;
        }
      }
      break;
    }
  }
  if ( v6 )
LABEL_46:
    *v5 = 0;
  return v5 - a2;
}

```

## disassembly

```asm
0x18000cd38  push    rbx
0x18000cd3a  push    rbp
0x18000cd3b  push    rsi
0x18000cd3c  push    rdi
0x18000cd3d  push    r12
0x18000cd3f  push    r13
0x18000cd41  push    r14
0x18000cd43  push    r15
0x18000cd45  sub     rsp, 28h
0x18000cd49  xor     r13d, r13d
0x18000cd4c  mov     r15, rdx
0x18000cd4f  mov     r14, rcx
0x18000cd52  test    rdx, rdx
0x18000cd55  jz      loc_18000CF9B
0x18000cd5b  movzx   r8d, word ptr [rcx]
0x18000cd5f  mov     rdi, rdx
0x18000cd62  mov     ebx, 200h
0x18000cd67  mov     esi, r13d
0x18000cd6a  mov     ebp, r13d
0x18000cd6d  mov     r12b, 1
0x18000cd70  test    r8w, r8w
0x18000cd74  jz      loc_18000CF8C
0x18000cd7a  lea     eax, [r13+26h]
0x18000cd7e  mov     edx, 3FFh
0x18000cd83  cmp     r8w, ax
0x18000cd87  jz      loc_18000CF06
0x18000cd8d  cmp     r8w, 3Ch ; '<'
0x18000cd92  jz      loc_18000CED2
0x18000cd98  cmp     r8w, 3Eh ; '>'
0x18000cd9d  jz      loc_18000CED2
0x18000cda3  mov     eax, 2800h
0x18000cda8  add     eax, r8d
0x18000cdab  cmp     ax, dx
0x18000cdae  ja      short loc_18000CDE9
0x18000cdb0  test    bp, bp
0x18000cdb3  jz      short loc_18000CDE0
0x18000cdb5  cmp     rbx, 8
0x18000cdb9  jb      loc_18000CF87
0x18000cdbf  mov     r8, rbx; unsigned __int64
0x18000cdc2  mov     rdx, rdi; unsigned __int16 *
0x18000cdc5  movzx   ecx, bp; unsigned __int16
0x18000cdc8  call    ?_CopyNCR@@YA_KGPEAG_K@Z; _CopyNCR(ushort,ushort *,unsigned __int64)
0x18000cdcd  add     rsi, rax
0x18000cdd0  cmp     rsi, rbx
0x18000cdd3  jnb     loc_18000CF8C
0x18000cdd9  lea     rdi, [rdi+rsi*2]
0x18000cddd  sub     rbx, rsi
0x18000cde0  movzx   ebp, word ptr [r14]
0x18000cde4  jmp     loc_18000CF26
0x18000cde9  test    bp, bp
0x18000cdec  jz      loc_18000CE85
0x18000cdf2  mov     eax, 2400h
0x18000cdf7  add     eax, r8d
0x18000cdfa  cmp     ax, dx
0x18000cdfd  ja      short loc_18000CE4C
0x18000cdff  cmp     rbx, 0Ah
0x18000ce03  jbe     loc_18000CF87
0x18000ce09  movzx   r9d, r8w
0x18000ce0d  mov     rdx, rbx; unsigned __int64
0x18000ce10  movzx   ecx, bp
0x18000ce13  lea     r8, aX06x; "&#x%06X;"
0x18000ce1a  shl     ecx, 0Ah
0x18000ce1d  add     ecx, 0FCA02400h
0x18000ce23  add     r9d, ecx
0x18000ce26  mov     rcx, rdi; unsigned __int16 *
0x18000ce29  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ce2e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000ce32  inc     rsi
0x18000ce35  cmp     [rdi+rsi*2], r13w
0x18000ce3a  jnz     short loc_18000CE32
0x18000ce3c  cmp     rsi, rbx
0x18000ce3f  jnb     loc_18000CF8C
0x18000ce45  sub     rbx, rsi
0x18000ce48  mov     cl, 1
0x18000ce4a  jmp     short loc_18000CE76
0x18000ce4c  cmp     rbx, 8
0x18000ce50  jbe     loc_18000CF87
0x18000ce56  mov     r8, rbx; unsigned __int64
0x18000ce59  mov     rdx, rdi; unsigned __int16 *
0x18000ce5c  movzx   ecx, bp; unsigned __int16
0x18000ce5f  call    ?_CopyNCR@@YA_KGPEAG_K@Z; _CopyNCR(ushort,ushort *,unsigned __int64)
0x18000ce64  mov     rsi, rax
0x18000ce67  cmp     rax, rbx
0x18000ce6a  jnb     loc_18000CF8C
0x18000ce70  mov     cl, r13b
0x18000ce73  sub     rbx, rax
0x18000ce76  lea     rdi, [rdi+rsi*2]
0x18000ce7a  mov     ebp, r13d
0x18000ce7d  test    cl, cl
0x18000ce7f  jnz     loc_18000CF26
0x18000ce85  movzx   ecx, word ptr [r14]; unsigned __int16
0x18000ce89  lea     eax, [rcx-20h]
0x18000ce8c  cmp     ax, 5Eh ; '^'
0x18000ce90  ja      short loc_18000CEA8
0x18000ce92  cmp     rbx, 1
0x18000ce96  jbe     loc_18000CF87
0x18000ce9c  mov     [rdi], cx
0x18000ce9f  add     rdi, 2
0x18000cea3  dec     rbx
0x18000cea6  jmp     short loc_18000CF26
0x18000cea8  cmp     rbx, 8
0x18000ceac  jbe     loc_18000CF87
0x18000ceb2  mov     r8, rbx; unsigned __int64
0x18000ceb5  mov     rdx, rdi; unsigned __int16 *
0x18000ceb8  call    ?_CopyNCR@@YA_KGPEAG_K@Z; _CopyNCR(ushort,ushort *,unsigned __int64)
0x18000cebd  mov     rsi, rax
0x18000cec0  cmp     rax, rbx
0x18000cec3  jnb     loc_18000CF8C
0x18000cec9  lea     rdi, [rdi+rax*2]
0x18000cecd  sub     rbx, rax
0x18000ced0  jmp     short loc_18000CF26
0x18000ced2  cmp     rbx, 4
0x18000ced6  jbe     short loc_18000CF01
0x18000ced8  mov     [rdi], ax
0x18000cedb  mov     eax, 6Ch ; 'l'
0x18000cee0  cmp     word ptr [r14], 3Ch ; '<'
0x18000cee5  lea     ecx, [rax-5]
0x18000cee8  cmovnz  ax, cx
0x18000ceec  mov     [rdi+2], ax
0x18000cef0  mov     dword ptr [rdi+4], 3B0074h
0x18000cef7  add     rdi, 8
0x18000cefb  sub     rbx, 4
0x18000ceff  jmp     short loc_18000CF26
0x18000cf01  mov     r12b, r13b
0x18000cf04  jmp     short loc_18000CF2B
0x18000cf06  cmp     rbx, 6
0x18000cf0a  jbe     short loc_18000CF87
0x18000cf0c  lea     r8, aAmp; "&amp;"
0x18000cf13  mov     rdx, rbx; unsigned __int64
0x18000cf16  mov     rcx, rdi; unsigned __int16 *
0x18000cf19  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cf1e  add     rdi, 0Ah
0x18000cf22  sub     rbx, 5
0x18000cf26  mov     eax, 26h ; '&'
0x18000cf2b  test    r12b, r12b
0x18000cf2e  jz      short loc_18000CF87
0x18000cf30  add     r14, 2
0x18000cf34  mov     edx, 3FFh
0x18000cf39  movzx   r8d, word ptr [r14]
0x18000cf3d  test    r8w, r8w
0x18000cf41  jnz     loc_18000CD83
0x18000cf47  test    bp, bp
0x18000cf4a  jz      short loc_18000CF87
0x18000cf4c  lea     eax, [rbp-20h]
0x18000cf4f  cmp     ax, 5Eh ; '^'
0x18000cf53  ja      short loc_18000CF67
0x18000cf55  cmp     rbx, 1
0x18000cf59  jbe     short loc_18000CF87
0x18000cf5b  mov     [rdi], bp
0x18000cf5e  add     rdi, 2
0x18000cf62  dec     rbx
0x18000cf65  jmp     short loc_18000CF87
0x18000cf67  cmp     rbx, 8
0x18000cf6b  jbe     short loc_18000CF87
0x18000cf6d  mov     r8, rbx; unsigned __int64
0x18000cf70  mov     rdx, rdi; unsigned __int16 *
0x18000cf73  movzx   ecx, bp; unsigned __int16
0x18000cf76  call    ?_CopyNCR@@YA_KGPEAG_K@Z; _CopyNCR(ushort,ushort *,unsigned __int64)
0x18000cf7b  cmp     rax, rbx
0x18000cf7e  jnb     short loc_18000CF8C
0x18000cf80  lea     rdi, [rdi+rax*2]
0x18000cf84  sub     rbx, rax
0x18000cf87  test    rbx, rbx
0x18000cf8a  jz      short loc_18000CF90
0x18000cf8c  mov     [rdi], r13w
0x18000cf90  sub     rdi, r15
0x18000cf93  sar     rdi, 1
0x18000cf96  mov     rax, rdi
0x18000cf99  jmp     short loc_18000CFA2
0x18000cf9b  mov     rax, 0FFFFFFFF80004003h
0x18000cfa2  add     rsp, 28h
0x18000cfa6  pop     r15
0x18000cfa8  pop     r14
0x18000cfaa  pop     r13
0x18000cfac  pop     r12
0x18000cfae  pop     rdi
0x18000cfaf  pop     rsi
0x18000cfb0  pop     rbp
0x18000cfb1  pop     rbx
0x18000cfb2  retn
```
