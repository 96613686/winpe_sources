# WPP_RECORDER_SF_q

- ea: `0x1400068bc`
- end: `0x140006970`
- name: `WPP_RECORDER_SF_q`
- size: `180`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001300`
- `0x140001a00`
- `0x140002240`

## callees

- `0x1400068bc`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140006953`
- `WppRecorder!WppAutoLogTrace` at `0x140006953`

## pseudocode

```c
__int64 WPP_RECORDER_SF_q(__int64 a1, unsigned __int8 a2, __int64 a3, unsigned __int16 a4, int a5, ...)
{
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-28h]
  va_list va; // [rsp+78h] [rbp+30h] BYREF

  va_start(va, a5);
  v7 = a2;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= a2 )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids,
      a4,
      va,
      8,
      0);
  LOWORD(v9) = a4;
  return WppAutoLogTrace(a1, v7, 2, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids, v9, va);
}

```

## disassembly

```asm
0x1400068bc  mov     r11, rsp
0x1400068bf  mov     [r11+8], rbx
0x1400068c3  mov     [r11+10h], rsi
0x1400068c7  push    rdi
0x1400068c8  sub     rsp, 40h
0x1400068cc  mov     rsi, rcx
0x1400068cf  movzx   edi, r9w
0x1400068d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068da  movzx   ebx, dl
0x1400068dd  mov     eax, [rcx+2Ch]
0x1400068e0  test    al, 2
0x1400068e2  jz      short loc_140006920
0x1400068e4  cmp     [rcx+29h], bl
0x1400068e7  jb      short loc_140006920
0x1400068e9  mov     rax, cs:pfnWppTraceMessage
0x1400068f0  lea     rdx, [r11+30h]
0x1400068f4  mov     rcx, [rcx+18h]
0x1400068f8  lea     r8, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x1400068ff  mov     qword ptr [r11-18h], 0
0x140006907  mov     r9d, edi
0x14000690a  mov     qword ptr [r11-20h], 8
0x140006912  mov     [r11-28h], rdx
0x140006916  mov     edx, 2Bh ; '+'
0x14000691b  call    _guard_dispatch_icall
0x140006920  mov     [rsp+48h+var_10], 0
0x140006929  lea     rax, [rsp+48h+arg_28]
0x14000692e  mov     [rsp+48h+var_18], 8
0x140006937  lea     r9, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x14000693e  mov     [rsp+48h+var_20], rax
0x140006943  mov     r8d, 2
0x140006949  mov     edx, ebx
0x14000694b  mov     [rsp+48h+var_28], di
0x140006950  mov     rcx, rsi
0x140006953  call    cs:__imp_WppAutoLogTrace
0x14000695a  nop     dword ptr [rax+rax+00h]
0x14000695f  mov     rbx, [rsp+48h+arg_0]
0x140006964  mov     rsi, [rsp+48h+arg_8]
0x140006969  add     rsp, 40h
0x14000696d  pop     rdi
0x14000696e  retn
```
