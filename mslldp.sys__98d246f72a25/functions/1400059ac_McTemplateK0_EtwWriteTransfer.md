# McTemplateK0_EtwWriteTransfer

- ea: `0x1400059ac`
- end: `0x1400059e7`
- name: `McTemplateK0_EtwWriteTransfer`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f8f4`
- `0x140013008`

## callees

- `0x1400048f8`
- `0x140006630`

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
0x1400059ac  sub     rsp, 58h
0x1400059b0  mov     rax, cs:__security_cookie
0x1400059b7  xor     rax, rsp
0x1400059ba  mov     [rsp+58h+var_18], rax
0x1400059bf  lea     rax, [rsp+58h+var_28]
0x1400059c4  mov     r9d, 1
0x1400059ca  mov     [rsp+58h+var_38], rax
0x1400059cf  call    McGenEventWrite_EtwWriteTransfer
0x1400059d4  mov     rcx, [rsp+58h+var_18]
0x1400059d9  xor     rcx, rsp; StackCookie
0x1400059dc  call    __security_check_cookie
0x1400059e1  add     rsp, 58h
0x1400059e5  retn
```
