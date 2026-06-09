# ASN1Free_KERB_REALM_CACHE

- ea: `0x180018d30`
- end: `0x180018d85`
- name: `ASN1Free_KERB_REALM_CACHE`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180018d30`

## import_xrefs

- `MSASN1!ASN1ztcharstring_free` at `0x180018d53`
- `MSASN1!ASN1ztcharstring_free` at `0x180018d53`
- `MSASN1!ASN1Free` at `0x180018d65`
- `MSASN1!ASN1Free` at `0x180018d65`

## pseudocode

```c
__int64 __fastcall ASN1Free_KERB_REALM_CACHE(_QWORD **a1)
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
          ASN1ztcharstring_free(v1[1]);
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
0x180018d30  test    rcx, rcx
0x180018d33  jz      short locret_180018D83
0x180018d35  mov     [rsp+arg_0], rbx
0x180018d3a  push    rdi
0x180018d3b  sub     rsp, 20h
0x180018d3f  mov     rdi, [rcx]
0x180018d42  test    rdi, rdi
0x180018d45  jz      short loc_180018D79
0x180018d47  lea     rcx, [rdi+8]
0x180018d4b  test    rcx, rcx
0x180018d4e  jz      short loc_180018D5F
0x180018d50  mov     rcx, [rcx]
0x180018d53  call    cs:__imp_ASN1ztcharstring_free
0x180018d5a  nop     dword ptr [rax+rax+00h]
0x180018d5f  mov     rbx, [rdi]
0x180018d62  mov     rcx, rdi
0x180018d65  call    cs:__imp_ASN1Free
0x180018d6c  nop     dword ptr [rax+rax+00h]
0x180018d71  mov     rdi, rbx
0x180018d74  test    rbx, rbx
0x180018d77  jnz     short loc_180018D47
0x180018d79  mov     rbx, [rsp+28h+arg_0]
0x180018d7e  add     rsp, 20h
0x180018d82  pop     rdi
0x180018d83  retn
```
