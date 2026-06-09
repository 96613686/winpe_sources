# WPP_RECORDER_AND_TRACE_SF_qdqqd

- ea: `0x1800127d0`
- end: `0x180012927`
- name: `WPP_RECORDER_AND_TRACE_SF_qdqqd`
- size: `343`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x1800043a0`
- `0x1800053c0`
- `0x180006ac8`
- `0x18000b140`
- `0x18000e880`
- `0x180012480`
- `0x1800125c4`
- `0x1800129a4`
- `0x180013040`
- `0x180025f64`
- `0x180026b40`

## callees

- `0x1800127d0`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x180012888`
- `WppRecorder!WppAutoLogTrace` at `0x180012888`

## pseudocode

```c

```

## disassembly

```asm
0x1800127d0  push    rbx
0x1800127d2  push    rbp
0x1800127d3  push    rsi
0x1800127d4  push    rdi
0x1800127d5  push    r14
0x1800127d7  sub     rsp, 80h
0x1800127de  movzx   edi, [rsp+0A8h+arg_30]
0x1800127e6  mov     ebp, 8
0x1800127eb  mov     rsi, r9
0x1800127ee  mov     bl, r8b
0x1800127f1  lea     r14d, [rbp-4]
0x1800127f5  test    dl, dl
0x1800127f7  jnz     loc_1800128A3
0x1800127fd  test    bl, bl
0x1800127ff  jz      loc_180012894
0x180012805  mov     r9, [rsp+0A8h+arg_38]
0x18001280d  lea     rax, [rsp+0A8h+arg_60]
0x180012815  mov     r8d, [rsp+0A8h+arg_28]
0x18001281d  mov     rcx, rsi
0x180012820  movzx   edx, [rsp+0A8h+arg_20]
0x180012828  mov     [rsp+0A8h+var_30], 0
0x180012831  mov     [rsp+0A8h+var_38], r14
0x180012836  mov     [rsp+0A8h+var_40], rax
0x18001283b  lea     rax, [rsp+0A8h+arg_58]
0x180012843  mov     [rsp+0A8h+var_48], rbp
0x180012848  mov     [rsp+0A8h+var_50], rax
0x18001284d  lea     rax, [rsp+0A8h+arg_50]
0x180012855  mov     [rsp+0A8h+var_58], rbp
0x18001285a  mov     [rsp+0A8h+var_60], rax
0x18001285f  lea     rax, [rsp+0A8h+arg_48]
0x180012867  mov     [rsp+0A8h+var_68], r14
0x18001286c  mov     [rsp+0A8h+var_70], rax
0x180012871  lea     rax, [rsp+0A8h+arg_40]
0x180012879  mov     [rsp+0A8h+var_78], rbp
0x18001287e  mov     [rsp+0A8h+var_80], rax
0x180012883  mov     word ptr [rsp+0A8h+var_88], di
0x180012888  call    cs:__imp_WppAutoLogTrace
0x18001288f  nop     dword ptr [rax+rax+00h]
0x180012894  add     rsp, 80h
0x18001289b  pop     r14
0x18001289d  pop     rdi
0x18001289e  pop     rsi
0x18001289f  pop     rbp
0x1800128a0  pop     rbx
0x1800128a1  retn
0x1800128a3  mov     rax, cs:pfnWppTraceMessage
0x1800128aa  lea     rdx, [rsp+0A8h+arg_60]
0x1800128b2  mov     r8, [rsp+0A8h+arg_38]
0x1800128ba  mov     r9d, edi
0x1800128bd  mov     [rsp+0A8h+var_38], 0
0x1800128c6  mov     [rsp+0A8h+var_40], r14
0x1800128cb  mov     [rsp+0A8h+var_48], rdx
0x1800128d0  lea     rdx, [rsp+0A8h+arg_58]
0x1800128d8  mov     [rsp+0A8h+var_50], rbp
0x1800128dd  mov     [rsp+0A8h+var_58], rdx
0x1800128e2  lea     rdx, [rsp+0A8h+arg_50]
0x1800128ea  mov     [rsp+0A8h+var_60], rbp
0x1800128ef  mov     [rsp+0A8h+var_68], rdx
0x1800128f4  lea     rdx, [rsp+0A8h+arg_48]
0x1800128fc  mov     [rsp+0A8h+var_70], r14
0x180012901  mov     [rsp+0A8h+var_78], rdx
0x180012906  lea     rdx, [rsp+0A8h+arg_40]
0x18001290e  mov     [rsp+0A8h+var_80], rbp
0x180012913  mov     [rsp+0A8h+var_88], rdx
0x180012918  mov     edx, 2Bh ; '+'
0x18001291d  call    _guard_dispatch_icall
0x180012922  jmp     loc_1800127FD
```
