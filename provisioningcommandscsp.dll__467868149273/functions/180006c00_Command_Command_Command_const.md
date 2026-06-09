# Command::Command(Command const &)

- ea: `0x180006c00`
- end: `0x180006ca7`
- name: `??0Command@@QEAA@AEBU0@@Z`
- size: `167`
- prototype: `Command *__fastcall(Command *__hidden this, const struct Command *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006a70`

## callees

- `0x180007e9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Command *__fastcall Command::Command(Command *this, const struct Command *a2)
{
  *((_QWORD *)this + 3) = 7;
  *((_QWORD *)this + 2) = 0;
  *(_WORD *)this = 0;
  std::wstring::assign(this);
  *((_QWORD *)this + 7) = 7;
  *((_QWORD *)this + 6) = 0;
  *((_WORD *)this + 16) = 0;
  std::wstring::assign((char *)this + 32);
  *((_QWORD *)this + 11) = 7;
  *((_QWORD *)this + 10) = 0;
  *((_WORD *)this + 32) = 0;
  std::wstring::assign((char *)this + 64);
  *((_DWORD *)this + 24) = *((_DWORD *)a2 + 24);
  *((_DWORD *)this + 25) = *((_DWORD *)a2 + 25);
  *((_DWORD *)this + 26) = *((_DWORD *)a2 + 26);
  *((_DWORD *)this + 27) = *((_DWORD *)a2 + 27);
  return this;
}

```

## disassembly

```asm
0x180006c00  mov     [rsp+arg_0], rcx
0x180006c05  push    rbx
0x180006c06  push    rbp
0x180006c07  push    rsi
0x180006c08  push    rdi
0x180006c09  sub     rsp, 28h
0x180006c0d  mov     rbx, rdx
0x180006c10  mov     rdi, rcx
0x180006c13  mov     ebp, 7
0x180006c18  mov     [rcx+18h], rbp
0x180006c1c  mov     qword ptr [rcx+10h], 0
0x180006c24  xor     eax, eax
0x180006c26  mov     [rcx], ax
0x180006c29  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006c2d  mov     r9, rsi
0x180006c30  xor     r8d, r8d
0x180006c33  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180006c38  nop
0x180006c39  lea     rcx, [rdi+20h]; void *
0x180006c3d  mov     [rcx+18h], rbp
0x180006c41  mov     qword ptr [rcx+10h], 0
0x180006c49  xor     eax, eax
0x180006c4b  mov     [rcx], ax
0x180006c4e  lea     rdx, [rbx+20h]
0x180006c52  mov     r9, rsi
0x180006c55  xor     r8d, r8d
0x180006c58  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180006c5d  nop
0x180006c5e  lea     rcx, [rdi+40h]; void *
0x180006c62  mov     [rcx+18h], rbp
0x180006c66  mov     qword ptr [rcx+10h], 0
0x180006c6e  xor     eax, eax
0x180006c70  mov     [rcx], ax
0x180006c73  lea     rdx, [rbx+40h]
0x180006c77  mov     r9, rsi
0x180006c7a  xor     r8d, r8d
0x180006c7d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180006c82  mov     eax, [rbx+60h]
0x180006c85  mov     [rdi+60h], eax
0x180006c88  mov     eax, [rbx+64h]
0x180006c8b  mov     [rdi+64h], eax
0x180006c8e  mov     eax, [rbx+68h]
0x180006c91  mov     [rdi+68h], eax
0x180006c94  mov     eax, [rbx+6Ch]
0x180006c97  mov     [rdi+6Ch], eax
0x180006c9a  mov     rax, rdi
0x180006c9d  add     rsp, 28h
0x180006ca1  pop     rdi
0x180006ca2  pop     rsi
0x180006ca3  pop     rbp
0x180006ca4  pop     rbx
0x180006ca5  retn
```
