# WPP_RECORDER_SF_qLL

- ea: `0x140002130`
- end: `0x140002233`
- name: `WPP_RECORDER_SF_qLL`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001ed0`

## callees

- `0x140002130`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002216`
- `WppRecorder!WppAutoLogTrace` at `0x140002216`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qLL(__int64 a1, unsigned __int8 a2, __int64 a3, unsigned __int16 a4, int a5, ...)
{
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-48h]
  __int64 v10; // [rsp+98h] [rbp+30h] BYREF
  va_list va; // [rsp+98h] [rbp+30h]
  __int64 v12; // [rsp+A0h] [rbp+38h] BYREF
  va_list va1; // [rsp+A0h] [rbp+38h]
  va_list va2; // [rsp+A8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v10 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v12 = va_arg(va2, _QWORD);
  v7 = a2;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= a2 )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids,
      a4,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      4,
      va2,
      4,
      0);
  LOWORD(v9) = a4;
  return WppAutoLogTrace(a1, v7, 2, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids, v9, (__int64 *)va);
}

```

## disassembly

```asm
0x140002130  mov     r11, rsp
0x140002133  mov     [r11+8], rbx
0x140002137  mov     [r11+10h], rsi
0x14000213b  push    rdi
0x14000213c  sub     rsp, 60h
0x140002140  mov     rsi, rcx
0x140002143  movzx   edi, r9w
0x140002147  mov     rcx, cs:WPP_GLOBAL_Control
0x14000214e  movzx   ebx, dl
0x140002151  mov     eax, [rcx+2Ch]
0x140002154  test    al, 2
0x140002156  jz      short loc_1400021B4
0x140002158  cmp     [rcx+29h], bl
0x14000215b  jb      short loc_1400021B4
0x14000215d  mov     rax, cs:pfnWppTraceMessage
0x140002164  lea     rdx, [r11+40h]
0x140002168  mov     rcx, [rcx+18h]
0x14000216c  lea     r8, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x140002173  mov     qword ptr [r11-18h], 0
0x14000217b  mov     r9d, edi
0x14000217e  mov     qword ptr [r11-20h], 4
0x140002186  mov     [r11-28h], rdx
0x14000218a  lea     rdx, [r11+38h]
0x14000218e  mov     qword ptr [r11-30h], 4
0x140002196  mov     [r11-38h], rdx
0x14000219a  lea     rdx, [r11+30h]
0x14000219e  mov     qword ptr [r11-40h], 8
0x1400021a6  mov     [r11-48h], rdx
0x1400021aa  mov     edx, 2Bh ; '+'
0x1400021af  call    _guard_dispatch_icall
0x1400021b4  mov     [rsp+68h+var_10], 0
0x1400021bd  lea     rax, [rsp+68h+arg_38]
0x1400021c5  mov     [rsp+68h+var_18], 4
0x1400021ce  lea     r9, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x1400021d5  mov     [rsp+68h+var_20], rax
0x1400021da  mov     r8d, 2
0x1400021e0  mov     [rsp+68h+var_28], 4
0x1400021e9  lea     rax, [rsp+68h+arg_30]
0x1400021f1  mov     [rsp+68h+var_30], rax
0x1400021f6  mov     edx, ebx
0x1400021f8  lea     rax, [rsp+68h+arg_28]
0x140002200  mov     [rsp+68h+var_38], 8
0x140002209  mov     [rsp+68h+var_40], rax
0x14000220e  mov     rcx, rsi
0x140002211  mov     [rsp+68h+var_48], di
0x140002216  call    cs:__imp_WppAutoLogTrace
0x14000221d  nop     dword ptr [rax+rax+00h]
0x140002222  mov     rbx, [rsp+68h+arg_0]
0x140002227  mov     rsi, [rsp+68h+arg_8]
0x14000222c  add     rsp, 60h
0x140002230  pop     rdi
0x140002231  retn
```
