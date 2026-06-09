# ASN1Dec_GET_LENGTH

- ea: `0x1800023c0`
- end: `0x1800023e2`
- name: `ASN1Dec_GET_LENGTH`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MSASN1!ASN1BERDecOpenType2` at `0x1800023c7`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800023c7`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_GET_LENGTH(__int64 a1, __int64 a2, __int64 a3)
{
  return (unsigned int)ASN1BERDecOpenType2(a1, a3) != 0;
}

```

## disassembly

```asm
0x1800023c0  sub     rsp, 28h
0x1800023c4  mov     rdx, r8
0x1800023c7  call    cs:__imp_ASN1BERDecOpenType2
0x1800023ce  nop     dword ptr [rax+rax+00h]
0x1800023d3  xor     ecx, ecx
0x1800023d5  test    eax, eax
0x1800023d7  setnz   cl
0x1800023da  mov     eax, ecx
0x1800023dc  add     rsp, 28h
0x1800023e0  retn
```
