# _IsNonwritableInCurrentImage

- ea: `0x1800015e0`
- end: `0x18000162d`
- name: `_IsNonwritableInCurrentImage`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000109c`

## callees

- `0x180001590`
- `0x1800015e0`
- `0x180001640`

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
      return *(int *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800015e0  mov     [rsp+arg_0], rbx
0x1800015e5  push    rdi
0x1800015e6  sub     rsp, 20h
0x1800015ea  mov     rbx, rcx
0x1800015ed  lea     rdi, cs:180000000h
0x1800015f4  mov     rcx, rdi
0x1800015f7  call    _ValidateImageBase
0x1800015fc  test    eax, eax
0x1800015fe  jz      short loc_180001622
0x180001600  sub     rbx, rdi
0x180001603  mov     rdx, rbx
0x180001606  mov     rcx, rdi
0x180001609  call    _FindPESection
0x18000160e  test    rax, rax
0x180001611  jz      short loc_180001622
0x180001613  mov     eax, [rax+24h]
0x180001616  shr     eax, 1Fh
0x180001619  not     eax
0x18000161b  and     eax, 1
0x18000161e  jmp     short loc_180001622
0x180001620  xor     eax, eax
0x180001622  mov     rbx, [rsp+28h+arg_0]
0x180001627  add     rsp, 20h
0x18000162b  pop     rdi
0x18000162c  retn
0x1800023b0  push    rbp
0x1800023b2  sub     rsp, 20h
0x1800023b6  mov     rbp, rdx
0x1800023b9  mov     rax, [rcx]
0x1800023bc  xor     ecx, ecx
0x1800023be  cmp     dword ptr [rax], 0C0000005h
0x1800023c4  setz    cl
0x1800023c7  mov     eax, ecx
0x1800023c9  add     rsp, 20h
0x1800023cd  pop     rbp
0x1800023ce  retn
```
