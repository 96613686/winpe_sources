# McTemplateU0qq_EtwEventWriteTransfer

- ea: `0x180013a20`
- end: `0x180013a91`
- name: `McTemplateU0qq_EtwEventWriteTransfer`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a8e0`

## callees

- `0x180004594`
- `0x18000d0a0`

## pseudocode

```c
__int64 __fastcall McTemplateU0qq_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  _QWORD v5[6]; // [rsp+30h] [rbp-48h] BYREF
  int v6; // [rsp+90h] [rbp+18h] BYREF
  int v7; // [rsp+98h] [rbp+20h] BYREF

  v7 = a4;
  v6 = a3;
  v5[3] = 4;
  v5[2] = &v6;
  v5[5] = 4;
  v5[4] = &v7;
  return McGenEventWrite_EtwEventWriteTransfer(
           Microsoft_Windows_Dwm_Api_Provider_Context,
           (__int64)ApiRenderGesture_Stop,
           a3,
           3,
           (__int64)v5);
}

```

## disassembly

```asm
0x180013a20  mov     r11, rsp
0x180013a23  mov     [r11+20h], r9d
0x180013a27  mov     [r11+18h], r8d
0x180013a2b  sub     rsp, 78h
0x180013a2f  mov     rax, cs:__security_cookie
0x180013a36  xor     rax, rsp
0x180013a39  mov     [rsp+78h+var_18], rax
0x180013a3e  lea     rax, [r11+18h]
0x180013a42  mov     qword ptr [r11-30h], 4
0x180013a4a  mov     [r11-38h], rax
0x180013a4e  lea     rdx, ApiRenderGesture_Stop
0x180013a55  lea     rax, [r11+20h]
0x180013a59  mov     qword ptr [r11-20h], 4
0x180013a61  mov     [r11-28h], rax
0x180013a65  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180013a6c  lea     rax, [r11-48h]
0x180013a70  mov     r9d, 3
0x180013a76  mov     [r11-58h], rax
0x180013a7a  call    McGenEventWrite_EtwEventWriteTransfer
0x180013a7f  mov     rcx, [rsp+78h+var_18]
0x180013a84  xor     rcx, rsp; StackCookie
0x180013a87  call    __security_check_cookie
0x180013a8c  add     rsp, 78h
0x180013a90  retn
```
