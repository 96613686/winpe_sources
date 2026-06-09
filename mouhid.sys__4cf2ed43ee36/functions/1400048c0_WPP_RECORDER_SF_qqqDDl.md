# WPP_RECORDER_SF_qqqDDl

- ea: `0x1400048c0`
- end: `0x140004a03`
- name: `WPP_RECORDER_SF_qqqDDl`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003fd0`

## callees

- `0x1400048c0`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400049e8`
- `WppRecorder!WppAutoLogTrace` at `0x1400049e8`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qqqDDl(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
{
  int v7; // [rsp+28h] [rbp-69h]
  __int64 v8; // [rsp+F0h] [rbp+5Fh] BYREF
  va_list va; // [rsp+F0h] [rbp+5Fh]
  __int64 v10; // [rsp+F8h] [rbp+67h] BYREF
  va_list va1; // [rsp+F8h] [rbp+67h]
  __int64 v12; // [rsp+100h] [rbp+6Fh] BYREF
  va_list va2; // [rsp+100h] [rbp+6Fh]
  __int64 v14; // [rsp+108h] [rbp+77h] BYREF
  va_list va3; // [rsp+108h] [rbp+77h]
  __int64 v16; // [rsp+110h] [rbp+7Fh] BYREF
  va_list va4; // [rsp+110h] [rbp+7Fh]
  va_list va5; // [rsp+118h] [rbp+87h] BYREF

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
      WPP_bce545a1de1235e2be96703916423b99_Traceguids,
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
  return WppAutoLogTrace(a1, 4, 1, WPP_bce545a1de1235e2be96703916423b99_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x1400048c0  mov     r11, rsp
0x1400048c3  push    rbp
0x1400048c4  push    rbx
0x1400048c5  push    rsi
0x1400048c6  push    rdi
0x1400048c7  push    r14
0x1400048c9  lea     rbp, [r11-2Fh]
0x1400048cd  sub     rsp, 90h
0x1400048d4  mov     edi, 4
0x1400048d9  mov     rbx, rcx
0x1400048dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400048e3  lea     esi, [rdi+4]
0x1400048e6  mov     eax, [rcx+2Ch]
0x1400048e9  lea     r14d, [rdi+0Dh]
0x1400048ed  test    al, 1
0x1400048ef  jz      short loc_14000496A
0x1400048f1  cmp     [rcx+29h], dil
0x1400048f5  jb      short loc_14000496A
0x1400048f7  mov     rax, cs:pfnWppTraceMessage
0x1400048fe  lea     rdx, [rbp+27h+arg_50]
0x140004905  mov     rcx, [rcx+18h]
0x140004909  lea     r8, WPP_bce545a1de1235e2be96703916423b99_Traceguids
0x140004910  mov     qword ptr [r11-38h], 0
0x140004918  mov     r9d, r14d
0x14000491b  mov     [r11-40h], rdi
0x14000491f  mov     [r11-48h], rdx
0x140004923  lea     rdx, [rbp+27h+arg_48]
0x140004927  mov     [r11-50h], rdi
0x14000492b  mov     [r11-58h], rdx
0x14000492f  lea     rdx, [rbp+27h+arg_40]
0x140004933  mov     [r11-60h], rdi
0x140004937  mov     [r11-68h], rdx
0x14000493b  lea     rdx, [rbp+27h+arg_38]
0x14000493f  mov     [r11-70h], rsi
0x140004943  mov     [r11-78h], rdx
0x140004947  lea     rdx, [rbp+27h+arg_30]
0x14000494b  mov     [r11-80h], rsi
0x14000494f  mov     [rsp+0B0h+var_80], rdx
0x140004954  lea     rdx, [rbp+27h+arg_28]
0x140004958  mov     [rsp+0B0h+var_88], rsi
0x14000495d  mov     [rsp+0B0h+var_90], rdx
0x140004962  lea     edx, [rdi+27h]
0x140004965  call    _guard_dispatch_icall
0x14000496a  mov     qword ptr [rsp+88h], 0
0x140004976  lea     rax, [rbp+27h+arg_50]
0x14000497d  mov     [rsp+0B0h+var_30], rdi
0x140004985  lea     r9, WPP_bce545a1de1235e2be96703916423b99_Traceguids
0x14000498c  mov     [rsp+0B0h+var_38], rax
0x140004991  mov     r8d, 1
0x140004997  mov     [rsp+0B0h+var_40], rdi
0x14000499c  lea     rax, [rbp+27h+arg_48]
0x1400049a0  mov     [rsp+0B0h+var_48], rax
0x1400049a5  mov     edx, edi
0x1400049a7  mov     [rsp+0B0h+var_50], rdi
0x1400049ac  lea     rax, [rbp+27h+arg_40]
0x1400049b0  mov     [rsp+0B0h+var_58], rax
0x1400049b5  mov     rcx, rbx
0x1400049b8  mov     [rsp+0B0h+var_60], rsi
0x1400049bd  lea     rax, [rbp+27h+arg_38]
0x1400049c1  mov     [rsp+0B0h+var_68], rax
0x1400049c6  lea     rax, [rbp+27h+arg_30]
0x1400049ca  mov     [rsp+0B0h+var_70], rsi
0x1400049cf  mov     [rsp+0B0h+var_78], rax
0x1400049d4  lea     rax, [rbp+27h+arg_28]
0x1400049d8  mov     [rsp+0B0h+var_80], rsi
0x1400049dd  mov     [rsp+0B0h+var_88], rax
0x1400049e2  mov     word ptr [rsp+0B0h+var_90], r14w
0x1400049e8  call    cs:__imp_WppAutoLogTrace
0x1400049ef  nop     dword ptr [rax+rax+00h]
0x1400049f4  add     rsp, 90h
0x1400049fb  pop     r14
0x1400049fd  pop     rdi
0x1400049fe  pop     rsi
0x1400049ff  pop     rbx
0x140004a00  pop     rbp
0x140004a01  retn
```
