# ASN1Enc_PKERB_TICKET_EXTENSIONS

- ea: `0x180042870`
- end: `0x1800428d7`
- name: `ASN1Enc_PKERB_TICKET_EXTENSIONS`
- size: `103`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180012240`
- `0x180013ec0`
- `0x1800407e0`
- `0x180041724`

## callees

- `0x180018e50`
- `0x180042870`

## import_xrefs

- `MSASN1!ASN1BEREncEndOfContents` at `0x1800428b9`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800428b9`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180042895`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180042895`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_PKERB_TICKET_EXTENSIONS(__int64 a1, __int64 a2, _QWORD *a3)
{
  int i; // eax
  __int64 v6; // rdx
  unsigned int v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  for ( i = ASN1BEREncExplicitTag(a1, 16, &v8); i; i = ASN1Enc_PKERB_TICKET_EXTENSIONS_Seq(a1, v6, a3 + 1) )
  {
    a3 = (_QWORD *)*a3;
    if ( !a3 )
      return (unsigned int)ASN1BEREncEndOfContents(a1, v8) != 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180042870  mov     rax, rsp
0x180042873  mov     [rax+8], rbx
0x180042877  mov     [rax+10h], edx
0x18004287a  push    rdi
0x18004287b  sub     rsp, 20h
0x18004287f  mov     rbx, r8
0x180042882  mov     dword ptr [rax+10h], 0
0x180042889  lea     r8, [rax+10h]
0x18004288d  mov     edx, 10h
0x180042892  mov     rdi, rcx
0x180042895  call    cs:__imp_ASN1BEREncExplicitTag
0x18004289b  test    eax, eax
0x18004289d  jz      short loc_1800428CA
0x18004289f  mov     rbx, [rbx]
0x1800428a2  mov     rcx, rdi
0x1800428a5  test    rbx, rbx
0x1800428a8  jz      short loc_1800428B5
0x1800428aa  lea     r8, [rbx+8]
0x1800428ae  call    ASN1Enc_PKERB_TICKET_EXTENSIONS_Seq
0x1800428b3  jmp     short loc_18004289B
0x1800428b5  mov     edx, [rsp+28h+arg_8]
0x1800428b9  call    cs:__imp_ASN1BEREncEndOfContents
0x1800428bf  xor     ecx, ecx
0x1800428c1  test    eax, eax
0x1800428c3  setnz   cl
0x1800428c6  mov     eax, ecx
0x1800428c8  jmp     short loc_1800428CC
0x1800428ca  xor     eax, eax
0x1800428cc  mov     rbx, [rsp+28h+arg_0]
0x1800428d1  add     rsp, 20h
0x1800428d5  pop     rdi
0x1800428d6  retn
```
