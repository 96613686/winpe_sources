# NpUnlinkProtectedPrefix

- ea: `0x14000e570`
- end: `0x14000e638`
- name: `NpUnlinkProtectedPrefix`
- size: `200`
- prototype: `__int64 __fastcall(struct _UNICODE_PREFIX_TABLE *, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000d6dc`
- `0x14000e980`

## callees

- `0x14000d6dc`
- `0x14000e570`

## import_xrefs

- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14000e5d4`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14000e5d4`

## pseudocode

```c
__int64 __fastcall NpUnlinkProtectedPrefix(struct _UNICODE_PREFIX_TABLE *a1, __int64 a2, __int64 a3)
{
  _QWORD *v4; // rsi
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  __int64 result; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rdx
  _QWORD *v12; // r9

  v4 = (_QWORD *)(a2 + 248);
  do
  {
    v7 = (_QWORD *)*v4;
    v8 = v4;
    while ( v7 != v8 )
    {
      v12 = v7 - 29;
      if ( *((_WORD *)v7 - 116) != 515 || (v7 = (_QWORD *)v12[31], v7 == v12 + 31) )
      {
        NpUnlinkNode(v12, a1, a3);
        v7 = (_QWORD *)*v8;
      }
      else
      {
        v8 = v12 + 31;
      }
    }
  }
  while ( v8 != v4 );
  result = 0;
  if ( *(_WORD *)(a2 + 160) )
  {
    v10 = *(_QWORD *)(a2 + 232);
    if ( *(_QWORD *)(v10 + 8) != a2 + 232 || (v11 = *(_QWORD **)(a2 + 240), *v11 != a2 + 232) )
      __fastfail(3u);
    *v11 = v10;
    *(_QWORD *)(v10 + 8) = v11;
    RtlRemoveUnicodePrefix(a1 + 9, (PUNICODE_PREFIX_TABLE_ENTRY)(a2 + 176));
    result = 0;
    *(_WORD *)(a2 + 160) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000e570  push    rbx
0x14000e572  push    rbp
0x14000e573  push    rsi
0x14000e574  push    rdi
0x14000e575  push    r14
0x14000e577  sub     rsp, 20h
0x14000e57b  mov     r14, r8
0x14000e57e  lea     rsi, [rdx+0F8h]
0x14000e585  mov     rbx, rdx
0x14000e588  mov     rbp, rcx
0x14000e58b  mov     rax, [rsi]
0x14000e58e  mov     rdi, rsi
0x14000e591  cmp     rax, rdi
0x14000e594  jnz     short loc_14000E610
0x14000e596  cmp     rdi, rsi
0x14000e599  jnz     short loc_14000E58B
0x14000e59b  xor     eax, eax
0x14000e59d  cmp     ax, [rbx+0A0h]
0x14000e5a4  jz      short loc_14000E5E9
0x14000e5a6  lea     rax, [rbx+0E8h]
0x14000e5ad  mov     rcx, [rax]
0x14000e5b0  cmp     [rcx+8], rax
0x14000e5b4  jnz     short loc_14000E5F5
0x14000e5b6  mov     rdx, [rax+8]
0x14000e5ba  cmp     [rdx], rax
0x14000e5bd  jnz     short loc_14000E5F5
0x14000e5bf  mov     [rdx], rcx
0x14000e5c2  mov     [rcx+8], rdx
0x14000e5c6  lea     rdx, [rbx+0B0h]; PrefixTableEntry
0x14000e5cd  lea     rcx, [rbp+0D8h]; PrefixTable
0x14000e5d4  call    cs:__imp_RtlRemoveUnicodePrefix
0x14000e5db  nop     dword ptr [rax+rax+00h]
0x14000e5e0  xor     eax, eax
0x14000e5e2  mov     [rbx+0A0h], ax
0x14000e5e9  add     rsp, 20h
0x14000e5ed  pop     r14
0x14000e5ef  pop     rdi
0x14000e5f0  pop     rsi
0x14000e5f1  pop     rbp
0x14000e5f2  pop     rbx
0x14000e5f3  retn
0x14000e5f5  mov     ecx, 3
0x14000e5fa  int     29h; Win8: RtlFailFast(ecx)
0x14000e5fc  lea     rcx, [r9+0F8h]
0x14000e603  mov     rax, [rcx]
0x14000e606  cmp     rax, rcx
0x14000e609  jz      short loc_14000E622
0x14000e60b  mov     rdi, rcx
0x14000e60e  jmp     short loc_14000E591
0x14000e610  lea     r9, [rax-0E8h]
0x14000e617  mov     eax, 203h
0x14000e61c  cmp     ax, [r9]
0x14000e620  jz      short loc_14000E5FC
0x14000e622  mov     r8, r14
0x14000e625  mov     rdx, rbp
0x14000e628  mov     rcx, r9
0x14000e62b  call    NpUnlinkNode
0x14000e630  mov     rax, [rdi]
0x14000e633  jmp     loc_14000E591
```
