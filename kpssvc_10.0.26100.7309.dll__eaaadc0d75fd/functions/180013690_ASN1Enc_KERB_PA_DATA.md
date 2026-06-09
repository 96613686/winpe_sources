# ASN1Enc_KERB_PA_DATA

- ea: `0x180013690`
- end: `0x1800137a2`
- name: `ASN1Enc_KERB_PA_DATA`
- size: `274`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800115e8`
- `0x180012904`
- `0x180012c48`
- `0x180013414`
- `0x1800169c0`
- `0x1800175f0`

## callees

- `0x180013690`

## import_xrefs

- `MSASN1!ASN1BEREncExplicitTag` at `0x1800136b8`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800136d9`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18001372e`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800136b8`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800136d9`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18001372e`
- `MSASN1!ASN1BEREncS32` at `0x1800136f6`
- `MSASN1!ASN1BEREncS32` at `0x1800136f6`
- `MSASN1!ASN1DEREncOctetString` at `0x18001374c`
- `MSASN1!ASN1DEREncOctetString` at `0x18001374c`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180013711`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180013763`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001377a`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180013711`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180013763`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001377a`

## pseudocode

```c
__int64 __fastcall ASN1Enc_KERB_PA_DATA(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v3; // ebx
  unsigned int v7; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v8; // [rsp+48h] [rbp+20h] BYREF

  v3 = 0;
  v8 = 0;
  v7 = 0;
  if ( !(unsigned int)ASN1BEREncExplicitTag(a1, 16, &v8)
    || !(unsigned int)ASN1BEREncExplicitTag(a1, 2147483649LL, &v7)
    || !(unsigned int)ASN1BEREncS32(a1, 2, *a3)
    || !(unsigned int)ASN1BEREncEndOfContents(a1, v7)
    || !(unsigned int)ASN1BEREncExplicitTag(a1, 2147483650LL, &v7)
    || !(unsigned int)ASN1DEREncOctetString(a1, 4, a3[2], *((_QWORD *)a3 + 2))
    || !(unsigned int)ASN1BEREncEndOfContents(a1, v7) )
  {
    return 0;
  }
  LOBYTE(v3) = (unsigned int)ASN1BEREncEndOfContents(a1, v8) != 0;
  return v3;
}

```

## disassembly

```asm
0x180013690  mov     rax, rsp
0x180013693  mov     [rax+8], rbx
0x180013697  mov     [rax+18h], rsi
0x18001369b  mov     [rax+10h], edx
0x18001369e  push    rdi
0x18001369f  sub     rsp, 20h
0x1800136a3  xor     ebx, ebx
0x1800136a5  mov     rsi, r8
0x1800136a8  lea     r8, [rax+20h]
0x1800136ac  mov     [rax+20h], ebx
0x1800136af  mov     rdi, rcx
0x1800136b2  mov     [rax+10h], ebx
0x1800136b5  lea     edx, [rbx+10h]
0x1800136b8  call    cs:__imp_ASN1BEREncExplicitTag
0x1800136bf  nop     dword ptr [rax+rax+00h]
0x1800136c4  test    eax, eax
0x1800136c6  jz      loc_18001378F
0x1800136cc  lea     r8, [rsp+28h+arg_8]
0x1800136d1  mov     edx, 80000001h
0x1800136d6  mov     rcx, rdi
0x1800136d9  call    cs:__imp_ASN1BEREncExplicitTag
0x1800136e0  nop     dword ptr [rax+rax+00h]
0x1800136e5  test    eax, eax
0x1800136e7  jz      loc_18001378F
0x1800136ed  mov     r8d, [rsi]
0x1800136f0  lea     edx, [rbx+2]
0x1800136f3  mov     rcx, rdi
0x1800136f6  call    cs:__imp_ASN1BEREncS32
0x1800136fd  nop     dword ptr [rax+rax+00h]
0x180013702  test    eax, eax
0x180013704  jz      loc_18001378F
0x18001370a  mov     edx, [rsp+28h+arg_8]
0x18001370e  mov     rcx, rdi
0x180013711  call    cs:__imp_ASN1BEREncEndOfContents
0x180013718  nop     dword ptr [rax+rax+00h]
0x18001371d  test    eax, eax
0x18001371f  jz      short loc_18001378F
0x180013721  lea     r8, [rsp+28h+arg_8]
0x180013726  mov     edx, 80000002h
0x18001372b  mov     rcx, rdi
0x18001372e  call    cs:__imp_ASN1BEREncExplicitTag
0x180013735  nop     dword ptr [rax+rax+00h]
0x18001373a  test    eax, eax
0x18001373c  jz      short loc_18001378F
0x18001373e  mov     r9, [rsi+10h]
0x180013742  lea     edx, [rbx+4]
0x180013745  mov     r8d, [rsi+8]
0x180013749  mov     rcx, rdi
0x18001374c  call    cs:__imp_ASN1DEREncOctetString
0x180013753  nop     dword ptr [rax+rax+00h]
0x180013758  test    eax, eax
0x18001375a  jz      short loc_18001378F
0x18001375c  mov     edx, [rsp+28h+arg_8]
0x180013760  mov     rcx, rdi
0x180013763  call    cs:__imp_ASN1BEREncEndOfContents
0x18001376a  nop     dword ptr [rax+rax+00h]
0x18001376f  test    eax, eax
0x180013771  jz      short loc_18001378F
0x180013773  mov     edx, [rsp+28h+arg_18]
0x180013777  mov     rcx, rdi
0x18001377a  call    cs:__imp_ASN1BEREncEndOfContents
0x180013781  nop     dword ptr [rax+rax+00h]
0x180013786  test    eax, eax
0x180013788  setnz   bl
0x18001378b  mov     eax, ebx
0x18001378d  jmp     short loc_180013791
0x18001378f  xor     eax, eax
0x180013791  mov     rbx, [rsp+28h+arg_0]
0x180013796  mov     rsi, [rsp+28h+arg_10]
0x18001379b  add     rsp, 20h
0x18001379f  pop     rdi
0x1800137a0  retn
```
