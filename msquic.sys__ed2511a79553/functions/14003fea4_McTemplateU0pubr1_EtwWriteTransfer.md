# McTemplateU0pubr1_EtwWriteTransfer

- ea: `0x14003fea4`
- end: `0x14003ff23`
- name: `McTemplateU0pubr1_EtwWriteTransfer`
- size: `127`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140001d6c`
- `0x140003520`
- `0x140003fac`
- `0x140007b30`
- `0x140013200`
- `0x14002a180`
- `0x14002a694`
- `0x1400436c8`

## callees

- `0x14003c8e0`
- `0x14003e8c4`

## pseudocode

```c
NTSTATUS __fastcall McTemplateU0pubr1_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        unsigned __int8 a4,
        __int64 a5)
{
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v7; // [rsp+40h] [rbp-40h]
  __int64 v8; // [rsp+48h] [rbp-38h]
  char *v9; // [rsp+50h] [rbp-30h]
  __int64 v10; // [rsp+58h] [rbp-28h]
  __int64 v11; // [rsp+60h] [rbp-20h]
  int v12; // [rsp+68h] [rbp-18h]
  int v13; // [rsp+6Ch] [rbp-14h]
  __int64 v14; // [rsp+A0h] [rbp+20h] BYREF
  unsigned __int8 v15; // [rsp+A8h] [rbp+28h] BYREF

  v15 = a4;
  v14 = a3;
  v8 = 8;
  v10 = 1;
  v7 = &v14;
  v9 = (char *)&v15;
  v11 = a5;
  v12 = a4;
  v13 = 0;
  return McGenEventWrite_EtwWriteTransfer(0, a2, a3, 4u, &v6);
}

```

## disassembly

```asm
0x14003fea4  mov     [rsp-8+arg_18], r9b
0x14003fea9  mov     [rsp-8+arg_10], r8
0x14003feae  push    rbp
0x14003feaf  mov     rbp, rsp
0x14003feb2  sub     rsp, 80h
0x14003feb9  mov     rax, cs:__security_cookie
0x14003fec0  xor     rax, rsp
0x14003fec3  mov     [rbp+var_10], rax
0x14003fec7  xor     ecx, ecx
0x14003fec9  mov     [rbp+var_38], 8
0x14003fed1  lea     rax, [rbp+arg_10]
0x14003fed5  mov     [rbp+var_28], 1
0x14003fedd  mov     [rbp+var_40], rax
0x14003fee1  lea     rax, [rbp+arg_18]
0x14003fee5  mov     [rbp+var_30], rax
0x14003fee9  mov     rax, [rbp+arg_20]
0x14003feed  mov     [rbp+var_20], rax
0x14003fef1  movzx   eax, r9b
0x14003fef5  lea     r9d, [rcx+4]
0x14003fef9  mov     [rbp+var_18], eax
0x14003fefc  lea     rax, [rbp+var_50]
0x14003ff00  mov     [rsp+80h+var_60], rax
0x14003ff05  mov     [rbp+var_14], ecx
0x14003ff08  call    McGenEventWrite_EtwWriteTransfer
0x14003ff0d  mov     rcx, [rbp+var_10]
0x14003ff11  xor     rcx, rsp; StackCookie
0x14003ff14  call    __security_check_cookie
0x14003ff19  add     rsp, 80h
0x14003ff20  pop     rbp
0x14003ff21  retn
```
