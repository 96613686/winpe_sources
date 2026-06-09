# WPP_RECORDER_AND_TRACE_SF_qDlll

- ea: `0x18000daa8`
- end: `0x18000dbf4`
- name: `WPP_RECORDER_AND_TRACE_SF_qDlll`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d308`

## callees

- `0x18000daa8`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x18000db53`
- `WppRecorder!WppAutoLogTrace` at `0x18000db53`

## pseudocode

```c

```

## disassembly

```asm
0x18000daa8  push    rbx
0x18000daaa  push    rsi
0x18000daab  push    rdi
0x18000daac  push    r14
0x18000daae  sub     rsp, 88h
0x18000dab5  mov     esi, 4
0x18000daba  mov     rdi, r9
0x18000dabd  mov     bl, r8b
0x18000dac0  lea     r14d, [rsi+58h]
0x18000dac4  test    dl, dl
0x18000dac6  jnz     loc_18000DB6D
0x18000dacc  test    bl, bl
0x18000dace  jz      loc_18000DB5F
0x18000dad4  mov     [rsp+0A8h+var_30], 0
0x18000dadd  lea     rax, [rsp+0A8h+arg_60]
0x18000dae5  mov     [rsp+0A8h+var_38], rsi
0x18000daea  lea     r9, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18000daf1  mov     [rsp+0A8h+var_40], rax
0x18000daf6  mov     r8d, 9
0x18000dafc  mov     [rsp+0A8h+var_48], rsi
0x18000db01  lea     rax, [rsp+0A8h+arg_58]
0x18000db09  mov     [rsp+0A8h+var_50], rax
0x18000db0e  mov     edx, esi
0x18000db10  mov     [rsp+0A8h+var_58], rsi
0x18000db15  lea     rax, [rsp+0A8h+arg_50]
0x18000db1d  mov     [rsp+0A8h+var_60], rax
0x18000db22  mov     rcx, rdi
0x18000db25  mov     [rsp+0A8h+var_68], rsi
0x18000db2a  lea     rax, [rsp+0A8h+arg_48]
0x18000db32  mov     [rsp+0A8h+var_70], rax
0x18000db37  lea     rax, [rsp+0A8h+arg_40]
0x18000db3f  mov     [rsp+0A8h+var_78], 8
0x18000db48  mov     [rsp+0A8h+var_80], rax
0x18000db4d  mov     word ptr [rsp+0A8h+var_88], r14w
0x18000db53  call    cs:__imp_WppAutoLogTrace
0x18000db5a  nop     dword ptr [rax+rax+00h]
0x18000db5f  add     rsp, 88h
0x18000db66  pop     r14
0x18000db68  pop     rdi
0x18000db69  pop     rsi
0x18000db6a  pop     rbx
0x18000db6b  retn
0x18000db6d  mov     rax, cs:pfnWppTraceMessage
0x18000db74  lea     rdx, [rsp+0A8h+arg_60]
0x18000db7c  mov     [rsp+0A8h+var_38], 0
0x18000db85  lea     r8, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18000db8c  mov     [rsp+0A8h+var_40], rsi
0x18000db91  mov     r9d, r14d
0x18000db94  mov     [rsp+0A8h+var_48], rdx
0x18000db99  lea     rdx, [rsp+0A8h+arg_58]
0x18000dba1  mov     [rsp+0A8h+var_50], rsi
0x18000dba6  mov     [rsp+0A8h+var_58], rdx
0x18000dbab  lea     rdx, [rsp+0A8h+arg_50]
0x18000dbb3  mov     [rsp+0A8h+var_60], rsi
0x18000dbb8  mov     [rsp+0A8h+var_68], rdx
0x18000dbbd  lea     rdx, [rsp+0A8h+arg_48]
0x18000dbc5  mov     [rsp+0A8h+var_70], rsi
0x18000dbca  mov     [rsp+0A8h+var_78], rdx
0x18000dbcf  lea     rdx, [rsp+0A8h+arg_40]
0x18000dbd7  mov     [rsp+0A8h+var_80], 8
0x18000dbe0  mov     [rsp+0A8h+var_88], rdx
0x18000dbe5  mov     edx, 2Bh ; '+'
0x18000dbea  call    _guard_dispatch_icall
0x18000dbef  jmp     loc_18000DACC
```
