# McTemplateU0tpq_EtwEventWriteTransfer

- ea: `0x180013774`
- end: `0x1800137ef`
- name: `McTemplateU0tpq_EtwEventWriteTransfer`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009340`

## callees

- `0x180004594`
- `0x18000d0a0`

## pseudocode

```c
__int64 McTemplateU0tpq_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, ...)
{
  _BYTE v4[16]; // [rsp+30h] [rbp-50h] BYREF
  int *v5; // [rsp+40h] [rbp-40h]
  __int64 v6; // [rsp+48h] [rbp-38h]
  va_list v7; // [rsp+50h] [rbp-30h]
  __int64 v8; // [rsp+58h] [rbp-28h]
  va_list v9; // [rsp+60h] [rbp-20h]
  __int64 v10; // [rsp+68h] [rbp-18h]
  int v11; // [rsp+A0h] [rbp+20h] BYREF
  __int64 v12; // [rsp+A8h] [rbp+28h] BYREF
  va_list va; // [rsp+A8h] [rbp+28h]
  va_list va1; // [rsp+B0h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v12 = va_arg(va1, _QWORD);
  v11 = a3;
  v8 = 8;
  v6 = 4;
  v5 = &v11;
  v10 = 4;
  va_copy(v7, va);
  va_copy(v9, va1);
  return McGenEventWrite_EtwEventWriteTransfer(Microsoft_Windows_Dwm_Api_Provider_Context, a2, a3, 4, (__int64)v4);
}

```

## disassembly

```asm
0x180013774  mov     [rsp-8+arg_18], r9
0x180013779  mov     [rsp-8+arg_10], r8d
0x18001377e  push    rbp
0x18001377f  mov     rbp, rsp
0x180013782  sub     rsp, 80h
0x180013789  mov     rax, cs:__security_cookie
0x180013790  xor     rax, rsp
0x180013793  mov     [rbp+var_10], rax
0x180013797  mov     r9d, 4
0x18001379d  mov     [rbp+var_28], 8
0x1800137a5  lea     rax, [rbp+arg_10]
0x1800137a9  mov     [rbp+var_38], r9
0x1800137ad  mov     [rbp+var_40], rax
0x1800137b1  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x1800137b8  lea     rax, [rbp+arg_18]
0x1800137bc  mov     [rbp+var_18], r9
0x1800137c0  mov     [rbp+var_30], rax
0x1800137c4  lea     rax, [rbp+arg_20]
0x1800137c8  mov     [rbp+var_20], rax
0x1800137cc  lea     rax, [rbp+var_50]
0x1800137d0  mov     [rsp+80h+var_60], rax
0x1800137d5  call    McGenEventWrite_EtwEventWriteTransfer
0x1800137da  mov     rcx, [rbp+var_10]
0x1800137de  xor     rcx, rsp; StackCookie
0x1800137e1  call    __security_check_cookie
0x1800137e6  add     rsp, 80h
0x1800137ed  pop     rbp
0x1800137ee  retn
```
