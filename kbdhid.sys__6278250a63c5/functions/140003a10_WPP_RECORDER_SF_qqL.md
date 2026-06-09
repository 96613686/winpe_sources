# WPP_RECORDER_SF_qqL

- ea: `0x140003a10`
- end: `0x140003b0c`
- name: `WPP_RECORDER_SF_qqL`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003470`

## callees

- `0x140003a10`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140003af4`
- `WppRecorder!WppAutoLogTrace` at `0x140003af4`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qqL(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
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
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids,
      11,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      va2,
      4,
      0);
  LOWORD(v7) = 11;
  return WppAutoLogTrace(a1, 4, 3, WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x140003a10  mov     r11, rsp
0x140003a13  mov     [r11+8], rbx
0x140003a17  push    rsi
0x140003a18  sub     rsp, 60h
0x140003a1c  mov     rbx, rcx
0x140003a1f  mov     esi, 0Bh
0x140003a24  mov     rcx, cs:WPP_GLOBAL_Control
0x140003a2b  mov     eax, [rcx+2Ch]
0x140003a2e  test    al, 4
0x140003a30  jz      short loc_140003A8F
0x140003a32  cmp     byte ptr [rcx+29h], 4
0x140003a36  jb      short loc_140003A8F
0x140003a38  mov     rax, cs:pfnWppTraceMessage
0x140003a3f  lea     rdx, [r11+40h]
0x140003a43  mov     rcx, [rcx+18h]
0x140003a47  lea     r8, WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids
0x140003a4e  mov     qword ptr [r11-18h], 0
0x140003a56  mov     r9d, esi
0x140003a59  mov     qword ptr [r11-20h], 4
0x140003a61  mov     [r11-28h], rdx
0x140003a65  lea     rdx, [r11+38h]
0x140003a69  mov     qword ptr [r11-30h], 8
0x140003a71  mov     [r11-38h], rdx
0x140003a75  lea     rdx, [r11+30h]
0x140003a79  mov     qword ptr [r11-40h], 8
0x140003a81  mov     [r11-48h], rdx
0x140003a85  mov     edx, 2Bh ; '+'
0x140003a8a  call    _guard_dispatch_icall
0x140003a8f  mov     [rsp+68h+var_10], 0
0x140003a98  lea     rax, [rsp+68h+arg_38]
0x140003aa0  mov     [rsp+68h+var_18], 4
0x140003aa9  lea     r9, WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids
0x140003ab0  mov     [rsp+68h+var_20], rax
0x140003ab5  mov     edx, 4
0x140003aba  mov     [rsp+68h+var_28], 8
0x140003ac3  lea     rax, [rsp+68h+arg_30]
0x140003acb  mov     [rsp+68h+var_30], rax
0x140003ad0  mov     r8d, 3
0x140003ad6  lea     rax, [rsp+68h+arg_28]
0x140003ade  mov     [rsp+68h+var_38], 8
0x140003ae7  mov     [rsp+68h+var_40], rax
0x140003aec  mov     rcx, rbx
0x140003aef  mov     [rsp+68h+var_48], si
0x140003af4  call    cs:__imp_WppAutoLogTrace
0x140003afb  nop     dword ptr [rax+rax+00h]
0x140003b00  mov     rbx, [rsp+68h+arg_0]
0x140003b05  add     rsp, 60h
0x140003b09  pop     rsi
0x140003b0a  retn
```
