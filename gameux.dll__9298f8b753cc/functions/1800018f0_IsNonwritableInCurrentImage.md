# _IsNonwritableInCurrentImage

- ea: `0x1800018f0`
- end: `0x18000193a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800012f0`

## callees

- `0x1800018a0`
- `0x1800018f0`
- `0x180001940`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(&_ImageBase);
  if ( (_DWORD)result )
  {
    result = FindPESection(&_ImageBase, a1 - (_QWORD)&_ImageBase);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800018f0  mov     [rsp+arg_0], rbx
0x1800018f5  push    rdi
0x1800018f6  sub     rsp, 20h
0x1800018fa  mov     rbx, rcx
0x1800018fd  lea     rdi, __ImageBase
0x180001904  mov     rcx, rdi
0x180001907  call    _ValidateImageBase
0x18000190c  test    eax, eax
0x18000190e  jz      short loc_18000192F
0x180001910  sub     rbx, rdi
0x180001913  mov     rdx, rbx
0x180001916  mov     rcx, rdi
0x180001919  call    _FindPESection
0x18000191e  test    rax, rax
0x180001921  jz      short loc_18000192F
0x180001923  mov     eax, [rax+24h]
0x180001926  not     eax
0x180001928  shr     eax, 1Fh
0x18000192b  jmp     short loc_18000192F
0x18000192d  xor     eax, eax
0x18000192f  mov     rbx, [rsp+28h+arg_0]
0x180001934  add     rsp, 20h
0x180001938  pop     rdi
0x180001939  retn
0x1800033d0  push    rbp
0x1800033d2  sub     rsp, 20h
0x1800033d6  mov     rbp, rdx
0x1800033d9  mov     rax, [rcx]
0x1800033dc  xor     ecx, ecx
0x1800033de  cmp     dword ptr [rax], 0C0000005h
0x1800033e4  setz    cl
0x1800033e7  mov     eax, ecx
0x1800033e9  add     rsp, 20h
0x1800033ed  pop     rbp
0x1800033ee  retn
```
