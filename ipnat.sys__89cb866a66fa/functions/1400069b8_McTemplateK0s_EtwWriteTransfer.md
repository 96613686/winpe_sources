# McTemplateK0s_EtwWriteTransfer

- ea: `0x1400069b8`
- end: `0x140006a01`
- name: `McTemplateK0s_EtwWriteTransfer`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006c08`

## callees

- `0x140006950`
- `0x14002c6d0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0s_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-38h] BYREF
  const char *v6; // [rsp+40h] [rbp-28h]
  __int64 v7; // [rsp+48h] [rbp-20h]

  v7 = 43;
  v6 = "Could not allocate debug trace buffer pool";
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, a4, &v5);
}

```

## disassembly

```asm
0x1400069b8  mov     r11, rsp
0x1400069bb  sub     rsp, 68h
0x1400069bf  mov     rax, cs:__security_cookie
0x1400069c6  xor     rax, rsp
0x1400069c9  mov     [rsp+68h+var_18], rax
0x1400069ce  lea     rax, aCouldNotAlloca; "Could not allocate debug trace buffer p"...
0x1400069d5  mov     qword ptr [r11-20h], 2Bh ; '+'
0x1400069dd  mov     [r11-28h], rax
0x1400069e1  lea     rax, [r11-38h]
0x1400069e5  mov     [r11-48h], rax
0x1400069e9  call    McGenEventWrite_EtwWriteTransfer
0x1400069ee  mov     rcx, [rsp+68h+var_18]
0x1400069f3  xor     rcx, rsp; StackCookie
0x1400069f6  call    __security_check_cookie
0x1400069fb  add     rsp, 68h
0x1400069ff  retn
```
