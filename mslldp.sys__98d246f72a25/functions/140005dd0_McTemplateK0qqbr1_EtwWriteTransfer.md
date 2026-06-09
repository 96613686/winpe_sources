# McTemplateK0qqbr1_EtwWriteTransfer

- ea: `0x140005dd0`
- end: `0x140005e43`
- name: `McTemplateK0qqbr1_EtwWriteTransfer`
- size: `115`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1400022c0`
- `0x1400026c0`
- `0x140002fe0`
- `0x1400049a0`
- `0x140005fe4`

## callees

- `0x1400048f8`
- `0x140006630`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qqbr1_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-50h] BYREF
  int *v8; // [rsp+40h] [rbp-40h]
  __int64 v9; // [rsp+48h] [rbp-38h]
  int *v10; // [rsp+50h] [rbp-30h]
  __int64 v11; // [rsp+58h] [rbp-28h]
  __int64 v12; // [rsp+60h] [rbp-20h]
  int v13; // [rsp+68h] [rbp-18h]
  int v14; // [rsp+6Ch] [rbp-14h]
  int v15; // [rsp+A8h] [rbp+28h] BYREF

  v15 = a4;
  v8 = &v15;
  v9 = 4;
  v10 = &a5;
  v12 = a6;
  v13 = a5;
  v11 = 4;
  v14 = 0;
  return McGenEventWrite_EtwWriteTransfer(0, a2, a3, 4u, &v7);
}

```

## disassembly

```asm
0x140005dd0  mov     [rsp-8+arg_18], r9d
0x140005dd5  push    rbp
0x140005dd6  mov     rbp, rsp
0x140005dd9  sub     rsp, 80h
0x140005de0  mov     rax, cs:__security_cookie
0x140005de7  xor     rax, rsp
0x140005dea  mov     [rbp+var_10], rax
0x140005dee  mov     r9d, 4
0x140005df4  lea     rax, [rbp+arg_18]
0x140005df8  mov     [rbp+var_40], rax
0x140005dfc  xor     ecx, ecx
0x140005dfe  lea     rax, [rbp+arg_20]
0x140005e02  mov     [rbp+var_38], r9
0x140005e06  mov     [rbp+var_30], rax
0x140005e0a  mov     rax, [rbp+arg_28]
0x140005e0e  mov     [rbp+var_20], rax
0x140005e12  mov     eax, [rbp+arg_20]
0x140005e15  mov     [rbp+var_18], eax
0x140005e18  lea     rax, [rbp+var_50]
0x140005e1c  mov     [rsp+80h+var_60], rax
0x140005e21  mov     [rbp+var_28], r9
0x140005e25  mov     [rbp+var_14], ecx
0x140005e28  call    McGenEventWrite_EtwWriteTransfer
0x140005e2d  mov     rcx, [rbp+var_10]
0x140005e31  xor     rcx, rsp; StackCookie
0x140005e34  call    __security_check_cookie
0x140005e39  add     rsp, 80h
0x140005e40  pop     rbp
0x140005e41  retn
```
