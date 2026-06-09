# _IsNonwritableInCurrentImage

- ea: `0x140001510`
- end: `0x14000155a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400011a0`

## callees

- `0x1400014c0`
- `0x140001510`
- `0x140001560`

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
0x140001510  mov     [rsp+arg_0], rbx
0x140001515  push    rdi
0x140001516  sub     rsp, 20h
0x14000151a  mov     rbx, rcx
0x14000151d  lea     rdi, cs:140000000h
0x140001524  mov     rcx, rdi
0x140001527  call    _ValidateImageBase
0x14000152c  test    eax, eax
0x14000152e  jz      short loc_14000154F
0x140001530  sub     rbx, rdi
0x140001533  mov     rdx, rbx
0x140001536  mov     rcx, rdi
0x140001539  call    _FindPESection
0x14000153e  test    rax, rax
0x140001541  jz      short loc_14000154F
0x140001543  mov     eax, [rax+24h]
0x140001546  not     eax
0x140001548  shr     eax, 1Fh
0x14000154b  jmp     short loc_14000154F
0x14000154d  xor     eax, eax
0x14000154f  mov     rbx, [rsp+28h+arg_0]
0x140001554  add     rsp, 20h
0x140001558  pop     rdi
0x140001559  retn
0x140005600  push    rbp
0x140005602  sub     rsp, 20h
0x140005606  mov     rbp, rdx
0x140005609  mov     rax, [rcx]
0x14000560c  xor     ecx, ecx
0x14000560e  cmp     dword ptr [rax], 0C0000005h
0x140005614  setz    cl
0x140005617  mov     eax, ecx
0x140005619  add     rsp, 20h
0x14000561d  pop     rbp
0x14000561e  retn
```
