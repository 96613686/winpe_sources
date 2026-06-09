# WPP_SF_id

- ea: `0x14000bbfc`
- end: `0x14000bc4a`
- name: `WPP_SF_id`
- size: `78`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000927c`
- `0x140009380`
- `0x140014bac`
- `0x1400157d0`
- `0x1400158c8`
- `0x140016c4c`
- `0x140016d38`

## callees

- `0x14002c710`

## pseudocode

```c
__int64 WPP_SF_id(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
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
           4,
           0);
}

```

## disassembly

```asm
0x14000bbfc  mov     r11, rsp
0x14000bbff  mov     [r11+20h], r9
0x14000bc03  sub     rsp, 58h
0x14000bc07  mov     rax, cs:pfnWppTraceMessage
0x14000bc0e  lea     r9, [r11+28h]
0x14000bc12  mov     qword ptr [r11-18h], 0
0x14000bc1a  mov     qword ptr [r11-20h], 4
0x14000bc22  mov     [r11-28h], r9
0x14000bc26  lea     r9, [r11+20h]
0x14000bc2a  mov     qword ptr [r11-30h], 8
0x14000bc32  mov     [r11-38h], r9
0x14000bc36  movzx   r9d, dx
0x14000bc3a  mov     edx, 2Bh ; '+'
0x14000bc3f  call    _guard_dispatch_icall
0x14000bc44  add     rsp, 58h
0x14000bc48  retn
```
