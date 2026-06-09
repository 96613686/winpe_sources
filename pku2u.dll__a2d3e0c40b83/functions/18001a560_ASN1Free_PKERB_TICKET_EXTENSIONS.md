# ASN1Free_PKERB_TICKET_EXTENSIONS

- ea: `0x18001a560`
- end: `0x18001a5a9`
- name: `ASN1Free_PKERB_TICKET_EXTENSIONS`
- size: `73`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800192c0`
- `0x1800200a0`
- `0x1800209c8`
- `0x180042d80`
- `0x180042eec`
- `0x180042fb0`

## callees

- `0x18001a560`

## import_xrefs

- `MSASN1!ASN1Free` at `0x18001a590`
- `MSASN1!ASN1Free` at `0x18001a590`
- `MSASN1!ASN1octetstring_free` at `0x18001a584`
- `MSASN1!ASN1octetstring_free` at `0x18001a584`

## pseudocode

```c
__int64 __fastcall ASN1Free_PKERB_TICKET_EXTENSIONS(_QWORD **a1)
{
  _QWORD *v1; // rdi
  _QWORD *v2; // rbx
  __int64 result; // rax

  if ( a1 )
  {
    v1 = *a1;
    if ( *a1 )
    {
      do
      {
        if ( v1 != (_QWORD *)-8LL )
          ASN1octetstring_free(v1 + 2);
        v2 = (_QWORD *)*v1;
        result = ASN1Free(v1);
        v1 = v2;
      }
      while ( v2 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001a560  test    rcx, rcx
0x18001a563  jz      short locret_18001A5A8
0x18001a565  mov     [rsp+arg_0], rbx
0x18001a56a  push    rdi
0x18001a56b  sub     rsp, 20h
0x18001a56f  mov     rdi, [rcx]
0x18001a572  test    rdi, rdi
0x18001a575  jz      short loc_18001A59E
0x18001a577  lea     rcx, [rdi+8]
0x18001a57b  test    rcx, rcx
0x18001a57e  jz      short loc_18001A58A
0x18001a580  add     rcx, 8
0x18001a584  call    cs:__imp_ASN1octetstring_free
0x18001a58a  mov     rbx, [rdi]
0x18001a58d  mov     rcx, rdi
0x18001a590  call    cs:__imp_ASN1Free
0x18001a596  mov     rdi, rbx
0x18001a599  test    rbx, rbx
0x18001a59c  jnz     short loc_18001A577
0x18001a59e  mov     rbx, [rsp+28h+arg_0]
0x18001a5a3  add     rsp, 20h
0x18001a5a7  pop     rdi
0x18001a5a8  retn
```
