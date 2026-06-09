# McTemplateK0qqq_EtwWriteTransfer

- ea: `0x140005ef8`
- end: `0x140005f6b`
- name: `McTemplateK0qqq_EtwWriteTransfer`
- size: `115`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140001010`
- `0x140002b20`
- `0x140002fe0`
- `0x1400034c0`

## callees

- `0x1400048f8`
- `0x140006630`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qqq_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, char a5, char a6)
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
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)LldpduDiscarded, a3, 4u, &v7);
}

```

## disassembly

```asm
0x140005ef8  mov     [rsp-8+arg_18], r9d
0x140005efd  push    rbp
0x140005efe  mov     rbp, rsp
0x140005f01  sub     rsp, 80h
0x140005f08  mov     rax, cs:__security_cookie
0x140005f0f  xor     rax, rsp
0x140005f12  mov     [rbp+var_10], rax
0x140005f16  mov     r9d, 4
0x140005f1c  lea     rax, [rbp+arg_18]
0x140005f20  mov     [rbp+var_40], rax
0x140005f24  lea     rdx, LldpduDiscarded
0x140005f2b  lea     rax, [rbp+arg_20]
0x140005f2f  mov     [rbp+var_38], r9
0x140005f33  mov     [rbp+var_30], rax
0x140005f37  lea     rax, [rbp+arg_28]
0x140005f3b  mov     [rbp+var_20], rax
0x140005f3f  lea     rax, [rbp+var_50]
0x140005f43  mov     [rsp+80h+var_60], rax
0x140005f48  mov     [rbp+var_28], r9
0x140005f4c  mov     [rbp+var_18], r9
0x140005f50  call    McGenEventWrite_EtwWriteTransfer
0x140005f55  mov     rcx, [rbp+var_10]
0x140005f59  xor     rcx, rsp; StackCookie
0x140005f5c  call    __security_check_cookie
0x140005f61  add     rsp, 80h
0x140005f68  pop     rbp
0x140005f69  retn
```
