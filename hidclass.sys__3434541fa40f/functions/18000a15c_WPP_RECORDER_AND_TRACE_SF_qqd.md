# WPP_RECORDER_AND_TRACE_SF_qqd

- ea: `0x18000a15c`
- end: `0x18000a25d`
- name: `WPP_RECORDER_AND_TRACE_SF_qqd`
- size: `257`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x1800017d0`
- `0x180002a50`
- `0x180003190`
- `0x1800097f8`
- `0x180009bec`
- `0x180009d00`
- `0x18000b140`
- `0x180016188`
- `0x180017a80`
- `0x18001a890`
- `0x18001b4f0`
- `0x18001be48`
- `0x1800236e0`
- `0x180025c00`

## callees

- `0x18000a15c`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x18000a1e3`
- `WppRecorder!WppAutoLogTrace` at `0x18000a1e3`

## pseudocode

```c

```

## disassembly

```asm
0x18000a15c  push    rbx
0x18000a15e  push    rbp
0x18000a15f  push    rsi
0x18000a160  push    rdi
0x18000a161  sub     rsp, 68h
0x18000a165  movzx   edi, [rsp+88h+arg_30]
0x18000a16d  mov     rsi, r9
0x18000a170  mov     bl, r8b
0x18000a173  mov     ebp, 8
0x18000a178  test    dl, dl
0x18000a17a  jnz     short loc_18000A1F9
0x18000a17c  test    bl, bl
0x18000a17e  jz      short loc_18000A1EF
0x18000a180  mov     r9, [rsp+88h+arg_38]
0x18000a188  lea     rax, [rsp+88h+arg_50]
0x18000a190  mov     r8d, [rsp+88h+arg_28]
0x18000a198  mov     rcx, rsi
0x18000a19b  movzx   edx, [rsp+88h+arg_20]
0x18000a1a3  mov     [rsp+88h+var_30], 0
0x18000a1ac  mov     [rsp+88h+var_38], 4
0x18000a1b5  mov     [rsp+88h+var_40], rax
0x18000a1ba  lea     rax, [rsp+88h+arg_48]
0x18000a1c2  mov     [rsp+88h+var_48], rbp
0x18000a1c7  mov     [rsp+88h+var_50], rax
0x18000a1cc  lea     rax, [rsp+88h+arg_40]
0x18000a1d4  mov     [rsp+88h+var_58], rbp
0x18000a1d9  mov     [rsp+88h+var_60], rax
0x18000a1de  mov     word ptr [rsp+88h+var_68], di
0x18000a1e3  call    cs:__imp_WppAutoLogTrace
0x18000a1ea  nop     dword ptr [rax+rax+00h]
0x18000a1ef  add     rsp, 68h
0x18000a1f3  pop     rdi
0x18000a1f4  pop     rsi
0x18000a1f5  pop     rbp
0x18000a1f6  pop     rbx
0x18000a1f7  retn
0x18000a1f9  mov     rax, cs:pfnWppTraceMessage
0x18000a200  lea     rdx, [rsp+88h+arg_50]
0x18000a208  mov     r8, [rsp+88h+arg_38]
0x18000a210  mov     r9d, edi
0x18000a213  mov     [rsp+88h+var_38], 0
0x18000a21c  mov     [rsp+88h+var_40], 4
0x18000a225  mov     [rsp+88h+var_48], rdx
0x18000a22a  lea     rdx, [rsp+88h+arg_48]
0x18000a232  mov     [rsp+88h+var_50], rbp
0x18000a237  mov     [rsp+88h+var_58], rdx
0x18000a23c  lea     rdx, [rsp+88h+arg_40]
0x18000a244  mov     [rsp+88h+var_60], rbp
0x18000a249  mov     [rsp+88h+var_68], rdx
0x18000a24e  mov     edx, 2Bh ; '+'
0x18000a253  call    _guard_dispatch_icall
0x18000a258  jmp     loc_18000A17C
```
