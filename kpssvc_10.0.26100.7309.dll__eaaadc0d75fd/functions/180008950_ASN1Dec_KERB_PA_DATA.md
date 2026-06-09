# ASN1Dec_KERB_PA_DATA

- ea: `0x180008950`
- end: `0x180008a8d`
- name: `ASN1Dec_KERB_PA_DATA`
- size: `317`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005f90`
- `0x18000771c`
- `0x180007b30`
- `0x1800085d8`
- `0x18000cb74`
- `0x18000dd80`

## callees

- `0x180008950`

## import_xrefs

- `MSASN1!ASN1BERDecOctetString` at `0x180008a29`
- `MSASN1!ASN1BERDecOctetString` at `0x180008a29`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800089ed`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180008a45`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180008a60`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800089ed`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180008a45`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180008a60`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000898a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800089af`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180008a0e`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000898a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800089af`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180008a0e`
- `MSASN1!ASN1BERDecS32Val` at `0x1800089cd`
- `MSASN1!ASN1BERDecS32Val` at `0x1800089cd`

## pseudocode

```c
__int64 __fastcall ASN1Dec_KERB_PA_DATA(__int64 a1, __int64 a2, __int64 a3)
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
    || !(unsigned int)ASN1BERDecExplicitTag(v7, 2147483649LL, &v10, &v8)
    || !(unsigned int)ASN1BERDecS32Val(v10, 2, a3)
    || !(unsigned int)ASN1BERDecEndOfContents(v7, v10, v8)
    || !(unsigned int)ASN1BERDecExplicitTag(v7, 2147483650LL, &v10, &v8)
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
0x180008950  mov     [rsp-8+arg_0], rbx
0x180008955  mov     [rsp-8+arg_8], rsi
0x18000895a  mov     [rsp-8+arg_10], rdi
0x18000895f  push    rbp
0x180008960  mov     rbp, rsp
0x180008963  sub     rsp, 40h
0x180008967  xor     ebx, ebx
0x180008969  lea     r9, [rbp+var_10]
0x18000896d  mov     rdi, r8
0x180008970  mov     [rbp+var_20], rbx
0x180008974  lea     r8, [rbp+var_20]
0x180008978  mov     [rbp+var_10], rbx
0x18000897c  mov     rsi, rcx
0x18000897f  mov     [rbp+arg_18], rbx
0x180008983  lea     edx, [rbx+10h]
0x180008986  mov     [rbp+var_18], rbx
0x18000898a  call    cs:__imp_ASN1BERDecExplicitTag
0x180008991  nop     dword ptr [rax+rax+00h]
0x180008996  test    eax, eax
0x180008998  jz      loc_180008A75
0x18000899e  mov     rcx, [rbp+var_20]
0x1800089a2  lea     r9, [rbp+var_18]
0x1800089a6  lea     r8, [rbp+arg_18]
0x1800089aa  mov     edx, 80000001h
0x1800089af  call    cs:__imp_ASN1BERDecExplicitTag
0x1800089b6  nop     dword ptr [rax+rax+00h]
0x1800089bb  test    eax, eax
0x1800089bd  jz      loc_180008A75
0x1800089c3  mov     rcx, [rbp+arg_18]
0x1800089c7  lea     edx, [rbx+2]
0x1800089ca  mov     r8, rdi
0x1800089cd  call    cs:__imp_ASN1BERDecS32Val
0x1800089d4  nop     dword ptr [rax+rax+00h]
0x1800089d9  test    eax, eax
0x1800089db  jz      loc_180008A75
0x1800089e1  mov     r8, [rbp+var_18]
0x1800089e5  mov     rdx, [rbp+arg_18]
0x1800089e9  mov     rcx, [rbp+var_20]
0x1800089ed  call    cs:__imp_ASN1BERDecEndOfContents
0x1800089f4  nop     dword ptr [rax+rax+00h]
0x1800089f9  test    eax, eax
0x1800089fb  jz      short loc_180008A75
0x1800089fd  mov     rcx, [rbp+var_20]
0x180008a01  lea     r9, [rbp+var_18]
0x180008a05  lea     r8, [rbp+arg_18]
0x180008a09  mov     edx, 80000002h
0x180008a0e  call    cs:__imp_ASN1BERDecExplicitTag
0x180008a15  nop     dword ptr [rax+rax+00h]
0x180008a1a  test    eax, eax
0x180008a1c  jz      short loc_180008A75
0x180008a1e  mov     rcx, [rbp+arg_18]
0x180008a22  lea     r8, [rdi+8]
0x180008a26  lea     edx, [rbx+4]
0x180008a29  call    cs:__imp_ASN1BERDecOctetString
0x180008a30  nop     dword ptr [rax+rax+00h]
0x180008a35  test    eax, eax
0x180008a37  jz      short loc_180008A75
0x180008a39  mov     r8, [rbp+var_18]
0x180008a3d  mov     rdx, [rbp+arg_18]
0x180008a41  mov     rcx, [rbp+var_20]
0x180008a45  call    cs:__imp_ASN1BERDecEndOfContents
0x180008a4c  nop     dword ptr [rax+rax+00h]
0x180008a51  test    eax, eax
0x180008a53  jz      short loc_180008A75
0x180008a55  mov     r8, [rbp+var_10]
0x180008a59  mov     rcx, rsi
0x180008a5c  mov     rdx, [rbp+var_20]
0x180008a60  call    cs:__imp_ASN1BERDecEndOfContents
0x180008a67  nop     dword ptr [rax+rax+00h]
0x180008a6c  test    eax, eax
0x180008a6e  setnz   bl
0x180008a71  mov     eax, ebx
0x180008a73  jmp     short loc_180008A77
0x180008a75  xor     eax, eax
0x180008a77  mov     rbx, [rsp+40h+arg_0]
0x180008a7c  mov     rsi, [rsp+40h+arg_8]
0x180008a81  mov     rdi, [rsp+40h+arg_10]
0x180008a86  add     rsp, 40h
0x180008a8a  pop     rbp
0x180008a8b  retn
```
