# LuafvLookupElementTableFull

- ea: `0x14001e580`
- end: `0x14001e674`
- name: `LuafvLookupElementTableFull`
- size: `244`
- prototype: `__int64 __fastcall(PRTL_SPLAY_LINKS *, __int64, __int64, _DWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001af3c`
- `0x14001c3d0`
- `0x14001ef70`

## callees

- `0x14001e580`

## import_xrefs

- `ntoskrnl!RtlSplay` at `0x14001e5e2`
- `ntoskrnl!RtlSplay` at `0x14001e5e2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001e5ba`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001e5ba`

## pseudocode

```c
__int64 __fastcall LuafvLookupElementTableFull(PRTL_SPLAY_LINKS *a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  PRTL_SPLAY_LINKS v8; // rdi
  int v9; // esi
  signed __int64 v10; // rcx

  if ( *((_DWORD *)a1 + 4) )
  {
    v8 = *a1;
    v9 = *((_DWORD *)a1 + 5);
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v9 )
        {
          v10 = *(_QWORD *)(a2 + 8) - (unsigned __int64)v8[1].LeftChild;
          if ( !v10 )
            v10 = (*(_QWORD *)a2 & 0xFFFFFFFFFFFFFFF8uLL) - ((unsigned __int64)v8[1].Parent & 0xFFFFFFFFFFFFFFF8uLL);
        }
        else
        {
          v10 = RtlCompareUnicodeString((PCUNICODE_STRING)(a2 + 8), (PCUNICODE_STRING)&v8[1].LeftChild, 1u);
        }
        if ( v10 < 0 )
          break;
        if ( v10 <= 0 )
        {
          *(_QWORD *)a3 = v8;
          *a4 = 1;
          *a1 = RtlSplay(v8);
          return *(_QWORD *)a3;
        }
        if ( !v8->RightChild )
        {
          *a4 = 3;
          goto LABEL_13;
        }
        v8 = v8->RightChild;
      }
      if ( !v8->LeftChild )
        break;
      v8 = v8->LeftChild;
    }
    *a4 = 2;
LABEL_13:
    *(_QWORD *)a3 = v8;
  }
  else
  {
    *a4 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14001e580  push    rbx
0x14001e582  push    rbp
0x14001e583  push    rsi
0x14001e584  push    rdi
0x14001e585  push    r12
0x14001e587  push    r14
0x14001e589  push    r15
0x14001e58b  sub     rsp, 20h
0x14001e58f  cmp     dword ptr [rcx+10h], 0
0x14001e593  mov     r12, r9
0x14001e596  mov     r15, r8
0x14001e599  mov     r14, rdx
0x14001e59c  mov     rbx, rcx
0x14001e59f  jz      loc_14001E650
0x14001e5a5  mov     rdi, [rcx]
0x14001e5a8  mov     esi, [rcx+14h]
0x14001e5ab  test    esi, esi
0x14001e5ad  jnz     short loc_14001E604
0x14001e5af  mov     r8b, 1; CaseInSensitive
0x14001e5b2  lea     rdx, [rdi+20h]; String2
0x14001e5b6  lea     rcx, [r14+8]; String1
0x14001e5ba  call    cs:__imp_RtlCompareUnicodeString
0x14001e5c1  nop     dword ptr [rax+rax+00h]
0x14001e5c6  movsxd  rcx, eax
0x14001e5c9  test    rcx, rcx
0x14001e5cc  js      loc_14001E659
0x14001e5d2  jg      short loc_14001E622
0x14001e5d4  mov     rcx, rdi; Links
0x14001e5d7  mov     [r15], rdi
0x14001e5da  mov     dword ptr [r12], 1
0x14001e5e2  call    cs:__imp_RtlSplay
0x14001e5e9  nop     dword ptr [rax+rax+00h]
0x14001e5ee  mov     [rbx], rax
0x14001e5f1  mov     rax, [r15]
0x14001e5f4  add     rsp, 20h
0x14001e5f8  pop     r15
0x14001e5fa  pop     r14
0x14001e5fc  pop     r12
0x14001e5fe  pop     rdi
0x14001e5ff  pop     rsi
0x14001e600  pop     rbp
0x14001e601  pop     rbx
0x14001e602  retn
0x14001e604  mov     rcx, [r14+8]
0x14001e608  sub     rcx, [rdi+20h]
0x14001e60c  jnz     short loc_14001E5C9
0x14001e60e  mov     rcx, [r14]
0x14001e611  mov     rax, [rdi+18h]
0x14001e615  and     rcx, 0FFFFFFFFFFFFFFF8h
0x14001e619  and     rax, 0FFFFFFFFFFFFFFF8h
0x14001e61d  sub     rcx, rax
0x14001e620  jmp     short loc_14001E5C9
0x14001e622  mov     rax, [rdi+10h]
0x14001e626  test    rax, rax
0x14001e629  jz      short loc_14001E633
0x14001e62b  mov     rdi, rax
0x14001e62e  jmp     loc_14001E5AB
0x14001e633  mov     dword ptr [r12], 3
0x14001e63b  mov     [r15], rdi
0x14001e63e  xor     eax, eax
0x14001e640  add     rsp, 20h
0x14001e644  pop     r15
0x14001e646  pop     r14
0x14001e648  pop     r12
0x14001e64a  pop     rdi
0x14001e64b  pop     rsi
0x14001e64c  pop     rbp
0x14001e64d  pop     rbx
0x14001e64e  retn
0x14001e650  mov     dword ptr [r9], 0
0x14001e657  jmp     short loc_14001E63E
0x14001e659  mov     rax, [rdi+8]
0x14001e65d  test    rax, rax
0x14001e660  jz      short loc_14001E66A
0x14001e662  mov     rdi, rax
0x14001e665  jmp     loc_14001E5AB
0x14001e66a  mov     dword ptr [r12], 2
0x14001e672  jmp     short loc_14001E63B
```
