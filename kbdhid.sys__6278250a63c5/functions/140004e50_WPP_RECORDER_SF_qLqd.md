# WPP_RECORDER_SF_qLqd

- ea: `0x140004e50`
- end: `0x140004f74`
- name: `WPP_RECORDER_SF_qLqd`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000fd50`

## callees

- `0x140004e50`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004f59`
- `WppRecorder!WppAutoLogTrace` at `0x140004f59`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qLqd(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, int a5, ...)
{
  int v8; // [rsp+20h] [rbp-58h]
  __int64 v9; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  __int64 v11; // [rsp+B0h] [rbp+38h] BYREF
  va_list va1; // [rsp+B0h] [rbp+38h]
  __int64 v13; // [rsp+B8h] [rbp+40h] BYREF
  va_list va2; // [rsp+B8h] [rbp+40h]
  va_list va3; // [rsp+C0h] [rbp+48h] BYREF

  va_start(va3, a5);
  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v9 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v11 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v13 = va_arg(va3, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    pfnWppTraceMessage(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids,
      a4,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      4,
      (__int64 *)va2,
      8,
      va3,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 4, 2, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids, v8, (__int64 *)va);
}

```

## disassembly

```asm
0x140004e50  mov     r11, rsp
0x140004e53  mov     [r11+8], rbx
0x140004e57  push    rdi
0x140004e58  sub     rsp, 70h
0x140004e5c  mov     rdi, rcx
0x140004e5f  movzx   ebx, r9w
0x140004e63  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e6a  mov     eax, [rcx+2Ch]
0x140004e6d  test    al, 2
0x140004e6f  jz      short loc_140004EDE
0x140004e71  cmp     byte ptr [rcx+29h], 4
0x140004e75  jb      short loc_140004EDE
0x140004e77  mov     rax, cs:pfnWppTraceMessage
0x140004e7e  lea     rdx, [r11+48h]
0x140004e82  mov     rcx, [rcx+18h]
0x140004e86  lea     r8, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x140004e8d  mov     qword ptr [r11-18h], 0
0x140004e95  mov     r9d, ebx
0x140004e98  mov     qword ptr [r11-20h], 4
0x140004ea0  mov     [r11-28h], rdx
0x140004ea4  lea     rdx, [r11+40h]
0x140004ea8  mov     qword ptr [r11-30h], 8
0x140004eb0  mov     [r11-38h], rdx
0x140004eb4  lea     rdx, [r11+38h]
0x140004eb8  mov     qword ptr [r11-40h], 4
0x140004ec0  mov     [r11-48h], rdx
0x140004ec4  lea     rdx, [r11+30h]
0x140004ec8  mov     qword ptr [r11-50h], 8
0x140004ed0  mov     [r11-58h], rdx
0x140004ed4  mov     edx, 2Bh ; '+'
0x140004ed9  call    _guard_dispatch_icall
0x140004ede  mov     [rsp+78h+var_10], 0
0x140004ee7  lea     rax, [rsp+78h+arg_40]
0x140004eef  mov     [rsp+78h+var_18], 4
0x140004ef8  lea     r9, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x140004eff  mov     [rsp+78h+var_20], rax
0x140004f04  mov     edx, 4
0x140004f09  mov     [rsp+78h+var_28], 8
0x140004f12  lea     rax, [rsp+78h+arg_38]
0x140004f1a  mov     [rsp+78h+var_30], rax
0x140004f1f  mov     r8d, 2
0x140004f25  mov     [rsp+78h+var_38], 4
0x140004f2e  lea     rax, [rsp+78h+arg_30]
0x140004f36  mov     [rsp+78h+var_40], rax
0x140004f3b  mov     rcx, rdi
0x140004f3e  lea     rax, [rsp+78h+arg_28]
0x140004f46  mov     [rsp+78h+var_48], 8
0x140004f4f  mov     [rsp+78h+var_50], rax
0x140004f54  mov     [rsp+78h+var_58], bx
0x140004f59  call    cs:__imp_WppAutoLogTrace
0x140004f60  nop     dword ptr [rax+rax+00h]
0x140004f65  mov     rbx, [rsp+78h+arg_0]
0x140004f6d  add     rsp, 70h
0x140004f71  pop     rdi
0x140004f72  retn
```
