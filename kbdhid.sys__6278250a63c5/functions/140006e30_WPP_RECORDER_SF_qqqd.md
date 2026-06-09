# WPP_RECORDER_SF_qqqd

- ea: `0x140006e30`
- end: `0x140006f45`
- name: `WPP_RECORDER_SF_qqqd`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400026a0`

## callees

- `0x140006e30`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140006f26`
- `WppRecorder!WppAutoLogTrace` at `0x140006f26`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qqqd(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, int a5, ...)
{
  int v8; // [rsp+20h] [rbp-58h]
  __int64 v9; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  __int64 v11; // [rsp+B0h] [rbp+38h] BYREF
  va_list va1; // [rsp+B0h] [rbp+38h]
  __int64 v13; // [rsp+B8h] [rbp+40h] BYREF
  va_list va2; // [rsp+B8h] [rbp+40h]
  va_list va3; // [rsp+C0h] [rbp+48h] BYREF

  va_start(va3, a5);
  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v9 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v11 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v13 = va_arg(va3, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    pfnWppTraceMessage(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
      a4,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      (__int64 *)va2,
      8,
      va3,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 2, 1, WPP_98d22518711f34f074bb80910c9ade48_Traceguids, v8, (__int64 *)va);
}

```

## disassembly

```asm
0x140006e30  mov     r11, rsp
0x140006e33  mov     [r11+8], rbx
0x140006e37  mov     [r11+10h], rsi
0x140006e3b  push    rdi
0x140006e3c  sub     rsp, 70h
0x140006e40  mov     rdi, rcx
0x140006e43  movzx   ebx, r9w
0x140006e47  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e4e  mov     esi, 8
0x140006e53  mov     eax, [rcx+2Ch]
0x140006e56  test    al, 1
0x140006e58  jz      short loc_140006EB9
0x140006e5a  cmp     byte ptr [rcx+29h], 2
0x140006e5e  jb      short loc_140006EB9
0x140006e60  mov     rax, cs:pfnWppTraceMessage
0x140006e67  lea     rdx, [r11+48h]
0x140006e6b  mov     rcx, [rcx+18h]
0x140006e6f  lea     r8, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x140006e76  mov     qword ptr [r11-18h], 0
0x140006e7e  mov     r9d, ebx
0x140006e81  mov     qword ptr [r11-20h], 4
0x140006e89  mov     [r11-28h], rdx
0x140006e8d  lea     rdx, [r11+40h]
0x140006e91  mov     [r11-30h], rsi
0x140006e95  mov     [r11-38h], rdx
0x140006e99  lea     rdx, [r11+38h]
0x140006e9d  mov     [r11-40h], rsi
0x140006ea1  mov     [r11-48h], rdx
0x140006ea5  lea     rdx, [r11+30h]
0x140006ea9  mov     [r11-50h], rsi
0x140006ead  mov     [r11-58h], rdx
0x140006eb1  lea     edx, [rsi+23h]
0x140006eb4  call    _guard_dispatch_icall
0x140006eb9  mov     [rsp+78h+var_10], 0
0x140006ec2  lea     rax, [rsp+78h+arg_40]
0x140006eca  mov     [rsp+78h+var_18], 4
0x140006ed3  lea     r9, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x140006eda  mov     [rsp+78h+var_20], rax
0x140006edf  mov     edx, 2
0x140006ee4  mov     [rsp+78h+var_28], rsi
0x140006ee9  lea     rax, [rsp+78h+arg_38]
0x140006ef1  mov     [rsp+78h+var_30], rax
0x140006ef6  mov     rcx, rdi
0x140006ef9  mov     [rsp+78h+var_38], rsi
0x140006efe  lea     rax, [rsp+78h+arg_30]
0x140006f06  mov     [rsp+78h+var_40], rax
0x140006f0b  lea     r8d, [rdx-1]
0x140006f0f  lea     rax, [rsp+78h+arg_28]
0x140006f17  mov     [rsp+78h+var_48], rsi
0x140006f1c  mov     [rsp+78h+var_50], rax
0x140006f21  mov     [rsp+78h+var_58], bx
0x140006f26  call    cs:__imp_WppAutoLogTrace
0x140006f2d  nop     dword ptr [rax+rax+00h]
0x140006f32  lea     r11, [rsp+78h+var_8]
0x140006f37  mov     rbx, [r11+10h]
0x140006f3b  mov     rsi, [r11+18h]
0x140006f3f  mov     rsp, r11
0x140006f42  pop     rdi
0x140006f43  retn
```
