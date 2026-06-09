# _IsNonwritableInCurrentImage

- ea: `0x1800025a0`
- end: `0x1800025ea`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002080`

## callees

- `0x180002550`
- `0x1800025a0`
- `0x1800025f0`

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
0x1800025a0  mov     [rsp+arg_0], rbx
0x1800025a5  push    rdi
0x1800025a6  sub     rsp, 20h
0x1800025aa  mov     rbx, rcx
0x1800025ad  lea     rdi, cs:180000000h
0x1800025b4  mov     rcx, rdi
0x1800025b7  call    _ValidateImageBase
0x1800025bc  test    eax, eax
0x1800025be  jz      short loc_1800025DF
0x1800025c0  sub     rbx, rdi
0x1800025c3  mov     rdx, rbx
0x1800025c6  mov     rcx, rdi
0x1800025c9  call    _FindPESection
0x1800025ce  test    rax, rax
0x1800025d1  jz      short loc_1800025DF
0x1800025d3  mov     eax, [rax+24h]
0x1800025d6  not     eax
0x1800025d8  shr     eax, 1Fh
0x1800025db  jmp     short loc_1800025DF
0x1800025dd  xor     eax, eax
0x1800025df  mov     rbx, [rsp+28h+arg_0]
0x1800025e4  add     rsp, 20h
0x1800025e8  pop     rdi
0x1800025e9  retn
0x180007bb0  push    rbp
0x180007bb2  sub     rsp, 20h
0x180007bb6  mov     rbp, rdx
0x180007bb9  mov     rax, [rcx]
0x180007bbc  xor     ecx, ecx
0x180007bbe  cmp     dword ptr [rax], 0C0000005h
0x180007bc4  setz    cl
0x180007bc7  mov     eax, ecx
0x180007bc9  add     rsp, 20h
0x180007bcd  pop     rbp
0x180007bce  retn
```
