# WPP_RECORDER_SF_qql

- ea: `0x140003cf8`
- end: `0x140003dec`
- name: `WPP_RECORDER_SF_qql`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002ff0`

## callees

- `0x140003cf8`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140003dcf`
- `WppRecorder!WppAutoLogTrace` at `0x140003dcf`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qql(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
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
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids,
      11,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      va2,
      4,
      0);
  LOWORD(v7) = 11;
  return WppAutoLogTrace(a1, 4, 2, WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x140003cf8  mov     r11, rsp
0x140003cfb  mov     [r11+8], rbx
0x140003cff  mov     [r11+10h], rbp
0x140003d03  push    rsi
0x140003d04  sub     rsp, 60h
0x140003d08  mov     rbx, rcx
0x140003d0b  mov     ebp, 0Bh
0x140003d10  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d17  lea     esi, [rbp-3]
0x140003d1a  mov     eax, [rcx+2Ch]
0x140003d1d  test    al, 2
0x140003d1f  jz      short loc_140003D74
0x140003d21  cmp     byte ptr [rcx+29h], 4
0x140003d25  jb      short loc_140003D74
0x140003d27  mov     rax, cs:pfnWppTraceMessage
0x140003d2e  lea     rdx, [r11+40h]
0x140003d32  mov     rcx, [rcx+18h]
0x140003d36  lea     r8, WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids
0x140003d3d  mov     qword ptr [r11-18h], 0
0x140003d45  mov     r9d, ebp
0x140003d48  mov     qword ptr [r11-20h], 4
0x140003d50  mov     [r11-28h], rdx
0x140003d54  lea     rdx, [r11+38h]
0x140003d58  mov     [r11-30h], rsi
0x140003d5c  mov     [r11-38h], rdx
0x140003d60  lea     rdx, [r11+30h]
0x140003d64  mov     [r11-40h], rsi
0x140003d68  mov     [r11-48h], rdx
0x140003d6c  lea     edx, [rbp+20h]
0x140003d6f  call    _guard_dispatch_icall
0x140003d74  mov     [rsp+68h+var_10], 0
0x140003d7d  lea     rax, [rsp+68h+arg_38]
0x140003d85  mov     [rsp+68h+var_18], 4
0x140003d8e  lea     r9, WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids
0x140003d95  mov     [rsp+68h+var_20], rax
0x140003d9a  mov     edx, 4
0x140003d9f  mov     [rsp+68h+var_28], rsi
0x140003da4  lea     rax, [rsp+68h+arg_30]
0x140003dac  mov     [rsp+68h+var_30], rax
0x140003db1  mov     rcx, rbx
0x140003db4  lea     rax, [rsp+68h+arg_28]
0x140003dbc  mov     [rsp+68h+var_38], rsi
0x140003dc1  mov     [rsp+68h+var_40], rax
0x140003dc6  lea     r8d, [rdx-2]
0x140003dca  mov     [rsp+68h+var_48], bp
0x140003dcf  call    cs:__imp_WppAutoLogTrace
0x140003dd6  nop     dword ptr [rax+rax+00h]
0x140003ddb  mov     rbx, [rsp+68h+arg_0]
0x140003de0  mov     rbp, [rsp+68h+arg_8]
0x140003de5  add     rsp, 60h
0x140003de9  pop     rsi
0x140003dea  retn
```
