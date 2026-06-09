# ASN1Enc_KERB_PRINCIPAL_NAME

- ea: `0x180014614`
- end: `0x1800146d8`
- name: `ASN1Enc_KERB_PRINCIPAL_NAME`
- size: `196`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f510`
- `0x18000fd50`
- `0x18001008c`
- `0x18001112c`
- `0x1800119d0`
- `0x180012030`
- `0x1800129b8`
- `0x180012e78`
- `0x1800134c8`
- `0x1800137b0`
- `0x1800140a0`
- `0x1800142c0`
- `0x1800143e8`
- `0x180015910`
- `0x180015ca0`
- `0x180015e90`
- `0x1800161c0`
- `0x1800164e4`
- `0x180017710`

## callees

- `0x180014614`
- `0x1800146e0`

## import_xrefs

- `MSASN1!ASN1BEREncExplicitTag` at `0x18001463c`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180014659`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18001463c`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180014659`
- `MSASN1!ASN1BEREncS32` at `0x180014672`
- `MSASN1!ASN1BEREncS32` at `0x180014672`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180014689`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800146b0`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180014689`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800146b0`

## pseudocode

```c
__int64 __fastcall ASN1Enc_KERB_PRINCIPAL_NAME(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v3; // ebx
  __int64 v6; // rdx
  unsigned int v8; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v9; // [rsp+48h] [rbp+20h] BYREF

  v3 = 0;
  v9 = 0;
  v8 = 0;
  if ( !(unsigned int)ASN1BEREncExplicitTag(a1, 16, &v9)
    || !(unsigned int)ASN1BEREncExplicitTag(a1, 0x80000000LL, &v8)
    || !(unsigned int)ASN1BEREncS32(a1, 2, *a3)
    || !(unsigned int)ASN1BEREncEndOfContents(a1, v8)
    || !(unsigned int)ASN1Enc_KERB_PRINCIPAL_NAME_name_string(a1, v6, a3 + 2) )
  {
    return 0;
  }
  LOBYTE(v3) = (unsigned int)ASN1BEREncEndOfContents(a1, v9) != 0;
  return v3;
}

```

## disassembly

```asm
0x180014614  mov     rax, rsp
0x180014617  mov     [rax+8], rbx
0x18001461b  mov     [rax+18h], rsi
0x18001461f  mov     [rax+10h], edx
0x180014622  push    rdi
0x180014623  sub     rsp, 20h
0x180014627  xor     ebx, ebx
0x180014629  mov     rsi, r8
0x18001462c  lea     r8, [rax+20h]
0x180014630  mov     [rax+20h], ebx
0x180014633  mov     rdi, rcx
0x180014636  mov     [rax+10h], ebx
0x180014639  lea     edx, [rbx+10h]
0x18001463c  call    cs:__imp_ASN1BEREncExplicitTag
0x180014643  nop     dword ptr [rax+rax+00h]
0x180014648  test    eax, eax
0x18001464a  jz      short loc_1800146C5
0x18001464c  lea     r8, [rsp+28h+arg_8]
0x180014651  mov     edx, 80000000h
0x180014656  mov     rcx, rdi
0x180014659  call    cs:__imp_ASN1BEREncExplicitTag
0x180014660  nop     dword ptr [rax+rax+00h]
0x180014665  test    eax, eax
0x180014667  jz      short loc_1800146C5
0x180014669  mov     r8d, [rsi]
0x18001466c  lea     edx, [rbx+2]
0x18001466f  mov     rcx, rdi
0x180014672  call    cs:__imp_ASN1BEREncS32
0x180014679  nop     dword ptr [rax+rax+00h]
0x18001467e  test    eax, eax
0x180014680  jz      short loc_1800146C5
0x180014682  mov     edx, [rsp+28h+arg_8]
0x180014686  mov     rcx, rdi
0x180014689  call    cs:__imp_ASN1BEREncEndOfContents
0x180014690  nop     dword ptr [rax+rax+00h]
0x180014695  test    eax, eax
0x180014697  jz      short loc_1800146C5
0x180014699  lea     r8, [rsi+8]
0x18001469d  mov     rcx, rdi
0x1800146a0  call    ASN1Enc_KERB_PRINCIPAL_NAME_name_string
0x1800146a5  test    eax, eax
0x1800146a7  jz      short loc_1800146C5
0x1800146a9  mov     edx, [rsp+28h+arg_18]
0x1800146ad  mov     rcx, rdi
0x1800146b0  call    cs:__imp_ASN1BEREncEndOfContents
0x1800146b7  nop     dword ptr [rax+rax+00h]
0x1800146bc  test    eax, eax
0x1800146be  setnz   bl
0x1800146c1  mov     eax, ebx
0x1800146c3  jmp     short loc_1800146C7
0x1800146c5  xor     eax, eax
0x1800146c7  mov     rbx, [rsp+28h+arg_0]
0x1800146cc  mov     rsi, [rsp+28h+arg_10]
0x1800146d1  add     rsp, 20h
0x1800146d5  pop     rdi
0x1800146d6  retn
```
