# DLNACommon::ConvertTimeStampIntoInt64(ushort const *,__int64 *)

- ea: `0x18002baec`
- end: `0x18002bdac`
- name: `?ConvertTimeStampIntoInt64@DLNACommon@@YAJPEBGPEA_J@Z`
- size: `704`
- prototype: `__int64 __fastcall(DLNACommon *__hidden this, const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002b708`
- `0x18002e0c0`

## callees

- `0x180011930`
- `0x180013044`
- `0x18002baec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002bb9e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002bb9e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bb4d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bb4d`

## pseudocode

```c
__int64 __fastcall DLNACommon::ConvertTimeStampIntoInt64(const WCHAR *this, unsigned __int16 *a2, __int64 *a3)
{
  unsigned int v5; // ebx
  size_t v6; // rdi
  const wchar_t *v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // r8
  float v13; // [rsp+40h] [rbp-40h] BYREF
  float v14; // [rsp+44h] [rbp-3Ch] BYREF
  float v15; // [rsp+48h] [rbp-38h] BYREF
  __int128 v16; // [rsp+50h] [rbp-30h] BYREF

  *(_QWORD *)a2 = 0;
  v5 = 0;
  if ( !this )
    return v5;
  if ( !*this )
    return v5;
  v6 = -1;
  if ( CompareStringOrdinal(this, -1, L"NOT_IMPLEMENTED", 15, 0) == 2 )
    return v5;
  v15 = 0.0;
  v16 = 0;
  v14 = 0.0;
  v13 = 0.0;
  do
    ++v6;
  while ( this[v6] );
  if ( ((*this - 43) & 0xFFFD) != 0 )
  {
    v7 = this;
  }
  else
  {
    v7 = this + 1;
    --v6;
  }
  if ( !wcschr(v7, 0x2Eu) )
  {
    if ( snwscanf_s(v7, v6, L"%hu:%hu:%hu", (char *)&v16 + 8, (char *)&v16 + 10, (char *)&v16 + 12) == 3
      || (WORD4(v16) = 0, snwscanf_s(v7, v6, L"%hu:%hu", (char *)&v16 + 10, (char *)&v16 + 12) == 2) )
    {
      v8 = WORD5(v16) + 60LL * WORD4(v16);
      v9 = WORD6(v16);
      goto LABEL_22;
    }
    return (unsigned int)-2147024809;
  }
  if ( snwscanf_s(v7, v6, L"%hu:%hu:%hu.%f/%f", (char *)&v16 + 8, (char *)&v16 + 10, (char *)&v16 + 12, &v15, &v14) == 5
    || (WORD4(v16) = 0, snwscanf_s(v7, v6, L"%hu:%hu.%f/%f", (char *)&v16 + 10, (char *)&v16 + 12, &v15, &v14) == 4) )
  {
    if ( v14 > v15 && v14 != 0.0 )
    {
      v10 = WORD6(v16);
      v9 = ((float)(v15 / v14) >= 0.5) + 60 * (WORD5(v16) + 60LL * WORD4(v16));
      goto LABEL_23;
    }
    return (unsigned int)-2147024809;
  }
  if ( snwscanf_s(v7, v6, L"%hu:%hu:%f", (char *)&v16 + 8, (char *)&v16 + 10, &v13) != 3 )
  {
    WORD4(v16) = 0;
    if ( snwscanf_s(v7, v6, L"%hu:%f", (char *)&v16 + 10, &v13) != 2 )
      return (unsigned int)-2147024809;
  }
  v8 = WORD5(v16) + 60LL * WORD4(v16);
  v9 = (unsigned int)(int)(v13 + 0.5);
LABEL_22:
  v10 = 60 * v8;
LABEL_23:
  v11 = v9 + v10;
  v5 = 0;
  *(_QWORD *)a2 = 10000000 * v11;
  if ( *this == 45 )
    *(_QWORD *)a2 = -10000000 * v11;
  return v5;
}

```

## disassembly

```asm
0x18002baec  mov     [rsp-28h+arg_10], rbx
0x18002baf1  push    rbp
0x18002baf2  push    rsi
0x18002baf3  push    rdi
0x18002baf4  push    r14
0x18002baf6  push    r15
0x18002baf8  mov     rbp, rsp
0x18002bafb  sub     rsp, 80h
0x18002bb02  movaps  [rsp+80h+var_10], xmm6
0x18002bb07  mov     rax, cs:__security_cookie
0x18002bb0e  xor     rax, rsp
0x18002bb11  mov     [rbp+var_20], rax
0x18002bb15  xor     r15d, r15d
0x18002bb18  mov     r14, rdx
0x18002bb1b  mov     [rdx], r15
0x18002bb1e  mov     rsi, rcx
0x18002bb21  mov     ebx, r15d
0x18002bb24  test    rcx, rcx
0x18002bb27  jz      loc_18002BD82
0x18002bb2d  cmp     r15w, [rcx]
0x18002bb31  jz      loc_18002BD82
0x18002bb37  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002bb3b  mov     [rsp+80h+bIgnoreCase], r15d; bIgnoreCase
0x18002bb40  mov     edx, edi; cchCount1
0x18002bb42  lea     r9d, [r15+0Fh]; cchCount2
0x18002bb46  lea     r8, aNotImplemented; "NOT_IMPLEMENTED"
0x18002bb4d  call    cs:__imp_CompareStringOrdinal
0x18002bb53  cmp     eax, 2
0x18002bb56  jz      loc_18002BD82
0x18002bb5c  xorps   xmm0, xmm0
0x18002bb5f  mov     [rbp+var_38], ebx
0x18002bb62  movups  [rbp+var_30], xmm0
0x18002bb66  mov     [rbp+var_3C], ebx
0x18002bb69  xorps   xmm6, xmm6
0x18002bb6c  mov     [rbp+var_40], ebx
0x18002bb6f  inc     rdi
0x18002bb72  cmp     [rsi+rdi*2], r15w
0x18002bb77  jnz     short loc_18002BB6F
0x18002bb79  movzx   eax, word ptr [rsi]
0x18002bb7c  mov     ecx, 0FFFDh
0x18002bb81  sub     ax, 2Bh ; '+'
0x18002bb85  test    cx, ax
0x18002bb88  jnz     short loc_18002BB93
0x18002bb8a  lea     rbx, [rsi+2]
0x18002bb8e  dec     rdi
0x18002bb91  jmp     short loc_18002BB96
0x18002bb93  mov     rbx, rsi
0x18002bb96  mov     edx, 2Eh ; '.'; Ch
0x18002bb9b  mov     rcx, rbx; Str
0x18002bb9e  call    cs:__imp_wcschr
0x18002bba4  lea     r9, [rbp+var_30+8]
0x18002bba8  mov     rdx, rdi; BufferCount
0x18002bbab  mov     rcx, rbx; Buffer
0x18002bbae  test    rax, rax
0x18002bbb1  jz      loc_18002BCFC
0x18002bbb7  lea     rax, [rbp+var_3C]
0x18002bbbb  mov     [rsp+80h+var_48], rax
0x18002bbc0  lea     r8, aHuHuHuFF; "%hu:%hu:%hu.%f/%f"
0x18002bbc7  lea     rax, [rbp+var_38]
0x18002bbcb  mov     [rsp+80h+var_50], rax
0x18002bbd0  lea     rax, [rbp+var_30+0Ch]
0x18002bbd4  mov     [rsp+80h+var_58], rax
0x18002bbd9  lea     rax, [rbp+var_30+0Ah]
0x18002bbdd  mov     qword ptr [rsp+80h+bIgnoreCase], rax
0x18002bbe2  call    _snwscanf_s
0x18002bbe7  cmp     eax, 5
0x18002bbea  jz      loc_18002BCAA
0x18002bbf0  lea     rax, [rbp+var_3C]
0x18002bbf4  mov     word ptr [rbp+var_30+8], r15w
0x18002bbf9  mov     [rsp+80h+var_50], rax
0x18002bbfe  lea     r9, [rbp+var_30+0Ah]
0x18002bc02  lea     rax, [rbp+var_38]
0x18002bc06  mov     rdx, rdi; BufferCount
0x18002bc09  mov     [rsp+80h+var_58], rax
0x18002bc0e  lea     r8, aHuHuFF; "%hu:%hu.%f/%f"
0x18002bc15  lea     rax, [rbp+var_30+0Ch]
0x18002bc19  mov     rcx, rbx; Buffer
0x18002bc1c  mov     qword ptr [rsp+80h+bIgnoreCase], rax
0x18002bc21  call    _snwscanf_s
0x18002bc26  cmp     eax, 4
0x18002bc29  jz      short loc_18002BCAA
0x18002bc2b  lea     rax, [rbp+var_40]
0x18002bc2f  mov     rdx, rdi; BufferCount
0x18002bc32  mov     [rsp+80h+var_58], rax
0x18002bc37  lea     r9, [rbp+var_30+8]
0x18002bc3b  lea     rax, [rbp+var_30+0Ah]
0x18002bc3f  mov     rcx, rbx; Buffer
0x18002bc42  lea     r8, aHuHuF; "%hu:%hu:%f"
0x18002bc49  mov     qword ptr [rsp+80h+bIgnoreCase], rax
0x18002bc4e  call    _snwscanf_s
0x18002bc53  cmp     eax, 3
0x18002bc56  jz      short loc_18002BC81
0x18002bc58  lea     rax, [rbp+var_40]
0x18002bc5c  mov     word ptr [rbp+var_30+8], r15w
0x18002bc61  lea     r9, [rbp+var_30+0Ah]
0x18002bc65  mov     qword ptr [rsp+80h+bIgnoreCase], rax
0x18002bc6a  lea     r8, aHuF; "%hu:%f"
0x18002bc71  mov     rdx, rdi; BufferCount
0x18002bc74  mov     rcx, rbx; Buffer
0x18002bc77  call    _snwscanf_s
0x18002bc7c  cmp     eax, 2
0x18002bc7f  jnz     short loc_18002BCF2
0x18002bc81  movzx   eax, word ptr [rbp+var_30+8]
0x18002bc85  movss   xmm0, [rbp+var_40]
0x18002bc8a  imul    rcx, rax, 3Ch ; '<'
0x18002bc8e  cvtps2pd xmm0, xmm0
0x18002bc91  movzx   eax, word ptr [rbp+var_30+0Ah]
0x18002bc95  add     rcx, rax
0x18002bc98  addsd   xmm0, cs:__real@3fe0000000000000
0x18002bca0  cvttsd2si rax, xmm0
0x18002bca5  jmp     loc_18002BD5B
0x18002bcaa  movss   xmm0, [rbp+var_3C]
0x18002bcaf  movss   xmm1, [rbp+var_38]
0x18002bcb4  comiss  xmm0, xmm1
0x18002bcb7  jbe     short loc_18002BCF2
0x18002bcb9  ucomiss xmm6, xmm0
0x18002bcbc  jp      short loc_18002BCC0
0x18002bcbe  jz      short loc_18002BCF2
0x18002bcc0  movzx   eax, word ptr [rbp+var_30+8]
0x18002bcc4  mov     rdx, r15
0x18002bcc7  movzx   r8d, word ptr [rbp+var_30+0Ch]
0x18002bccc  divss   xmm1, xmm0
0x18002bcd0  cvtps2pd xmm0, xmm1
0x18002bcd3  comisd  xmm0, cs:__real@3fe0000000000000
0x18002bcdb  setnb   dl
0x18002bcde  imul    rcx, rax, 3Ch ; '<'
0x18002bce2  movzx   eax, word ptr [rbp+var_30+0Ah]
0x18002bce6  add     rcx, rax
0x18002bce9  imul    rax, rcx, 3Ch ; '<'
0x18002bced  add     rax, rdx
0x18002bcf0  jmp     short loc_18002BD5F
0x18002bcf2  mov     ebx, 80070057h
0x18002bcf7  jmp     loc_18002BD82
0x18002bcfc  lea     rax, [rbp+var_30+0Ch]
0x18002bd00  mov     [rsp+80h+var_58], rax
0x18002bd05  lea     r8, aHuHuHu; "%hu:%hu:%hu"
0x18002bd0c  lea     rax, [rbp+var_30+0Ah]
0x18002bd10  mov     qword ptr [rsp+80h+bIgnoreCase], rax
0x18002bd15  call    _snwscanf_s
0x18002bd1a  cmp     eax, 3
0x18002bd1d  jz      short loc_18002BD48
0x18002bd1f  lea     rax, [rbp+var_30+0Ch]
0x18002bd23  mov     word ptr [rbp+var_30+8], r15w
0x18002bd28  lea     r9, [rbp+var_30+0Ah]
0x18002bd2c  mov     qword ptr [rsp+80h+bIgnoreCase], rax
0x18002bd31  lea     r8, aHuHu; "%hu:%hu"
0x18002bd38  mov     rdx, rdi; BufferCount
0x18002bd3b  mov     rcx, rbx; Buffer
0x18002bd3e  call    _snwscanf_s
0x18002bd43  cmp     eax, 2
0x18002bd46  jnz     short loc_18002BCF2
0x18002bd48  movzx   eax, word ptr [rbp+var_30+8]
0x18002bd4c  imul    rcx, rax, 3Ch ; '<'
0x18002bd50  movzx   eax, word ptr [rbp+var_30+0Ah]
0x18002bd54  add     rcx, rax
0x18002bd57  movzx   eax, word ptr [rbp+var_30+0Ch]
0x18002bd5b  imul    r8, rcx, 3Ch ; '<'
0x18002bd5f  add     r8, rax
0x18002bd62  mov     ecx, 2Dh ; '-'
0x18002bd67  imul    rax, r8, 989680h
0x18002bd6e  mov     r9, r14
0x18002bd71  mov     ebx, r15d
0x18002bd74  mov     [r14], rax
0x18002bd77  cmp     cx, [rsi]
0x18002bd7a  jnz     short loc_18002BD82
0x18002bd7c  neg     rax
0x18002bd7f  mov     [r14], rax
0x18002bd82  mov     eax, ebx
0x18002bd84  mov     rcx, [rbp+var_20]
0x18002bd88  xor     rcx, rsp; StackCookie
0x18002bd8b  call    __security_check_cookie
0x18002bd90  mov     rbx, [rsp+80h+arg_10]
0x18002bd98  movaps  xmm6, [rsp+80h+var_10]
0x18002bd9d  add     rsp, 80h
0x18002bda4  pop     r15
0x18002bda6  pop     r14
0x18002bda8  pop     rdi
0x18002bda9  pop     rsi
0x18002bdaa  pop     rbp
0x18002bdab  retn
```
