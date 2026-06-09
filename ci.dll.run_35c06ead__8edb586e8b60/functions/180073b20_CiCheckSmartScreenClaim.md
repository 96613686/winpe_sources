# CiCheckSmartScreenClaim

- ea: `0x180073b20`
- end: `0x180073c24`
- name: `CiCheckSmartScreenClaim`
- size: `260`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800647dc`
- `0x1800b4f38`

## callees

- `0x180073b20`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180073b54`
- `ntoskrnl!ExAllocatePool2` at `0x180073b54`
- `ntoskrnl!ExFreePoolWithTag` at `0x180073bb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x180073c07`
- `ntoskrnl!ExFreePoolWithTag` at `0x180073bb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x180073c07`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x180073b91`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x180073b91`

## pseudocode

```c
void __fastcall CiCheckSmartScreenClaim(int *a1)
{
  int v1; // eax
  __int64 Pool2; // rbx
  unsigned int v4; // esi
  int v5; // eax
  __int64 v6; // rax
  unsigned int v7; // [rsp+40h] [rbp+8h] BYREF

  v1 = *a1;
  Pool2 = 0;
  v7 = 0;
  v4 = 678;
  if ( (v1 & 0x10) != 0 )
  {
    while ( 1 )
    {
      Pool2 = ExAllocatePool2(258, v4, 1098149235);
      if ( !Pool2 )
        break;
      v5 = SeQuerySecurityAttributesToken(*((_QWORD *)a1 + 381), L"`b", 1, Pool2, v4, &v7);
      if ( v5 != -1073741789 )
      {
        if ( v5 >= 0 )
        {
          if ( *(_DWORD *)(Pool2 + 4) )
          {
            v6 = *(_QWORD *)(Pool2 + 8);
            if ( *(_WORD *)(v6 + 16) == 16 && *(_DWORD *)(*(_QWORD *)(v6 + 32) + 8LL) == 524 )
              a1[382] = 1;
          }
        }
        break;
      }
      if ( v4 >= v7 )
        break;
      v4 = v7;
      ExFreePoolWithTag((PVOID)Pool2, 0x41746D73u);
    }
  }
  a1[383] = 1;
  if ( Pool2 )
    ExFreePoolWithTag((PVOID)Pool2, 0x41746D73u);
}

```

## disassembly

```asm
0x180073b20  mov     [rsp+arg_8], rbx
0x180073b25  mov     [rsp+arg_10], rsi
0x180073b2a  push    rdi
0x180073b2b  sub     rsp, 30h
0x180073b2f  mov     eax, [rcx]
0x180073b31  xor     ebx, ebx
0x180073b33  mov     [rsp+38h+arg_0], ebx
0x180073b37  mov     rdi, rcx
0x180073b3a  mov     esi, 2A6h
0x180073b3f  test    al, 10h
0x180073b41  jz      loc_180073BF0
0x180073b47  mov     edx, esi
0x180073b49  mov     ecx, 102h
0x180073b4e  mov     r8d, 41746D73h
0x180073b54  call    cs:__imp_ExAllocatePool2
0x180073b5b  nop     dword ptr [rax+rax+00h]
0x180073b60  mov     rbx, rax
0x180073b63  test    rax, rax
0x180073b66  jz      loc_180073BF0
0x180073b6c  mov     rcx, [rdi+0BE8h]
0x180073b73  lea     rax, [rsp+38h+arg_0]
0x180073b78  mov     [rsp+38h+var_10], rax
0x180073b7d  lea     rdx, aB_0; "`b"
0x180073b84  mov     r9, rbx
0x180073b87  mov     [rsp+38h+var_18], esi
0x180073b8b  mov     r8d, 1
0x180073b91  call    cs:__imp_SeQuerySecurityAttributesToken
0x180073b98  nop     dword ptr [rax+rax+00h]
0x180073b9d  cmp     eax, 0C0000023h
0x180073ba2  jnz     short loc_180073BC4
0x180073ba4  cmp     esi, [rsp+38h+arg_0]
0x180073ba8  jnb     short loc_180073BF0
0x180073baa  mov     esi, [rsp+38h+arg_0]
0x180073bae  mov     edx, 41746D73h; Tag
0x180073bb3  mov     rcx, rbx; P
0x180073bb6  call    cs:__imp_ExFreePoolWithTag
0x180073bbd  nop     dword ptr [rax+rax+00h]
0x180073bc2  jmp     short loc_180073B47
0x180073bc4  test    eax, eax
0x180073bc6  js      short loc_180073BF0
0x180073bc8  cmp     dword ptr [rbx+4], 0
0x180073bcc  jbe     short loc_180073BF0
0x180073bce  mov     rax, [rbx+8]
0x180073bd2  cmp     word ptr [rax+10h], 10h
0x180073bd7  jnz     short loc_180073BF0
0x180073bd9  mov     rax, [rax+20h]
0x180073bdd  cmp     dword ptr [rax+8], 20Ch
0x180073be4  jnz     short loc_180073BF0
0x180073be6  mov     dword ptr [rdi+5F8h], 1
0x180073bf0  mov     dword ptr [rdi+5FCh], 1
0x180073bfa  test    rbx, rbx
0x180073bfd  jz      short loc_180073C13
0x180073bff  mov     edx, 41746D73h; Tag
0x180073c04  mov     rcx, rbx; P
0x180073c07  call    cs:__imp_ExFreePoolWithTag
0x180073c0e  nop     dword ptr [rax+rax+00h]
0x180073c13  mov     rbx, [rsp+38h+arg_8]
0x180073c18  mov     rsi, [rsp+38h+arg_10]
0x180073c1d  add     rsp, 30h
0x180073c21  pop     rdi
0x180073c22  retn
```
