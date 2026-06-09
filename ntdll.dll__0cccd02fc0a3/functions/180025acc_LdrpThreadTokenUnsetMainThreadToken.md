# LdrpThreadTokenUnsetMainThreadToken

- ea: `0x180025acc`
- end: `0x180025b22`
- name: `LdrpThreadTokenUnsetMainThreadToken`
- size: `86`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800249a0`
- `0x1800d6508`

## callees

- `0x18001eb80`
- `0x18015e4b0`

## string_xrefs

- `0x180025ae2`: `LdrpThreadTokenUnsetMainThreadToken`

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
0x180025acc  push    rbx
0x180025ace  sub     rsp, 30h
0x180025ad2  mov     rcx, cs:LdrpMainThreadToken; Handle
0x180025ad9  call    NtClose
0x180025ade  mov     dword ptr [rsp+38h+ArgList], eax; ArgList
0x180025ae2  lea     r8, aLdrpthreadtoke; "LdrpThreadTokenUnsetMainThreadToken"
0x180025ae9  mov     ebx, eax
0x180025aeb  mov     cs:LdrpMainThreadToken, 0
0x180025af6  lea     rax, aStatus0xX; "Status: 0x%x\n"
0x180025afd  mov     r9d, 2; int
0x180025b03  mov     edx, 1145h; int
0x180025b08  mov     [rsp+38h+Format], rax; Format
0x180025b0d  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x180025b14  call    LdrpLogInternal
0x180025b19  mov     eax, ebx
0x180025b1b  add     rsp, 30h
0x180025b1f  pop     rbx
0x180025b20  retn
```
