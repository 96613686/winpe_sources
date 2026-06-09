# McTemplateU0s4pu_EventWriteTransfer

- ea: `0x18000eb80`
- end: `0x18000ebef`
- name: `McTemplateU0s4pu_EventWriteTransfer`
- size: `111`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ae0`
- `0x1800084e4`

## callees

- `0x18000ab30`
- `0x18000eb28`

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
0x18000eb80  mov     [rsp-8+arg_18], r9
0x18000eb85  push    rbp
0x18000eb86  mov     rbp, rsp
0x18000eb89  sub     rsp, 80h
0x18000eb90  mov     rax, cs:__security_cookie
0x18000eb97  xor     rax, rsp
0x18000eb9a  mov     [rbp+var_10], rax
0x18000eb9e  lea     rax, [rbp+arg_18]
0x18000eba2  mov     [rbp+var_40], r8
0x18000eba6  mov     [rbp+var_30], rax
0x18000ebaa  mov     r9d, 4
0x18000ebb0  lea     rax, [rbp+arg_20]
0x18000ebb4  mov     [rbp+var_38], r9
0x18000ebb8  mov     [rbp+var_20], rax
0x18000ebbc  lea     rax, [rbp+var_50]
0x18000ebc0  mov     [rsp+80h+var_60], rax
0x18000ebc5  mov     [rbp+var_28], 8
0x18000ebcd  mov     [rbp+var_18], 1
0x18000ebd5  call    McGenEventWrite_EventWriteTransfer
0x18000ebda  mov     rcx, [rbp+var_10]
0x18000ebde  xor     rcx, rsp; StackCookie
0x18000ebe1  call    __security_check_cookie
0x18000ebe6  add     rsp, 80h
0x18000ebed  pop     rbp
0x18000ebee  retn
```
