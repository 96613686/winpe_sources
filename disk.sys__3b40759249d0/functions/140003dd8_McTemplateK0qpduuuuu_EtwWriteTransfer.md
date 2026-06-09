# McTemplateK0qpduuuuu_EtwWriteTransfer

- ea: `0x140003dd8`
- end: `0x140003ec3`
- name: `McTemplateK0qpduuuuu_EtwWriteTransfer`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140012210`

## callees

- `0x140003c54`
- `0x140005bf0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qpduuuuu_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        const GUID *a3,
        int a4,
        char a5,
        char a6)
{
  char v7; // [rsp+30h] [rbp-B1h] BYREF
  char v8; // [rsp+38h] [rbp-A9h] BYREF
  char v9; // [rsp+40h] [rbp-A1h] BYREF
  char v10; // [rsp+48h] [rbp-99h] BYREF
  char v11; // [rsp+50h] [rbp-91h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+60h] [rbp-81h] BYREF
  int *v13; // [rsp+70h] [rbp-71h]
  __int64 v14; // [rsp+78h] [rbp-69h]
  char *v15; // [rsp+80h] [rbp-61h]
  __int64 v16; // [rsp+88h] [rbp-59h]
  char *v17; // [rsp+90h] [rbp-51h]
  __int64 v18; // [rsp+98h] [rbp-49h]
  char *v19; // [rsp+A0h] [rbp-41h]
  __int64 v20; // [rsp+A8h] [rbp-39h]
  char *v21; // [rsp+B0h] [rbp-31h]
  __int64 v22; // [rsp+B8h] [rbp-29h]
  char *v23; // [rsp+C0h] [rbp-21h]
  __int64 v24; // [rsp+C8h] [rbp-19h]
  char *v25; // [rsp+D0h] [rbp-11h]
  __int64 v26; // [rsp+D8h] [rbp-9h]
  char *v27; // [rsp+E0h] [rbp-1h]
  __int64 v28; // [rsp+E8h] [rbp+7h]
  int v29; // [rsp+128h] [rbp+47h] BYREF

  v29 = a4;
  v14 = 4;
  v11 = 0;
  v13 = &v29;
  v15 = &a5;
  v17 = &a6;
  v10 = 0;
  v19 = &v7;
  v21 = &v8;
  v23 = &v9;
  v25 = &v10;
  v27 = &v11;
  v9 = 0;
  v8 = 0;
  v7 = 0;
  v16 = 8;
  v18 = 4;
  v20 = 1;
  v22 = 1;
  v24 = 1;
  v26 = 1;
  v28 = 1;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)EventIORequestComplete, a3, 9u, &v12);
}

```

## disassembly

```asm
0x140003dd8  mov     [rsp-8+arg_18], r9d
0x140003ddd  push    rbp
0x140003dde  lea     rbp, [rsp-1Fh]
0x140003de3  sub     rsp, 100h
0x140003dea  mov     rax, cs:__security_cookie
0x140003df1  xor     rax, rsp
0x140003df4  mov     [rbp+1Fh+var_10], rax
0x140003df8  xor     edx, edx
0x140003dfa  mov     [rbp+1Fh+var_88], 4
0x140003e02  lea     rax, [rbp+1Fh+arg_18]
0x140003e06  mov     [rsp+100h+var_B0], dl
0x140003e0a  mov     [rbp+1Fh+var_90], rax
0x140003e0e  lea     rax, [rbp+1Fh+arg_20]
0x140003e12  mov     [rbp+1Fh+var_80], rax
0x140003e16  lea     rax, [rbp+1Fh+arg_28]
0x140003e1a  mov     [rbp+1Fh+var_70], rax
0x140003e1e  lea     r9d, [rdx+9]
0x140003e22  lea     rax, [rsp+100h+var_D0]
0x140003e27  mov     [rsp+100h+var_B8], dl
0x140003e2b  mov     [rbp+1Fh+var_60], rax
0x140003e2f  lea     rax, [rsp+100h+var_C8]
0x140003e34  mov     [rbp+1Fh+var_50], rax
0x140003e38  lea     rax, [rsp+100h+var_C0]
0x140003e3d  mov     [rbp+1Fh+var_40], rax
0x140003e41  lea     rax, [rsp+100h+var_B8]
0x140003e46  mov     [rbp+1Fh+var_30], rax
0x140003e4a  lea     rax, [rsp+100h+var_B0]
0x140003e4f  mov     [rbp+1Fh+var_20], rax
0x140003e53  lea     rax, [rsp+100h+var_A0]
0x140003e58  mov     [rsp+100h+var_C0], dl
0x140003e5c  mov     [rsp+100h+var_C8], dl
0x140003e60  mov     [rsp+100h+var_D0], dl
0x140003e64  lea     rdx, EventIORequestComplete
0x140003e6b  mov     [rsp+100h+var_E0], rax
0x140003e70  mov     [rbp+1Fh+var_78], 8
0x140003e78  mov     [rbp+1Fh+var_68], 4
0x140003e80  mov     [rbp+1Fh+var_58], 1
0x140003e88  mov     [rbp+1Fh+var_48], 1
0x140003e90  mov     [rbp+1Fh+var_38], 1
0x140003e98  mov     [rbp+1Fh+var_28], 1
0x140003ea0  mov     [rbp+1Fh+var_18], 1
0x140003ea8  call    McGenEventWrite_EtwWriteTransfer
0x140003ead  mov     rcx, [rbp+1Fh+var_10]
0x140003eb1  xor     rcx, rsp; StackCookie
0x140003eb4  call    __security_check_cookie
0x140003eb9  add     rsp, 100h
0x140003ec0  pop     rbp
0x140003ec1  retn
```
