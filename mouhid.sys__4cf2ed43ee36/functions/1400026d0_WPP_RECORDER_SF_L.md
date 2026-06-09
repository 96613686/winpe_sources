# WPP_RECORDER_SF_L

- ea: `0x1400026d0`
- end: `0x140002779`
- name: `WPP_RECORDER_SF_L`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002370`

## callees

- `0x1400026d0`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002761`
- `WppRecorder!WppAutoLogTrace` at `0x140002761`

## pseudocode

```c
__int64 WPP_RECORDER_SF_L(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
{
  int v7; // [rsp+20h] [rbp-28h]
  va_list va; // [rsp+78h] [rbp+30h] BYREF

  va_start(va, a5);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids,
      27,
      va,
      4,
      0);
  LOWORD(v7) = 27;
  return WppAutoLogTrace(a1, 2, 4, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids, v7, va);
}

```

## disassembly

```asm
0x1400026d0  mov     r11, rsp
0x1400026d3  mov     [r11+8], rbx
0x1400026d7  push    rsi
0x1400026d8  sub     rsp, 40h
0x1400026dc  mov     rbx, rcx
0x1400026df  mov     esi, 1Bh
0x1400026e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400026eb  mov     eax, [rcx+2Ch]
0x1400026ee  test    al, 8
0x1400026f0  jz      short loc_14000272D
0x1400026f2  cmp     byte ptr [rcx+29h], 2
0x1400026f6  jb      short loc_14000272D
0x1400026f8  mov     rax, cs:pfnWppTraceMessage
0x1400026ff  lea     rdx, [r11+30h]
0x140002703  mov     rcx, [rcx+18h]
0x140002707  lea     r8, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x14000270e  mov     qword ptr [r11-18h], 0
0x140002716  mov     r9d, esi
0x140002719  mov     qword ptr [r11-20h], 4
0x140002721  mov     [r11-28h], rdx
0x140002725  lea     edx, [rsi+10h]
0x140002728  call    _guard_dispatch_icall
0x14000272d  mov     [rsp+48h+var_10], 0
0x140002736  lea     rax, [rsp+48h+arg_28]
0x14000273b  mov     edx, 2
0x140002740  mov     [rsp+48h+var_18], 4
0x140002749  mov     [rsp+48h+var_20], rax
0x14000274e  lea     r9, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x140002755  mov     rcx, rbx
0x140002758  mov     [rsp+48h+var_28], si
0x14000275d  lea     r8d, [rdx+2]
0x140002761  call    cs:__imp_WppAutoLogTrace
0x140002768  nop     dword ptr [rax+rax+00h]
0x14000276d  mov     rbx, [rsp+48h+arg_0]
0x140002772  add     rsp, 40h
0x140002776  pop     rsi
0x140002777  retn
```
