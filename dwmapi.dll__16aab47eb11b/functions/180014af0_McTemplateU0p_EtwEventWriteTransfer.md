# McTemplateU0p_EtwEventWriteTransfer

- ea: `0x180014af0`
- end: `0x180014b46`
- name: `McTemplateU0p_EtwEventWriteTransfer`
- size: `86`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001570`
- `0x180013ca0`
- `0x180013ed0`
- `0x1800143c0`
- `0x1800148b0`

## callees

- `0x180004594`
- `0x18000d0a0`

## pseudocode

```c
__int64 __fastcall McTemplateU0p_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD v4[4]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v5; // [rsp+80h] [rbp+18h] BYREF

  v5 = a3;
  v4[3] = 8;
  v4[2] = &v5;
  return McGenEventWrite_EtwEventWriteTransfer(Microsoft_Windows_Dwm_Api_Provider_Context, a2, a3, 2, (__int64)v4);
}

```

## disassembly

```asm
0x180014af0  mov     r11, rsp
0x180014af3  mov     [r11+18h], r8
0x180014af7  sub     rsp, 68h
0x180014afb  mov     rax, cs:__security_cookie
0x180014b02  xor     rax, rsp
0x180014b05  mov     [rsp+68h+var_18], rax
0x180014b0a  lea     rax, [r11+18h]
0x180014b0e  mov     qword ptr [r11-20h], 8
0x180014b16  mov     [r11-28h], rax
0x180014b1a  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180014b21  lea     rax, [r11-38h]
0x180014b25  mov     r9d, 2
0x180014b2b  mov     [r11-48h], rax
0x180014b2f  call    McGenEventWrite_EtwEventWriteTransfer
0x180014b34  mov     rcx, [rsp+68h+var_18]
0x180014b39  xor     rcx, rsp; StackCookie
0x180014b3c  call    __security_check_cookie
0x180014b41  add     rsp, 68h
0x180014b45  retn
```
