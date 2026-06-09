# WPP_RECORDER_SF_qqqDD

- ea: `0x140002eb0`
- end: `0x14000302b`
- name: `WPP_RECORDER_SF_qqqDD`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400026a0`

## callees

- `0x140002eb0`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002f68`
- `WppRecorder!WppAutoLogTrace` at `0x140002f68`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qqqDD(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
{
  int v7; // [rsp+20h] [rbp-68h]
  __int64 v8; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  __int64 v10; // [rsp+C0h] [rbp+38h] BYREF
  va_list va1; // [rsp+C0h] [rbp+38h]
  __int64 v12; // [rsp+C8h] [rbp+40h] BYREF
  va_list va2; // [rsp+C8h] [rbp+40h]
  __int64 v14; // [rsp+D0h] [rbp+48h] BYREF
  va_list va3; // [rsp+D0h] [rbp+48h]
  va_list va4; // [rsp+D8h] [rbp+50h] BYREF

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
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
      11,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      (__int64 *)va2,
      8,
      (__int64 *)va3,
      4,
      va4,
      4,
      0);
  LOWORD(v7) = 11;
  return WppAutoLogTrace(a1, 4, 1, WPP_98d22518711f34f074bb80910c9ade48_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x140002eb0  mov     [rsp+arg_0], rbx
0x140002eb5  push    rsi
0x140002eb6  sub     rsp, 80h
0x140002ebd  mov     rbx, rcx
0x140002ec0  mov     esi, 0Bh
0x140002ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x140002ecc  mov     eax, [rcx+2Ch]
0x140002ecf  test    al, 1
0x140002ed1  jnz     loc_140002F86
0x140002ed7  mov     [rsp+88h+var_10], 0
0x140002ee0  lea     rax, [rsp+88h+arg_48]
0x140002ee8  mov     [rsp+88h+var_18], 4
0x140002ef1  lea     r9, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x140002ef8  mov     [rsp+88h+var_20], rax
0x140002efd  mov     edx, 4
0x140002f02  mov     [rsp+88h+var_28], 4
0x140002f0b  lea     rax, [rsp+88h+arg_40]
0x140002f13  mov     [rsp+88h+var_30], rax
0x140002f18  mov     r8d, 1
0x140002f1e  mov     [rsp+88h+var_38], 8
0x140002f27  lea     rax, [rsp+88h+arg_38]
0x140002f2f  mov     [rsp+88h+var_40], rax
0x140002f34  mov     rcx, rbx
0x140002f37  mov     [rsp+88h+var_48], 8
0x140002f40  lea     rax, [rsp+88h+arg_30]
0x140002f48  mov     [rsp+88h+var_50], rax
0x140002f4d  lea     rax, [rsp+88h+arg_28]
0x140002f55  mov     [rsp+88h+var_58], 8
0x140002f5e  mov     [rsp+88h+var_60], rax
0x140002f63  mov     word ptr [rsp+88h+var_68], si
0x140002f68  call    cs:__imp_WppAutoLogTrace
0x140002f6f  nop     dword ptr [rax+rax+00h]
0x140002f74  mov     rbx, [rsp+88h+arg_0]
0x140002f7c  add     rsp, 80h
0x140002f83  pop     rsi
0x140002f84  retn
0x140002f86  cmp     byte ptr [rcx+29h], 4
0x140002f8a  jb      loc_140002ED7
0x140002f90  mov     rax, cs:pfnWppTraceMessage
0x140002f97  lea     rdx, [rsp+88h+arg_48]
0x140002f9f  mov     rcx, [rcx+18h]
0x140002fa3  lea     r8, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x140002faa  mov     [rsp+88h+var_18], 0
0x140002fb3  mov     r9d, esi
0x140002fb6  mov     [rsp+88h+var_20], 4
0x140002fbf  mov     [rsp+88h+var_28], rdx
0x140002fc4  lea     rdx, [rsp+88h+arg_40]
0x140002fcc  mov     [rsp+88h+var_30], 4
0x140002fd5  mov     [rsp+88h+var_38], rdx
0x140002fda  lea     rdx, [rsp+88h+arg_38]
0x140002fe2  mov     [rsp+88h+var_40], 8
0x140002feb  mov     [rsp+88h+var_48], rdx
0x140002ff0  lea     rdx, [rsp+88h+arg_30]
0x140002ff8  mov     [rsp+88h+var_50], 8
0x140003001  mov     [rsp+88h+var_58], rdx
0x140003006  lea     rdx, [rsp+88h+arg_28]
0x14000300e  mov     [rsp+88h+var_60], 8
0x140003017  mov     [rsp+88h+var_68], rdx
0x14000301c  mov     edx, 2Bh ; '+'
0x140003021  call    _guard_dispatch_icall
0x140003026  jmp     loc_140002ED7
```
