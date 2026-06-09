# McTemplateU0q_EtwEventWriteTransfer

- ea: `0x180005b5c`
- end: `0x180005bab`
- name: `McTemplateU0q_EtwEventWriteTransfer`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `22`
- callee_count: `2`
- tags: ``

## callers

- `0x180001a10`
- `0x180001c10`
- `0x180003030`
- `0x1800052c0`
- `0x180007310`
- `0x180007c50`
- `0x1800080e0`
- `0x180008cc0`
- `0x180008fe0`
- `0x180009340`
- `0x180009690`
- `0x180009f50`
- `0x18000a320`
- `0x18000a8e0`
- `0x18000b2e0`
- `0x180011650`
- `0x1800127c0`
- `0x180013800`
- `0x180013910`
- `0x180013bd0`
- `0x1800148b0`
- `0x180014bc0`

## callees

- `0x180004594`
- `0x18000d0a0`

## pseudocode

```c
__int64 __fastcall McTemplateU0q_EtwEventWriteTransfer(_QWORD *a1, __int64 a2, __int64 a3)
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
0x180005b5c  mov     r11, rsp
0x180005b5f  mov     [r11+18h], r8d
0x180005b63  sub     rsp, 68h
0x180005b67  mov     rax, cs:__security_cookie
0x180005b6e  xor     rax, rsp
0x180005b71  mov     [rsp+68h+var_18], rax
0x180005b76  lea     rax, [r11+18h]
0x180005b7a  mov     qword ptr [r11-20h], 4
0x180005b82  mov     [r11-28h], rax
0x180005b86  mov     r9d, 2
0x180005b8c  lea     rax, [r11-38h]
0x180005b90  mov     [r11-48h], rax
0x180005b94  call    McGenEventWrite_EtwEventWriteTransfer
0x180005b99  mov     rcx, [rsp+68h+var_18]
0x180005b9e  xor     rcx, rsp; StackCookie
0x180005ba1  call    __security_check_cookie
0x180005ba6  add     rsp, 68h
0x180005baa  retn
```
