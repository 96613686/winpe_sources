# ASN1Free_KERB_PRINCIPAL_NAME

- ea: `0x180018cc8`
- end: `0x180018d1e`
- name: `ASN1Free_KERB_PRINCIPAL_NAME`
- size: `86`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x180017e10`
- `0x180017eb0`
- `0x180018020`
- `0x180018260`
- `0x18001834c`
- `0x1800184b0`
- `0x180018550`
- `0x180018670`
- `0x1800187a8`
- `0x180018920`
- `0x180018bb0`
- `0x180018c90`
- `0x180018f70`
- `0x180018fc0`
- `0x180019000`
- `0x1800190b0`
- `0x180019110`
- `0x1800191e0`
- `0x1800194b0`

## callees

- `0x180018cc8`

## import_xrefs

- `MSASN1!ASN1ztcharstring_free` at `0x180018cec`
- `MSASN1!ASN1ztcharstring_free` at `0x180018cec`
- `MSASN1!ASN1Free` at `0x180018cfe`
- `MSASN1!ASN1Free` at `0x180018cfe`

## pseudocode

```c
__int64 __fastcall ASN1Free_KERB_PRINCIPAL_NAME(__int64 a1)
{
  _QWORD *v1; // rdi
  _QWORD *v2; // rbx
  __int64 result; // rax

  if ( a1 )
  {
    if ( a1 != -8 )
    {
      v1 = *(_QWORD **)(a1 + 8);
      if ( v1 )
      {
        do
        {
          ASN1ztcharstring_free(v1[1]);
          v2 = (_QWORD *)*v1;
          result = ASN1Free(v1);
          v1 = v2;
        }
        while ( v2 );
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180018cc8  test    rcx, rcx
0x180018ccb  jz      short locret_180018D1C
0x180018ccd  mov     [rsp+arg_0], rbx
0x180018cd2  push    rdi
0x180018cd3  sub     rsp, 20h
0x180018cd7  lea     rdi, [rcx+8]
0x180018cdb  test    rdi, rdi
0x180018cde  jz      short loc_180018D12
0x180018ce0  mov     rdi, [rdi]
0x180018ce3  test    rdi, rdi
0x180018ce6  jz      short loc_180018D12
0x180018ce8  mov     rcx, [rdi+8]
0x180018cec  call    cs:__imp_ASN1ztcharstring_free
0x180018cf3  nop     dword ptr [rax+rax+00h]
0x180018cf8  mov     rbx, [rdi]
0x180018cfb  mov     rcx, rdi
0x180018cfe  call    cs:__imp_ASN1Free
0x180018d05  nop     dword ptr [rax+rax+00h]
0x180018d0a  mov     rdi, rbx
0x180018d0d  test    rbx, rbx
0x180018d10  jnz     short loc_180018CE8
0x180018d12  mov     rbx, [rsp+28h+arg_0]
0x180018d17  add     rsp, 20h
0x180018d1b  pop     rdi
0x180018d1c  retn
```
