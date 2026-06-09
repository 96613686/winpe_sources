# WPP_RECORDER_SF_DDDD

- ea: `0x14000cc5c`
- end: `0x14000cd62`
- name: `WPP_RECORDER_SF_DDDD`
- size: `262`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001c808`
- `0x14001cfa0`

## callees

- `0x14000cc5c`
- `0x14000daa0`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000cd43`
- `WppRecorder!WppAutoLogTrace` at `0x14000cd43`

## pseudocode

```c
__int64 WPP_RECORDER_SF_DDDD(__int64 a1, _DWORD a2, _DWORD a3, unsigned __int16 a4, __int64 a5, ...)
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
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids,
      a4,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      (__int64 *)va2,
      4,
      va3,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 0, 16, WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids, v8, (__int64 *)va);
}

```

## disassembly

```asm
0x14000cc5c  mov     r11, rsp
0x14000cc5f  mov     [r11+8], rbx
0x14000cc63  mov     [r11+10h], rsi
0x14000cc67  push    rdi
0x14000cc68  sub     rsp, 70h
0x14000cc6c  mov     rdi, rcx
0x14000cc6f  movzx   ebx, r9w
0x14000cc73  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cc7a  mov     esi, 4
0x14000cc7f  test    dword ptr [rcx+2Ch], 8000h
0x14000cc86  jz      short loc_14000CCDD
0x14000cc88  mov     rax, cs:pfnWppTraceMessage
0x14000cc8f  lea     rdx, [r11+48h]
0x14000cc93  mov     rcx, [rcx+18h]
0x14000cc97  lea     r8, WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids
0x14000cc9e  mov     qword ptr [r11-18h], 0
0x14000cca6  mov     r9d, ebx
0x14000cca9  mov     [r11-20h], rsi
0x14000ccad  mov     [r11-28h], rdx
0x14000ccb1  lea     rdx, [r11+40h]
0x14000ccb5  mov     [r11-30h], rsi
0x14000ccb9  mov     [r11-38h], rdx
0x14000ccbd  lea     rdx, [r11+38h]
0x14000ccc1  mov     [r11-40h], rsi
0x14000ccc5  mov     [r11-48h], rdx
0x14000ccc9  lea     rdx, [r11+30h]
0x14000cccd  mov     [r11-50h], rsi
0x14000ccd1  mov     [r11-58h], rdx
0x14000ccd5  lea     edx, [rsi+27h]
0x14000ccd8  call    _guard_dispatch_icall
0x14000ccdd  mov     [rsp+78h+var_10], 0
0x14000cce6  lea     rax, [rsp+78h+arg_40]
0x14000ccee  mov     [rsp+78h+var_18], rsi
0x14000ccf3  lea     r9, WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids
0x14000ccfa  mov     [rsp+78h+var_20], rax
0x14000ccff  xor     edx, edx
0x14000cd01  mov     [rsp+78h+var_28], rsi
0x14000cd06  lea     rax, [rsp+78h+arg_38]
0x14000cd0e  mov     [rsp+78h+var_30], rax
0x14000cd13  mov     rcx, rdi
0x14000cd16  mov     [rsp+78h+var_38], rsi
0x14000cd1b  lea     rax, [rsp+78h+arg_30]
0x14000cd23  mov     [rsp+78h+var_40], rax
0x14000cd28  lea     r8d, [rdx+10h]
0x14000cd2c  lea     rax, [rsp+78h+arg_28]
0x14000cd34  mov     [rsp+78h+var_48], rsi
0x14000cd39  mov     [rsp+78h+var_50], rax
0x14000cd3e  mov     [rsp+78h+var_58], bx
0x14000cd43  call    cs:__imp_WppAutoLogTrace
0x14000cd4a  nop     dword ptr [rax+rax+00h]
0x14000cd4f  lea     r11, [rsp+78h+var_8]
0x14000cd54  mov     rbx, [r11+10h]
0x14000cd58  mov     rsi, [r11+18h]
0x14000cd5c  mov     rsp, r11
0x14000cd5f  pop     rdi
0x14000cd60  retn
```
