# McTemplateU0s4pu_EventWriteTransfer

- ea: `0x18000fcc8`
- end: `0x18000fd37`
- name: `McTemplateU0s4pu_EventWriteTransfer`
- size: `111`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bf78`
- `0x18000dcd0`

## callees

- `0x18000d214`
- `0x18000e3a0`

## pseudocode

```c
ULONG McTemplateU0s4pu_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-50h] BYREF
  __int64 v5; // [rsp+40h] [rbp-40h]
  __int64 v6; // [rsp+48h] [rbp-38h]
  va_list v7; // [rsp+50h] [rbp-30h]
  __int64 v8; // [rsp+58h] [rbp-28h]
  va_list v9; // [rsp+60h] [rbp-20h]
  __int64 v10; // [rsp+68h] [rbp-18h]
  __int64 v11; // [rsp+A8h] [rbp+28h] BYREF
  va_list va; // [rsp+A8h] [rbp+28h]
  va_list va1; // [rsp+B0h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v11 = va_arg(va1, _QWORD);
  v5 = a3;
  va_copy(v7, va);
  v6 = 4;
  va_copy(v9, va1);
  v8 = 8;
  v10 = 1;
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 4u, &v4);
}

```

## disassembly

```asm
0x18000fcc8  mov     [rsp-8+arg_18], r9
0x18000fccd  push    rbp
0x18000fcce  mov     rbp, rsp
0x18000fcd1  sub     rsp, 80h
0x18000fcd8  mov     rax, cs:__security_cookie
0x18000fcdf  xor     rax, rsp
0x18000fce2  mov     [rbp+var_10], rax
0x18000fce6  lea     rax, [rbp+arg_18]
0x18000fcea  mov     [rbp+var_40], r8
0x18000fcee  mov     [rbp+var_30], rax
0x18000fcf2  mov     r9d, 4
0x18000fcf8  lea     rax, [rbp+arg_20]
0x18000fcfc  mov     [rbp+var_38], r9
0x18000fd00  mov     [rbp+var_20], rax
0x18000fd04  lea     rax, [rbp+var_50]
0x18000fd08  mov     [rsp+80h+var_60], rax
0x18000fd0d  mov     [rbp+var_28], 8
0x18000fd15  mov     [rbp+var_18], 1
0x18000fd1d  call    McGenEventWrite_EventWriteTransfer
0x18000fd22  mov     rcx, [rbp+var_10]
0x18000fd26  xor     rcx, rsp; StackCookie
0x18000fd29  call    __security_check_cookie
0x18000fd2e  add     rsp, 80h
0x18000fd35  pop     rbp
0x18000fd36  retn
```
