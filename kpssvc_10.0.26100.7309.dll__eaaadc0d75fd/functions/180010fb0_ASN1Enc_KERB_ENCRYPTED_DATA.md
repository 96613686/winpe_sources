# ASN1Enc_KERB_ENCRYPTED_DATA

- ea: `0x180010fb0`
- end: `0x180011126`
- name: `ASN1Enc_KERB_ENCRYPTED_DATA`
- size: `374`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e800`
- `0x18000f020`
- `0x18000f1c0`
- `0x18000fee0`
- `0x180011f6c`
- `0x1800129b8`
- `0x180012e78`
- `0x180013c50`
- `0x1800147c0`
- `0x180015e90`
- `0x1800162d8`
- `0x18001638c`

## callees

- `0x180010fb0`

## import_xrefs

- `MSASN1!ASN1BEREncExplicitTag` at `0x180010fdb`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180010ffc`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18001105a`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800110b0`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180010fdb`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180010ffc`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18001105a`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800110b0`
- `MSASN1!ASN1BEREncS32` at `0x18001101a`
- `MSASN1!ASN1BEREncS32` at `0x180011078`
- `MSASN1!ASN1BEREncS32` at `0x18001101a`
- `MSASN1!ASN1BEREncS32` at `0x180011078`
- `MSASN1!ASN1DEREncOctetString` at `0x1800110d0`
- `MSASN1!ASN1DEREncOctetString` at `0x1800110d0`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180011035`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180011093`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800110e7`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800110fe`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180011035`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180011093`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800110e7`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800110fe`

## pseudocode

```c
__int64 __fastcall ASN1Enc_KERB_ENCRYPTED_DATA(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  unsigned int v7; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v8; // [rsp+48h] [rbp+20h] BYREF

  v3 = 0;
  v8 = 0;
  v7 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( !(unsigned int)ASN1BEREncExplicitTag(a1, a2, &v8)
    || !(unsigned int)ASN1BEREncExplicitTag(a1, 0x80000000LL, &v7)
    || !(unsigned int)ASN1BEREncS32(a1, 2, *(unsigned int *)(a3 + 4))
    || !(unsigned int)ASN1BEREncEndOfContents(a1, v7)
    || *(char *)a3 < 0
    && (!(unsigned int)ASN1BEREncExplicitTag(a1, 2147483649LL, &v7)
     || !(unsigned int)ASN1BEREncS32(a1, 2, *(unsigned int *)(a3 + 8))
     || !(unsigned int)ASN1BEREncEndOfContents(a1, v7))
    || !(unsigned int)ASN1BEREncExplicitTag(a1, 2147483650LL, &v7)
    || !(unsigned int)ASN1DEREncOctetString(a1, 4, *(unsigned int *)(a3 + 16), *(_QWORD *)(a3 + 24))
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
0x180010fb0  mov     rax, rsp
0x180010fb3  mov     [rax+8], rbx
0x180010fb7  mov     [rax+18h], rsi
0x180010fbb  push    rdi
0x180010fbc  sub     rsp, 20h
0x180010fc0  xor     ebx, ebx
0x180010fc2  mov     rsi, r8
0x180010fc5  mov     [rax+20h], ebx
0x180010fc8  lea     r8, [rsp+28h+arg_18]
0x180010fcd  mov     [rax+10h], ebx
0x180010fd0  test    edx, edx
0x180010fd2  mov     rdi, rcx
0x180010fd5  lea     eax, [rbx+10h]
0x180010fd8  cmovz   edx, eax
0x180010fdb  call    cs:__imp_ASN1BEREncExplicitTag
0x180010fe2  nop     dword ptr [rax+rax+00h]
0x180010fe7  test    eax, eax
0x180010fe9  jz      loc_180011113
0x180010fef  lea     r8, [rsp+28h+arg_8]
0x180010ff4  mov     edx, 80000000h
0x180010ff9  mov     rcx, rdi
0x180010ffc  call    cs:__imp_ASN1BEREncExplicitTag
0x180011003  nop     dword ptr [rax+rax+00h]
0x180011008  test    eax, eax
0x18001100a  jz      loc_180011113
0x180011010  mov     r8d, [rsi+4]
0x180011014  lea     edx, [rbx+2]
0x180011017  mov     rcx, rdi
0x18001101a  call    cs:__imp_ASN1BEREncS32
0x180011021  nop     dword ptr [rax+rax+00h]
0x180011026  test    eax, eax
0x180011028  jz      loc_180011113
0x18001102e  mov     edx, [rsp+28h+arg_8]
0x180011032  mov     rcx, rdi
0x180011035  call    cs:__imp_ASN1BEREncEndOfContents
0x18001103c  nop     dword ptr [rax+rax+00h]
0x180011041  test    eax, eax
0x180011043  jz      loc_180011113
0x180011049  cmp     [rsi], bl
0x18001104b  jge     short loc_1800110A3
0x18001104d  lea     r8, [rsp+28h+arg_8]
0x180011052  mov     edx, 80000001h
0x180011057  mov     rcx, rdi
0x18001105a  call    cs:__imp_ASN1BEREncExplicitTag
0x180011061  nop     dword ptr [rax+rax+00h]
0x180011066  test    eax, eax
0x180011068  jz      loc_180011113
0x18001106e  mov     r8d, [rsi+8]
0x180011072  lea     edx, [rbx+2]
0x180011075  mov     rcx, rdi
0x180011078  call    cs:__imp_ASN1BEREncS32
0x18001107f  nop     dword ptr [rax+rax+00h]
0x180011084  test    eax, eax
0x180011086  jz      loc_180011113
0x18001108c  mov     edx, [rsp+28h+arg_8]
0x180011090  mov     rcx, rdi
0x180011093  call    cs:__imp_ASN1BEREncEndOfContents
0x18001109a  nop     dword ptr [rax+rax+00h]
0x18001109f  test    eax, eax
0x1800110a1  jz      short loc_180011113
0x1800110a3  lea     r8, [rsp+28h+arg_8]
0x1800110a8  mov     edx, 80000002h
0x1800110ad  mov     rcx, rdi
0x1800110b0  call    cs:__imp_ASN1BEREncExplicitTag
0x1800110b7  nop     dword ptr [rax+rax+00h]
0x1800110bc  test    eax, eax
0x1800110be  jz      short loc_180011113
0x1800110c0  mov     r9, [rsi+18h]
0x1800110c4  mov     edx, 4
0x1800110c9  mov     r8d, [rsi+10h]
0x1800110cd  mov     rcx, rdi
0x1800110d0  call    cs:__imp_ASN1DEREncOctetString
0x1800110d7  nop     dword ptr [rax+rax+00h]
0x1800110dc  test    eax, eax
0x1800110de  jz      short loc_180011113
0x1800110e0  mov     edx, [rsp+28h+arg_8]
0x1800110e4  mov     rcx, rdi
0x1800110e7  call    cs:__imp_ASN1BEREncEndOfContents
0x1800110ee  nop     dword ptr [rax+rax+00h]
0x1800110f3  test    eax, eax
0x1800110f5  jz      short loc_180011113
0x1800110f7  mov     edx, [rsp+28h+arg_18]
0x1800110fb  mov     rcx, rdi
0x1800110fe  call    cs:__imp_ASN1BEREncEndOfContents
0x180011105  nop     dword ptr [rax+rax+00h]
0x18001110a  test    eax, eax
0x18001110c  setnz   bl
0x18001110f  mov     eax, ebx
0x180011111  jmp     short loc_180011115
0x180011113  xor     eax, eax
0x180011115  mov     rbx, [rsp+28h+arg_0]
0x18001111a  mov     rsi, [rsp+28h+arg_10]
0x18001111f  add     rsp, 20h
0x180011123  pop     rdi
0x180011124  retn
```
