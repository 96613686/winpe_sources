# _IsNonwritableInCurrentImage

- ea: `0x1800017b0`
- end: `0x1800017fa`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010a0`

## callees

- `0x180001760`
- `0x1800017b0`
- `0x180001800`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(&_ImageBase);
  if ( (_DWORD)result )
  {
    result = FindPESection(&_ImageBase, a1 - (_QWORD)&_ImageBase);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800017b0  mov     [rsp+arg_0], rbx
0x1800017b5  push    rdi
0x1800017b6  sub     rsp, 20h
0x1800017ba  mov     rbx, rcx
0x1800017bd  lea     rdi, __ImageBase
0x1800017c4  mov     rcx, rdi
0x1800017c7  call    _ValidateImageBase
0x1800017cc  test    eax, eax
0x1800017ce  jz      short loc_1800017EF
0x1800017d0  sub     rbx, rdi
0x1800017d3  mov     rdx, rbx
0x1800017d6  mov     rcx, rdi
0x1800017d9  call    _FindPESection
0x1800017de  test    rax, rax
0x1800017e1  jz      short loc_1800017EF
0x1800017e3  mov     eax, [rax+24h]
0x1800017e6  not     eax
0x1800017e8  shr     eax, 1Fh
0x1800017eb  jmp     short loc_1800017EF
0x1800017ed  xor     eax, eax
0x1800017ef  mov     rbx, [rsp+28h+arg_0]
0x1800017f4  add     rsp, 20h
0x1800017f8  pop     rdi
0x1800017f9  retn
0x180003110  push    rbp
0x180003112  sub     rsp, 20h
0x180003116  mov     rbp, rdx
0x180003119  mov     rax, [rcx]
0x18000311c  xor     ecx, ecx
0x18000311e  cmp     dword ptr [rax], 0C0000005h
0x180003124  setz    cl
0x180003127  mov     eax, ecx
0x180003129  add     rsp, 20h
0x18000312d  pop     rbp
0x18000312e  retn
```
