# McTemplateU0x_EventWriteTransfer

- ea: `0x180007f78`
- end: `0x180007fd5`
- name: `McTemplateU0x_EventWriteTransfer`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007f60`

## callees

- `0x180007fdc`
- `0x18000b410`

## pseudocode

```c
ULONG __fastcall McTemplateU0x_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF
  __int64 *v5; // [rsp+40h] [rbp-28h]
  __int64 v6; // [rsp+48h] [rbp-20h]
  __int64 v7; // [rsp+80h] [rbp+18h] BYREF

  v7 = a3;
  v6 = 8;
  v5 = &v7;
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)PIX_ETW_PROVIDER_Context,
           (const EVENT_DESCRIPTOR *)PIXNotifyWakeFromFenceSignalEventData,
           a3,
           2u,
           &v4);
}

```

## disassembly

```asm
0x180007f78  mov     r11, rsp
0x180007f7b  mov     [r11+18h], r8
0x180007f7f  sub     rsp, 68h
0x180007f83  mov     rax, cs:__security_cookie
0x180007f8a  xor     rax, rsp
0x180007f8d  mov     [rsp+68h+var_18], rax
0x180007f92  lea     rax, [r11+18h]
0x180007f96  mov     qword ptr [r11-20h], 8
0x180007f9e  mov     [r11-28h], rax
0x180007fa2  lea     rdx, PIXNotifyWakeFromFenceSignalEventData
0x180007fa9  lea     rax, [r11-38h]
0x180007fad  mov     r9d, 2
0x180007fb3  lea     rcx, PIX_ETW_PROVIDER_Context
0x180007fba  mov     [r11-48h], rax
0x180007fbe  call    McGenEventWrite_EventWriteTransfer
0x180007fc3  mov     rcx, [rsp+68h+var_18]
0x180007fc8  xor     rcx, rsp; StackCookie
0x180007fcb  call    __security_check_cookie
0x180007fd0  add     rsp, 68h
0x180007fd4  retn
```
