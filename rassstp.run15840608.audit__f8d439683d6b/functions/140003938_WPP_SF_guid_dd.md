# WPP_SF__guid_dd

- ea: `0x140003938`
- end: `0x140003997`
- name: `WPP_SF__guid_dd`
- size: `95`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140010fd4`
- `0x140013ad0`
- `0x140019040`

## callees

- `0x140005ef0`

## pseudocode

```c
__int64 WPP_SF__guid_dd(__int64 a1, unsigned __int16 a2, __int64 a3, __int64 a4, ...)
{
  __int64 v5; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v5 = va_arg(va1, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           a4,
           16,
           (__int64 *)va,
           4,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x140003938  sub     rsp, 68h
0x14000393c  mov     rax, cs:pfnWppTraceMessage
0x140003943  lea     r10, [rsp+68h+arg_28]
0x14000394b  mov     [rsp+68h+var_18], 0
0x140003954  mov     r11d, 4
0x14000395a  mov     [rsp+68h+var_20], r11
0x14000395f  mov     [rsp+68h+var_28], r10
0x140003964  lea     r10, [rsp+68h+arg_20]
0x14000396c  mov     [rsp+68h+var_30], r11
0x140003971  mov     [rsp+68h+var_38], r10
0x140003976  mov     [rsp+68h+var_40], 10h
0x14000397f  mov     [rsp+68h+var_48], r9
0x140003984  movzx   r9d, dx
0x140003988  lea     edx, [r11+27h]
0x14000398c  call    _guard_dispatch_icall
0x140003991  add     rsp, 68h
0x140003995  retn
```
