# McTemplateK0q_EtwWriteTransfer

- ea: `0x140005d78`
- end: `0x140005dc8`
- name: `McTemplateK0q_EtwWriteTransfer`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002fe0`
- `0x140004720`

## callees

- `0x1400048f8`
- `0x140006630`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0q_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-38h] BYREF
  int *v6; // [rsp+40h] [rbp-28h]
  __int64 v7; // [rsp+48h] [rbp-20h]
  int v8; // [rsp+88h] [rbp+20h] BYREF

  v8 = a4;
  v7 = 4;
  v6 = &v8;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 2u, &v5);
}

```

## disassembly

```asm
0x140005d78  mov     r11, rsp
0x140005d7b  mov     [r11+20h], r9d
0x140005d7f  sub     rsp, 68h
0x140005d83  mov     rax, cs:__security_cookie
0x140005d8a  xor     rax, rsp
0x140005d8d  mov     [rsp+68h+var_18], rax
0x140005d92  lea     rax, [r11+20h]
0x140005d96  mov     qword ptr [r11-20h], 4
0x140005d9e  mov     [r11-28h], rax
0x140005da2  mov     r9d, 2
0x140005da8  lea     rax, [r11-38h]
0x140005dac  mov     [r11-48h], rax
0x140005db0  call    McGenEventWrite_EtwWriteTransfer
0x140005db5  mov     rcx, [rsp+68h+var_18]
0x140005dba  xor     rcx, rsp; StackCookie
0x140005dbd  call    __security_check_cookie
0x140005dc2  add     rsp, 68h
0x140005dc6  retn
```
