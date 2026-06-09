# McTemplateU0b16_EtwEventWriteTransfer

- ea: `0x180018524`
- end: `0x18001857a`
- name: `McTemplateU0b16_EtwEventWriteTransfer`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012634`

## callees

- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0b16_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD v4[4]; // [rsp+30h] [rbp-38h] BYREF

  v4[2] = a3;
  v4[3] = 16;
  return McGenEventWrite_EtwEventWriteTransfer(&Dhcpv6_Context, (__int64)DeletedIpv6Address, a3, 2, (__int64)v4);
}

```

## disassembly

```asm
0x180018524  mov     r11, rsp
0x180018527  sub     rsp, 68h
0x18001852b  mov     rax, cs:__security_cookie
0x180018532  xor     rax, rsp
0x180018535  mov     [rsp+68h+var_18], rax
0x18001853a  lea     rax, [r11-38h]
0x18001853e  mov     [r11-28h], r8
0x180018542  mov     r9d, 2
0x180018548  mov     [r11-48h], rax
0x18001854c  lea     rdx, DeletedIpv6Address
0x180018553  mov     qword ptr [r11-20h], 10h
0x18001855b  lea     rcx, Dhcpv6_Context
0x180018562  call    McGenEventWrite_EtwEventWriteTransfer
0x180018567  mov     rcx, [rsp+68h+var_18]
0x18001856c  xor     rcx, rsp; StackCookie
0x18001856f  call    __security_check_cookie
0x180018574  add     rsp, 68h
0x180018578  retn
```
