# WPP_RECORDER_AND_TRACE_SF_sDdd

- ea: `0x14000d5e8`
- end: `0x14000d74e`
- name: `WPP_RECORDER_AND_TRACE_SF_sDdd`
- size: `358`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x140002b50`
- `0x140002d9c`
- `0x1400092ec`
- `0x140022320`
- `0x140024b24`
- `0x14002a6b4`
- `0x14002c3f8`
- `0x14002c98c`
- `0x14002e374`
- `0x14002f5f0`
- `0x14003005c`
- `0x1400306f8`
- `0x1400311b0`
- `0x140031a00`
- `0x1400333c4`
- `0x1400359a0`
- `0x140045694`

## callees

- `0x140005cf4`
- `0x14000d5e8`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000d732`
- `WppRecorder!WppAutoLogTrace` at `0x14000d732`

## pseudocode

```c

```

## disassembly

```asm
0x14000d5e8  push    rbx
0x14000d5ea  push    rbp
0x14000d5eb  push    rsi
0x14000d5ec  push    rdi
0x14000d5ed  push    r13
0x14000d5ef  push    r14
0x14000d5f1  push    r15
0x14000d5f3  sub     rsp, 70h
0x14000d5f7  mov     rbx, [rsp+0A8h+arg_40]
0x14000d5ff  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000d603  movzx   r14d, [rsp+0A8h+arg_30]
0x14000d60c  mov     bpl, r8b
0x14000d60f  lea     r8, aNull; "NULL"
0x14000d616  mov     r15, r9
0x14000d619  lea     esi, [rdi+6]
0x14000d61c  lea     r13d, [rdi+5]
0x14000d620  test    dl, dl
0x14000d622  jz      loc_14000D6A9
0x14000d628  test    rbx, rbx
0x14000d62b  jz      short loc_14000D63E
0x14000d62d  mov     rax, rdi
0x14000d630  inc     rax
0x14000d633  cmp     byte ptr [rbx+rax], 0
0x14000d637  jnz     short loc_14000D630
0x14000d639  inc     rax
0x14000d63c  jmp     short loc_14000D641
0x14000d63e  mov     rax, rsi
0x14000d641  mov     [rsp+0A8h+var_50], 0
0x14000d64a  lea     rdx, [rsp+0A8h+arg_58]
0x14000d652  mov     [rsp+0A8h+var_58], r13
0x14000d657  test    rbx, rbx
0x14000d65a  mov     [rsp+0A8h+var_60], rdx
0x14000d65f  mov     r9, rbx
0x14000d662  mov     [rsp+0A8h+var_68], r13
0x14000d667  lea     rdx, [rsp+0A8h+arg_50]
0x14000d66f  mov     [rsp+0A8h+var_70], rdx
0x14000d674  cmovz   r9, r8
0x14000d678  mov     r8, [rsp+0A8h+arg_38]
0x14000d680  lea     rdx, [rsp+0A8h+arg_48]
0x14000d688  mov     [rsp+0A8h+var_78], r13
0x14000d68d  mov     [rsp+0A8h+var_80], rdx
0x14000d692  mov     edx, r14d
0x14000d695  movzx   ecx, cx
0x14000d698  mov     [rsp+0A8h+var_88], rax
0x14000d69d  call    FastWppTraceMessage
0x14000d6a2  lea     r8, aNull; "NULL"
0x14000d6a9  test    bpl, bpl
0x14000d6ac  jz      loc_14000D73E
0x14000d6b2  test    rbx, rbx
0x14000d6b5  jz      short loc_14000D6C7
0x14000d6b7  inc     rdi
0x14000d6ba  cmp     byte ptr [rbx+rdi], 0
0x14000d6be  jnz     short loc_14000D6B7
0x14000d6c0  lea     rsi, [rdi+1]
0x14000d6c4  test    rbx, rbx
0x14000d6c7  mov     r9, [rsp+0A8h+arg_38]
0x14000d6cf  lea     rax, [rsp+0A8h+arg_58]
0x14000d6d7  mov     [rsp+0A8h+var_40], 0
0x14000d6e0  cmovz   rbx, r8
0x14000d6e4  mov     r8d, [rsp+0A8h+arg_28]
0x14000d6ec  mov     edx, 2
0x14000d6f1  mov     [rsp+0A8h+var_48], r13
0x14000d6f6  mov     rcx, r15
0x14000d6f9  mov     [rsp+0A8h+var_50], rax
0x14000d6fe  lea     rax, [rsp+0A8h+arg_50]
0x14000d706  mov     [rsp+0A8h+var_58], r13
0x14000d70b  mov     [rsp+0A8h+var_60], rax
0x14000d710  lea     rax, [rsp+0A8h+arg_48]
0x14000d718  mov     [rsp+0A8h+var_68], r13
0x14000d71d  mov     [rsp+0A8h+var_70], rax
0x14000d722  mov     [rsp+0A8h+var_78], rsi
0x14000d727  mov     [rsp+0A8h+var_80], rbx
0x14000d72c  mov     word ptr [rsp+0A8h+var_88], r14w
0x14000d732  call    cs:__imp_WppAutoLogTrace
0x14000d739  nop     dword ptr [rax+rax+00h]
0x14000d73e  add     rsp, 70h
0x14000d742  pop     r15
0x14000d744  pop     r14
0x14000d746  pop     r13
0x14000d748  pop     rdi
0x14000d749  pop     rsi
0x14000d74a  pop     rbp
0x14000d74b  pop     rbx
0x14000d74c  retn
```
