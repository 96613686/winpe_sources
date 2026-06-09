# WPP_SF_qq

- ea: `0x14000b9b4`
- end: `0x14000b9ff`
- name: `WPP_SF_qq`
- size: `75`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x14000533c`
- `0x140006e88`
- `0x1400078f4`
- `0x140007a88`
- `0x140007e3c`
- `0x140009a54`
- `0x14000b390`
- `0x140014a58`
- `0x140018410`
- `0x1400184cc`
- `0x140018a04`
- `0x14001a220`
- `0x14001e0c0`
- `0x14001eaa0`

## callees

- `0x140024bf0`

## pseudocode

```c
__int64 WPP_SF_qq(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           va1,
           8,
           0);
}

```

## disassembly

```asm
0x14000b9b4  mov     r11, rsp
0x14000b9b7  mov     [r11+20h], r9
0x14000b9bb  sub     rsp, 58h
0x14000b9bf  mov     rax, cs:pfnWppTraceMessage
0x14000b9c6  lea     r9, [r11+28h]
0x14000b9ca  mov     qword ptr [r11-18h], 0
0x14000b9d2  mov     r10d, 8
0x14000b9d8  mov     [r11-20h], r10
0x14000b9dc  mov     [r11-28h], r9
0x14000b9e0  lea     r9, [r11+20h]
0x14000b9e4  mov     [r11-30h], r10
0x14000b9e8  mov     [r11-38h], r9
0x14000b9ec  movzx   r9d, dx
0x14000b9f0  lea     edx, [r10+23h]
0x14000b9f4  call    _guard_dispatch_icall
0x14000b9f9  add     rsp, 58h
0x14000b9fd  retn
```
