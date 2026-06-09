# McTemplateU0ppubr2ubr4_EtwWriteTransfer

- ea: `0x14003fcc4`
- end: `0x14003fd7b`
- name: `McTemplateU0ppubr2ubr4_EtwWriteTransfer`
- size: `183`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002840`
- `0x140002e8c`
- `0x140040908`

## callees

- `0x14003c8e0`
- `0x14003e8c4`

## pseudocode

```c
NTSTATUS McTemplateU0ppubr2ubr4_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        ...)
{
  char v7; // [rsp+30h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-49h] BYREF
  __int64 *v9; // [rsp+50h] [rbp-39h]
  __int64 v10; // [rsp+58h] [rbp-31h]
  __int64 *v11; // [rsp+60h] [rbp-29h]
  __int64 v12; // [rsp+68h] [rbp-21h]
  char *v13; // [rsp+70h] [rbp-19h]
  __int64 v14; // [rsp+78h] [rbp-11h]
  __int64 v15; // [rsp+80h] [rbp-9h]
  __int64 v16; // [rsp+88h] [rbp-1h]
  va_list v17; // [rsp+90h] [rbp+7h]
  __int64 v18; // [rsp+98h] [rbp+Fh]
  __int64 v19; // [rsp+A0h] [rbp+17h]
  int v20; // [rsp+A8h] [rbp+1Fh]
  int v21; // [rsp+ACh] [rbp+23h]
  __int64 v22; // [rsp+E0h] [rbp+57h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+5Fh] BYREF
  __int64 v24; // [rsp+100h] [rbp+77h] BYREF
  va_list va; // [rsp+100h] [rbp+77h]
  __int64 v26; // [rsp+108h] [rbp+7Fh]
  va_list va1; // [rsp+110h] [rbp+87h] BYREF

  va_start(va1, a6);
  va_start(va, a6);
  v24 = va_arg(va1, _QWORD);
  v26 = va_arg(va1, _QWORD);
  v23 = a4;
  v22 = a3;
  v7 = 28;
  v10 = 8;
  v9 = &v22;
  v11 = &v23;
  v13 = &v7;
  v15 = a6;
  va_copy(v17, va);
  v19 = v26;
  v20 = (unsigned __int8)v24;
  v12 = 8;
  v14 = 1;
  v16 = 28;
  v18 = 1;
  v21 = 0;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, 0, 7u, &v8);
}

```

## disassembly

```asm
0x14003fcc4  mov     [rsp-8+arg_18], r9
0x14003fcc9  mov     [rsp-8+arg_10], r8
0x14003fcce  push    rbp
0x14003fccf  lea     rbp, [rsp-37h]
0x14003fcd4  sub     rsp, 0C0h
0x14003fcdb  mov     rax, cs:__security_cookie
0x14003fce2  xor     rax, rsp
0x14003fce5  mov     [rbp+37h+var_10], rax
0x14003fce9  xor     r8d, r8d
0x14003fcec  mov     [rbp+37h+var_90], 1Ch
0x14003fcf0  lea     rax, [rbp+37h+arg_10]
0x14003fcf4  mov     [rbp+37h+var_68], 8
0x14003fcfc  mov     [rbp+37h+var_70], rax
0x14003fd00  lea     rax, [rbp+37h+arg_18]
0x14003fd04  mov     [rbp+37h+var_60], rax
0x14003fd08  lea     rax, [rbp+37h+var_90]
0x14003fd0c  mov     [rbp+37h+var_50], rax
0x14003fd10  lea     r9d, [r8+7]
0x14003fd14  mov     rax, [rbp+37h+arg_28]
0x14003fd18  mov     [rbp+37h+var_40], rax
0x14003fd1c  lea     rax, [rbp+37h+arg_30]
0x14003fd20  mov     [rbp+37h+var_30], rax
0x14003fd24  mov     rax, [rbp+37h+arg_38]
0x14003fd28  mov     [rbp+37h+var_20], rax
0x14003fd2c  movzx   eax, byte ptr [rbp+37h+arg_30]
0x14003fd30  mov     [rbp+37h+var_18], eax
0x14003fd33  lea     rax, [rbp+37h+var_80]
0x14003fd37  mov     [rsp+0C0h+var_A0], rax
0x14003fd3c  mov     [rbp+37h+var_58], 8
0x14003fd44  mov     [rbp+37h+var_48], 1
0x14003fd4c  mov     [rbp+37h+var_38], 1Ch
0x14003fd54  mov     [rbp+37h+var_28], 1
0x14003fd5c  mov     [rbp+37h+var_14], r8d
0x14003fd60  call    McGenEventWrite_EtwWriteTransfer
0x14003fd65  mov     rcx, [rbp+37h+var_10]
0x14003fd69  xor     rcx, rsp; StackCookie
0x14003fd6c  call    __security_check_cookie
0x14003fd71  add     rsp, 0C0h
0x14003fd78  pop     rbp
0x14003fd79  retn
```
