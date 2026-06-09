# WPP_RECORDER_SF_qDD

- ea: `0x140002830`
- end: `0x140002925`
- name: `WPP_RECORDER_SF_qDD`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001960`

## callees

- `0x140002830`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002908`
- `WppRecorder!WppAutoLogTrace` at `0x140002908`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qDD(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, int a5, ...)
{
  int v8; // [rsp+20h] [rbp-48h]
  __int64 v9; // [rsp+98h] [rbp+30h] BYREF
  va_list va; // [rsp+98h] [rbp+30h]
  __int64 v11; // [rsp+A0h] [rbp+38h] BYREF
  va_list va1; // [rsp+A0h] [rbp+38h]
  va_list va2; // [rsp+A8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v9 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v11 = va_arg(va2, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids,
      a4,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      4,
      va2,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 2, 5, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids, v8, (__int64 *)va);
}

```

## disassembly

```asm
0x140002830  mov     r11, rsp
0x140002833  mov     [r11+8], rbx
0x140002837  mov     [r11+10h], rsi
0x14000283b  push    rdi
0x14000283c  sub     rsp, 60h
0x140002840  mov     rdi, rcx
0x140002843  movzx   ebx, r9w
0x140002847  mov     rcx, cs:WPP_GLOBAL_Control
0x14000284e  mov     esi, 4
0x140002853  mov     eax, [rcx+2Ch]
0x140002856  test    al, 10h
0x140002858  jz      short loc_1400028AD
0x14000285a  cmp     byte ptr [rcx+29h], 2
0x14000285e  jb      short loc_1400028AD
0x140002860  mov     rax, cs:pfnWppTraceMessage
0x140002867  lea     rdx, [r11+40h]
0x14000286b  mov     rcx, [rcx+18h]
0x14000286f  lea     r8, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x140002876  mov     qword ptr [r11-18h], 0
0x14000287e  mov     r9d, ebx
0x140002881  mov     [r11-20h], rsi
0x140002885  mov     [r11-28h], rdx
0x140002889  lea     rdx, [r11+38h]
0x14000288d  mov     [r11-30h], rsi
0x140002891  mov     [r11-38h], rdx
0x140002895  lea     rdx, [r11+30h]
0x140002899  mov     qword ptr [r11-40h], 8
0x1400028a1  mov     [r11-48h], rdx
0x1400028a5  lea     edx, [rsi+27h]
0x1400028a8  call    _guard_dispatch_icall
0x1400028ad  mov     [rsp+68h+var_10], 0
0x1400028b6  lea     rax, [rsp+68h+arg_38]
0x1400028be  mov     [rsp+68h+var_18], rsi
0x1400028c3  lea     r9, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x1400028ca  mov     [rsp+68h+var_20], rax
0x1400028cf  mov     edx, 2
0x1400028d4  mov     [rsp+68h+var_28], rsi
0x1400028d9  lea     rax, [rsp+68h+arg_30]
0x1400028e1  mov     [rsp+68h+var_30], rax
0x1400028e6  mov     rcx, rdi
0x1400028e9  lea     rax, [rsp+68h+arg_28]
0x1400028f1  mov     [rsp+68h+var_38], 8
0x1400028fa  mov     [rsp+68h+var_40], rax
0x1400028ff  lea     r8d, [rdx+3]
0x140002903  mov     [rsp+68h+var_48], bx
0x140002908  call    cs:__imp_WppAutoLogTrace
0x14000290f  nop     dword ptr [rax+rax+00h]
0x140002914  mov     rbx, [rsp+68h+arg_0]
0x140002919  mov     rsi, [rsp+68h+arg_8]
0x14000291e  add     rsp, 60h
0x140002922  pop     rdi
0x140002923  retn
```
