# _IsNonwritableInCurrentImage

- ea: `0x180001770`
- end: `0x1800017ba`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001170`

## callees

- `0x180001720`
- `0x180001770`
- `0x1800017c0`

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
0x180001770  mov     [rsp+arg_0], rbx
0x180001775  push    rdi
0x180001776  sub     rsp, 20h
0x18000177a  mov     rbx, rcx
0x18000177d  lea     rdi, cs:180000000h
0x180001784  mov     rcx, rdi
0x180001787  call    _ValidateImageBase
0x18000178c  test    eax, eax
0x18000178e  jz      short loc_1800017AF
0x180001790  sub     rbx, rdi
0x180001793  mov     rdx, rbx
0x180001796  mov     rcx, rdi
0x180001799  call    _FindPESection
0x18000179e  test    rax, rax
0x1800017a1  jz      short loc_1800017AF
0x1800017a3  mov     eax, [rax+24h]
0x1800017a6  not     eax
0x1800017a8  shr     eax, 1Fh
0x1800017ab  jmp     short loc_1800017AF
0x1800017ad  xor     eax, eax
0x1800017af  mov     rbx, [rsp+28h+arg_0]
0x1800017b4  add     rsp, 20h
0x1800017b8  pop     rdi
0x1800017b9  retn
0x180004c80  push    rbp
0x180004c82  sub     rsp, 20h
0x180004c86  mov     rbp, rdx
0x180004c89  mov     rax, [rcx]
0x180004c8c  xor     ecx, ecx
0x180004c8e  cmp     dword ptr [rax], 0C0000005h
0x180004c94  setz    cl
0x180004c97  mov     eax, ecx
0x180004c99  add     rsp, 20h
0x180004c9d  pop     rbp
0x180004c9e  retn
```
