# McTemplateU0q_EtwEventWriteTransfer

- ea: `0x14000ce0c`
- end: `0x14000ce66`
- name: `McTemplateU0q_EtwEventWriteTransfer`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004470`

## callees

- `0x140005530`
- `0x14000cdb4`

## pseudocode

```c
__int64 __fastcall McTemplateU0q_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v5[4]; // [rsp+38h] [rbp-30h] BYREF

  v4 = 0;
  v5[2] = &v4;
  v5[3] = 4;
  return McGenEventWrite_EtwEventWriteTransfer(a1, (__int64)StartDWMTransport, a3, 2, (__int64)v5);
}

```

## disassembly

```asm
0x14000ce0c  mov     r11, rsp
0x14000ce0f  sub     rsp, 68h
0x14000ce13  mov     rax, cs:__security_cookie
0x14000ce1a  xor     rax, rsp
0x14000ce1d  mov     [rsp+68h+var_10], rax
0x14000ce22  lea     rax, [r11-38h]
0x14000ce26  mov     [rsp+68h+var_38], 0
0x14000ce2e  mov     [r11-20h], rax
0x14000ce32  lea     rdx, StartDWMTransport
0x14000ce39  lea     rax, [r11-30h]
0x14000ce3d  mov     qword ptr [r11-18h], 4
0x14000ce45  mov     r9d, 2
0x14000ce4b  mov     [r11-48h], rax
0x14000ce4f  call    McGenEventWrite_EtwEventWriteTransfer
0x14000ce54  mov     rcx, [rsp+68h+var_10]
0x14000ce59  xor     rcx, rsp; StackCookie
0x14000ce5c  call    __security_check_cookie
0x14000ce61  add     rsp, 68h
0x14000ce65  retn
```
