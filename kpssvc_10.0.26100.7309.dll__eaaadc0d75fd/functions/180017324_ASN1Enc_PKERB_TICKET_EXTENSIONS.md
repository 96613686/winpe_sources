# ASN1Enc_PKERB_TICKET_EXTENSIONS

- ea: `0x180017324`
- end: `0x180017482`
- name: `ASN1Enc_PKERB_TICKET_EXTENSIONS`
- size: `350`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001008c`
- `0x18001112c`
- `0x1800119d0`
- `0x180012e78`
- `0x180015e90`

## callees

- `0x180017324`

## import_xrefs

- `MSASN1!ASN1BEREncExplicitTag` at `0x180017349`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18001736c`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18001738d`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800173e9`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180017349`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18001736c`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18001738d`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800173e9`
- `MSASN1!ASN1BEREncS32` at `0x1800173ad`
- `MSASN1!ASN1BEREncS32` at `0x1800173ad`
- `MSASN1!ASN1DEREncOctetString` at `0x180017409`
- `MSASN1!ASN1DEREncOctetString` at `0x180017409`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800173c8`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180017420`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180017437`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001745a`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800173c8`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180017420`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180017437`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001745a`

## pseudocode

```c
__int64 __fastcall ASN1Enc_PKERB_TICKET_EXTENSIONS(__int64 a1, unsigned int a2, __int64 **a3)
{
  unsigned int v3; // ebx
  int i; // eax
  _DWORD v8[6]; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v9; // [rsp+48h] [rbp+10h] BYREF
  unsigned int v10; // [rsp+58h] [rbp+20h] BYREF

  v9 = a2;
  v3 = 0;
  v8[0] = 0;
  for ( i = ASN1BEREncExplicitTag(a1, 16, v8); i; i = ASN1BEREncEndOfContents(a1, v10) )
  {
    a3 = (__int64 **)*a3;
    if ( !a3 )
    {
      LOBYTE(v3) = (unsigned int)ASN1BEREncEndOfContents(a1, v8[0]) != 0;
      return v3;
    }
    v10 = 0;
    v9 = 0;
    if ( !(unsigned int)ASN1BEREncExplicitTag(a1, 16, &v10)
      || !(unsigned int)ASN1BEREncExplicitTag(a1, 0x80000000LL, &v9)
      || !(unsigned int)ASN1BEREncS32(a1, 2, *((unsigned int *)a3 + 2))
      || !(unsigned int)ASN1BEREncEndOfContents(a1, v9)
      || !(unsigned int)ASN1BEREncExplicitTag(a1, 2147483649LL, &v9)
      || !(unsigned int)ASN1DEREncOctetString(a1, 4, *((unsigned int *)a3 + 4), a3[3])
      || !(unsigned int)ASN1BEREncEndOfContents(a1, v9) )
    {
      break;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180017324  mov     rax, rsp
0x180017327  mov     [rax+8], rbx
0x18001732b  mov     [rax+18h], rsi
0x18001732f  mov     [rax+10h], edx
0x180017332  push    rdi
0x180017333  sub     rsp, 30h
0x180017337  xor     ebx, ebx
0x180017339  mov     rsi, r8
0x18001733c  lea     r8, [rax-18h]
0x180017340  mov     [rax-18h], ebx
0x180017343  mov     rdi, rcx
0x180017346  lea     edx, [rbx+10h]
0x180017349  call    cs:__imp_ASN1BEREncExplicitTag
0x180017350  nop     dword ptr [rax+rax+00h]
0x180017355  jmp     loc_180017443
0x18001735a  lea     r8, [rsp+38h+arg_18]
0x18001735f  mov     [rsp+38h+arg_18], ebx
0x180017363  mov     edx, 10h
0x180017368  mov     [rsp+38h+arg_8], ebx
0x18001736c  call    cs:__imp_ASN1BEREncExplicitTag
0x180017373  nop     dword ptr [rax+rax+00h]
0x180017378  test    eax, eax
0x18001737a  jz      loc_18001746F
0x180017380  lea     r8, [rsp+38h+arg_8]
0x180017385  mov     edx, 80000000h
0x18001738a  mov     rcx, rdi
0x18001738d  call    cs:__imp_ASN1BEREncExplicitTag
0x180017394  nop     dword ptr [rax+rax+00h]
0x180017399  test    eax, eax
0x18001739b  jz      loc_18001746F
0x1800173a1  mov     r8d, [rsi+8]
0x1800173a5  mov     edx, 2
0x1800173aa  mov     rcx, rdi
0x1800173ad  call    cs:__imp_ASN1BEREncS32
0x1800173b4  nop     dword ptr [rax+rax+00h]
0x1800173b9  test    eax, eax
0x1800173bb  jz      loc_18001746F
0x1800173c1  mov     edx, [rsp+38h+arg_8]
0x1800173c5  mov     rcx, rdi
0x1800173c8  call    cs:__imp_ASN1BEREncEndOfContents
0x1800173cf  nop     dword ptr [rax+rax+00h]
0x1800173d4  test    eax, eax
0x1800173d6  jz      loc_18001746F
0x1800173dc  lea     r8, [rsp+38h+arg_8]
0x1800173e1  mov     edx, 80000001h
0x1800173e6  mov     rcx, rdi
0x1800173e9  call    cs:__imp_ASN1BEREncExplicitTag
0x1800173f0  nop     dword ptr [rax+rax+00h]
0x1800173f5  test    eax, eax
0x1800173f7  jz      short loc_18001746F
0x1800173f9  mov     r9, [rsi+18h]
0x1800173fd  mov     edx, 4
0x180017402  mov     r8d, [rsi+10h]
0x180017406  mov     rcx, rdi
0x180017409  call    cs:__imp_ASN1DEREncOctetString
0x180017410  nop     dword ptr [rax+rax+00h]
0x180017415  test    eax, eax
0x180017417  jz      short loc_18001746F
0x180017419  mov     edx, [rsp+38h+arg_8]
0x18001741d  mov     rcx, rdi
0x180017420  call    cs:__imp_ASN1BEREncEndOfContents
0x180017427  nop     dword ptr [rax+rax+00h]
0x18001742c  test    eax, eax
0x18001742e  jz      short loc_18001746F
0x180017430  mov     edx, [rsp+38h+arg_18]
0x180017434  mov     rcx, rdi
0x180017437  call    cs:__imp_ASN1BEREncEndOfContents
0x18001743e  nop     dword ptr [rax+rax+00h]
0x180017443  test    eax, eax
0x180017445  jz      short loc_18001746F
0x180017447  mov     rsi, [rsi]
0x18001744a  mov     rcx, rdi
0x18001744d  test    rsi, rsi
0x180017450  jnz     loc_18001735A
0x180017456  mov     edx, [rsp+38h+var_18]
0x18001745a  call    cs:__imp_ASN1BEREncEndOfContents
0x180017461  nop     dword ptr [rax+rax+00h]
0x180017466  test    eax, eax
0x180017468  setnz   bl
0x18001746b  mov     eax, ebx
0x18001746d  jmp     short loc_180017471
0x18001746f  xor     eax, eax
0x180017471  mov     rbx, [rsp+38h+arg_0]
0x180017476  mov     rsi, [rsp+38h+arg_10]
0x18001747b  add     rsp, 30h
0x18001747f  pop     rdi
0x180017480  retn
```
