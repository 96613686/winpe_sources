# McTemplateU0qp_EtwEventWriteTransfer

- ea: `0x180014b4c`
- end: `0x180014bb6`
- name: `McTemplateU0qp_EtwEventWriteTransfer`
- size: `106`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001570`
- `0x180013ca0`
- `0x180013ed0`
- `0x1800143c0`

## callees

- `0x180004594`
- `0x18000d0a0`

## pseudocode

```c
__int64 McTemplateU0qp_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, ...)
{
  _QWORD v4[6]; // [rsp+30h] [rbp-48h] BYREF
  int v5; // [rsp+90h] [rbp+18h] BYREF
  va_list va; // [rsp+98h] [rbp+20h] BYREF

  va_start(va, a3);
  v5 = a3;
  v4[3] = 4;
  v4[2] = &v5;
  v4[5] = 8;
  va_copy((va_list)&v4[4], va);
  return McGenEventWrite_EtwEventWriteTransfer(Microsoft_Windows_Dwm_Api_Provider_Context, a2, a3, 3, (__int64)v4);
}

```

## disassembly

```asm
0x180014b4c  mov     r11, rsp
0x180014b4f  mov     [r11+20h], r9
0x180014b53  mov     [r11+18h], r8d
0x180014b57  sub     rsp, 78h
0x180014b5b  mov     rax, cs:__security_cookie
0x180014b62  xor     rax, rsp
0x180014b65  mov     [rsp+78h+var_18], rax
0x180014b6a  lea     rax, [r11+18h]
0x180014b6e  mov     qword ptr [r11-30h], 4
0x180014b76  mov     [r11-38h], rax
0x180014b7a  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180014b81  lea     rax, [r11+20h]
0x180014b85  mov     qword ptr [r11-20h], 8
0x180014b8d  mov     [r11-28h], rax
0x180014b91  mov     r9d, 3
0x180014b97  lea     rax, [r11-48h]
0x180014b9b  mov     [r11-58h], rax
0x180014b9f  call    McGenEventWrite_EtwEventWriteTransfer
0x180014ba4  mov     rcx, [rsp+78h+var_18]
0x180014ba9  xor     rcx, rsp; StackCookie
0x180014bac  call    __security_check_cookie
0x180014bb1  add     rsp, 78h
0x180014bb5  retn
```
