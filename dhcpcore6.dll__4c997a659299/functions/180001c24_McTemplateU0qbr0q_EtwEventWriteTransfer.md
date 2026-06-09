# McTemplateU0qbr0q_EtwEventWriteTransfer

- ea: `0x180001c24`
- end: `0x180001c9b`
- name: `McTemplateU0qbr0q_EtwEventWriteTransfer`
- size: `119`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180014070`
- `0x180014590`
- `0x180020d50`
- `0x180021150`
- `0x1800225c8`

## callees

- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0qbr0q_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  _BYTE v6[16]; // [rsp+30h] [rbp-50h] BYREF
  int *v7; // [rsp+40h] [rbp-40h]
  __int64 v8; // [rsp+48h] [rbp-38h]
  __int64 v9; // [rsp+50h] [rbp-30h]
  int v10; // [rsp+58h] [rbp-28h]
  int v11; // [rsp+5Ch] [rbp-24h]
  char *v12; // [rsp+60h] [rbp-20h]
  __int64 v13; // [rsp+68h] [rbp-18h]
  int v14; // [rsp+A0h] [rbp+20h] BYREF

  v14 = a3;
  v9 = a4;
  v8 = 4;
  v11 = 0;
  v7 = &v14;
  v10 = a3;
  v12 = &a5;
  v13 = 4;
  return McGenEventWrite_EtwEventWriteTransfer(&Dhcpv6_Context, a2, a3, 4, (__int64)v6);
}

```

## disassembly

```asm
0x180001c24  mov     [rsp-8+arg_10], r8d
0x180001c29  push    rbp
0x180001c2a  mov     rbp, rsp
0x180001c2d  sub     rsp, 80h
0x180001c34  mov     rax, cs:__security_cookie
0x180001c3b  xor     rax, rsp
0x180001c3e  mov     [rbp+var_10], rax
0x180001c42  mov     r10d, 4
0x180001c48  mov     [rbp+var_30], r9
0x180001c4c  xor     ecx, ecx
0x180001c4e  mov     [rbp+var_38], r10
0x180001c52  lea     rax, [rbp+arg_10]
0x180001c56  mov     [rbp+var_24], ecx
0x180001c59  mov     [rbp+var_40], rax
0x180001c5d  lea     rcx, Dhcpv6_Context
0x180001c64  lea     rax, [rbp+arg_20]
0x180001c68  mov     [rbp+var_28], r8d
0x180001c6c  mov     [rbp+var_20], rax
0x180001c70  mov     r9d, r10d
0x180001c73  lea     rax, [rbp+var_50]
0x180001c77  mov     [rbp+var_18], r10
0x180001c7b  mov     [rsp+80h+var_60], rax
0x180001c80  call    McGenEventWrite_EtwEventWriteTransfer
0x180001c85  mov     rcx, [rbp+var_10]
0x180001c89  xor     rcx, rsp; StackCookie
0x180001c8c  call    __security_check_cookie
0x180001c91  add     rsp, 80h
0x180001c98  pop     rbp
0x180001c99  retn
```
