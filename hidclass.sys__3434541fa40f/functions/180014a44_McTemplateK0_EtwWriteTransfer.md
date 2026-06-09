# McTemplateK0_EtwWriteTransfer

- ea: `0x180014a44`
- end: `0x180014a7f`
- name: `McTemplateK0_EtwWriteTransfer`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b81c`
- `0x180020c54`

## callees

- `0x180014a88`
- `0x180027ba0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0_EtwWriteTransfer(REGHANDLE *a1, const EVENT_DESCRIPTOR *a2, const GUID *a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-28h] BYREF

  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 1u, &v4);
}

```

## disassembly

```asm
0x180014a44  sub     rsp, 58h
0x180014a48  mov     rax, cs:__security_cookie
0x180014a4f  xor     rax, rsp
0x180014a52  mov     [rsp+58h+var_18], rax
0x180014a57  lea     rax, [rsp+58h+var_28]
0x180014a5c  mov     r9d, 1
0x180014a62  mov     [rsp+58h+var_38], rax
0x180014a67  call    McGenEventWrite_EtwWriteTransfer
0x180014a6c  mov     rcx, [rsp+58h+var_18]
0x180014a71  xor     rcx, rsp; StackCookie
0x180014a74  call    __security_check_cookie
0x180014a79  add     rsp, 58h
0x180014a7d  retn
```
