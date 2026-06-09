# ASN1Dec_PKERB_TICKET_EXTENSIONS

- ea: `0x18003f368`
- end: `0x18003f438`
- name: `ASN1Dec_PKERB_TICKET_EXTENSIONS`
- size: `208`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180013260`
- `0x180015940`
- `0x18003c2f0`
- `0x18003c980`

## callees

- `0x180019550`
- `0x18003f368`

## import_xrefs

- `MSASN1!ASN1DecAlloc` at `0x18003f3df`
- `MSASN1!ASN1DecAlloc` at `0x18003f3df`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18003f415`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18003f415`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x18003f3ba`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x18003f3ba`
- `MSASN1!ASN1BERDecPeekTag` at `0x18003f3cc`
- `MSASN1!ASN1BERDecPeekTag` at `0x18003f3cc`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18003f3a8`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18003f3a8`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_PKERB_TICKET_EXTENSIONS(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v8; // [rsp+20h] [rbp-10h] BYREF
  int v9; // [rsp+48h] [rbp+18h] BYREF
  __int64 v10; // [rsp+58h] [rbp+28h] BYREF

  v10 = 0;
  v8 = 0;
  v9 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, 16, &v10, &v8) )
    return 0;
  while ( (unsigned int)ASN1BERDecNotEndOfContents(v10, v8) )
  {
    if ( !(unsigned int)ASN1BERDecPeekTag(v10, &v9) )
      return 0;
    v5 = ASN1DecAlloc(v10, 32);
    *a3 = v5;
    if ( !v5 || !(unsigned int)ASN1Dec_PKERB_TICKET_EXTENSIONS_Seq(v10, v6, v5 + 8) )
      return 0;
    a3 = (__int64 *)*a3;
  }
  *a3 = 0;
  return (unsigned int)ASN1BERDecEndOfContents(a1, v10, v8) != 0;
}

```

## disassembly

```asm
0x18003f368  mov     [rsp-8+arg_0], rbx
0x18003f36d  mov     [rsp-8+arg_10], rdi
0x18003f372  mov     [rsp-8+arg_8], edx
0x18003f376  push    rbp
0x18003f377  mov     rbp, rsp
0x18003f37a  sub     rsp, 30h
0x18003f37e  mov     rbx, r8
0x18003f381  mov     [rbp+arg_18], 0
0x18003f389  lea     r8, [rbp+arg_18]
0x18003f38d  mov     [rbp+var_10], 0
0x18003f395  lea     r9, [rbp+var_10]
0x18003f399  mov     [rbp+arg_8], 0
0x18003f3a0  mov     edx, 10h
0x18003f3a5  mov     rdi, rcx
0x18003f3a8  call    cs:__imp_ASN1BERDecExplicitTag
0x18003f3ae  test    eax, eax
0x18003f3b0  jz      short loc_18003F426
0x18003f3b2  mov     rdx, [rbp+var_10]
0x18003f3b6  mov     rcx, [rbp+arg_18]
0x18003f3ba  call    cs:__imp_ASN1BERDecNotEndOfContents
0x18003f3c0  test    eax, eax
0x18003f3c2  jz      short loc_18003F403
0x18003f3c4  mov     rcx, [rbp+arg_18]
0x18003f3c8  lea     rdx, [rbp+arg_8]
0x18003f3cc  call    cs:__imp_ASN1BERDecPeekTag
0x18003f3d2  test    eax, eax
0x18003f3d4  jz      short loc_18003F426
0x18003f3d6  mov     rcx, [rbp+arg_18]
0x18003f3da  mov     edx, 20h ; ' '
0x18003f3df  call    cs:__imp_ASN1DecAlloc
0x18003f3e5  mov     [rbx], rax
0x18003f3e8  test    rax, rax
0x18003f3eb  jz      short loc_18003F426
0x18003f3ed  mov     rcx, [rbp+arg_18]
0x18003f3f1  lea     r8, [rax+8]
0x18003f3f5  call    ASN1Dec_PKERB_TICKET_EXTENSIONS_Seq
0x18003f3fa  test    eax, eax
0x18003f3fc  jz      short loc_18003F426
0x18003f3fe  mov     rbx, [rbx]
0x18003f401  jmp     short loc_18003F3B2
0x18003f403  mov     qword ptr [rbx], 0
0x18003f40a  mov     rcx, rdi
0x18003f40d  mov     r8, [rbp+var_10]
0x18003f411  mov     rdx, [rbp+arg_18]
0x18003f415  call    cs:__imp_ASN1BERDecEndOfContents
0x18003f41b  xor     ecx, ecx
0x18003f41d  test    eax, eax
0x18003f41f  setnz   cl
0x18003f422  mov     eax, ecx
0x18003f424  jmp     short loc_18003F428
0x18003f426  xor     eax, eax
0x18003f428  mov     rbx, [rsp+30h+arg_0]
0x18003f42d  mov     rdi, [rsp+30h+arg_10]
0x18003f432  add     rsp, 30h
0x18003f436  pop     rbp
0x18003f437  retn
```
