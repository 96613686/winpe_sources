# _IsNonwritableInCurrentImage

- ea: `0x1800016f0`
- end: `0x18000173a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001120`

## callees

- `0x1800016a0`
- `0x1800016f0`
- `0x180001740`

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
0x1800016f0  mov     [rsp+arg_0], rbx
0x1800016f5  push    rdi
0x1800016f6  sub     rsp, 20h
0x1800016fa  mov     rbx, rcx
0x1800016fd  lea     rdi, cs:180000000h
0x180001704  mov     rcx, rdi
0x180001707  call    _ValidateImageBase
0x18000170c  test    eax, eax
0x18000170e  jz      short loc_18000172F
0x180001710  sub     rbx, rdi
0x180001713  mov     rdx, rbx
0x180001716  mov     rcx, rdi
0x180001719  call    _FindPESection
0x18000171e  test    rax, rax
0x180001721  jz      short loc_18000172F
0x180001723  mov     eax, [rax+24h]
0x180001726  not     eax
0x180001728  shr     eax, 1Fh
0x18000172b  jmp     short loc_18000172F
0x18000172d  xor     eax, eax
0x18000172f  mov     rbx, [rsp+28h+arg_0]
0x180001734  add     rsp, 20h
0x180001738  pop     rdi
0x180001739  retn
0x180004e30  push    rbp
0x180004e32  sub     rsp, 20h
0x180004e36  mov     rbp, rdx
0x180004e39  mov     rax, [rcx]
0x180004e3c  xor     ecx, ecx
0x180004e3e  cmp     dword ptr [rax], 0C0000005h
0x180004e44  setz    cl
0x180004e47  mov     eax, ecx
0x180004e49  add     rsp, 20h
0x180004e4d  pop     rbp
0x180004e4e  retn
```
