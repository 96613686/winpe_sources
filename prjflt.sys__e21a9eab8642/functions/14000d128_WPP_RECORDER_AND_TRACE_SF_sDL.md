# WPP_RECORDER_AND_TRACE_SF_sDL

- ea: `0x14000d128`
- end: `0x14000d265`
- name: `WPP_RECORDER_AND_TRACE_SF_sDL`
- size: `317`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, char, _DWORD, __int16, __int64, __int64, char, char)`
- caller_count: `119`
- callee_count: `2`
- tags: ``

## callers

- `0x140001658`
- `0x140001b3c`
- `0x1400020b4`
- `0x140003480`
- `0x1400035d4`
- `0x1400037e0`
- `0x140003a8c`
- `0x140003e6c`
- `0x14000420c`
- `0x140004640`
- `0x1400047cc`
- `0x14000500c`
- `0x1400066a4`
- `0x140007694`
- `0x140007990`
- `0x140007cec`
- `0x1400080e4`
- `0x1400081f0`
- `0x1400083b0`
- `0x1400089d8`
- `0x1400092ec`
- `0x140009b2c`
- `0x140009d20`
- `0x140021368`
- `0x140021550`
- `0x1400217a4`
- `0x140021c5c`
- `0x1400220d0`
- `0x140022320`
- `0x140023470`
- `0x1400237d0`
- `0x140023d68`
- `0x140024184`
- `0x140024758`
- `0x1400249dc`
- `0x140024b24`
- `0x140025a78`
- `0x1400260a4`
- `0x1400266ec`
- `0x140026d94`
- `0x140027144`
- `0x1400277f4`
- `0x140027ca0`
- `0x1400280f0`
- `0x140028464`
- `0x140028b30`
- `0x140029650`
- `0x14002a6b4`
- `0x14002b0d0`
- `0x14002b640`

## callees

- `0x140005cf4`
- `0x14000d128`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000d249`
- `WppRecorder!WppAutoLogTrace` at `0x14000d249`

## pseudocode

```c

```

## disassembly

```asm
0x14000d128  push    rbx
0x14000d12a  push    rbp
0x14000d12b  push    rsi
0x14000d12c  push    rdi
0x14000d12d  push    r13
0x14000d12f  push    r14
0x14000d131  push    r15
0x14000d133  sub     rsp, 60h
0x14000d137  mov     rbx, [rsp+98h+arg_40]
0x14000d13f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000d143  movzx   r14d, [rsp+98h+arg_30]
0x14000d14c  mov     bpl, r8b
0x14000d14f  lea     r8, aNull; "NULL"
0x14000d156  mov     r15, r9
0x14000d159  lea     esi, [rdi+6]
0x14000d15c  lea     r13d, [rdi+5]
0x14000d160  test    dl, dl
0x14000d162  jz      short loc_14000D1D3
0x14000d164  test    rbx, rbx
0x14000d167  jz      short loc_14000D17A
0x14000d169  mov     rax, rdi
0x14000d16c  inc     rax
0x14000d16f  cmp     byte ptr [rbx+rax], 0
0x14000d173  jnz     short loc_14000D16C
0x14000d175  inc     rax
0x14000d178  jmp     short loc_14000D17D
0x14000d17a  mov     rax, rsi
0x14000d17d  mov     [rsp+98h+var_50], 0
0x14000d186  lea     rdx, [rsp+98h+arg_50]
0x14000d18e  mov     [rsp+98h+var_58], r13
0x14000d193  test    rbx, rbx
0x14000d196  mov     [rsp+98h+var_60], rdx
0x14000d19b  mov     r9, rbx
0x14000d19e  lea     rdx, [rsp+98h+arg_48]
0x14000d1a6  mov     [rsp+98h+var_68], r13
0x14000d1ab  mov     [rsp+98h+var_70], rdx
0x14000d1b0  cmovz   r9, r8
0x14000d1b4  mov     r8, [rsp+98h+arg_38]
0x14000d1bc  mov     edx, r14d
0x14000d1bf  movzx   ecx, cx
0x14000d1c2  mov     [rsp+98h+var_78], rax
0x14000d1c7  call    FastWppTraceMessage
0x14000d1cc  lea     r8, aNull; "NULL"
0x14000d1d3  test    bpl, bpl
0x14000d1d6  jz      short loc_14000D255
0x14000d1d8  test    rbx, rbx
0x14000d1db  jz      short loc_14000D1ED
0x14000d1dd  inc     rdi
0x14000d1e0  cmp     byte ptr [rbx+rdi], 0
0x14000d1e4  jnz     short loc_14000D1DD
0x14000d1e6  lea     rsi, [rdi+1]
0x14000d1ea  test    rbx, rbx
0x14000d1ed  mov     r9, [rsp+98h+arg_38]
0x14000d1f5  lea     rax, [rsp+98h+arg_50]
0x14000d1fd  movzx   edx, [rsp+98h+arg_20]
0x14000d205  cmovz   rbx, r8
0x14000d209  mov     r8d, [rsp+98h+arg_28]
0x14000d211  mov     rcx, r15
0x14000d214  mov     [rsp+98h+var_40], 0
0x14000d21d  mov     [rsp+98h+var_48], r13
0x14000d222  mov     [rsp+98h+var_50], rax
0x14000d227  lea     rax, [rsp+98h+arg_48]
0x14000d22f  mov     [rsp+98h+var_58], r13
0x14000d234  mov     [rsp+98h+var_60], rax
0x14000d239  mov     [rsp+98h+var_68], rsi
0x14000d23e  mov     [rsp+98h+var_70], rbx
0x14000d243  mov     word ptr [rsp+98h+var_78], r14w
0x14000d249  call    cs:__imp_WppAutoLogTrace
0x14000d250  nop     dword ptr [rax+rax+00h]
0x14000d255  add     rsp, 60h
0x14000d259  pop     r15
0x14000d25b  pop     r14
0x14000d25d  pop     r13
0x14000d25f  pop     rdi
0x14000d260  pop     rsi
0x14000d261  pop     rbp
0x14000d262  pop     rbx
0x14000d263  retn
```
