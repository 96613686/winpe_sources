# McTemplateU0qqb16_EtwEventWriteTransfer

- ea: `0x180001930`
- end: `0x1800019ac`
- name: `McTemplateU0qqb16_EtwEventWriteTransfer`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002458c`
- `0x180025094`

## callees

- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0qqb16_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  _BYTE v6[16]; // [rsp+30h] [rbp-50h] BYREF
  int *v7; // [rsp+40h] [rbp-40h]
  __int64 v8; // [rsp+48h] [rbp-38h]
  int *v9; // [rsp+50h] [rbp-30h]
  __int64 v10; // [rsp+58h] [rbp-28h]
  __int64 v11; // [rsp+60h] [rbp-20h]
  __int64 v12; // [rsp+68h] [rbp-18h]
  int v13; // [rsp+A0h] [rbp+20h] BYREF
  int v14; // [rsp+A8h] [rbp+28h] BYREF

  v14 = a4;
  v13 = a3;
  v12 = 16;
  v8 = 4;
  v7 = &v13;
  v10 = 4;
  v9 = &v14;
  v11 = a5;
  return McGenEventWrite_EtwEventWriteTransfer(&Dhcpv6_Context, a2, a3, 4, (__int64)v6);
}

```

## disassembly

```asm
0x180001930  mov     [rsp-8+arg_18], r9d
0x180001935  mov     [rsp-8+arg_10], r8d
0x18000193a  push    rbp
0x18000193b  mov     rbp, rsp
0x18000193e  sub     rsp, 80h
0x180001945  mov     rax, cs:__security_cookie
0x18000194c  xor     rax, rsp
0x18000194f  mov     [rbp+var_10], rax
0x180001953  mov     r9d, 4
0x180001959  mov     [rbp+var_18], 10h
0x180001961  lea     rax, [rbp+arg_10]
0x180001965  mov     [rbp+var_38], r9
0x180001969  mov     [rbp+var_40], rax
0x18000196d  lea     rcx, Dhcpv6_Context
0x180001974  lea     rax, [rbp+arg_18]
0x180001978  mov     [rbp+var_28], r9
0x18000197c  mov     [rbp+var_30], rax
0x180001980  mov     rax, [rbp+arg_20]
0x180001984  mov     [rbp+var_20], rax
0x180001988  lea     rax, [rbp+var_50]
0x18000198c  mov     [rsp+80h+var_60], rax
0x180001991  call    McGenEventWrite_EtwEventWriteTransfer
0x180001996  mov     rcx, [rbp+var_10]
0x18000199a  xor     rcx, rsp; StackCookie
0x18000199d  call    __security_check_cookie
0x1800019a2  add     rsp, 80h
0x1800019a9  pop     rbp
0x1800019aa  retn
```
