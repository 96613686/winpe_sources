# LdrpThreadTokenSetMainThreadToken

- ea: `0x180025a50`
- end: `0x180025ac3`
- name: `LdrpThreadTokenSetMainThreadToken`
- size: `115`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800249a0`
- `0x1800d6508`

## callees

- `0x18001eb80`
- `0x180025a50`
- `0x18015e750`

## string_xrefs

- `0x180025aa9`: `LdrpThreadTokenSetMainThreadToken`

## pseudocode

```c
__int64 LdrpThreadTokenSetMainThreadToken()
{
  unsigned int ArgList; // ebx
  void *v2; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  ArgList = NtOpenThreadToken(-2, 131100, 0, &v2);
  LdrpMainThreadToken = v2;
  if ( ArgList != -1073741700 )
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrapi.c",
      4383,
      (int)"LdrpThreadTokenSetMainThreadToken",
      2,
      "Status: 0x%x\n",
      ArgList);
  return ArgList;
}

```

## disassembly

```asm
0x180025a50  push    rbx
0x180025a52  sub     rsp, 30h
0x180025a56  xor     r8d, r8d
0x180025a59  mov     [rsp+38h+arg_0], 0
0x180025a62  lea     r9, [rsp+38h+arg_0]
0x180025a67  mov     edx, 2001Ch
0x180025a6c  lea     rcx, [r8-2]
0x180025a70  call    NtOpenThreadToken
0x180025a75  mov     rcx, [rsp+38h+arg_0]
0x180025a7a  mov     ebx, eax
0x180025a7c  mov     cs:LdrpMainThreadToken, rcx
0x180025a83  cmp     eax, 0C000007Ch
0x180025a88  jnz     short loc_180025A93
0x180025a8a  mov     eax, ebx
0x180025a8c  add     rsp, 30h
0x180025a90  pop     rbx
0x180025a91  retn
0x180025a93  lea     rax, aStatus0xX; "Status: 0x%x\n"
0x180025a9a  mov     dword ptr [rsp+38h+ArgList], ebx; ArgList
0x180025a9e  mov     r9d, 2; int
0x180025aa4  mov     [rsp+38h+Format], rax; Format
0x180025aa9  lea     r8, aLdrpthreadtoke_1; "LdrpThreadTokenSetMainThreadToken"
0x180025ab0  mov     edx, 111Fh; int
0x180025ab5  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x180025abc  call    LdrpLogInternal
0x180025ac1  jmp     short loc_180025A8A
```
