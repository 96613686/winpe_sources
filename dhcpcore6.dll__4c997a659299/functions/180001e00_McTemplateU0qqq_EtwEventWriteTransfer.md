# McTemplateU0qqq_EtwEventWriteTransfer

- ea: `0x180001e00`
- end: `0x180001e71`
- name: `McTemplateU0qqq_EtwEventWriteTransfer`
- size: `113`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d6ac`
- `0x180010fd4`
- `0x180014590`
- `0x18001f3ac`
- `0x18002e6d4`

## callees

- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0qqq_EtwEventWriteTransfer(_QWORD *a1, __int64 a2, __int64 a3, int a4, char a5)
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
0x180001e00  mov     [rsp-8+arg_18], r9d
0x180001e05  mov     [rsp-8+arg_10], r8d
0x180001e0a  push    rbp
0x180001e0b  mov     rbp, rsp
0x180001e0e  sub     rsp, 80h
0x180001e15  mov     rax, cs:__security_cookie
0x180001e1c  xor     rax, rsp
0x180001e1f  mov     [rbp+var_10], rax
0x180001e23  mov     r9d, 4
0x180001e29  lea     rax, [rbp+arg_10]
0x180001e2d  mov     [rbp+var_40], rax
0x180001e31  lea     rax, [rbp+arg_18]
0x180001e35  mov     [rbp+var_30], rax
0x180001e39  lea     rax, [rbp+arg_20]
0x180001e3d  mov     [rbp+var_20], rax
0x180001e41  lea     rax, [rbp+var_50]
0x180001e45  mov     [rsp+80h+var_60], rax
0x180001e4a  mov     [rbp+var_38], r9
0x180001e4e  mov     [rbp+var_28], r9
0x180001e52  mov     [rbp+var_18], r9
0x180001e56  call    McGenEventWrite_EtwEventWriteTransfer
0x180001e5b  mov     rcx, [rbp+var_10]
0x180001e5f  xor     rcx, rsp; StackCookie
0x180001e62  call    __security_check_cookie
0x180001e67  add     rsp, 80h
0x180001e6e  pop     rbp
0x180001e6f  retn
```
