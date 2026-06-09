# WPP_SF_q

- ea: `0x1400031ec`
- end: `0x14000322a`
- name: `WPP_SF_q`
- size: `62`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x140001e60`
- `0x140001fc0`
- `0x1400021c0`
- `0x1400023b0`
- `0x1400100d0`
- `0x14001083c`
- `0x140010d20`
- `0x140011288`
- `0x1400128bc`
- `0x140019a80`
- `0x14001ac30`
- `0x14001af80`
- `0x14001b1e0`
- `0x14001be00`

## callees

- `0x140004830`

## pseudocode

```c
__int64 WPP_SF_q(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           0);
}

```

## disassembly

```asm
0x1400031ec  mov     r11, rsp
0x1400031ef  mov     [r11+20h], r9
0x1400031f3  sub     rsp, 48h
0x1400031f7  mov     rax, cs:pfnWppTraceMessage
0x1400031fe  lea     r9, [r11+20h]
0x140003202  mov     qword ptr [r11-18h], 0
0x14000320a  mov     qword ptr [r11-20h], 8
0x140003212  mov     [r11-28h], r9
0x140003216  movzx   r9d, dx
0x14000321a  mov     edx, 2Bh ; '+'
0x14000321f  call    _guard_dispatch_icall
0x140003224  add     rsp, 48h
0x140003228  retn
```
