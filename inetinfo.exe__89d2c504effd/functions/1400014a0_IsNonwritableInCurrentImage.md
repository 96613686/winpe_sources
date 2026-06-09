# _IsNonwritableInCurrentImage

- ea: `0x1400014a0`
- end: `0x1400014ea`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001140`

## callees

- `0x140001450`
- `0x1400014a0`
- `0x1400014f0`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(0x140000000uLL);
  if ( (_DWORD)result )
  {
    result = FindPESection(0x140000000uLL, a1 - 0x140000000LL);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400014a0  mov     [rsp+arg_0], rbx
0x1400014a5  push    rdi
0x1400014a6  sub     rsp, 20h
0x1400014aa  mov     rbx, rcx
0x1400014ad  lea     rdi, cs:140000000h
0x1400014b4  mov     rcx, rdi
0x1400014b7  call    _ValidateImageBase
0x1400014bc  test    eax, eax
0x1400014be  jz      short loc_1400014DF
0x1400014c0  sub     rbx, rdi
0x1400014c3  mov     rdx, rbx
0x1400014c6  mov     rcx, rdi
0x1400014c9  call    _FindPESection
0x1400014ce  test    rax, rax
0x1400014d1  jz      short loc_1400014DF
0x1400014d3  mov     eax, [rax+24h]
0x1400014d6  not     eax
0x1400014d8  shr     eax, 1Fh
0x1400014db  jmp     short loc_1400014DF
0x1400014dd  xor     eax, eax
0x1400014df  mov     rbx, [rsp+28h+arg_0]
0x1400014e4  add     rsp, 20h
0x1400014e8  pop     rdi
0x1400014e9  retn
0x140002930  push    rbp
0x140002932  sub     rsp, 20h
0x140002936  mov     rbp, rdx
0x140002939  mov     rax, [rcx]
0x14000293c  xor     ecx, ecx
0x14000293e  cmp     dword ptr [rax], 0C0000005h
0x140002944  setz    cl
0x140002947  mov     eax, ecx
0x140002949  add     rsp, 20h
0x14000294d  pop     rbp
0x14000294e  retn
```
