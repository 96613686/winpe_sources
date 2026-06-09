# McTemplateU0pddddd_EventWriteTransfer

- ea: `0x18006538c`
- end: `0x180065441`
- name: `McTemplateU0pddddd_EventWriteTransfer`
- size: `181`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800602f0`
- `0x1800609e0`
- `0x180060f90`

## callees

- `0x180024220`
- `0x180058578`

## pseudocode

```c
ULONG __fastcall McTemplateU0pddddd_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        char a7,
        char a8)
{
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-49h] BYREF
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
  v15 = 4;
  v14 = &a5;
  v16 = &a6;
  v18 = &a7;
  v20 = &a8;
  v17 = 4;
  v19 = 4;
  v21 = 4;
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)Microsoft_Windows_MediaFoundation_Performance_Context,
           a2,
           a3,
           7u,
           &v9);
}

```

## disassembly

```asm
0x18006538c  mov     [rsp-8+arg_18], r9d
0x180065391  mov     [rsp-8+arg_10], r8
0x180065396  push    rbp
0x180065397  lea     rbp, [rsp-37h]
0x18006539c  sub     rsp, 0B0h
0x1800653a3  mov     rax, cs:__security_cookie
0x1800653aa  xor     rax, rsp
0x1800653ad  mov     [rbp+37h+var_10], rax
0x1800653b1  lea     rax, [rbp+37h+arg_10]
0x1800653b5  mov     [rbp+37h+var_68], 8
0x1800653bd  mov     [rbp+37h+var_70], rax
0x1800653c1  lea     rcx, Microsoft_Windows_MediaFoundation_Performance_Context
0x1800653c8  lea     rax, [rbp+37h+arg_18]
0x1800653cc  mov     [rbp+37h+var_58], 4
0x1800653d4  mov     [rbp+37h+var_60], rax
0x1800653d8  mov     r9d, 7
0x1800653de  lea     rax, [rbp+37h+arg_20]
0x1800653e2  mov     [rbp+37h+var_48], 4
0x1800653ea  mov     [rbp+37h+var_50], rax
0x1800653ee  lea     rax, [rbp+37h+arg_28]
0x1800653f2  mov     [rbp+37h+var_40], rax
0x1800653f6  lea     rax, [rbp+37h+arg_30]
0x1800653fa  mov     [rbp+37h+var_30], rax
0x1800653fe  lea     rax, [rbp+37h+arg_38]
0x180065402  mov     [rbp+37h+var_20], rax
0x180065406  lea     rax, [rbp+37h+var_80]
0x18006540a  mov     [rsp+0B0h+var_90], rax
0x18006540f  mov     [rbp+37h+var_38], 4
0x180065417  mov     [rbp+37h+var_28], 4
0x18006541f  mov     [rbp+37h+var_18], 4
0x180065427  call    McGenEventWrite_EventWriteTransfer
0x18006542c  mov     rcx, [rbp+37h+var_10]
0x180065430  xor     rcx, rsp; StackCookie
0x180065433  call    __security_check_cookie
0x180065438  add     rsp, 0B0h
0x18006543f  pop     rbp
0x180065440  retn
```
