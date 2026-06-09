# McTemplateU0qqq_EtwEventWriteTransfer

- ea: `0x18001d108`
- end: `0x18001d178`
- name: `McTemplateU0qqq_EtwEventWriteTransfer`
- size: `112`
- prototype: ``
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ac0`
- `0x180002020`
- `0x180002470`
- `0x180002a30`
- `0x1800067e0`
- `0x180008d40`
- `0x1800129b0`
- `0x180017f70`
- `0x180019910`
- `0x18001d208`
- `0x180026b04`
- `0x180026e54`
- `0x180027158`
- `0x180027494`
- `0x180029668`
- `0x18002b968`

## callees

- `0x1800053e0`
- `0x180020250`

## pseudocode

```c
__int64 __fastcall McTemplateU0qqq_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, char a5)
{
  _BYTE v6[16]; // [rsp+30h] [rbp-50h] BYREF
  int *v7; // [rsp+40h] [rbp-40h]
  __int64 v8; // [rsp+48h] [rbp-38h]
  int *v9; // [rsp+50h] [rbp-30h]
  __int64 v10; // [rsp+58h] [rbp-28h]
  char *v11; // [rsp+60h] [rbp-20h]
  __int64 v12; // [rsp+68h] [rbp-18h]
  int v13; // [rsp+A0h] [rbp+20h] BYREF
  int v14; // [rsp+A8h] [rbp+28h] BYREF

  v14 = a4;
  v13 = a3;
  v7 = &v13;
  v9 = &v14;
  v11 = &a5;
  v8 = 4;
  v10 = 4;
  v12 = 4;
  return McGenEventWrite_EtwEventWriteTransfer(a1, a2, a3, 4, (__int64)v6);
}

```

## disassembly

```asm
0x18001d108  mov     [rsp-8+arg_18], r9d
0x18001d10d  mov     [rsp-8+arg_10], r8d
0x18001d112  push    rbp
0x18001d113  mov     rbp, rsp
0x18001d116  sub     rsp, 80h
0x18001d11d  mov     rax, cs:__security_cookie
0x18001d124  xor     rax, rsp
0x18001d127  mov     [rbp+var_10], rax
0x18001d12b  mov     r9d, 4
0x18001d131  lea     rax, [rbp+arg_10]
0x18001d135  mov     [rbp+var_40], rax
0x18001d139  lea     rax, [rbp+arg_18]
0x18001d13d  mov     [rbp+var_30], rax
0x18001d141  lea     rax, [rbp+arg_20]
0x18001d145  mov     [rbp+var_20], rax
0x18001d149  lea     rax, [rbp+var_50]
0x18001d14d  mov     [rsp+80h+var_60], rax
0x18001d152  mov     [rbp+var_38], r9
0x18001d156  mov     [rbp+var_28], r9
0x18001d15a  mov     [rbp+var_18], r9
0x18001d15e  call    McGenEventWrite_EtwEventWriteTransfer
0x18001d163  mov     rcx, [rbp+var_10]
0x18001d167  xor     rcx, rsp; StackCookie
0x18001d16a  call    __security_check_cookie
0x18001d16f  add     rsp, 80h
0x18001d176  pop     rbp
0x18001d177  retn
```
