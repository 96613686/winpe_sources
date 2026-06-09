# McTemplateU0q_EtwEventWriteTransfer

- ea: `0x180001ca4`
- end: `0x180001cfb`
- name: `McTemplateU0q_EtwEventWriteTransfer`
- size: `87`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x180008440`
- `0x180008a70`
- `0x18000c884`
- `0x18000d340`
- `0x18000d6ac`
- `0x180010340`
- `0x1800108f0`
- `0x1800128dc`
- `0x180012ee4`
- `0x180014070`
- `0x180014590`
- `0x18001b314`
- `0x18001be30`
- `0x18001cb0c`
- `0x18001e81c`
- `0x18001eac0`
- `0x18001ed84`
- `0x18001ef90`
- `0x18001f3ac`
- `0x180020824`

## callees

- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0q_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD v4[4]; // [rsp+30h] [rbp-38h] BYREF
  int v5; // [rsp+80h] [rbp+18h] BYREF

  v5 = a3;
  v4[3] = 4;
  v4[2] = &v5;
  return McGenEventWrite_EtwEventWriteTransfer(&Dhcpv6_Context, a2, a3, 2, (__int64)v4);
}

```

## disassembly

```asm
0x180001ca4  mov     r11, rsp
0x180001ca7  mov     [r11+18h], r8d
0x180001cab  sub     rsp, 68h
0x180001caf  mov     rax, cs:__security_cookie
0x180001cb6  xor     rax, rsp
0x180001cb9  mov     [rsp+68h+var_18], rax
0x180001cbe  lea     rax, [r11+18h]
0x180001cc2  mov     qword ptr [r11-20h], 4
0x180001cca  mov     [r11-28h], rax
0x180001cce  lea     rcx, Dhcpv6_Context
0x180001cd5  lea     rax, [r11-38h]
0x180001cd9  mov     r9d, 2
0x180001cdf  mov     [r11-48h], rax
0x180001ce3  call    McGenEventWrite_EtwEventWriteTransfer
0x180001ce8  mov     rcx, [rsp+68h+var_18]
0x180001ced  xor     rcx, rsp; StackCookie
0x180001cf0  call    __security_check_cookie
0x180001cf5  add     rsp, 68h
0x180001cf9  retn
```
