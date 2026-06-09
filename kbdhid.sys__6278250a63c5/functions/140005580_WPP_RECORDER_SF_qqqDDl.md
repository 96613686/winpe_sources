# WPP_RECORDER_SF_qqqDDl

- ea: `0x140005580`
- end: `0x140005705`
- name: `WPP_RECORDER_SF_qqqDDl`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400026a0`

## callees

- `0x140005580`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400056e7`
- `WppRecorder!WppAutoLogTrace` at `0x1400056e7`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qqqDDl(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
{
  int v7; // [rsp+20h] [rbp-78h]
  __int64 v8; // [rsp+C8h] [rbp+30h] BYREF
  va_list va; // [rsp+C8h] [rbp+30h]
  __int64 v10; // [rsp+D0h] [rbp+38h] BYREF
  va_list va1; // [rsp+D0h] [rbp+38h]
  __int64 v12; // [rsp+D8h] [rbp+40h] BYREF
  va_list va2; // [rsp+D8h] [rbp+40h]
  __int64 v14; // [rsp+E0h] [rbp+48h] BYREF
  va_list va3; // [rsp+E0h] [rbp+48h]
  __int64 v16; // [rsp+E8h] [rbp+50h] BYREF
  va_list va4; // [rsp+E8h] [rbp+50h]
  va_list va5; // [rsp+F0h] [rbp+58h] BYREF

  va_start(va5, a5);
  va_start(va4, a5);
  va_start(va3, a5);
  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v8 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v10 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v12 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v14 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v16 = va_arg(va5, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
      17,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      (__int64 *)va2,
      8,
      (__int64 *)va3,
      4,
      (__int64 *)va4,
      4,
      va5,
      4,
      0);
  LOWORD(v7) = 17;
  return WppAutoLogTrace(a1, 4, 1, WPP_98d22518711f34f074bb80910c9ade48_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x140005580  mov     r11, rsp
0x140005583  mov     [r11+8], rbx
0x140005587  push    rsi
0x140005588  sub     rsp, 90h
0x14000558f  mov     rbx, rcx
0x140005592  mov     esi, 11h
0x140005597  mov     rcx, cs:WPP_GLOBAL_Control
0x14000559e  mov     eax, [rcx+2Ch]
0x1400055a1  test    al, 1
0x1400055a3  jz      loc_14000563A
0x1400055a9  cmp     byte ptr [rcx+29h], 4
0x1400055ad  jb      loc_14000563A
0x1400055b3  mov     rax, cs:pfnWppTraceMessage
0x1400055ba  lea     rdx, [r11+58h]
0x1400055be  mov     rcx, [rcx+18h]
0x1400055c2  lea     r8, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x1400055c9  mov     qword ptr [r11-18h], 0
0x1400055d1  mov     r9d, esi
0x1400055d4  mov     qword ptr [r11-20h], 4
0x1400055dc  mov     [r11-28h], rdx
0x1400055e0  lea     rdx, [r11+50h]
0x1400055e4  mov     qword ptr [r11-30h], 4
0x1400055ec  mov     [r11-38h], rdx
0x1400055f0  lea     rdx, [r11+48h]
0x1400055f4  mov     qword ptr [r11-40h], 4
0x1400055fc  mov     [r11-48h], rdx
0x140005600  lea     rdx, [r11+40h]
0x140005604  mov     qword ptr [r11-50h], 8
0x14000560c  mov     [r11-58h], rdx
0x140005610  lea     rdx, [r11+38h]
0x140005614  mov     qword ptr [r11-60h], 8
0x14000561c  mov     [r11-68h], rdx
0x140005620  lea     rdx, [r11+30h]
0x140005624  mov     qword ptr [r11-70h], 8
0x14000562c  mov     [r11-78h], rdx
0x140005630  mov     edx, 2Bh ; '+'
0x140005635  call    _guard_dispatch_icall
0x14000563a  mov     [rsp+98h+var_10], 0
0x140005646  lea     rax, [rsp+98h+arg_50]
0x14000564e  mov     [rsp+98h+var_18], 4
0x14000565a  lea     r9, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x140005661  mov     [rsp+98h+var_20], rax
0x140005666  mov     edx, 4
0x14000566b  mov     [rsp+98h+var_28], 4
0x140005674  lea     rax, [rsp+98h+arg_48]
0x14000567c  mov     [rsp+98h+var_30], rax
0x140005681  mov     r8d, 1
0x140005687  mov     [rsp+98h+var_38], 4
0x140005690  lea     rax, [rsp+98h+arg_40]
0x140005698  mov     [rsp+98h+var_40], rax
0x14000569d  mov     rcx, rbx
0x1400056a0  mov     [rsp+98h+var_48], 8
0x1400056a9  lea     rax, [rsp+98h+arg_38]
0x1400056b1  mov     [rsp+98h+var_50], rax
0x1400056b6  lea     rax, [rsp+98h+arg_30]
0x1400056be  mov     [rsp+98h+var_58], 8
0x1400056c7  mov     [rsp+98h+var_60], rax
0x1400056cc  lea     rax, [rsp+98h+arg_28]
0x1400056d4  mov     [rsp+98h+var_68], 8
0x1400056dd  mov     [rsp+98h+var_70], rax
0x1400056e2  mov     [rsp+98h+var_78], si
0x1400056e7  call    cs:__imp_WppAutoLogTrace
0x1400056ee  nop     dword ptr [rax+rax+00h]
0x1400056f3  mov     rbx, [rsp+98h+arg_0]
0x1400056fb  add     rsp, 90h
0x140005702  pop     rsi
0x140005703  retn
```
