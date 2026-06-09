# McTemplateK0qqq_EtwWriteTransfer

- ea: `0x14000e694`
- end: `0x14000e700`
- name: `McTemplateK0qqq_EtwWriteTransfer`
- size: `108`
- prototype: `__int64(_DWORD, _DWORD, _DWORD, _DWORD, char, ...)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x1400017a0`
- `0x140002614`
- `0x140007820`
- `0x14000d660`
- `0x14000fee0`
- `0x140029ff0`
- `0x140035df8`
- `0x140036d40`
- `0x14003c81c`
- `0x14003ceb8`
- `0x140050ae0`
- `0x1400519f0`
- `0x1400522a0`

## callees

- `0x14000e638`
- `0x140016560`

## pseudocode

```c
NTSTATUS McTemplateK0qqq_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const GUID *a3, int a4, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-50h] BYREF
  int *v6; // [rsp+40h] [rbp-40h]
  __int64 v7; // [rsp+48h] [rbp-38h]
  va_list v8; // [rsp+50h] [rbp-30h]
  __int64 v9; // [rsp+58h] [rbp-28h]
  va_list v10; // [rsp+60h] [rbp-20h]
  __int64 v11; // [rsp+68h] [rbp-18h]
  int v12; // [rsp+A8h] [rbp+28h] BYREF
  __int64 v13; // [rsp+B0h] [rbp+30h] BYREF
  va_list va; // [rsp+B0h] [rbp+30h]
  va_list va1; // [rsp+B8h] [rbp+38h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v13 = va_arg(va1, _QWORD);
  v12 = a4;
  v6 = &v12;
  va_copy(v8, va);
  va_copy(v10, va1);
  v7 = 4;
  v9 = 4;
  v11 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 4u, &v5);
}

```

## disassembly

```asm
0x14000e694  mov     [rsp-8+arg_18], r9d
0x14000e699  push    rbp
0x14000e69a  mov     rbp, rsp
0x14000e69d  sub     rsp, 80h
0x14000e6a4  mov     rax, cs:__security_cookie
0x14000e6ab  xor     rax, rsp
0x14000e6ae  mov     [rbp+var_10], rax
0x14000e6b2  mov     r9d, 4
0x14000e6b8  lea     rax, [rbp+arg_18]
0x14000e6bc  mov     [rbp+var_40], rax
0x14000e6c0  lea     rax, [rbp+arg_20]
0x14000e6c4  mov     [rbp+var_30], rax
0x14000e6c8  lea     rax, [rbp+arg_28]
0x14000e6cc  mov     [rbp+var_20], rax
0x14000e6d0  lea     rax, [rbp+var_50]
0x14000e6d4  mov     [rsp+80h+var_60], rax
0x14000e6d9  mov     [rbp+var_38], r9
0x14000e6dd  mov     [rbp+var_28], r9
0x14000e6e1  mov     [rbp+var_18], r9
0x14000e6e5  call    McGenEventWrite_EtwWriteTransfer
0x14000e6ea  mov     rcx, [rbp+var_10]
0x14000e6ee  xor     rcx, rsp; StackCookie
0x14000e6f1  call    __security_check_cookie
0x14000e6f6  add     rsp, 80h
0x14000e6fd  pop     rbp
0x14000e6fe  retn
```
