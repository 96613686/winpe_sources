# _IsNonwritableInCurrentImage

- ea: `0x180005e10`
- end: `0x180005e5a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800058f0`

## callees

- `0x180005dc0`
- `0x180005e10`
- `0x180005e60`

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
0x180005e10  mov     [rsp+arg_0], rbx
0x180005e15  push    rdi
0x180005e16  sub     rsp, 20h
0x180005e1a  mov     rbx, rcx
0x180005e1d  lea     rdi, cs:180000000h
0x180005e24  mov     rcx, rdi
0x180005e27  call    _ValidateImageBase
0x180005e2c  test    eax, eax
0x180005e2e  jz      short loc_180005E4F
0x180005e30  sub     rbx, rdi
0x180005e33  mov     rdx, rbx
0x180005e36  mov     rcx, rdi
0x180005e39  call    _FindPESection
0x180005e3e  test    rax, rax
0x180005e41  jz      short loc_180005E4F
0x180005e43  mov     eax, [rax+24h]
0x180005e46  not     eax
0x180005e48  shr     eax, 1Fh
0x180005e4b  jmp     short loc_180005E4F
0x180005e4d  xor     eax, eax
0x180005e4f  mov     rbx, [rsp+28h+arg_0]
0x180005e54  add     rsp, 20h
0x180005e58  pop     rdi
0x180005e59  retn
0x180007f00  push    rbp
0x180007f02  sub     rsp, 20h
0x180007f06  mov     rbp, rdx
0x180007f09  mov     rax, [rcx]
0x180007f0c  xor     ecx, ecx
0x180007f0e  cmp     dword ptr [rax], 0C0000005h
0x180007f14  setz    cl
0x180007f17  mov     eax, ecx
0x180007f19  add     rsp, 20h
0x180007f1d  pop     rbp
0x180007f1e  retn
```
