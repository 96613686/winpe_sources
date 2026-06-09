# WPP_RECORDER_AND_TRACE_SF_qLL

- ea: `0x180014e80`
- end: `0x180014f69`
- name: `WPP_RECORDER_AND_TRACE_SF_qLL`
- size: `233`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x1800017d0`
- `0x180014cb0`
- `0x180014dac`
- `0x180016a40`
- `0x18001c4c0`
- `0x18001c734`
- `0x1800206e0`
- `0x180020c54`
- `0x180037008`
- `0x1800377e0`
- `0x180037b20`
- `0x18003b0d0`
- `0x18003d250`
- `0x180041248`
- `0x180041d94`

## callees

- `0x180014e80`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x180014f53`
- `WppRecorder!WppAutoLogTrace` at `0x180014f53`

## pseudocode

```c

```

## disassembly

```asm
0x180014e80  mov     r11, rsp
0x180014e83  push    rbx
0x180014e84  push    rbp
0x180014e85  push    rsi
0x180014e86  push    rdi
0x180014e87  sub     rsp, 68h
0x180014e8b  movzx   edi, [rsp+88h+arg_30]
0x180014e93  mov     rsi, r9
0x180014e96  mov     bl, r8b
0x180014e99  mov     ebp, 4
0x180014e9e  test    dl, dl
0x180014ea0  jz      short loc_180014EEC
0x180014ea2  mov     rax, cs:pfnWppTraceMessage
0x180014ea9  lea     rdx, [r11+58h]
0x180014ead  mov     r8, [rsp+88h+arg_38]
0x180014eb5  mov     r9d, edi
0x180014eb8  mov     qword ptr [r11-38h], 0
0x180014ec0  mov     [r11-40h], rbp
0x180014ec4  mov     [r11-48h], rdx
0x180014ec8  lea     rdx, [r11+50h]
0x180014ecc  mov     [r11-50h], rbp
0x180014ed0  mov     [r11-58h], rdx
0x180014ed4  lea     rdx, [r11+48h]
0x180014ed8  mov     qword ptr [r11-60h], 8
0x180014ee0  mov     [r11-68h], rdx
0x180014ee4  lea     edx, [rbp+27h]
0x180014ee7  call    _guard_dispatch_icall
0x180014eec  test    bl, bl
0x180014eee  jz      short loc_180014F5F
0x180014ef0  mov     r9, [rsp+88h+arg_38]
0x180014ef8  lea     rax, [rsp+88h+arg_50]
0x180014f00  mov     r8d, [rsp+88h+arg_28]
0x180014f08  mov     rcx, rsi
0x180014f0b  movzx   edx, [rsp+88h+arg_20]
0x180014f13  mov     [rsp+88h+var_30], 0
0x180014f1c  mov     [rsp+88h+var_38], rbp
0x180014f21  mov     [rsp+88h+var_40], rax
0x180014f26  lea     rax, [rsp+88h+arg_48]
0x180014f2e  mov     [rsp+88h+var_48], rbp
0x180014f33  mov     [rsp+88h+var_50], rax
0x180014f38  lea     rax, [rsp+88h+arg_40]
0x180014f40  mov     [rsp+88h+var_58], 8
0x180014f49  mov     [rsp+88h+var_60], rax
0x180014f4e  mov     [rsp+88h+var_68], di
0x180014f53  call    cs:__imp_WppAutoLogTrace
0x180014f5a  nop     dword ptr [rax+rax+00h]
0x180014f5f  add     rsp, 68h
0x180014f63  pop     rdi
0x180014f64  pop     rsi
0x180014f65  pop     rbp
0x180014f66  pop     rbx
0x180014f67  retn
```
