# McTemplateU0b16q_EtwEventWriteTransfer

- ea: `0x180001bb8`
- end: `0x180001c1b`
- name: `McTemplateU0b16q_EtwEventWriteTransfer`
- size: `99`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d340`
- `0x180010340`
- `0x1800108f0`
- `0x180012634`
- `0x1800132c0`
- `0x180013700`
- `0x18001e110`
- `0x18001f630`
- `0x180022b80`

## callees

- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0b16q_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  _QWORD v5[6]; // [rsp+30h] [rbp-48h] BYREF
  int v6; // [rsp+98h] [rbp+20h] BYREF

  v6 = a4;
  v5[2] = a3;
  v5[4] = &v6;
  v5[3] = 16;
  v5[5] = 4;
  return McGenEventWrite_EtwEventWriteTransfer(&Dhcpv6_Context, a2, a3, 3, (__int64)v5);
}

```

## disassembly

```asm
0x180001bb8  mov     r11, rsp
0x180001bbb  mov     [r11+20h], r9d
0x180001bbf  sub     rsp, 78h
0x180001bc3  mov     rax, cs:__security_cookie
0x180001bca  xor     rax, rsp
0x180001bcd  mov     [rsp+78h+var_18], rax
0x180001bd2  lea     rax, [r11+20h]
0x180001bd6  mov     [r11-38h], r8
0x180001bda  mov     [r11-28h], rax
0x180001bde  lea     rcx, Dhcpv6_Context
0x180001be5  lea     rax, [r11-48h]
0x180001be9  mov     qword ptr [r11-30h], 10h
0x180001bf1  mov     r9d, 3
0x180001bf7  mov     [r11-58h], rax
0x180001bfb  mov     qword ptr [r11-20h], 4
0x180001c03  call    McGenEventWrite_EtwEventWriteTransfer
0x180001c08  mov     rcx, [rsp+78h+var_18]
0x180001c0d  xor     rcx, rsp; StackCookie
0x180001c10  call    __security_check_cookie
0x180001c15  add     rsp, 78h
0x180001c19  retn
```
