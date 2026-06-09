# ASN1Free_KERB_SUBJECT_PUBLIC_KEY_INFO

- ea: `0x180018ef8`
- end: `0x180018f2c`
- name: `ASN1Free_KERB_SUBJECT_PUBLIC_KEY_INFO`
- size: `52`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180017eb0`
- `0x180017f10`
- `0x180018600`
- `0x180018a30`
- `0x180018bb0`
- `0x180018f40`

## callees

- `0x180018ef8`

## import_xrefs

- `MSASN1!ASN1objectidentifier_free` at `0x180018f09`
- `MSASN1!ASN1objectidentifier_free` at `0x180018f09`
- `MSASN1!ASN1bitstring_free` at `0x180018f19`
- `MSASN1!ASN1bitstring_free` at `0x180018f19`

## pseudocode

```c
__int64 __fastcall ASN1Free_KERB_SUBJECT_PUBLIC_KEY_INFO(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
  {
    ASN1objectidentifier_free(a1 + 8);
    return ASN1bitstring_free(a1 + 32);
  }
  return result;
}

```

## disassembly

```asm
0x180018ef8  test    rcx, rcx
0x180018efb  jz      short locret_180018F2A
0x180018efd  push    rbx
0x180018efe  sub     rsp, 20h
0x180018f02  mov     rbx, rcx
0x180018f05  add     rcx, 8
0x180018f09  call    cs:__imp_ASN1objectidentifier_free
0x180018f10  nop     dword ptr [rax+rax+00h]
0x180018f15  lea     rcx, [rbx+20h]
0x180018f19  call    cs:__imp_ASN1bitstring_free
0x180018f20  nop     dword ptr [rax+rax+00h]
0x180018f25  add     rsp, 20h
0x180018f29  pop     rbx
0x180018f2a  retn
```
