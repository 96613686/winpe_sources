# McTemplateK0_EtwWriteTransfer

- ea: `0x14000458c`
- end: `0x1400045c7`
- name: `McTemplateK0_EtwWriteTransfer`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140016a34`
- `0x140016dc4`

## callees

- `0x140004158`
- `0x1400054a0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-28h] BYREF

  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 1u, &v4);
}

```

## disassembly

```asm
0x14000458c  sub     rsp, 58h
0x140004590  mov     rax, cs:__security_cookie
0x140004597  xor     rax, rsp
0x14000459a  mov     [rsp+58h+var_18], rax
0x14000459f  lea     rax, [rsp+58h+var_28]
0x1400045a4  mov     r9d, 1
0x1400045aa  mov     [rsp+58h+var_38], rax
0x1400045af  call    McGenEventWrite_EtwWriteTransfer
0x1400045b4  mov     rcx, [rsp+58h+var_18]
0x1400045b9  xor     rcx, rsp; StackCookie
0x1400045bc  call    __security_check_cookie
0x1400045c1  add     rsp, 58h
0x1400045c5  retn
```
