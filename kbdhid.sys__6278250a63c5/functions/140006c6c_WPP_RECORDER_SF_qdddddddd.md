# WPP_RECORDER_SF_qdddddddd

- ea: `0x140006c6c`
- end: `0x140006e27`
- name: `WPP_RECORDER_SF_qdddddddd`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400042d0`

## callees

- `0x140006c6c`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140006e0e`
- `WppRecorder!WppAutoLogTrace` at `0x140006e0e`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qdddddddd(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
{
  int v7; // [rsp+28h] [rbp-A1h]
  __int64 v8; // [rsp+120h] [rbp+57h] BYREF
  va_list va; // [rsp+120h] [rbp+57h]
  __int64 v10; // [rsp+128h] [rbp+5Fh] BYREF
  va_list va1; // [rsp+128h] [rbp+5Fh]
  __int64 v12; // [rsp+130h] [rbp+67h] BYREF
  va_list va2; // [rsp+130h] [rbp+67h]
  __int64 v14; // [rsp+138h] [rbp+6Fh] BYREF
  va_list va3; // [rsp+138h] [rbp+6Fh]
  __int64 v16; // [rsp+140h] [rbp+77h] BYREF
  va_list va4; // [rsp+140h] [rbp+77h]
  __int64 v18; // [rsp+148h] [rbp+7Fh] BYREF
  va_list va5; // [rsp+148h] [rbp+7Fh]
  __int64 v20; // [rsp+150h] [rbp+87h] BYREF
  va_list va6; // [rsp+150h] [rbp+87h]
  __int64 v22; // [rsp+158h] [rbp+8Fh] BYREF
  va_list va7; // [rsp+158h] [rbp+8Fh]
  va_list va8; // [rsp+160h] [rbp+97h] BYREF

  va_start(va8, a5);
  va_start(va7, a5);
  va_start(va6, a5);
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
  va_copy(va6, va5);
  v18 = va_arg(va6, _QWORD);
  va_copy(va7, va6);
  v20 = va_arg(va7, _QWORD);
  va_copy(va8, va7);
  v22 = va_arg(va8, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
      43,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      4,
      (__int64 *)va2,
      4,
      (__int64 *)va3,
      4,
      (__int64 *)va4,
      4,
      (__int64 *)va5,
      4,
      (__int64 *)va6,
      4,
      (__int64 *)va7,
      4,
      va8,
      4,
      0);
  LOWORD(v7) = 43;
  return WppAutoLogTrace(a1, 4, 1, WPP_98d22518711f34f074bb80910c9ade48_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x140006c6c  mov     r11, rsp
0x140006c6f  push    rbp
0x140006c70  push    rbx
0x140006c71  push    rsi
0x140006c72  push    rdi
0x140006c73  lea     rbp, [r11-27h]
0x140006c77  sub     rsp, 0C8h
0x140006c7e  mov     rbx, rcx
0x140006c81  mov     edi, 4
0x140006c86  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c8d  lea     esi, [rdi+27h]
0x140006c90  mov     eax, [rcx+2Ch]
0x140006c93  test    al, 1
0x140006c95  jz      loc_140006D4B
0x140006c9b  cmp     [rcx+29h], dil
0x140006c9f  jb      loc_140006D4B
0x140006ca5  mov     rax, cs:pfnWppTraceMessage
0x140006cac  lea     rdx, [rbp+1Fh+arg_68]
0x140006cb3  mov     rcx, [rcx+18h]
0x140006cb7  lea     r8, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x140006cbe  mov     qword ptr [r11-38h], 0
0x140006cc6  mov     r9d, esi
0x140006cc9  mov     [r11-40h], rdi
0x140006ccd  mov     [r11-48h], rdx
0x140006cd1  lea     rdx, [rbp+1Fh+arg_60]
0x140006cd8  mov     [r11-50h], rdi
0x140006cdc  mov     [r11-58h], rdx
0x140006ce0  lea     rdx, [rbp+1Fh+arg_58]
0x140006ce7  mov     [r11-60h], rdi
0x140006ceb  mov     [r11-68h], rdx
0x140006cef  lea     rdx, [rbp+1Fh+arg_50]
0x140006cf3  mov     [r11-70h], rdi
0x140006cf7  mov     [r11-78h], rdx
0x140006cfb  lea     rdx, [rbp+1Fh+arg_48]
0x140006cff  mov     [r11-80h], rdi
0x140006d03  mov     [rsp+0E0h+var_80], rdx
0x140006d08  lea     rdx, [rbp+1Fh+arg_40]
0x140006d0c  mov     [rsp+0E0h+var_88], rdi
0x140006d11  mov     [rsp+0E0h+var_90], rdx
0x140006d16  lea     rdx, [rbp+1Fh+arg_38]
0x140006d1a  mov     [rsp+0E0h+var_98], rdi
0x140006d1f  mov     [rsp+0E0h+var_A0], rdx
0x140006d24  lea     rdx, [rbp+1Fh+arg_30]
0x140006d28  mov     [rsp+0E0h+var_A8], rdi
0x140006d2d  mov     [rsp+0E0h+var_B0], rdx
0x140006d32  lea     rdx, [rbp+1Fh+arg_28]
0x140006d36  mov     [rsp+0E0h+var_B8], 8
0x140006d3f  mov     [rsp+0E0h+var_C0], rdx
0x140006d44  mov     edx, esi
0x140006d46  call    _guard_dispatch_icall
0x140006d4b  mov     qword ptr [rsp+0B8h], 0
0x140006d57  lea     rax, [rbp+1Fh+arg_68]
0x140006d5e  mov     [rsp+0E0h+var_30], rdi
0x140006d66  lea     r9, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x140006d6d  mov     [rsp+0E0h+var_38], rax
0x140006d75  mov     r8d, 1
0x140006d7b  mov     [rsp+0E0h+var_40], rdi
0x140006d83  lea     rax, [rbp+1Fh+arg_60]
0x140006d8a  mov     [rsp+0E0h+var_48], rax
0x140006d92  mov     edx, edi
0x140006d94  mov     [rsp+0E0h+var_50], rdi
0x140006d9c  lea     rax, [rbp+1Fh+arg_58]
0x140006da3  mov     [rsp+0E0h+var_58], rax
0x140006dab  mov     rcx, rbx
0x140006dae  mov     [rsp+0E0h+var_60], rdi
0x140006db6  lea     rax, [rbp+1Fh+arg_50]
0x140006dba  mov     [rsp+0E0h+var_68], rax
0x140006dbf  lea     rax, [rbp+1Fh+arg_48]
0x140006dc3  mov     [rsp+0E0h+var_70], rdi
0x140006dc8  mov     [rsp+0E0h+var_78], rax
0x140006dcd  lea     rax, [rbp+1Fh+arg_40]
0x140006dd1  mov     [rsp+0E0h+var_80], rdi
0x140006dd6  mov     [rsp+0E0h+var_88], rax
0x140006ddb  lea     rax, [rbp+1Fh+arg_38]
0x140006ddf  mov     [rsp+0E0h+var_90], rdi
0x140006de4  mov     [rsp+0E0h+var_98], rax
0x140006de9  lea     rax, [rbp+1Fh+arg_30]
0x140006ded  mov     [rsp+0E0h+var_A0], rdi
0x140006df2  mov     [rsp+0E0h+var_A8], rax
0x140006df7  lea     rax, [rbp+1Fh+arg_28]
0x140006dfb  mov     [rsp+0E0h+var_B0], 8
0x140006e04  mov     [rsp+0E0h+var_B8], rax
0x140006e09  mov     word ptr [rsp+0E0h+var_C0], si
0x140006e0e  call    cs:__imp_WppAutoLogTrace
0x140006e15  nop     dword ptr [rax+rax+00h]
0x140006e1a  add     rsp, 0C8h
0x140006e21  pop     rdi
0x140006e22  pop     rsi
0x140006e23  pop     rbx
0x140006e24  pop     rbp
0x140006e25  retn
```
