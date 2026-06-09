# LdrpThreadTokenSetImpersonationToken

- ea: `0x180025998`
- end: `0x1800259f6`
- name: `LdrpThreadTokenSetImpersonationToken`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025870`

## callees

- `0x18001eb80`
- `0x18015e470`

## string_xrefs

- `0x1800259c1`: `LdrpThreadTokenSetImpersonationToken`

## pseudocode

```c
__int64 __fastcall LdrpThreadTokenSetImpersonationToken(__int64 a1)
{
  unsigned int ArgList; // ebx
  __int64 v3; // [rsp+40h] [rbp+8h] BYREF

  v3 = a1;
  ArgList = NtSetInformationThread(-2, 5, &v3, 8);
  LdrpLogInternal(
    (int)"minkernel\\ldr\\ldrapi.c",
    4480,
    (int)"LdrpThreadTokenSetImpersonationToken",
    2,
    "Status: 0x%x\n",
    ArgList);
  return ArgList;
}

```

## disassembly

```asm
0x180025998  mov     [rsp+arg_0], rcx
0x18002599d  push    rbx
0x18002599e  sub     rsp, 30h
0x1800259a2  mov     r9d, 8
0x1800259a8  lea     r8, [rsp+38h+arg_0]
0x1800259ad  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x1800259b4  lea     edx, [r9-3]
0x1800259b8  call    NtSetInformationThread
0x1800259bd  mov     dword ptr [rsp+38h+ArgList], eax; ArgList
0x1800259c1  lea     r8, aLdrpthreadtoke_0; "LdrpThreadTokenSetImpersonationToken"
0x1800259c8  mov     ebx, eax
0x1800259ca  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x1800259d1  lea     rax, aStatus0xX; "Status: 0x%x\n"
0x1800259d8  mov     r9d, 2; int
0x1800259de  mov     edx, 1180h; int
0x1800259e3  mov     [rsp+38h+Format], rax; Format
0x1800259e8  call    LdrpLogInternal
0x1800259ed  mov     eax, ebx
0x1800259ef  add     rsp, 30h
0x1800259f3  pop     rbx
0x1800259f4  retn
```
