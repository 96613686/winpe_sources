# McTemplateU0qqbr1_EventWriteTransfer

- ea: `0x180011c48`
- end: `0x180011cc7`
- name: `McTemplateU0qqbr1_EventWriteTransfer`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011b3c`
- `0x180012c80`

## callees

- `0x180007fdc`
- `0x18000b410`

## pseudocode

```c
ULONG __fastcall McTemplateU0qqbr1_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        int a3,
        int a4,
        __int64 a5)
{
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-50h] BYREF
  int *v7; // [rsp+40h] [rbp-40h]
  __int64 v8; // [rsp+48h] [rbp-38h]
  int *v9; // [rsp+50h] [rbp-30h]
  __int64 v10; // [rsp+58h] [rbp-28h]
  __int64 v11; // [rsp+60h] [rbp-20h]
  int v12; // [rsp+68h] [rbp-18h]
  int v13; // [rsp+6Ch] [rbp-14h]
  int v14; // [rsp+A0h] [rbp+20h] BYREF
  int v15; // [rsp+A8h] [rbp+28h] BYREF

  v15 = a4;
  v14 = a3;
  v12 = a4;
  v8 = 4;
  v13 = 0;
  v7 = &v14;
  v10 = 4;
  v9 = &v15;
  v11 = a5;
  return McGenEventWrite_EventWriteTransfer((REGHANDLE *)PIX_ETW_PROVIDER_Context, a2, 4, 4u, &v6);
}

```

## disassembly

```asm
0x180011c48  mov     [rsp-8+arg_18], r9d
0x180011c4d  mov     [rsp-8+arg_10], r8d
0x180011c52  push    rbp
0x180011c53  mov     rbp, rsp
0x180011c56  sub     rsp, 80h
0x180011c5d  mov     rax, cs:__security_cookie
0x180011c64  xor     rax, rsp
0x180011c67  mov     [rbp+var_10], rax
0x180011c6b  mov     r8d, 4
0x180011c71  mov     [rbp+var_18], r9d
0x180011c75  xor     ecx, ecx
0x180011c77  mov     [rbp+var_38], r8
0x180011c7b  lea     rax, [rbp+arg_10]
0x180011c7f  mov     [rbp+var_14], ecx
0x180011c82  mov     [rbp+var_40], rax
0x180011c86  lea     rcx, PIX_ETW_PROVIDER_Context
0x180011c8d  lea     rax, [rbp+arg_18]
0x180011c91  mov     [rbp+var_28], r8
0x180011c95  mov     [rbp+var_30], rax
0x180011c99  mov     r9d, r8d
0x180011c9c  mov     rax, [rbp+arg_20]
0x180011ca0  mov     [rbp+var_20], rax
0x180011ca4  lea     rax, [rbp+var_50]
0x180011ca8  mov     [rsp+80h+var_60], rax
0x180011cad  call    McGenEventWrite_EventWriteTransfer
0x180011cb2  mov     rcx, [rbp+var_10]
0x180011cb6  xor     rcx, rsp; StackCookie
0x180011cb9  call    __security_check_cookie
0x180011cbe  add     rsp, 80h
0x180011cc5  pop     rbp
0x180011cc6  retn
```
