# McTemplateK0qqbr1qbr3_EtwWriteTransfer

- ea: `0x140005e4c`
- end: `0x140005eef`
- name: `McTemplateK0qqbr1qbr3_EtwWriteTransfer`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002fe0`

## callees

- `0x1400048f8`
- `0x140006630`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qqbr1qbr3_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        int a7,
        __int64 a8)
{
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-39h] BYREF
  int *v10; // [rsp+40h] [rbp-29h]
  __int64 v11; // [rsp+48h] [rbp-21h]
  int *v12; // [rsp+50h] [rbp-19h]
  __int64 v13; // [rsp+58h] [rbp-11h]
  __int64 v14; // [rsp+60h] [rbp-9h]
  int v15; // [rsp+68h] [rbp-1h]
  int v16; // [rsp+6Ch] [rbp+3h]
  int *v17; // [rsp+70h] [rbp+7h]
  __int64 v18; // [rsp+78h] [rbp+Fh]
  __int64 v19; // [rsp+80h] [rbp+17h]
  int v20; // [rsp+88h] [rbp+1Fh]
  int v21; // [rsp+8Ch] [rbp+23h]
  int v22; // [rsp+C8h] [rbp+5Fh] BYREF

  v22 = a4;
  v11 = 4;
  v16 = 0;
  v10 = &v22;
  v12 = &a5;
  v14 = a6;
  v15 = a5;
  v17 = &a7;
  v19 = a8;
  v20 = a7;
  v21 = 0;
  v13 = 4;
  v18 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)TooManyNeighborsReceive, a3, 6u, &v9);
}

```

## disassembly

```asm
0x140005e4c  mov     [rsp-8+arg_18], r9d
0x140005e51  push    rbp
0x140005e52  lea     rbp, [rsp-37h]
0x140005e57  sub     rsp, 0A0h
0x140005e5e  mov     rax, cs:__security_cookie
0x140005e65  xor     rax, rsp
0x140005e68  mov     [rbp+37h+var_10], rax
0x140005e6c  xor     edx, edx
0x140005e6e  mov     [rbp+37h+var_58], 4
0x140005e76  lea     rax, [rbp+37h+arg_18]
0x140005e7a  mov     [rbp+37h+var_34], edx
0x140005e7d  mov     [rbp+37h+var_60], rax
0x140005e81  lea     rax, [rbp+37h+arg_20]
0x140005e85  mov     [rbp+37h+var_50], rax
0x140005e89  mov     rax, [rbp+37h+arg_28]
0x140005e8d  lea     r9d, [rdx+6]
0x140005e91  mov     [rbp+37h+var_40], rax
0x140005e95  mov     eax, [rbp+37h+arg_20]
0x140005e98  mov     [rbp+37h+var_38], eax
0x140005e9b  lea     rax, [rbp+37h+arg_30]
0x140005e9f  mov     [rbp+37h+var_30], rax
0x140005ea3  mov     rax, [rbp+37h+arg_38]
0x140005ea7  mov     [rbp+37h+var_20], rax
0x140005eab  mov     eax, [rbp+37h+arg_30]
0x140005eae  mov     [rbp+37h+var_18], eax
0x140005eb1  lea     rax, [rbp+37h+var_70]
0x140005eb5  mov     [rbp+37h+var_14], edx
0x140005eb8  lea     rdx, TooManyNeighborsReceive
0x140005ebf  mov     [rsp+0A0h+var_80], rax
0x140005ec4  mov     [rbp+37h+var_48], 4
0x140005ecc  mov     [rbp+37h+var_28], 4
0x140005ed4  call    McGenEventWrite_EtwWriteTransfer
0x140005ed9  mov     rcx, [rbp+37h+var_10]
0x140005edd  xor     rcx, rsp; StackCookie
0x140005ee0  call    __security_check_cookie
0x140005ee5  add     rsp, 0A0h
0x140005eec  pop     rbp
0x140005eed  retn
```
