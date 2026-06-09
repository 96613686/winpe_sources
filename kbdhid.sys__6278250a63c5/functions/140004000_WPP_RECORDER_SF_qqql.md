# WPP_RECORDER_SF_qqql

- ea: `0x140004000`
- end: `0x140004125`
- name: `WPP_RECORDER_SF_qqql`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010c0`

## callees

- `0x140004000`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000410a`
- `WppRecorder!WppAutoLogTrace` at `0x14000410a`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qqql(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
{
  int v7; // [rsp+20h] [rbp-58h]
  __int64 v8; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  __int64 v10; // [rsp+B0h] [rbp+38h] BYREF
  va_list va1; // [rsp+B0h] [rbp+38h]
  __int64 v12; // [rsp+B8h] [rbp+40h] BYREF
  va_list va2; // [rsp+B8h] [rbp+40h]
  va_list va3; // [rsp+C0h] [rbp+48h] BYREF

  va_start(va3, a5);
  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v8 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v10 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v12 = va_arg(va3, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    pfnWppTraceMessage(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
      23,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      (__int64 *)va2,
      8,
      va3,
      4,
      0);
  LOWORD(v7) = 23;
  return WppAutoLogTrace(a1, 4, 1, WPP_98d22518711f34f074bb80910c9ade48_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x140004000  mov     r11, rsp
0x140004003  mov     [r11+8], rbx
0x140004007  push    rsi
0x140004008  sub     rsp, 70h
0x14000400c  mov     rbx, rcx
0x14000400f  mov     esi, 17h
0x140004014  mov     rcx, cs:WPP_GLOBAL_Control
0x14000401b  mov     eax, [rcx+2Ch]
0x14000401e  test    al, 1
0x140004020  jz      short loc_14000408F
0x140004022  cmp     byte ptr [rcx+29h], 4
0x140004026  jb      short loc_14000408F
0x140004028  mov     rax, cs:pfnWppTraceMessage
0x14000402f  lea     rdx, [r11+48h]
0x140004033  mov     rcx, [rcx+18h]
0x140004037  lea     r8, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x14000403e  mov     qword ptr [r11-18h], 0
0x140004046  mov     r9d, esi
0x140004049  mov     qword ptr [r11-20h], 4
0x140004051  mov     [r11-28h], rdx
0x140004055  lea     rdx, [r11+40h]
0x140004059  mov     qword ptr [r11-30h], 8
0x140004061  mov     [r11-38h], rdx
0x140004065  lea     rdx, [r11+38h]
0x140004069  mov     qword ptr [r11-40h], 8
0x140004071  mov     [r11-48h], rdx
0x140004075  lea     rdx, [r11+30h]
0x140004079  mov     qword ptr [r11-50h], 8
0x140004081  mov     [r11-58h], rdx
0x140004085  mov     edx, 2Bh ; '+'
0x14000408a  call    _guard_dispatch_icall
0x14000408f  mov     [rsp+78h+var_10], 0
0x140004098  lea     rax, [rsp+78h+arg_40]
0x1400040a0  mov     [rsp+78h+var_18], 4
0x1400040a9  lea     r9, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x1400040b0  mov     [rsp+78h+var_20], rax
0x1400040b5  mov     edx, 4
0x1400040ba  mov     [rsp+78h+var_28], 8
0x1400040c3  lea     rax, [rsp+78h+arg_38]
0x1400040cb  mov     [rsp+78h+var_30], rax
0x1400040d0  mov     r8d, 1
0x1400040d6  mov     [rsp+78h+var_38], 8
0x1400040df  lea     rax, [rsp+78h+arg_30]
0x1400040e7  mov     [rsp+78h+var_40], rax
0x1400040ec  mov     rcx, rbx
0x1400040ef  lea     rax, [rsp+78h+arg_28]
0x1400040f7  mov     [rsp+78h+var_48], 8
0x140004100  mov     [rsp+78h+var_50], rax
0x140004105  mov     [rsp+78h+var_58], si
0x14000410a  call    cs:__imp_WppAutoLogTrace
0x140004111  nop     dword ptr [rax+rax+00h]
0x140004116  mov     rbx, [rsp+78h+arg_0]
0x14000411e  add     rsp, 70h
0x140004122  pop     rsi
0x140004123  retn
```
