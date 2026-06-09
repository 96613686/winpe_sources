# WPP_RECORDER_AND_TRACE_SF_qLDDqldLLiIIIIIIi

- ea: `0x18001667c`
- end: `0x180016956`
- name: `WPP_RECORDER_AND_TRACE_SF_qLDDqldLLiIIIIIIi`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800164d8`

## callees

- `0x18001667c`
- `0x180027c80`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x180016939`
- `WppRecorder!WppAutoLogTrace` at `0x180016939`

## pseudocode

```c

```

## disassembly

```asm
0x18001667c  mov     r11, rsp
0x18001667f  push    rbp
0x180016680  push    rbx
0x180016681  push    rsi
0x180016682  push    rdi
0x180016683  push    r14
0x180016685  push    r15
0x180016687  lea     rbp, [r11+48h]
0x18001668b  sub     rsp, 148h
0x180016692  mov     esi, 8
0x180016697  mov     rdi, r9
0x18001669a  mov     bl, r8b
0x18001669d  lea     r15d, [rsi+55h]
0x1800166a1  lea     r14d, [rsi-4]
0x1800166a5  test    dl, dl
0x1800166a7  jz      loc_1800167D6
0x1800166ad  mov     qword ptr [r11-48h], 0
0x1800166b5  lea     rdx, [rbp-50h+arg_C0]
0x1800166bc  mov     [r11-50h], rsi
0x1800166c0  lea     r8, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x1800166c7  mov     [r11-58h], rdx
0x1800166cb  mov     r9d, r15d
0x1800166ce  mov     [r11-60h], rsi
0x1800166d2  lea     rdx, [rbp-50h+arg_B8]
0x1800166d6  mov     [r11-68h], rdx
0x1800166da  lea     rdx, [rbp-50h+arg_B0]
0x1800166de  mov     rax, cs:pfnWppTraceMessage
0x1800166e5  mov     [r11-70h], rsi
0x1800166e9  mov     [r11-78h], rdx
0x1800166ed  lea     rdx, [rbp-50h+arg_A8]
0x1800166f1  mov     [r11-80h], rsi
0x1800166f5  mov     [r11-88h], rdx
0x1800166fc  lea     rdx, [rbp-50h+arg_A0]
0x180016700  mov     [r11-90h], rsi
0x180016707  mov     [r11-98h], rdx
0x18001670e  lea     rdx, [rbp-50h+arg_98]
0x180016712  mov     [r11-0A0h], rsi
0x180016719  mov     [r11-0A8h], rdx
0x180016720  lea     rdx, [rbp-50h+arg_90]
0x180016724  mov     [r11-0B0h], rsi
0x18001672b  mov     [r11-0B8h], rdx
0x180016732  lea     rdx, [rbp-50h+arg_88]
0x180016736  mov     [r11-0C0h], rsi
0x18001673d  mov     [r11-0C8h], rdx
0x180016744  lea     rdx, [rbp-50h+arg_80]
0x180016748  mov     [r11-0D0h], r14
0x18001674f  mov     [r11-0D8h], rdx
0x180016756  lea     rdx, [rbp-50h+arg_78]
0x18001675a  mov     [r11-0E0h], r14
0x180016761  mov     [r11-0E8h], rdx
0x180016768  lea     rdx, [rbp-50h+arg_70]
0x18001676c  mov     [r11-0F0h], r14
0x180016773  mov     [r11-0F8h], rdx
0x18001677a  lea     rdx, [rbp-50h+arg_68]
0x18001677e  mov     [rsp+170h+var_F8], r14
0x180016783  mov     [rsp+170h+var_100], rdx
0x180016788  lea     rdx, [rbp-50h+arg_60]
0x18001678c  mov     [rsp+170h+var_108], rsi
0x180016791  mov     [rsp+170h+var_110], rdx
0x180016796  lea     rdx, [rbp-50h+arg_58]
0x18001679a  mov     [rsp+170h+var_118], r14
0x18001679f  mov     [rsp+170h+var_120], rdx
0x1800167a4  lea     rdx, [rbp-50h+arg_50]
0x1800167a8  mov     [rsp+170h+var_128], r14
0x1800167ad  mov     [rsp+170h+var_130], rdx
0x1800167b2  lea     rdx, [rbp-50h+arg_48]
0x1800167b6  mov     [rsp+170h+var_138], r14
0x1800167bb  mov     [rsp+170h+var_140], rdx
0x1800167c0  lea     rdx, [rbp-50h+arg_40]
0x1800167c4  mov     [rsp+170h+var_148], rsi
0x1800167c9  mov     [rsp+170h+var_150], rdx
0x1800167ce  lea     edx, [rsi+23h]
0x1800167d1  call    _guard_dispatch_icall
0x1800167d6  test    bl, bl
0x1800167d8  jz      loc_180016945
0x1800167de  mov     qword ptr [rsp+138h], 0
0x1800167ea  lea     rax, [rbp-50h+arg_C0]
0x1800167f1  mov     [rsp+170h+var_40], rsi
0x1800167f9  lea     r9, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x180016800  mov     [rsp+170h+var_48], rax
0x180016808  mov     r8d, 2
0x18001680e  mov     [rsp+170h+var_50], rsi
0x180016816  lea     rax, [rbp-50h+arg_B8]
0x18001681a  mov     [rsp+170h+var_58], rax
0x180016822  mov     edx, r14d
0x180016825  mov     [rsp+170h+var_60], rsi
0x18001682d  lea     rax, [rbp-50h+arg_B0]
0x180016831  mov     [rsp+170h+var_68], rax
0x180016839  mov     rcx, rdi
0x18001683c  mov     [rsp+170h+var_70], rsi
0x180016844  lea     rax, [rbp-50h+arg_A8]
0x180016848  mov     [rsp+170h+var_78], rax
0x180016850  lea     rax, [rbp-50h+arg_A0]
0x180016854  mov     [rsp+170h+var_80], rsi
0x18001685c  mov     [rsp+170h+var_88], rax
0x180016864  lea     rax, [rbp-50h+arg_98]
0x180016868  mov     [rsp+170h+var_90], rsi
0x180016870  mov     [rsp+170h+var_98], rax
0x180016878  lea     rax, [rbp-50h+arg_90]
0x18001687c  mov     [rsp+170h+var_A0], rsi
0x180016884  mov     [rsp+170h+var_A8], rax
0x18001688c  lea     rax, [rbp-50h+arg_88]
0x180016890  mov     [rsp+170h+var_B0], rsi
0x180016898  mov     [rsp+170h+var_B8], rax
0x1800168a0  lea     rax, [rbp-50h+arg_80]
0x1800168a4  mov     [rsp+170h+var_C0], r14
0x1800168ac  mov     [rsp+170h+var_C8], rax
0x1800168b4  lea     rax, [rbp-50h+arg_78]
0x1800168b8  mov     [rsp+170h+var_D0], r14
0x1800168c0  mov     [rsp+170h+var_D8], rax
0x1800168c8  lea     rax, [rbp-50h+arg_70]
0x1800168cc  mov     [rsp+170h+var_E0], r14
0x1800168d4  mov     [rsp+170h+var_E8], rax
0x1800168dc  lea     rax, [rbp-50h+arg_68]
0x1800168e0  mov     [rsp+170h+var_F0], r14
0x1800168e8  mov     [rsp+170h+var_F8], rax
0x1800168ed  lea     rax, [rbp-50h+arg_60]
0x1800168f1  mov     [rsp+170h+var_100], rsi
0x1800168f6  mov     [rsp+170h+var_108], rax
0x1800168fb  lea     rax, [rbp-50h+arg_58]
0x1800168ff  mov     [rsp+170h+var_110], r14
0x180016904  mov     [rsp+170h+var_118], rax
0x180016909  lea     rax, [rbp-50h+arg_50]
0x18001690d  mov     [rsp+170h+var_120], r14
0x180016912  mov     [rsp+170h+var_128], rax
0x180016917  lea     rax, [rbp-50h+arg_48]
0x18001691b  mov     [rsp+170h+var_130], r14
0x180016920  mov     [rsp+170h+var_138], rax
0x180016925  lea     rax, [rbp-50h+arg_40]
0x180016929  mov     [rsp+170h+var_140], rsi
0x18001692e  mov     [rsp+170h+var_148], rax
0x180016933  mov     word ptr [rsp+170h+var_150], r15w
0x180016939  call    cs:__imp_WppAutoLogTrace
0x180016940  nop     dword ptr [rax+rax+00h]
0x180016945  add     rsp, 148h
0x18001694c  pop     r15
0x18001694e  pop     r14
0x180016950  pop     rdi
0x180016951  pop     rsi
0x180016952  pop     rbx
0x180016953  pop     rbp
0x180016954  retn
```
