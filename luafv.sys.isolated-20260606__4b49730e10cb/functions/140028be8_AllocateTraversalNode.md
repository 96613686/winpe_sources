# AllocateTraversalNode

- ea: `0x140028be8`
- end: `0x140028c7d`
- name: `AllocateTraversalNode`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140028c84`

## callees

- `0x140006380`
- `0x14001b6a0`
- `0x140028be8`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140028c42`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140028c42`

## pseudocode

```c
char *__fastcall AllocateTraversalNode(__int64 a1, const UNICODE_STRING *a2)
{
  unsigned int v4; // ebp
  char *result; // rax
  char *v6; // rbx
  _QWORD *v7; // rcx

  v4 = a2->Length + 72;
  result = LuafvAllocatePool(1, v4, 9);
  v6 = result;
  if ( result )
  {
    memset(result, 0, v4);
    *((_QWORD *)v6 + 1) = v6;
    *(_QWORD *)v6 = v6;
    *((_QWORD *)v6 + 4) = a1;
    *((_WORD *)v6 + 25) = a2->Length;
    *((_QWORD *)v6 + 7) = v6 + 72;
    RtlCopyUnicodeString((PUNICODE_STRING)v6 + 3, a2);
    v7 = *(_QWORD **)(a1 + 8);
    if ( *v7 != a1 )
      __fastfail(3u);
    *((_QWORD *)v6 + 2) = a1;
    *((_QWORD *)v6 + 3) = v7;
    *v7 = v6 + 16;
    *(_QWORD *)(a1 + 8) = v6 + 16;
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x140028be8  push    rbx
0x140028bea  push    rbp
0x140028beb  push    rsi
0x140028bec  push    rdi
0x140028bed  sub     rsp, 28h
0x140028bf1  movzx   ebp, word ptr [rdx]
0x140028bf4  mov     rsi, rdx
0x140028bf7  mov     rdi, rcx
0x140028bfa  add     ebp, 48h ; 'H'
0x140028bfd  mov     edx, ebp
0x140028bff  mov     r8b, 9
0x140028c02  mov     ecx, 1
0x140028c07  call    LuafvAllocatePool
0x140028c0c  mov     rbx, rax
0x140028c0f  test    rax, rax
0x140028c12  jz      short loc_140028C73
0x140028c14  mov     r8d, ebp; Size
0x140028c17  xor     edx, edx; Val
0x140028c19  mov     rcx, rbx; void *
0x140028c1c  call    memset
0x140028c21  mov     [rbx+8], rbx
0x140028c25  lea     rcx, [rbx+30h]; DestinationString
0x140028c29  mov     [rbx], rbx
0x140028c2c  mov     rdx, rsi; SourceString
0x140028c2f  mov     [rbx+20h], rdi
0x140028c33  movzx   eax, word ptr [rsi]
0x140028c36  mov     [rbx+32h], ax
0x140028c3a  lea     rax, [rbx+48h]
0x140028c3e  mov     [rbx+38h], rax
0x140028c42  call    cs:__imp_RtlCopyUnicodeString
0x140028c49  nop     dword ptr [rax+rax+00h]
0x140028c4e  mov     rcx, [rdi+8]
0x140028c52  cmp     [rcx], rdi
0x140028c55  jz      short loc_140028C5E
0x140028c57  mov     ecx, 3
0x140028c5c  int     29h; Win8: RtlFailFast(ecx)
0x140028c5e  lea     rax, [rbx+10h]
0x140028c62  mov     [rax], rdi
0x140028c65  mov     [rax+8], rcx
0x140028c69  mov     [rcx], rax
0x140028c6c  mov     [rdi+8], rax
0x140028c70  mov     rax, rbx
0x140028c73  add     rsp, 28h
0x140028c77  pop     rdi
0x140028c78  pop     rsi
0x140028c79  pop     rbp
0x140028c7a  pop     rbx
0x140028c7b  retn
```
