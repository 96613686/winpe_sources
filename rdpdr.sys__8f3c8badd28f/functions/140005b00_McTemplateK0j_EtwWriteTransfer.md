# McTemplateK0j_EtwWriteTransfer

- ea: `0x140005b00`
- end: `0x140005b49`
- name: `McTemplateK0j_EtwWriteTransfer`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001fe70`

## callees

- `0x140005a98`
- `0x140006480`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0j_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-38h] BYREF
  __int64 *v6; // [rsp+40h] [rbp-28h]
  __int64 v7; // [rsp+48h] [rbp-20h]

  v7 = 16;
  v6 = g_ScDeviceEnumTriggerStartGuid;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, a4, &v5);
}

```

## disassembly

```asm
0x140005b00  mov     r11, rsp
0x140005b03  sub     rsp, 68h
0x140005b07  mov     rax, cs:__security_cookie
0x140005b0e  xor     rax, rsp
0x140005b11  mov     [rsp+68h+var_18], rax
0x140005b16  lea     rax, g_ScDeviceEnumTriggerStartGuid
0x140005b1d  mov     qword ptr [r11-20h], 10h
0x140005b25  mov     [r11-28h], rax
0x140005b29  lea     rax, [r11-38h]
0x140005b2d  mov     [r11-48h], rax
0x140005b31  call    McGenEventWrite_EtwWriteTransfer
0x140005b36  mov     rcx, [rsp+68h+var_18]
0x140005b3b  xor     rcx, rsp; StackCookie
0x140005b3e  call    __security_check_cookie
0x140005b43  add     rsp, 68h
0x140005b47  retn
```
