# ASN1Dec_KERB_ALGORITHM_IDENTIFIER

- ea: `0x180002ca0`
- end: `0x180002d6f`
- name: `ASN1Dec_KERB_ALGORITHM_IDENTIFIER`
- size: `207`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003bb8`
- `0x18000afe4`
- `0x18000b4c8`
- `0x18000cc9c`
- `0x18000e270`

## callees

- `0x180002ca0`

## import_xrefs

- `MSASN1!ASN1BERDecPeekTag` at `0x180002d0e`
- `MSASN1!ASN1BERDecPeekTag` at `0x180002d0e`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180002d47`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180002d47`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180002cd4`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180002cd4`
- `MSASN1!ASN1BERDecObjectIdentifier` at `0x180002cf4`
- `MSASN1!ASN1BERDecObjectIdentifier` at `0x180002cf4`
- `MSASN1!ASN1BERDecOpenType2` at `0x180002d2a`
- `MSASN1!ASN1BERDecOpenType2` at `0x180002d2a`

## pseudocode

```c
__int64 __fastcall ASN1Dec_KERB_ALGORITHM_IDENTIFIER(__int64 a1, __int64 a2, _BYTE *a3)
{
  unsigned int v3; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  _QWORD v9[3]; // [rsp+20h] [rbp-18h] BYREF
  int v10; // [rsp+48h] [rbp+10h] BYREF
  __int64 v11; // [rsp+58h] [rbp+20h] BYREF

  v3 = 0;
  v11 = 0;
  v9[0] = 0;
  v10 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, a2, &v11, v9) )
    return 0;
  v6 = v11;
  *a3 = 0;
  if ( !(unsigned int)ASN1BERDecObjectIdentifier(v6, 6, a3 + 8) )
    return 0;
  if ( (unsigned int)ASN1BERDecPeekTag(v11, &v10) )
  {
    v7 = v11;
    *a3 |= 0x80u;
    if ( !(unsigned int)ASN1BERDecOpenType2(v7, a3 + 16) )
      return 0;
  }
  LOBYTE(v3) = (unsigned int)ASN1BERDecEndOfContents(a1, v11, v9[0]) != 0;
  return v3;
}

```

## disassembly

```asm
0x180002ca0  mov     r11, rsp
0x180002ca3  mov     [r11+8], rbx
0x180002ca7  mov     [r11+18h], rsi
0x180002cab  push    rdi
0x180002cac  sub     rsp, 30h
0x180002cb0  xor     ebx, ebx
0x180002cb2  lea     r9, [r11-18h]
0x180002cb6  test    edx, edx
0x180002cb8  mov     [r11+20h], rbx
0x180002cbc  mov     rdi, r8
0x180002cbf  mov     [r11-18h], rbx
0x180002cc3  lea     r8, [r11+20h]
0x180002cc7  mov     [rsp+38h+arg_8], ebx
0x180002ccb  lea     eax, [rbx+10h]
0x180002cce  mov     rsi, rcx
0x180002cd1  cmovz   edx, eax
0x180002cd4  call    cs:__imp_ASN1BERDecExplicitTag
0x180002cdb  nop     dword ptr [rax+rax+00h]
0x180002ce0  test    eax, eax
0x180002ce2  jz      short loc_180002D5C
0x180002ce4  mov     rcx, [rsp+38h+arg_18]
0x180002ce9  lea     r8, [rdi+8]
0x180002ced  xor     eax, eax
0x180002cef  lea     edx, [rbx+6]
0x180002cf2  mov     [rdi], al
0x180002cf4  call    cs:__imp_ASN1BERDecObjectIdentifier
0x180002cfb  nop     dword ptr [rax+rax+00h]
0x180002d00  test    eax, eax
0x180002d02  jz      short loc_180002D5C
0x180002d04  mov     rcx, [rsp+38h+arg_18]
0x180002d09  lea     rdx, [rsp+38h+arg_8]
0x180002d0e  call    cs:__imp_ASN1BERDecPeekTag
0x180002d15  nop     dword ptr [rax+rax+00h]
0x180002d1a  test    eax, eax
0x180002d1c  jz      short loc_180002D3A
0x180002d1e  mov     rcx, [rsp+38h+arg_18]
0x180002d23  lea     rdx, [rdi+10h]
0x180002d27  or      byte ptr [rdi], 80h
0x180002d2a  call    cs:__imp_ASN1BERDecOpenType2
0x180002d31  nop     dword ptr [rax+rax+00h]
0x180002d36  test    eax, eax
0x180002d38  jz      short loc_180002D5C
0x180002d3a  mov     r8, [rsp+38h+var_18]
0x180002d3f  mov     rcx, rsi
0x180002d42  mov     rdx, [rsp+38h+arg_18]
0x180002d47  call    cs:__imp_ASN1BERDecEndOfContents
0x180002d4e  nop     dword ptr [rax+rax+00h]
0x180002d53  test    eax, eax
0x180002d55  setnz   bl
0x180002d58  mov     eax, ebx
0x180002d5a  jmp     short loc_180002D5E
0x180002d5c  xor     eax, eax
0x180002d5e  mov     rbx, [rsp+38h+arg_0]
0x180002d63  mov     rsi, [rsp+38h+arg_10]
0x180002d68  add     rsp, 30h
0x180002d6c  pop     rdi
0x180002d6d  retn
```
