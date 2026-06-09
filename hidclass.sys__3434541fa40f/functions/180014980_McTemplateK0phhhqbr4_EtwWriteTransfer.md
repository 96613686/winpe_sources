# McTemplateK0phhhqbr4_EtwWriteTransfer

- ea: `0x180014980`
- end: `0x180014a3c`
- name: `McTemplateK0phhhqbr4_EtwWriteTransfer`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180023b44`

## callees

- `0x180014a88`
- `0x180027ba0`

## pseudocode

```c
NTSTATUS McTemplateK0phhhqbr4_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-51h] BYREF
  va_list v5; // [rsp+40h] [rbp-41h]
  __int64 v6; // [rsp+48h] [rbp-39h]
  va_list v7; // [rsp+50h] [rbp-31h]
  __int64 v8; // [rsp+58h] [rbp-29h]
  va_list v9; // [rsp+60h] [rbp-21h]
  __int64 v10; // [rsp+68h] [rbp-19h]
  va_list v11; // [rsp+70h] [rbp-11h]
  __int64 v12; // [rsp+78h] [rbp-9h]
  va_list v13; // [rsp+80h] [rbp-1h]
  __int64 v14; // [rsp+88h] [rbp+7h]
  __int64 v15; // [rsp+90h] [rbp+Fh]
  int v16; // [rsp+98h] [rbp+17h]
  int v17; // [rsp+9Ch] [rbp+1Bh]
  __int64 v18; // [rsp+D8h] [rbp+57h] BYREF
  va_list va; // [rsp+D8h] [rbp+57h]
  __int64 v20; // [rsp+E0h] [rbp+5Fh] BYREF
  va_list va1; // [rsp+E0h] [rbp+5Fh]
  __int64 v22; // [rsp+E8h] [rbp+67h] BYREF
  va_list va2; // [rsp+E8h] [rbp+67h]
  __int64 v24; // [rsp+F0h] [rbp+6Fh] BYREF
  va_list va3; // [rsp+F0h] [rbp+6Fh]
  __int64 v26; // [rsp+F8h] [rbp+77h] BYREF
  va_list va4; // [rsp+F8h] [rbp+77h]
  __int64 v28; // [rsp+100h] [rbp+7Fh]
  va_list va5; // [rsp+108h] [rbp+87h] BYREF

  va_start(va5, a3);
  va_start(va4, a3);
  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v18 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v20 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v22 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v24 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v26 = va_arg(va5, _QWORD);
  v28 = va_arg(va5, _QWORD);
  v6 = 8;
  v17 = 0;
  va_copy(v5, va);
  v8 = 2;
  va_copy(v7, va1);
  v10 = 2;
  va_copy(v9, va2);
  v12 = 2;
  va_copy(v11, va3);
  v14 = 4;
  va_copy(v13, va4);
  v15 = v28;
  v16 = v26;
  return McGenEventWrite_EtwWriteTransfer(
           &MS_HIDCLASS_ETW_PROVIDER_Context,
           (const EVENT_DESCRIPTOR *)HIDCLASS_ETW_EVENT_DEVICE_INFORMATION,
           0,
           7u,
           &v4);
}

```

## disassembly

```asm
0x180014980  mov     [rsp-8+arg_18], r9
0x180014985  push    rbp
0x180014986  lea     rbp, [rsp-2Fh]
0x18001498b  sub     rsp, 0B0h
0x180014992  mov     rax, cs:__security_cookie
0x180014999  xor     rax, rsp
0x18001499c  mov     [rbp+2Fh+var_10], rax
0x1800149a0  xor     edx, edx
0x1800149a2  mov     [rbp+2Fh+var_68], 8
0x1800149aa  lea     rax, [rbp+2Fh+arg_18]
0x1800149ae  mov     [rbp+2Fh+var_14], edx
0x1800149b1  mov     [rbp+2Fh+var_70], rax
0x1800149b5  lea     rcx, MS_HIDCLASS_ETW_PROVIDER_Context
0x1800149bc  lea     rax, [rbp+2Fh+arg_20]
0x1800149c0  mov     [rbp+2Fh+var_58], 2
0x1800149c8  mov     [rbp+2Fh+var_60], rax
0x1800149cc  lea     r9d, [rdx+7]
0x1800149d0  lea     rax, [rbp+2Fh+arg_28]
0x1800149d4  mov     [rbp+2Fh+var_48], 2
0x1800149dc  mov     [rbp+2Fh+var_50], rax
0x1800149e0  lea     rdx, HIDCLASS_ETW_EVENT_DEVICE_INFORMATION
0x1800149e7  lea     rax, [rbp+2Fh+arg_30]
0x1800149eb  mov     [rbp+2Fh+var_38], 2
0x1800149f3  mov     [rbp+2Fh+var_40], rax
0x1800149f7  xor     r8d, r8d
0x1800149fa  lea     rax, [rbp+2Fh+arg_38]
0x1800149fe  mov     [rbp+2Fh+var_28], 4
0x180014a06  mov     [rbp+2Fh+var_30], rax
0x180014a0a  mov     rax, [rbp+2Fh+arg_40]
0x180014a0e  mov     [rbp+2Fh+var_20], rax
0x180014a12  mov     eax, dword ptr [rbp+2Fh+arg_38]
0x180014a15  mov     [rbp+2Fh+var_18], eax
0x180014a18  lea     rax, [rbp+2Fh+var_80]
0x180014a1c  mov     [rsp+0B0h+var_90], rax
0x180014a21  call    McGenEventWrite_EtwWriteTransfer
0x180014a26  mov     rcx, [rbp+2Fh+var_10]
0x180014a2a  xor     rcx, rsp; StackCookie
0x180014a2d  call    __security_check_cookie
0x180014a32  add     rsp, 0B0h
0x180014a39  pop     rbp
0x180014a3a  retn
```
