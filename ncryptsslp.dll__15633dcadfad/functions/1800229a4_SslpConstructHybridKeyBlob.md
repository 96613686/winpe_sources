# SslpConstructHybridKeyBlob

- ea: `0x1800229a4`
- end: `0x180022c9b`
- name: `SslpConstructHybridKeyBlob`
- size: `759`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, unsigned int, _DWORD *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180022e04`

## callees

- `0x18000b654`
- `0x18002170c`
- `0x1800221fc`
- `0x1800229a4`
- `0x180023314`
- `0x1800233d0`
- `0x1800237a0`
- `0x180024fb0`
- `0x180025660`

## string_xrefs

- `0x180022a29`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180022b05`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180022be6`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180022c66`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`

## pseudocode

```c
__int64 __fastcall SslpConstructHybridKeyBlob(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        _DWORD *a6,
        unsigned int a7,
        unsigned int *a8)
{
  int v9; // r15d
  _DWORD *v11; // rdi
  int HybridPublicKeySizes; // ebx
  __int64 v13; // r9
  __int64 v15; // rcx
  char v16; // r13
  const wchar_t *v17; // r14
  const wchar_t *v18; // rax
  int v19; // r8d
  int v20; // r15d
  __int64 v21; // r9
  size_t v22; // r13
  unsigned int v23; // r12d
  __int64 v24; // r9
  __int64 v25; // rcx
  int HybridKeyConstituentKeyIndices; // eax
  unsigned int v27; // r14d
  char v28; // cl
  _BYTE *v29; // rdi
  unsigned int v30; // r15d
  unsigned int i; // esi
  void *v32; // [rsp+30h] [rbp-20h] BYREF
  size_t Size; // [rsp+38h] [rbp-18h] BYREF
  __int64 v34; // [rsp+40h] [rbp-10h] BYREF
  void *Src; // [rsp+48h] [rbp-8h] BYREF
  __int64 v36; // [rsp+90h] [rbp+40h] BYREF
  int v37; // [rsp+A0h] [rbp+50h]

  v37 = a3;
  v36 = 0;
  v9 = a2;
  v34 = 0;
  if ( !a1 || !a2 || !a4 || (v11 = a6) == 0 || !a7 || !a8 )
  {
    v24 = 675;
    goto LABEL_44;
  }
  HybridPublicKeySizes = SslpValidateConstituentKeys(a1, &v36, &v34);
  if ( HybridPublicKeySizes < 0 )
  {
    v13 = 685;
LABEL_9:
    DebugTraceError(
      (unsigned int)HybridPublicKeySizes,
      "status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c",
      v13);
    return (unsigned int)HybridPublicKeySizes;
  }
  v15 = *(unsigned __int16 *)(a1 + 8);
  if ( (_WORD)v15 == 4587 || (LOBYTE(v36) = 0, v16 = 0, (_WORD)v15 == 4589) )
  {
    v16 = 1;
    LOBYTE(v36) = 1;
  }
  v17 = L"MLKEMPUBLICBLOB";
  if ( *(_QWORD *)(v34 + 32) )
  {
    v18 = L"TLS_KEM_CIPHERTEXT";
    if ( !*(_DWORD *)(v34 + 40) )
      v18 = L"MLKEMPUBLICBLOB";
    v17 = v18;
  }
  LODWORD(Size) = 0;
  LODWORD(v34) = 0;
  HybridPublicKeySizes = SslpGetHybridPublicKeySizes(v15, v17, &Size, &v34);
  if ( HybridPublicKeySizes < 0 )
  {
    v13 = 713;
    goto LABEL_9;
  }
  LOBYTE(v19) = v16;
  Src = 0;
  LODWORD(v32) = 0;
  HybridPublicKeySizes = SslpGetRawEcdhKeyBuffer(v9, v37, v19, (unsigned int)&Src, (__int64)&v32);
  if ( HybridPublicKeySizes < 0 )
  {
    v13 = 727;
    goto LABEL_9;
  }
  v20 = (int)v32;
  if ( (_DWORD)v32 != (_DWORD)Size )
  {
    v21 = 734;
LABEL_23:
    DebugTraceError(2148073477LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", v21);
    return 2148073477LL;
  }
  v32 = 0;
  LODWORD(Size) = 0;
  HybridPublicKeySizes = SslpGetRawKemKeyBuffer(a4, a5, v17, &v32, &Size);
  if ( HybridPublicKeySizes < 0 )
  {
    v13 = 748;
    goto LABEL_9;
  }
  v22 = (unsigned int)Size;
  if ( (_DWORD)Size != (_DWORD)v34 )
  {
    v21 = 755;
    goto LABEL_23;
  }
  v23 = v20 + Size + 32;
  if ( a7 < v23 )
  {
    v24 = 763;
LABEL_44:
    DebugTraceError(2148073511LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", v24);
    return 2148073511LL;
  }
  memset(v11, 0, v23);
  *v11 = 1213418580;
  *((_WORD *)v11 + 2) = *(_WORD *)(a1 + 8);
  *((_QWORD *)v11 + 1) = L"SSLECCPUBLICBLOB";
  *((_QWORD *)v11 + 2) = v17;
  v11[6] = v20 + v22;
  v25 = *(unsigned __int16 *)(a1 + 8);
  LODWORD(v34) = 0;
  LODWORD(Size) = 0;
  HybridKeyConstituentKeyIndices = SslpGetHybridKeyConstituentKeyIndices(v25, &v34, &Size);
  v27 = HybridKeyConstituentKeyIndices;
  if ( HybridKeyConstituentKeyIndices < 0 )
  {
    DebugTraceError(
      (unsigned int)HybridKeyConstituentKeyIndices,
      "status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c",
      801);
    return v27;
  }
  v28 = v36;
  v29 = v11 + 8;
  v30 = v20 - (unsigned __int8)v36;
  for ( i = 0; i < 2; ++i )
  {
    if ( i == (_DWORD)v34 )
    {
      if ( v28 )
        *v29++ = 4;
      memmove(v29, Src, v30);
      v29 += v30;
    }
    else
    {
      if ( i != (_DWORD)Size )
        continue;
      memmove(v29, v32, v22);
      v29 += v22;
    }
    v28 = v36;
  }
  *a8 = v23;
  return v27;
}

```

## disassembly

```asm
0x1800229a4  mov     [rsp-38h+arg_8], rbx
0x1800229a9  mov     [rsp-38h+arg_10], r8d
0x1800229ae  push    rbp
0x1800229af  push    rsi
0x1800229b0  push    rdi
0x1800229b1  push    r12
0x1800229b3  push    r13
0x1800229b5  push    r14
0x1800229b7  push    r15
0x1800229b9  mov     rbp, rsp
0x1800229bc  sub     rsp, 50h
0x1800229c0  xor     r14d, r14d
0x1800229c3  mov     r12, r9
0x1800229c6  mov     [rbp+arg_0], r14
0x1800229ca  mov     r15, rdx
0x1800229cd  mov     [rbp+var_10], r14
0x1800229d1  mov     rsi, rcx
0x1800229d4  test    rcx, rcx
0x1800229d7  jz      loc_180022C60
0x1800229dd  test    rdx, rdx
0x1800229e0  jz      loc_180022C60
0x1800229e6  test    r9, r9
0x1800229e9  jz      loc_180022C60
0x1800229ef  mov     rdi, [rbp+arg_28]
0x1800229f3  test    rdi, rdi
0x1800229f6  jz      loc_180022C60
0x1800229fc  cmp     [rbp+arg_30], r14d
0x180022a00  jz      loc_180022C60
0x180022a06  cmp     [rbp+arg_38], r14
0x180022a0a  jz      loc_180022C60
0x180022a10  lea     r8, [rbp+var_10]
0x180022a14  lea     rdx, [rbp+arg_0]
0x180022a18  call    SslpValidateConstituentKeys
0x180022a1d  mov     ebx, eax
0x180022a1f  test    eax, eax
0x180022a21  jns     short loc_180022A45
0x180022a23  mov     r9d, 2ADh
0x180022a29  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022a30  mov     ecx, ebx
0x180022a32  lea     rdx, aStatus_0; "status"
0x180022a39  call    DebugTraceError
0x180022a3e  mov     eax, ebx
0x180022a40  jmp     loc_180022C83
0x180022a45  movzx   ecx, word ptr [rsi+8]
0x180022a49  mov     eax, 11EBh
0x180022a4e  cmp     cx, ax
0x180022a51  jz      short loc_180022A64
0x180022a53  mov     eax, 11EDh
0x180022a58  mov     byte ptr [rbp+arg_0], r14b
0x180022a5c  mov     r13b, r14b
0x180022a5f  cmp     cx, ax
0x180022a62  jnz     short loc_180022A6B
0x180022a64  mov     r13b, 1
0x180022a67  mov     byte ptr [rbp+arg_0], r13b
0x180022a6b  mov     rdx, [rbp+var_10]
0x180022a6f  lea     r14, aMlkempublicblo; "MLKEMPUBLICBLOB"
0x180022a76  xor     r8d, r8d
0x180022a79  cmp     [rdx+20h], r8
0x180022a7d  jz      short loc_180022A91
0x180022a7f  cmp     [rdx+28h], r8d
0x180022a83  lea     rax, aTlsKemCipherte; "TLS_KEM_CIPHERTEXT"
0x180022a8a  cmovz   rax, r14
0x180022a8e  mov     r14, rax
0x180022a91  mov     dword ptr [rbp+Size], r8d
0x180022a95  lea     r9, [rbp+var_10]
0x180022a99  mov     dword ptr [rbp+var_10], r8d
0x180022a9d  mov     rdx, r14
0x180022aa0  lea     r8, [rbp+Size]
0x180022aa4  call    SslpGetHybridPublicKeySizes
0x180022aa9  mov     ebx, eax
0x180022aab  test    eax, eax
0x180022aad  jns     short loc_180022ABA
0x180022aaf  mov     r9d, 2C9h
0x180022ab5  jmp     loc_180022A29
0x180022aba  mov     edx, [rbp+arg_10]
0x180022abd  lea     rax, [rbp+var_20]
0x180022ac1  lea     r9, [rbp+Src]
0x180022ac5  mov     [rsp+50h+var_30], rax
0x180022aca  mov     r8b, r13b
0x180022acd  mov     [rbp+Src], 0
0x180022ad5  mov     rcx, r15
0x180022ad8  mov     dword ptr [rbp+var_20], 0
0x180022adf  call    SslpGetRawEcdhKeyBuffer
0x180022ae4  mov     ebx, eax
0x180022ae6  test    eax, eax
0x180022ae8  jns     short loc_180022AF5
0x180022aea  mov     r9d, 2D7h
0x180022af0  jmp     loc_180022A29
0x180022af5  mov     r15d, dword ptr [rbp+var_20]
0x180022af9  cmp     r15d, dword ptr [rbp+Size]
0x180022afd  jz      short loc_180022B27
0x180022aff  mov     r9d, 2DEh
0x180022b05  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022b0c  mov     ecx, 80090005h
0x180022b11  lea     rdx, aStatus_0; "status"
0x180022b18  call    DebugTraceError
0x180022b1d  mov     eax, 80090005h
0x180022b22  jmp     loc_180022C83
0x180022b27  mov     edx, [rbp+arg_20]
0x180022b2a  lea     rax, [rbp+Size]
0x180022b2e  lea     r9, [rbp+var_20]
0x180022b32  mov     [rsp+50h+var_30], rax
0x180022b37  mov     r8, r14
0x180022b3a  mov     [rbp+var_20], 0
0x180022b42  mov     rcx, r12
0x180022b45  mov     dword ptr [rbp+Size], 0
0x180022b4c  call    SslpGetRawKemKeyBuffer
0x180022b51  mov     ebx, eax
0x180022b53  test    eax, eax
0x180022b55  jns     short loc_180022B62
0x180022b57  mov     r9d, 2ECh
0x180022b5d  jmp     loc_180022A29
0x180022b62  mov     r13d, dword ptr [rbp+Size]
0x180022b66  cmp     r13d, dword ptr [rbp+var_10]
0x180022b6a  jz      short loc_180022B74
0x180022b6c  mov     r9d, 2F3h
0x180022b72  jmp     short loc_180022B05
0x180022b74  lea     ebx, [r15+r13]
0x180022b78  lea     r12d, [rbx+20h]
0x180022b7c  cmp     [rbp+arg_30], r12d
0x180022b80  jnb     short loc_180022B8D
0x180022b82  mov     r9d, 2FBh
0x180022b88  jmp     loc_180022C66
0x180022b8d  mov     r8d, r12d; Size
0x180022b90  xor     edx, edx; Val
0x180022b92  mov     rcx, rdi; void *
0x180022b95  call    memset
0x180022b9a  mov     dword ptr [rdi], 48534C54h
0x180022ba0  lea     r8, [rbp+Size]
0x180022ba4  movzx   eax, word ptr [rsi+8]
0x180022ba8  lea     rdx, [rbp+var_10]
0x180022bac  mov     [rdi+4], ax
0x180022bb0  lea     rax, aSsleccpublicbl; "SSLECCPUBLICBLOB"
0x180022bb7  mov     [rdi+8], rax
0x180022bbb  mov     [rdi+10h], r14
0x180022bbf  mov     [rdi+18h], ebx
0x180022bc2  movzx   ecx, word ptr [rsi+8]
0x180022bc6  mov     dword ptr [rbp+var_10], 0
0x180022bcd  mov     dword ptr [rbp+Size], 0
0x180022bd4  call    SslpGetHybridKeyConstituentKeyIndices
0x180022bd9  mov     r14d, eax
0x180022bdc  test    eax, eax
0x180022bde  jns     short loc_180022C03
0x180022be0  mov     r9d, 321h
0x180022be6  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022bed  lea     rdx, aStatus_0; "status"
0x180022bf4  mov     ecx, eax
0x180022bf6  call    DebugTraceError
0x180022bfb  mov     eax, r14d
0x180022bfe  jmp     loc_180022C83
0x180022c03  movzx   ecx, byte ptr [rbp+arg_0]
0x180022c07  add     rdi, 20h ; ' '
0x180022c0b  sub     r15d, ecx
0x180022c0e  xor     esi, esi
0x180022c10  cmp     esi, dword ptr [rbp+var_10]
0x180022c13  jnz     short loc_180022C36
0x180022c15  test    cl, cl
0x180022c17  jz      short loc_180022C1F
0x180022c19  mov     byte ptr [rdi], 4
0x180022c1c  inc     rdi
0x180022c1f  mov     rdx, [rbp+Src]; Src
0x180022c23  mov     rcx, rdi; void *
0x180022c26  mov     r8d, r15d; Size
0x180022c29  mov     ebx, r15d
0x180022c2c  call    memmove
0x180022c31  add     rdi, rbx
0x180022c34  jmp     short loc_180022C4D
0x180022c36  cmp     esi, dword ptr [rbp+Size]
0x180022c39  jnz     short loc_180022C50
0x180022c3b  mov     rdx, [rbp+var_20]; Src
0x180022c3f  mov     r8, r13; Size
0x180022c42  mov     rcx, rdi; void *
0x180022c45  call    memmove
0x180022c4a  add     rdi, r13
0x180022c4d  mov     cl, byte ptr [rbp+arg_0]
0x180022c50  inc     esi
0x180022c52  cmp     esi, 2
0x180022c55  jb      short loc_180022C10
0x180022c57  mov     rax, [rbp+arg_38]
0x180022c5b  mov     [rax], r12d
0x180022c5e  jmp     short loc_180022BFB
0x180022c60  mov     r9d, 2A3h
0x180022c66  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022c6d  mov     ecx, 80090027h
0x180022c72  lea     rdx, aStatus_0; "status"
0x180022c79  call    DebugTraceError
0x180022c7e  mov     eax, 80090027h
0x180022c83  mov     rbx, [rsp+50h+arg_8]
0x180022c8b  add     rsp, 50h
0x180022c8f  pop     r15
0x180022c91  pop     r14
0x180022c93  pop     r13
0x180022c95  pop     r12
0x180022c97  pop     rdi
0x180022c98  pop     rsi
0x180022c99  pop     rbp
0x180022c9a  retn
```
