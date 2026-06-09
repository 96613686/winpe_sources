# CscPathPrefixpDeletePrefixList

- ea: `0x14004ae48`
- end: `0x14004aea1`
- name: `CscPathPrefixpDeletePrefixList`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14004acac`
- `0x140053338`

## callees

- `0x14004ae48`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14004ae86`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14004ae86`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004ae74`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004ae74`

## pseudocode

```c
void __fastcall CscPathPrefixpDeletePrefixList(__int64 a1, struct _UNICODE_STRING **a2, struct _UNICODE_STRING **a3)
{
  struct _UNICODE_STRING *v3; // rdi
  struct _UNICODE_STRING **v4; // rsi
  struct _PAGED_LOOKASIDE_LIST *v5; // rbp
  struct _UNICODE_STRING *v6; // rbx

  v3 = *a2;
  v4 = a3;
  if ( !a3 )
    v4 = a2;
  if ( v3 != (struct _UNICODE_STRING *)v4 )
  {
    v5 = (struct _PAGED_LOOKASIDE_LIST *)(a1 + 192);
    do
    {
      v6 = v3;
      v3 = *(struct _UNICODE_STRING **)&v3->Length;
      RtlFreeUnicodeString(v6 + 1);
      ExFreeToPagedLookasideList(v5, v6);
    }
    while ( v3 != (struct _UNICODE_STRING *)v4 );
  }
}

```

## disassembly

```asm
0x14004ae48  push    rbx
0x14004ae4a  push    rbp
0x14004ae4b  push    rsi
0x14004ae4c  push    rdi
0x14004ae4d  sub     rsp, 28h
0x14004ae51  mov     rdi, [rdx]
0x14004ae54  test    r8, r8
0x14004ae57  mov     rsi, r8
0x14004ae5a  cmovz   rsi, rdx
0x14004ae5e  cmp     rdi, rsi
0x14004ae61  jz      short loc_14004AE97
0x14004ae63  lea     rbp, [rcx+0C0h]
0x14004ae6a  mov     rbx, rdi
0x14004ae6d  mov     rdi, [rdi]
0x14004ae70  lea     rcx, [rbx+10h]; UnicodeString
0x14004ae74  call    cs:__imp_RtlFreeUnicodeString
0x14004ae7b  nop     dword ptr [rax+rax+00h]
0x14004ae80  mov     rdx, rbx; Entry
0x14004ae83  mov     rcx, rbp; Lookaside
0x14004ae86  call    cs:__imp_ExFreeToPagedLookasideList
0x14004ae8d  nop     dword ptr [rax+rax+00h]
0x14004ae92  cmp     rdi, rsi
0x14004ae95  jnz     short loc_14004AE6A
0x14004ae97  add     rsp, 28h
0x14004ae9b  pop     rdi
0x14004ae9c  pop     rsi
0x14004ae9d  pop     rbp
0x14004ae9e  pop     rbx
0x14004ae9f  retn
```
