# _IsNonwritableInCurrentImage

- ea: `0x140001530`
- end: `0x14000157a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400011c0`

## callees

- `0x1400014e0`
- `0x140001530`
- `0x140001580`

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
0x140001530  mov     [rsp+arg_0], rbx
0x140001535  push    rdi
0x140001536  sub     rsp, 20h
0x14000153a  mov     rbx, rcx
0x14000153d  lea     rdi, cs:140000000h
0x140001544  mov     rcx, rdi
0x140001547  call    _ValidateImageBase
0x14000154c  test    eax, eax
0x14000154e  jz      short loc_14000156F
0x140001550  sub     rbx, rdi
0x140001553  mov     rdx, rbx
0x140001556  mov     rcx, rdi
0x140001559  call    _FindPESection
0x14000155e  test    rax, rax
0x140001561  jz      short loc_14000156F
0x140001563  mov     eax, [rax+24h]
0x140001566  not     eax
0x140001568  shr     eax, 1Fh
0x14000156b  jmp     short loc_14000156F
0x14000156d  xor     eax, eax
0x14000156f  mov     rbx, [rsp+28h+arg_0]
0x140001574  add     rsp, 20h
0x140001578  pop     rdi
0x140001579  retn
0x1400019b0  push    rbp
0x1400019b2  sub     rsp, 20h
0x1400019b6  mov     rbp, rdx
0x1400019b9  mov     rax, [rcx]
0x1400019bc  xor     ecx, ecx
0x1400019be  cmp     dword ptr [rax], 0C0000005h
0x1400019c4  setz    cl
0x1400019c7  mov     eax, ecx
0x1400019c9  add     rsp, 20h
0x1400019cd  pop     rbp
0x1400019ce  retn
```
