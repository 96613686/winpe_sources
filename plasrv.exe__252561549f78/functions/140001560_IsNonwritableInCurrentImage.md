# _IsNonwritableInCurrentImage

- ea: `0x140001560`
- end: `0x1400015aa`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001140`

## callees

- `0x140001510`
- `0x140001560`
- `0x1400015b0`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(0x140000000uLL);
  if ( (_DWORD)result )
  {
    result = FindPESection(0x140000000LL, a1 - 0x140000000LL);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x140001560  mov     [rsp+arg_0], rbx
0x140001565  push    rdi
0x140001566  sub     rsp, 20h
0x14000156a  mov     rbx, rcx
0x14000156d  lea     rdi, cs:140000000h
0x140001574  mov     rcx, rdi
0x140001577  call    _ValidateImageBase
0x14000157c  test    eax, eax
0x14000157e  jz      short loc_14000159F
0x140001580  sub     rbx, rdi
0x140001583  mov     rdx, rbx
0x140001586  mov     rcx, rdi
0x140001589  call    _FindPESection
0x14000158e  test    rax, rax
0x140001591  jz      short loc_14000159F
0x140001593  mov     eax, [rax+24h]
0x140001596  not     eax
0x140001598  shr     eax, 1Fh
0x14000159b  jmp     short loc_14000159F
0x14000159d  xor     eax, eax
0x14000159f  mov     rbx, [rsp+28h+arg_0]
0x1400015a4  add     rsp, 20h
0x1400015a8  pop     rdi
0x1400015a9  retn
0x140001c10  push    rbp
0x140001c12  sub     rsp, 20h
0x140001c16  mov     rbp, rdx
0x140001c19  mov     rax, [rcx]
0x140001c1c  xor     ecx, ecx
0x140001c1e  cmp     dword ptr [rax], 0C0000005h
0x140001c24  setz    cl
0x140001c27  mov     eax, ecx
0x140001c29  add     rsp, 20h
0x140001c2d  pop     rbp
0x140001c2e  retn
```
