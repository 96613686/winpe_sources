# _IsNonwritableInCurrentImage

- ea: `0x140001500`
- end: `0x14000154a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001190`

## callees

- `0x1400014b0`
- `0x140001500`
- `0x140001550`

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
0x140001500  mov     [rsp+arg_0], rbx
0x140001505  push    rdi
0x140001506  sub     rsp, 20h
0x14000150a  mov     rbx, rcx
0x14000150d  lea     rdi, cs:140000000h
0x140001514  mov     rcx, rdi
0x140001517  call    _ValidateImageBase
0x14000151c  test    eax, eax
0x14000151e  jz      short loc_14000153F
0x140001520  sub     rbx, rdi
0x140001523  mov     rdx, rbx
0x140001526  mov     rcx, rdi
0x140001529  call    _FindPESection
0x14000152e  test    rax, rax
0x140001531  jz      short loc_14000153F
0x140001533  mov     eax, [rax+24h]
0x140001536  not     eax
0x140001538  shr     eax, 1Fh
0x14000153b  jmp     short loc_14000153F
0x14000153d  xor     eax, eax
0x14000153f  mov     rbx, [rsp+28h+arg_0]
0x140001544  add     rsp, 20h
0x140001548  pop     rdi
0x140001549  retn
0x140002df0  push    rbp
0x140002df2  sub     rsp, 20h
0x140002df6  mov     rbp, rdx
0x140002df9  mov     rax, [rcx]
0x140002dfc  xor     ecx, ecx
0x140002dfe  cmp     dword ptr [rax], 0C0000005h
0x140002e04  setz    cl
0x140002e07  mov     eax, ecx
0x140002e09  add     rsp, 20h
0x140002e0d  pop     rbp
0x140002e0e  retn
```
