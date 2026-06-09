# McTemplateK0qpd_EtwWriteTransfer

- ea: `0x140003cb0`
- end: `0x140003d27`
- name: `McTemplateK0qpd_EtwWriteTransfer`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400014a0`

## callees

- `0x140003c54`
- `0x140005bf0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qpd_EtwWriteTransfer(__int64 a1, __int64 a2, const GUID *a3, int a4, char a5, char a6)
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
  v11 = 8;
  v9 = 4;
  v8 = &v14;
  v13 = 4;
  v10 = &a5;
  v12 = &a6;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)EventNonReadWriteRequestComplete, a3, 4u, &v7);
}

```

## disassembly

```asm
0x140003cb0  mov     [rsp-8+arg_18], r9d
0x140003cb5  push    rbp
0x140003cb6  mov     rbp, rsp
0x140003cb9  sub     rsp, 80h
0x140003cc0  mov     rax, cs:__security_cookie
0x140003cc7  xor     rax, rsp
0x140003cca  mov     [rbp+var_10], rax
0x140003cce  mov     r9d, 4
0x140003cd4  mov     [rbp+var_28], 8
0x140003cdc  lea     rax, [rbp+arg_18]
0x140003ce0  mov     [rbp+var_38], r9
0x140003ce4  mov     [rbp+var_40], rax
0x140003ce8  lea     rdx, EventNonReadWriteRequestComplete
0x140003cef  lea     rax, [rbp+arg_20]
0x140003cf3  mov     [rbp+var_18], r9
0x140003cf7  mov     [rbp+var_30], rax
0x140003cfb  lea     rax, [rbp+arg_28]
0x140003cff  mov     [rbp+var_20], rax
0x140003d03  lea     rax, [rbp+var_50]
0x140003d07  mov     [rsp+80h+var_60], rax
0x140003d0c  call    McGenEventWrite_EtwWriteTransfer
0x140003d11  mov     rcx, [rbp+var_10]
0x140003d15  xor     rcx, rsp; StackCookie
0x140003d18  call    __security_check_cookie
0x140003d1d  add     rsp, 80h
0x140003d24  pop     rbp
0x140003d25  retn
```
