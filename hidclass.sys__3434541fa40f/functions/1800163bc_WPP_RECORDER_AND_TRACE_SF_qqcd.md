# WPP_RECORDER_AND_TRACE_SF_qqcd

- ea: `0x1800163bc`
- end: `0x1800164cf`
- name: `WPP_RECORDER_AND_TRACE_SF_qqcd`
- size: `275`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180003190`
- `0x1800043a0`
- `0x180004c00`
- `0x18000a020`
- `0x18000f4f0`
- `0x180019694`

## callees

- `0x1800163bc`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1800164b9`
- `WppRecorder!WppAutoLogTrace` at `0x1800164b9`

## pseudocode

```c

```

## disassembly

```asm
0x1800163bc  mov     r11, rsp
0x1800163bf  push    rbx
0x1800163c0  push    rbp
0x1800163c1  push    rsi
0x1800163c2  push    rdi
0x1800163c3  sub     rsp, 78h
0x1800163c7  movzx   edi, [rsp+98h+arg_30]
0x1800163cf  mov     rsi, r9
0x1800163d2  mov     bl, r8b
0x1800163d5  mov     ebp, 8
0x1800163da  test    dl, dl
0x1800163dc  jz      short loc_180016438
0x1800163de  mov     rax, cs:pfnWppTraceMessage
0x1800163e5  lea     rdx, [r11+60h]
0x1800163e9  mov     r8, [rsp+98h+arg_38]
0x1800163f1  mov     r9d, edi
0x1800163f4  mov     qword ptr [r11-38h], 0
0x1800163fc  mov     qword ptr [r11-40h], 4
0x180016404  mov     [r11-48h], rdx
0x180016408  lea     rdx, [r11+58h]
0x18001640c  mov     qword ptr [r11-50h], 1
0x180016414  mov     [r11-58h], rdx
0x180016418  lea     rdx, [r11+50h]
0x18001641c  mov     [r11-60h], rbp
0x180016420  mov     [r11-68h], rdx
0x180016424  lea     rdx, [r11+48h]
0x180016428  mov     [r11-70h], rbp
0x18001642c  mov     [r11-78h], rdx
0x180016430  lea     edx, [rbp+23h]
0x180016433  call    _guard_dispatch_icall
0x180016438  test    bl, bl
0x18001643a  jz      loc_1800164C5
0x180016440  mov     r9, [rsp+98h+arg_38]
0x180016448  lea     rax, [rsp+98h+arg_58]
0x180016450  mov     r8d, [rsp+98h+arg_28]
0x180016458  mov     rcx, rsi
0x18001645b  movzx   edx, [rsp+98h+arg_20]
0x180016463  mov     [rsp+98h+var_30], 0
0x18001646c  mov     [rsp+98h+var_38], 4
0x180016475  mov     [rsp+98h+var_40], rax
0x18001647a  lea     rax, [rsp+98h+arg_50]
0x180016482  mov     [rsp+98h+var_48], 1
0x18001648b  mov     [rsp+98h+var_50], rax
0x180016490  lea     rax, [rsp+98h+arg_48]
0x180016498  mov     [rsp+98h+var_58], rbp
0x18001649d  mov     [rsp+98h+var_60], rax
0x1800164a2  lea     rax, [rsp+98h+arg_40]
0x1800164aa  mov     [rsp+98h+var_68], rbp
0x1800164af  mov     [rsp+98h+var_70], rax
0x1800164b4  mov     [rsp+98h+var_78], di
0x1800164b9  call    cs:__imp_WppAutoLogTrace
0x1800164c0  nop     dword ptr [rax+rax+00h]
0x1800164c5  add     rsp, 78h
0x1800164c9  pop     rdi
0x1800164ca  pop     rsi
0x1800164cb  pop     rbp
0x1800164cc  pop     rbx
0x1800164cd  retn
```
