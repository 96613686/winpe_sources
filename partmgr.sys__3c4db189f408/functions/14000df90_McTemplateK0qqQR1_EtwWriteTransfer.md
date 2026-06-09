# McTemplateK0qqQR1_EtwWriteTransfer

- ea: `0x14000df90`
- end: `0x14000e010`
- name: `McTemplateK0qqQR1_EtwWriteTransfer`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140026f44`

## callees

- `0x140004300`
- `0x140010f20`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qqQR1_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, int a5, __int64 a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-50h] BYREF
  int *v8; // [rsp+40h] [rbp-40h]
  __int64 v9; // [rsp+48h] [rbp-38h]
  int *v10; // [rsp+50h] [rbp-30h]
  __int64 v11; // [rsp+58h] [rbp-28h]
  __int64 v12; // [rsp+60h] [rbp-20h]
  int v13; // [rsp+68h] [rbp-18h]
  int v14; // [rsp+6Ch] [rbp-14h]
  int v15; // [rsp+A8h] [rbp+28h] BYREF

  v15 = a4;
  v8 = &v15;
  v9 = 4;
  v10 = &a5;
  v12 = a6;
  v13 = 4 * a5;
  v11 = 4;
  v14 = 0;
  return McGenEventWrite_EtwWriteTransfer(0, (const EVENT_DESCRIPTOR *)PartitionHidden, 0, 4u, &v7);
}

```

## disassembly

```asm
0x14000df90  mov     [rsp-8+arg_18], r9d
0x14000df95  push    rbp
0x14000df96  mov     rbp, rsp
0x14000df99  sub     rsp, 80h
0x14000dfa0  mov     rax, cs:__security_cookie
0x14000dfa7  xor     rax, rsp
0x14000dfaa  mov     [rbp+var_10], rax
0x14000dfae  mov     r9d, 4
0x14000dfb4  lea     rax, [rbp+arg_18]
0x14000dfb8  mov     [rbp+var_40], rax
0x14000dfbc  lea     rdx, PartitionHidden
0x14000dfc3  lea     rax, [rbp+arg_20]
0x14000dfc7  mov     [rbp+var_38], r9
0x14000dfcb  mov     [rbp+var_30], rax
0x14000dfcf  xor     ecx, ecx
0x14000dfd1  mov     rax, [rbp+arg_28]
0x14000dfd5  xor     r8d, r8d
0x14000dfd8  mov     [rbp+var_20], rax
0x14000dfdc  mov     eax, [rbp+arg_20]
0x14000dfdf  shl     eax, 2
0x14000dfe2  mov     [rbp+var_18], eax
0x14000dfe5  lea     rax, [rbp+var_50]
0x14000dfe9  mov     [rsp+80h+var_60], rax
0x14000dfee  mov     [rbp+var_28], r9
0x14000dff2  mov     [rbp+var_14], ecx
0x14000dff5  call    McGenEventWrite_EtwWriteTransfer
0x14000dffa  mov     rcx, [rbp+var_10]
0x14000dffe  xor     rcx, rsp; StackCookie
0x14000e001  call    __security_check_cookie
0x14000e006  add     rsp, 80h
0x14000e00d  pop     rbp
0x14000e00e  retn
```
