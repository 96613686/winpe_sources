# McTemplateU0_EtwWriteTransfer

- ea: `0x14003eb54`
- end: `0x14003eb8f`
- name: `McTemplateU0_EtwWriteTransfer`
- size: `59`
- prototype: ``
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x140001008`
- `0x1400018a0`
- `0x14001d490`
- `0x14001fc30`
- `0x14001ffc0`
- `0x1400220f0`
- `0x140022270`
- `0x140022f70`
- `0x140023350`
- `0x140023e4c`
- `0x140023f20`
- `0x140025700`
- `0x140025780`
- `0x140041220`
- `0x140043a00`
- `0x140043af0`

## callees

- `0x14003c8e0`
- `0x14003e8c4`

## pseudocode

```c
NTSTATUS __fastcall McTemplateU0_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-28h] BYREF

  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 1u, &v4);
}

```

## disassembly

```asm
0x14003eb54  sub     rsp, 58h
0x14003eb58  mov     rax, cs:__security_cookie
0x14003eb5f  xor     rax, rsp
0x14003eb62  mov     [rsp+58h+var_18], rax
0x14003eb67  lea     rax, [rsp+58h+var_28]
0x14003eb6c  mov     r9d, 1
0x14003eb72  mov     [rsp+58h+var_38], rax
0x14003eb77  call    McGenEventWrite_EtwWriteTransfer
0x14003eb7c  mov     rcx, [rsp+58h+var_18]
0x14003eb81  xor     rcx, rsp; StackCookie
0x14003eb84  call    __security_check_cookie
0x14003eb89  add     rsp, 58h
0x14003eb8d  retn
```
