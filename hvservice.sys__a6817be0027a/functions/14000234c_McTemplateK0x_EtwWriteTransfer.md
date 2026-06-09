# McTemplateK0x_EtwWriteTransfer

- ea: `0x14000234c`
- end: `0x1400023a3`
- name: `McTemplateK0x_EtwWriteTransfer`
- size: `87`
- prototype: `NTSTATUS(__int64, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400129f4`

## callees

- `0x1400021ac`
- `0x140002ae0`

## pseudocode

```c
NTSTATUS McTemplateK0x_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF
  va_list v5; // [rsp+40h] [rbp-28h]
  __int64 v6; // [rsp+48h] [rbp-20h]
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, a3);
  v6 = 8;
  va_copy(v5, va);
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)HV_EVENTLOG_SECFW_VERSION, a3, 2u, &v4);
}

```

## disassembly

```asm
0x14000234c  mov     r11, rsp
0x14000234f  mov     [r11+20h], r9
0x140002353  sub     rsp, 68h
0x140002357  mov     rax, cs:__security_cookie
0x14000235e  xor     rax, rsp
0x140002361  mov     [rsp+68h+var_18], rax
0x140002366  lea     rax, [r11+20h]
0x14000236a  mov     qword ptr [r11-20h], 8
0x140002372  mov     [r11-28h], rax
0x140002376  lea     rdx, HV_EVENTLOG_SECFW_VERSION
0x14000237d  lea     rax, [r11-38h]
0x140002381  mov     r9d, 2
0x140002387  mov     [r11-48h], rax
0x14000238b  call    McGenEventWrite_EtwWriteTransfer
0x140002390  mov     rcx, [rsp+68h+var_18]
0x140002395  xor     rcx, rsp; StackCookie
0x140002398  call    __security_check_cookie
0x14000239d  add     rsp, 68h
0x1400023a1  retn
```
