# McTemplateK0qpuxi_EtwWriteTransfer

- ea: `0x140003ecc`
- end: `0x140003f71`
- name: `McTemplateK0qpuxi_EtwWriteTransfer`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140012210`

## callees

- `0x140003c54`
- `0x140005bf0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qpuxi_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        const GUID *a3,
        int a4,
        char a5,
        int a6,
        char a7,
        char a8)
{
  char v9; // [rsp+30h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+40h] [rbp-39h] BYREF
  int *v11; // [rsp+50h] [rbp-29h]
  __int64 v12; // [rsp+58h] [rbp-21h]
  char *v13; // [rsp+60h] [rbp-19h]
  __int64 v14; // [rsp+68h] [rbp-11h]
  char *v15; // [rsp+70h] [rbp-9h]
  __int64 v16; // [rsp+78h] [rbp-1h]
  char *v17; // [rsp+80h] [rbp+7h]
  __int64 v18; // [rsp+88h] [rbp+Fh]
  char *v19; // [rsp+90h] [rbp+17h]
  __int64 v20; // [rsp+98h] [rbp+1Fh]
  int v21; // [rsp+D8h] [rbp+5Fh] BYREF

  v21 = a4;
  v9 = 40;
  v11 = &v21;
  v12 = 4;
  v13 = &a5;
  v14 = 8;
  v15 = &v9;
  v17 = &a7;
  v19 = &a8;
  v16 = 1;
  v18 = 8;
  v20 = 8;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)EventReadRequest, a3, 6u, &v10);
}

```

## disassembly

```asm
0x140003ecc  mov     [rsp-8+arg_18], r9d
0x140003ed1  push    rbp
0x140003ed2  lea     rbp, [rsp-37h]
0x140003ed7  sub     rsp, 0B0h
0x140003ede  mov     rax, cs:__security_cookie
0x140003ee5  xor     rax, rsp
0x140003ee8  mov     [rbp+37h+var_10], rax
0x140003eec  lea     rax, [rbp+37h+arg_18]
0x140003ef0  mov     [rbp+37h+var_80], 28h ; '('
0x140003ef4  mov     [rbp+37h+var_60], rax
0x140003ef8  lea     rdx, EventReadRequest
0x140003eff  lea     rax, [rbp+37h+arg_20]
0x140003f03  mov     [rbp+37h+var_58], 4
0x140003f0b  mov     [rbp+37h+var_50], rax
0x140003f0f  mov     r9d, 6
0x140003f15  lea     rax, [rbp+37h+var_80]
0x140003f19  mov     [rbp+37h+var_48], 8
0x140003f21  mov     [rbp+37h+var_40], rax
0x140003f25  lea     rax, [rbp+37h+arg_30]
0x140003f29  mov     [rbp+37h+var_30], rax
0x140003f2d  lea     rax, [rbp+37h+arg_38]
0x140003f31  mov     [rbp+37h+var_20], rax
0x140003f35  lea     rax, [rbp+37h+var_70]
0x140003f39  mov     [rsp+0B0h+var_90], rax
0x140003f3e  mov     [rbp+37h+var_38], 1
0x140003f46  mov     [rbp+37h+var_28], 8
0x140003f4e  mov     [rbp+37h+var_18], 8
0x140003f56  call    McGenEventWrite_EtwWriteTransfer
0x140003f5b  mov     rcx, [rbp+37h+var_10]
0x140003f5f  xor     rcx, rsp; StackCookie
0x140003f62  call    __security_check_cookie
0x140003f67  add     rsp, 0B0h
0x140003f6e  pop     rbp
0x140003f6f  retn
```
