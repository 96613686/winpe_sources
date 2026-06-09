# ASN1Enc_CertificateToBeSigned

- ea: `0x18008ed60`
- end: `0x18008ef36`
- name: `ASN1Enc_CertificateToBeSigned`
- size: `470`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18008ed60`
- `0x18008ef3c`
- `0x18008efc0`
- `0x18008f5f0`
- `0x18008f680`

## import_xrefs

- `MSASN1!ASN1DEREncBitString` at `0x18008eeba`
- `MSASN1!ASN1DEREncBitString` at `0x18008eedc`
- `MSASN1!ASN1DEREncBitString` at `0x18008eeba`
- `MSASN1!ASN1DEREncBitString` at `0x18008eedc`
- `MSASN1!ASN1BEREncOpenType` at `0x18008ee2b`
- `MSASN1!ASN1BEREncOpenType` at `0x18008ee4c`
- `MSASN1!ASN1BEREncOpenType` at `0x18008ee2b`
- `MSASN1!ASN1BEREncOpenType` at `0x18008ee4c`
- `MSASN1!ASN1BEREncSX` at `0x18008ee08`
- `MSASN1!ASN1BEREncSX` at `0x18008ee08`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18008edf2`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18008ee93`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18008ef23`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18008edf2`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18008ee93`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18008ef23`
- `MSASN1!ASN1BEREncS32` at `0x18008eddd`
- `MSASN1!ASN1BEREncS32` at `0x18008eddd`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18008ed93`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18008edc4`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18008eef5`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18008ed93`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18008edc4`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18008eef5`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_CertificateToBeSigned(__int64 a1, __int64 a2, __int64 a3)
{
  char v5; // si
  __int64 v6; // rdx
  unsigned int v8; // [rsp+48h] [rbp+10h] BYREF
  unsigned int v9; // [rsp+58h] [rbp+20h] BYREF

  v9 = 0;
  v8 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( !(unsigned int)ASN1BEREncExplicitTag(a1, a2, &v9) )
    return 0;
  v5 = *(_BYTE *)a3 & 0x7F;
  if ( *(_DWORD *)(a3 + 4) )
    v5 = *(_BYTE *)a3;
  return (v5 >= 0
       || (unsigned int)ASN1BEREncExplicitTag(a1, 0x80000000LL, &v8)
       && (unsigned int)ASN1BEREncS32(a1, 2, *(unsigned int *)(a3 + 4))
       && (unsigned int)ASN1BEREncEndOfContents(a1, v8))
      && (unsigned int)ASN1BEREncSX(a1, 2, a3 + 8)
      && (unsigned int)ASN1Enc_AlgorithmIdentifier_0(a1, 0, a3 + 24)
      && (unsigned int)ASN1BEREncOpenType(a1, a3 + 64)
      && (unsigned int)ASN1Enc_Validity(a1, v6, a3 + 80)
      && (unsigned int)ASN1BEREncOpenType(a1, a3 + 112)
      && (unsigned int)ASN1Enc_SubjectPublicKeyInfo(a1, 0, a3 + 128)
      && ((v5 & 0x40) == 0
       || (unsigned int)ASN1DEREncBitString(a1, 2147483649LL, *(unsigned int *)(a3 + 184), *(_QWORD *)(a3 + 192)))
      && ((v5 & 0x20) == 0
       || (unsigned int)ASN1DEREncBitString(a1, 2147483650LL, *(unsigned int *)(a3 + 200), *(_QWORD *)(a3 + 208)))
      && ((v5 & 0x10) == 0
       || (unsigned int)ASN1BEREncExplicitTag(a1, 2147483651LL, &v8)
       && (unsigned int)ASN1Enc_Extensions(a1, 0, a3 + 216)
       && (unsigned int)ASN1BEREncEndOfContents(a1, v8))
      && (unsigned int)ASN1BEREncEndOfContents(a1, v9) != 0;
}

```

## disassembly

```asm
0x18008ed60  mov     rax, rsp
0x18008ed63  mov     [rax+8], rbx
0x18008ed67  push    rsi
0x18008ed68  push    rdi
0x18008ed69  push    r15
0x18008ed6b  sub     rsp, 20h
0x18008ed6f  test    edx, edx
0x18008ed71  mov     dword ptr [rax+20h], 0
0x18008ed78  mov     rdi, r8
0x18008ed7b  mov     dword ptr [rax+10h], 0
0x18008ed82  mov     r15d, 10h
0x18008ed88  lea     r8, [rax+20h]
0x18008ed8c  cmovz   edx, r15d
0x18008ed90  mov     rbx, rcx
0x18008ed93  call    cs:__imp_ASN1BEREncExplicitTag
0x18008ed99  test    eax, eax
0x18008ed9b  jz      loc_18008EE6B
0x18008eda1  movzx   ecx, byte ptr [rdi]
0x18008eda4  mov     al, cl
0x18008eda6  and     al, 7Fh
0x18008eda8  cmp     dword ptr [rdi+4], 0
0x18008edac  movzx   esi, al
0x18008edaf  cmovnz  esi, ecx
0x18008edb2  test    sil, sil
0x18008edb5  jns     short loc_18008EDFC
0x18008edb7  lea     r8, [rsp+38h+arg_8]
0x18008edbc  mov     edx, 80000000h
0x18008edc1  mov     rcx, rbx
0x18008edc4  call    cs:__imp_ASN1BEREncExplicitTag
0x18008edca  test    eax, eax
0x18008edcc  jz      loc_18008EE6B
0x18008edd2  mov     r8d, [rdi+4]
0x18008edd6  lea     edx, [r15-0Eh]
0x18008edda  mov     rcx, rbx
0x18008eddd  call    cs:__imp_ASN1BEREncS32
0x18008ede3  test    eax, eax
0x18008ede5  jz      loc_18008EE6B
0x18008edeb  mov     edx, [rsp+38h+arg_8]
0x18008edef  mov     rcx, rbx
0x18008edf2  call    cs:__imp_ASN1BEREncEndOfContents
0x18008edf8  test    eax, eax
0x18008edfa  jz      short loc_18008EE6B
0x18008edfc  lea     r8, [rdi+8]
0x18008ee00  mov     edx, 2
0x18008ee05  mov     rcx, rbx
0x18008ee08  call    cs:__imp_ASN1BEREncSX
0x18008ee0e  test    eax, eax
0x18008ee10  jz      short loc_18008EE6B
0x18008ee12  lea     r8, [rdi+18h]
0x18008ee16  xor     edx, edx
0x18008ee18  mov     rcx, rbx
0x18008ee1b  call    ASN1Enc_AlgorithmIdentifier_0
0x18008ee20  test    eax, eax
0x18008ee22  jz      short loc_18008EE6B
0x18008ee24  lea     rdx, [rdi+40h]
0x18008ee28  mov     rcx, rbx
0x18008ee2b  call    cs:__imp_ASN1BEREncOpenType
0x18008ee31  test    eax, eax
0x18008ee33  jz      short loc_18008EE6B
0x18008ee35  lea     r8, [rdi+50h]
0x18008ee39  mov     rcx, rbx
0x18008ee3c  call    ASN1Enc_Validity
0x18008ee41  test    eax, eax
0x18008ee43  jz      short loc_18008EE6B
0x18008ee45  lea     rdx, [rdi+70h]
0x18008ee49  mov     rcx, rbx
0x18008ee4c  call    cs:__imp_ASN1BEREncOpenType
0x18008ee52  test    eax, eax
0x18008ee54  jz      short loc_18008EE6B
0x18008ee56  lea     r8, [rdi+80h]
0x18008ee5d  xor     edx, edx
0x18008ee5f  mov     rcx, rbx
0x18008ee62  call    ASN1Enc_SubjectPublicKeyInfo
0x18008ee67  test    eax, eax
0x18008ee69  jnz     short loc_18008EE7B
0x18008ee6b  xor     eax, eax
0x18008ee6d  mov     rbx, [rsp+38h+arg_0]
0x18008ee72  add     rsp, 20h
0x18008ee76  pop     r15
0x18008ee78  pop     rdi
0x18008ee79  pop     rsi
0x18008ee7a  retn
0x18008ee7b  test    sil, 40h
0x18008ee7f  jnz     short loc_18008EEA4
0x18008ee81  test    sil, 20h
0x18008ee85  jnz     short loc_18008EEC6
0x18008ee87  test    r15b, sil
0x18008ee8a  jnz     short loc_18008EEE8
0x18008ee8c  mov     edx, [rsp+38h+arg_18]
0x18008ee90  mov     rcx, rbx
0x18008ee93  call    cs:__imp_ASN1BEREncEndOfContents
0x18008ee99  xor     ecx, ecx
0x18008ee9b  test    eax, eax
0x18008ee9d  setnz   cl
0x18008eea0  mov     eax, ecx
0x18008eea2  jmp     short loc_18008EE6D
0x18008eea4  mov     r9, [rdi+0C0h]
0x18008eeab  mov     edx, 80000001h
0x18008eeb0  mov     r8d, [rdi+0B8h]
0x18008eeb7  mov     rcx, rbx
0x18008eeba  call    cs:__imp_ASN1DEREncBitString
0x18008eec0  test    eax, eax
0x18008eec2  jz      short loc_18008EE6B
0x18008eec4  jmp     short loc_18008EE81
0x18008eec6  mov     r9, [rdi+0D0h]
0x18008eecd  mov     edx, 80000002h
0x18008eed2  mov     r8d, [rdi+0C8h]
0x18008eed9  mov     rcx, rbx
0x18008eedc  call    cs:__imp_ASN1DEREncBitString
0x18008eee2  test    eax, eax
0x18008eee4  jz      short loc_18008EE6B
0x18008eee6  jmp     short loc_18008EE87
0x18008eee8  lea     r8, [rsp+38h+arg_8]
0x18008eeed  mov     edx, 80000003h
0x18008eef2  mov     rcx, rbx
0x18008eef5  call    cs:__imp_ASN1BEREncExplicitTag
0x18008eefb  test    eax, eax
0x18008eefd  jz      loc_18008EE6B
0x18008ef03  lea     r8, [rdi+0D8h]
0x18008ef0a  xor     edx, edx
0x18008ef0c  mov     rcx, rbx
0x18008ef0f  call    ASN1Enc_Extensions
0x18008ef14  test    eax, eax
0x18008ef16  jz      loc_18008EE6B
0x18008ef1c  mov     edx, [rsp+38h+arg_8]
0x18008ef20  mov     rcx, rbx
0x18008ef23  call    cs:__imp_ASN1BEREncEndOfContents
0x18008ef29  test    eax, eax
0x18008ef2b  jz      loc_18008EE6B
0x18008ef31  jmp     loc_18008EE8C
```
