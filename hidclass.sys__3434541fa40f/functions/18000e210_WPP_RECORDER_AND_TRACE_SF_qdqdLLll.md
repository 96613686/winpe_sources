# WPP_RECORDER_AND_TRACE_SF_qdqdLLll

- ea: `0x18000e210`
- end: `0x18000e430`
- name: `WPP_RECORDER_AND_TRACE_SF_qdqdLLll`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e004`

## callees

- `0x18000e210`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x18000e326`
- `WppRecorder!WppAutoLogTrace` at `0x18000e326`

## pseudocode

```c

```

## disassembly

```asm
0x18000e210  mov     [rsp+arg_0], rbx
0x18000e215  mov     [rsp+arg_8], rsi
0x18000e21a  push    rdi
0x18000e21b  sub     rsp, 0B0h
0x18000e222  movzx   edi, [rsp+0B8h+arg_30]
0x18000e22a  mov     rsi, r9
0x18000e22d  movzx   ebx, r8b
0x18000e231  test    dl, dl
0x18000e233  jnz     loc_18000E348
0x18000e239  test    bl, bl
0x18000e23b  jz      loc_18000E332
0x18000e241  mov     [rsp+0B8h+var_10], 0
0x18000e24d  lea     rax, [rsp+0B8h+arg_78]
0x18000e255  mov     [rsp+0B8h+var_18], 4
0x18000e261  lea     r9, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x18000e268  mov     [rsp+0B8h+var_20], rax
0x18000e270  mov     edx, 4
0x18000e275  mov     [rsp+0B8h+var_28], 4
0x18000e281  lea     rax, [rsp+0B8h+arg_70]
0x18000e289  mov     [rsp+0B8h+var_30], rax
0x18000e291  mov     r8d, 9
0x18000e297  mov     [rsp+0B8h+var_38], 4
0x18000e2a3  lea     rax, [rsp+0B8h+arg_68]
0x18000e2ab  mov     [rsp+0B8h+var_40], rax
0x18000e2b0  mov     rcx, rsi
0x18000e2b3  mov     [rsp+0B8h+var_48], 4
0x18000e2bc  lea     rax, [rsp+0B8h+arg_60]
0x18000e2c4  mov     [rsp+0B8h+var_50], rax
0x18000e2c9  lea     rax, [rsp+0B8h+arg_58]
0x18000e2d1  mov     [rsp+0B8h+var_58], 4
0x18000e2da  mov     [rsp+0B8h+var_60], rax
0x18000e2df  lea     rax, [rsp+0B8h+arg_50]
0x18000e2e7  mov     [rsp+0B8h+var_68], 8
0x18000e2f0  mov     [rsp+0B8h+var_70], rax
0x18000e2f5  lea     rax, [rsp+0B8h+arg_48]
0x18000e2fd  mov     [rsp+0B8h+var_78], 4
0x18000e306  mov     [rsp+0B8h+var_80], rax
0x18000e30b  lea     rax, [rsp+0B8h+arg_40]
0x18000e313  mov     [rsp+0B8h+var_88], 8
0x18000e31c  mov     [rsp+0B8h+var_90], rax
0x18000e321  mov     word ptr [rsp+0B8h+var_98], di
0x18000e326  call    cs:__imp_WppAutoLogTrace
0x18000e32d  nop     dword ptr [rax+rax+00h]
0x18000e332  lea     r11, [rsp+0B8h+var_8]
0x18000e33a  mov     rbx, [r11+10h]
0x18000e33e  mov     rsi, [r11+18h]
0x18000e342  mov     rsp, r11
0x18000e345  pop     rdi
0x18000e346  retn
0x18000e348  mov     rax, cs:pfnWppTraceMessage
0x18000e34f  lea     rdx, [rsp+0B8h+arg_78]
0x18000e357  mov     [rsp+0B8h+var_18], 0
0x18000e363  lea     r8, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x18000e36a  mov     [rsp+0B8h+var_20], 4
0x18000e376  mov     r9d, edi
0x18000e379  mov     [rsp+0B8h+var_28], rdx
0x18000e381  lea     rdx, [rsp+0B8h+arg_70]
0x18000e389  mov     [rsp+0B8h+var_30], 4
0x18000e395  mov     [rsp+0B8h+var_38], rdx
0x18000e39d  lea     rdx, [rsp+0B8h+arg_68]
0x18000e3a5  mov     [rsp+0B8h+var_40], 4
0x18000e3ae  mov     [rsp+0B8h+var_48], rdx
0x18000e3b3  lea     rdx, [rsp+0B8h+arg_60]
0x18000e3bb  mov     [rsp+0B8h+var_50], 4
0x18000e3c4  mov     [rsp+0B8h+var_58], rdx
0x18000e3c9  lea     rdx, [rsp+0B8h+arg_58]
0x18000e3d1  mov     [rsp+0B8h+var_60], 4
0x18000e3da  mov     [rsp+0B8h+var_68], rdx
0x18000e3df  lea     rdx, [rsp+0B8h+arg_50]
0x18000e3e7  mov     [rsp+0B8h+var_70], 8
0x18000e3f0  mov     [rsp+0B8h+var_78], rdx
0x18000e3f5  lea     rdx, [rsp+0B8h+arg_48]
0x18000e3fd  mov     [rsp+0B8h+var_80], 4
0x18000e406  mov     [rsp+0B8h+var_88], rdx
0x18000e40b  lea     rdx, [rsp+0B8h+arg_40]
0x18000e413  mov     [rsp+0B8h+var_90], 8
0x18000e41c  mov     [rsp+0B8h+var_98], rdx
0x18000e421  mov     edx, 2Bh ; '+'
0x18000e426  call    _guard_dispatch_icall
0x18000e42b  jmp     loc_18000E239
```
