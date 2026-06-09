# _IsNonwritableInCurrentImage

- ea: `0x1800047c0`
- end: `0x18000480a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800042a0`

## callees

- `0x180004770`
- `0x1800047c0`
- `0x180004810`

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
0x1800047c0  mov     [rsp+arg_0], rbx
0x1800047c5  push    rdi
0x1800047c6  sub     rsp, 20h
0x1800047ca  mov     rbx, rcx
0x1800047cd  lea     rdi, cs:180000000h
0x1800047d4  mov     rcx, rdi
0x1800047d7  call    _ValidateImageBase
0x1800047dc  test    eax, eax
0x1800047de  jz      short loc_1800047FF
0x1800047e0  sub     rbx, rdi
0x1800047e3  mov     rdx, rbx
0x1800047e6  mov     rcx, rdi
0x1800047e9  call    _FindPESection
0x1800047ee  test    rax, rax
0x1800047f1  jz      short loc_1800047FF
0x1800047f3  mov     eax, [rax+24h]
0x1800047f6  not     eax
0x1800047f8  shr     eax, 1Fh
0x1800047fb  jmp     short loc_1800047FF
0x1800047fd  xor     eax, eax
0x1800047ff  mov     rbx, [rsp+28h+arg_0]
0x180004804  add     rsp, 20h
0x180004808  pop     rdi
0x180004809  retn
0x180004f50  push    rbp
0x180004f52  sub     rsp, 20h
0x180004f56  mov     rbp, rdx
0x180004f59  mov     rax, [rcx]
0x180004f5c  xor     ecx, ecx
0x180004f5e  cmp     dword ptr [rax], 0C0000005h
0x180004f64  setz    cl
0x180004f67  mov     eax, ecx
0x180004f69  add     rsp, 20h
0x180004f6d  pop     rbp
0x180004f6e  retn
```
