# _IsNonwritableInCurrentImage

- ea: `0x180001880`
- end: `0x1800018ca`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001050`

## callees

- `0x180001830`
- `0x180001880`
- `0x1800018d0`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(0x180000000uLL);
  if ( (_DWORD)result )
  {
    result = FindPESection(0x180000000uLL, a1 - 0x180000000LL);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001880  mov     [rsp+arg_0], rbx
0x180001885  push    rdi
0x180001886  sub     rsp, 20h
0x18000188a  mov     rbx, rcx
0x18000188d  lea     rdi, cs:180000000h
0x180001894  mov     rcx, rdi
0x180001897  call    _ValidateImageBase
0x18000189c  test    eax, eax
0x18000189e  jz      short loc_1800018BF
0x1800018a0  sub     rbx, rdi
0x1800018a3  mov     rdx, rbx
0x1800018a6  mov     rcx, rdi
0x1800018a9  call    _FindPESection
0x1800018ae  test    rax, rax
0x1800018b1  jz      short loc_1800018BF
0x1800018b3  mov     eax, [rax+24h]
0x1800018b6  not     eax
0x1800018b8  shr     eax, 1Fh
0x1800018bb  jmp     short loc_1800018BF
0x1800018bd  xor     eax, eax
0x1800018bf  mov     rbx, [rsp+28h+arg_0]
0x1800018c4  add     rsp, 20h
0x1800018c8  pop     rdi
0x1800018c9  retn
0x1800057f0  push    rbp
0x1800057f2  sub     rsp, 20h
0x1800057f6  mov     rbp, rdx
0x1800057f9  mov     rax, [rcx]
0x1800057fc  xor     ecx, ecx
0x1800057fe  cmp     dword ptr [rax], 0C0000005h
0x180005804  setz    cl
0x180005807  mov     eax, ecx
0x180005809  add     rsp, 20h
0x18000580d  pop     rbp
0x18000580e  retn
```
