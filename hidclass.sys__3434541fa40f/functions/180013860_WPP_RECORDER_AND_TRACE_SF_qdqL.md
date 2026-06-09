# WPP_RECORDER_AND_TRACE_SF_qdqL

- ea: `0x180013860`
- end: `0x180013967`
- name: `WPP_RECORDER_AND_TRACE_SF_qdqL`
- size: `263`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x1800043a0`
- `0x1800053c0`
- `0x18000621c`
- `0x180006ac8`
- `0x180008a80`
- `0x18000a430`
- `0x18000a88c`
- `0x180010528`
- `0x180015438`
- `0x18001ccc0`
- `0x180038090`
- `0x18003da1c`
- `0x18003e5b0`
- `0x18003ff7c`
- `0x1800405e4`
- `0x180041b44`
- `0x180041d94`
- `0x180042530`

## callees

- `0x180013860`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x18001394f`
- `WppRecorder!WppAutoLogTrace` at `0x18001394f`

## pseudocode

```c

```

## disassembly

```asm
0x180013860  mov     r11, rsp
0x180013863  push    rbx
0x180013864  push    rbp
0x180013865  push    rsi
0x180013866  push    rdi
0x180013867  push    r14
0x180013869  sub     rsp, 70h
0x18001386d  movzx   edi, [rsp+98h+arg_30]
0x180013875  mov     ebp, 4
0x18001387a  mov     rsi, r9
0x18001387d  mov     bl, r8b
0x180013880  lea     r14d, [rbp+4]
0x180013884  test    dl, dl
0x180013886  jz      short loc_1800138DA
0x180013888  mov     rax, cs:pfnWppTraceMessage
0x18001388f  lea     rdx, [r11+60h]
0x180013893  mov     r8, [rsp+98h+arg_38]
0x18001389b  mov     r9d, edi
0x18001389e  mov     qword ptr [r11-38h], 0
0x1800138a6  mov     [r11-40h], rbp
0x1800138aa  mov     [r11-48h], rdx
0x1800138ae  lea     rdx, [r11+58h]
0x1800138b2  mov     [r11-50h], r14
0x1800138b6  mov     [r11-58h], rdx
0x1800138ba  lea     rdx, [r11+50h]
0x1800138be  mov     [r11-60h], rbp
0x1800138c2  mov     [r11-68h], rdx
0x1800138c6  lea     rdx, [r11+48h]
0x1800138ca  mov     [r11-70h], r14
0x1800138ce  mov     [r11-78h], rdx
0x1800138d2  lea     edx, [rbp+27h]
0x1800138d5  call    _guard_dispatch_icall
0x1800138da  test    bl, bl
0x1800138dc  jz      short loc_18001395B
0x1800138de  mov     r9, [rsp+98h+arg_38]
0x1800138e6  lea     rax, [rsp+98h+arg_58]
0x1800138ee  mov     r8d, [rsp+98h+arg_28]
0x1800138f6  mov     rcx, rsi
0x1800138f9  movzx   edx, [rsp+98h+arg_20]
0x180013901  mov     [rsp+98h+var_30], 0
0x18001390a  mov     [rsp+98h+var_38], rbp
0x18001390f  mov     [rsp+98h+var_40], rax
0x180013914  lea     rax, [rsp+98h+arg_50]
0x18001391c  mov     [rsp+98h+var_48], r14
0x180013921  mov     [rsp+98h+var_50], rax
0x180013926  lea     rax, [rsp+98h+arg_48]
0x18001392e  mov     [rsp+98h+var_58], rbp
0x180013933  mov     [rsp+98h+var_60], rax
0x180013938  lea     rax, [rsp+98h+arg_40]
0x180013940  mov     [rsp+98h+var_68], r14
0x180013945  mov     [rsp+98h+var_70], rax
0x18001394a  mov     [rsp+98h+var_78], di
0x18001394f  call    cs:__imp_WppAutoLogTrace
0x180013956  nop     dword ptr [rax+rax+00h]
0x18001395b  add     rsp, 70h
0x18001395f  pop     r14
0x180013961  pop     rdi
0x180013962  pop     rsi
0x180013963  pop     rbp
0x180013964  pop     rbx
0x180013965  retn
```
