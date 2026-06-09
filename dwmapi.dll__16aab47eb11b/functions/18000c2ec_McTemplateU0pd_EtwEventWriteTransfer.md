# McTemplateU0pd_EtwEventWriteTransfer

- ea: `0x18000c2ec`
- end: `0x18000c356`
- name: `McTemplateU0pd_EtwEventWriteTransfer`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008fe0`
- `0x180014bc0`

## callees

- `0x180004594`
- `0x18000d0a0`

## pseudocode

```c
__int64 __fastcall McTemplateU0pd_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  _QWORD v5[6]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v6; // [rsp+90h] [rbp+18h] BYREF
  int v7; // [rsp+98h] [rbp+20h] BYREF

  v7 = a4;
  v6 = a3;
  v5[3] = 8;
  v5[2] = &v6;
  v5[5] = 4;
  v5[4] = &v7;
  return McGenEventWrite_EtwEventWriteTransfer(Microsoft_Windows_Dwm_Api_Provider_Context, a2, a3, 3, (__int64)v5);
}

```

## disassembly

```asm
0x18000c2ec  mov     r11, rsp
0x18000c2ef  mov     [r11+20h], r9d
0x18000c2f3  mov     [r11+18h], r8
0x18000c2f7  sub     rsp, 78h
0x18000c2fb  mov     rax, cs:__security_cookie
0x18000c302  xor     rax, rsp
0x18000c305  mov     [rsp+78h+var_18], rax
0x18000c30a  lea     rax, [r11+18h]
0x18000c30e  mov     qword ptr [r11-30h], 8
0x18000c316  mov     [r11-38h], rax
0x18000c31a  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x18000c321  lea     rax, [r11+20h]
0x18000c325  mov     qword ptr [r11-20h], 4
0x18000c32d  mov     [r11-28h], rax
0x18000c331  mov     r9d, 3
0x18000c337  lea     rax, [r11-48h]
0x18000c33b  mov     [r11-58h], rax
0x18000c33f  call    McGenEventWrite_EtwEventWriteTransfer
0x18000c344  mov     rcx, [rsp+78h+var_18]
0x18000c349  xor     rcx, rsp; StackCookie
0x18000c34c  call    __security_check_cookie
0x18000c351  add     rsp, 78h
0x18000c355  retn
```
