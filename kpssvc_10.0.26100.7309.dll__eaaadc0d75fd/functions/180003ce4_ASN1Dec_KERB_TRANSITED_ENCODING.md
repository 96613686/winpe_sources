# ASN1Dec_KERB_TRANSITED_ENCODING

- ea: `0x180003ce4`
- end: `0x180003e21`
- name: `ASN1Dec_KERB_TRANSITED_ENCODING`
- size: `317`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005380`
- `0x1800060c0`
- `0x1800064d0`
- `0x18000921c`
- `0x180009784`
- `0x18000a898`

## callees

- `0x180003ce4`

## import_xrefs

- `MSASN1!ASN1BERDecOctetString` at `0x180003dbd`
- `MSASN1!ASN1BERDecOctetString` at `0x180003dbd`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180003d81`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180003dd9`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180003df4`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180003d81`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180003dd9`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180003df4`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180003d1e`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180003d43`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180003da2`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180003d1e`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180003d43`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180003da2`
- `MSASN1!ASN1BERDecS32Val` at `0x180003d61`
- `MSASN1!ASN1BERDecS32Val` at `0x180003d61`

## pseudocode

```c
__int64 __fastcall ASN1Dec_KERB_TRANSITED_ENCODING(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  __int64 v7; // [rsp+20h] [rbp-20h] BYREF
  __int64 v8; // [rsp+28h] [rbp-18h] BYREF
  __int64 v9; // [rsp+30h] [rbp-10h] BYREF
  __int64 v10; // [rsp+68h] [rbp+28h] BYREF

  v3 = 0;
  v7 = 0;
  v9 = 0;
  v10 = 0;
  v8 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, 16, &v7, &v9)
    || !(unsigned int)ASN1BERDecExplicitTag(v7, 0x80000000LL, &v10, &v8)
    || !(unsigned int)ASN1BERDecS32Val(v10, 2, a3)
    || !(unsigned int)ASN1BERDecEndOfContents(v7, v10, v8)
    || !(unsigned int)ASN1BERDecExplicitTag(v7, 2147483649LL, &v10, &v8)
    || !(unsigned int)ASN1BERDecOctetString(v10, 4, a3 + 8)
    || !(unsigned int)ASN1BERDecEndOfContents(v7, v10, v8) )
  {
    return 0;
  }
  LOBYTE(v3) = (unsigned int)ASN1BERDecEndOfContents(a1, v7, v9) != 0;
  return v3;
}

```

## disassembly

```asm
0x180003ce4  mov     [rsp-8+arg_0], rbx
0x180003ce9  mov     [rsp-8+arg_8], rsi
0x180003cee  mov     [rsp-8+arg_10], rdi
0x180003cf3  push    rbp
0x180003cf4  mov     rbp, rsp
0x180003cf7  sub     rsp, 40h
0x180003cfb  xor     ebx, ebx
0x180003cfd  lea     r9, [rbp+var_10]
0x180003d01  mov     rdi, r8
0x180003d04  mov     [rbp+var_20], rbx
0x180003d08  lea     r8, [rbp+var_20]
0x180003d0c  mov     [rbp+var_10], rbx
0x180003d10  mov     rsi, rcx
0x180003d13  mov     [rbp+arg_18], rbx
0x180003d17  lea     edx, [rbx+10h]
0x180003d1a  mov     [rbp+var_18], rbx
0x180003d1e  call    cs:__imp_ASN1BERDecExplicitTag
0x180003d25  nop     dword ptr [rax+rax+00h]
0x180003d2a  test    eax, eax
0x180003d2c  jz      loc_180003E09
0x180003d32  mov     rcx, [rbp+var_20]
0x180003d36  lea     r9, [rbp+var_18]
0x180003d3a  lea     r8, [rbp+arg_18]
0x180003d3e  mov     edx, 80000000h
0x180003d43  call    cs:__imp_ASN1BERDecExplicitTag
0x180003d4a  nop     dword ptr [rax+rax+00h]
0x180003d4f  test    eax, eax
0x180003d51  jz      loc_180003E09
0x180003d57  mov     rcx, [rbp+arg_18]
0x180003d5b  lea     edx, [rbx+2]
0x180003d5e  mov     r8, rdi
0x180003d61  call    cs:__imp_ASN1BERDecS32Val
0x180003d68  nop     dword ptr [rax+rax+00h]
0x180003d6d  test    eax, eax
0x180003d6f  jz      loc_180003E09
0x180003d75  mov     r8, [rbp+var_18]
0x180003d79  mov     rdx, [rbp+arg_18]
0x180003d7d  mov     rcx, [rbp+var_20]
0x180003d81  call    cs:__imp_ASN1BERDecEndOfContents
0x180003d88  nop     dword ptr [rax+rax+00h]
0x180003d8d  test    eax, eax
0x180003d8f  jz      short loc_180003E09
0x180003d91  mov     rcx, [rbp+var_20]
0x180003d95  lea     r9, [rbp+var_18]
0x180003d99  lea     r8, [rbp+arg_18]
0x180003d9d  mov     edx, 80000001h
0x180003da2  call    cs:__imp_ASN1BERDecExplicitTag
0x180003da9  nop     dword ptr [rax+rax+00h]
0x180003dae  test    eax, eax
0x180003db0  jz      short loc_180003E09
0x180003db2  mov     rcx, [rbp+arg_18]
0x180003db6  lea     r8, [rdi+8]
0x180003dba  lea     edx, [rbx+4]
0x180003dbd  call    cs:__imp_ASN1BERDecOctetString
0x180003dc4  nop     dword ptr [rax+rax+00h]
0x180003dc9  test    eax, eax
0x180003dcb  jz      short loc_180003E09
0x180003dcd  mov     r8, [rbp+var_18]
0x180003dd1  mov     rdx, [rbp+arg_18]
0x180003dd5  mov     rcx, [rbp+var_20]
0x180003dd9  call    cs:__imp_ASN1BERDecEndOfContents
0x180003de0  nop     dword ptr [rax+rax+00h]
0x180003de5  test    eax, eax
0x180003de7  jz      short loc_180003E09
0x180003de9  mov     r8, [rbp+var_10]
0x180003ded  mov     rcx, rsi
0x180003df0  mov     rdx, [rbp+var_20]
0x180003df4  call    cs:__imp_ASN1BERDecEndOfContents
0x180003dfb  nop     dword ptr [rax+rax+00h]
0x180003e00  test    eax, eax
0x180003e02  setnz   bl
0x180003e05  mov     eax, ebx
0x180003e07  jmp     short loc_180003E0B
0x180003e09  xor     eax, eax
0x180003e0b  mov     rbx, [rsp+40h+arg_0]
0x180003e10  mov     rsi, [rsp+40h+arg_8]
0x180003e15  mov     rdi, [rsp+40h+arg_10]
0x180003e1a  add     rsp, 40h
0x180003e1e  pop     rbp
0x180003e1f  retn
```
