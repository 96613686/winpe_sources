# McTemplateK0qpddd_EtwWriteTransfer

- ea: `0x140003d30`
- end: `0x140003dd1`
- name: `McTemplateK0qpddd_EtwWriteTransfer`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400014a0`

## callees

- `0x140003c54`
- `0x140005bf0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qpddd_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        const GUID *a3,
        int a4,
        char a5,
        char a6,
        char a7,
        char a8)
{
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-39h] BYREF
  int *v10; // [rsp+40h] [rbp-29h]
  __int64 v11; // [rsp+48h] [rbp-21h]
  char *v12; // [rsp+50h] [rbp-19h]
  __int64 v13; // [rsp+58h] [rbp-11h]
  char *v14; // [rsp+60h] [rbp-9h]
  __int64 v15; // [rsp+68h] [rbp-1h]
  char *v16; // [rsp+70h] [rbp+7h]
  __int64 v17; // [rsp+78h] [rbp+Fh]
  char *v18; // [rsp+80h] [rbp+17h]
  __int64 v19; // [rsp+88h] [rbp+1Fh]
  int v20; // [rsp+C8h] [rbp+5Fh] BYREF

  v20 = a4;
  v11 = 4;
  v10 = &v20;
  v13 = 8;
  v12 = &a5;
  v15 = 4;
  v14 = &a6;
  v16 = &a7;
  v18 = &a8;
  v17 = 4;
  v19 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)EventIOCTL, a3, 6u, &v9);
}

```

## disassembly

```asm
0x140003d30  mov     [rsp-8+arg_18], r9d
0x140003d35  push    rbp
0x140003d36  lea     rbp, [rsp-37h]
0x140003d3b  sub     rsp, 0A0h
0x140003d42  mov     rax, cs:__security_cookie
0x140003d49  xor     rax, rsp
0x140003d4c  mov     [rbp+37h+var_10], rax
0x140003d50  lea     rax, [rbp+37h+arg_18]
0x140003d54  mov     [rbp+37h+var_58], 4
0x140003d5c  mov     [rbp+37h+var_60], rax
0x140003d60  lea     rdx, EventIOCTL
0x140003d67  lea     rax, [rbp+37h+arg_20]
0x140003d6b  mov     [rbp+37h+var_48], 8
0x140003d73  mov     [rbp+37h+var_50], rax
0x140003d77  mov     r9d, 6
0x140003d7d  lea     rax, [rbp+37h+arg_28]
0x140003d81  mov     [rbp+37h+var_38], 4
0x140003d89  mov     [rbp+37h+var_40], rax
0x140003d8d  lea     rax, [rbp+37h+arg_30]
0x140003d91  mov     [rbp+37h+var_30], rax
0x140003d95  lea     rax, [rbp+37h+arg_38]
0x140003d99  mov     [rbp+37h+var_20], rax
0x140003d9d  lea     rax, [rbp+37h+var_70]
0x140003da1  mov     [rsp+0A0h+var_80], rax
0x140003da6  mov     [rbp+37h+var_28], 4
0x140003dae  mov     [rbp+37h+var_18], 4
0x140003db6  call    McGenEventWrite_EtwWriteTransfer
0x140003dbb  mov     rcx, [rbp+37h+var_10]
0x140003dbf  xor     rcx, rsp; StackCookie
0x140003dc2  call    __security_check_cookie
0x140003dc7  add     rsp, 0A0h
0x140003dce  pop     rbp
0x140003dcf  retn
```
