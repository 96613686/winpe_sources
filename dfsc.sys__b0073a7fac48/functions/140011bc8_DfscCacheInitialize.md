# DfscCacheInitialize

- ea: `0x140011bc8`
- end: `0x140011c74`
- name: `DfscCacheInitialize`
- size: `172`
- prototype: `__int64 __fastcall(_QWORD *, char, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a040`
- `0x14002a488`

## callees

- `0x140006380`
- `0x140011bc8`

## import_xrefs

- `ntoskrnl!RtlInitializeUnicodePrefix` at `0x140011c4d`
- `ntoskrnl!RtlInitializeUnicodePrefix` at `0x140011c4d`
- `ntoskrnl!ExInitializeResourceLite` at `0x140011c2b`
- `ntoskrnl!ExInitializeResourceLite` at `0x140011c3e`
- `ntoskrnl!ExInitializeResourceLite` at `0x140011c2b`
- `ntoskrnl!ExInitializeResourceLite` at `0x140011c3e`
- `ntoskrnl!ExAllocatePool2` at `0x140011bf1`
- `ntoskrnl!ExAllocatePool2` at `0x140011bf1`

## pseudocode

```c
__int64 __fastcall DfscCacheInitialize(_QWORD *a1, char a2, int a3)
{
  char *Pool2; // rax
  char *v7; // rbx
  __int64 result; // rax

  *a1 = 0;
  Pool2 = (char *)ExAllocatePool2(66, 264, 1732470340);
  v7 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  memset(Pool2, 0, 0x108u);
  *((_QWORD *)v7 + 4) = v7 + 24;
  *((_QWORD *)v7 + 3) = v7 + 24;
  ExInitializeResourceLite((PERESOURCE)(v7 + 56));
  ExInitializeResourceLite((PERESOURCE)(v7 + 160));
  RtlInitializeUnicodePrefix((PUNICODE_PREFIX_TABLE)v7);
  if ( a2 )
    *((_DWORD *)v7 + 10) |= 1u;
  *((_DWORD *)v7 + 13) = a3;
  result = 0;
  *a1 = v7;
  return result;
}

```

## disassembly

```asm
0x140011bc8  push    rbx
0x140011bca  push    rbp
0x140011bcb  push    rsi
0x140011bcc  push    rdi
0x140011bcd  sub     rsp, 28h
0x140011bd1  mov     esi, r8d
0x140011bd4  mov     qword ptr [rcx], 0
0x140011bdb  mov     bpl, dl
0x140011bde  mov     rdi, rcx
0x140011be1  mov     edx, 108h
0x140011be6  mov     ecx, 42h ; 'B'
0x140011beb  mov     r8d, 67436644h
0x140011bf1  call    cs:__imp_ExAllocatePool2
0x140011bf8  nop     dword ptr [rax+rax+00h]
0x140011bfd  mov     rbx, rax
0x140011c00  test    rax, rax
0x140011c03  jnz     short loc_140011C0C
0x140011c05  mov     eax, 0C000009Ah
0x140011c0a  jmp     short loc_140011C6A
0x140011c0c  xor     edx, edx; Val
0x140011c0e  mov     r8d, 108h; Size
0x140011c14  mov     rcx, rbx; void *
0x140011c17  call    memset
0x140011c1c  lea     rax, [rbx+18h]
0x140011c20  lea     rcx, [rbx+38h]; Resource
0x140011c24  mov     [rax+8], rax
0x140011c28  mov     [rax], rax
0x140011c2b  call    cs:__imp_ExInitializeResourceLite
0x140011c32  nop     dword ptr [rax+rax+00h]
0x140011c37  lea     rcx, [rbx+0A0h]; Resource
0x140011c3e  call    cs:__imp_ExInitializeResourceLite
0x140011c45  nop     dword ptr [rax+rax+00h]
0x140011c4a  mov     rcx, rbx; PrefixTable
0x140011c4d  call    cs:__imp_RtlInitializeUnicodePrefix
0x140011c54  nop     dword ptr [rax+rax+00h]
0x140011c59  test    bpl, bpl
0x140011c5c  jz      short loc_140011C62
0x140011c5e  or      dword ptr [rbx+28h], 1
0x140011c62  mov     [rbx+34h], esi
0x140011c65  xor     eax, eax
0x140011c67  mov     [rdi], rbx
0x140011c6a  add     rsp, 28h
0x140011c6e  pop     rdi
0x140011c6f  pop     rsi
0x140011c70  pop     rbp
0x140011c71  pop     rbx
0x140011c72  retn
```
