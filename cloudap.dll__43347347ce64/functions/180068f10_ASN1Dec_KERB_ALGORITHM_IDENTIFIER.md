# ASN1Dec_KERB_ALGORITHM_IDENTIFIER

- ea: `0x180068f10`
- end: `0x180068fc5`
- name: `ASN1Dec_KERB_ALGORITHM_IDENTIFIER`
- size: `181`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180069c58`
- `0x1800705d8`
- `0x180070a28`
- `0x180071f34`
- `0x180072fb0`

## callees

- `0x180068f10`

## import_xrefs

- `MSASN1!ASN1BERDecObjectIdentifier` at `0x180068f66`
- `MSASN1!ASN1BERDecObjectIdentifier` at `0x180068f66`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180068fa7`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180068fa7`
- `MSASN1!ASN1BERDecPeekTag` at `0x180068f7a`
- `MSASN1!ASN1BERDecPeekTag` at `0x180068f7a`
- `MSASN1!ASN1BERDecOpenType2` at `0x180068f90`
- `MSASN1!ASN1BERDecOpenType2` at `0x180068f90`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180068f4c`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180068f4c`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_KERB_ALGORITHM_IDENTIFIER(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF
  int v9; // [rsp+48h] [rbp+10h] BYREF
  __int64 v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  v8[0] = 0;
  v9 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( (unsigned int)ASN1BERDecExplicitTag(a1, a2, &v10, v8)
    && (v5 = v10, *a3 = 0, (unsigned int)ASN1BERDecObjectIdentifier(v5, 6, a3 + 8))
    && (!(unsigned int)ASN1BERDecPeekTag(v10, &v9)
     || (v6 = v10, *a3 |= 0x80u, (unsigned int)ASN1BERDecOpenType2(v6, a3 + 16))) )
  {
    return (unsigned int)ASN1BERDecEndOfContents(a1, v10, v8[0]) != 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180068f10  mov     r11, rsp
0x180068f13  mov     [r11+8], rbx
0x180068f17  push    rdi
0x180068f18  sub     rsp, 30h
0x180068f1c  test    edx, edx
0x180068f1e  mov     qword ptr [r11+20h], 0
0x180068f26  mov     eax, 10h
0x180068f2b  mov     qword ptr [r11-18h], 0
0x180068f33  mov     rbx, r8
0x180068f36  mov     [rsp+38h+arg_8], 0
0x180068f3e  cmovz   edx, eax
0x180068f41  lea     r9, [r11-18h]
0x180068f45  lea     r8, [r11+20h]
0x180068f49  mov     rdi, rcx
0x180068f4c  call    cs:__imp_ASN1BERDecExplicitTag
0x180068f52  test    eax, eax
0x180068f54  jz      short loc_180068FB8
0x180068f56  mov     rcx, [rsp+38h+arg_18]
0x180068f5b  lea     r8, [rbx+8]
0x180068f5f  xor     eax, eax
0x180068f61  mov     [rbx], al
0x180068f63  lea     edx, [rax+6]
0x180068f66  call    cs:__imp_ASN1BERDecObjectIdentifier
0x180068f6c  test    eax, eax
0x180068f6e  jz      short loc_180068FB8
0x180068f70  mov     rcx, [rsp+38h+arg_18]
0x180068f75  lea     rdx, [rsp+38h+arg_8]
0x180068f7a  call    cs:__imp_ASN1BERDecPeekTag
0x180068f80  test    eax, eax
0x180068f82  jz      short loc_180068F9A
0x180068f84  mov     rcx, [rsp+38h+arg_18]
0x180068f89  lea     rdx, [rbx+10h]
0x180068f8d  or      byte ptr [rbx], 80h
0x180068f90  call    cs:__imp_ASN1BERDecOpenType2
0x180068f96  test    eax, eax
0x180068f98  jz      short loc_180068FB8
0x180068f9a  mov     r8, [rsp+38h+var_18]
0x180068f9f  mov     rcx, rdi
0x180068fa2  mov     rdx, [rsp+38h+arg_18]
0x180068fa7  call    cs:__imp_ASN1BERDecEndOfContents
0x180068fad  xor     ecx, ecx
0x180068faf  test    eax, eax
0x180068fb1  setnz   cl
0x180068fb4  mov     eax, ecx
0x180068fb6  jmp     short loc_180068FBA
0x180068fb8  xor     eax, eax
0x180068fba  mov     rbx, [rsp+38h+arg_0]
0x180068fbf  add     rsp, 30h
0x180068fc3  pop     rdi
0x180068fc4  retn
```
