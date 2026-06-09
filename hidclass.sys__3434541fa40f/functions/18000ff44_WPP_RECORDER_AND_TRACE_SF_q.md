# WPP_RECORDER_AND_TRACE_SF_q

- ea: `0x18000ff44`
- end: `0x180010000`
- name: `WPP_RECORDER_AND_TRACE_SF_q`
- size: `188`
- prototype: ``
- caller_count: `23`
- callee_count: `2`
- tags: ``

## callers

- `0x1800017d0`
- `0x18000ce08`
- `0x18000f4f0`
- `0x18000fcb4`
- `0x18000fe00`
- `0x180010010`
- `0x1800118c4`
- `0x1800144ec`
- `0x180015b98`
- `0x180016188`
- `0x180016984`
- `0x180016e14`
- `0x180017540`
- `0x180017d98`
- `0x180017ea4`
- `0x180018880`
- `0x180019694`
- `0x180019d28`
- `0x18001a890`
- `0x1800376c0`
- `0x18003b0d0`
- `0x18003b748`
- `0x18003e5b0`

## callees

- `0x18000ff44`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x18000ffa3`
- `WppRecorder!WppAutoLogTrace` at `0x18000ffa3`

## pseudocode

```c

```

## disassembly

```asm
0x18000ff44  mov     [rsp+arg_0], rbx
0x18000ff49  mov     [rsp+arg_8], rsi
0x18000ff4e  push    rdi
0x18000ff4f  sub     rsp, 40h
0x18000ff53  movzx   ebx, [rsp+48h+arg_30]
0x18000ff5b  mov     rsi, r9
0x18000ff5e  mov     dil, r8b
0x18000ff61  test    dl, dl
0x18000ff63  jnz     short loc_18000FFC0
0x18000ff65  test    dil, dil
0x18000ff68  jz      short loc_18000FFAF
0x18000ff6a  mov     r9, [rsp+48h+arg_38]
0x18000ff72  lea     rax, [rsp+48h+arg_40]
0x18000ff7a  mov     r8d, [rsp+48h+arg_28]
0x18000ff7f  mov     rcx, rsi
0x18000ff82  movzx   edx, [rsp+48h+arg_20]
0x18000ff87  mov     [rsp+48h+var_10], 0
0x18000ff90  mov     [rsp+48h+var_18], 8
0x18000ff99  mov     [rsp+48h+var_20], rax
0x18000ff9e  mov     word ptr [rsp+48h+var_28], bx
0x18000ffa3  call    cs:__imp_WppAutoLogTrace
0x18000ffaa  nop     dword ptr [rax+rax+00h]
0x18000ffaf  mov     rbx, [rsp+48h+arg_0]
0x18000ffb4  mov     rsi, [rsp+48h+arg_8]
0x18000ffb9  add     rsp, 40h
0x18000ffbd  pop     rdi
0x18000ffbe  retn
0x18000ffc0  mov     rax, cs:pfnWppTraceMessage
0x18000ffc7  lea     rdx, [rsp+48h+arg_40]
0x18000ffcf  mov     r8, [rsp+48h+arg_38]
0x18000ffd7  mov     r9d, ebx
0x18000ffda  mov     [rsp+48h+var_18], 0
0x18000ffe3  mov     [rsp+48h+var_20], 8
0x18000ffec  mov     [rsp+48h+var_28], rdx
0x18000fff1  mov     edx, 2Bh ; '+'
0x18000fff6  call    _guard_dispatch_icall
0x18000fffb  jmp     loc_18000FF65
```
