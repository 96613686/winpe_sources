# ASN1Enc_GET_LENGTH

- ea: `0x18000e8b0`
- end: `0x18000e8d2`
- name: `ASN1Enc_GET_LENGTH`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MSASN1!ASN1BEREncOpenType` at `0x18000e8b7`
- `MSASN1!ASN1BEREncOpenType` at `0x18000e8b7`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_GET_LENGTH(__int64 a1, __int64 a2, __int64 a3)
{
  return (unsigned int)ASN1BEREncOpenType(a1, a3) != 0;
}

```

## disassembly

```asm
0x18000e8b0  sub     rsp, 28h
0x18000e8b4  mov     rdx, r8
0x18000e8b7  call    cs:__imp_ASN1BEREncOpenType
0x18000e8be  nop     dword ptr [rax+rax+00h]
0x18000e8c3  xor     ecx, ecx
0x18000e8c5  test    eax, eax
0x18000e8c7  setnz   cl
0x18000e8ca  mov     eax, ecx
0x18000e8cc  add     rsp, 28h
0x18000e8d0  retn
```
