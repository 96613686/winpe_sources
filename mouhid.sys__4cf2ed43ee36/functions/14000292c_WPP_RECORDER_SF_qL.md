# WPP_RECORDER_SF_qL

- ea: `0x14000292c`
- end: `0x1400029ff`
- name: `WPP_RECORDER_SF_qL`
- size: `211`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002050`
- `0x140002370`

## callees

- `0x14000292c`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400029e2`
- `WppRecorder!WppAutoLogTrace` at `0x1400029e2`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qL(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, int a5, ...)
{
  int v8; // [rsp+20h] [rbp-38h]
  __int64 v9; // [rsp+88h] [rbp+30h] BYREF
  va_list va; // [rsp+88h] [rbp+30h]
  va_list va1; // [rsp+90h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v9 = va_arg(va1, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids,
      a4,
      (__int64 *)va,
      8,
      va1,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 4, 4, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids, v8, (__int64 *)va);
}

```

## disassembly

```asm
0x14000292c  mov     r11, rsp
0x14000292f  mov     [r11+8], rbx
0x140002933  mov     [r11+10h], rsi
0x140002937  push    rdi
0x140002938  sub     rsp, 50h
0x14000293c  mov     rdi, rcx
0x14000293f  movzx   ebx, r9w
0x140002943  mov     rcx, cs:WPP_GLOBAL_Control
0x14000294a  mov     esi, 4
0x14000294f  mov     eax, [rcx+2Ch]
0x140002952  test    al, 8
0x140002954  jz      short loc_14000299D
0x140002956  cmp     [rcx+29h], sil
0x14000295a  jb      short loc_14000299D
0x14000295c  mov     rax, cs:pfnWppTraceMessage
0x140002963  lea     rdx, [r11+38h]
0x140002967  mov     rcx, [rcx+18h]
0x14000296b  lea     r8, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x140002972  mov     qword ptr [r11-18h], 0
0x14000297a  mov     r9d, ebx
0x14000297d  mov     [r11-20h], rsi
0x140002981  mov     [r11-28h], rdx
0x140002985  lea     rdx, [r11+30h]
0x140002989  mov     qword ptr [r11-30h], 8
0x140002991  mov     [r11-38h], rdx
0x140002995  lea     edx, [rsi+27h]
0x140002998  call    _guard_dispatch_icall
0x14000299d  mov     [rsp+58h+var_10], 0
0x1400029a6  lea     rax, [rsp+58h+arg_30]
0x1400029ae  mov     [rsp+58h+var_18], rsi
0x1400029b3  lea     r9, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x1400029ba  mov     [rsp+58h+var_20], rax
0x1400029bf  mov     r8d, esi
0x1400029c2  lea     rax, [rsp+58h+arg_28]
0x1400029ca  mov     [rsp+58h+var_28], 8
0x1400029d3  mov     [rsp+58h+var_30], rax
0x1400029d8  mov     edx, esi
0x1400029da  mov     rcx, rdi
0x1400029dd  mov     [rsp+58h+var_38], bx
0x1400029e2  call    cs:__imp_WppAutoLogTrace
0x1400029e9  nop     dword ptr [rax+rax+00h]
0x1400029ee  mov     rbx, [rsp+58h+arg_0]
0x1400029f3  mov     rsi, [rsp+58h+arg_8]
0x1400029f8  add     rsp, 50h
0x1400029fc  pop     rdi
0x1400029fd  retn
```
