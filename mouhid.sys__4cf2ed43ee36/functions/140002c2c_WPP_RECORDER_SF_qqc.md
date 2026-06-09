# WPP_RECORDER_SF_qqc

- ea: `0x140002c2c`
- end: `0x140002d20`
- name: `WPP_RECORDER_SF_qqc`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b730`

## callees

- `0x140002c2c`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002d03`
- `WppRecorder!WppAutoLogTrace` at `0x140002d03`

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
      WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids,
      21,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      va2,
      1,
      0);
  LOWORD(v7) = 21;
  return WppAutoLogTrace(a1, 4, 5, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x140002c2c  mov     r11, rsp
0x140002c2f  mov     [r11+8], rbx
0x140002c33  mov     [r11+10h], rbp
0x140002c37  push    rdi
0x140002c38  sub     rsp, 60h
0x140002c3c  mov     rbx, rcx
0x140002c3f  mov     ebp, 15h
0x140002c44  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c4b  lea     edi, [rbp-0Dh]
0x140002c4e  mov     eax, [rcx+2Ch]
0x140002c51  test    al, 10h
0x140002c53  jz      short loc_140002CA8
0x140002c55  cmp     byte ptr [rcx+29h], 4
0x140002c59  jb      short loc_140002CA8
0x140002c5b  mov     rax, cs:pfnWppTraceMessage
0x140002c62  lea     rdx, [r11+40h]
0x140002c66  mov     rcx, [rcx+18h]
0x140002c6a  lea     r8, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x140002c71  mov     qword ptr [r11-18h], 0
0x140002c79  mov     r9d, ebp
0x140002c7c  mov     qword ptr [r11-20h], 1
0x140002c84  mov     [r11-28h], rdx
0x140002c88  lea     rdx, [r11+38h]
0x140002c8c  mov     [r11-30h], rdi
0x140002c90  mov     [r11-38h], rdx
0x140002c94  lea     rdx, [r11+30h]
0x140002c98  mov     [r11-40h], rdi
0x140002c9c  mov     [r11-48h], rdx
0x140002ca0  lea     edx, [rbp+16h]
0x140002ca3  call    _guard_dispatch_icall
0x140002ca8  mov     [rsp+68h+var_10], 0
0x140002cb1  lea     rax, [rsp+68h+arg_38]
0x140002cb9  mov     [rsp+68h+var_18], 1
0x140002cc2  lea     r9, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x140002cc9  mov     [rsp+68h+var_20], rax
0x140002cce  mov     edx, 4
0x140002cd3  mov     [rsp+68h+var_28], rdi
0x140002cd8  lea     rax, [rsp+68h+arg_30]
0x140002ce0  mov     [rsp+68h+var_30], rax
0x140002ce5  mov     rcx, rbx
0x140002ce8  lea     rax, [rsp+68h+arg_28]
0x140002cf0  mov     [rsp+68h+var_38], rdi
0x140002cf5  mov     [rsp+68h+var_40], rax
0x140002cfa  lea     r8d, [rdx+1]
0x140002cfe  mov     [rsp+68h+var_48], bp
0x140002d03  call    cs:__imp_WppAutoLogTrace
0x140002d0a  nop     dword ptr [rax+rax+00h]
0x140002d0f  mov     rbx, [rsp+68h+arg_0]
0x140002d14  mov     rbp, [rsp+68h+arg_8]
0x140002d19  add     rsp, 60h
0x140002d1d  pop     rdi
0x140002d1e  retn
```
