# McTemplateU0qqqq_EtwEventWriteTransfer

- ea: `0x180001894`
- end: `0x180001929`
- name: `McTemplateU0qqqq_EtwEventWriteTransfer`
- size: `149`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180013580`
- `0x180013840`
- `0x18001f3ac`

## callees

- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0qqqq_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, char a5, char a6)
{
  _BYTE v7[16]; // [rsp+38h] [rbp-19h] BYREF
  int *v8; // [rsp+48h] [rbp-9h]
  __int64 v9; // [rsp+50h] [rbp-1h]
  int *v10; // [rsp+58h] [rbp+7h]
  __int64 v11; // [rsp+60h] [rbp+Fh]
  char *v12; // [rsp+68h] [rbp+17h]
  __int64 v13; // [rsp+70h] [rbp+1Fh]
  char *v14; // [rsp+78h] [rbp+27h]
  __int64 v15; // [rsp+80h] [rbp+2Fh]
  int v16; // [rsp+B8h] [rbp+67h] BYREF
  int v17; // [rsp+C0h] [rbp+6Fh] BYREF

  v17 = a4;
  v16 = a3;
  v9 = 4;
  v8 = &v16;
  v11 = 4;
  v10 = &v17;
  v13 = 4;
  v12 = &a5;
  v14 = &a6;
  v15 = 4;
  return McGenEventWrite_EtwEventWriteTransfer(&Dhcpv6_Context, a2, a3, 5, (__int64)v7);
}

```

## disassembly

```asm
0x180001894  mov     r11, rsp
0x180001897  mov     [r11+20h], r9d
0x18000189b  mov     [r11+18h], r8d
0x18000189f  push    rbp
0x1800018a0  lea     rbp, [r11-4Fh]
0x1800018a4  sub     rsp, 90h
0x1800018ab  mov     rax, cs:__security_cookie
0x1800018b2  xor     rax, rsp
0x1800018b5  mov     [rbp+47h+var_10], rax
0x1800018b9  lea     rax, [rbp+47h+arg_10]
0x1800018bd  mov     [rbp+47h+var_48], 4
0x1800018c5  mov     [rbp+47h+var_50], rax
0x1800018c9  lea     rcx, Dhcpv6_Context
0x1800018d0  lea     rax, [rbp+47h+arg_18]
0x1800018d4  mov     [rbp+47h+var_38], 4
0x1800018dc  mov     [rbp+47h+var_40], rax
0x1800018e0  mov     r9d, 5
0x1800018e6  lea     rax, [rbp+47h+arg_20]
0x1800018ea  mov     [rbp+47h+var_28], 4
0x1800018f2  mov     [rbp+47h+var_30], rax
0x1800018f6  lea     rax, [rbp+47h+arg_28]
0x1800018fa  mov     [rbp+47h+var_20], rax
0x1800018fe  lea     rax, [rbp+47h+var_60]
0x180001902  mov     [r11-78h], rax
0x180001906  mov     [rbp+47h+var_18], 4
0x18000190e  call    McGenEventWrite_EtwEventWriteTransfer
0x180001913  mov     rcx, [rbp+47h+var_10]
0x180001917  xor     rcx, rsp; StackCookie
0x18000191a  call    __security_check_cookie
0x18000191f  add     rsp, 90h
0x180001926  pop     rbp
0x180001927  retn
```
