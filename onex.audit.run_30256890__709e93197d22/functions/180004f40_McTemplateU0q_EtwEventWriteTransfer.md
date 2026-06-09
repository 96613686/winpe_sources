# McTemplateU0q_EtwEventWriteTransfer

- ea: `0x180004f40`
- end: `0x180004f8f`
- name: `McTemplateU0q_EtwEventWriteTransfer`
- size: `79`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x180001510`
- `0x180002470`
- `0x180002a30`
- `0x18000b330`
- `0x18000e230`
- `0x18000ecd0`
- `0x180014a20`
- `0x180014e50`
- `0x180016a40`
- `0x180016e80`
- `0x180018950`
- `0x18001a920`
- `0x18001d208`
- `0x180022630`
- `0x180023d80`
- `0x180026194`
- `0x1800280d0`
- `0x18002aa58`

## callees

- `0x1800053e0`
- `0x180020250`

## pseudocode

```c
__int64 __fastcall McTemplateU0q_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD v4[4]; // [rsp+30h] [rbp-38h] BYREF
  int v5; // [rsp+80h] [rbp+18h] BYREF

  v5 = a3;
  v4[3] = 4;
  v4[2] = &v5;
  return McGenEventWrite_EtwEventWriteTransfer(a1, a2, a3, 2, (__int64)v4);
}

```

## disassembly

```asm
0x180004f40  mov     r11, rsp
0x180004f43  mov     [r11+18h], r8d
0x180004f47  sub     rsp, 68h
0x180004f4b  mov     rax, cs:__security_cookie
0x180004f52  xor     rax, rsp
0x180004f55  mov     [rsp+68h+var_18], rax
0x180004f5a  lea     rax, [r11+18h]
0x180004f5e  mov     qword ptr [r11-20h], 4
0x180004f66  mov     [r11-28h], rax
0x180004f6a  mov     r9d, 2
0x180004f70  lea     rax, [r11-38h]
0x180004f74  mov     [r11-48h], rax
0x180004f78  call    McGenEventWrite_EtwEventWriteTransfer
0x180004f7d  mov     rcx, [rsp+68h+var_18]
0x180004f82  xor     rcx, rsp; StackCookie
0x180004f85  call    __security_check_cookie
0x180004f8a  add     rsp, 68h
0x180004f8e  retn
```
