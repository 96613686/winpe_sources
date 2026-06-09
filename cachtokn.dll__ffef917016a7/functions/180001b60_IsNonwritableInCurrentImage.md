# _IsNonwritableInCurrentImage

- ea: `0x180001b60`
- end: `0x180001baa`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001640`

## callees

- `0x180001b10`
- `0x180001b60`
- `0x180001bb0`

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
0x180001b60  mov     [rsp+arg_0], rbx
0x180001b65  push    rdi
0x180001b66  sub     rsp, 20h
0x180001b6a  mov     rbx, rcx
0x180001b6d  lea     rdi, cs:180000000h
0x180001b74  mov     rcx, rdi
0x180001b77  call    _ValidateImageBase
0x180001b7c  test    eax, eax
0x180001b7e  jz      short loc_180001B9F
0x180001b80  sub     rbx, rdi
0x180001b83  mov     rdx, rbx
0x180001b86  mov     rcx, rdi
0x180001b89  call    _FindPESection
0x180001b8e  test    rax, rax
0x180001b91  jz      short loc_180001B9F
0x180001b93  mov     eax, [rax+24h]
0x180001b96  not     eax
0x180001b98  shr     eax, 1Fh
0x180001b9b  jmp     short loc_180001B9F
0x180001b9d  xor     eax, eax
0x180001b9f  mov     rbx, [rsp+28h+arg_0]
0x180001ba4  add     rsp, 20h
0x180001ba8  pop     rdi
0x180001ba9  retn
0x180002960  push    rbp
0x180002962  sub     rsp, 20h
0x180002966  mov     rbp, rdx
0x180002969  mov     rax, [rcx]
0x18000296c  xor     ecx, ecx
0x18000296e  cmp     dword ptr [rax], 0C0000005h
0x180002974  setz    cl
0x180002977  mov     eax, ecx
0x180002979  add     rsp, 20h
0x18000297d  pop     rbp
0x18000297e  retn
```
