# McTemplateU0u_EtwEventWriteTransfer

- ea: `0x18002aa00`
- end: `0x18002aa4f`
- name: `McTemplateU0u_EtwEventWriteTransfer`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002b224`

## callees

- `0x1800053e0`
- `0x180020250`

## pseudocode

```c
__int64 __fastcall McTemplateU0u_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD v4[4]; // [rsp+30h] [rbp-38h] BYREF
  char v5; // [rsp+80h] [rbp+18h] BYREF

  v5 = a3;
  v4[3] = 1;
  v4[2] = &v5;
  return McGenEventWrite_EtwEventWriteTransfer(a1, a2, a3, 2, (__int64)v4);
}

```

## disassembly

```asm
0x18002aa00  mov     r11, rsp
0x18002aa03  mov     [r11+18h], r8b
0x18002aa07  sub     rsp, 68h
0x18002aa0b  mov     rax, cs:__security_cookie
0x18002aa12  xor     rax, rsp
0x18002aa15  mov     [rsp+68h+var_18], rax
0x18002aa1a  lea     rax, [r11+18h]
0x18002aa1e  mov     qword ptr [r11-20h], 1
0x18002aa26  mov     [r11-28h], rax
0x18002aa2a  mov     r9d, 2
0x18002aa30  lea     rax, [r11-38h]
0x18002aa34  mov     [r11-48h], rax
0x18002aa38  call    McGenEventWrite_EtwEventWriteTransfer
0x18002aa3d  mov     rcx, [rsp+68h+var_18]
0x18002aa42  xor     rcx, rsp; StackCookie
0x18002aa45  call    __security_check_cookie
0x18002aa4a  add     rsp, 68h
0x18002aa4e  retn
```
