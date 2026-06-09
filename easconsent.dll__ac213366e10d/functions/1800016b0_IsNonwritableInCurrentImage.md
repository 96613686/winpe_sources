# _IsNonwritableInCurrentImage

- ea: `0x1800016b0`
- end: `0x1800016fa`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010c0`

## callees

- `0x180001660`
- `0x1800016b0`
- `0x180001700`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(0x180000000uLL);
  if ( (_DWORD)result )
  {
    result = FindPESection(0x180000000LL, a1 - 0x180000000LL);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800016b0  mov     [rsp+arg_0], rbx
0x1800016b5  push    rdi
0x1800016b6  sub     rsp, 20h
0x1800016ba  mov     rbx, rcx
0x1800016bd  lea     rdi, cs:180000000h
0x1800016c4  mov     rcx, rdi
0x1800016c7  call    _ValidateImageBase
0x1800016cc  test    eax, eax
0x1800016ce  jz      short loc_1800016EF
0x1800016d0  sub     rbx, rdi
0x1800016d3  mov     rdx, rbx
0x1800016d6  mov     rcx, rdi
0x1800016d9  call    _FindPESection
0x1800016de  test    rax, rax
0x1800016e1  jz      short loc_1800016EF
0x1800016e3  mov     eax, [rax+24h]
0x1800016e6  not     eax
0x1800016e8  shr     eax, 1Fh
0x1800016eb  jmp     short loc_1800016EF
0x1800016ed  xor     eax, eax
0x1800016ef  mov     rbx, [rsp+28h+arg_0]
0x1800016f4  add     rsp, 20h
0x1800016f8  pop     rdi
0x1800016f9  retn
0x180003490  push    rbp
0x180003492  sub     rsp, 20h
0x180003496  mov     rbp, rdx
0x180003499  mov     rax, [rcx]
0x18000349c  xor     ecx, ecx
0x18000349e  cmp     dword ptr [rax], 0C0000005h
0x1800034a4  setz    cl
0x1800034a7  mov     eax, ecx
0x1800034a9  add     rsp, 20h
0x1800034ad  pop     rbp
0x1800034ae  retn
```
