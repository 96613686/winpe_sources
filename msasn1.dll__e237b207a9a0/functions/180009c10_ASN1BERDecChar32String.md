# ASN1BERDecChar32String

- ea: `0x180009c10`
- end: `0x180009e5b`
- name: `ASN1BERDecChar32String`
- size: `587`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180009c10`

## callees

- `0x180001b10`
- `0x180001b30`
- `0x1800020a0`
- `0x180002200`
- `0x180003a60`
- `0x180004310`
- `0x180004340`
- `0x180004760`
- `0x1800062ec`
- `0x180009c10`
- `0x18000aadd`

## pseudocode

```c
__int64 __fastcall ASN1BERDecChar32String(__int64 a1, __int64 a2, unsigned int *a3)
{
  int v5; // r8d
  unsigned int v6; // edx
  __int64 v7; // rbx
  unsigned __int64 v8; // r8
  unsigned int v9; // ecx
  __int64 v10; // rax
  const void *v11; // rdx
  __int64 v12; // r8
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  int v20; // [rsp+30h] [rbp-38h] BYREF
  int v21; // [rsp+34h] [rbp-34h] BYREF
  __int64 v22; // [rsp+38h] [rbp-30h] BYREF
  __int64 v23; // [rsp+40h] [rbp-28h] BYREF
  __int64 v24; // [rsp+48h] [rbp-20h] BYREF
  const void *Src_4; // [rsp+50h] [rbp-18h]
  unsigned int v26; // [rsp+B8h] [rbp+50h] BYREF

  LODWORD(Src_4) = 0;
  v24 = 0;
  v20 = 0;
  v26 = 0;
  v21 = 0;
  v23 = 0;
  v22 = 0;
  if ( !(unsigned int)ASN1BERDecTag(a1, a2, &v20) || !(unsigned int)ASN1BERDecLength(a1, &v26, &v21) )
    return 0;
  if ( !v20 )
  {
    v14 = v26 >> 2;
    *a3 = v14;
    if ( (_DWORD)v14 )
    {
      v15 = DecMemAlloc(a1, (unsigned int)(4 * v14 + 4));
      *((_QWORD *)a3 + 1) = v15;
      if ( !v15 )
        return 0;
      LODWORD(v16) = 0;
      do
      {
        v17 = (unsigned int)v16;
        v16 = (unsigned int)(v16 + 1);
        *(_DWORD *)(*((_QWORD *)a3 + 1) + 4 * v17) = *(unsigned __int8 *)(*(_QWORD *)(a1 + 40) + 3LL)
                                                   | ((*(unsigned __int8 *)(*(_QWORD *)(a1 + 40) + 2LL)
                                                     | ((*(unsigned __int8 *)(*(_QWORD *)(a1 + 40) + 1LL)
                                                       | (**(unsigned __int8 **)(a1 + 40) << 8)) << 8)) << 8);
        *(_QWORD *)(a1 + 40) += 4LL;
      }
      while ( (unsigned int)v16 < (unsigned int)v14 );
      *(_DWORD *)(*((_QWORD *)a3 + 1) + 4 * v14) = 0;
      if ( (g_dwDecodingRules & 2) == 0 )
      {
        do
        {
          v18 = (unsigned int)(v14 - 1);
          if ( *(_DWORD *)(*((_QWORD *)a3 + 1) + 4 * v18) )
            break;
          LODWORD(v14) = v14 - 1;
        }
        while ( (_DWORD)v18 );
        while ( (_DWORD)v14 )
        {
          v19 = *((_QWORD *)a3 + 1);
          v14 = (unsigned int)(v14 - 1);
          if ( !*(_DWORD *)(v19 + 4 * v14) )
          {
            DecMemFreeFn(a1, v19, v16);
            *((_QWORD *)a3 + 1) = 0;
            *a3 = 0;
            ASN1DecSetError(a1, 0xFFFFFC0B);
            return 0;
          }
        }
      }
    }
    else
    {
      *((_QWORD *)a3 + 1) = 0;
    }
    return 1;
  }
  v5 = v21;
  v6 = v26;
  *a3 = 0;
  *((_QWORD *)a3 + 1) = 0;
  if ( !(unsigned int)BERDecConstructed(a1, v6, v5, (unsigned int)&v23, (__int64)&v22) )
    return 0;
  v7 = v23;
  while ( (unsigned int)ASN1BERDecNotEndOfContents(v7, v22) )
  {
    if ( !(unsigned int)ASN1BERDecChar32String(v7, 4, &v24) )
      return 0;
    if ( (_DWORD)v24 )
    {
      v9 = *a3 + v24;
      if ( v9 < *a3 || v9 + 1 < v9 || (v8 = 4LL * (v9 + 1), v8 > 0xFFFFFFFF) )
      {
        v11 = Src_4;
LABEL_14:
        DecMemFreeFn(a1, v11, v8);
        return 0;
      }
      v10 = DecMemReAlloc(v7, *((_QWORD *)a3 + 1));
      v11 = Src_4;
      *((_QWORD *)a3 + 1) = v10;
      if ( !v10 )
        goto LABEL_14;
      memcpy_0((void *)(v10 + 4LL * *a3), v11, 4LL * (unsigned int)v24);
      *a3 += v24;
      *(_DWORD *)(*((_QWORD *)a3 + 1) + 4LL * *a3) = 0;
      DecMemFreeFn(a1, Src_4, v12);
      Src_4 = 0;
    }
  }
  return ASN1BERDecEndOfContents(a1, v7, v22);
}

```

## disassembly

```asm
0x180009c10  push    rbp
0x180009c12  push    rbx
0x180009c13  push    rsi
0x180009c14  push    rdi
0x180009c15  push    r14
0x180009c17  push    r15
0x180009c19  mov     rbp, rsp
0x180009c1c  sub     rsp, 68h
0x180009c20  xor     r15d, r15d
0x180009c23  xor     eax, eax
0x180009c25  mov     rdi, r8
0x180009c28  mov     qword ptr [rbp+Src], rax
0x180009c2c  lea     r8, [rbp+var_38]
0x180009c30  mov     [rbp-20h], rax
0x180009c34  mov     rsi, rcx
0x180009c37  mov     [rbp+var_38], r15d
0x180009c3b  mov     [rbp+arg_18], r15d
0x180009c3f  mov     [rbp+var_34], r15d
0x180009c43  mov     [rbp+var_28], r15
0x180009c47  mov     [rbp+var_30], r15
0x180009c4b  call    ASN1BERDecTag
0x180009c50  test    eax, eax
0x180009c52  jz      loc_180009D5E
0x180009c58  lea     r8, [rbp+var_34]
0x180009c5c  mov     rcx, rsi
0x180009c5f  lea     rdx, [rbp+arg_18]
0x180009c63  call    ASN1BERDecLength
0x180009c68  test    eax, eax
0x180009c6a  jz      loc_180009D5E
0x180009c70  cmp     [rbp+var_38], r15d
0x180009c74  jz      loc_180009D84
0x180009c7a  mov     r8d, [rbp+var_34]
0x180009c7e  lea     rax, [rbp+var_30]
0x180009c82  mov     edx, [rbp+arg_18]
0x180009c85  lea     r9, [rbp+var_28]
0x180009c89  mov     rcx, rsi
0x180009c8c  mov     [rsp+68h+var_48], rax
0x180009c91  mov     [rdi], r15d
0x180009c94  mov     [rdi+8], r15
0x180009c98  call    _BERDecConstructed
0x180009c9d  test    eax, eax
0x180009c9f  jz      loc_180009D5E
0x180009ca5  mov     rbx, [rbp+var_28]
0x180009ca9  mov     r14d, 0FFFFFFFFh
0x180009caf  mov     rdx, [rbp+var_30]
0x180009cb3  mov     rcx, rbx
0x180009cb6  call    ASN1BERDecNotEndOfContents
0x180009cbb  test    eax, eax
0x180009cbd  jz      loc_180009D73
0x180009cc3  lea     r8, [rbp+var_20]
0x180009cc7  mov     edx, 4
0x180009ccc  mov     rcx, rbx
0x180009ccf  call    ASN1BERDecChar32String
0x180009cd4  test    eax, eax
0x180009cd6  jz      loc_180009D5E
0x180009cdc  mov     ecx, [rbp+var_20]
0x180009cdf  test    ecx, ecx
0x180009ce1  jz      short loc_180009CAF
0x180009ce3  add     ecx, [rdi]
0x180009ce5  cmp     ecx, [rdi]
0x180009ce7  jb      loc_180009D6D
0x180009ced  lea     eax, [rcx+1]
0x180009cf0  mov     edx, r14d
0x180009cf3  cmp     eax, ecx
0x180009cf5  cmovnb  edx, eax
0x180009cf8  jb      short loc_180009D6D
0x180009cfa  mov     r8d, edx
0x180009cfd  shl     r8, 2
0x180009d01  cmp     r8, r14
0x180009d04  ja      short loc_180009D6D
0x180009d06  mov     rdx, [rdi+8]
0x180009d0a  mov     rcx, rbx
0x180009d0d  call    DecMemReAlloc
0x180009d12  mov     rdx, qword ptr [rbp+Src+4]; Src
0x180009d16  mov     [rdi+8], rax
0x180009d1a  test    rax, rax
0x180009d1d  jz      short loc_180009D56
0x180009d1f  mov     ecx, [rdi]
0x180009d21  mov     r8d, [rbp+var_20]
0x180009d25  shl     r8, 2; Size
0x180009d29  lea     rcx, [rax+rcx*4]; void *
0x180009d2d  call    memcpy_0
0x180009d32  mov     eax, [rbp+var_20]
0x180009d35  add     [rdi], eax
0x180009d37  mov     ecx, [rdi]
0x180009d39  mov     rax, [rdi+8]
0x180009d3d  mov     [rax+rcx*4], r15d
0x180009d41  mov     rcx, rsi
0x180009d44  mov     rdx, qword ptr [rbp+Src+4]
0x180009d48  call    DecMemFreeFn
0x180009d4d  mov     qword ptr [rbp+Src+4], r15
0x180009d51  jmp     loc_180009CAF
0x180009d56  mov     rcx, rsi
0x180009d59  call    DecMemFreeFn
0x180009d5e  xor     eax, eax
0x180009d60  add     rsp, 68h
0x180009d64  pop     r15
0x180009d66  pop     r14
0x180009d68  pop     rdi
0x180009d69  pop     rsi
0x180009d6a  pop     rbx
0x180009d6b  pop     rbp
0x180009d6c  retn
0x180009d6d  mov     rdx, qword ptr [rbp+Src+4]
0x180009d71  jmp     short loc_180009D56
0x180009d73  mov     r8, [rbp+var_30]
0x180009d77  mov     rdx, rbx
0x180009d7a  mov     rcx, rsi
0x180009d7d  call    ASN1BERDecEndOfContents
0x180009d82  jmp     short loc_180009D60
0x180009d84  mov     ebx, [rbp+arg_18]
0x180009d87  shr     ebx, 2
0x180009d8a  mov     [rdi], ebx
0x180009d8c  test    ebx, ebx
0x180009d8e  jz      loc_180009E4D
0x180009d94  lea     edx, ds:4[rbx*4]
0x180009d9b  mov     rcx, rsi
0x180009d9e  call    DecMemAlloc
0x180009da3  mov     [rdi+8], rax
0x180009da7  test    rax, rax
0x180009daa  jz      short loc_180009D5E
0x180009dac  mov     r8d, r15d
0x180009daf  test    ebx, ebx
0x180009db1  jz      short loc_180009DEC
0x180009db3  mov     rcx, [rsi+28h]
0x180009db7  movzx   eax, byte ptr [rcx+1]
0x180009dbb  movzx   edx, byte ptr [rcx]
0x180009dbe  shl     edx, 8
0x180009dc1  or      edx, eax
0x180009dc3  movzx   eax, byte ptr [rcx+2]
0x180009dc7  shl     edx, 8
0x180009dca  or      edx, eax
0x180009dcc  movzx   eax, byte ptr [rcx+3]
0x180009dd0  shl     edx, 8
0x180009dd3  or      edx, eax
0x180009dd5  mov     ecx, r8d
0x180009dd8  mov     rax, [rdi+8]
0x180009ddc  inc     r8d
0x180009ddf  mov     [rax+rcx*4], edx
0x180009de2  add     qword ptr [rsi+28h], 4
0x180009de7  cmp     r8d, ebx
0x180009dea  jb      short loc_180009DB3
0x180009dec  mov     rax, [rdi+8]
0x180009df0  mov     [rax+rbx*4], r15d
0x180009df4  mov     eax, cs:g_dwDecodingRules
0x180009dfa  test    al, 2
0x180009dfc  jnz     short loc_180009E51
0x180009dfe  test    ebx, ebx
0x180009e00  jz      short loc_180009E15
0x180009e02  mov     rdx, [rdi+8]
0x180009e06  lea     ecx, [rbx-1]
0x180009e09  cmp     [rdx+rcx*4], r15d
0x180009e0d  jnz     short loc_180009E15
0x180009e0f  mov     ebx, ecx
0x180009e11  test    ecx, ecx
0x180009e13  jnz     short loc_180009E06
0x180009e15  mov     r14d, 0FFFFFFFFh
0x180009e1b  test    ebx, ebx
0x180009e1d  jz      short loc_180009E51
0x180009e1f  mov     rdx, [rdi+8]
0x180009e23  add     ebx, r14d
0x180009e26  cmp     [rdx+rbx*4], r15d
0x180009e2a  jnz     short loc_180009E1B
0x180009e2c  mov     rcx, rsi
0x180009e2f  call    DecMemFreeFn
0x180009e34  mov     [rdi+8], r15
0x180009e38  mov     edx, 0FFFFFC0Bh
0x180009e3d  mov     rcx, rsi
0x180009e40  mov     [rdi], r15d
0x180009e43  call    ASN1DecSetError
0x180009e48  jmp     loc_180009D5E
0x180009e4d  mov     [rdi+8], r15
0x180009e51  mov     eax, 1
0x180009e56  jmp     loc_180009D60
```
