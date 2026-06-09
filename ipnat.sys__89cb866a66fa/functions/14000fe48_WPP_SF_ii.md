# WPP_SF_ii

- ea: `0x14000fe48`
- end: `0x14000fe93`
- name: `WPP_SF_ii`
- size: `75`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x1400058c0`
- `0x14000d8b0`
- `0x14000e988`
- `0x14000ed8c`
- `0x14000ef60`
- `0x14000f2a4`
- `0x14000f6cc`
- `0x14001d05c`
- `0x14001e0f8`
- `0x14001f110`
- `0x140022320`
- `0x140024cc0`
- `0x14002597c`
- `0x14002665c`
- `0x1400275d0`

## callees

- `0x14002c710`

## pseudocode

```c
__int64 WPP_SF_ii(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
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
0x14000fe48  mov     r11, rsp
0x14000fe4b  mov     [r11+20h], r9
0x14000fe4f  sub     rsp, 58h
0x14000fe53  mov     rax, cs:pfnWppTraceMessage
0x14000fe5a  lea     r9, [r11+28h]
0x14000fe5e  mov     qword ptr [r11-18h], 0
0x14000fe66  mov     r10d, 8
0x14000fe6c  mov     [r11-20h], r10
0x14000fe70  mov     [r11-28h], r9
0x14000fe74  lea     r9, [r11+20h]
0x14000fe78  mov     [r11-30h], r10
0x14000fe7c  mov     [r11-38h], r9
0x14000fe80  movzx   r9d, dx
0x14000fe84  lea     edx, [r10+23h]
0x14000fe88  call    _guard_dispatch_icall
0x14000fe8d  add     rsp, 58h
0x14000fe91  retn
```
