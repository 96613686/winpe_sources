# Command::Command(Command const &)

- ea: `0x1400082c4`
- end: `0x14000836a`
- name: `??0Command@@QEAA@AEBU0@@Z`
- size: `166`
- prototype: `Command *__fastcall(Command *__hidden this, const struct Command *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400080e0`

## callees

- `0x14000961c`

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
0x1400082c4  mov     [rsp+arg_0], rcx
0x1400082c9  push    rbx
0x1400082ca  push    rbp
0x1400082cb  push    rsi
0x1400082cc  push    rdi
0x1400082cd  sub     rsp, 28h
0x1400082d1  mov     rbx, rdx
0x1400082d4  mov     rdi, rcx
0x1400082d7  mov     ebp, 7
0x1400082dc  mov     [rcx+18h], rbp
0x1400082e0  mov     qword ptr [rcx+10h], 0
0x1400082e8  xor     eax, eax
0x1400082ea  mov     [rcx], ax
0x1400082ed  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400082f1  mov     r9, rsi
0x1400082f4  xor     r8d, r8d
0x1400082f7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1400082fc  nop
0x1400082fd  lea     rcx, [rdi+20h]; void *
0x140008301  mov     [rcx+18h], rbp
0x140008305  mov     qword ptr [rcx+10h], 0
0x14000830d  xor     eax, eax
0x14000830f  mov     [rcx], ax
0x140008312  lea     rdx, [rbx+20h]
0x140008316  mov     r9, rsi
0x140008319  xor     r8d, r8d
0x14000831c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x140008321  nop
0x140008322  lea     rcx, [rdi+40h]; void *
0x140008326  mov     [rcx+18h], rbp
0x14000832a  mov     qword ptr [rcx+10h], 0
0x140008332  xor     eax, eax
0x140008334  mov     [rcx], ax
0x140008337  lea     rdx, [rbx+40h]
0x14000833b  mov     r9, rsi
0x14000833e  xor     r8d, r8d
0x140008341  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x140008346  mov     eax, [rbx+60h]
0x140008349  mov     [rdi+60h], eax
0x14000834c  mov     eax, [rbx+64h]
0x14000834f  mov     [rdi+64h], eax
0x140008352  mov     eax, [rbx+68h]
0x140008355  mov     [rdi+68h], eax
0x140008358  mov     eax, [rbx+6Ch]
0x14000835b  mov     [rdi+6Ch], eax
0x14000835e  mov     rax, rdi
0x140008361  add     rsp, 28h
0x140008365  pop     rdi
0x140008366  pop     rsi
0x140008367  pop     rbp
0x140008368  pop     rbx
0x140008369  retn
```
