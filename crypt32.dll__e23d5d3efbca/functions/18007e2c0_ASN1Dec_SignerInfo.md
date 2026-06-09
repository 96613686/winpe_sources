# ASN1Dec_SignerInfo

- ea: `0x18007e2c0`
- end: `0x18007e5bb`
- name: `ASN1Dec_SignerInfo`
- size: `763`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18010c6f0`

## callees

- `0x18007e2c0`
- `0x18007e5d0`

## import_xrefs

- `MSASN1!ASN1BERDecOctetString` at `0x18007e53d`
- `MSASN1!ASN1BERDecOctetString` at `0x18011b8ae`
- `MSASN1!ASN1BERDecOctetString` at `0x18007e53d`
- `MSASN1!ASN1BERDecOctetString` at `0x18011b8ae`
- `MSASN1!ASN1BERDecObjectIdentifier2` at `0x18007e407`
- `MSASN1!ASN1BERDecObjectIdentifier2` at `0x18007e4d4`
- `MSASN1!ASN1BERDecObjectIdentifier2` at `0x18007e407`
- `MSASN1!ASN1BERDecObjectIdentifier2` at `0x18007e4d4`
- `MSASN1!ASN1BERDecOpenType` at `0x18007e37d`
- `MSASN1!ASN1BERDecOpenType` at `0x18007e432`
- `MSASN1!ASN1BERDecOpenType` at `0x18007e506`
- `MSASN1!ASN1BERDecOpenType` at `0x18007e37d`
- `MSASN1!ASN1BERDecOpenType` at `0x18007e432`
- `MSASN1!ASN1BERDecOpenType` at `0x18007e506`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007e3a7`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007e44b`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007e51f`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007e589`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007e3a7`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007e44b`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007e51f`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007e589`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007e33d`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007e419`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007e461`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007e4ea`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007e553`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007e33d`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007e419`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007e461`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007e4ea`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007e553`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007e2ff`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007e36b`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007e3e9`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007e4b0`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007e2ff`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007e36b`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007e3e9`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007e4b0`
- `MSASN1!ASN1DecSetError` at `0x18007e5b0`
- `MSASN1!ASN1DecSetError` at `0x18007e5b0`
- `MSASN1!ASN1BERDecS32Val` at `0x18007e320`
- `MSASN1!ASN1BERDecS32Val` at `0x18007e320`
- `MSASN1!ASN1BERDecSXVal` at `0x18007e392`
- `MSASN1!ASN1BERDecSXVal` at `0x18007e392`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_SignerInfo(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rcx
  __int64 v6; // rdi
  int v7; // eax
  __int64 v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // [rsp+20h] [rbp-20h] BYREF
  __int64 v18; // [rsp+28h] [rbp-18h] BYREF
  __int64 v19; // [rsp+30h] [rbp-10h] BYREF
  __int64 v20; // [rsp+38h] [rbp-8h] BYREF
  int v21; // [rsp+78h] [rbp+38h] BYREF
  int v22; // [rsp+88h] [rbp+48h] BYREF

  v17 = 0;
  v20 = 0;
  v21 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, a2, &v17, &v20) )
    return 0;
  v5 = v17;
  *(_BYTE *)a3 = 0;
  if ( !(unsigned int)ASN1BERDecS32Val(v5, 2, a3 + 4) )
    return 0;
  v6 = v17;
  v22 = 0;
  if ( !(unsigned int)ASN1BERDecPeekTag(v17, &v22) )
    return 0;
  if ( v22 == 16 )
  {
    *(_WORD *)(a3 + 8) = 1;
    v18 = 0;
    v19 = 0;
    if ( (unsigned int)ASN1BERDecExplicitTag(v6, 16, &v18, &v19)
      && (unsigned int)ASN1BERDecOpenType(v18, a3 + 16)
      && (unsigned int)ASN1BERDecSXVal(v18, 2, a3 + 32) )
    {
      v7 = ASN1BERDecEndOfContents(v6, v18, v19);
      goto LABEL_11;
    }
    return 0;
  }
  if ( v22 != 0x80000000 )
  {
    ASN1DecSetError(v6, 4294966293LL);
    return 0;
  }
  *(_WORD *)(a3 + 8) = 2;
  v7 = ASN1BERDecOctetString(v6, 0x80000000LL, a3 + 16);
LABEL_11:
  if ( !v7 )
    return 0;
  v9 = v17;
  v18 = 0;
  v19 = 0;
  v22 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v17, 16, &v18, &v19) )
    return 0;
  v10 = v18;
  *(_BYTE *)(a3 + 48) = 0;
  if ( !(unsigned int)ASN1BERDecObjectIdentifier2(v10, 6, a3 + 52) )
    return 0;
  if ( (unsigned int)ASN1BERDecPeekTag(v18, &v22) )
  {
    v11 = v18;
    *(_BYTE *)(a3 + 48) |= 0x80u;
    if ( !(unsigned int)ASN1BERDecOpenType(v11, a3 + 120) )
      return 0;
  }
  if ( !(unsigned int)ASN1BERDecEndOfContents(v9, v18, v19) )
    return 0;
  ASN1BERDecPeekTag(v17, &v21);
  if ( v21 == 0x80000000 )
  {
    v12 = v17;
    *(_BYTE *)a3 |= 0x80u;
    if ( !ASN1Dec_Attributes_0(v12, 0x80000000LL, (unsigned int *)(a3 + 136)) )
      return 0;
  }
  v13 = v17;
  v18 = 0;
  v19 = 0;
  v22 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v17, 16, &v18, &v19) )
    return 0;
  v14 = v18;
  *(_BYTE *)(a3 + 152) = 0;
  if ( !(unsigned int)ASN1BERDecObjectIdentifier2(v14, 6, a3 + 156) )
    return 0;
  if ( (unsigned int)ASN1BERDecPeekTag(v18, &v22) )
  {
    v15 = v18;
    *(_BYTE *)(a3 + 152) |= 0x80u;
    if ( !(unsigned int)ASN1BERDecOpenType(v15, a3 + 224) )
      return 0;
  }
  if ( !(unsigned int)ASN1BERDecEndOfContents(v13, v18, v19) )
    return 0;
  if ( !(unsigned int)ASN1BERDecOctetString(v17, 4, a3 + 240) )
    return 0;
  ASN1BERDecPeekTag(v17, &v21);
  if ( v21 == -2147483647 )
  {
    v16 = v17;
    *(_BYTE *)a3 |= 0x40u;
    if ( !ASN1Dec_Attributes_0(v16, 2147483649LL, (unsigned int *)(a3 + 256)) )
      return 0;
  }
  return (unsigned int)ASN1BERDecEndOfContents(a1, v17, v20) != 0;
}

```

## disassembly

```asm
0x18007e2c0  mov     [rsp-28h+arg_0], rbx
0x18007e2c5  mov     [rsp-28h+arg_10], rsi
0x18007e2ca  push    rbp
0x18007e2cb  push    rdi
0x18007e2cc  push    r13
0x18007e2ce  push    r14
0x18007e2d0  push    r15
0x18007e2d2  mov     rbp, rsp
0x18007e2d5  sub     rsp, 40h
0x18007e2d9  xor     r15d, r15d
0x18007e2dc  lea     r9, [rbp+var_8]
0x18007e2e0  test    edx, edx
0x18007e2e2  mov     [rbp+var_20], r15
0x18007e2e6  mov     rbx, r8
0x18007e2e9  mov     [rbp+var_8], r15
0x18007e2ed  lea     r8, [rbp+var_20]
0x18007e2f1  mov     [rbp+arg_8], r15d
0x18007e2f5  lea     esi, [r15+10h]
0x18007e2f9  mov     r14, rcx
0x18007e2fc  cmovz   edx, esi
0x18007e2ff  call    cs:__imp_ASN1BERDecExplicitTag
0x18007e305  test    eax, eax
0x18007e307  jz      loc_18007E3B1
0x18007e30d  mov     rcx, [rbp+var_20]
0x18007e311  lea     r13d, [r15+2]
0x18007e315  xor     eax, eax
0x18007e317  lea     r8, [rbx+4]
0x18007e31b  mov     edx, r13d
0x18007e31e  mov     [rbx], al
0x18007e320  call    cs:__imp_ASN1BERDecS32Val
0x18007e326  test    eax, eax
0x18007e328  jz      loc_18007E3B1
0x18007e32e  mov     rdi, [rbp+var_20]
0x18007e332  lea     rdx, [rbp+arg_18]
0x18007e336  mov     rcx, rdi
0x18007e339  mov     [rbp+arg_18], r15d
0x18007e33d  call    cs:__imp_ASN1BERDecPeekTag
0x18007e343  test    eax, eax
0x18007e345  jz      short loc_18007E3B1
0x18007e347  mov     rcx, rdi
0x18007e34a  cmp     [rbp+arg_18], esi
0x18007e34d  jnz     loc_18007E59E
0x18007e353  lea     r9, [rbp+var_10]
0x18007e357  mov     word ptr [rbx+8], 1
0x18007e35d  lea     r8, [rbp+var_18]
0x18007e361  mov     [rbp+var_18], r15
0x18007e365  mov     edx, esi
0x18007e367  mov     [rbp+var_10], r15
0x18007e36b  call    cs:__imp_ASN1BERDecExplicitTag
0x18007e371  test    eax, eax
0x18007e373  jz      short loc_18007E3B1
0x18007e375  mov     rcx, [rbp+var_18]
0x18007e379  lea     rdx, [rbx+10h]
0x18007e37d  call    cs:__imp_ASN1BERDecOpenType
0x18007e383  test    eax, eax
0x18007e385  jz      short loc_18007E3B1
0x18007e387  mov     rcx, [rbp+var_18]
0x18007e38b  lea     r8, [rbx+20h]
0x18007e38f  mov     edx, r13d
0x18007e392  call    cs:__imp_ASN1BERDecSXVal
0x18007e398  test    eax, eax
0x18007e39a  jz      short loc_18007E3B1
0x18007e39c  mov     r8, [rbp+var_10]
0x18007e3a0  mov     rcx, rdi
0x18007e3a3  mov     rdx, [rbp+var_18]
0x18007e3a7  call    cs:__imp_ASN1BERDecEndOfContents
0x18007e3ad  test    eax, eax
0x18007e3af  jnz     short loc_18007E3CC
0x18007e3b1  xor     eax, eax
0x18007e3b3  lea     r11, [rsp+40h+var_s0]
0x18007e3b8  mov     rbx, [r11+30h]
0x18007e3bc  mov     rsi, [r11+40h]
0x18007e3c0  mov     rsp, r11
0x18007e3c3  pop     r15
0x18007e3c5  pop     r14
0x18007e3c7  pop     r13
0x18007e3c9  pop     rdi
0x18007e3ca  pop     rbp
0x18007e3cb  retn
0x18007e3cc  mov     rdi, [rbp+var_20]
0x18007e3d0  lea     r9, [rbp+var_10]
0x18007e3d4  mov     rcx, rdi
0x18007e3d7  mov     [rbp+var_18], r15
0x18007e3db  lea     r8, [rbp+var_18]
0x18007e3df  mov     [rbp+var_10], r15
0x18007e3e3  mov     edx, esi
0x18007e3e5  mov     [rbp+arg_18], r15d
0x18007e3e9  call    cs:__imp_ASN1BERDecExplicitTag
0x18007e3ef  test    eax, eax
0x18007e3f1  jz      short loc_18007E3B1
0x18007e3f3  mov     rcx, [rbp+var_18]
0x18007e3f7  lea     r8, [rbx+34h]
0x18007e3fb  xor     eax, eax
0x18007e3fd  mov     [rbx+30h], al
0x18007e400  lea     r13d, [rax+6]
0x18007e404  mov     edx, r13d
0x18007e407  call    cs:__imp_ASN1BERDecObjectIdentifier2
0x18007e40d  test    eax, eax
0x18007e40f  jz      short loc_18007E3B1
0x18007e411  mov     rcx, [rbp+var_18]
0x18007e415  lea     rdx, [rbp+arg_18]
0x18007e419  call    cs:__imp_ASN1BERDecPeekTag
0x18007e41f  mov     sil, 80h
0x18007e422  test    eax, eax
0x18007e424  jz      short loc_18007E440
0x18007e426  mov     rcx, [rbp+var_18]
0x18007e42a  lea     rdx, [rbx+78h]
0x18007e42e  or      [rbx+30h], sil
0x18007e432  call    cs:__imp_ASN1BERDecOpenType
0x18007e438  test    eax, eax
0x18007e43a  jz      loc_18007E3B1
0x18007e440  mov     r8, [rbp+var_10]
0x18007e444  mov     rcx, rdi
0x18007e447  mov     rdx, [rbp+var_18]
0x18007e44b  call    cs:__imp_ASN1BERDecEndOfContents
0x18007e451  test    eax, eax
0x18007e453  jz      loc_18007E3B1
0x18007e459  mov     rcx, [rbp+var_20]
0x18007e45d  lea     rdx, [rbp+arg_8]
0x18007e461  call    cs:__imp_ASN1BERDecPeekTag
0x18007e467  cmp     [rbp+arg_8], 80000000h
0x18007e46e  jnz     short loc_18007E490
0x18007e470  mov     rcx, [rbp+var_20]
0x18007e474  lea     r8, [rbx+88h]
0x18007e47b  or      [rbx], sil
0x18007e47e  mov     edx, 80000000h
0x18007e483  call    ASN1Dec_Attributes_0
0x18007e488  test    eax, eax
0x18007e48a  jz      loc_18007E3B1
0x18007e490  mov     rdi, [rbp+var_20]
0x18007e494  lea     r9, [rbp+var_10]
0x18007e498  mov     rcx, rdi
0x18007e49b  mov     [rbp+var_18], r15
0x18007e49f  lea     r8, [rbp+var_18]
0x18007e4a3  mov     [rbp+var_10], r15
0x18007e4a7  mov     edx, 10h
0x18007e4ac  mov     [rbp+arg_18], r15d
0x18007e4b0  call    cs:__imp_ASN1BERDecExplicitTag
0x18007e4b6  test    eax, eax
0x18007e4b8  jz      loc_18007E3B1
0x18007e4be  mov     rcx, [rbp+var_18]
0x18007e4c2  lea     r8, [rbx+9Ch]
0x18007e4c9  xor     eax, eax
0x18007e4cb  mov     edx, r13d
0x18007e4ce  mov     [rbx+98h], al
0x18007e4d4  call    cs:__imp_ASN1BERDecObjectIdentifier2
0x18007e4da  test    eax, eax
0x18007e4dc  jz      loc_18007E3B1
0x18007e4e2  mov     rcx, [rbp+var_18]
0x18007e4e6  lea     rdx, [rbp+arg_18]
0x18007e4ea  call    cs:__imp_ASN1BERDecPeekTag
0x18007e4f0  test    eax, eax
0x18007e4f2  jz      short loc_18007E514
0x18007e4f4  mov     rcx, [rbp+var_18]
0x18007e4f8  lea     rdx, [rbx+0E0h]
0x18007e4ff  or      [rbx+98h], sil
0x18007e506  call    cs:__imp_ASN1BERDecOpenType
0x18007e50c  test    eax, eax
0x18007e50e  jz      loc_18007E3B1
0x18007e514  mov     r8, [rbp+var_10]
0x18007e518  mov     rcx, rdi
0x18007e51b  mov     rdx, [rbp+var_18]
0x18007e51f  call    cs:__imp_ASN1BERDecEndOfContents
0x18007e525  test    eax, eax
0x18007e527  jz      loc_18007E3B1
0x18007e52d  mov     rcx, [rbp+var_20]
0x18007e531  lea     r8, [rbx+0F0h]
0x18007e538  mov     edx, 4
0x18007e53d  call    cs:__imp_ASN1BERDecOctetString
0x18007e543  test    eax, eax
0x18007e545  jz      loc_18007E3B1
0x18007e54b  mov     rcx, [rbp+var_20]
0x18007e54f  lea     rdx, [rbp+arg_8]
0x18007e553  call    cs:__imp_ASN1BERDecPeekTag
0x18007e559  mov     edx, 80000001h
0x18007e55e  cmp     [rbp+arg_8], edx
0x18007e561  jnz     short loc_18007E57E
0x18007e563  mov     rcx, [rbp+var_20]
0x18007e567  lea     r8, [rbx+100h]
0x18007e56e  or      byte ptr [rbx], 40h
0x18007e571  call    ASN1Dec_Attributes_0
0x18007e576  test    eax, eax
0x18007e578  jz      loc_18007E3B1
0x18007e57e  mov     r8, [rbp+var_8]
0x18007e582  mov     rcx, r14
0x18007e585  mov     rdx, [rbp+var_20]
0x18007e589  call    cs:__imp_ASN1BERDecEndOfContents
0x18007e58f  test    eax, eax
0x18007e591  mov     ecx, r15d
0x18007e594  setnz   cl
0x18007e597  mov     eax, ecx
0x18007e599  jmp     loc_18007E3B3
0x18007e59e  cmp     [rbp+arg_18], 80000000h
0x18007e5a5  jz      loc_18011B8A0
0x18007e5ab  mov     edx, 0FFFFFC15h
0x18007e5b0  call    cs:__imp_ASN1DecSetError
0x18007e5b6  jmp     loc_18007E3B1
0x18011b8a0  lea     r8, [rbx+10h]
0x18011b8a4  mov     [rbx+8], r13w
0x18011b8a9  mov     edx, 80000000h
0x18011b8ae  call    cs:__imp_ASN1BERDecOctetString
0x18011b8b4  nop
0x18011b8b5  jmp     loc_18007E3AD
```
