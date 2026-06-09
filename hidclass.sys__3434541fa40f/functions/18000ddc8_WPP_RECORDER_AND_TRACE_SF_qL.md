# WPP_RECORDER_AND_TRACE_SF_qL

- ea: `0x18000ddc8`
- end: `0x18000dea5`
- name: `WPP_RECORDER_AND_TRACE_SF_qL`
- size: `221`
- prototype: ``
- caller_count: `38`
- callee_count: `2`
- tags: ``

## callers

- `0x1800017d0`
- `0x18000621c`
- `0x180009d00`
- `0x18000d628`
- `0x180010830`
- `0x180011738`
- `0x1800144ec`
- `0x180014b0c`
- `0x180015b98`
- `0x180017264`
- `0x180017540`
- `0x180017a80`
- `0x180019d28`
- `0x18001a5b0`
- `0x18001c924`
- `0x180020038`
- `0x180020288`
- `0x18002136c`
- `0x180023b44`
- `0x180037008`
- `0x180037384`
- `0x1800377e0`
- `0x180037b20`
- `0x1800385f0`
- `0x1800395c8`
- `0x18003a1c0`
- `0x18003a590`
- `0x18003b0d0`
- `0x18003b444`
- `0x18003b748`
- `0x18003d250`
- `0x18003d608`
- `0x180041074`
- `0x180041248`
- `0x1800417d4`
- `0x1800419a8`
- `0x1800426e8`
- `0x180042b00`

## callees

- `0x18000ddc8`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x18000de88`
- `WppRecorder!WppAutoLogTrace` at `0x18000de88`

## pseudocode

```c

```

## disassembly

```asm
0x18000ddc8  mov     r11, rsp
0x18000ddcb  mov     [r11+8], rbx
0x18000ddcf  mov     [r11+10h], rsi
0x18000ddd3  push    rdi
0x18000ddd4  sub     rsp, 50h
0x18000ddd8  movzx   ebx, [rsp+58h+arg_30]
0x18000dde0  mov     rsi, r9
0x18000dde3  mov     dil, r8b
0x18000dde6  test    dl, dl
0x18000dde8  jz      short loc_18000DE2E
0x18000ddea  mov     rax, cs:pfnWppTraceMessage
0x18000ddf1  lea     rdx, [r11+50h]
0x18000ddf5  mov     r8, [rsp+58h+arg_38]
0x18000ddfd  mov     r9d, ebx
0x18000de00  mov     qword ptr [r11-18h], 0
0x18000de08  mov     qword ptr [r11-20h], 4
0x18000de10  mov     [r11-28h], rdx
0x18000de14  lea     rdx, [r11+48h]
0x18000de18  mov     qword ptr [r11-30h], 8
0x18000de20  mov     [r11-38h], rdx
0x18000de24  mov     edx, 2Bh ; '+'
0x18000de29  call    _guard_dispatch_icall
0x18000de2e  test    dil, dil
0x18000de31  jz      short loc_18000DE94
0x18000de33  mov     r9, [rsp+58h+arg_38]
0x18000de3b  lea     rax, [rsp+58h+arg_48]
0x18000de43  mov     r8d, [rsp+58h+arg_28]
0x18000de4b  mov     rcx, rsi
0x18000de4e  movzx   edx, [rsp+58h+arg_20]
0x18000de56  mov     [rsp+58h+var_10], 0
0x18000de5f  mov     [rsp+58h+var_18], 4
0x18000de68  mov     [rsp+58h+var_20], rax
0x18000de6d  lea     rax, [rsp+58h+arg_40]
0x18000de75  mov     [rsp+58h+var_28], 8
0x18000de7e  mov     [rsp+58h+var_30], rax
0x18000de83  mov     [rsp+58h+var_38], bx
0x18000de88  call    cs:__imp_WppAutoLogTrace
0x18000de8f  nop     dword ptr [rax+rax+00h]
0x18000de94  mov     rbx, [rsp+58h+arg_0]
0x18000de99  mov     rsi, [rsp+58h+arg_8]
0x18000de9e  add     rsp, 50h
0x18000dea2  pop     rdi
0x18000dea3  retn
```
