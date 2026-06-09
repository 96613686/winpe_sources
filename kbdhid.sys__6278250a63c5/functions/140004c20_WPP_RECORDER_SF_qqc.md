# WPP_RECORDER_SF_qqc

- ea: `0x140004c20`
- end: `0x140004d1c`
- name: `WPP_RECORDER_SF_qqc`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f930`

## callees

- `0x140004c20`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004d04`
- `WppRecorder!WppAutoLogTrace` at `0x140004d04`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qqc(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
{
  int v7; // [rsp+20h] [rbp-48h]
  __int64 v8; // [rsp+98h] [rbp+30h] BYREF
  va_list va; // [rsp+98h] [rbp+30h]
  __int64 v10; // [rsp+A0h] [rbp+38h] BYREF
  va_list va1; // [rsp+A0h] [rbp+38h]
  va_list va2; // [rsp+A8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v8 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v10 = va_arg(va2, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids,
      19,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      va2,
      1,
      0);
  LOWORD(v7) = 19;
  return WppAutoLogTrace(a1, 4, 5, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x140004c20  mov     r11, rsp
0x140004c23  mov     [r11+8], rbx
0x140004c27  push    rsi
0x140004c28  sub     rsp, 60h
0x140004c2c  mov     rbx, rcx
0x140004c2f  mov     esi, 13h
0x140004c34  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c3b  mov     eax, [rcx+2Ch]
0x140004c3e  test    al, 10h
0x140004c40  jz      short loc_140004C9F
0x140004c42  cmp     byte ptr [rcx+29h], 4
0x140004c46  jb      short loc_140004C9F
0x140004c48  mov     rax, cs:pfnWppTraceMessage
0x140004c4f  lea     rdx, [r11+40h]
0x140004c53  mov     rcx, [rcx+18h]
0x140004c57  lea     r8, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids
0x140004c5e  mov     qword ptr [r11-18h], 0
0x140004c66  mov     r9d, esi
0x140004c69  mov     qword ptr [r11-20h], 1
0x140004c71  mov     [r11-28h], rdx
0x140004c75  lea     rdx, [r11+38h]
0x140004c79  mov     qword ptr [r11-30h], 8
0x140004c81  mov     [r11-38h], rdx
0x140004c85  lea     rdx, [r11+30h]
0x140004c89  mov     qword ptr [r11-40h], 8
0x140004c91  mov     [r11-48h], rdx
0x140004c95  mov     edx, 2Bh ; '+'
0x140004c9a  call    _guard_dispatch_icall
0x140004c9f  mov     [rsp+68h+var_10], 0
0x140004ca8  lea     rax, [rsp+68h+arg_38]
0x140004cb0  mov     [rsp+68h+var_18], 1
0x140004cb9  lea     r9, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids
0x140004cc0  mov     [rsp+68h+var_20], rax
0x140004cc5  mov     edx, 4
0x140004cca  mov     [rsp+68h+var_28], 8
0x140004cd3  lea     rax, [rsp+68h+arg_30]
0x140004cdb  mov     [rsp+68h+var_30], rax
0x140004ce0  mov     r8d, 5
0x140004ce6  lea     rax, [rsp+68h+arg_28]
0x140004cee  mov     [rsp+68h+var_38], 8
0x140004cf7  mov     [rsp+68h+var_40], rax
0x140004cfc  mov     rcx, rbx
0x140004cff  mov     [rsp+68h+var_48], si
0x140004d04  call    cs:__imp_WppAutoLogTrace
0x140004d0b  nop     dword ptr [rax+rax+00h]
0x140004d10  mov     rbx, [rsp+68h+arg_0]
0x140004d15  add     rsp, 60h
0x140004d19  pop     rsi
0x140004d1a  retn
```
