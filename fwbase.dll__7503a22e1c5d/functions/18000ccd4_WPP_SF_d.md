# WPP_SF_d

- ea: `0x18000ccd4`
- end: `0x18000cd27`
- name: `WPP_SF_d`
- size: `83`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `68`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001da0`
- `0x1800039f0`
- `0x180004e00`
- `0x180005590`
- `0x180006330`
- `0x180006d60`
- `0x180007040`
- `0x18000c0a0`
- `0x18000c25c`
- `0x18000c360`
- `0x18000c49c`
- `0x18000c720`
- `0x18000c880`
- `0x18000cbd0`
- `0x18000cd30`
- `0x18000cdf0`
- `0x18000d2cc`
- `0x18000d364`
- `0x18000d3fc`
- `0x18000d490`
- `0x18000f520`
- `0x18000fbc0`
- `0x18000fdc0`
- `0x180010d70`
- `0x180010f20`
- `0x1800113f4`
- `0x180012c00`
- `0x180012e60`
- `0x180013484`
- `0x180013690`
- `0x180013b60`
- `0x180014028`
- `0x180014200`
- `0x180014340`
- `0x180014b6c`
- `0x180014cb0`
- `0x1800150e0`
- `0x180016650`
- `0x1800169f0`
- `0x180017044`
- `0x180017718`
- `0x18001fa10`
- `0x18001fd70`
- `0x18002acb0`
- `0x18002b1a0`
- `0x18002c420`
- `0x18002c560`
- `0x18002c6a0`
- `0x18002c840`
- `0x18002c980`

## callees

- `0x18001e1d0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000cd0f`
- `ntdll!EtwTraceMessage` at `0x18000cd0f`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+40h] [rbp-18h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x18000ccd4  mov     r11, rsp
0x18000ccd7  sub     rsp, 58h
0x18000ccdb  mov     rax, cs:__security_cookie
0x18000cce2  xor     rax, rsp
0x18000cce5  mov     [rsp+58h+var_10], rax
0x18000ccea  mov     qword ptr [r11-28h], 0
0x18000ccf2  lea     rax, [r11-18h]
0x18000ccf6  mov     [r11-18h], r9d
0x18000ccfa  movzx   r9d, dx
0x18000ccfe  mov     edx, 2Bh ; '+'
0x18000cd03  mov     qword ptr [r11-30h], 4
0x18000cd0b  mov     [r11-38h], rax
0x18000cd0f  call    cs:__imp_EtwTraceMessage
0x18000cd15  mov     rcx, [rsp+58h+var_10]
0x18000cd1a  xor     rcx, rsp; StackCookie
0x18000cd1d  call    __security_check_cookie
0x18000cd22  add     rsp, 58h
0x18000cd26  retn
```
