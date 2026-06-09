# McTemplateU0qhquq_EtwEventWriteTransfer

- ea: `0x180004660`
- end: `0x180004701`
- name: `McTemplateU0qhquq_EtwEventWriteTransfer`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006160`

## callees

- `0x1800053e0`
- `0x180020250`

## pseudocode

```c
__int64 __fastcall McTemplateU0qhquq_EtwEventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int16 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD v8[12]; // [rsp+30h] [rbp-78h] BYREF
  int v9; // [rsp+C0h] [rbp+18h] BYREF
  __int16 v10; // [rsp+C8h] [rbp+20h] BYREF

  v10 = a4;
  v9 = a3;
  v8[3] = 4;
  v8[2] = &v9;
  v8[5] = 2;
  v8[4] = &v10;
  v8[6] = &a5;
  v8[8] = &a6;
  v8[10] = &a7;
  v8[7] = 4;
  v8[9] = 1;
  v8[11] = 4;
  return McGenEventWrite_EtwEventWriteTransfer(a1, a2, a3, 6, (__int64)v8);
}

```

## disassembly

```asm
0x180004660  mov     r11, rsp
0x180004663  mov     [r11+20h], r9w
0x180004668  mov     [r11+18h], r8d
0x18000466c  sub     rsp, 0A8h
0x180004673  mov     rax, cs:__security_cookie
0x18000467a  xor     rax, rsp
0x18000467d  mov     [rsp+0A8h+var_18], rax
0x180004685  lea     rax, [r11+18h]
0x180004689  mov     qword ptr [r11-60h], 4
0x180004691  mov     [r11-68h], rax
0x180004695  mov     r9d, 6
0x18000469b  lea     rax, [r11+20h]
0x18000469f  mov     qword ptr [r11-50h], 2
0x1800046a7  mov     [r11-58h], rax
0x1800046ab  lea     rax, [r11+28h]
0x1800046af  mov     [r11-48h], rax
0x1800046b3  lea     rax, [r11+30h]
0x1800046b7  mov     [r11-38h], rax
0x1800046bb  lea     rax, [r11+38h]
0x1800046bf  mov     [r11-28h], rax
0x1800046c3  lea     rax, [r11-78h]
0x1800046c7  mov     [rsp+0A8h+var_88], rax
0x1800046cc  mov     qword ptr [r11-40h], 4
0x1800046d4  mov     qword ptr [r11-30h], 1
0x1800046dc  mov     qword ptr [r11-20h], 4
0x1800046e4  call    McGenEventWrite_EtwEventWriteTransfer
0x1800046e9  mov     rcx, [rsp+0A8h+var_18]
0x1800046f1  xor     rcx, rsp; StackCookie
0x1800046f4  call    __security_check_cookie
0x1800046f9  add     rsp, 0A8h
0x180004700  retn
```
