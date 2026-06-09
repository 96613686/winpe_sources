# McTemplateK0_EtwWriteTransfer

- ea: `0x14000220c`
- end: `0x14000224e`
- name: `McTemplateK0_EtwWriteTransfer`
- size: `66`
- prototype: `NTSTATUS __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140012658`

## callees

- `0x1400021ac`
- `0x140002ae0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-28h] BYREF

  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)HV_EVENTLOG_HW_WATCHDOG_REBOOT, a3, 1u, &v4);
}

```

## disassembly

```asm
0x14000220c  sub     rsp, 58h
0x140002210  mov     rax, cs:__security_cookie
0x140002217  xor     rax, rsp
0x14000221a  mov     [rsp+58h+var_18], rax
0x14000221f  lea     rax, [rsp+58h+var_28]
0x140002224  mov     r9d, 1
0x14000222a  lea     rdx, HV_EVENTLOG_HW_WATCHDOG_REBOOT
0x140002231  mov     [rsp+58h+var_38], rax
0x140002236  call    McGenEventWrite_EtwWriteTransfer
0x14000223b  mov     rcx, [rsp+58h+var_18]
0x140002240  xor     rcx, rsp; StackCookie
0x140002243  call    __security_check_cookie
0x140002248  add     rsp, 58h
0x14000224c  retn
```
