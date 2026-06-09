# _IsNonwritableInCurrentImage

- ea: `0x180001aa0`
- end: `0x180001aea`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001150`

## callees

- `0x180001a50`
- `0x180001aa0`
- `0x180001af0`

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
0x180001aa0  mov     [rsp+arg_0], rbx
0x180001aa5  push    rdi
0x180001aa6  sub     rsp, 20h
0x180001aaa  mov     rbx, rcx
0x180001aad  lea     rdi, cs:180000000h
0x180001ab4  mov     rcx, rdi
0x180001ab7  call    _ValidateImageBase
0x180001abc  test    eax, eax
0x180001abe  jz      short loc_180001ADF
0x180001ac0  sub     rbx, rdi
0x180001ac3  mov     rdx, rbx
0x180001ac6  mov     rcx, rdi
0x180001ac9  call    _FindPESection
0x180001ace  test    rax, rax
0x180001ad1  jz      short loc_180001ADF
0x180001ad3  mov     eax, [rax+24h]
0x180001ad6  not     eax
0x180001ad8  shr     eax, 1Fh
0x180001adb  jmp     short loc_180001ADF
0x180001add  xor     eax, eax
0x180001adf  mov     rbx, [rsp+28h+arg_0]
0x180001ae4  add     rsp, 20h
0x180001ae8  pop     rdi
0x180001ae9  retn
0x1800063f0  push    rbp
0x1800063f2  sub     rsp, 20h
0x1800063f6  mov     rbp, rdx
0x1800063f9  mov     rax, [rcx]
0x1800063fc  xor     ecx, ecx
0x1800063fe  cmp     dword ptr [rax], 0C0000005h
0x180006404  setz    cl
0x180006407  mov     eax, ecx
0x180006409  add     rsp, 20h
0x18000640d  pop     rbp
0x18000640e  retn
```
