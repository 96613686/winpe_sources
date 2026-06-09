# WPP_RECORDER_AND_TRACE_SF_qdLLiiIIIIIIIII

- ea: `0x18000150c`
- end: `0x1800017c6`
- name: `WPP_RECORDER_AND_TRACE_SF_qdLLiiIIIIIIIII`
- size: `698`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002560`

## callees

- `0x18000150c`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x180001675`
- `WppRecorder!WppAutoLogTrace` at `0x180001675`

## pseudocode

```c

```

## disassembly

```asm
0x18000150c  push    rbp
0x18000150e  push    rbx
0x18000150f  push    rsi
0x180001510  push    rdi
0x180001511  push    r14
0x180001513  push    r15
0x180001515  lea     rbp, [rsp+78h]
0x18000151a  sub     rsp, 128h
0x180001521  movzx   edi, [rbp-50h+arg_30]
0x180001525  mov     r14d, 8
0x18000152b  mov     rsi, r9
0x18000152e  mov     bl, r8b
0x180001531  lea     r15d, [r14-4]
0x180001535  test    dl, dl
0x180001537  jnz     loc_180001692
0x18000153d  test    bl, bl
0x18000153f  jz      loc_180001681
0x180001545  movzx   edx, [rbp-50h+arg_20]
0x180001549  lea     rax, [rbp-50h+arg_B0]
0x18000154d  mov     [rsp+150h+var_38], 0
0x180001559  lea     r9, WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids
0x180001560  mov     [rsp+150h+var_40], r14
0x180001568  mov     r8d, 5
0x18000156e  mov     [rsp+150h+var_48], rax
0x180001576  mov     rcx, rsi
0x180001579  mov     [rsp+150h+var_50], r14
0x180001581  lea     rax, [rbp-50h+arg_A8]
0x180001585  mov     [rsp+150h+var_58], rax
0x18000158d  lea     rax, [rbp-50h+arg_A0]
0x180001591  mov     [rsp+150h+var_60], r14
0x180001599  mov     [rsp+150h+var_68], rax
0x1800015a1  lea     rax, [rbp-50h+arg_98]
0x1800015a5  mov     [rsp+150h+var_70], r14
0x1800015ad  mov     [rsp+150h+var_78], rax
0x1800015b5  lea     rax, [rbp-50h+arg_90]
0x1800015b9  mov     [rsp+150h+var_80], r14
0x1800015c1  mov     [rsp+150h+var_88], rax
0x1800015c9  lea     rax, [rbp-50h+arg_88]
0x1800015cd  mov     [rsp+150h+var_90], r14
0x1800015d5  mov     [rsp+150h+var_98], rax
0x1800015dd  lea     rax, [rbp-50h+arg_80]
0x1800015e1  mov     [rsp+150h+var_A0], r14
0x1800015e9  mov     [rsp+150h+var_A8], rax
0x1800015f1  lea     rax, [rbp-50h+arg_78]
0x1800015f5  mov     [rsp+150h+var_B0], r14
0x1800015fd  mov     [rsp+150h+var_B8], rax
0x180001605  lea     rax, [rbp-50h+arg_70]
0x180001609  mov     [rsp+150h+var_C0], r14
0x180001611  mov     [rsp+150h+var_C8], rax
0x180001619  lea     rax, [rbp-50h+arg_68]
0x18000161d  mov     [rsp+150h+var_D0], r14
0x180001625  mov     [rsp+150h+var_D8], rax
0x18000162a  lea     rax, [rbp-50h+arg_60]
0x18000162e  mov     [rsp+150h+var_E0], r14
0x180001633  mov     [rsp+150h+var_E8], rax
0x180001638  lea     rax, [rbp-50h+arg_58]
0x18000163c  mov     [rsp+150h+var_F0], r15
0x180001641  mov     [rsp+150h+var_F8], rax
0x180001646  lea     rax, [rbp-50h+arg_50]
0x18000164a  mov     [rsp+150h+var_100], r15
0x18000164f  mov     [rsp+150h+var_108], rax
0x180001654  lea     rax, [rbp-50h+arg_48]
0x180001658  mov     [rsp+150h+var_110], r15
0x18000165d  mov     [rsp+150h+var_118], rax
0x180001662  lea     rax, [rbp-50h+arg_40]
0x180001666  mov     [rsp+150h+var_120], r14
0x18000166b  mov     [rsp+150h+var_128], rax
0x180001670  mov     word ptr [rsp+150h+var_130], di
0x180001675  call    cs:__imp_WppAutoLogTrace
0x18000167c  nop     dword ptr [rax+rax+00h]
0x180001681  add     rsp, 128h
0x180001688  pop     r15
0x18000168a  pop     r14
0x18000168c  pop     rdi
0x18000168d  pop     rsi
0x18000168e  pop     rbx
0x18000168f  pop     rbp
0x180001690  retn
0x180001692  mov     rax, cs:pfnWppTraceMessage
0x180001699  lea     rdx, [rbp-50h+arg_B0]
0x18000169d  mov     [rsp+150h+var_40], 0
0x1800016a9  lea     r8, WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids
0x1800016b0  mov     [rsp+150h+var_48], r14
0x1800016b8  mov     r9d, edi
0x1800016bb  mov     [rsp+150h+var_50], rdx
0x1800016c3  lea     rdx, [rbp-50h+arg_A8]
0x1800016c7  mov     [rsp+150h+var_58], r14
0x1800016cf  mov     [rsp+150h+var_60], rdx
0x1800016d7  lea     rdx, [rbp-50h+arg_A0]
0x1800016db  mov     [rsp+150h+var_68], r14
0x1800016e3  mov     [rsp+150h+var_70], rdx
0x1800016eb  lea     rdx, [rbp-50h+arg_98]
0x1800016ef  mov     [rsp+150h+var_78], r14
0x1800016f7  mov     [rsp+150h+var_80], rdx
0x1800016ff  lea     rdx, [rbp-50h+arg_90]
0x180001703  mov     [rsp+150h+var_88], r14
0x18000170b  mov     [rsp+150h+var_90], rdx
0x180001713  lea     rdx, [rbp-50h+arg_88]
0x180001717  mov     [rsp+150h+var_98], r14
0x18000171f  mov     [rsp+150h+var_A0], rdx
0x180001727  lea     rdx, [rbp-50h+arg_80]
0x18000172b  mov     [rsp+150h+var_A8], r14
0x180001733  mov     [rsp+150h+var_B0], rdx
0x18000173b  lea     rdx, [rbp-50h+arg_78]
0x18000173f  mov     [rsp+150h+var_B8], r14
0x180001747  mov     [rsp+150h+var_C0], rdx
0x18000174f  lea     rdx, [rbp-50h+arg_70]
0x180001753  mov     [rsp+150h+var_C8], r14
0x18000175b  mov     [rsp+150h+var_D0], rdx
0x180001763  lea     rdx, [rbp-50h+arg_68]
0x180001767  mov     [rsp+150h+var_D8], r14
0x18000176c  mov     [rsp+150h+var_E0], rdx
0x180001771  lea     rdx, [rbp-50h+arg_60]
0x180001775  mov     [rsp+150h+var_E8], r14
0x18000177a  mov     [rsp+150h+var_F0], rdx
0x18000177f  lea     rdx, [rbp-50h+arg_58]
0x180001783  mov     [rsp+150h+var_F8], r15
0x180001788  mov     [rsp+150h+var_100], rdx
0x18000178d  lea     rdx, [rbp-50h+arg_50]
0x180001791  mov     [rsp+150h+var_108], r15
0x180001796  mov     [rsp+150h+var_110], rdx
0x18000179b  lea     rdx, [rbp-50h+arg_48]
0x18000179f  mov     [rsp+150h+var_118], r15
0x1800017a4  mov     [rsp+150h+var_120], rdx
0x1800017a9  lea     rdx, [rbp-50h+arg_40]
0x1800017ad  mov     [rsp+150h+var_128], r14
0x1800017b2  mov     [rsp+150h+var_130], rdx
0x1800017b7  mov     edx, 2Bh ; '+'
0x1800017bc  call    _guard_dispatch_icall
0x1800017c1  jmp     loc_18000153D
```
