# WPP_RECORDER_AND_TRACE_SF_qLDDLLDD

- ea: `0x18000dbfc`
- end: `0x18000ddc0`
- name: `WPP_RECORDER_AND_TRACE_SF_qLDDLLDD`
- size: `452`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ce08`

## callees

- `0x18000dbfc`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x18000dce7`
- `WppRecorder!WppAutoLogTrace` at `0x18000dce7`

## pseudocode

```c

```

## disassembly

```asm
0x18000dbfc  push    rbp
0x18000dbfe  push    rbx
0x18000dbff  push    rsi
0x18000dc00  push    rdi
0x18000dc01  push    r15
0x18000dc03  lea     rbp, [rsp-7]
0x18000dc08  sub     rsp, 0B0h
0x18000dc0f  mov     esi, 4
0x18000dc14  mov     rdi, r9
0x18000dc17  mov     bl, r8b
0x18000dc1a  lea     r15d, [rsi+28h]
0x18000dc1e  test    dl, dl
0x18000dc20  jnz     loc_18000DD02
0x18000dc26  test    bl, bl
0x18000dc28  jz      loc_18000DCF3
0x18000dc2e  mov     [rsp+0D0h+var_28], 0
0x18000dc3a  lea     rax, [rbp+27h+arg_78]
0x18000dc41  mov     [rsp+0D0h+var_30], rsi
0x18000dc49  lea     r9, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x18000dc50  mov     [rsp+0D0h+var_38], rax
0x18000dc58  mov     r8d, 9
0x18000dc5e  mov     [rsp+0D0h+var_40], rsi
0x18000dc66  lea     rax, [rbp+27h+arg_70]
0x18000dc6d  mov     [rsp+0D0h+var_48], rax
0x18000dc75  mov     edx, esi
0x18000dc77  mov     [rsp+0D0h+var_50], rsi
0x18000dc7f  lea     rax, [rbp+27h+arg_68]
0x18000dc86  mov     [rsp+0D0h+var_58], rax
0x18000dc8b  mov     rcx, rdi
0x18000dc8e  mov     [rsp+0D0h+var_60], rsi
0x18000dc93  lea     rax, [rbp+27h+arg_60]
0x18000dc9a  mov     [rsp+0D0h+var_68], rax
0x18000dc9f  lea     rax, [rbp+27h+arg_58]
0x18000dca6  mov     [rsp+0D0h+var_70], rsi
0x18000dcab  mov     [rsp+0D0h+var_78], rax
0x18000dcb0  lea     rax, [rbp+27h+arg_50]
0x18000dcb7  mov     [rsp+0D0h+var_80], rsi
0x18000dcbc  mov     [rsp+0D0h+var_88], rax
0x18000dcc1  lea     rax, [rbp+27h+arg_48]
0x18000dcc5  mov     [rsp+0D0h+var_90], rsi
0x18000dcca  mov     [rsp+0D0h+var_98], rax
0x18000dccf  lea     rax, [rbp+27h+arg_40]
0x18000dcd3  mov     [rsp+0D0h+var_A0], 8
0x18000dcdc  mov     [rsp+0D0h+var_A8], rax
0x18000dce1  mov     word ptr [rsp+0D0h+var_B0], r15w
0x18000dce7  call    cs:__imp_WppAutoLogTrace
0x18000dcee  nop     dword ptr [rax+rax+00h]
0x18000dcf3  add     rsp, 0B0h
0x18000dcfa  pop     r15
0x18000dcfc  pop     rdi
0x18000dcfd  pop     rsi
0x18000dcfe  pop     rbx
0x18000dcff  pop     rbp
0x18000dd00  retn
0x18000dd02  mov     rax, cs:pfnWppTraceMessage
0x18000dd09  lea     rdx, [rbp+27h+arg_78]
0x18000dd10  mov     [rsp+0D0h+var_30], 0
0x18000dd1c  lea     r8, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x18000dd23  mov     [rsp+0D0h+var_38], rsi
0x18000dd2b  mov     r9d, r15d
0x18000dd2e  mov     [rsp+0D0h+var_40], rdx
0x18000dd36  lea     rdx, [rbp+27h+arg_70]
0x18000dd3d  mov     [rsp+0D0h+var_48], rsi
0x18000dd45  mov     [rsp+0D0h+var_50], rdx
0x18000dd4d  lea     rdx, [rbp+27h+arg_68]
0x18000dd54  mov     [rsp+0D0h+var_58], rsi
0x18000dd59  mov     [rsp+0D0h+var_60], rdx
0x18000dd5e  lea     rdx, [rbp+27h+arg_60]
0x18000dd65  mov     [rsp+0D0h+var_68], rsi
0x18000dd6a  mov     [rsp+0D0h+var_70], rdx
0x18000dd6f  lea     rdx, [rbp+27h+arg_58]
0x18000dd76  mov     [rsp+0D0h+var_78], rsi
0x18000dd7b  mov     [rsp+0D0h+var_80], rdx
0x18000dd80  lea     rdx, [rbp+27h+arg_50]
0x18000dd87  mov     [rsp+0D0h+var_88], rsi
0x18000dd8c  mov     [rsp+0D0h+var_90], rdx
0x18000dd91  lea     rdx, [rbp+27h+arg_48]
0x18000dd95  mov     [rsp+0D0h+var_98], rsi
0x18000dd9a  mov     [rsp+0D0h+var_A0], rdx
0x18000dd9f  lea     rdx, [rbp+27h+arg_40]
0x18000dda3  mov     [rsp+0D0h+var_A8], 8
0x18000ddac  mov     [rsp+0D0h+var_B0], rdx
0x18000ddb1  mov     edx, 2Bh ; '+'
0x18000ddb6  call    _guard_dispatch_icall
0x18000ddbb  jmp     loc_18000DC26
```
