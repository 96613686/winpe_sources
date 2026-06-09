# WPP_RECORDER_AND_TRACE_SF_qdq

- ea: `0x180009a78`
- end: `0x180009b61`
- name: `WPP_RECORDER_AND_TRACE_SF_qdq`
- size: `233`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1800053c0`
- `0x18000a88c`
- `0x180013500`
- `0x1800144ec`
- `0x180015438`
- `0x18001a1cc`
- `0x18001ccc0`
- `0x18003c6b0`
- `0x18003e5b0`

## callees

- `0x180009a78`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x180009b4b`
- `WppRecorder!WppAutoLogTrace` at `0x180009b4b`

## pseudocode

```c

```

## disassembly

```asm
0x180009a78  mov     r11, rsp
0x180009a7b  push    rbx
0x180009a7c  push    rbp
0x180009a7d  push    rsi
0x180009a7e  push    rdi
0x180009a7f  sub     rsp, 68h
0x180009a83  movzx   edi, [rsp+88h+arg_30]
0x180009a8b  mov     rsi, r9
0x180009a8e  mov     bl, r8b
0x180009a91  mov     ebp, 8
0x180009a96  test    dl, dl
0x180009a98  jz      short loc_180009AE4
0x180009a9a  mov     rax, cs:pfnWppTraceMessage
0x180009aa1  lea     rdx, [r11+58h]
0x180009aa5  mov     r8, [rsp+88h+arg_38]
0x180009aad  mov     r9d, edi
0x180009ab0  mov     qword ptr [r11-38h], 0
0x180009ab8  mov     [r11-40h], rbp
0x180009abc  mov     [r11-48h], rdx
0x180009ac0  lea     rdx, [r11+50h]
0x180009ac4  mov     qword ptr [r11-50h], 4
0x180009acc  mov     [r11-58h], rdx
0x180009ad0  lea     rdx, [r11+48h]
0x180009ad4  mov     [r11-60h], rbp
0x180009ad8  mov     [r11-68h], rdx
0x180009adc  lea     edx, [rbp+23h]
0x180009adf  call    _guard_dispatch_icall
0x180009ae4  test    bl, bl
0x180009ae6  jz      short loc_180009B57
0x180009ae8  mov     r9, [rsp+88h+arg_38]
0x180009af0  lea     rax, [rsp+88h+arg_50]
0x180009af8  mov     r8d, [rsp+88h+arg_28]
0x180009b00  mov     rcx, rsi
0x180009b03  movzx   edx, [rsp+88h+arg_20]
0x180009b0b  mov     [rsp+88h+var_30], 0
0x180009b14  mov     [rsp+88h+var_38], rbp
0x180009b19  mov     [rsp+88h+var_40], rax
0x180009b1e  lea     rax, [rsp+88h+arg_48]
0x180009b26  mov     [rsp+88h+var_48], 4
0x180009b2f  mov     [rsp+88h+var_50], rax
0x180009b34  lea     rax, [rsp+88h+arg_40]
0x180009b3c  mov     [rsp+88h+var_58], rbp
0x180009b41  mov     [rsp+88h+var_60], rax
0x180009b46  mov     [rsp+88h+var_68], di
0x180009b4b  call    cs:__imp_WppAutoLogTrace
0x180009b52  nop     dword ptr [rax+rax+00h]
0x180009b57  add     rsp, 68h
0x180009b5b  pop     rdi
0x180009b5c  pop     rsi
0x180009b5d  pop     rbp
0x180009b5e  pop     rbx
0x180009b5f  retn
```
