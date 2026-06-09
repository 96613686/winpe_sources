# WPP_RECORDER_SF_c

- ea: `0x140002780`
- end: `0x140002829`
- name: `WPP_RECORDER_SF_c`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002050`

## callees

- `0x140002780`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002811`
- `WppRecorder!WppAutoLogTrace` at `0x140002811`

## pseudocode

```c
__int64 WPP_RECORDER_SF_c(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
{
  int v7; // [rsp+20h] [rbp-28h]
  va_list va; // [rsp+78h] [rbp+30h] BYREF

  va_start(va, a5);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids,
      33,
      va,
      1,
      0);
  LOWORD(v7) = 33;
  return WppAutoLogTrace(a1, 2, 4, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids, v7, va);
}

```

## disassembly

```asm
0x140002780  mov     r11, rsp
0x140002783  mov     [r11+8], rbx
0x140002787  push    rsi
0x140002788  sub     rsp, 40h
0x14000278c  mov     rbx, rcx
0x14000278f  mov     esi, 21h ; '!'
0x140002794  mov     rcx, cs:WPP_GLOBAL_Control
0x14000279b  mov     eax, [rcx+2Ch]
0x14000279e  test    al, 8
0x1400027a0  jz      short loc_1400027DD
0x1400027a2  cmp     byte ptr [rcx+29h], 2
0x1400027a6  jb      short loc_1400027DD
0x1400027a8  mov     rax, cs:pfnWppTraceMessage
0x1400027af  lea     rdx, [r11+30h]
0x1400027b3  mov     rcx, [rcx+18h]
0x1400027b7  lea     r8, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x1400027be  mov     qword ptr [r11-18h], 0
0x1400027c6  mov     r9d, esi
0x1400027c9  mov     qword ptr [r11-20h], 1
0x1400027d1  mov     [r11-28h], rdx
0x1400027d5  lea     edx, [rsi+0Ah]
0x1400027d8  call    _guard_dispatch_icall
0x1400027dd  mov     [rsp+48h+var_10], 0
0x1400027e6  lea     rax, [rsp+48h+arg_28]
0x1400027eb  mov     edx, 2
0x1400027f0  mov     [rsp+48h+var_18], 1
0x1400027f9  mov     [rsp+48h+var_20], rax
0x1400027fe  lea     r9, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x140002805  mov     rcx, rbx
0x140002808  mov     [rsp+48h+var_28], si
0x14000280d  lea     r8d, [rdx+2]
0x140002811  call    cs:__imp_WppAutoLogTrace
0x140002818  nop     dword ptr [rax+rax+00h]
0x14000281d  mov     rbx, [rsp+48h+arg_0]
0x140002822  add     rsp, 40h
0x140002826  pop     rsi
0x140002827  retn
```
