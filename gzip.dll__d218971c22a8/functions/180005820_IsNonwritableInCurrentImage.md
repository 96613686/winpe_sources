# _IsNonwritableInCurrentImage

- ea: `0x180005820`
- end: `0x18000586a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005010`

## callees

- `0x1800057d0`
- `0x180005820`
- `0x180005870`

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
0x180005820  mov     [rsp+arg_0], rbx
0x180005825  push    rdi
0x180005826  sub     rsp, 20h
0x18000582a  mov     rbx, rcx
0x18000582d  lea     rdi, cs:180000000h
0x180005834  mov     rcx, rdi
0x180005837  call    _ValidateImageBase
0x18000583c  test    eax, eax
0x18000583e  jz      short loc_18000585F
0x180005840  sub     rbx, rdi
0x180005843  mov     rdx, rbx
0x180005846  mov     rcx, rdi
0x180005849  call    _FindPESection
0x18000584e  test    rax, rax
0x180005851  jz      short loc_18000585F
0x180005853  mov     eax, [rax+24h]
0x180005856  not     eax
0x180005858  shr     eax, 1Fh
0x18000585b  jmp     short loc_18000585F
0x18000585d  xor     eax, eax
0x18000585f  mov     rbx, [rsp+28h+arg_0]
0x180005864  add     rsp, 20h
0x180005868  pop     rdi
0x180005869  retn
0x180006e10  push    rbp
0x180006e12  sub     rsp, 20h
0x180006e16  mov     rbp, rdx
0x180006e19  mov     rax, [rcx]
0x180006e1c  xor     ecx, ecx
0x180006e1e  cmp     dword ptr [rax], 0C0000005h
0x180006e24  setz    cl
0x180006e27  mov     eax, ecx
0x180006e29  add     rsp, 20h
0x180006e2d  pop     rbp
0x180006e2e  retn
```
