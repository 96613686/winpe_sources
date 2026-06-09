# McTemplateU0xqxxqq_EtwEventWriteTransfer

- ea: `0x18000be7c`
- end: `0x18000bf38`
- name: `McTemplateU0xqxxqq_EtwEventWriteTransfer`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002200`

## callees

- `0x180004594`
- `0x18000d0a0`

## pseudocode

```c
__int64 __fastcall McTemplateU0xqxxqq_EtwEventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        char a7,
        char a8)
{
  char v9[16]; // [rsp+30h] [rbp-49h] BYREF
  __int64 *v10; // [rsp+40h] [rbp-39h]
  __int64 v11; // [rsp+48h] [rbp-31h]
  int *v12; // [rsp+50h] [rbp-29h]
  __int64 v13; // [rsp+58h] [rbp-21h]
  char *v14; // [rsp+60h] [rbp-19h]
  __int64 v15; // [rsp+68h] [rbp-11h]
  char *v16; // [rsp+70h] [rbp-9h]
  __int64 v17; // [rsp+78h] [rbp-1h]
  char *v18; // [rsp+80h] [rbp+7h]
  __int64 v19; // [rsp+88h] [rbp+Fh]
  char *v20; // [rsp+90h] [rbp+17h]
  __int64 v21; // [rsp+98h] [rbp+1Fh]
  __int64 v22; // [rsp+D0h] [rbp+57h] BYREF
  int v23; // [rsp+D8h] [rbp+5Fh] BYREF

  v23 = a4;
  v22 = a3;
  v11 = 8;
  v10 = &v22;
  v13 = 4;
  v12 = &v23;
  v15 = 8;
  v14 = &a5;
  v17 = 8;
  v16 = &a6;
  v18 = &a7;
  v20 = &a8;
  v19 = 4;
  v21 = 4;
  return McGenEventWrite_EtwEventWriteTransfer(
           Microsoft_Windows_Dwm_Api_Provider_Context,
           (__int64)ApipDxGetWindowSharedSurface_Stop,
           a3,
           7,
           (__int64)v9);
}

```

## disassembly

```asm
0x18000be7c  mov     [rsp-8+arg_18], r9d
0x18000be81  mov     [rsp-8+arg_10], r8
0x18000be86  push    rbp
0x18000be87  lea     rbp, [rsp-37h]
0x18000be8c  sub     rsp, 0B0h
0x18000be93  mov     rax, cs:__security_cookie
0x18000be9a  xor     rax, rsp
0x18000be9d  mov     [rbp+37h+var_10], rax
0x18000bea1  lea     rax, [rbp+37h+arg_10]
0x18000bea5  mov     [rbp+37h+var_68], 8
0x18000bead  mov     [rbp+37h+var_70], rax
0x18000beb1  lea     rdx, ApipDxGetWindowSharedSurface_Stop
0x18000beb8  lea     rax, [rbp+37h+arg_18]
0x18000bebc  mov     [rbp+37h+var_58], 4
0x18000bec4  mov     [rbp+37h+var_60], rax
0x18000bec8  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x18000becf  lea     rax, [rbp+37h+arg_20]
0x18000bed3  mov     [rbp+37h+var_48], 8
0x18000bedb  mov     [rbp+37h+var_50], rax
0x18000bedf  mov     r9d, 7
0x18000bee5  lea     rax, [rbp+37h+arg_28]
0x18000bee9  mov     [rbp+37h+var_38], 8
0x18000bef1  mov     [rbp+37h+var_40], rax
0x18000bef5  lea     rax, [rbp+37h+arg_30]
0x18000bef9  mov     [rbp+37h+var_30], rax
0x18000befd  lea     rax, [rbp+37h+arg_38]
0x18000bf01  mov     [rbp+37h+var_20], rax
0x18000bf05  lea     rax, [rbp+37h+var_80]
0x18000bf09  mov     [rsp+0B0h+var_90], rax
0x18000bf0e  mov     [rbp+37h+var_28], 4
0x18000bf16  mov     [rbp+37h+var_18], 4
0x18000bf1e  call    McGenEventWrite_EtwEventWriteTransfer
0x18000bf23  mov     rcx, [rbp+37h+var_10]
0x18000bf27  xor     rcx, rsp; StackCookie
0x18000bf2a  call    __security_check_cookie
0x18000bf2f  add     rsp, 0B0h
0x18000bf36  pop     rbp
0x18000bf37  retn
```
