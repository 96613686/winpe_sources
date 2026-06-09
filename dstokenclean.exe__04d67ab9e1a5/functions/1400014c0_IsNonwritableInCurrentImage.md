# _IsNonwritableInCurrentImage

- ea: `0x1400014c0`
- end: `0x14000150a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001160`

## callees

- `0x140001470`
- `0x1400014c0`
- `0x140001510`

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
0x1400014c0  mov     [rsp+arg_0], rbx
0x1400014c5  push    rdi
0x1400014c6  sub     rsp, 20h
0x1400014ca  mov     rbx, rcx
0x1400014cd  lea     rdi, cs:140000000h
0x1400014d4  mov     rcx, rdi
0x1400014d7  call    _ValidateImageBase
0x1400014dc  test    eax, eax
0x1400014de  jz      short loc_1400014FF
0x1400014e0  sub     rbx, rdi
0x1400014e3  mov     rdx, rbx
0x1400014e6  mov     rcx, rdi
0x1400014e9  call    _FindPESection
0x1400014ee  test    rax, rax
0x1400014f1  jz      short loc_1400014FF
0x1400014f3  mov     eax, [rax+24h]
0x1400014f6  not     eax
0x1400014f8  shr     eax, 1Fh
0x1400014fb  jmp     short loc_1400014FF
0x1400014fd  xor     eax, eax
0x1400014ff  mov     rbx, [rsp+28h+arg_0]
0x140001504  add     rsp, 20h
0x140001508  pop     rdi
0x140001509  retn
0x1400020a0  push    rbp
0x1400020a2  sub     rsp, 20h
0x1400020a6  mov     rbp, rdx
0x1400020a9  mov     rax, [rcx]
0x1400020ac  xor     ecx, ecx
0x1400020ae  cmp     dword ptr [rax], 0C0000005h
0x1400020b4  setz    cl
0x1400020b7  mov     eax, ecx
0x1400020b9  add     rsp, 20h
0x1400020bd  pop     rbp
0x1400020be  retn
```
