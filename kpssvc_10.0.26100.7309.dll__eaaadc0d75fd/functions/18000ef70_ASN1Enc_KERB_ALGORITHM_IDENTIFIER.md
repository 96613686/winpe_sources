# ASN1Enc_KERB_ALGORITHM_IDENTIFIER

- ea: `0x18000ef70`
- end: `0x18000f00c`
- name: `ASN1Enc_KERB_ALGORITHM_IDENTIFIER`
- size: `156`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fb80`
- `0x18001545c`
- `0x180015874`
- `0x180016a74`
- `0x180017960`

## callees

- `0x18000ef70`

## import_xrefs

- `MSASN1!ASN1BEREncExplicitTag` at `0x18000ef98`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000ef98`
- `MSASN1!ASN1BEREncObjectIdentifier` at `0x18000efb2`
- `MSASN1!ASN1BEREncObjectIdentifier` at `0x18000efb2`
- `MSASN1!ASN1BEREncOpenType` at `0x18000efcd`
- `MSASN1!ASN1BEREncOpenType` at `0x18000efcd`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000efe4`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000efe4`

## pseudocode

```c
__int64 __fastcall ASN1Enc_KERB_ALGORITHM_IDENTIFIER(__int64 a1, __int64 a2, char *a3)
{
  unsigned int v3; // ebx
  unsigned int v7; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v7 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( !(unsigned int)ASN1BEREncExplicitTag(a1, a2, &v7)
    || !(unsigned int)ASN1BEREncObjectIdentifier(a1, 6, a3 + 8)
    || *a3 < 0 && !(unsigned int)ASN1BEREncOpenType(a1, a3 + 16) )
  {
    return 0;
  }
  LOBYTE(v3) = (unsigned int)ASN1BEREncEndOfContents(a1, v7) != 0;
  return v3;
}

```

## disassembly

```asm
0x18000ef70  mov     [rsp+arg_0], rbx
0x18000ef75  mov     [rsp+arg_10], rsi
0x18000ef7a  push    rdi
0x18000ef7b  sub     rsp, 20h
0x18000ef7f  xor     ebx, ebx
0x18000ef81  mov     rdi, r8
0x18000ef84  test    edx, edx
0x18000ef86  mov     [rsp+28h+arg_8], ebx
0x18000ef8a  lea     r8, [rsp+28h+arg_8]
0x18000ef8f  mov     rsi, rcx
0x18000ef92  lea     eax, [rbx+10h]
0x18000ef95  cmovz   edx, eax
0x18000ef98  call    cs:__imp_ASN1BEREncExplicitTag
0x18000ef9f  nop     dword ptr [rax+rax+00h]
0x18000efa4  test    eax, eax
0x18000efa6  jz      short loc_18000EFF9
0x18000efa8  lea     r8, [rdi+8]
0x18000efac  mov     rcx, rsi
0x18000efaf  lea     edx, [rbx+6]
0x18000efb2  call    cs:__imp_ASN1BEREncObjectIdentifier
0x18000efb9  nop     dword ptr [rax+rax+00h]
0x18000efbe  test    eax, eax
0x18000efc0  jz      short loc_18000EFF9
0x18000efc2  cmp     [rdi], bl
0x18000efc4  jge     short loc_18000EFDD
0x18000efc6  lea     rdx, [rdi+10h]
0x18000efca  mov     rcx, rsi
0x18000efcd  call    cs:__imp_ASN1BEREncOpenType
0x18000efd4  nop     dword ptr [rax+rax+00h]
0x18000efd9  test    eax, eax
0x18000efdb  jz      short loc_18000EFF9
0x18000efdd  mov     edx, [rsp+28h+arg_8]
0x18000efe1  mov     rcx, rsi
0x18000efe4  call    cs:__imp_ASN1BEREncEndOfContents
0x18000efeb  nop     dword ptr [rax+rax+00h]
0x18000eff0  test    eax, eax
0x18000eff2  setnz   bl
0x18000eff5  mov     eax, ebx
0x18000eff7  jmp     short loc_18000EFFB
0x18000eff9  xor     eax, eax
0x18000effb  mov     rbx, [rsp+28h+arg_0]
0x18000f000  mov     rsi, [rsp+28h+arg_10]
0x18000f005  add     rsp, 20h
0x18000f009  pop     rdi
0x18000f00a  retn
```
