# McTemplateK0xxx_EtwWriteTransfer

- ea: `0x140003734`
- end: `0x1400037b6`
- name: `McTemplateK0xxx_EtwWriteTransfer`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400045c0`

## callees

- `0x140004300`
- `0x140010f20`

## pseudocode

```c
NTSTATUS McTemplateK0xxx_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-50h] BYREF
  va_list v5; // [rsp+40h] [rbp-40h]
  __int64 v6; // [rsp+48h] [rbp-38h]
  va_list v7; // [rsp+50h] [rbp-30h]
  __int64 v8; // [rsp+58h] [rbp-28h]
  va_list v9; // [rsp+60h] [rbp-20h]
  __int64 v10; // [rsp+68h] [rbp-18h]
  __int64 v11; // [rsp+A8h] [rbp+28h] BYREF
  va_list va; // [rsp+A8h] [rbp+28h]
  __int64 v13; // [rsp+B0h] [rbp+30h] BYREF
  va_list va1; // [rsp+B0h] [rbp+30h]
  va_list va2; // [rsp+B8h] [rbp+38h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v11 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v13 = va_arg(va2, _QWORD);
  v6 = 8;
  va_copy(v5, va);
  v8 = 8;
  va_copy(v7, va1);
  v10 = 8;
  va_copy(v9, va2);
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)RaceCompletion, 0, 4u, &v4);
}

```

## disassembly

```asm
0x140003734  mov     [rsp-8+arg_18], r9
0x140003739  push    rbp
0x14000373a  mov     rbp, rsp
0x14000373d  sub     rsp, 80h
0x140003744  mov     rax, cs:__security_cookie
0x14000374b  xor     rax, rsp
0x14000374e  mov     [rbp+var_10], rax
0x140003752  lea     rax, [rbp+arg_18]
0x140003756  mov     [rbp+var_38], 8
0x14000375e  mov     [rbp+var_40], rax
0x140003762  lea     rdx, RaceCompletion
0x140003769  lea     rax, [rbp+arg_20]
0x14000376d  mov     [rbp+var_28], 8
0x140003775  mov     [rbp+var_30], rax
0x140003779  mov     r9d, 4
0x14000377f  lea     rax, [rbp+arg_28]
0x140003783  mov     [rbp+var_18], 8
0x14000378b  mov     [rbp+var_20], rax
0x14000378f  xor     r8d, r8d
0x140003792  lea     rax, [rbp+var_50]
0x140003796  mov     [rsp+80h+var_60], rax
0x14000379b  call    McGenEventWrite_EtwWriteTransfer
0x1400037a0  mov     rcx, [rbp+var_10]
0x1400037a4  xor     rcx, rsp; StackCookie
0x1400037a7  call    __security_check_cookie
0x1400037ac  add     rsp, 80h
0x1400037b3  pop     rbp
0x1400037b4  retn
```
