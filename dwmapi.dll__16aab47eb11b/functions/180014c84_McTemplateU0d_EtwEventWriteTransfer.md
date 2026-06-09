# McTemplateU0d_EtwEventWriteTransfer

- ea: `0x180014c84`
- end: `0x180014cda`
- name: `McTemplateU0d_EtwEventWriteTransfer`
- size: `86`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009690`
- `0x180009f50`

## callees

- `0x180004594`
- `0x18000d0a0`

## pseudocode

```c
__int64 __fastcall McTemplateU0d_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD v4[4]; // [rsp+30h] [rbp-38h] BYREF
  int v5; // [rsp+80h] [rbp+18h] BYREF

  v5 = a3;
  v4[3] = 4;
  v4[2] = &v5;
  return McGenEventWrite_EtwEventWriteTransfer(Microsoft_Windows_Dwm_Api_Provider_Context, a2, a3, 2, (__int64)v4);
}

```

## disassembly

```asm
0x180014c84  mov     r11, rsp
0x180014c87  mov     [r11+18h], r8d
0x180014c8b  sub     rsp, 68h
0x180014c8f  mov     rax, cs:__security_cookie
0x180014c96  xor     rax, rsp
0x180014c99  mov     [rsp+68h+var_18], rax
0x180014c9e  lea     rax, [r11+18h]
0x180014ca2  mov     qword ptr [r11-20h], 4
0x180014caa  mov     [r11-28h], rax
0x180014cae  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180014cb5  lea     rax, [r11-38h]
0x180014cb9  mov     r9d, 2
0x180014cbf  mov     [r11-48h], rax
0x180014cc3  call    McGenEventWrite_EtwEventWriteTransfer
0x180014cc8  mov     rcx, [rsp+68h+var_18]
0x180014ccd  xor     rcx, rsp; StackCookie
0x180014cd0  call    __security_check_cookie
0x180014cd5  add     rsp, 68h
0x180014cd9  retn
```
