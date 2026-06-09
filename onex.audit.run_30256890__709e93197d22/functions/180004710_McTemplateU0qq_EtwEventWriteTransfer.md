# McTemplateU0qq_EtwEventWriteTransfer

- ea: `0x180004710`
- end: `0x180004773`
- name: `McTemplateU0qq_EtwEventWriteTransfer`
- size: `99`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ade0`
- `0x180012660`
- `0x180015f90`
- `0x180018950`
- `0x18001ce44`
- `0x180022960`
- `0x1800230c0`
- `0x180025dbc`
- `0x180026930`
- `0x1800288c4`

## callees

- `0x1800053e0`
- `0x180020250`

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
  return McGenEventWrite_EtwEventWriteTransfer(a1, a2, a3, 3, (__int64)v5);
}

```

## disassembly

```asm
0x180004710  mov     r11, rsp
0x180004713  mov     [r11+20h], r9d
0x180004717  mov     [r11+18h], r8d
0x18000471b  sub     rsp, 78h
0x18000471f  mov     rax, cs:__security_cookie
0x180004726  xor     rax, rsp
0x180004729  mov     [rsp+78h+var_18], rax
0x18000472e  lea     rax, [r11+18h]
0x180004732  mov     qword ptr [r11-30h], 4
0x18000473a  mov     [r11-38h], rax
0x18000473e  mov     r9d, 3
0x180004744  lea     rax, [r11+20h]
0x180004748  mov     qword ptr [r11-20h], 4
0x180004750  mov     [r11-28h], rax
0x180004754  lea     rax, [r11-48h]
0x180004758  mov     [r11-58h], rax
0x18000475c  call    McGenEventWrite_EtwEventWriteTransfer
0x180004761  mov     rcx, [rsp+78h+var_18]
0x180004766  xor     rcx, rsp; StackCookie
0x180004769  call    __security_check_cookie
0x18000476e  add     rsp, 78h
0x180004772  retn
```
