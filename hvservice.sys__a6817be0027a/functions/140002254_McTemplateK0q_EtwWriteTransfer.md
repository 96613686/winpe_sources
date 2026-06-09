# McTemplateK0q_EtwWriteTransfer

- ea: `0x140002254`
- end: `0x1400022ab`
- name: `McTemplateK0q_EtwWriteTransfer`
- size: `87`
- prototype: `NTSTATUS __fastcall(__int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400129f4`

## callees

- `0x1400021ac`
- `0x140002ae0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0q_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-38h] BYREF
  int *v6; // [rsp+40h] [rbp-28h]
  __int64 v7; // [rsp+48h] [rbp-20h]
  int v8; // [rsp+88h] [rbp+20h] BYREF

  v8 = a4;
  v7 = 4;
  v6 = &v8;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)HV_EVENTLOG_SECFW_UPDATE_STATUS, a3, 2u, &v5);
}

```

## disassembly

```asm
0x140002254  mov     r11, rsp
0x140002257  mov     [r11+20h], r9d
0x14000225b  sub     rsp, 68h
0x14000225f  mov     rax, cs:__security_cookie
0x140002266  xor     rax, rsp
0x140002269  mov     [rsp+68h+var_18], rax
0x14000226e  lea     rax, [r11+20h]
0x140002272  mov     qword ptr [r11-20h], 4
0x14000227a  mov     [r11-28h], rax
0x14000227e  lea     rdx, HV_EVENTLOG_SECFW_UPDATE_STATUS
0x140002285  lea     rax, [r11-38h]
0x140002289  mov     r9d, 2
0x14000228f  mov     [r11-48h], rax
0x140002293  call    McGenEventWrite_EtwWriteTransfer
0x140002298  mov     rcx, [rsp+68h+var_18]
0x14000229d  xor     rcx, rsp; StackCookie
0x1400022a0  call    __security_check_cookie
0x1400022a5  add     rsp, 68h
0x1400022a9  retn
```
