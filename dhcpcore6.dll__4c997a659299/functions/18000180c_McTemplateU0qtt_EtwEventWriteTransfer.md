# McTemplateU0qtt_EtwEventWriteTransfer

- ea: `0x18000180c`
- end: `0x18000188b`
- name: `McTemplateU0qtt_EtwEventWriteTransfer`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d340`

## callees

- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0qtt_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, char a5)
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
  v8 = 4;
  v9 = &v14;
  v10 = 4;
  v11 = &a5;
  v12 = 4;
  return McGenEventWrite_EtwEventWriteTransfer(&Dhcpv6_Context, (__int64)RAReceived, a3, 4, (__int64)v6);
}

```

## disassembly

```asm
0x18000180c  mov     [rsp-8+arg_18], r9d
0x180001811  mov     [rsp-8+arg_10], r8d
0x180001816  push    rbp
0x180001817  mov     rbp, rsp
0x18000181a  sub     rsp, 80h
0x180001821  mov     rax, cs:__security_cookie
0x180001828  xor     rax, rsp
0x18000182b  mov     [rbp+var_10], rax
0x18000182f  mov     r9d, 4
0x180001835  lea     rax, [rbp+arg_10]
0x180001839  mov     [rbp+var_40], rax
0x18000183d  lea     rdx, RAReceived
0x180001844  lea     rax, [rbp+arg_18]
0x180001848  mov     [rbp+var_38], r9
0x18000184c  mov     [rbp+var_30], rax
0x180001850  lea     rcx, Dhcpv6_Context
0x180001857  lea     rax, [rbp+arg_20]
0x18000185b  mov     [rbp+var_28], r9
0x18000185f  mov     [rbp+var_20], rax
0x180001863  lea     rax, [rbp+var_50]
0x180001867  mov     [rsp+80h+var_60], rax
0x18000186c  mov     [rbp+var_18], r9
0x180001870  call    McGenEventWrite_EtwEventWriteTransfer
0x180001875  mov     rcx, [rbp+var_10]
0x180001879  xor     rcx, rsp; StackCookie
0x18000187c  call    __security_check_cookie
0x180001881  add     rsp, 80h
0x180001888  pop     rbp
0x180001889  retn
```
