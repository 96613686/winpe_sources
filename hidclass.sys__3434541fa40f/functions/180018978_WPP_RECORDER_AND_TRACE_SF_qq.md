# WPP_RECORDER_AND_TRACE_SF_qq

- ea: `0x180018978`
- end: `0x180018a3c`
- name: `WPP_RECORDER_AND_TRACE_SF_qq`
- size: `196`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180001430`
- `0x1800017d0`
- `0x180003190`
- `0x1800097f8`
- `0x18000f8a8`
- `0x180013500`
- `0x18001a890`
- `0x180025c00`

## callees

- `0x180018978`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x180018a26`
- `WppRecorder!WppAutoLogTrace` at `0x180018a26`

## pseudocode

```c

```

## disassembly

```asm
0x180018978  mov     r11, rsp
0x18001897b  push    rbx
0x18001897c  push    rbp
0x18001897d  push    rsi
0x18001897e  push    rdi
0x18001897f  sub     rsp, 58h
0x180018983  movzx   ebx, [rsp+78h+arg_30]
0x18001898b  mov     rsi, r9
0x18001898e  mov     dil, r8b
0x180018991  mov     ebp, 8
0x180018996  test    dl, dl
0x180018998  jz      short loc_1800189D4
0x18001899a  mov     rax, cs:pfnWppTraceMessage
0x1800189a1  lea     rdx, [r11+50h]
0x1800189a5  mov     r8, [rsp+78h+arg_38]
0x1800189ad  mov     r9d, ebx
0x1800189b0  mov     qword ptr [r11-38h], 0
0x1800189b8  mov     [r11-40h], rbp
0x1800189bc  mov     [r11-48h], rdx
0x1800189c0  lea     rdx, [r11+48h]
0x1800189c4  mov     [r11-50h], rbp
0x1800189c8  mov     [r11-58h], rdx
0x1800189cc  lea     edx, [rbp+23h]
0x1800189cf  call    _guard_dispatch_icall
0x1800189d4  test    dil, dil
0x1800189d7  jz      short loc_180018A32
0x1800189d9  mov     r9, [rsp+78h+arg_38]
0x1800189e1  lea     rax, [rsp+78h+arg_48]
0x1800189e9  mov     r8d, [rsp+78h+arg_28]
0x1800189f1  mov     rcx, rsi
0x1800189f4  movzx   edx, [rsp+78h+arg_20]
0x1800189fc  mov     [rsp+78h+var_30], 0
0x180018a05  mov     [rsp+78h+var_38], rbp
0x180018a0a  mov     [rsp+78h+var_40], rax
0x180018a0f  lea     rax, [rsp+78h+arg_40]
0x180018a17  mov     [rsp+78h+var_48], rbp
0x180018a1c  mov     [rsp+78h+var_50], rax
0x180018a21  mov     [rsp+78h+var_58], bx
0x180018a26  call    cs:__imp_WppAutoLogTrace
0x180018a2d  nop     dword ptr [rax+rax+00h]
0x180018a32  add     rsp, 58h
0x180018a36  pop     rdi
0x180018a37  pop     rsi
0x180018a38  pop     rbp
0x180018a39  pop     rbx
0x180018a3a  retn
```
