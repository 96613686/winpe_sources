# _IsNonwritableInCurrentImage

- ea: `0x180001a40`
- end: `0x180001a8a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001520`

## callees

- `0x1800019f0`
- `0x180001a40`
- `0x180001a90`

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
0x180001a40  mov     [rsp+arg_0], rbx
0x180001a45  push    rdi
0x180001a46  sub     rsp, 20h
0x180001a4a  mov     rbx, rcx
0x180001a4d  lea     rdi, cs:180000000h
0x180001a54  mov     rcx, rdi
0x180001a57  call    _ValidateImageBase
0x180001a5c  test    eax, eax
0x180001a5e  jz      short loc_180001A7F
0x180001a60  sub     rbx, rdi
0x180001a63  mov     rdx, rbx
0x180001a66  mov     rcx, rdi
0x180001a69  call    _FindPESection
0x180001a6e  test    rax, rax
0x180001a71  jz      short loc_180001A7F
0x180001a73  mov     eax, [rax+24h]
0x180001a76  not     eax
0x180001a78  shr     eax, 1Fh
0x180001a7b  jmp     short loc_180001A7F
0x180001a7d  xor     eax, eax
0x180001a7f  mov     rbx, [rsp+28h+arg_0]
0x180001a84  add     rsp, 20h
0x180001a88  pop     rdi
0x180001a89  retn
0x180002300  push    rbp
0x180002302  sub     rsp, 20h
0x180002306  mov     rbp, rdx
0x180002309  mov     rax, [rcx]
0x18000230c  xor     ecx, ecx
0x18000230e  cmp     dword ptr [rax], 0C0000005h
0x180002314  setz    cl
0x180002317  mov     eax, ecx
0x180002319  add     rsp, 20h
0x18000231d  pop     rbp
0x18000231e  retn
```
