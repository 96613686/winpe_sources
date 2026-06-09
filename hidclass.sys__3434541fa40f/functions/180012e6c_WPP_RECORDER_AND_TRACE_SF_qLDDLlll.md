# WPP_RECORDER_AND_TRACE_SF_qLDDLlll

- ea: `0x180012e6c`
- end: `0x180013032`
- name: `WPP_RECORDER_AND_TRACE_SF_qLDDLlll`
- size: `454`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003b70`
- `0x180003f40`

## callees

- `0x180012e6c`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x180012f59`
- `WppRecorder!WppAutoLogTrace` at `0x180012f59`

## pseudocode

```c

```

## disassembly

```asm
0x180012e6c  push    rbp
0x180012e6e  push    rbx
0x180012e6f  push    rsi
0x180012e70  push    rdi
0x180012e71  push    r14
0x180012e73  lea     rbp, [rsp-7]
0x180012e78  sub     rsp, 0B0h
0x180012e7f  movzx   edi, [rbp+27h+arg_30]
0x180012e83  mov     rsi, r9
0x180012e86  mov     bl, r8b
0x180012e89  mov     r14d, 4
0x180012e8f  test    dl, dl
0x180012e91  jnz     loc_180012F74
0x180012e97  test    bl, bl
0x180012e99  jz      loc_180012F65
0x180012e9f  movzx   edx, [rbp+27h+arg_20]
0x180012ea3  lea     rax, [rbp+27h+arg_78]
0x180012eaa  mov     [rsp+0D0h+var_28], 0
0x180012eb6  lea     r9, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x180012ebd  mov     [rsp+0D0h+var_30], r14
0x180012ec5  mov     r8d, 9
0x180012ecb  mov     [rsp+0D0h+var_38], rax
0x180012ed3  mov     rcx, rsi
0x180012ed6  mov     [rsp+0D0h+var_40], r14
0x180012ede  lea     rax, [rbp+27h+arg_70]
0x180012ee5  mov     [rsp+0D0h+var_48], rax
0x180012eed  lea     rax, [rbp+27h+arg_68]
0x180012ef4  mov     [rsp+0D0h+var_50], r14
0x180012efc  mov     [rsp+0D0h+var_58], rax
0x180012f01  lea     rax, [rbp+27h+arg_60]
0x180012f08  mov     [rsp+0D0h+var_60], r14
0x180012f0d  mov     [rsp+0D0h+var_68], rax
0x180012f12  lea     rax, [rbp+27h+arg_58]
0x180012f19  mov     [rsp+0D0h+var_70], r14
0x180012f1e  mov     [rsp+0D0h+var_78], rax
0x180012f23  lea     rax, [rbp+27h+arg_50]
0x180012f2a  mov     [rsp+0D0h+var_80], r14
0x180012f2f  mov     [rsp+0D0h+var_88], rax
0x180012f34  lea     rax, [rbp+27h+arg_48]
0x180012f38  mov     [rsp+0D0h+var_90], r14
0x180012f3d  mov     [rsp+0D0h+var_98], rax
0x180012f42  lea     rax, [rbp+27h+arg_40]
0x180012f46  mov     [rsp+0D0h+var_A0], 8
0x180012f4f  mov     [rsp+0D0h+var_A8], rax
0x180012f54  mov     word ptr [rsp+0D0h+var_B0], di
0x180012f59  call    cs:__imp_WppAutoLogTrace
0x180012f60  nop     dword ptr [rax+rax+00h]
0x180012f65  add     rsp, 0B0h
0x180012f6c  pop     r14
0x180012f6e  pop     rdi
0x180012f6f  pop     rsi
0x180012f70  pop     rbx
0x180012f71  pop     rbp
0x180012f72  retn
0x180012f74  mov     rax, cs:pfnWppTraceMessage
0x180012f7b  lea     rdx, [rbp+27h+arg_78]
0x180012f82  mov     [rsp+0D0h+var_30], 0
0x180012f8e  lea     r8, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x180012f95  mov     [rsp+0D0h+var_38], r14
0x180012f9d  mov     r9d, edi
0x180012fa0  mov     [rsp+0D0h+var_40], rdx
0x180012fa8  lea     rdx, [rbp+27h+arg_70]
0x180012faf  mov     [rsp+0D0h+var_48], r14
0x180012fb7  mov     [rsp+0D0h+var_50], rdx
0x180012fbf  lea     rdx, [rbp+27h+arg_68]
0x180012fc6  mov     [rsp+0D0h+var_58], r14
0x180012fcb  mov     [rsp+0D0h+var_60], rdx
0x180012fd0  lea     rdx, [rbp+27h+arg_60]
0x180012fd7  mov     [rsp+0D0h+var_68], r14
0x180012fdc  mov     [rsp+0D0h+var_70], rdx
0x180012fe1  lea     rdx, [rbp+27h+arg_58]
0x180012fe8  mov     [rsp+0D0h+var_78], r14
0x180012fed  mov     [rsp+0D0h+var_80], rdx
0x180012ff2  lea     rdx, [rbp+27h+arg_50]
0x180012ff9  mov     [rsp+0D0h+var_88], r14
0x180012ffe  mov     [rsp+0D0h+var_90], rdx
0x180013003  lea     rdx, [rbp+27h+arg_48]
0x180013007  mov     [rsp+0D0h+var_98], r14
0x18001300c  mov     [rsp+0D0h+var_A0], rdx
0x180013011  lea     rdx, [rbp+27h+arg_40]
0x180013015  mov     [rsp+0D0h+var_A8], 8
0x18001301e  mov     [rsp+0D0h+var_B0], rdx
0x180013023  mov     edx, 2Bh ; '+'
0x180013028  call    _guard_dispatch_icall
0x18001302d  jmp     loc_180012E97
```
