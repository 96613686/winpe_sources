# McTemplateK0pxxxquu_EtwWriteTransfer

- ea: `0x140004190`
- end: `0x140004254`
- name: `McTemplateK0pxxxquu_EtwWriteTransfer`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400045c0`

## callees

- `0x140004300`
- `0x140010f20`

## pseudocode

```c
NTSTATUS McTemplateK0pxxxquu_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-69h] BYREF
  va_list v5; // [rsp+40h] [rbp-59h]
  __int64 v6; // [rsp+48h] [rbp-51h]
  va_list v7; // [rsp+50h] [rbp-49h]
  __int64 v8; // [rsp+58h] [rbp-41h]
  va_list v9; // [rsp+60h] [rbp-39h]
  __int64 v10; // [rsp+68h] [rbp-31h]
  va_list v11; // [rsp+70h] [rbp-29h]
  __int64 v12; // [rsp+78h] [rbp-21h]
  va_list v13; // [rsp+80h] [rbp-19h]
  __int64 v14; // [rsp+88h] [rbp-11h]
  va_list v15; // [rsp+90h] [rbp-9h]
  __int64 v16; // [rsp+98h] [rbp-1h]
  va_list v17; // [rsp+A0h] [rbp+7h]
  __int64 v18; // [rsp+A8h] [rbp+Fh]
  __int64 v19; // [rsp+E8h] [rbp+4Fh] BYREF
  va_list va; // [rsp+E8h] [rbp+4Fh]
  __int64 v21; // [rsp+F0h] [rbp+57h] BYREF
  va_list va1; // [rsp+F0h] [rbp+57h]
  __int64 v23; // [rsp+F8h] [rbp+5Fh] BYREF
  va_list va2; // [rsp+F8h] [rbp+5Fh]
  __int64 v25; // [rsp+100h] [rbp+67h] BYREF
  va_list va3; // [rsp+100h] [rbp+67h]
  __int64 v27; // [rsp+108h] [rbp+6Fh] BYREF
  va_list va4; // [rsp+108h] [rbp+6Fh]
  __int64 v29; // [rsp+110h] [rbp+77h] BYREF
  va_list va5; // [rsp+110h] [rbp+77h]
  va_list va6; // [rsp+118h] [rbp+7Fh] BYREF

  va_start(va6, a3);
  va_start(va5, a3);
  va_start(va4, a3);
  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v19 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v21 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v23 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v25 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v27 = va_arg(va5, _QWORD);
  va_copy(va6, va5);
  v29 = va_arg(va6, _QWORD);
  v6 = 8;
  va_copy(v5, va);
  v8 = 8;
  va_copy(v7, va1);
  v10 = 8;
  va_copy(v9, va2);
  v12 = 8;
  va_copy(v11, va3);
  va_copy(v13, va4);
  va_copy(v15, va5);
  va_copy(v17, va6);
  v14 = 4;
  v16 = 1;
  v18 = 1;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)IoPower, 0, 8u, &v4);
}

```

## disassembly

```asm
0x140004190  mov     [rsp-8+arg_18], r9
0x140004195  push    rbp
0x140004196  lea     rbp, [rsp-27h]
0x14000419b  sub     rsp, 0C0h
0x1400041a2  mov     rax, cs:__security_cookie
0x1400041a9  xor     rax, rsp
0x1400041ac  mov     [rbp+27h+var_10], rax
0x1400041b0  lea     rax, [rbp+27h+arg_18]
0x1400041b4  mov     [rbp+27h+var_78], 8
0x1400041bc  mov     [rbp+27h+var_80], rax
0x1400041c0  lea     rdx, IoPower
0x1400041c7  lea     rax, [rbp+27h+arg_20]
0x1400041cb  mov     [rbp+27h+var_68], 8
0x1400041d3  mov     [rbp+27h+var_70], rax
0x1400041d7  mov     r9d, 8
0x1400041dd  lea     rax, [rbp+27h+arg_28]
0x1400041e1  mov     [rbp+27h+var_58], 8
0x1400041e9  mov     [rbp+27h+var_60], rax
0x1400041ed  xor     r8d, r8d
0x1400041f0  lea     rax, [rbp+27h+arg_30]
0x1400041f4  mov     [rbp+27h+var_48], 8
0x1400041fc  mov     [rbp+27h+var_50], rax
0x140004200  lea     rax, [rbp+27h+arg_38]
0x140004204  mov     [rbp+27h+var_40], rax
0x140004208  lea     rax, [rbp+27h+arg_40]
0x14000420c  mov     [rbp+27h+var_30], rax
0x140004210  lea     rax, [rbp+27h+arg_48]
0x140004214  mov     [rbp+27h+var_20], rax
0x140004218  lea     rax, [rbp+27h+var_90]
0x14000421c  mov     [rsp+0C0h+var_A0], rax
0x140004221  mov     [rbp+27h+var_38], 4
0x140004229  mov     [rbp+27h+var_28], 1
0x140004231  mov     [rbp+27h+var_18], 1
0x140004239  call    McGenEventWrite_EtwWriteTransfer
0x14000423e  mov     rcx, [rbp+27h+var_10]
0x140004242  xor     rcx, rsp; StackCookie
0x140004245  call    __security_check_cookie
0x14000424a  add     rsp, 0C0h
0x140004251  pop     rbp
0x140004252  retn
```
