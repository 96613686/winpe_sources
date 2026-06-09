# McTemplateU0qp_EtwWriteTransfer

- ea: `0x140040c2c`
- end: `0x140040ca1`
- name: `McTemplateU0qp_EtwWriteTransfer`
- size: `117`
- prototype: ``
- caller_count: `30`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010b0`
- `0x1400018a0`
- `0x140002840`
- `0x14000af30`
- `0x14000b850`
- `0x14000bf30`
- `0x14001d490`
- `0x14001fc30`
- `0x14001ffc0`
- `0x140020010`
- `0x140021b60`
- `0x1400220f0`
- `0x140022270`
- `0x140022710`
- `0x140022f70`
- `0x140023350`
- `0x1400258c0`
- `0x140026600`
- `0x140026770`
- `0x140029810`
- `0x140029970`
- `0x140029a60`
- `0x140029bb0`
- `0x14002db50`
- `0x140040e60`
- `0x1400410d0`
- `0x140041220`
- `0x1400413f0`
- `0x140043a00`
- `0x140043af0`

## callees

- `0x14003c8e0`
- `0x14003e8c4`

## pseudocode

```c
NTSTATUS McTemplateU0qp_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-48h] BYREF
  int *v5; // [rsp+40h] [rbp-38h]
  int v6; // [rsp+48h] [rbp-30h]
  int v7; // [rsp+4Ch] [rbp-2Ch]
  va_list v8; // [rsp+50h] [rbp-28h]
  int v9; // [rsp+58h] [rbp-20h]
  int v10; // [rsp+5Ch] [rbp-1Ch]
  int v11; // [rsp+90h] [rbp+18h] BYREF
  va_list va; // [rsp+98h] [rbp+20h] BYREF

  va_start(va, a3);
  v11 = a3;
  v5 = &v11;
  v7 = 0;
  v6 = 4;
  va_copy(v8, va);
  v10 = 0;
  v9 = 8;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)QuicApiEnter, a3, 3u, &v4);
}

```

## disassembly

```asm
0x140040c2c  mov     r11, rsp
0x140040c2f  mov     [r11+20h], r9
0x140040c33  mov     [r11+18h], r8d
0x140040c37  sub     rsp, 78h
0x140040c3b  mov     rax, cs:__security_cookie
0x140040c42  xor     rax, rsp
0x140040c45  mov     [rsp+78h+var_18], rax
0x140040c4a  lea     rax, [r11+18h]
0x140040c4e  mov     r9d, 3
0x140040c54  mov     [r11-38h], rax
0x140040c58  lea     rdx, QuicApiEnter
0x140040c5f  and     [rsp+78h+var_2C], 0
0x140040c64  lea     rax, [r11+20h]
0x140040c68  mov     [rsp+78h+var_30], 4
0x140040c70  mov     [r11-28h], rax
0x140040c74  lea     rax, [r11-48h]
0x140040c78  and     [rsp+78h+var_1C], 0
0x140040c7d  mov     [r11-58h], rax
0x140040c81  mov     [rsp+78h+var_20], 8
0x140040c89  call    McGenEventWrite_EtwWriteTransfer
0x140040c8e  mov     rcx, [rsp+78h+var_18]
0x140040c93  xor     rcx, rsp; StackCookie
0x140040c96  call    __security_check_cookie
0x140040c9b  add     rsp, 78h
0x140040c9f  retn
```
