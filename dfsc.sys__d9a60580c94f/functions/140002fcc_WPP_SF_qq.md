# WPP_SF_qq

- ea: `0x140002fcc`
- end: `0x140003017`
- name: `WPP_SF_qq`
- size: `75`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1400110d8`
- `0x140014d30`
- `0x140015050`
- `0x14001520c`
- `0x14001a4a0`
- `0x14001f040`
- `0x14001f8a0`
- `0x14001fb50`
- `0x140020660`
- `0x14002184c`
- `0x140023120`

## callees

- `0x140005fb0`

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
0x140002fcc  mov     r11, rsp
0x140002fcf  mov     [r11+20h], r9
0x140002fd3  sub     rsp, 58h
0x140002fd7  mov     rax, cs:pfnWppTraceMessage
0x140002fde  lea     r9, [r11+28h]
0x140002fe2  mov     qword ptr [r11-18h], 0
0x140002fea  mov     r10d, 8
0x140002ff0  mov     [r11-20h], r10
0x140002ff4  mov     [r11-28h], r9
0x140002ff8  lea     r9, [r11+20h]
0x140002ffc  mov     [r11-30h], r10
0x140003000  mov     [r11-38h], r9
0x140003004  movzx   r9d, dx
0x140003008  lea     edx, [r10+23h]
0x14000300c  call    _guard_dispatch_icall
0x140003011  add     rsp, 58h
0x140003015  retn
```
