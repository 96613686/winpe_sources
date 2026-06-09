# AllocateTraversalNode

- ea: `0x140028be8`
- end: `0x140028c7d`
- name: `AllocateTraversalNode`
- size: `149`
- prototype: `struct _UNICODE_STRING *__fastcall(__int64, const UNICODE_STRING *, __int64)`
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
struct _UNICODE_STRING *__fastcall AllocateTraversalNode(__int64 a1, const UNICODE_STRING *a2, __int64 a3)
{
  unsigned int v5; // ebp
  struct _UNICODE_STRING *result; // rax
  struct _UNICODE_STRING *v7; // rbx
  WCHAR *v8; // rcx

  v5 = a2->Length + 72;
  LOBYTE(a3) = 9;
  result = (struct _UNICODE_STRING *)LuafvAllocatePool(1, v5, a3);
  v7 = result;
  if ( result )
  {
    memset(result, 0, v5);
    v7->Buffer = &v7->Length;
    *(_QWORD *)&v7->Length = v7;
    *(_QWORD *)&v7[2].Length = a1;
    v7[3].MaximumLength = a2->Length;
    v7[3].Buffer = (PWSTR)&v7[4].Buffer;
    RtlCopyUnicodeString(v7 + 3, a2);
    v8 = *(WCHAR **)(a1 + 8);
    if ( *(_QWORD *)v8 != a1 )
      __fastfail(3u);
    *(_QWORD *)&v7[1].Length = a1;
    v7[1].Buffer = v8;
    *(_QWORD *)v8 = v7 + 1;
    *(_QWORD *)(a1 + 8) = v7 + 1;
    return v7;
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
