# McTemplateU0qqqqqqq_EventWriteTransfer

- ea: `0x18002b7cc`
- end: `0x18002b88b`
- name: `McTemplateU0qqqqqqq_EventWriteTransfer`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002a838`

## callees

- `0x18001ada8`
- `0x180031040`

## pseudocode

```c
ULONG __fastcall McTemplateU0qqqqqqq_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9)
{
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-61h] BYREF
  int *v11; // [rsp+40h] [rbp-51h]
  __int64 v12; // [rsp+48h] [rbp-49h]
  int *v13; // [rsp+50h] [rbp-41h]
  __int64 v14; // [rsp+58h] [rbp-39h]
  char *v15; // [rsp+60h] [rbp-31h]
  __int64 v16; // [rsp+68h] [rbp-29h]
  char *v17; // [rsp+70h] [rbp-21h]
  __int64 v18; // [rsp+78h] [rbp-19h]
  char *v19; // [rsp+80h] [rbp-11h]
  __int64 v20; // [rsp+88h] [rbp-9h]
  char *v21; // [rsp+90h] [rbp-1h]
  __int64 v22; // [rsp+98h] [rbp+7h]
  char *v23; // [rsp+A0h] [rbp+Fh]
  __int64 v24; // [rsp+A8h] [rbp+17h]
  int v25; // [rsp+E0h] [rbp+4Fh] BYREF
  int v26; // [rsp+E8h] [rbp+57h] BYREF

  v26 = a4;
  v25 = a3;
  v12 = 4;
  v11 = &v25;
  v14 = 4;
  v13 = &v26;
  v15 = &a5;
  v17 = &a6;
  v19 = &a7;
  v21 = &a8;
  v23 = &a9;
  v16 = 4;
  v18 = 4;
  v20 = 4;
  v22 = 4;
  v24 = 4;
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 8u, &v10);
}

```

## disassembly

```asm
0x18002b7cc  mov     [rsp-8+arg_18], r9d
0x18002b7d1  mov     [rsp-8+arg_10], r8d
0x18002b7d6  push    rbp
0x18002b7d7  lea     rbp, [rsp-2Fh]
0x18002b7dc  sub     rsp, 0C0h
0x18002b7e3  mov     rax, cs:__security_cookie
0x18002b7ea  xor     rax, rsp
0x18002b7ed  mov     [rbp+2Fh+var_10], rax
0x18002b7f1  lea     rax, [rbp+2Fh+arg_10]
0x18002b7f5  mov     [rbp+2Fh+var_78], 4
0x18002b7fd  mov     [rbp+2Fh+var_80], rax
0x18002b801  mov     r9d, 8
0x18002b807  lea     rax, [rbp+2Fh+arg_18]
0x18002b80b  mov     [rbp+2Fh+var_68], 4
0x18002b813  mov     [rbp+2Fh+var_70], rax
0x18002b817  lea     rax, [rbp+2Fh+arg_20]
0x18002b81b  mov     [rbp+2Fh+var_60], rax
0x18002b81f  lea     rax, [rbp+2Fh+arg_28]
0x18002b823  mov     [rbp+2Fh+var_50], rax
0x18002b827  lea     rax, [rbp+2Fh+arg_30]
0x18002b82b  mov     [rbp+2Fh+var_40], rax
0x18002b82f  lea     rax, [rbp+2Fh+arg_38]
0x18002b833  mov     [rbp+2Fh+var_30], rax
0x18002b837  lea     rax, [rbp+2Fh+arg_40]
0x18002b83b  mov     [rbp+2Fh+var_20], rax
0x18002b83f  lea     rax, [rbp+2Fh+var_90]
0x18002b843  mov     [rsp+0C0h+var_A0], rax
0x18002b848  mov     [rbp+2Fh+var_58], 4
0x18002b850  mov     [rbp+2Fh+var_48], 4
0x18002b858  mov     [rbp+2Fh+var_38], 4
0x18002b860  mov     [rbp+2Fh+var_28], 4
0x18002b868  mov     [rbp+2Fh+var_18], 4
0x18002b870  call    McGenEventWrite_EventWriteTransfer
0x18002b875  mov     rcx, [rbp+2Fh+var_10]
0x18002b879  xor     rcx, rsp; StackCookie
0x18002b87c  call    __security_check_cookie
0x18002b881  add     rsp, 0C0h
0x18002b888  pop     rbp
0x18002b889  retn
```
