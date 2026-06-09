# WPP_RECORDER_SF_qd

- ea: `0x140002a08`
- end: `0x140002ae7`
- name: `WPP_RECORDER_SF_qd`
- size: `223`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001960`
- `0x1400044bc`

## callees

- `0x140002a08`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002aca`
- `WppRecorder!WppAutoLogTrace` at `0x140002aca`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qd(__int64 a1, unsigned __int8 a2, __int64 a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-38h]
  __int64 v10; // [rsp+88h] [rbp+30h] BYREF
  va_list va; // [rsp+88h] [rbp+30h]
  va_list va1; // [rsp+90h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v10 = va_arg(va1, _QWORD);
  v7 = a2;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= a2 )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      a5,
      a4,
      (__int64 *)va,
      8,
      va1,
      4,
      0);
  LOWORD(v9) = a4;
  return WppAutoLogTrace(a1, v7, 5, a5, v9, (__int64 *)va);
}

```

## disassembly

```asm
0x140002a08  mov     r11, rsp
0x140002a0b  mov     [r11+8], rbx
0x140002a0f  mov     [r11+10h], rsi
0x140002a13  push    rdi
0x140002a14  sub     rsp, 50h
0x140002a18  mov     rsi, rcx
0x140002a1b  movzx   edi, r9w
0x140002a1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a26  movzx   ebx, dl
0x140002a29  mov     eax, [rcx+2Ch]
0x140002a2c  test    al, 10h
0x140002a2e  jz      short loc_140002A7D
0x140002a30  cmp     [rcx+29h], bl
0x140002a33  jb      short loc_140002A7D
0x140002a35  mov     rax, cs:pfnWppTraceMessage
0x140002a3c  lea     rdx, [r11+38h]
0x140002a40  mov     r8, [rsp+58h+arg_20]
0x140002a48  mov     r9d, edi
0x140002a4b  mov     rcx, [rcx+18h]
0x140002a4f  mov     qword ptr [r11-18h], 0
0x140002a57  mov     qword ptr [r11-20h], 4
0x140002a5f  mov     [r11-28h], rdx
0x140002a63  lea     rdx, [r11+30h]
0x140002a67  mov     qword ptr [r11-30h], 8
0x140002a6f  mov     [r11-38h], rdx
0x140002a73  mov     edx, 2Bh ; '+'
0x140002a78  call    _guard_dispatch_icall
0x140002a7d  mov     r9, [rsp+58h+arg_20]
0x140002a85  lea     rax, [rsp+58h+arg_30]
0x140002a8d  mov     [rsp+58h+var_10], 0
0x140002a96  mov     r8d, 5
0x140002a9c  mov     [rsp+58h+var_18], 4
0x140002aa5  mov     edx, ebx
0x140002aa7  mov     [rsp+58h+var_20], rax
0x140002aac  mov     rcx, rsi
0x140002aaf  lea     rax, [rsp+58h+arg_28]
0x140002ab7  mov     [rsp+58h+var_28], 8
0x140002ac0  mov     [rsp+58h+var_30], rax
0x140002ac5  mov     [rsp+58h+var_38], di
0x140002aca  call    cs:__imp_WppAutoLogTrace
0x140002ad1  nop     dword ptr [rax+rax+00h]
0x140002ad6  mov     rbx, [rsp+58h+arg_0]
0x140002adb  mov     rsi, [rsp+58h+arg_8]
0x140002ae0  add     rsp, 50h
0x140002ae4  pop     rdi
0x140002ae5  retn
```
