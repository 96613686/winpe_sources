# ASN1Enc_KERB_PKCS_SIGNATURE

- ea: `0x18000ee50`
- end: `0x18000ef65`
- name: `ASN1Enc_KERB_PKCS_SIGNATURE`
- size: `277`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e8e0`
- `0x18000f510`
- `0x18001008c`
- `0x180010898`
- `0x180010950`
- `0x180010a10`
- `0x18001112c`
- `0x1800119d0`
- `0x1800135e0`
- `0x1800137b0`
- `0x180014ae0`
- `0x180014bf0`
- `0x180014d70`
- `0x1800150f0`
- `0x18001638c`
- `0x1800164e4`
- `0x180016840`
- `0x180016cc0`

## callees

- `0x18000ee50`

## import_xrefs

- `MSASN1!ASN1BEREncExplicitTag` at `0x18000ee7b`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000ee9c`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000eef1`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000ee7b`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000ee9c`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000eef1`
- `MSASN1!ASN1BEREncS32` at `0x18000eeb9`
- `MSASN1!ASN1BEREncS32` at `0x18000eeb9`
- `MSASN1!ASN1DEREncOctetString` at `0x18000ef0f`
- `MSASN1!ASN1DEREncOctetString` at `0x18000ef0f`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000eed4`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000ef26`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000ef3d`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000eed4`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000ef26`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000ef3d`

## pseudocode

```c
__int64 __fastcall ASN1Enc_KERB_PKCS_SIGNATURE(__int64 a1, __int64 a2, unsigned int *a3)
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
    || !(unsigned int)ASN1BEREncS32(a1, 2, *a3)
    || !(unsigned int)ASN1BEREncEndOfContents(a1, v7)
    || !(unsigned int)ASN1BEREncExplicitTag(a1, 2147483649LL, &v7)
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
0x18000ee50  mov     rax, rsp
0x18000ee53  mov     [rax+8], rbx
0x18000ee57  mov     [rax+18h], rsi
0x18000ee5b  push    rdi
0x18000ee5c  sub     rsp, 20h
0x18000ee60  xor     ebx, ebx
0x18000ee62  mov     rsi, r8
0x18000ee65  mov     [rax+20h], ebx
0x18000ee68  lea     r8, [rsp+28h+arg_18]
0x18000ee6d  mov     [rax+10h], ebx
0x18000ee70  test    edx, edx
0x18000ee72  mov     rdi, rcx
0x18000ee75  lea     eax, [rbx+10h]
0x18000ee78  cmovz   edx, eax
0x18000ee7b  call    cs:__imp_ASN1BEREncExplicitTag
0x18000ee82  nop     dword ptr [rax+rax+00h]
0x18000ee87  test    eax, eax
0x18000ee89  jz      loc_18000EF52
0x18000ee8f  lea     r8, [rsp+28h+arg_8]
0x18000ee94  mov     edx, 80000000h
0x18000ee99  mov     rcx, rdi
0x18000ee9c  call    cs:__imp_ASN1BEREncExplicitTag
0x18000eea3  nop     dword ptr [rax+rax+00h]
0x18000eea8  test    eax, eax
0x18000eeaa  jz      loc_18000EF52
0x18000eeb0  mov     r8d, [rsi]
0x18000eeb3  lea     edx, [rbx+2]
0x18000eeb6  mov     rcx, rdi
0x18000eeb9  call    cs:__imp_ASN1BEREncS32
0x18000eec0  nop     dword ptr [rax+rax+00h]
0x18000eec5  test    eax, eax
0x18000eec7  jz      loc_18000EF52
0x18000eecd  mov     edx, [rsp+28h+arg_8]
0x18000eed1  mov     rcx, rdi
0x18000eed4  call    cs:__imp_ASN1BEREncEndOfContents
0x18000eedb  nop     dword ptr [rax+rax+00h]
0x18000eee0  test    eax, eax
0x18000eee2  jz      short loc_18000EF52
0x18000eee4  lea     r8, [rsp+28h+arg_8]
0x18000eee9  mov     edx, 80000001h
0x18000eeee  mov     rcx, rdi
0x18000eef1  call    cs:__imp_ASN1BEREncExplicitTag
0x18000eef8  nop     dword ptr [rax+rax+00h]
0x18000eefd  test    eax, eax
0x18000eeff  jz      short loc_18000EF52
0x18000ef01  mov     r9, [rsi+10h]
0x18000ef05  lea     edx, [rbx+4]
0x18000ef08  mov     r8d, [rsi+8]
0x18000ef0c  mov     rcx, rdi
0x18000ef0f  call    cs:__imp_ASN1DEREncOctetString
0x18000ef16  nop     dword ptr [rax+rax+00h]
0x18000ef1b  test    eax, eax
0x18000ef1d  jz      short loc_18000EF52
0x18000ef1f  mov     edx, [rsp+28h+arg_8]
0x18000ef23  mov     rcx, rdi
0x18000ef26  call    cs:__imp_ASN1BEREncEndOfContents
0x18000ef2d  nop     dword ptr [rax+rax+00h]
0x18000ef32  test    eax, eax
0x18000ef34  jz      short loc_18000EF52
0x18000ef36  mov     edx, [rsp+28h+arg_18]
0x18000ef3a  mov     rcx, rdi
0x18000ef3d  call    cs:__imp_ASN1BEREncEndOfContents
0x18000ef44  nop     dword ptr [rax+rax+00h]
0x18000ef49  test    eax, eax
0x18000ef4b  setnz   bl
0x18000ef4e  mov     eax, ebx
0x18000ef50  jmp     short loc_18000EF54
0x18000ef52  xor     eax, eax
0x18000ef54  mov     rbx, [rsp+28h+arg_0]
0x18000ef59  mov     rsi, [rsp+28h+arg_10]
0x18000ef5e  add     rsp, 20h
0x18000ef62  pop     rdi
0x18000ef63  retn
```
