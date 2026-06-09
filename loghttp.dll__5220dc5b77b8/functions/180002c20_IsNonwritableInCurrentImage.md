# _IsNonwritableInCurrentImage

- ea: `0x180002c20`
- end: `0x180002c6a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002640`

## callees

- `0x180002bd0`
- `0x180002c20`
- `0x180002c70`

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
0x180002c20  mov     [rsp+arg_0], rbx
0x180002c25  push    rdi
0x180002c26  sub     rsp, 20h
0x180002c2a  mov     rbx, rcx
0x180002c2d  lea     rdi, __ImageBase
0x180002c34  mov     rcx, rdi
0x180002c37  call    _ValidateImageBase
0x180002c3c  test    eax, eax
0x180002c3e  jz      short loc_180002C5F
0x180002c40  sub     rbx, rdi
0x180002c43  mov     rdx, rbx
0x180002c46  mov     rcx, rdi
0x180002c49  call    _FindPESection
0x180002c4e  test    rax, rax
0x180002c51  jz      short loc_180002C5F
0x180002c53  mov     eax, [rax+24h]
0x180002c56  not     eax
0x180002c58  shr     eax, 1Fh
0x180002c5b  jmp     short loc_180002C5F
0x180002c5d  xor     eax, eax
0x180002c5f  mov     rbx, [rsp+28h+arg_0]
0x180002c64  add     rsp, 20h
0x180002c68  pop     rdi
0x180002c69  retn
0x180005a80  push    rbp
0x180005a82  sub     rsp, 20h
0x180005a86  mov     rbp, rdx
0x180005a89  mov     rax, [rcx]
0x180005a8c  xor     ecx, ecx
0x180005a8e  cmp     dword ptr [rax], 0C0000005h
0x180005a94  setz    cl
0x180005a97  mov     eax, ecx
0x180005a99  add     rsp, 20h
0x180005a9d  pop     rbp
0x180005a9e  retn
```
