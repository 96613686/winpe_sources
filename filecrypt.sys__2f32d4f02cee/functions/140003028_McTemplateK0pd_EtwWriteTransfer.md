# McTemplateK0pd_EtwWriteTransfer

- ea: `0x140003028`
- end: `0x14000308f`
- name: `McTemplateK0pd_EtwWriteTransfer`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400022a0`
- `0x140002a00`

## callees

- `0x140002f6c`
- `0x140003540`

## pseudocode

```c
NTSTATUS McTemplateK0pd_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-48h] BYREF
  va_list v5; // [rsp+40h] [rbp-38h]
  __int64 v6; // [rsp+48h] [rbp-30h]
  va_list v7; // [rsp+50h] [rbp-28h]
  __int64 v8; // [rsp+58h] [rbp-20h]
  __int64 v9; // [rsp+98h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+20h]
  va_list va1; // [rsp+A0h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v9 = va_arg(va1, _QWORD);
  v6 = 8;
  va_copy(v5, va);
  v8 = 4;
  va_copy(v7, va1);
  return McGenEventWrite_EtwWriteTransfer(a1, &InvalidBufferFailure, a3, 3u, &v4);
}

```

## disassembly

```asm
0x140003028  mov     r11, rsp
0x14000302b  mov     [r11+20h], r9
0x14000302f  sub     rsp, 78h
0x140003033  mov     rax, cs:__security_cookie
0x14000303a  xor     rax, rsp
0x14000303d  mov     [rsp+78h+var_18], rax
0x140003042  lea     rax, [r11+20h]
0x140003046  mov     qword ptr [r11-30h], 8
0x14000304e  mov     [r11-38h], rax
0x140003052  lea     rdx, InvalidBufferFailure
0x140003059  lea     rax, [r11+28h]
0x14000305d  mov     qword ptr [r11-20h], 4
0x140003065  mov     [r11-28h], rax
0x140003069  mov     r9d, 3
0x14000306f  lea     rax, [r11-48h]
0x140003073  mov     [r11-58h], rax
0x140003077  call    McGenEventWrite_EtwWriteTransfer
0x14000307c  mov     rcx, [rsp+78h+var_18]
0x140003081  xor     rcx, rsp; StackCookie
0x140003084  call    __security_check_cookie
0x140003089  add     rsp, 78h
0x14000308d  retn
```
