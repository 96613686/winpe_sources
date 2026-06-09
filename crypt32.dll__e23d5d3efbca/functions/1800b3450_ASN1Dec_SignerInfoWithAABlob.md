# ASN1Dec_SignerInfoWithAABlob

- ea: `0x1800b3450`
- end: `0x1800b3571`
- name: `ASN1Dec_SignerInfoWithAABlob`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18010c4a0`

## callees

- `0x1800b3450`
- `0x18010a880`

## import_xrefs

- `MSASN1!ASN1BERDecEndOfContents` at `0x1800b354e`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800b354e`
- `MSASN1!ASN1BERDecPeekTag` at `0x1800b351f`
- `MSASN1!ASN1BERDecPeekTag` at `0x1800b351f`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800b3491`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800b3491`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800b34ab`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800b34c1`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800b34d7`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800b34e9`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800b34fb`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800b350d`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800b34ab`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800b34c1`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800b34d7`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800b34e9`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800b34fb`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800b350d`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_SignerInfoWithAABlob(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v8; // [rsp+20h] [rbp-10h] BYREF
  int v9; // [rsp+48h] [rbp+18h] BYREF
  __int64 v10; // [rsp+58h] [rbp+28h] BYREF

  v10 = 0;
  v8 = 0;
  v9 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( (unsigned int)ASN1BERDecExplicitTag(a1, a2, &v10, &v8)
    && (v5 = v10, *a3 = 0, (unsigned int)ASN1BERDecOpenType2(v5, a3 + 8))
    && (unsigned int)ASN1BERDecOpenType2(v10, a3 + 24)
    && (unsigned int)ASN1BERDecOpenType2(v10, a3 + 40)
    && (unsigned int)ASN1BERDecOpenType2(v10, a3 + 56)
    && (unsigned int)ASN1BERDecOpenType2(v10, a3 + 72)
    && (unsigned int)ASN1BERDecOpenType2(v10, a3 + 88)
    && ((ASN1BERDecPeekTag(v10, &v9), v9 != -2147483647)
     || (v6 = v10, *a3 |= 0x80u, (unsigned int)ASN1Dec_DigestAlgorithmBlobs(v6, 2147483649LL, a3 + 104))) )
  {
    return (unsigned int)ASN1BERDecEndOfContents(a1, v10, v8) != 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x1800b3450  mov     [rsp-8+arg_0], rbx
0x1800b3455  mov     [rsp-8+arg_10], rdi
0x1800b345a  push    rbp
0x1800b345b  mov     rbp, rsp
0x1800b345e  sub     rsp, 30h
0x1800b3462  test    edx, edx
0x1800b3464  mov     [rbp+arg_18], 0
0x1800b346c  mov     eax, 10h
0x1800b3471  mov     [rbp+var_10], 0
0x1800b3479  mov     rbx, r8
0x1800b347c  mov     [rbp+arg_8], 0
0x1800b3483  cmovz   edx, eax
0x1800b3486  lea     r9, [rbp+var_10]
0x1800b348a  lea     r8, [rbp+arg_18]
0x1800b348e  mov     rdi, rcx
0x1800b3491  call    cs:__imp_ASN1BERDecExplicitTag
0x1800b3497  test    eax, eax
0x1800b3499  jz      loc_1800B355F
0x1800b349f  mov     rcx, [rbp+arg_18]
0x1800b34a3  lea     rdx, [rbx+8]
0x1800b34a7  xor     eax, eax
0x1800b34a9  mov     [rbx], al
0x1800b34ab  call    cs:__imp_ASN1BERDecOpenType2
0x1800b34b1  test    eax, eax
0x1800b34b3  jz      loc_1800B355F
0x1800b34b9  mov     rcx, [rbp+arg_18]
0x1800b34bd  lea     rdx, [rbx+18h]
0x1800b34c1  call    cs:__imp_ASN1BERDecOpenType2
0x1800b34c7  test    eax, eax
0x1800b34c9  jz      loc_1800B355F
0x1800b34cf  mov     rcx, [rbp+arg_18]
0x1800b34d3  lea     rdx, [rbx+28h]
0x1800b34d7  call    cs:__imp_ASN1BERDecOpenType2
0x1800b34dd  test    eax, eax
0x1800b34df  jz      short loc_1800B355F
0x1800b34e1  mov     rcx, [rbp+arg_18]
0x1800b34e5  lea     rdx, [rbx+38h]
0x1800b34e9  call    cs:__imp_ASN1BERDecOpenType2
0x1800b34ef  test    eax, eax
0x1800b34f1  jz      short loc_1800B355F
0x1800b34f3  mov     rcx, [rbp+arg_18]
0x1800b34f7  lea     rdx, [rbx+48h]
0x1800b34fb  call    cs:__imp_ASN1BERDecOpenType2
0x1800b3501  test    eax, eax
0x1800b3503  jz      short loc_1800B355F
0x1800b3505  mov     rcx, [rbp+arg_18]
0x1800b3509  lea     rdx, [rbx+58h]
0x1800b350d  call    cs:__imp_ASN1BERDecOpenType2
0x1800b3513  test    eax, eax
0x1800b3515  jz      short loc_1800B355F
0x1800b3517  mov     rcx, [rbp+arg_18]
0x1800b351b  lea     rdx, [rbp+arg_8]
0x1800b351f  call    cs:__imp_ASN1BERDecPeekTag
0x1800b3525  mov     edx, 80000001h
0x1800b352a  cmp     [rbp+arg_8], edx
0x1800b352d  jnz     short loc_1800B3543
0x1800b352f  mov     rcx, [rbp+arg_18]
0x1800b3533  lea     r8, [rbx+68h]
0x1800b3537  or      byte ptr [rbx], 80h
0x1800b353a  call    ASN1Dec_DigestAlgorithmBlobs
0x1800b353f  test    eax, eax
0x1800b3541  jz      short loc_1800B355F
0x1800b3543  mov     r8, [rbp+var_10]
0x1800b3547  mov     rcx, rdi
0x1800b354a  mov     rdx, [rbp+arg_18]
0x1800b354e  call    cs:__imp_ASN1BERDecEndOfContents
0x1800b3554  xor     ecx, ecx
0x1800b3556  test    eax, eax
0x1800b3558  setnz   cl
0x1800b355b  mov     eax, ecx
0x1800b355d  jmp     short loc_1800B3561
0x1800b355f  xor     eax, eax
0x1800b3561  mov     rbx, [rsp+30h+arg_0]
0x1800b3566  mov     rdi, [rsp+30h+arg_10]
0x1800b356b  add     rsp, 30h
0x1800b356f  pop     rbp
0x1800b3570  retn
```
