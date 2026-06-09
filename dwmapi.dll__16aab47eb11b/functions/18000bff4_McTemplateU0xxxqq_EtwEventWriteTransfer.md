# McTemplateU0xxxqq_EtwEventWriteTransfer

- ea: `0x18000bff4`
- end: `0x18000c0a0`
- name: `McTemplateU0xxxqq_EtwEventWriteTransfer`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002200`

## callees

- `0x180004594`
- `0x18000d0a0`

## pseudocode

```c
__int64 McTemplateU0xxxqq_EtwEventWriteTransfer(__int64 a1, __int64 a2, ...)
{
  _BYTE v3[16]; // [rsp+30h] [rbp-31h] BYREF
  va_list v4; // [rsp+40h] [rbp-21h]
  __int64 v5; // [rsp+48h] [rbp-19h]
  va_list v6; // [rsp+50h] [rbp-11h]
  __int64 v7; // [rsp+58h] [rbp-9h]
  va_list v8; // [rsp+60h] [rbp-1h]
  __int64 v9; // [rsp+68h] [rbp+7h]
  va_list v10; // [rsp+70h] [rbp+Fh]
  __int64 v11; // [rsp+78h] [rbp+17h]
  va_list v12; // [rsp+80h] [rbp+1Fh]
  __int64 v13; // [rsp+88h] [rbp+27h]
  va_list va; // [rsp+C0h] [rbp+5Fh]
  __int64 v15; // [rsp+C0h] [rbp+5Fh] BYREF
  __int64 v16; // [rsp+C8h] [rbp+67h] BYREF
  va_list va1; // [rsp+C8h] [rbp+67h]
  __int64 v18; // [rsp+D0h] [rbp+6Fh] BYREF
  va_list va2; // [rsp+D0h] [rbp+6Fh]
  __int64 v20; // [rsp+D8h] [rbp+77h] BYREF
  va_list va3; // [rsp+D8h] [rbp+77h]
  va_list va4; // [rsp+E0h] [rbp+7Fh] BYREF

  va_start(va4, a2);
  va_start(va3, a2);
  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v15 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v16 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v18 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v20 = va_arg(va4, _QWORD);
  v5 = 8;
  va_copy(v4, va);
  v7 = 8;
  va_copy(v6, va1);
  v9 = 8;
  va_copy(v8, va2);
  v11 = 4;
  va_copy(v10, va3);
  va_copy(v12, va4);
  v13 = 4;
  return McGenEventWrite_EtwEventWriteTransfer(
           Microsoft_Windows_Dwm_Api_Provider_Context,
           (__int64)ApipDxGetWindowSharedSurface_Start,
           v15,
           6,
           (__int64)v3);
}

```

## disassembly

```asm
0x18000bff4  mov     [rsp-8+arg_18], r9
0x18000bff9  mov     [rsp-8+arg_10], r8
0x18000bffe  push    rbp
0x18000bfff  lea     rbp, [rsp-3Fh]
0x18000c004  sub     rsp, 0A0h
0x18000c00b  mov     rax, cs:__security_cookie
0x18000c012  xor     rax, rsp
0x18000c015  mov     [rbp+3Fh+var_10], rax
0x18000c019  lea     rax, [rbp+3Fh+arg_10]
0x18000c01d  mov     [rbp+3Fh+var_58], 8
0x18000c025  mov     [rbp+3Fh+var_60], rax
0x18000c029  lea     rdx, ApipDxGetWindowSharedSurface_Start
0x18000c030  lea     rax, [rbp+3Fh+arg_18]
0x18000c034  mov     [rbp+3Fh+var_48], 8
0x18000c03c  mov     [rbp+3Fh+var_50], rax
0x18000c040  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x18000c047  lea     rax, [rbp+3Fh+arg_20]
0x18000c04b  mov     [rbp+3Fh+var_38], 8
0x18000c053  mov     [rbp+3Fh+var_40], rax
0x18000c057  mov     r9d, 6
0x18000c05d  lea     rax, [rbp+3Fh+arg_28]
0x18000c061  mov     [rbp+3Fh+var_28], 4
0x18000c069  mov     [rbp+3Fh+var_30], rax
0x18000c06d  lea     rax, [rbp+3Fh+arg_30]
0x18000c071  mov     [rbp+3Fh+var_20], rax
0x18000c075  lea     rax, [rbp+3Fh+var_70]
0x18000c079  mov     [rsp+0A0h+var_80], rax
0x18000c07e  mov     [rbp+3Fh+var_18], 4
0x18000c086  call    McGenEventWrite_EtwEventWriteTransfer
0x18000c08b  mov     rcx, [rbp+3Fh+var_10]
0x18000c08f  xor     rcx, rsp; StackCookie
0x18000c092  call    __security_check_cookie
0x18000c097  add     rsp, 0A0h
0x18000c09e  pop     rbp
0x18000c09f  retn
```
