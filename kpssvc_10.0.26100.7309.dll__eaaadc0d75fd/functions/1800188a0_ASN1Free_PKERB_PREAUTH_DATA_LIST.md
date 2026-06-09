# ASN1Free_PKERB_PREAUTH_DATA_LIST

- ea: `0x1800188a0`
- end: `0x1800188f6`
- name: `ASN1Free_PKERB_PREAUTH_DATA_LIST`
- size: `86`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180017e10`
- `0x180018260`
- `0x18001834c`
- `0x1800184b0`
- `0x1800187a8`
- `0x1800193c0`

## callees

- `0x1800188a0`

## import_xrefs

- `MSASN1!ASN1octetstring_free` at `0x1800188c4`
- `MSASN1!ASN1octetstring_free` at `0x1800188c4`
- `MSASN1!ASN1Free` at `0x1800188d6`
- `MSASN1!ASN1Free` at `0x1800188d6`

## pseudocode

```c
__int64 __fastcall ASN1Free_PKERB_PREAUTH_DATA_LIST(_QWORD **a1)
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
0x1800188a0  test    rcx, rcx
0x1800188a3  jz      short locret_1800188F4
0x1800188a5  mov     [rsp+arg_0], rbx
0x1800188aa  push    rdi
0x1800188ab  sub     rsp, 20h
0x1800188af  mov     rdi, [rcx]
0x1800188b2  test    rdi, rdi
0x1800188b5  jz      short loc_1800188EA
0x1800188b7  lea     rcx, [rdi+8]
0x1800188bb  test    rcx, rcx
0x1800188be  jz      short loc_1800188D0
0x1800188c0  add     rcx, 8
0x1800188c4  call    cs:__imp_ASN1octetstring_free
0x1800188cb  nop     dword ptr [rax+rax+00h]
0x1800188d0  mov     rbx, [rdi]
0x1800188d3  mov     rcx, rdi
0x1800188d6  call    cs:__imp_ASN1Free
0x1800188dd  nop     dword ptr [rax+rax+00h]
0x1800188e2  mov     rdi, rbx
0x1800188e5  test    rbx, rbx
0x1800188e8  jnz     short loc_1800188B7
0x1800188ea  mov     rbx, [rsp+28h+arg_0]
0x1800188ef  add     rsp, 20h
0x1800188f3  pop     rdi
0x1800188f4  retn
```
