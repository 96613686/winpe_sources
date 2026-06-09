# WPP_RECORDER_AND_TRACE_SF_d

- ea: `0x18001d7b4`
- end: `0x18001d865`
- name: `WPP_RECORDER_AND_TRACE_SF_d`
- size: `177`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b914`
- `0x1800211b0`
- `0x1800385f0`
- `0x18003a590`
- `0x18004227c`

## callees

- `0x18001d7b4`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x18001d848`
- `WppRecorder!WppAutoLogTrace` at `0x18001d848`

## pseudocode

```c

```

## disassembly

```asm
0x18001d7b4  mov     r11, rsp
0x18001d7b7  mov     [r11+8], rbx
0x18001d7bb  mov     [r11+10h], rsi
0x18001d7bf  push    rdi
0x18001d7c0  sub     rsp, 40h
0x18001d7c4  movzx   ebx, [rsp+48h+arg_30]
0x18001d7cc  mov     rsi, r9
0x18001d7cf  mov     dil, r8b
0x18001d7d2  test    dl, dl
0x18001d7d4  jz      short loc_18001D80A
0x18001d7d6  mov     rax, cs:pfnWppTraceMessage
0x18001d7dd  lea     rdx, [r11+48h]
0x18001d7e1  mov     r8, [rsp+48h+arg_38]
0x18001d7e9  mov     r9d, ebx
0x18001d7ec  mov     qword ptr [r11-18h], 0
0x18001d7f4  mov     qword ptr [r11-20h], 4
0x18001d7fc  mov     [r11-28h], rdx
0x18001d800  mov     edx, 2Bh ; '+'
0x18001d805  call    _guard_dispatch_icall
0x18001d80a  test    dil, dil
0x18001d80d  jz      short loc_18001D854
0x18001d80f  mov     r9, [rsp+48h+arg_38]
0x18001d817  lea     rax, [rsp+48h+arg_40]
0x18001d81f  mov     r8d, [rsp+48h+arg_28]
0x18001d824  mov     rcx, rsi
0x18001d827  movzx   edx, [rsp+48h+arg_20]
0x18001d82c  mov     [rsp+48h+var_10], 0
0x18001d835  mov     [rsp+48h+var_18], 4
0x18001d83e  mov     [rsp+48h+var_20], rax
0x18001d843  mov     [rsp+48h+var_28], bx
0x18001d848  call    cs:__imp_WppAutoLogTrace
0x18001d84f  nop     dword ptr [rax+rax+00h]
0x18001d854  mov     rbx, [rsp+48h+arg_0]
0x18001d859  mov     rsi, [rsp+48h+arg_8]
0x18001d85e  add     rsp, 40h
0x18001d862  pop     rdi
0x18001d863  retn
```
