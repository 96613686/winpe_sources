# WPP_RECORDER_SF_qql

- ea: `0x140006a74`
- end: `0x140006b68`
- name: `WPP_RECORDER_SF_qql`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001300`

## callees

- `0x140006a74`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140006b4b`
- `WppRecorder!WppAutoLogTrace` at `0x140006b4b`

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
      WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids,
      11,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      va2,
      4,
      0);
  LOWORD(v7) = 11;
  return WppAutoLogTrace(a1, 4, 2, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x140006a74  mov     r11, rsp
0x140006a77  mov     [r11+8], rbx
0x140006a7b  mov     [r11+10h], rbp
0x140006a7f  push    rsi
0x140006a80  sub     rsp, 60h
0x140006a84  mov     rbx, rcx
0x140006a87  mov     ebp, 0Bh
0x140006a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a93  lea     esi, [rbp-3]
0x140006a96  mov     eax, [rcx+2Ch]
0x140006a99  test    al, 2
0x140006a9b  jz      short loc_140006AF0
0x140006a9d  cmp     byte ptr [rcx+29h], 4
0x140006aa1  jb      short loc_140006AF0
0x140006aa3  mov     rax, cs:pfnWppTraceMessage
0x140006aaa  lea     rdx, [r11+40h]
0x140006aae  mov     rcx, [rcx+18h]
0x140006ab2  lea     r8, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x140006ab9  mov     qword ptr [r11-18h], 0
0x140006ac1  mov     r9d, ebp
0x140006ac4  mov     qword ptr [r11-20h], 4
0x140006acc  mov     [r11-28h], rdx
0x140006ad0  lea     rdx, [r11+38h]
0x140006ad4  mov     [r11-30h], rsi
0x140006ad8  mov     [r11-38h], rdx
0x140006adc  lea     rdx, [r11+30h]
0x140006ae0  mov     [r11-40h], rsi
0x140006ae4  mov     [r11-48h], rdx
0x140006ae8  lea     edx, [rbp+20h]
0x140006aeb  call    _guard_dispatch_icall
0x140006af0  mov     [rsp+68h+var_10], 0
0x140006af9  lea     rax, [rsp+68h+arg_38]
0x140006b01  mov     [rsp+68h+var_18], 4
0x140006b0a  lea     r9, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x140006b11  mov     [rsp+68h+var_20], rax
0x140006b16  mov     edx, 4
0x140006b1b  mov     [rsp+68h+var_28], rsi
0x140006b20  lea     rax, [rsp+68h+arg_30]
0x140006b28  mov     [rsp+68h+var_30], rax
0x140006b2d  mov     rcx, rbx
0x140006b30  lea     rax, [rsp+68h+arg_28]
0x140006b38  mov     [rsp+68h+var_38], rsi
0x140006b3d  mov     [rsp+68h+var_40], rax
0x140006b42  lea     r8d, [rdx-2]
0x140006b46  mov     [rsp+68h+var_48], bp
0x140006b4b  call    cs:__imp_WppAutoLogTrace
0x140006b52  nop     dword ptr [rax+rax+00h]
0x140006b57  mov     rbx, [rsp+68h+arg_0]
0x140006b5c  mov     rbp, [rsp+68h+arg_8]
0x140006b61  add     rsp, 60h
0x140006b65  pop     rsi
0x140006b66  retn
```
