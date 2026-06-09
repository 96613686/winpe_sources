# _IsNonwritableInCurrentImage

- ea: `0x180002e90`
- end: `0x180002eda`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002970`

## callees

- `0x180002e40`
- `0x180002e90`
- `0x180002ee0`

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
0x180002e90  mov     [rsp+arg_0], rbx
0x180002e95  push    rdi
0x180002e96  sub     rsp, 20h
0x180002e9a  mov     rbx, rcx
0x180002e9d  lea     rdi, cs:180000000h
0x180002ea4  mov     rcx, rdi
0x180002ea7  call    _ValidateImageBase
0x180002eac  test    eax, eax
0x180002eae  jz      short loc_180002ECF
0x180002eb0  sub     rbx, rdi
0x180002eb3  mov     rdx, rbx
0x180002eb6  mov     rcx, rdi
0x180002eb9  call    _FindPESection
0x180002ebe  test    rax, rax
0x180002ec1  jz      short loc_180002ECF
0x180002ec3  mov     eax, [rax+24h]
0x180002ec6  not     eax
0x180002ec8  shr     eax, 1Fh
0x180002ecb  jmp     short loc_180002ECF
0x180002ecd  xor     eax, eax
0x180002ecf  mov     rbx, [rsp+28h+arg_0]
0x180002ed4  add     rsp, 20h
0x180002ed8  pop     rdi
0x180002ed9  retn
0x180003fb0  push    rbp
0x180003fb2  sub     rsp, 20h
0x180003fb6  mov     rbp, rdx
0x180003fb9  mov     rax, [rcx]
0x180003fbc  xor     ecx, ecx
0x180003fbe  cmp     dword ptr [rax], 0C0000005h
0x180003fc4  setz    cl
0x180003fc7  mov     eax, ecx
0x180003fc9  add     rsp, 20h
0x180003fcd  pop     rbp
0x180003fce  retn
```
