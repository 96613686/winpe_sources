# WPP_RECORDER_AND_TRACE_SF_qdqq

- ea: `0x180012d1c`
- end: `0x180012e49`
- name: `WPP_RECORDER_AND_TRACE_SF_qdqq`
- size: `301`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800053c0`
- `0x1800129a4`
- `0x180015438`
- `0x180025f64`
- `0x180026b40`

## callees

- `0x180012d1c`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x180012dbd`
- `WppRecorder!WppAutoLogTrace` at `0x180012dbd`

## pseudocode

```c

```

## disassembly

```asm
0x180012d1c  push    rbx
0x180012d1e  push    rbp
0x180012d1f  push    rsi
0x180012d20  push    rdi
0x180012d21  sub     rsp, 78h
0x180012d25  movzx   edi, [rsp+98h+arg_30]
0x180012d2d  mov     rsi, r9
0x180012d30  mov     bl, r8b
0x180012d33  mov     ebp, 8
0x180012d38  test    dl, dl
0x180012d3a  jnz     loc_180012DD3
0x180012d40  test    bl, bl
0x180012d42  jz      loc_180012DC9
0x180012d48  mov     r9, [rsp+98h+arg_38]
0x180012d50  lea     rax, [rsp+98h+arg_58]
0x180012d58  mov     r8d, [rsp+98h+arg_28]
0x180012d60  mov     rcx, rsi
0x180012d63  movzx   edx, [rsp+98h+arg_20]
0x180012d6b  mov     [rsp+98h+var_30], 0
0x180012d74  mov     [rsp+98h+var_38], rbp
0x180012d79  mov     [rsp+98h+var_40], rax
0x180012d7e  lea     rax, [rsp+98h+arg_50]
0x180012d86  mov     [rsp+98h+var_48], rbp
0x180012d8b  mov     [rsp+98h+var_50], rax
0x180012d90  lea     rax, [rsp+98h+arg_48]
0x180012d98  mov     [rsp+98h+var_58], 4
0x180012da1  mov     [rsp+98h+var_60], rax
0x180012da6  lea     rax, [rsp+98h+arg_40]
0x180012dae  mov     [rsp+98h+var_68], rbp
0x180012db3  mov     [rsp+98h+var_70], rax
0x180012db8  mov     word ptr [rsp+98h+var_78], di
0x180012dbd  call    cs:__imp_WppAutoLogTrace
0x180012dc4  nop     dword ptr [rax+rax+00h]
0x180012dc9  add     rsp, 78h
0x180012dcd  pop     rdi
0x180012dce  pop     rsi
0x180012dcf  pop     rbp
0x180012dd0  pop     rbx
0x180012dd1  retn
0x180012dd3  mov     rax, cs:pfnWppTraceMessage
0x180012dda  lea     rdx, [rsp+98h+arg_58]
0x180012de2  mov     r8, [rsp+98h+arg_38]
0x180012dea  mov     r9d, edi
0x180012ded  mov     [rsp+98h+var_38], 0
0x180012df6  mov     [rsp+98h+var_40], rbp
0x180012dfb  mov     [rsp+98h+var_48], rdx
0x180012e00  lea     rdx, [rsp+98h+arg_50]
0x180012e08  mov     [rsp+98h+var_50], rbp
0x180012e0d  mov     [rsp+98h+var_58], rdx
0x180012e12  lea     rdx, [rsp+98h+arg_48]
0x180012e1a  mov     [rsp+98h+var_60], 4
0x180012e23  mov     [rsp+98h+var_68], rdx
0x180012e28  lea     rdx, [rsp+98h+arg_40]
0x180012e30  mov     [rsp+98h+var_70], rbp
0x180012e35  mov     [rsp+98h+var_78], rdx
0x180012e3a  mov     edx, 2Bh ; '+'
0x180012e3f  call    _guard_dispatch_icall
0x180012e44  jmp     loc_180012D40
```
