# McTemplateK0_EtwWriteTransfer

- ea: `0x140009a00`
- end: `0x140009a3b`
- name: `McTemplateK0_EtwWriteTransfer`
- size: `59`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400413b0`
- `0x1400484e0`

## callees

- `0x140004100`
- `0x14000ba20`

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
0x140009a00  sub     rsp, 58h
0x140009a04  mov     rax, cs:__security_cookie
0x140009a0b  xor     rax, rsp
0x140009a0e  mov     [rsp+58h+var_18], rax
0x140009a13  lea     rax, [rsp+58h+var_28]
0x140009a18  mov     r9d, 1
0x140009a1e  mov     [rsp+58h+var_38], rax
0x140009a23  call    McGenEventWrite_EtwWriteTransfer
0x140009a28  mov     rcx, [rsp+58h+var_18]
0x140009a2d  xor     rcx, rsp; StackCookie
0x140009a30  call    __security_check_cookie
0x140009a35  add     rsp, 58h
0x140009a39  retn
```
