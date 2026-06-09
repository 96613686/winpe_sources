# WPP_RECORDER_AND_TRACE_SF_qdqLd

- ea: `0x18001952c`
- end: `0x18001965c`
- name: `WPP_RECORDER_AND_TRACE_SF_qdqLd`
- size: `304`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000621c`
- `0x180008a80`
- `0x180010528`
- `0x18001e99c`
- `0x180041698`

## callees

- `0x18001952c`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x180019641`
- `WppRecorder!WppAutoLogTrace` at `0x180019641`

## pseudocode

```c

```

## disassembly

```asm
0x18001952c  mov     r11, rsp
0x18001952f  push    rbx
0x180019530  push    rbp
0x180019531  push    rsi
0x180019532  push    rdi
0x180019533  push    r14
0x180019535  sub     rsp, 80h
0x18001953c  movzx   edi, [rsp+0A8h+arg_30]
0x180019544  mov     ebp, 4
0x180019549  mov     rsi, r9
0x18001954c  mov     bl, r8b
0x18001954f  lea     r14d, [rbp+4]
0x180019553  test    dl, dl
0x180019555  jz      short loc_1800195B6
0x180019557  mov     rax, cs:pfnWppTraceMessage
0x18001955e  lea     rdx, [r11+68h]
0x180019562  mov     r8, [rsp+0A8h+arg_38]
0x18001956a  mov     r9d, edi
0x18001956d  mov     qword ptr [r11-38h], 0
0x180019575  mov     [r11-40h], rbp
0x180019579  mov     [r11-48h], rdx
0x18001957d  lea     rdx, [r11+60h]
0x180019581  mov     [r11-50h], rbp
0x180019585  mov     [r11-58h], rdx
0x180019589  lea     rdx, [r11+58h]
0x18001958d  mov     [r11-60h], r14
0x180019591  mov     [r11-68h], rdx
0x180019595  lea     rdx, [r11+50h]
0x180019599  mov     [r11-70h], rbp
0x18001959d  mov     [r11-78h], rdx
0x1800195a1  lea     rdx, [r11+48h]
0x1800195a5  mov     [r11-80h], r14
0x1800195a9  mov     [rsp+0A8h+var_88], rdx
0x1800195ae  lea     edx, [rbp+27h]
0x1800195b1  call    _guard_dispatch_icall
0x1800195b6  test    bl, bl
0x1800195b8  jz      loc_18001964D
0x1800195be  mov     r9, [rsp+0A8h+arg_38]
0x1800195c6  lea     rax, [rsp+0A8h+arg_60]
0x1800195ce  mov     r8d, [rsp+0A8h+arg_28]
0x1800195d6  mov     rcx, rsi
0x1800195d9  movzx   edx, [rsp+0A8h+arg_20]
0x1800195e1  mov     [rsp+0A8h+var_30], 0
0x1800195ea  mov     [rsp+0A8h+var_38], rbp
0x1800195ef  mov     [rsp+0A8h+var_40], rax
0x1800195f4  lea     rax, [rsp+0A8h+arg_58]
0x1800195fc  mov     [rsp+0A8h+var_48], rbp
0x180019601  mov     [rsp+0A8h+var_50], rax
0x180019606  lea     rax, [rsp+0A8h+arg_50]
0x18001960e  mov     [rsp+0A8h+var_58], r14
0x180019613  mov     [rsp+0A8h+var_60], rax
0x180019618  lea     rax, [rsp+0A8h+arg_48]
0x180019620  mov     [rsp+0A8h+var_68], rbp
0x180019625  mov     [rsp+0A8h+var_70], rax
0x18001962a  lea     rax, [rsp+0A8h+arg_40]
0x180019632  mov     [rsp+0A8h+var_78], r14
0x180019637  mov     [rsp+0A8h+var_80], rax
0x18001963c  mov     word ptr [rsp+0A8h+var_88], di
0x180019641  call    cs:__imp_WppAutoLogTrace
0x180019648  nop     dword ptr [rax+rax+00h]
0x18001964d  add     rsp, 80h
0x180019654  pop     r14
0x180019656  pop     rdi
0x180019657  pop     rsi
0x180019658  pop     rbp
0x180019659  pop     rbx
0x18001965a  retn
```
