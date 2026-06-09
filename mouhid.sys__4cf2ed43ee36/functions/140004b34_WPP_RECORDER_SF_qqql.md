# WPP_RECORDER_SF_qqql

- ea: `0x140004b34`
- end: `0x140004c48`
- name: `WPP_RECORDER_SF_qqql`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003e00`

## callees

- `0x140004b34`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004c29`
- `WppRecorder!WppAutoLogTrace` at `0x140004c29`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qqql(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
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
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_bce545a1de1235e2be96703916423b99_Traceguids,
      22,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      (__int64 *)va2,
      8,
      va3,
      4,
      0);
  LOWORD(v7) = 22;
  return WppAutoLogTrace(a1, 4, 1, WPP_bce545a1de1235e2be96703916423b99_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x140004b34  mov     r11, rsp
0x140004b37  mov     [r11+8], rbx
0x140004b3b  mov     [r11+10h], rbp
0x140004b3f  push    rsi
0x140004b40  sub     rsp, 70h
0x140004b44  mov     rbx, rcx
0x140004b47  mov     ebp, 16h
0x140004b4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b53  lea     esi, [rbp-0Eh]
0x140004b56  mov     eax, [rcx+2Ch]
0x140004b59  test    al, 1
0x140004b5b  jz      short loc_140004BBC
0x140004b5d  cmp     byte ptr [rcx+29h], 4
0x140004b61  jb      short loc_140004BBC
0x140004b63  mov     rax, cs:pfnWppTraceMessage
0x140004b6a  lea     rdx, [r11+48h]
0x140004b6e  mov     rcx, [rcx+18h]
0x140004b72  lea     r8, WPP_bce545a1de1235e2be96703916423b99_Traceguids
0x140004b79  mov     qword ptr [r11-18h], 0
0x140004b81  mov     r9d, ebp
0x140004b84  mov     qword ptr [r11-20h], 4
0x140004b8c  mov     [r11-28h], rdx
0x140004b90  lea     rdx, [r11+40h]
0x140004b94  mov     [r11-30h], rsi
0x140004b98  mov     [r11-38h], rdx
0x140004b9c  lea     rdx, [r11+38h]
0x140004ba0  mov     [r11-40h], rsi
0x140004ba4  mov     [r11-48h], rdx
0x140004ba8  lea     rdx, [r11+30h]
0x140004bac  mov     [r11-50h], rsi
0x140004bb0  mov     [r11-58h], rdx
0x140004bb4  lea     edx, [rbp+15h]
0x140004bb7  call    _guard_dispatch_icall
0x140004bbc  mov     [rsp+78h+var_10], 0
0x140004bc5  lea     rax, [rsp+78h+arg_40]
0x140004bcd  mov     [rsp+78h+var_18], 4
0x140004bd6  lea     r9, WPP_bce545a1de1235e2be96703916423b99_Traceguids
0x140004bdd  mov     [rsp+78h+var_20], rax
0x140004be2  mov     edx, 4
0x140004be7  mov     [rsp+78h+var_28], rsi
0x140004bec  lea     rax, [rsp+78h+arg_38]
0x140004bf4  mov     [rsp+78h+var_30], rax
0x140004bf9  mov     rcx, rbx
0x140004bfc  mov     [rsp+78h+var_38], rsi
0x140004c01  lea     rax, [rsp+78h+arg_30]
0x140004c09  mov     [rsp+78h+var_40], rax
0x140004c0e  lea     r8d, [rdx-3]
0x140004c12  lea     rax, [rsp+78h+arg_28]
0x140004c1a  mov     [rsp+78h+var_48], rsi
0x140004c1f  mov     [rsp+78h+var_50], rax
0x140004c24  mov     [rsp+78h+var_58], bp
0x140004c29  call    cs:__imp_WppAutoLogTrace
0x140004c30  nop     dword ptr [rax+rax+00h]
0x140004c35  lea     r11, [rsp+78h+var_8]
0x140004c3a  mov     rbx, [r11+10h]
0x140004c3e  mov     rbp, [r11+18h]
0x140004c42  mov     rsp, r11
0x140004c45  pop     rsi
0x140004c46  retn
```
