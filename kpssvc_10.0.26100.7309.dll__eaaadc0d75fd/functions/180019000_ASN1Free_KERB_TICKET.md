# ASN1Free_KERB_TICKET

- ea: `0x180019000`
- end: `0x18001909d`
- name: `ASN1Free_KERB_TICKET`
- size: `157`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180017d80`
- `0x180018070`
- `0x180018670`
- `0x1800187a8`
- `0x180018fa0`

## callees

- `0x180018cc8`
- `0x180019000`

## import_xrefs

- `MSASN1!ASN1ztcharstring_free` at `0x18001901a`
- `MSASN1!ASN1ztcharstring_free` at `0x18001901a`
- `MSASN1!ASN1octetstring_free` at `0x18001903c`
- `MSASN1!ASN1octetstring_free` at `0x18001906b`
- `MSASN1!ASN1octetstring_free` at `0x18001903c`
- `MSASN1!ASN1octetstring_free` at `0x18001906b`
- `MSASN1!ASN1Free` at `0x18001907d`
- `MSASN1!ASN1Free` at `0x18001907d`

## pseudocode

```c
__int64 __fastcall ASN1Free_KERB_TICKET(__int64 a1)
{
  __int64 result; // rax
  _QWORD *v3; // rdi
  _QWORD *v4; // rbx

  if ( a1 )
  {
    ASN1ztcharstring_free(*(_QWORD *)(a1 + 8));
    result = ASN1Free_KERB_PRINCIPAL_NAME(a1 + 16);
    if ( a1 != -32 )
      result = ASN1octetstring_free(a1 + 48);
    if ( *(char *)a1 < 0 && a1 != -64 )
    {
      v3 = *(_QWORD **)(a1 + 64);
      if ( v3 )
      {
        do
        {
          if ( v3 != (_QWORD *)-8LL )
            ASN1octetstring_free(v3 + 2);
          v4 = (_QWORD *)*v3;
          result = ASN1Free(v3);
          v3 = v4;
        }
        while ( v4 );
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019000  test    rcx, rcx
0x180019003  jz      locret_18001909B
0x180019009  mov     [rsp+arg_0], rbx
0x18001900e  push    rdi
0x18001900f  sub     rsp, 20h
0x180019013  mov     rbx, rcx
0x180019016  mov     rcx, [rcx+8]
0x18001901a  call    cs:__imp_ASN1ztcharstring_free
0x180019021  nop     dword ptr [rax+rax+00h]
0x180019026  lea     rcx, [rbx+10h]
0x18001902a  call    ASN1Free_KERB_PRINCIPAL_NAME
0x18001902f  lea     rcx, [rbx+20h]
0x180019033  test    rcx, rcx
0x180019036  jz      short loc_180019048
0x180019038  add     rcx, 10h
0x18001903c  call    cs:__imp_ASN1octetstring_free
0x180019043  nop     dword ptr [rax+rax+00h]
0x180019048  cmp     byte ptr [rbx], 0
0x18001904b  jge     short loc_180019091
0x18001904d  lea     rdi, [rbx+40h]
0x180019051  test    rdi, rdi
0x180019054  jz      short loc_180019091
0x180019056  mov     rdi, [rdi]
0x180019059  test    rdi, rdi
0x18001905c  jz      short loc_180019091
0x18001905e  lea     rcx, [rdi+8]
0x180019062  test    rcx, rcx
0x180019065  jz      short loc_180019077
0x180019067  add     rcx, 8
0x18001906b  call    cs:__imp_ASN1octetstring_free
0x180019072  nop     dword ptr [rax+rax+00h]
0x180019077  mov     rbx, [rdi]
0x18001907a  mov     rcx, rdi
0x18001907d  call    cs:__imp_ASN1Free
0x180019084  nop     dword ptr [rax+rax+00h]
0x180019089  mov     rdi, rbx
0x18001908c  test    rbx, rbx
0x18001908f  jnz     short loc_18001905E
0x180019091  mov     rbx, [rsp+28h+arg_0]
0x180019096  add     rsp, 20h
0x18001909a  pop     rdi
0x18001909b  retn
```
