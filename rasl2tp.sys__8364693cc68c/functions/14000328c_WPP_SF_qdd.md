# WPP_SF_qdd

- ea: `0x14000328c`
- end: `0x1400032e7`
- name: `WPP_SF_qdd`
- size: `91`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400021c0`
- `0x14000f008`
- `0x14001ac30`

## callees

- `0x140004830`

## pseudocode

```c
__int64 WPP_SF_qdd(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  __int64 v6; // [rsp+90h] [rbp+28h] BYREF
  va_list va1; // [rsp+90h] [rbp+28h]
  va_list va2; // [rsp+98h] [rbp+30h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v6 = va_arg(va2, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           (__int64 *)va1,
           4,
           va2,
           4,
           0);
}

```

## disassembly

```asm
0x14000328c  mov     r11, rsp
0x14000328f  mov     [r11+20h], r9
0x140003293  sub     rsp, 68h
0x140003297  mov     rax, cs:pfnWppTraceMessage
0x14000329e  lea     r9, [r11+30h]
0x1400032a2  mov     qword ptr [r11-18h], 0
0x1400032aa  mov     r10d, 4
0x1400032b0  mov     [r11-20h], r10
0x1400032b4  mov     [r11-28h], r9
0x1400032b8  lea     r9, [r11+28h]
0x1400032bc  mov     [r11-30h], r10
0x1400032c0  mov     [r11-38h], r9
0x1400032c4  lea     r9, [r11+20h]
0x1400032c8  mov     qword ptr [r11-40h], 8
0x1400032d0  mov     [r11-48h], r9
0x1400032d4  movzx   r9d, dx
0x1400032d8  lea     edx, [r10+27h]
0x1400032dc  call    _guard_dispatch_icall
0x1400032e1  add     rsp, 68h
0x1400032e5  retn
```
