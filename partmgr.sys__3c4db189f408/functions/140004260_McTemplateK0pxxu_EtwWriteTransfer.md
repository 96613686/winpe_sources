# McTemplateK0pxxu_EtwWriteTransfer

- ea: `0x140004260`
- end: `0x1400042f6`
- name: `McTemplateK0pxxu_EtwWriteTransfer`
- size: `150`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002550`
- `0x140002730`
- `0x1400029b0`

## callees

- `0x140004300`
- `0x140010f20`

## pseudocode

```c
NTSTATUS McTemplateK0pxxu_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-68h] BYREF
  va_list v5; // [rsp+40h] [rbp-58h]
  __int64 v6; // [rsp+48h] [rbp-50h]
  va_list v7; // [rsp+50h] [rbp-48h]
  __int64 v8; // [rsp+58h] [rbp-40h]
  va_list v9; // [rsp+60h] [rbp-38h]
  __int64 v10; // [rsp+68h] [rbp-30h]
  va_list v11; // [rsp+70h] [rbp-28h]
  __int64 v12; // [rsp+78h] [rbp-20h]
  __int64 v13; // [rsp+B8h] [rbp+20h] BYREF
  va_list va; // [rsp+B8h] [rbp+20h]
  __int64 v15; // [rsp+C0h] [rbp+28h] BYREF
  va_list va1; // [rsp+C0h] [rbp+28h]
  __int64 v17; // [rsp+C8h] [rbp+30h] BYREF
  va_list va2; // [rsp+C8h] [rbp+30h]
  va_list va3; // [rsp+D0h] [rbp+38h] BYREF

  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v13 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v15 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v17 = va_arg(va3, _QWORD);
  v6 = 8;
  va_copy(v5, va);
  v8 = 8;
  va_copy(v7, va1);
  v10 = 8;
  va_copy(v9, va2);
  v12 = 1;
  va_copy(v11, va3);
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)IdlePower, 0, 5u, &v4);
}

```

## disassembly

```asm
0x140004260  mov     r11, rsp
0x140004263  mov     [r11+20h], r9
0x140004267  sub     rsp, 98h
0x14000426e  mov     rax, cs:__security_cookie
0x140004275  xor     rax, rsp
0x140004278  mov     [rsp+98h+var_18], rax
0x140004280  lea     rax, [r11+20h]
0x140004284  mov     qword ptr [r11-50h], 8
0x14000428c  mov     [r11-58h], rax
0x140004290  lea     rdx, IdlePower
0x140004297  lea     rax, [r11+28h]
0x14000429b  mov     qword ptr [r11-40h], 8
0x1400042a3  mov     [r11-48h], rax
0x1400042a7  mov     r9d, 5
0x1400042ad  lea     rax, [r11+30h]
0x1400042b1  mov     qword ptr [r11-30h], 8
0x1400042b9  mov     [r11-38h], rax
0x1400042bd  xor     r8d, r8d
0x1400042c0  lea     rax, [r11+38h]
0x1400042c4  mov     qword ptr [r11-20h], 1
0x1400042cc  mov     [r11-28h], rax
0x1400042d0  lea     rax, [r11-68h]
0x1400042d4  mov     [r11-78h], rax
0x1400042d8  call    McGenEventWrite_EtwWriteTransfer
0x1400042dd  mov     rcx, [rsp+98h+var_18]
0x1400042e5  xor     rcx, rsp; StackCookie
0x1400042e8  call    __security_check_cookie
0x1400042ed  add     rsp, 98h
0x1400042f4  retn
```
