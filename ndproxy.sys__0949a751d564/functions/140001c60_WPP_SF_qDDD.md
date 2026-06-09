# WPP_SF_qDDD

- ea: `0x140001c60`
- end: `0x140001cc7`
- name: `WPP_SF_qDDD`
- size: `103`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f020`
- `0x14000f250`
- `0x14000f830`
- `0x14000fcb0`
- `0x140013bc0`

## callees

- `0x140008000`

## pseudocode

```c
__int64 WPP_SF_qDDD(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+98h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+20h]
  __int64 v6; // [rsp+A0h] [rbp+28h] BYREF
  va_list va1; // [rsp+A0h] [rbp+28h]
  __int64 v8; // [rsp+A8h] [rbp+30h] BYREF
  va_list va2; // [rsp+A8h] [rbp+30h]
  va_list va3; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v6 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v8 = va_arg(va3, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           (__int64 *)va1,
           4,
           (__int64 *)va2,
           4,
           va3,
           4,
           0);
}

```

## disassembly

```asm
0x140001c60  mov     r11, rsp
0x140001c63  mov     [r11+20h], r9
0x140001c67  sub     rsp, 78h
0x140001c6b  mov     rax, cs:pfnWppTraceMessage
0x140001c72  lea     r9, [r11+38h]
0x140001c76  mov     qword ptr [r11-18h], 0
0x140001c7e  mov     r10d, 4
0x140001c84  mov     [r11-20h], r10
0x140001c88  mov     [r11-28h], r9
0x140001c8c  lea     r9, [r11+30h]
0x140001c90  mov     [r11-30h], r10
0x140001c94  mov     [r11-38h], r9
0x140001c98  lea     r9, [r11+28h]
0x140001c9c  mov     [r11-40h], r10
0x140001ca0  mov     [r11-48h], r9
0x140001ca4  lea     r9, [r11+20h]
0x140001ca8  mov     qword ptr [r11-50h], 8
0x140001cb0  mov     [r11-58h], r9
0x140001cb4  movzx   r9d, dx
0x140001cb8  lea     edx, [r10+27h]
0x140001cbc  call    _guard_dispatch_icall
0x140001cc1  add     rsp, 78h
0x140001cc5  retn
```
