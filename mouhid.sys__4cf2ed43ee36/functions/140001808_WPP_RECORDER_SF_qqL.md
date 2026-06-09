# WPP_RECORDER_SF_qqL

- ea: `0x140001808`
- end: `0x1400018eb`
- name: `WPP_RECORDER_SF_qqL`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001100`

## callees

- `0x140001808`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400018d5`
- `WppRecorder!WppAutoLogTrace` at `0x1400018d5`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qqL(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
{
  int v7; // [rsp+20h] [rbp-68h]
  __int64 v8; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  __int64 v10; // [rsp+C0h] [rbp+38h] BYREF
  va_list va1; // [rsp+C0h] [rbp+38h]
  va_list va2; // [rsp+C8h] [rbp+40h] BYREF

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
      WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids,
      10,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      va2,
      4,
      0);
  LOWORD(v7) = 10;
  return WppAutoLogTrace(a1, 4, 3, WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x140001808  mov     r11, rsp
0x14000180b  push    rbx
0x14000180c  push    rbp
0x14000180d  push    rsi
0x14000180e  push    rdi
0x14000180f  sub     rsp, 68h
0x140001813  mov     ebp, 0Ah
0x140001818  mov     rbx, rcx
0x14000181b  mov     rcx, cs:WPP_GLOBAL_Control
0x140001822  lea     edi, [rbp-6]
0x140001825  mov     eax, [rcx+2Ch]
0x140001828  lea     esi, [rbp-2]
0x14000182b  test    dil, al
0x14000182e  jz      short loc_14000187F
0x140001830  cmp     [rcx+29h], dil
0x140001834  jb      short loc_14000187F
0x140001836  mov     rax, cs:pfnWppTraceMessage
0x14000183d  lea     rdx, [r11+40h]
0x140001841  mov     rcx, [rcx+18h]
0x140001845  lea     r8, WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids
0x14000184c  mov     qword ptr [r11-38h], 0
0x140001854  mov     r9d, ebp
0x140001857  mov     [r11-40h], rdi
0x14000185b  mov     [r11-48h], rdx
0x14000185f  lea     rdx, [r11+38h]
0x140001863  mov     [r11-50h], rsi
0x140001867  mov     [r11-58h], rdx
0x14000186b  lea     rdx, [r11+30h]
0x14000186f  mov     [r11-60h], rsi
0x140001873  mov     [r11-68h], rdx
0x140001877  lea     edx, [rbp+21h]
0x14000187a  call    _guard_dispatch_icall
0x14000187f  mov     [rsp+88h+var_30], 0
0x140001888  lea     rax, [rsp+88h+arg_38]
0x140001890  mov     [rsp+88h+var_38], rdi
0x140001895  lea     r9, WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids
0x14000189c  mov     [rsp+88h+var_40], rax
0x1400018a1  mov     r8d, 3
0x1400018a7  mov     [rsp+88h+var_48], rsi
0x1400018ac  lea     rax, [rsp+88h+arg_30]
0x1400018b4  mov     [rsp+88h+var_50], rax
0x1400018b9  mov     edx, edi
0x1400018bb  lea     rax, [rsp+88h+arg_28]
0x1400018c3  mov     [rsp+88h+var_58], rsi
0x1400018c8  mov     [rsp+88h+var_60], rax
0x1400018cd  mov     rcx, rbx
0x1400018d0  mov     [rsp+88h+var_68], bp
0x1400018d5  call    cs:__imp_WppAutoLogTrace
0x1400018dc  nop     dword ptr [rax+rax+00h]
0x1400018e1  add     rsp, 68h
0x1400018e5  pop     rdi
0x1400018e6  pop     rsi
0x1400018e7  pop     rbp
0x1400018e8  pop     rbx
0x1400018e9  retn
```
