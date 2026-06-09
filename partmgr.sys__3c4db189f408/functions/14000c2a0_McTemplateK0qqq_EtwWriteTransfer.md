# McTemplateK0qqq_EtwWriteTransfer

- ea: `0x14000c2a0`
- end: `0x14000c313`
- name: `McTemplateK0qqq_EtwWriteTransfer`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001fb44`

## callees

- `0x140004300`
- `0x140010f20`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qqq_EtwWriteTransfer(__int64 a1, __int64 a2, const GUID *a3, int a4, char a5, char a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-50h] BYREF
  int *v8; // [rsp+40h] [rbp-40h]
  __int64 v9; // [rsp+48h] [rbp-38h]
  char *v10; // [rsp+50h] [rbp-30h]
  __int64 v11; // [rsp+58h] [rbp-28h]
  char *v12; // [rsp+60h] [rbp-20h]
  __int64 v13; // [rsp+68h] [rbp-18h]
  int v14; // [rsp+A8h] [rbp+28h] BYREF

  v14 = a4;
  v8 = &v14;
  v9 = 4;
  v10 = &a5;
  v12 = &a6;
  v11 = 4;
  v13 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)ControlComplete, a3, 4u, &v7);
}

```

## disassembly

```asm
0x14000c2a0  mov     [rsp-8+arg_18], r9d
0x14000c2a5  push    rbp
0x14000c2a6  mov     rbp, rsp
0x14000c2a9  sub     rsp, 80h
0x14000c2b0  mov     rax, cs:__security_cookie
0x14000c2b7  xor     rax, rsp
0x14000c2ba  mov     [rbp+var_10], rax
0x14000c2be  mov     r9d, 4
0x14000c2c4  lea     rax, [rbp+arg_18]
0x14000c2c8  mov     [rbp+var_40], rax
0x14000c2cc  lea     rdx, ControlComplete
0x14000c2d3  lea     rax, [rbp+arg_20]
0x14000c2d7  mov     [rbp+var_38], r9
0x14000c2db  mov     [rbp+var_30], rax
0x14000c2df  lea     rax, [rbp+arg_28]
0x14000c2e3  mov     [rbp+var_20], rax
0x14000c2e7  lea     rax, [rbp+var_50]
0x14000c2eb  mov     [rsp+80h+var_60], rax
0x14000c2f0  mov     [rbp+var_28], r9
0x14000c2f4  mov     [rbp+var_18], r9
0x14000c2f8  call    McGenEventWrite_EtwWriteTransfer
0x14000c2fd  mov     rcx, [rbp+var_10]
0x14000c301  xor     rcx, rsp; StackCookie
0x14000c304  call    __security_check_cookie
0x14000c309  add     rsp, 80h
0x14000c310  pop     rbp
0x14000c311  retn
```
