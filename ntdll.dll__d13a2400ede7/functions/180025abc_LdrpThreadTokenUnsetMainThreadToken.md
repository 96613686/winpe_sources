# LdrpThreadTokenUnsetMainThreadToken

- ea: `0x180025abc`
- end: `0x180025b12`
- name: `LdrpThreadTokenUnsetMainThreadToken`
- size: `86`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180024990`
- `0x180050718`

## callees

- `0x18001eb80`
- `0x18015ecc0`

## string_xrefs

- `0x180025ad2`: `LdrpThreadTokenUnsetMainThreadToken`

## pseudocode

```c
__int64 LdrpThreadTokenUnsetMainThreadToken()
{
  unsigned int ArgList; // ebx

  ArgList = NtClose(LdrpMainThreadToken);
  LdrpMainThreadToken = 0;
  LdrpLogInternal(
    (int)"minkernel\\ldr\\ldrapi.c",
    4421,
    (int)"LdrpThreadTokenUnsetMainThreadToken",
    2,
    "Status: 0x%x\n",
    ArgList);
  return ArgList;
}

```

## disassembly

```asm
0x180025abc  push    rbx
0x180025abe  sub     rsp, 30h
0x180025ac2  mov     rcx, cs:LdrpMainThreadToken; Handle
0x180025ac9  call    NtClose
0x180025ace  mov     dword ptr [rsp+38h+ArgList], eax; ArgList
0x180025ad2  lea     r8, aLdrpthreadtoke; "LdrpThreadTokenUnsetMainThreadToken"
0x180025ad9  mov     ebx, eax
0x180025adb  mov     cs:LdrpMainThreadToken, 0
0x180025ae6  lea     rax, aStatus0xX; "Status: 0x%x\n"
0x180025aed  mov     r9d, 2; int
0x180025af3  mov     edx, 1145h; int
0x180025af8  mov     [rsp+38h+Format], rax; Format
0x180025afd  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x180025b04  call    LdrpLogInternal
0x180025b09  mov     eax, ebx
0x180025b0b  add     rsp, 30h
0x180025b0f  pop     rbx
0x180025b10  retn
```
