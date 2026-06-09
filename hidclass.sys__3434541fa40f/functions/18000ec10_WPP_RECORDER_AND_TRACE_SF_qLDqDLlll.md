# WPP_RECORDER_AND_TRACE_SF_qLDqDLlll

- ea: `0x18000ec10`
- end: `0x18000ee68`
- name: `WPP_RECORDER_AND_TRACE_SF_qLDqDLlll`
- size: `600`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003b70`
- `0x180003f40`

## callees

- `0x18000ec10`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x18000ed42`
- `WppRecorder!WppAutoLogTrace` at `0x18000ed42`

## pseudocode

```c

```

## disassembly

```asm
0x18000ec10  mov     [rsp+arg_0], rbx
0x18000ec15  mov     [rsp+arg_8], rsi
0x18000ec1a  push    rdi
0x18000ec1b  sub     rsp, 0C0h
0x18000ec22  movzx   edi, [rsp+0C8h+arg_30]
0x18000ec2a  mov     rsi, r9
0x18000ec2d  movzx   ebx, r8b
0x18000ec31  test    dl, dl
0x18000ec33  jnz     loc_18000ED64
0x18000ec39  test    bl, bl
0x18000ec3b  jz      loc_18000ED4E
0x18000ec41  mov     [rsp+0C8h+var_10], 0
0x18000ec4d  lea     rax, [rsp+0C8h+arg_80]
0x18000ec55  mov     [rsp+0C8h+var_18], 4
0x18000ec61  lea     r9, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x18000ec68  mov     [rsp+0C8h+var_20], rax
0x18000ec70  mov     edx, 4
0x18000ec75  mov     [rsp+0C8h+var_28], 4
0x18000ec81  lea     rax, [rsp+0C8h+arg_78]
0x18000ec89  mov     [rsp+0C8h+var_30], rax
0x18000ec91  mov     r8d, 9
0x18000ec97  mov     [rsp+0C8h+var_38], 4
0x18000eca3  lea     rax, [rsp+0C8h+arg_70]
0x18000ecab  mov     [rsp+0C8h+var_40], rax
0x18000ecb3  mov     rcx, rsi
0x18000ecb6  mov     [rsp+0C8h+var_48], 4
0x18000ecc2  lea     rax, [rsp+0C8h+arg_68]
0x18000ecca  mov     [rsp+0C8h+var_50], rax
0x18000eccf  lea     rax, [rsp+0C8h+arg_60]
0x18000ecd7  mov     [rsp+0C8h+var_58], 4
0x18000ece0  mov     [rsp+0C8h+var_60], rax
0x18000ece5  lea     rax, [rsp+0C8h+arg_58]
0x18000eced  mov     [rsp+0C8h+var_68], 8
0x18000ecf6  mov     [rsp+0C8h+var_70], rax
0x18000ecfb  lea     rax, [rsp+0C8h+arg_50]
0x18000ed03  mov     [rsp+0C8h+var_78], 4
0x18000ed0c  mov     [rsp+0C8h+var_80], rax
0x18000ed11  lea     rax, [rsp+0C8h+arg_48]
0x18000ed19  mov     [rsp+0C8h+var_88], 4
0x18000ed22  mov     [rsp+0C8h+var_90], rax
0x18000ed27  lea     rax, [rsp+0C8h+arg_40]
0x18000ed2f  mov     [rsp+0C8h+var_98], 8
0x18000ed38  mov     [rsp+0C8h+var_A0], rax
0x18000ed3d  mov     word ptr [rsp+0C8h+var_A8], di
0x18000ed42  call    cs:__imp_WppAutoLogTrace
0x18000ed49  nop     dword ptr [rax+rax+00h]
0x18000ed4e  lea     r11, [rsp+0C8h+var_8]
0x18000ed56  mov     rbx, [r11+10h]
0x18000ed5a  mov     rsi, [r11+18h]
0x18000ed5e  mov     rsp, r11
0x18000ed61  pop     rdi
0x18000ed62  retn
0x18000ed64  mov     rax, cs:pfnWppTraceMessage
0x18000ed6b  lea     rdx, [rsp+0C8h+arg_80]
0x18000ed73  mov     [rsp+0C8h+var_18], 0
0x18000ed7f  lea     r8, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x18000ed86  mov     [rsp+0C8h+var_20], 4
0x18000ed92  mov     r9d, edi
0x18000ed95  mov     [rsp+0C8h+var_28], rdx
0x18000ed9d  lea     rdx, [rsp+0C8h+arg_78]
0x18000eda5  mov     [rsp+0C8h+var_30], 4
0x18000edb1  mov     [rsp+0C8h+var_38], rdx
0x18000edb9  lea     rdx, [rsp+0C8h+arg_70]
0x18000edc1  mov     [rsp+0C8h+var_40], 4
0x18000edcd  mov     [rsp+0C8h+var_48], rdx
0x18000edd5  lea     rdx, [rsp+0C8h+arg_68]
0x18000eddd  mov     [rsp+0C8h+var_50], 4
0x18000ede6  mov     [rsp+0C8h+var_58], rdx
0x18000edeb  lea     rdx, [rsp+0C8h+arg_60]
0x18000edf3  mov     [rsp+0C8h+var_60], 4
0x18000edfc  mov     [rsp+0C8h+var_68], rdx
0x18000ee01  lea     rdx, [rsp+0C8h+arg_58]
0x18000ee09  mov     [rsp+0C8h+var_70], 8
0x18000ee12  mov     [rsp+0C8h+var_78], rdx
0x18000ee17  lea     rdx, [rsp+0C8h+arg_50]
0x18000ee1f  mov     [rsp+0C8h+var_80], 4
0x18000ee28  mov     [rsp+0C8h+var_88], rdx
0x18000ee2d  lea     rdx, [rsp+0C8h+arg_48]
0x18000ee35  mov     [rsp+0C8h+var_90], 4
0x18000ee3e  mov     [rsp+0C8h+var_98], rdx
0x18000ee43  lea     rdx, [rsp+0C8h+arg_40]
0x18000ee4b  mov     [rsp+0C8h+var_A0], 8
0x18000ee54  mov     [rsp+0C8h+var_A8], rdx
0x18000ee59  mov     edx, 2Bh ; '+'
0x18000ee5e  call    _guard_dispatch_icall
0x18000ee63  jmp     loc_18000EC39
```
