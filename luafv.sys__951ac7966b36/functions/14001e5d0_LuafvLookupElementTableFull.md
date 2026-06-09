# LuafvLookupElementTableFull

- ea: `0x14001e5d0`
- end: `0x14001e6c4`
- name: `LuafvLookupElementTableFull`
- size: `244`
- prototype: `__int64 __fastcall(PRTL_SPLAY_LINKS *, __int64, __int64, _DWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001af8c`
- `0x14001c420`
- `0x14001efc0`

## callees

- `0x14001e5d0`

## import_xrefs

- `ntoskrnl!RtlSplay` at `0x14001e632`
- `ntoskrnl!RtlSplay` at `0x14001e632`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001e60a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001e60a`

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
0x14001e5d0  push    rbx
0x14001e5d2  push    rbp
0x14001e5d3  push    rsi
0x14001e5d4  push    rdi
0x14001e5d5  push    r12
0x14001e5d7  push    r14
0x14001e5d9  push    r15
0x14001e5db  sub     rsp, 20h
0x14001e5df  cmp     dword ptr [rcx+10h], 0
0x14001e5e3  mov     r12, r9
0x14001e5e6  mov     r15, r8
0x14001e5e9  mov     r14, rdx
0x14001e5ec  mov     rbx, rcx
0x14001e5ef  jz      loc_14001E6A0
0x14001e5f5  mov     rdi, [rcx]
0x14001e5f8  mov     esi, [rcx+14h]
0x14001e5fb  test    esi, esi
0x14001e5fd  jnz     short loc_14001E654
0x14001e5ff  mov     r8b, 1; CaseInSensitive
0x14001e602  lea     rdx, [rdi+20h]; String2
0x14001e606  lea     rcx, [r14+8]; String1
0x14001e60a  call    cs:__imp_RtlCompareUnicodeString
0x14001e611  nop     dword ptr [rax+rax+00h]
0x14001e616  movsxd  rcx, eax
0x14001e619  test    rcx, rcx
0x14001e61c  js      loc_14001E6A9
0x14001e622  jg      short loc_14001E672
0x14001e624  mov     rcx, rdi; Links
0x14001e627  mov     [r15], rdi
0x14001e62a  mov     dword ptr [r12], 1
0x14001e632  call    cs:__imp_RtlSplay
0x14001e639  nop     dword ptr [rax+rax+00h]
0x14001e63e  mov     [rbx], rax
0x14001e641  mov     rax, [r15]
0x14001e644  add     rsp, 20h
0x14001e648  pop     r15
0x14001e64a  pop     r14
0x14001e64c  pop     r12
0x14001e64e  pop     rdi
0x14001e64f  pop     rsi
0x14001e650  pop     rbp
0x14001e651  pop     rbx
0x14001e652  retn
0x14001e654  mov     rcx, [r14+8]
0x14001e658  sub     rcx, [rdi+20h]
0x14001e65c  jnz     short loc_14001E619
0x14001e65e  mov     rcx, [r14]
0x14001e661  mov     rax, [rdi+18h]
0x14001e665  and     rcx, 0FFFFFFFFFFFFFFF8h
0x14001e669  and     rax, 0FFFFFFFFFFFFFFF8h
0x14001e66d  sub     rcx, rax
0x14001e670  jmp     short loc_14001E619
0x14001e672  mov     rax, [rdi+10h]
0x14001e676  test    rax, rax
0x14001e679  jz      short loc_14001E683
0x14001e67b  mov     rdi, rax
0x14001e67e  jmp     loc_14001E5FB
0x14001e683  mov     dword ptr [r12], 3
0x14001e68b  mov     [r15], rdi
0x14001e68e  xor     eax, eax
0x14001e690  add     rsp, 20h
0x14001e694  pop     r15
0x14001e696  pop     r14
0x14001e698  pop     r12
0x14001e69a  pop     rdi
0x14001e69b  pop     rsi
0x14001e69c  pop     rbp
0x14001e69d  pop     rbx
0x14001e69e  retn
0x14001e6a0  mov     dword ptr [r9], 0
0x14001e6a7  jmp     short loc_14001E68E
0x14001e6a9  mov     rax, [rdi+8]
0x14001e6ad  test    rax, rax
0x14001e6b0  jz      short loc_14001E6BA
0x14001e6b2  mov     rdi, rax
0x14001e6b5  jmp     loc_14001E5FB
0x14001e6ba  mov     dword ptr [r12], 2
0x14001e6c2  jmp     short loc_14001E68B
```
