# ASN1Dec_KERB_PKCS_SIGNATURE

- ea: `0x180004010`
- end: `0x180004152`
- name: `ASN1Dec_KERB_PKCS_SIGNATURE`
- size: `322`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023f0`
- `0x180003360`
- `0x180004368`
- `0x180004e00`
- `0x180004f2c`
- `0x180005060`
- `0x1800059c4`
- `0x1800064d0`
- `0x180008840`
- `0x180008aa0`
- `0x18000a3f0`
- `0x18000a570`
- `0x18000a730`
- `0x18000abd0`
- `0x18000c370`
- `0x18000c544`
- `0x18000c960`
- `0x18000cf80`

## callees

- `0x180004010`

## import_xrefs

- `MSASN1!ASN1BERDecOctetString` at `0x1800040ee`
- `MSASN1!ASN1BERDecOctetString` at `0x1800040ee`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800040b2`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000410a`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180004125`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800040b2`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000410a`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180004125`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000404f`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180004074`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800040d3`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000404f`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180004074`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800040d3`
- `MSASN1!ASN1BERDecS32Val` at `0x180004092`
- `MSASN1!ASN1BERDecS32Val` at `0x180004092`

## pseudocode

```c
__int64 __fastcall ASN1Dec_KERB_PKCS_SIGNATURE(__int64 a1, __int64 a2, __int64 a3)
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
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, a2, &v7, &v9)
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
0x180004010  mov     [rsp-8+arg_0], rbx
0x180004015  mov     [rsp-8+arg_8], rsi
0x18000401a  mov     [rsp-8+arg_10], rdi
0x18000401f  push    rbp
0x180004020  mov     rbp, rsp
0x180004023  sub     rsp, 40h
0x180004027  xor     ebx, ebx
0x180004029  lea     r9, [rbp+var_10]
0x18000402d  test    edx, edx
0x18000402f  mov     [rbp+var_20], rbx
0x180004033  mov     rdi, r8
0x180004036  mov     [rbp+var_10], rbx
0x18000403a  lea     r8, [rbp+var_20]
0x18000403e  mov     [rbp+arg_18], rbx
0x180004042  lea     eax, [rbx+10h]
0x180004045  mov     [rbp+var_18], rbx
0x180004049  cmovz   edx, eax
0x18000404c  mov     rsi, rcx
0x18000404f  call    cs:__imp_ASN1BERDecExplicitTag
0x180004056  nop     dword ptr [rax+rax+00h]
0x18000405b  test    eax, eax
0x18000405d  jz      loc_18000413A
0x180004063  mov     rcx, [rbp+var_20]
0x180004067  lea     r9, [rbp+var_18]
0x18000406b  lea     r8, [rbp+arg_18]
0x18000406f  mov     edx, 80000000h
0x180004074  call    cs:__imp_ASN1BERDecExplicitTag
0x18000407b  nop     dword ptr [rax+rax+00h]
0x180004080  test    eax, eax
0x180004082  jz      loc_18000413A
0x180004088  mov     rcx, [rbp+arg_18]
0x18000408c  lea     edx, [rbx+2]
0x18000408f  mov     r8, rdi
0x180004092  call    cs:__imp_ASN1BERDecS32Val
0x180004099  nop     dword ptr [rax+rax+00h]
0x18000409e  test    eax, eax
0x1800040a0  jz      loc_18000413A
0x1800040a6  mov     r8, [rbp+var_18]
0x1800040aa  mov     rdx, [rbp+arg_18]
0x1800040ae  mov     rcx, [rbp+var_20]
0x1800040b2  call    cs:__imp_ASN1BERDecEndOfContents
0x1800040b9  nop     dword ptr [rax+rax+00h]
0x1800040be  test    eax, eax
0x1800040c0  jz      short loc_18000413A
0x1800040c2  mov     rcx, [rbp+var_20]
0x1800040c6  lea     r9, [rbp+var_18]
0x1800040ca  lea     r8, [rbp+arg_18]
0x1800040ce  mov     edx, 80000001h
0x1800040d3  call    cs:__imp_ASN1BERDecExplicitTag
0x1800040da  nop     dword ptr [rax+rax+00h]
0x1800040df  test    eax, eax
0x1800040e1  jz      short loc_18000413A
0x1800040e3  mov     rcx, [rbp+arg_18]
0x1800040e7  lea     r8, [rdi+8]
0x1800040eb  lea     edx, [rbx+4]
0x1800040ee  call    cs:__imp_ASN1BERDecOctetString
0x1800040f5  nop     dword ptr [rax+rax+00h]
0x1800040fa  test    eax, eax
0x1800040fc  jz      short loc_18000413A
0x1800040fe  mov     r8, [rbp+var_18]
0x180004102  mov     rdx, [rbp+arg_18]
0x180004106  mov     rcx, [rbp+var_20]
0x18000410a  call    cs:__imp_ASN1BERDecEndOfContents
0x180004111  nop     dword ptr [rax+rax+00h]
0x180004116  test    eax, eax
0x180004118  jz      short loc_18000413A
0x18000411a  mov     r8, [rbp+var_10]
0x18000411e  mov     rcx, rsi
0x180004121  mov     rdx, [rbp+var_20]
0x180004125  call    cs:__imp_ASN1BERDecEndOfContents
0x18000412c  nop     dword ptr [rax+rax+00h]
0x180004131  test    eax, eax
0x180004133  setnz   bl
0x180004136  mov     eax, ebx
0x180004138  jmp     short loc_18000413C
0x18000413a  xor     eax, eax
0x18000413c  mov     rbx, [rsp+40h+arg_0]
0x180004141  mov     rsi, [rsp+40h+arg_8]
0x180004146  mov     rdi, [rsp+40h+arg_10]
0x18000414b  add     rsp, 40h
0x18000414f  pop     rbp
0x180004150  retn
```
