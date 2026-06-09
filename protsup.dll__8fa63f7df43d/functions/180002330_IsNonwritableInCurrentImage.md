# _IsNonwritableInCurrentImage

- ea: `0x180002330`
- end: `0x18000237a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001e10`

## callees

- `0x1800022e0`
- `0x180002330`
- `0x180002380`

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
0x180002330  mov     [rsp+arg_0], rbx
0x180002335  push    rdi
0x180002336  sub     rsp, 20h
0x18000233a  mov     rbx, rcx
0x18000233d  lea     rdi, cs:180000000h
0x180002344  mov     rcx, rdi
0x180002347  call    _ValidateImageBase
0x18000234c  test    eax, eax
0x18000234e  jz      short loc_18000236F
0x180002350  sub     rbx, rdi
0x180002353  mov     rdx, rbx
0x180002356  mov     rcx, rdi
0x180002359  call    _FindPESection
0x18000235e  test    rax, rax
0x180002361  jz      short loc_18000236F
0x180002363  mov     eax, [rax+24h]
0x180002366  not     eax
0x180002368  shr     eax, 1Fh
0x18000236b  jmp     short loc_18000236F
0x18000236d  xor     eax, eax
0x18000236f  mov     rbx, [rsp+28h+arg_0]
0x180002374  add     rsp, 20h
0x180002378  pop     rdi
0x180002379  retn
0x180002aa0  push    rbp
0x180002aa2  sub     rsp, 20h
0x180002aa6  mov     rbp, rdx
0x180002aa9  mov     rax, [rcx]
0x180002aac  xor     ecx, ecx
0x180002aae  cmp     dword ptr [rax], 0C0000005h
0x180002ab4  setz    cl
0x180002ab7  mov     eax, ecx
0x180002ab9  add     rsp, 20h
0x180002abd  pop     rbp
0x180002abe  retn
```
