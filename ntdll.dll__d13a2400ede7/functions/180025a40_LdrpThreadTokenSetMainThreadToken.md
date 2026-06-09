# LdrpThreadTokenSetMainThreadToken

- ea: `0x180025a40`
- end: `0x180025ab3`
- name: `LdrpThreadTokenSetMainThreadToken`
- size: `115`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180024990`
- `0x180050718`

## callees

- `0x18001eb80`
- `0x180025a40`
- `0x18015ef60`

## string_xrefs

- `0x180025a99`: `LdrpThreadTokenSetMainThreadToken`

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
0x180025a40  push    rbx
0x180025a42  sub     rsp, 30h
0x180025a46  xor     r8d, r8d
0x180025a49  mov     [rsp+38h+arg_0], 0
0x180025a52  lea     r9, [rsp+38h+arg_0]
0x180025a57  mov     edx, 2001Ch
0x180025a5c  lea     rcx, [r8-2]
0x180025a60  call    NtOpenThreadToken
0x180025a65  mov     rcx, [rsp+38h+arg_0]
0x180025a6a  mov     ebx, eax
0x180025a6c  mov     cs:LdrpMainThreadToken, rcx
0x180025a73  cmp     eax, 0C000007Ch
0x180025a78  jnz     short loc_180025A83
0x180025a7a  mov     eax, ebx
0x180025a7c  add     rsp, 30h
0x180025a80  pop     rbx
0x180025a81  retn
0x180025a83  lea     rax, aStatus0xX; "Status: 0x%x\n"
0x180025a8a  mov     dword ptr [rsp+38h+ArgList], ebx; ArgList
0x180025a8e  mov     r9d, 2; int
0x180025a94  mov     [rsp+38h+Format], rax; Format
0x180025a99  lea     r8, aLdrpthreadtoke_1; "LdrpThreadTokenSetMainThreadToken"
0x180025aa0  mov     edx, 111Fh; int
0x180025aa5  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x180025aac  call    LdrpLogInternal
0x180025ab1  jmp     short loc_180025A7A
```
