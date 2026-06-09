# McTemplateU0b16qq_EtwEventWriteTransfer

- ea: `0x1800016e0`
- end: `0x180001753`
- name: `McTemplateU0b16qq_EtwEventWriteTransfer`
- size: `115`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001189c`
- `0x18001225c`

## callees

- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0b16qq_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, char a5)
{
  _BYTE v6[16]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v7; // [rsp+40h] [rbp-40h]
  __int64 v8; // [rsp+48h] [rbp-38h]
  int *v9; // [rsp+50h] [rbp-30h]
  __int64 v10; // [rsp+58h] [rbp-28h]
  char *v11; // [rsp+60h] [rbp-20h]
  __int64 v12; // [rsp+68h] [rbp-18h]
  int v13; // [rsp+A8h] [rbp+28h] BYREF

  v13 = a4;
  v7 = a3;
  v8 = 16;
  v9 = &v13;
  v10 = 4;
  v11 = &a5;
  v12 = 4;
  return McGenEventWrite_EtwEventWriteTransfer(&Dhcpv6_Context, a2, a3, 4, (__int64)v6);
}

```

## disassembly

```asm
0x1800016e0  mov     [rsp-8+arg_18], r9d
0x1800016e5  push    rbp
0x1800016e6  mov     rbp, rsp
0x1800016e9  sub     rsp, 80h
0x1800016f0  mov     rax, cs:__security_cookie
0x1800016f7  xor     rax, rsp
0x1800016fa  mov     [rbp+var_10], rax
0x1800016fe  mov     r9d, 4
0x180001704  mov     [rbp+var_40], r8
0x180001708  lea     rax, [rbp+arg_18]
0x18000170c  mov     [rbp+var_38], 10h
0x180001714  mov     [rbp+var_30], rax
0x180001718  lea     rcx, Dhcpv6_Context
0x18000171f  lea     rax, [rbp+arg_20]
0x180001723  mov     [rbp+var_28], r9
0x180001727  mov     [rbp+var_20], rax
0x18000172b  lea     rax, [rbp+var_50]
0x18000172f  mov     [rsp+80h+var_60], rax
0x180001734  mov     [rbp+var_18], r9
0x180001738  call    McGenEventWrite_EtwEventWriteTransfer
0x18000173d  mov     rcx, [rbp+var_10]
0x180001741  xor     rcx, rsp; StackCookie
0x180001744  call    __security_check_cookie
0x180001749  add     rsp, 80h
0x180001750  pop     rbp
0x180001751  retn
```
