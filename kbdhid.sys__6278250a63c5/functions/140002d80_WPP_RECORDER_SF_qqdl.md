# WPP_RECORDER_SF_qqdl

- ea: `0x140002d80`
- end: `0x140002ea5`
- name: `WPP_RECORDER_SF_qqdl`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400026a0`

## callees

- `0x140002d80`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002e8a`
- `WppRecorder!WppAutoLogTrace` at `0x140002e8a`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qqdl(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
{
  int v7; // [rsp+20h] [rbp-58h]
  __int64 v8; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  __int64 v10; // [rsp+B0h] [rbp+38h] BYREF
  va_list va1; // [rsp+B0h] [rbp+38h]
  __int64 v12; // [rsp+B8h] [rbp+40h] BYREF
  va_list va2; // [rsp+B8h] [rbp+40h]
  va_list va3; // [rsp+C0h] [rbp+48h] BYREF

  va_start(va3, a5);
  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v8 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v10 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v12 = va_arg(va3, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    pfnWppTraceMessage(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
      16,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      (__int64 *)va2,
      4,
      va3,
      4,
      0);
  LOWORD(v7) = 16;
  return WppAutoLogTrace(a1, 4, 1, WPP_98d22518711f34f074bb80910c9ade48_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x140002d80  mov     r11, rsp
0x140002d83  mov     [r11+8], rbx
0x140002d87  push    rsi
0x140002d88  sub     rsp, 70h
0x140002d8c  mov     rbx, rcx
0x140002d8f  mov     esi, 10h
0x140002d94  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d9b  mov     eax, [rcx+2Ch]
0x140002d9e  test    al, 1
0x140002da0  jz      short loc_140002E0F
0x140002da2  cmp     byte ptr [rcx+29h], 4
0x140002da6  jb      short loc_140002E0F
0x140002da8  mov     rax, cs:pfnWppTraceMessage
0x140002daf  lea     rdx, [r11+48h]
0x140002db3  mov     rcx, [rcx+18h]
0x140002db7  lea     r8, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x140002dbe  mov     qword ptr [r11-18h], 0
0x140002dc6  mov     r9d, esi
0x140002dc9  mov     qword ptr [r11-20h], 4
0x140002dd1  mov     [r11-28h], rdx
0x140002dd5  lea     rdx, [r11+40h]
0x140002dd9  mov     qword ptr [r11-30h], 4
0x140002de1  mov     [r11-38h], rdx
0x140002de5  lea     rdx, [r11+38h]
0x140002de9  mov     qword ptr [r11-40h], 8
0x140002df1  mov     [r11-48h], rdx
0x140002df5  lea     rdx, [r11+30h]
0x140002df9  mov     qword ptr [r11-50h], 8
0x140002e01  mov     [r11-58h], rdx
0x140002e05  mov     edx, 2Bh ; '+'
0x140002e0a  call    _guard_dispatch_icall
0x140002e0f  mov     [rsp+78h+var_10], 0
0x140002e18  lea     rax, [rsp+78h+arg_40]
0x140002e20  mov     [rsp+78h+var_18], 4
0x140002e29  lea     r9, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x140002e30  mov     [rsp+78h+var_20], rax
0x140002e35  mov     edx, 4
0x140002e3a  mov     [rsp+78h+var_28], 4
0x140002e43  lea     rax, [rsp+78h+arg_38]
0x140002e4b  mov     [rsp+78h+var_30], rax
0x140002e50  mov     r8d, 1
0x140002e56  mov     [rsp+78h+var_38], 8
0x140002e5f  lea     rax, [rsp+78h+arg_30]
0x140002e67  mov     [rsp+78h+var_40], rax
0x140002e6c  mov     rcx, rbx
0x140002e6f  lea     rax, [rsp+78h+arg_28]
0x140002e77  mov     [rsp+78h+var_48], 8
0x140002e80  mov     [rsp+78h+var_50], rax
0x140002e85  mov     [rsp+78h+var_58], si
0x140002e8a  call    cs:__imp_WppAutoLogTrace
0x140002e91  nop     dword ptr [rax+rax+00h]
0x140002e96  mov     rbx, [rsp+78h+arg_0]
0x140002e9e  add     rsp, 70h
0x140002ea2  pop     rsi
0x140002ea3  retn
```
