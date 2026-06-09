# Command::Command(Command const &)

- ea: `0x1800068e4`
- end: `0x18000698a`
- name: `??0Command@@QEAA@AEBU0@@Z`
- size: `166`
- prototype: `Command *__fastcall(Command *__hidden this, const struct Command *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006760`

## callees

- `0x180007b08`

## pseudocode

```c
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
0x1800068e4  mov     [rsp+arg_0], rcx
0x1800068e9  push    rbx
0x1800068ea  push    rbp
0x1800068eb  push    rsi
0x1800068ec  push    rdi
0x1800068ed  sub     rsp, 28h
0x1800068f1  mov     rbx, rdx
0x1800068f4  mov     rdi, rcx
0x1800068f7  mov     ebp, 7
0x1800068fc  mov     [rcx+18h], rbp
0x180006900  mov     qword ptr [rcx+10h], 0
0x180006908  xor     eax, eax
0x18000690a  mov     [rcx], ax
0x18000690d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006911  mov     r9, rsi
0x180006914  xor     r8d, r8d
0x180006917  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000691c  nop
0x18000691d  lea     rcx, [rdi+20h]; void *
0x180006921  mov     [rcx+18h], rbp
0x180006925  mov     qword ptr [rcx+10h], 0
0x18000692d  xor     eax, eax
0x18000692f  mov     [rcx], ax
0x180006932  lea     rdx, [rbx+20h]
0x180006936  mov     r9, rsi
0x180006939  xor     r8d, r8d
0x18000693c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180006941  nop
0x180006942  lea     rcx, [rdi+40h]; void *
0x180006946  mov     [rcx+18h], rbp
0x18000694a  mov     qword ptr [rcx+10h], 0
0x180006952  xor     eax, eax
0x180006954  mov     [rcx], ax
0x180006957  lea     rdx, [rbx+40h]
0x18000695b  mov     r9, rsi
0x18000695e  xor     r8d, r8d
0x180006961  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180006966  mov     eax, [rbx+60h]
0x180006969  mov     [rdi+60h], eax
0x18000696c  mov     eax, [rbx+64h]
0x18000696f  mov     [rdi+64h], eax
0x180006972  mov     eax, [rbx+68h]
0x180006975  mov     [rdi+68h], eax
0x180006978  mov     eax, [rbx+6Ch]
0x18000697b  mov     [rdi+6Ch], eax
0x18000697e  mov     rax, rdi
0x180006981  add     rsp, 28h
0x180006985  pop     rdi
0x180006986  pop     rsi
0x180006987  pop     rbp
0x180006988  pop     rbx
0x180006989  retn
```
