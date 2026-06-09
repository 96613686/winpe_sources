# WPP_SF_qD

- ea: `0x140001c0c`
- end: `0x140001c5a`
- name: `WPP_SF_qD`
- size: `78`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `23`
- callee_count: `1`
- tags: ``

## callers

- `0x140001030`
- `0x140001ad0`
- `0x140002fd0`
- `0x140003860`
- `0x140004ad0`
- `0x140005ca4`
- `0x1400062c0`
- `0x140006cac`
- `0x14000f020`
- `0x14000f250`
- `0x14000f490`
- `0x14000f750`
- `0x14000f830`
- `0x14000fcb0`
- `0x1400100b0`
- `0x1400103c0`
- `0x140011ab0`
- `0x140011c00`
- `0x140011d30`
- `0x140012590`
- `0x140013770`
- `0x140015fa0`
- `0x140017150`

## callees

- `0x140008000`

## pseudocode

```c
__int64 WPP_SF_qD(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
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
0x140001c0c  mov     r11, rsp
0x140001c0f  mov     [r11+20h], r9
0x140001c13  sub     rsp, 58h
0x140001c17  mov     rax, cs:pfnWppTraceMessage
0x140001c1e  lea     r9, [r11+28h]
0x140001c22  mov     qword ptr [r11-18h], 0
0x140001c2a  mov     qword ptr [r11-20h], 4
0x140001c32  mov     [r11-28h], r9
0x140001c36  lea     r9, [r11+20h]
0x140001c3a  mov     qword ptr [r11-30h], 8
0x140001c42  mov     [r11-38h], r9
0x140001c46  movzx   r9d, dx
0x140001c4a  mov     edx, 2Bh ; '+'
0x140001c4f  call    _guard_dispatch_icall
0x140001c54  add     rsp, 58h
0x140001c58  retn
```
